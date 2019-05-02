---
ms.date: 06/20/2018
keywords: dsc,powershell,configuration,setup
title: Recurso PackageManagementSource de DSC
ms.openlocfilehash: e51b5318288bef458567dd4b58d17caaea3ed69b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077592"
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="01056-103">Recurso PackageManagementSource de DSC</span><span class="sxs-lookup"><span data-stu-id="01056-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="01056-104">Se aplica a: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="01056-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="01056-105">El recurso **PackageManagementSource** de la configuración de estado deseado (DSC) de Windows PowerShell ofrece un mecanismo para registrar o anular el registro de los orígenes de administración de paquetes en un nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="01056-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span> <span data-ttu-id="01056-106">**Los orígenes de administración de paquetes registrados de este modo se registran en el contexto del sistema y pueden usarse por la cuenta del sistema o por el motor de DSC.**</span><span class="sxs-lookup"><span data-stu-id="01056-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="01056-107">Este recurso requiere el módulo **PackageManagement**, disponible en http://PowerShellGallery.com.</span><span class="sxs-lookup"><span data-stu-id="01056-107">This resource requires the **PackageManagement** module, available from http://PowerShellGallery.com.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01056-108">El módulo **PackageManagement** debe tener al menos la versión 1.1.7.0 para que la siguiente información de propiedad sea correcta.</span><span class="sxs-lookup"><span data-stu-id="01056-108">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="01056-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01056-109">Syntax</span></span>

```
PackageManagementSource [String] #ResourceName
{
    Name = [string]
    ProviderName = [string]
    SourceLocation = [string]
    [DependsOn = [string[]]]
    [Ensure = [string]{ Absent | Present }]
    [InstallationPolicy = [string]{ Trusted | Untrusted }]
    [PsDscRunAsCredential = [PSCredential]]
    [SourceCredential = [PSCredential]]
}
```

## <a name="properties"></a><span data-ttu-id="01056-110">Propiedades</span><span class="sxs-lookup"><span data-stu-id="01056-110">Properties</span></span>

|  <span data-ttu-id="01056-111">Propiedad</span><span class="sxs-lookup"><span data-stu-id="01056-111">Property</span></span>  |  <span data-ttu-id="01056-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="01056-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="01056-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="01056-113">Name</span></span>| <span data-ttu-id="01056-114">Especifica el nombre del origen del paquete que se registra o se anula su registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="01056-114">Specifies the name of the package source to be registered or unregistered on your system.</span></span>|
| <span data-ttu-id="01056-115">ProviderName</span><span class="sxs-lookup"><span data-stu-id="01056-115">ProviderName</span></span>| <span data-ttu-id="01056-116">Especifica el nombre del proveedor de OneGet que permite la interoperabilidad con el origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="01056-116">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span>|
| <span data-ttu-id="01056-117">SourceLocation</span><span class="sxs-lookup"><span data-stu-id="01056-117">SourceLocation</span></span>| <span data-ttu-id="01056-118">Especifica el URI del origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="01056-118">Specifies the URI of the package source.</span></span>|
| <span data-ttu-id="01056-119">Ensure</span><span class="sxs-lookup"><span data-stu-id="01056-119">Ensure</span></span>| <span data-ttu-id="01056-120">Determina si el origen del paquete se registra o no.</span><span class="sxs-lookup"><span data-stu-id="01056-120">Determines whether the package source is to be registered or unregistered.</span></span>|
| <span data-ttu-id="01056-121">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="01056-121">InstallationPolicy</span></span>| <span data-ttu-id="01056-122">Usada por proveedores como el proveedor integrado de Nuget.</span><span class="sxs-lookup"><span data-stu-id="01056-122">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="01056-123">Determina si puede confiar en el origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="01056-123">Determines whether you trust the package's source.</span></span> <span data-ttu-id="01056-124">Uno de los valores siguientes: "No es de confianza", "De confianza".</span><span class="sxs-lookup"><span data-stu-id="01056-124">One of: "Untrusted", "Trusted".</span></span>|
| <span data-ttu-id="01056-125">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="01056-125">SourceCredential</span></span>| <span data-ttu-id="01056-126">Proporciona acceso al paquete en un origen remoto.</span><span class="sxs-lookup"><span data-stu-id="01056-126">Provides access to the package on a remote source.</span></span>|

## <a name="example"></a><span data-ttu-id="01056-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01056-127">Example</span></span>

<span data-ttu-id="01056-128">En este ejemplo se registra el origen del paquete http://nuget.org con el recurso de DSC **PackageManagementSource** DSC resource.</span><span class="sxs-lookup"><span data-stu-id="01056-128">This example registers the http://nuget.org package source using the **PackageManagementSource** DSC resource.</span></span>

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }
}
```