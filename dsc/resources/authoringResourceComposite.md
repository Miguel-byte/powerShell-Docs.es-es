---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: 'Recursos compuestos: uso de una configuración DSC como un recurso'
ms.openlocfilehash: 2823d05e0c8feb2933ca691f9ab5149ace2f7ee3
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402266"
---
# <a name="composite-resources-using-a-dsc-configuration-as-a-resource"></a><span data-ttu-id="08f75-103">Recursos compuestos Uso de una configuración DSC como un recurso</span><span class="sxs-lookup"><span data-stu-id="08f75-103">Composite resources: Using a DSC configuration as a resource</span></span>

> <span data-ttu-id="08f75-104">Se aplica a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="08f75-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="08f75-105">En situaciones del mundo real, las configuraciones pueden acabar siendo largas y complejas, con llamadas a muchos recursos diferentes y estableciendo una gran cantidad de propiedades.</span><span class="sxs-lookup"><span data-stu-id="08f75-105">In real-world situations, configurations can become long and complex, calling many different resources and setting a vast number of properties.</span></span> <span data-ttu-id="08f75-106">Para ayudar a abordar esta complejidad, puede utilizar una configuración de estado deseado (DSC) de Windows PowerShell como recurso para otras configuraciones.</span><span class="sxs-lookup"><span data-stu-id="08f75-106">To help address this complexity, you can use a Windows PowerShell Desired State Configuration (DSC) configuration as a resource for other configurations.</span></span> <span data-ttu-id="08f75-107">Es lo que se conoce como un recurso compuesto.</span><span class="sxs-lookup"><span data-stu-id="08f75-107">We call this a composite resource.</span></span> <span data-ttu-id="08f75-108">Un recurso compuesto es una configuración DSC que toma parámetros.</span><span class="sxs-lookup"><span data-stu-id="08f75-108">A composite resource is a DSC configuration that takes parameters.</span></span> <span data-ttu-id="08f75-109">Los parámetros de la configuración actúan como las propiedades del recurso.</span><span class="sxs-lookup"><span data-stu-id="08f75-109">The parameters of the configuration act as the properties of the resource.</span></span> <span data-ttu-id="08f75-110">La configuración se guarda como un archivo con una extensión **.schema.psm1** y ocupa el lugar tanto del esquema MOF como del recurso de script de un recurso de DSC típico (para más información sobre los recursos de DSC, consulte [Recursos de configuración de estado deseado de Windows PowerShell](resources.md).</span><span class="sxs-lookup"><span data-stu-id="08f75-110">The configuration is saved as a file with a **.schema.psm1** extension, and takes the place of both the MOF schema and the resource script in a typical DSC resource (for more information about DSC resources, see [Windows PowerShell Desired State Configuration Resources](resources.md).</span></span>

## <a name="creating-the-composite-resource"></a><span data-ttu-id="08f75-111">Creación del recurso compuesto</span><span class="sxs-lookup"><span data-stu-id="08f75-111">Creating the composite resource</span></span>

<span data-ttu-id="08f75-112">En nuestro ejemplo, se creará una configuración que invoca un número de recursos existentes para configurar las máquinas virtuales.</span><span class="sxs-lookup"><span data-stu-id="08f75-112">In our example, we create a configuration that invokes a number of existing resources to configure virtual machines.</span></span> <span data-ttu-id="08f75-113">En lugar de especificar los valores que se establecerán en bloques de configuración, la configuración toma un número de parámetros que se utilizan en los bloques de configuración.</span><span class="sxs-lookup"><span data-stu-id="08f75-113">Instead of specifying the values to be set in configuration blocks, the configuration takes a number of parameters that are then used in the configuration blocks.</span></span>

