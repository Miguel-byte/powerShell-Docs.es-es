---
ms.date: 06/09/2017
schema: 2.0.0
keywords: powershell
title: Módulos que requieren la aceptación de la licencia
ms.openlocfilehash: fe197ea271e18580a221ad4d5245b685bd81775b
ms.sourcegitcommit: e9ad4d85fd7eb72fb5bc37f6ca3ae1282ae3c6d7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/10/2018
---
# <a name="modules-requiring-license-acceptance"></a><span data-ttu-id="0510e-103">Módulos que requieren la aceptación de la licencia</span><span class="sxs-lookup"><span data-stu-id="0510e-103">Modules Requiring License Acceptance</span></span>

## <a name="synopsis"></a><span data-ttu-id="0510e-104">SINOPSIS</span><span class="sxs-lookup"><span data-stu-id="0510e-104">SYNOPSIS</span></span>

<span data-ttu-id="0510e-105">Los departamentos jurídicos de los publicadores de algunos módulos requieren que los clientes acepten la licencia de manera explícita antes de instalar el módulo desde la Galería de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0510e-105">Legal departments for some module publishers require that customers must explicitly accept the license before installing their module from PowerShell Gallery.</span></span> <span data-ttu-id="0510e-106">Si un usuario instala, actualiza o guarda un módulo con PowerShellGet, ya sea directamente o como una dependencia de otro elemento, y ese módulo requiere que el usuario acepte una licencia, el usuario debe indicar que acepta la licencia o la operación generará un error.</span><span class="sxs-lookup"><span data-stu-id="0510e-106">If a user installs, updates, or saves a module using PowerShellGet, whether directly or as a dependency for another item, and that module requires the user to agree to a license, the user must indicate they accept the license or the operation fails.</span></span>

## <a name="publish-requirements-for-modules"></a><span data-ttu-id="0510e-107">Requisitos de publicación de los módulos</span><span class="sxs-lookup"><span data-stu-id="0510e-107">Publish Requirements for Modules</span></span>

<span data-ttu-id="0510e-108">Los módulos que requieran que los usuarios acepten la licencia deberán cumplir los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0510e-108">Modules that would like to require users to accept license should fulfill following requirements:</span></span>

- <span data-ttu-id="0510e-109">La sección PSData del manifiesto del módulo debe incluir RequireLicenseAcceptance = $True.</span><span class="sxs-lookup"><span data-stu-id="0510e-109">PSData section of module manifest should include RequireLicenseAcceptance = $True.</span></span>
- <span data-ttu-id="0510e-110">El módulo debe incluir el archivo license.txt en el directorio raíz.</span><span class="sxs-lookup"><span data-stu-id="0510e-110">Module should contain license.txt file in root directory.</span></span>
- <span data-ttu-id="0510e-111">El manifiesto del módulo debe incluir el URI de la licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-111">Module manifest should contain License Uri.</span></span>
- <span data-ttu-id="0510e-112">El módulo se debe publicar con la versión 2.0 de PowerShellGet Format o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="0510e-112">Module should be published with PowerShellGet Format Version 2.0 and above.</span></span>

## <a name="impact-on-installsaveupdate-module"></a><span data-ttu-id="0510e-113">Impacto en Install/Save/Update-Module</span><span class="sxs-lookup"><span data-stu-id="0510e-113">Impact on Install/Save/Update-Module</span></span>

