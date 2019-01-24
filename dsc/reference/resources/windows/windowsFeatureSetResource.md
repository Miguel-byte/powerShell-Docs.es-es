---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Recurso WindowsFeatureSet de DSC
ms.openlocfilehash: 8b7c7e72dd58459bd19cb723e5790a82841515c0
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047542"
---
# <a name="dsc-windowsfeatureset-resource"></a><span data-ttu-id="693eb-103">Recurso WindowsFeatureSet de DSC</span><span class="sxs-lookup"><span data-stu-id="693eb-103">DSC WindowsFeatureSet Resource</span></span>

> <span data-ttu-id="693eb-104">Se aplica a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="693eb-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="693eb-105">El recurso **WindowsFeatureSet** de la configuración de estado deseado (DSC) de Windows PowerShell ofrece un mecanismo para asegurarse de que los roles y las características se agreguen o quiten en un nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="693eb-105">The **WindowsFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span>
<span data-ttu-id="693eb-106">Este es un [recurso compuesto](../../../resources/authoringResourceComposite.md) que llama al [recurso WindowsFeature](windowsfeatureResource.md) de cada una de las características especificadas en la propiedad `Name`.</span><span class="sxs-lookup"><span data-stu-id="693eb-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsFeature resource](windowsfeatureResource.md) for each feature specified in the `Name` property.</span></span>

<span data-ttu-id="693eb-107">Este recurso se usa cuando se desea configurar varias características de Windows para que tengan el mismo estado.</span><span class="sxs-lookup"><span data-stu-id="693eb-107">Use this resource when you want to configure a number of Windows Features to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="693eb-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="693eb-108">Syntax</span></span>

```
WindowsFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Ensure = [string] { Absent | Present }  ]
    [ Source = [string] ]
    [ IncludeAllSubFeature = [bool] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]

}
```

## <a name="properties"></a><span data-ttu-id="693eb-109">Propiedades</span><span class="sxs-lookup"><span data-stu-id="693eb-109">Properties</span></span>

|  <span data-ttu-id="693eb-110">Propiedad</span><span class="sxs-lookup"><span data-stu-id="693eb-110">Property</span></span>  |  <span data-ttu-id="693eb-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="693eb-111">Description</span></span>   |
|---|---|
| <span data-ttu-id="693eb-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="693eb-112">Name</span></span>| <span data-ttu-id="693eb-113">Los nombres de los roles o características que quiere garantizar que se agreguen o se quiten.</span><span class="sxs-lookup"><span data-stu-id="693eb-113">The names of the roles or features that you want to ensure are added or removed.</span></span> <span data-ttu-id="693eb-114">Estos son los mismos que con la propiedad **Name** del cmdlet [Get-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205469.aspx) y no el nombre para mostrar de los roles o características.</span><span class="sxs-lookup"><span data-stu-id="693eb-114">This is the same as the **Name** property of the [Get-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205469.aspx) cmdlet, and not the display name of the roles or features.</span></span>|
| <span data-ttu-id="693eb-115">Credential</span><span class="sxs-lookup"><span data-stu-id="693eb-115">Credential</span></span>| <span data-ttu-id="693eb-116">Las credenciales que se usarán para agregar o quitar los roles o las características.</span><span class="sxs-lookup"><span data-stu-id="693eb-116">The credentials to use to add or remove the roles or features.</span></span>|
| <span data-ttu-id="693eb-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="693eb-117">Ensure</span></span>| <span data-ttu-id="693eb-118">Indica si se agregan las funciones o características.</span><span class="sxs-lookup"><span data-stu-id="693eb-118">Indicates whether the roles or features are added.</span></span> <span data-ttu-id="693eb-119">Para asegurarse de que los roles o características se agregan, establezca esta propiedad en "Present"; para asegurarse de que se quitan los roles o características, establezca la propiedad en "Absent".</span><span class="sxs-lookup"><span data-stu-id="693eb-119">To ensure that the roles or features are added, set this property to "Present" To ensure that the roles or features are removed, set the property to "Absent".</span></span>|
| <span data-ttu-id="693eb-120">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="693eb-120">IncludeAllSubFeature</span></span>| <span data-ttu-id="693eb-121">Establezca esta propiedad en **$true** para incluir todas las subcaracterísticas requeridas de las características que se especifican con la propiedad **Name**.</span><span class="sxs-lookup"><span data-stu-id="693eb-121">Set this property to **$true** to include all required subfeatures with of the features you specify with the **Name** property.</span></span>|
| <span data-ttu-id="693eb-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="693eb-122">LogPath</span></span>| <span data-ttu-id="693eb-123">La ruta de acceso al archivo de registro en el que desea que el proveedor de recursos registre la operación.</span><span class="sxs-lookup"><span data-stu-id="693eb-123">The path to a log file where you want the resource provider to log the operation.</span></span>|
| <span data-ttu-id="693eb-124">DependsOn</span><span class="sxs-lookup"><span data-stu-id="693eb-124">DependsOn</span></span>| <span data-ttu-id="693eb-125">Indica que la configuración de otro recurso debe ejecutarse antes de que se configure este recurso.</span><span class="sxs-lookup"><span data-stu-id="693eb-125">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="693eb-126">Por ejemplo, si el elemento ID del bloque del script de configuración del recurso que quiere ejecutar primero es __ResourceName__ y su tipo es __ResourceType__, la sintaxis para usar esta propiedad es `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="693eb-126">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="693eb-127">Origen</span><span class="sxs-lookup"><span data-stu-id="693eb-127">Source</span></span>| <span data-ttu-id="693eb-128">Indica la ubicación del archivo de origen que se utilizará para la instalación, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="693eb-128">Indicates the location of the source file to use for installation, if necessary.</span></span>|

## <a name="example"></a><span data-ttu-id="693eb-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="693eb-129">Example</span></span>

<span data-ttu-id="693eb-130">La siguiente configuración garantiza que las características de **Web Server** (IIS) y del **servidor SMTP**, y todas las subcaracterísticas de cada uno, se instalan.</span><span class="sxs-lookup"><span data-stu-id="693eb-130">The following configuration ensures that the **Web-Server** (IIS) and **SMTP Server** features, and all subfeatures of each, are installed.</span></span>

```powershell
configuration FeatureSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        WindowsFeatureSet WindowsFeatureSetExample
        {
            Name                    = @("SMTP-Server", "Web-Server")
            Ensure                  = 'Present'
            IncludeAllSubFeature    = $true
        }
    }
}
```