```powershell
Configuration xVirtualMachine
{
    param
    (
        # Name of VMs
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String[]] $VMName,

        # Name of Switch to create
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $SwitchName,

        # Type of Switch to create
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $SwitchType,

        # Source Path for VHD
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VHDParentPath,

        # Destination path for diff VHD
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VHDPath,

        # Startup Memory for VM
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VMStartupMemory,

        # State of the VM
        [Parameter(Mandatory)]
        [ValidateNotNullOrEmpty()]
        [String] $VMState
    )

    # Import the module that defines custom resources
    Import-DscResource -Module xComputerManagement,xHyper-V

    # Install the Hyper-V role
    WindowsFeature HyperV
    {
        Ensure = "Present"
        Name = "Hyper-V"
    }

    # Create the virtual switch
    xVMSwitch $SwitchName
    {
        Ensure = "Present"
        Name = $SwitchName
        Type = $SwitchType
        DependsOn = "[WindowsFeature]HyperV"
    }

    # Check for Parent VHD file
    File ParentVHDFile
    {
        Ensure = "Present"
        DestinationPath = $VHDParentPath
        Type = "File"
        DependsOn = "[WindowsFeature]HyperV"
    }

    # Check the destination VHD folder
    File VHDFolder
    {
        Ensure = "Present"
        DestinationPath = $VHDPath
        Type = "Directory"
        DependsOn = "[File]ParentVHDFile"
    }

    # Create VM specific diff VHD
    foreach ($Name in $VMName)
    {
        xVHD "VHD$Name"
        {
            Ensure = "Present"
            Name = $Name
            Path = $VHDPath
            ParentPath = $VHDParentPath
            DependsOn = @("[WindowsFeature]HyperV",
                          "[File]VHDFolder")
        }
    }

    # Create VM using the above VHD
    foreach($Name in $VMName)
    {
        xVMHyperV "VMachine$Name"
        {
            Ensure = "Present"
            Name = $Name
            VhDPath = (Join-Path -Path $VHDPath -ChildPath $Name)
            SwitchName = $SwitchName
            StartupMemory = $VMStartupMemory
            State = $VMState
            MACAddress = $MACAddress
            WaitForIP = $true
            DependsOn = @("[WindowsFeature]HyperV",
                          "[xVHD]VHD$Name")
        }
    }
}
```

### <a name="saving-the-configuration-as-a-composite-resource"></a><span data-ttu-id="08f75-114">Guardar la configuración como un recurso compuesto</span><span class="sxs-lookup"><span data-stu-id="08f75-114">Saving the configuration as a composite resource</span></span>

<span data-ttu-id="08f75-115">Para usar la configuración con parámetros como un recurso de DSC, guárdela en una estructura de directorios similar a la de cualquier otro recurso basado en MOF y asígnele un nombre con una extensión **.schema.psm1**.</span><span class="sxs-lookup"><span data-stu-id="08f75-115">To use the parameterized configuration as a DSC resource, save it in a directory structure like that of any other MOF-based resource, and name it with a **.schema.psm1** extension.</span></span> <span data-ttu-id="08f75-116">En este ejemplo, el archivo se denominará **xVirtualMachine.schema.psm1**.</span><span class="sxs-lookup"><span data-stu-id="08f75-116">For this example, we’ll name the file **xVirtualMachine.schema.psm1**.</span></span> <span data-ttu-id="08f75-117">También deberá crear un manifiesto llamado **xVirtualMachine.psd1** que contenga la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="08f75-117">You also need to create a manifest named **xVirtualMachine.psd1** that contains the following line.</span></span> <span data-ttu-id="08f75-118">Tenga en cuenta que esto es además de **MyDscResources.psd1**, el manifiesto del módulo para todos los recursos de la carpeta **MyDscResources**.</span><span class="sxs-lookup"><span data-stu-id="08f75-118">Note that this is in addition to **MyDscResources.psd1**, the module manifest for all resources under the **MyDscResources** folder.</span></span>

```powershell
RootModule = 'xVirtualMachine.schema.psm1'
```

<span data-ttu-id="08f75-119">Cuando haya terminado, la estructura de carpetas debería ser la siguiente.</span><span class="sxs-lookup"><span data-stu-id="08f75-119">When you are done, the folder structure should be as follows.</span></span>

```
$env: psmodulepath
    |- MyDscResources
           MyDscResources.psd1
        |- DSCResources
            |- xVirtualMachine
                |- xVirtualMachine.psd1
                |- xVirtualMachine.schema.psm1
```

<span data-ttu-id="08f75-120">El recurso ahora es detectable mediante el cmdlet Get-DscResource y sus propiedades las puede detectar cualquier cmdlet o mediante la función de autocompletar **CTRL+BARRA ESPACIADORA** en Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="08f75-120">The resource is now discoverable by using the Get-DscResource cmdlet, and its properties are discoverable by either that cmdlet or by using **Ctrl+Space** auto-complete in the Windows PowerShell ISE.</span></span>