- <span data-ttu-id="0510e-114">Los cmdlets Install/Save/Update admitirán un parámetro nuevo, –AcceptLicense, que se comportará como si el usuario hubiese visto la licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-114">Install/Save/Update cmdlets will support a new parameter –AcceptLicense that will behave as though the user saw the license.</span></span>
- <span data-ttu-id="0510e-115">Si RequiredLicenseAcceptance es True y no se especifica –AcceptLicense, el usuario verá el archivo license.txt y se le preguntará: &quot;Do you accept these license terms (Yes/No/YesToAll/NoToAll)&quot; (¿Acepta estos términos de licencia? [Sí/No/SíATodo/NoATodo]).</span><span class="sxs-lookup"><span data-stu-id="0510e-115">If RequiredLicenseAcceptance is True and –AcceptLicense is not specified, the user will be shown the license.txt, and prompted with: &quot;Do you accept these license terms (Yes/No/YesToAll/NoToAll)&quot;.</span></span>
  - <span data-ttu-id="0510e-116">Si se acepta la licencia</span><span class="sxs-lookup"><span data-stu-id="0510e-116">If the license is accepted</span></span>
    - <span data-ttu-id="0510e-117">**Save-Module:** el módulo se copiará en el sistema del usuario.</span><span class="sxs-lookup"><span data-stu-id="0510e-117">**Save-Module:** the module will be copied to the user&#39;s system</span></span>
    - <span data-ttu-id="0510e-118">**Install-Module:** el módulo se copiará en el sistema del usuario, en la carpeta correspondiente (según el ámbito).</span><span class="sxs-lookup"><span data-stu-id="0510e-118">**Install-Module:** the module will be copied to the user&#39;s system to the proper folder (based on scope)</span></span>
    - <span data-ttu-id="0510e-119">**Update-Module:** el módulo se actualizará.</span><span class="sxs-lookup"><span data-stu-id="0510e-119">**Update-Module:** the module will be updated.</span></span>
  - <span data-ttu-id="0510e-120">Si se rechaza la licencia</span><span class="sxs-lookup"><span data-stu-id="0510e-120">If the license is declined.</span></span>
    - <span data-ttu-id="0510e-121">Se cancelará la operación.</span><span class="sxs-lookup"><span data-stu-id="0510e-121">Operation will be cancelled.</span></span>
- <span data-ttu-id="0510e-122">Todos los cmdlets buscarán los metadatos (requireLicenseAcceptance y Format Version) que indican que se requiere aceptar la licencia</span><span class="sxs-lookup"><span data-stu-id="0510e-122">All cmdlets will check for the metadata(requireLicenseAcceptance and Format Version) that says a license acceptance is required</span></span>
  - <span data-ttu-id="0510e-123">Si la versión del formato de cliente es anterior a 2.0, la operación presentará un error y le pedirá al usuario que actualice el cliente.</span><span class="sxs-lookup"><span data-stu-id="0510e-123">If format version of client is older than 2.0, operation will fail and ask the user to update the client.</span></span>
  - <span data-ttu-id="0510e-124">Si el módulo se publicó con una versión del formato anterior a 2.0, se omitirá la marca requireLicenseAcceptance.</span><span class="sxs-lookup"><span data-stu-id="0510e-124">If module was published with format version older than 2.0, requireLicenseAcceptance flag will be ignored.</span></span>


 ## <a name="module-dependencies"></a><span data-ttu-id="0510e-125">Dependencias de módulo</span><span class="sxs-lookup"><span data-stu-id="0510e-125">Module Dependencies</span></span>
- <span data-ttu-id="0510e-126">Durante la operación Install/Save/Update, si un módulo dependiente (si algo más depende del módulo) requiere aceptar la licencia, se requerirá el comportamiento de aceptación de la licencia (ya mencionado).</span><span class="sxs-lookup"><span data-stu-id="0510e-126">During Install/Save/Update operation, if a dependent module(something else depends on the module) requires license acceptance, then the license acceptance behavior (above) will be required.</span></span>
- <span data-ttu-id="0510e-127">Si la versión del módulo ya aparece en el catálogo local como instalada en el sistema, se omitirá la comprobación de la licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-127">If the module version is already listed in the local catalog as being installed on the system, we would bypass the license checking.</span></span>
- <span data-ttu-id="0510e-128">Durante la operación Install/Save/Update, si un módulo dependiente requiere una licencia y no se produce la aceptación de esta, la operación presentará un error y seguirá los procesos normales del elemento que no se instaló, guardó o actualizó.</span><span class="sxs-lookup"><span data-stu-id="0510e-128">During Install/Save/Update operation, if a dependent module requires a license, and the license acceptance does not occur, the operation will fail and follow normal processes for the item failed to install/save/update.</span></span>

 ## <a name="impact-on--force"></a><span data-ttu-id="0510e-129">Impacto en -Force</span><span class="sxs-lookup"><span data-stu-id="0510e-129">Impact on -Force</span></span>

