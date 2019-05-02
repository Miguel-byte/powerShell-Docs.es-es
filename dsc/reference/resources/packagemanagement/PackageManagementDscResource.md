---
ms.date: 06/20/2018
keywords: dsc,powershell,configuration,setup
title: Recurso PackageManagement de DSC
ms.openlocfilehash: 18cbbfe0715c82dcfdf4a5fb6ee36ee814e43d3b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077626"
---
# <a name="dsc-packagemanagement-resource"></a><span data-ttu-id="fd46e-103">Recurso PackageManagement de DSC</span><span class="sxs-lookup"><span data-stu-id="fd46e-103">DSC PackageManagement Resource</span></span>

<span data-ttu-id="fd46e-104">Se aplica a: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="fd46e-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="fd46e-105">El recurso **PackageManagement** de la configuración de estado deseado (DSC) de Windows PowerShell ofrece un mecanismo para instalar o desinstalar paquetes de administración de paquetes, en un nodo de destino.</span><span class="sxs-lookup"><span data-stu-id="fd46e-105">The **PackageManagement** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to install or uninstall Package Management packages on a target node.</span></span> <span data-ttu-id="fd46e-106">Este recurso requiere el módulo **PackageManagement**, disponible en [http://PowerShellGallery.com](http://PowerShellGallery.com).</span><span class="sxs-lookup"><span data-stu-id="fd46e-106">This resource requires the **PackageManagement** module, available from [http://PowerShellGallery.com](http://PowerShellGallery.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd46e-107">El módulo **PackageManagement** debe tener al menos la versión 1.1.7.0 para que la siguiente información de propiedad sea correcta.</span><span class="sxs-lookup"><span data-stu-id="fd46e-107">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd46e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd46e-108">Syntax</span></span>

```
PackageManagement [string] #ResourceName
{
    Name = [string]
    [AdditionalParameters = [HashTable]]
    [DependsOn = [string[]]]
    [Ensure = [string]{ Absent | Present }]
    [MaximumVersion = [string]]
    [MinimumVersion = [string]]
    [ProviderName = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [RequiredVersion = [string]]
    [Source = [string]]
    [SourceCredential = [PSCredential]]
}
```

## <a name="properties"></a><span data-ttu-id="fd46e-109">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fd46e-109">Properties</span></span>

