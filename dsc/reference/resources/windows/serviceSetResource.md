---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Recurso ServiceSet de DSC
ms.openlocfilehash: 5694c2abc5c0caf0098670b629af464b35125583
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047562"
---
# <a name="dsc-serviceset-resource"></a><span data-ttu-id="19889-103">Recurso ServiceSet de DSC</span><span class="sxs-lookup"><span data-stu-id="19889-103">DSC ServiceSet Resource</span></span>

> <span data-ttu-id="19889-104">Se aplica a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="19889-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="19889-105">El recurso **ServiceSet** del servicio de configuración de estado deseado (DSC) de Windows PowerShell (DSC) proporciona un mecanismo para administrar los servicios del nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="19889-105">The **ServiceSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span> <span data-ttu-id="19889-106">Este es un [recurso compuesto](../../../resources/authoringResourceComposite.md) que llama el [recurso de servicio](serviceResource.md) de cada uno de los servicios que se especifica en la propiedad `Name`.</span><span class="sxs-lookup"><span data-stu-id="19889-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [Service resource](serviceResource.md) for each service specified in the `Name` property.</span></span>

<span data-ttu-id="19889-107">Este recurso se usa cuando se desea configurar varios servicios para que tengan el mismo estado.</span><span class="sxs-lookup"><span data-stu-id="19889-107">Use this resource when you want to configure a number of services to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="19889-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19889-108">Syntax</span></span>

```
Service [string] #ResourceName
{
    Name = [string[]]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Ensure = [string] { Absent | Present }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]

}
```

## <a name="properties"></a><span data-ttu-id="19889-109">Propiedades</span><span class="sxs-lookup"><span data-stu-id="19889-109">Properties</span></span>

|  <span data-ttu-id="19889-110">Propiedad</span><span class="sxs-lookup"><span data-stu-id="19889-110">Property</span></span>  |  <span data-ttu-id="19889-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="19889-111">Description</span></span>   |
|---|---|
| <span data-ttu-id="19889-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="19889-112">Name</span></span>| <span data-ttu-id="19889-113">Indica los nombres de servicio.</span><span class="sxs-lookup"><span data-stu-id="19889-113">Indicates the service names.</span></span> <span data-ttu-id="19889-114">Tenga en cuenta que son distintos de los nombres que se muestran.</span><span class="sxs-lookup"><span data-stu-id="19889-114">Note that sometimes this is different from the display names.</span></span> <span data-ttu-id="19889-115">Con el cmdlet [Get-Service](https://technet.microsoft.com/library/hh849804.aspx) puede obtener una lista de los servicios y sus estados actuales.</span><span class="sxs-lookup"><span data-stu-id="19889-115">You can get a list of the services and their current state with the [Get-Service](https://technet.microsoft.com/library/hh849804.aspx) cmdlet.</span></span>|
| <span data-ttu-id="19889-116">StartupType</span><span class="sxs-lookup"><span data-stu-id="19889-116">StartupType</span></span>| <span data-ttu-id="19889-117">Indica el tipo de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="19889-117">Indicates the startup type for the service.</span></span> <span data-ttu-id="19889-118">Los valores permitidos para esta propiedad son: **Automática**, **deshabilitado**, y **Manual**</span><span class="sxs-lookup"><span data-stu-id="19889-118">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**</span></span>|
| <span data-ttu-id="19889-119">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="19889-119">BuiltInAccount</span></span>| <span data-ttu-id="19889-120">Indica la cuenta de inicio de sesión que se usa para los servicios.</span><span class="sxs-lookup"><span data-stu-id="19889-120">Indicates the sign-in account to use for the services.</span></span> <span data-ttu-id="19889-121">Los valores permitidos para esta propiedad son: **LocalService**, **LocalSystem**, y **NetworkService**.</span><span class="sxs-lookup"><span data-stu-id="19889-121">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span>|
| <span data-ttu-id="19889-122">Estado</span><span class="sxs-lookup"><span data-stu-id="19889-122">State</span></span>| <span data-ttu-id="19889-123">Indica el estado que quiere garantizar para el servicio. **Detenido** o **ejecutando**.</span><span class="sxs-lookup"><span data-stu-id="19889-123">Indicates the state you want to ensure for the services: **Stopped** or **Running**.</span></span>|
| <span data-ttu-id="19889-124">Ensure</span><span class="sxs-lookup"><span data-stu-id="19889-124">Ensure</span></span>| <span data-ttu-id="19889-125">Indica si los servicios existen en el sistema.</span><span class="sxs-lookup"><span data-stu-id="19889-125">Indicates whether the services exist on the system.</span></span> <span data-ttu-id="19889-126">Establezca esta propiedad en **Absent** para asegurarse de que los servicios no existen.</span><span class="sxs-lookup"><span data-stu-id="19889-126">Set this property to **Absent** to ensure that the services do not exist.</span></span> <span data-ttu-id="19889-127">Si la establece en **Present** (el valor predeterminado), se asegura de que los servicios de destino existen.</span><span class="sxs-lookup"><span data-stu-id="19889-127">Setting it to **Present** (the default value) ensures that target services exist.</span></span>|
| <span data-ttu-id="19889-128">Credential</span><span class="sxs-lookup"><span data-stu-id="19889-128">Credential</span></span>| <span data-ttu-id="19889-129">Indica las credenciales para la cuenta en la que se ejecutará el recurso del servicio.</span><span class="sxs-lookup"><span data-stu-id="19889-129">Indicates credentials for the account that the service resource will run under.</span></span> <span data-ttu-id="19889-130">Esta propiedad no se puede utilizar junto con la propiedad **BuiltinAccount**.</span><span class="sxs-lookup"><span data-stu-id="19889-130">This property and the **BuiltinAccount** property cannot be used together.</span></span>|
| <span data-ttu-id="19889-131">DependsOn</span><span class="sxs-lookup"><span data-stu-id="19889-131">DependsOn</span></span>| <span data-ttu-id="19889-132">Indica que la configuración de otro recurso debe ejecutarse antes de que se configure este recurso.</span><span class="sxs-lookup"><span data-stu-id="19889-132">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="19889-133">Por ejemplo, si el elemento ID del bloque del script de configuración del recurso que quiere ejecutar primero es *ResourceName* y su tipo es *ResourceType*, la sintaxis para usar esta propiedad es `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="19889-133">For example, if the ID of the resource configuration script block that you want to run first is *ResourceName* and its type is *ResourceType*, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|



## <a name="example"></a><span data-ttu-id="19889-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="19889-134">Example</span></span>

<span data-ttu-id="19889-135">La siguiente configuración inicia los servicios de "Audio de Windows" y "Servicios de Escritorio remoto".</span><span class="sxs-lookup"><span data-stu-id="19889-135">The following configuration starts the "Windows Audio" and "Remote Desktop Services" services.</span></span>

```powershell
configuration ServiceSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        ServiceSet ServiceSetExample
        {
            Name        = @("TermService", "Audiosrv")
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```