<span data-ttu-id="0510e-130">Especificar –Force NO es suficiente para aceptar una licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-130">Specifying –Force is NOT sufficient to accept a license.</span></span> <span data-ttu-id="0510e-131">Se requiere –AcceptLicense para tener permiso para realizar la instalación.</span><span class="sxs-lookup"><span data-stu-id="0510e-131">–AcceptLicense is required for permission to install.</span></span> <span data-ttu-id="0510e-132">Si se especifica –Force, RequiredLicenseAcceptance es True y NO se especifica –AcceptLicense, no se realizará la operación.</span><span class="sxs-lookup"><span data-stu-id="0510e-132">If –Force is specified, RequiredLicenseAcceptance is True, and –AcceptLicense is NOT specified, the operation will fail.</span></span>

## <a name="examples"></a><span data-ttu-id="0510e-133">EJEMPLOS</span><span class="sxs-lookup"><span data-stu-id="0510e-133">EXAMPLES</span></span>

### <a name="example-1-update-module-manifest-to-require-license-acceptance"></a><span data-ttu-id="0510e-134">Ejemplo 1: actualización del manifiesto del módulo para requerir la aceptación de la licencia</span><span class="sxs-lookup"><span data-stu-id="0510e-134">Example 1: Update Module Manifest to require license acceptance</span></span>

```PowerShell
PS> Update-ModuleManifest -Path C:\modulemanifest.psd1 -RequireLicenseAcceptance

PrivateData = @{

    PSData = @{
        # Flag to indicate whether the module requires explicit user acceptance
        RequireLicenseAcceptance = $true
    } # End of PSData hashtable

 } # End of PrivateData hashtable
```

<span data-ttu-id="0510e-135">Este comando actualiza el archivo de manifiesto y establece la marca RequireLicenseAcceptance en true.</span><span class="sxs-lookup"><span data-stu-id="0510e-135">This command updates the manifest file and sets the RequireLicenseAcceptance flag to true.</span></span>

### <a name="example-2-install-module-requiring-license-acceptance"></a><span data-ttu-id="0510e-136">Ejemplo 2: instalación de un módulo que requiere la aceptación de la licencia</span><span class="sxs-lookup"><span data-stu-id="0510e-136">Example 2: Install Module requiring license acceptance</span></span>

```PowerShell
PS> Install-Module -Name ModuleRequireLicenseAcceptance

License Acceptance

License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):

```

<span data-ttu-id="0510e-137">Este comando muestra la licencia del archivo license.txt y le pide al usuario que acepte la licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-137">This command shows the license from license.txt file and prompts the user to accept the license.</span></span>

### <a name="example-3-install-module-requiring-license-acceptance-with--acceptlicense"></a><span data-ttu-id="0510e-138">Ejemplo 3: instalación de un módulo que requiere la aceptación de la licencia con -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="0510e-138">Example 3: Install Module requiring license acceptance with -AcceptLicense</span></span>

```PowerShell
PS> Install-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense
```

<span data-ttu-id="0510e-139">El módulo se instala sin que aparezca ningún mensaje que pida aceptar la licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-139">Module is installed without any prompt to accept license.</span></span>

### <a name="example-4-install-module-requiring-license-acceptance-with--force"></a><span data-ttu-id="0510e-140">Ejemplo 4: instalación de un módulo que requiere la aceptación de la licencia con -Force</span><span class="sxs-lookup"><span data-stu-id="0510e-140">Example 4: Install Module requiring license acceptance with -Force</span></span>