## <a name="using-the-composite-resource"></a><span data-ttu-id="08f75-121">Uso del recurso compuesto</span><span class="sxs-lookup"><span data-stu-id="08f75-121">Using the composite resource</span></span>

<span data-ttu-id="08f75-122">A continuación, se crea una configuración que llama al recurso compuesto.</span><span class="sxs-lookup"><span data-stu-id="08f75-122">Next we create a configuration that calls the composite resource.</span></span> <span data-ttu-id="08f75-123">Esta configuración llama al recurso compuesto xVirtualMachine para crear una máquina virtual y después llama al recurso **xComputer** para cambiar su nombre.</span><span class="sxs-lookup"><span data-stu-id="08f75-123">This configuration calls the xVirtualMachine composite resource to create a virtual machine, and then calls the **xComputer** resource to rename it.</span></span>

```powershell

configuration RenameVM
{

    Import-DscResource -Module xVirtualMachine
    Node localhost
    {
        xVirtualMachine VM
        {
            VMName = "Test"
            SwitchName = "Internal"
            SwitchType = "Internal"
            VhdParentPath = "C:\Demo\VHD\RTM.vhd"
            VHDPath = "C:\Demo\VHD"
            VMStartupMemory = 1024MB
            VMState = "Running"
        }
    }

    Node "192.168.10.1"
    {
        xComputer Name
        {
            Name = "SQL01"
            DomainName = "fourthcoffee.com"
        }
    }
}
```

## <a name="supporting-psdscrunascredential"></a><span data-ttu-id="08f75-124">Compatibilidad con PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="08f75-124">Supporting PsDscRunAsCredential</span></span>

><span data-ttu-id="08f75-125">**Nota:** **PsDscRunAsCredential** se admite en PowerShell 5.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="08f75-125">**Note:** **PsDscRunAsCredential** is supported in PowerShell 5.0 and later.</span></span>

<span data-ttu-id="08f75-126">La propiedad **PsDscRunAsCredential** se puede usar en el bloque de recursos de [configuraciones de DSC](../configurations/configurations.md) para especificar que el recurso se debe ejecutar bajo un conjunto especificado de credenciales.</span><span class="sxs-lookup"><span data-stu-id="08f75-126">The **PsDscRunAsCredential** property can be used in [DSC configurations](../configurations/configurations.md) resource block to specify that the resource should be run under a specified set of credentials.</span></span>
<span data-ttu-id="08f75-127">Para más información, consulte [DSC de ejecución con las credenciales de usuario](../configurations/runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="08f75-127">For more information, see [Running DSC with user credentials](../configurations/runAsUser.md).</span></span>

<span data-ttu-id="08f75-128">Para tener acceso al contexto de usuario desde un recurso personalizado, puede usar la variable automática `$PsDscContext`.</span><span class="sxs-lookup"><span data-stu-id="08f75-128">To access the user context from within a custom resource, you can use the automatic variable `$PsDscContext`.</span></span>

<span data-ttu-id="08f75-129">Por ejemplo, el código siguiente podría escribir el contexto de usuario bajo el cual se ejecuta el recurso en el flujo de salida detallado:</span><span class="sxs-lookup"><span data-stu-id="08f75-129">For example the following code would write the user context under which the resource is running to the verbose output stream:</span></span>

```powershell
if ($PsDscContext.RunAsUser) {
    Write-Verbose "User: $PsDscContext.RunAsUser";
}
```

## <a name="see-also"></a><span data-ttu-id="08f75-130">Véase también</span><span class="sxs-lookup"><span data-stu-id="08f75-130">See Also</span></span>
### <a name="concepts"></a><span data-ttu-id="08f75-131">Conceptos</span><span class="sxs-lookup"><span data-stu-id="08f75-131">Concepts</span></span>
* [<span data-ttu-id="08f75-132">Escribir un recurso de DSC personalizado con MOF</span><span class="sxs-lookup"><span data-stu-id="08f75-132">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md)
* [<span data-ttu-id="08f75-133">Introducción a la configuración de estado deseado de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="08f75-133">Get Started with Windows PowerShell Desired State Configuration</span></span>](../overview/overview.md)