| <span data-ttu-id="fd46e-110">Propiedad</span><span class="sxs-lookup"><span data-stu-id="fd46e-110">Property</span></span> | <span data-ttu-id="fd46e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd46e-111">Description</span></span> |
| --- | --- |
| <span data-ttu-id="fd46e-112">Nombre</span><span class="sxs-lookup"><span data-stu-id="fd46e-112">Name</span></span>| <span data-ttu-id="fd46e-113">Especifica el nombre del paquete que se va a instalar o desinstalar.</span><span class="sxs-lookup"><span data-stu-id="fd46e-113">Specifies the name of the Package to be installed or uninstalled.</span></span>|
| <span data-ttu-id="fd46e-114">AdditionalParameters</span><span class="sxs-lookup"><span data-stu-id="fd46e-114">AdditionalParameters</span></span>| <span data-ttu-id="fd46e-115">La tabla hash de parámetros específica del proveedor que se pasará a `Get-Package -AdditionalArguments`.</span><span class="sxs-lookup"><span data-stu-id="fd46e-115">Provider specific hashtable of parameters that would be passed to `Get-Package -AdditionalArguments`.</span></span> <span data-ttu-id="fd46e-116">Por ejemplo, para el proveedor NuGet puede pasar parámetros adicionales, como DestinationPath.</span><span class="sxs-lookup"><span data-stu-id="fd46e-116">For example, for NuGet provider you can pass additional parameters like DestinationPath.</span></span>|
| <span data-ttu-id="fd46e-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="fd46e-117">Ensure</span></span>| <span data-ttu-id="fd46e-118">Determina si el paquete se puede instalar o desinstalar.</span><span class="sxs-lookup"><span data-stu-id="fd46e-118">Determines whether the package is to be installed or uninstalled.</span></span>|
| <span data-ttu-id="fd46e-119">MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="fd46e-119">MaximumVersion</span></span>|<span data-ttu-id="fd46e-120">Especifica la versión máxima permitida del paquete que desea encontrar.</span><span class="sxs-lookup"><span data-stu-id="fd46e-120">Specifies the maximum allowed version of the package that you want to find.</span></span> <span data-ttu-id="fd46e-121">Si no agrega este parámetro, el recurso busca la versión disponible más alta del paquete.</span><span class="sxs-lookup"><span data-stu-id="fd46e-121">If you do not add this parameter, the resource finds the highest available version of the package.</span></span>|
| <span data-ttu-id="fd46e-122">MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="fd46e-122">MinimumVersion</span></span>|<span data-ttu-id="fd46e-123">Especifica la versión mínima permitida del paquete que desea encontrar.</span><span class="sxs-lookup"><span data-stu-id="fd46e-123">Specifies the minimum allowed version of the package that you want to find.</span></span> <span data-ttu-id="fd46e-124">Si no se agrega este parámetro, este recurso busca la versión más alta disponible del paquete que también admite cualquier versión máxima especificada por el parámetro _MaximumVersion_.</span><span class="sxs-lookup"><span data-stu-id="fd46e-124">If you do not add this parameter, the resource finds the highest available version of the package that also satisfies any maximum specified version specified by the _MaximumVersion_ parameter.</span></span>|
| <span data-ttu-id="fd46e-125">ProviderName</span><span class="sxs-lookup"><span data-stu-id="fd46e-125">ProviderName</span></span>| <span data-ttu-id="fd46e-126">Especifica un nombre de proveedor del paquete que se va a dirigir la búsqueda del paquete.</span><span class="sxs-lookup"><span data-stu-id="fd46e-126">Specifies a package provider name to which to scope your package search.</span></span> <span data-ttu-id="fd46e-127">Puede obtener los nombres de proveedor del paquete mediante la ejecución del cmdlet `Get-PackageProvider`.</span><span class="sxs-lookup"><span data-stu-id="fd46e-127">You can get package provider names by running the `Get-PackageProvider` cmdlet.</span></span>|
| <span data-ttu-id="fd46e-128">RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="fd46e-128">RequiredVersion</span></span>| <span data-ttu-id="fd46e-129">Especifica la versión exacta del paquete que desea instalar.</span><span class="sxs-lookup"><span data-stu-id="fd46e-129">Specifies the exact version of the package that you want to install.</span></span> <span data-ttu-id="fd46e-130">Si no se especifica este parámetro, este recurso de DSC instala la versión más reciente disponible del paquete que también admite cualquier versión máxima especificada por el parámetro _MaximumVersion_.</span><span class="sxs-lookup"><span data-stu-id="fd46e-130">If you do not specify this parameter, this DSC resource installs the newest available version of the package that also satisfies any maximum version specified by the _MaximumVersion_ parameter.</span></span>|
| <span data-ttu-id="fd46e-131">Origen</span><span class="sxs-lookup"><span data-stu-id="fd46e-131">Source</span></span>| <span data-ttu-id="fd46e-132">Especifica el nombre del origen del paquete donde se encuentra el paquete.</span><span class="sxs-lookup"><span data-stu-id="fd46e-132">Specifies the name of the package source where the package can be found.</span></span> <span data-ttu-id="fd46e-133">Puede ser un URI o un origen registrado con `Register-PackageSource` o el recurso de DSC PackageManagementSource.</span><span class="sxs-lookup"><span data-stu-id="fd46e-133">This can either be a URI or a source registered with `Register-PackageSource` or PackageManagementSource DSC resource.</span></span>|
| <span data-ttu-id="fd46e-134">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="fd46e-134">SourceCredential</span></span> | <span data-ttu-id="fd46e-135">Especifica una cuenta de usuario que tenga derechos para instalar un paquete para un proveedor u origen de paquetes especificado.</span><span class="sxs-lookup"><span data-stu-id="fd46e-135">Specifies a user account that has rights to install a package for a specified package provider or source.</span></span>|