```PowerShell
PS> Install-Module -Name ModuleRequireLicenseAcceptance -Force
PackageManagement\Install-Package : License Acceptance is required for module 'ModuleRequireLicenseAcceptance'. Please specify '-AcceptLicense' to perform this operation.
At C:\Program Files\WindowsPowerShell\Modules\PowerShellGet\1.1.3.3\PSModule.psm1:1837 char:21
+ ...          $null = PackageManagement\Install-Package @PSBoundParameters
+                      ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (Microsoft.Power....InstallPackage:InstallPackage) [Install-Package], E
   xception
    + FullyQualifiedErrorId : ForceAcceptLicense,Install-PackageUtility,Microsoft.PowerShell.PackageManagement.Cmdlets
   .InstallPackage
```

### <a name="example-5-install-module-with-dependencies-requiring-license-acceptance"></a><span data-ttu-id="0510e-141">Ejemplo 5: instalación de un módulo con dependencias que requiere la aceptación de la licencia</span><span class="sxs-lookup"><span data-stu-id="0510e-141">Example 5: Install Module with dependencies requiring license acceptance</span></span>

<span data-ttu-id="0510e-142">El módulo "ModuleWithDependency" depende del módulo "ModuleRequireLicenseAcceptance".</span><span class="sxs-lookup"><span data-stu-id="0510e-142">Module 'ModuleWithDependency' depends on module 'ModuleRequireLicenseAcceptance'.</span></span> <span data-ttu-id="0510e-143">Se solicita al usuario que acepte la licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-143">User is prompted to Accept License.</span></span>

```PowerShell
PS> Install-Module -Name ModuleWithDependency

License Acceptance
MIT License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

### <a name="example-6-install-module-with-dependencies-requiring-license-acceptance-and--acceptlicense"></a><span data-ttu-id="0510e-144">Ejemplo 6: instalación de un módulo con dependencias que requiere la aceptación de la licencia y -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="0510e-144">Example 6: Install Module with dependencies requiring license acceptance and -AcceptLicense</span></span>

<span data-ttu-id="0510e-145">El módulo "ModuleWithDependency" depende del módulo "ModuleRequireLicenseAcceptance".</span><span class="sxs-lookup"><span data-stu-id="0510e-145">Module 'ModuleWithDependency' depends on module 'ModuleRequireLicenseAcceptance'.</span></span> <span data-ttu-id="0510e-146">No se le pide al usuario que acepte la licencia porque se especifica -AcceptLicense.</span><span class="sxs-lookup"><span data-stu-id="0510e-146">User is not prompted to accept license as -AcceptLicense is specified.</span></span>

```PowerShell
PS>  Install-Module -Name ModuleWithDependency -AcceptLicense
```

### <a name="example-7-install-module-requiring-license-acceptance-on-a-client-older-than-psgetformatversion-20"></a><span data-ttu-id="0510e-147">Ejemplo 7: instalación de un módulo que requiere la aceptación de la licencia en un cliente anterior a PSGetFormatVersion 2.0</span><span class="sxs-lookup"><span data-stu-id="0510e-147">Example 7: Install module requiring license acceptance on a client older than PSGetFormatVersion 2.0</span></span>

```PowerShell
PS C:\windows\system32> Install-Module -Name ModuleRequireLicenseAcceptance

WARNING: The specified module 'ModuleRequireLicenseAcceptance' with PowerShellGetFormatVersion '2.0' is not supported by the current version of PowerShellGet. Get the latest version of the PowerShellGet module to install this module, 'ModuleRequireLicenseAcceptance'.

