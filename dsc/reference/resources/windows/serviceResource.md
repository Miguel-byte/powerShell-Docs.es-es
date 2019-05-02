---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Recurso de DSC Service
ms.openlocfilehash: 09571bd0eaa428e7d0bb7a533d6ad1c0c936e2cf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076909"
---
# <a name="dsc-service-resource"></a><span data-ttu-id="18a82-103">Recurso de DSC Service</span><span class="sxs-lookup"><span data-stu-id="18a82-103">DSC Service Resource</span></span>

> <span data-ttu-id="18a82-104">Se aplica a: Windows PowerShell 4.0, Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="18a82-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>


<span data-ttu-id="18a82-105">El recurso **Service** de la configuración de estado deseado (DSC) de Windows PowerShell ofrece un mecanismo para administrar servicios en el nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="18a82-105">The **Service** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage services on the target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="18a82-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18a82-106">Syntax</span></span>

```
Service [string] #ResourceName
{
    Name = [string]
    [ BuiltInAccount = [string] { LocalService | LocalSystem | NetworkService }  ]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ StartupType = [string] { Automatic | Disabled | Manual }  ]
    [ State = [string] { Running | Stopped }  ]
    [ Description = [string] ]
    [ DisplayName = [string] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Path = [string] ]
}
```

## <a name="properties"></a><span data-ttu-id="18a82-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="18a82-107">Properties</span></span>

|  <span data-ttu-id="18a82-108">Propiedad</span><span class="sxs-lookup"><span data-stu-id="18a82-108">Property</span></span>  |  <span data-ttu-id="18a82-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="18a82-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="18a82-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="18a82-110">Name</span></span>| <span data-ttu-id="18a82-111">Indica el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="18a82-111">Indicates the service name.</span></span> <span data-ttu-id="18a82-112">Tenga en cuenta que a veces es distinto del nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="18a82-112">Note that sometimes this is different from the display name.</span></span> <span data-ttu-id="18a82-113">Puede obtener una lista de los servicios y sus estados actuales con el cmdlet Get-Service.</span><span class="sxs-lookup"><span data-stu-id="18a82-113">You can get a list of the services and their current state with the Get-Service cmdlet.</span></span>|
| <span data-ttu-id="18a82-114">BuiltInAccount</span><span class="sxs-lookup"><span data-stu-id="18a82-114">BuiltInAccount</span></span>| <span data-ttu-id="18a82-115">Indica la cuenta de inicio de sesión que se utilizará para el servicio.</span><span class="sxs-lookup"><span data-stu-id="18a82-115">Indicates the sign-in account to use for the service.</span></span> <span data-ttu-id="18a82-116">Los valores permitidos para esta propiedad son: **LocalService**, **LocalSystem** y **NetworkService**.</span><span class="sxs-lookup"><span data-stu-id="18a82-116">The values that are allowed for this property are: **LocalService**, **LocalSystem**, and **NetworkService**.</span></span>|
| <span data-ttu-id="18a82-117">Credential</span><span class="sxs-lookup"><span data-stu-id="18a82-117">Credential</span></span>| <span data-ttu-id="18a82-118">Indica las credenciales de la cuenta en la que se ejecutará el servicio.</span><span class="sxs-lookup"><span data-stu-id="18a82-118">Indicates credentials for the account that the service will run under.</span></span> <span data-ttu-id="18a82-119">Esta propiedad no se puede utilizar junto con la propiedad __BuiltinAccount__.</span><span class="sxs-lookup"><span data-stu-id="18a82-119">This property and the __BuiltinAccount__ property cannot be used together.</span></span>|
| <span data-ttu-id="18a82-120">DependsOn</span><span class="sxs-lookup"><span data-stu-id="18a82-120">DependsOn</span></span>| <span data-ttu-id="18a82-121">Indica que la configuración de otro recurso debe ejecutarse antes de que se configure este recurso.</span><span class="sxs-lookup"><span data-stu-id="18a82-121">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="18a82-122">Por ejemplo, si el elemento ID del bloque del script de configuración del recurso que quiere ejecutar primero es __ResourceName__ y su tipo es __ResourceType__, la sintaxis para usar esta propiedad es `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="18a82-122">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="18a82-123">StartupType</span><span class="sxs-lookup"><span data-stu-id="18a82-123">StartupType</span></span>| <span data-ttu-id="18a82-124">Indica el tipo de inicio del servicio.</span><span class="sxs-lookup"><span data-stu-id="18a82-124">Indicates the startup type for the service.</span></span> <span data-ttu-id="18a82-125">Los valores permitidos para esta propiedad son: **Automatic**, **Disabled** y **Manual**</span><span class="sxs-lookup"><span data-stu-id="18a82-125">The values that are allowed for this property are: **Automatic**, **Disabled**, and **Manual**</span></span>|
| <span data-ttu-id="18a82-126">Estado</span><span class="sxs-lookup"><span data-stu-id="18a82-126">State</span></span>| <span data-ttu-id="18a82-127">Indica el estado que quiere garantizar para el servicio.</span><span class="sxs-lookup"><span data-stu-id="18a82-127">Indicates the state you want to ensure for the service.</span></span>|
| <span data-ttu-id="18a82-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="18a82-128">Description</span></span> | <span data-ttu-id="18a82-129">Indica la descripción del servicio de destino.</span><span class="sxs-lookup"><span data-stu-id="18a82-129">Indicates the description of the target service.</span></span>|
| <span data-ttu-id="18a82-130">DisplayName</span><span class="sxs-lookup"><span data-stu-id="18a82-130">DisplayName</span></span> | <span data-ttu-id="18a82-131">Indica el nombre para mostrar del servicio de destino.</span><span class="sxs-lookup"><span data-stu-id="18a82-131">Indicates the display name of the target service.</span></span>|
| <span data-ttu-id="18a82-132">Ensure</span><span class="sxs-lookup"><span data-stu-id="18a82-132">Ensure</span></span> | <span data-ttu-id="18a82-133">Indica si el servicio de destino existe en el sistema.</span><span class="sxs-lookup"><span data-stu-id="18a82-133">Indicates whether the target service exists on the system.</span></span> <span data-ttu-id="18a82-134">Establezca esta propiedad en **Absent** para asegurarse de que el servicio de destino no exista.</span><span class="sxs-lookup"><span data-stu-id="18a82-134">Set this property to **Absent** to ensure that the target service does not exist.</span></span> <span data-ttu-id="18a82-135">Si la establece en **Present** (el valor predeterminado), se asegura de que el servicio de destino existe.</span><span class="sxs-lookup"><span data-stu-id="18a82-135">Setting it to **Present** (the default value) ensures that target service exists.</span></span>|
| <span data-ttu-id="18a82-136">Ruta</span><span class="sxs-lookup"><span data-stu-id="18a82-136">Path</span></span> | <span data-ttu-id="18a82-137">Indica la ruta de acceso al archivo binario para un nuevo servicio.</span><span class="sxs-lookup"><span data-stu-id="18a82-137">Indicates the path to the binary file for a new service.</span></span>|

## <a name="example"></a><span data-ttu-id="18a82-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="18a82-138">Example</span></span>

```powershell
configuration ServiceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        Service ServiceExample
        {
            Name        = "TermService"
            StartupType = "Manual"
            State       = "Running"
        }
    }
}
```