## <a name="additional-parameters"></a><span data-ttu-id="fd46e-136">Parámetros adicionales</span><span class="sxs-lookup"><span data-stu-id="fd46e-136">Additional Parameters</span></span>

<span data-ttu-id="fd46e-137">En la tabla siguiente se enumeran las opciones de la propiedad AdditionalParameters.</span><span class="sxs-lookup"><span data-stu-id="fd46e-137">The following table lists options for the AdditionalParameters property.</span></span>

| <span data-ttu-id="fd46e-138">Parámetro</span><span class="sxs-lookup"><span data-stu-id="fd46e-138">Parameter</span></span> | <span data-ttu-id="fd46e-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="fd46e-139">Description</span></span> |
| --- | --- |
| <span data-ttu-id="fd46e-140">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="fd46e-140">DestinationPath</span></span>| <span data-ttu-id="fd46e-141">Usada por proveedores como el proveedor integrado de Nuget.</span><span class="sxs-lookup"><span data-stu-id="fd46e-141">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="fd46e-142">Especifica una ubicación del archivo donde desea que se instale el paquete.</span><span class="sxs-lookup"><span data-stu-id="fd46e-142">Specifies a file location where you want the package to be installed.</span></span>|
| <span data-ttu-id="fd46e-143">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="fd46e-143">InstallationPolicy</span></span>| <span data-ttu-id="fd46e-144">Usada por proveedores como el proveedor integrado de Nuget.</span><span class="sxs-lookup"><span data-stu-id="fd46e-144">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="fd46e-145">Determina si puede confiar en el origen del paquete.</span><span class="sxs-lookup"><span data-stu-id="fd46e-145">Determines whether you trust the package's source.</span></span> <span data-ttu-id="fd46e-146">Uno de: `Untrusted`, `Trusted`.</span><span class="sxs-lookup"><span data-stu-id="fd46e-146">One of: `Untrusted`, `Trusted`.</span></span>|

## <a name="example"></a><span data-ttu-id="fd46e-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd46e-147">Example</span></span>

<span data-ttu-id="fd46e-148">Este ejemplo se instala el paquete NuGet **JQuery** y el módulo **GistProvider** de PowerShell mediante el recurso **PackageManagement** de DSC.</span><span class="sxs-lookup"><span data-stu-id="fd46e-148">This example installs the **JQuery** NuGet package and **GistProvider** PowerShell module using the **PackageManagement** DSC resource.</span></span> <span data-ttu-id="fd46e-149">Este ejemplo primero garantiza que los orígenes del paquete necesarios están disponibles y después define el estado esperado de los paquetes **JQuery** y **GistProvider** (NuGet y PowerShell, respectivamente).</span><span class="sxs-lookup"><span data-stu-id="fd46e-149">This example first ensures the required package sources are available then defines the expected state of the **JQuery** and **GistProvider** packages (NuGet and PowerShell, respectively).</span></span>

```powershell
Configuration PackageTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagementSource PSGallery
    {
        Ensure      = "Present"
        Name        = "psgallery"
        ProviderName= "PowerShellGet"
        SourceLocation   = "https://www.powershellgallery.com/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagement NugetPackage
    {
        Ensure               = "Present"
        Name                 = "JQuery"
        AdditionalParameters = "$env:HomeDrive\nuget"
        RequiredVersion      = "2.0.1"
        DependsOn            = "[PackageManagementSource]SourceRepository"
    }

    PackageManagement PSModule
    {
        Ensure               = "Present"
        Name                 = "gistprovider"
        Source               = "PSGallery"
        DependsOn            = "[PackageManagementSource]PSGallery"
    }
}
```