```

### <a name="example-8-save-module-requiring-license-acceptance"></a><span data-ttu-id="0510e-148">Ejemplo 8: guardado de un módulo que requiere la aceptación de la licencia</span><span class="sxs-lookup"><span data-stu-id="0510e-148">Example 8: Save Module requiring license acceptance</span></span>

```PowerShell
PS> Save-Module -Name ModuleRequireLicenseAcceptance -Path C:\Saved

License Acceptance

License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="0510e-149">Este comando muestra la licencia del archivo license.txt y le pide al usuario que acepte la licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-149">This command shows the license from license.txt file and prompts the user to accept the license.</span></span>

### <a name="example-9-save-module-requiring-license-acceptance-with--acceptlicense"></a><span data-ttu-id="0510e-150">Ejemplo 9: guardado de un módulo que requiere la aceptación de licencia con -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="0510e-150">Example 9: Save Module requiring license acceptance with -AcceptLicense</span></span>

```PowerShell
PS> Save-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense -Path C:\Saved
```

<span data-ttu-id="0510e-151">El módulo se guarda sin que aparezca ningún mensaje que pida aceptar la licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-151">Module is saved without any prompt to accept license.</span></span>

### <a name="example-10-update-module-requiring-license-acceptance"></a><span data-ttu-id="0510e-152">Ejemplo 10: actualización de un módulo que requiere la aceptación de la licencia</span><span class="sxs-lookup"><span data-stu-id="0510e-152">Example 10: Update Module requiring license acceptance</span></span>

```PowerShell
PS> Update-Module -Name ModuleRequireLicenseAcceptance

License Acceptance

License 2.0
Copyright (c) 2016 PowerShell Team
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.

Do you accept the license terms for module 'ModuleRequireLicenseAcceptance'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

<span data-ttu-id="0510e-153">Este comando muestra la licencia del archivo license.txt y le pide al usuario que acepte la licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-153">This command shows the license from license.txt file and prompts the user to accept the license.</span></span>

### <a name="example-11-update-module-requiring-license-acceptance-with--acceptlicense"></a><span data-ttu-id="0510e-154">Ejemplo 11: actualización de un módulo que requiere la aceptación de licencia con -AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="0510e-154">Example 11: Update Module requiring license acceptance with -AcceptLicense</span></span>

```PowerShell
PS> Update-Module -Name ModuleRequireLicenseAcceptance -AcceptLicense
```

<span data-ttu-id="0510e-155">El módulo se actualiza sin que aparezca ningún mensaje que pida aceptar la licencia.</span><span class="sxs-lookup"><span data-stu-id="0510e-155">Module is updated without any prompt to accept license.</span></span>

## <a name="more-details"></a><span data-ttu-id="0510e-156">Más detalles</span><span class="sxs-lookup"><span data-stu-id="0510e-156">More details</span></span>

### <a name="require-license-acceptance-for-scriptsscript-license-acceptancemd"></a>[<span data-ttu-id="0510e-157">Requerir la aceptación de la licencia para Scripts</span><span class="sxs-lookup"><span data-stu-id="0510e-157">Require License Acceptance for Scripts</span></span>](./script-license-acceptance.md)

### <a name="require-license-acceptance-support-on-powershellgalleryhow-toworking-with-itemsitems-that-require-license-acceptancemd"></a>[<span data-ttu-id="0510e-158">Compatibilidad de Requerir la aceptación de la licencia en PowerShellGallery</span><span class="sxs-lookup"><span data-stu-id="0510e-158">Require License Acceptance support on PowerShellGallery</span></span>](../how-to/working-with-items/items-that-require-license-acceptance.md)

### <a name="require-license-acceptance-on-deploy-to-azure-automationhow-toworking-with-itemsdeploy-to-azure-automationmd"></a>[<span data-ttu-id="0510e-159">Requerir la aceptación de licencia de Implementar en Azure Automation</span><span class="sxs-lookup"><span data-stu-id="0510e-159">Require License Acceptance on Deploy to Azure Automation</span></span>](../how-to/working-with-items/deploy-to-azure-automation.md)