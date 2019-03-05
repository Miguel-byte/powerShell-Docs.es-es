---
title: Instalación de un módulo de PowerShell | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb82827e-fdb7-4cbf-b3d4-093e72b3ff0e
caps.latest.revision: 28
ms.openlocfilehash: f7899713dd273b793017adfa0a20b3ff3352b62a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862171"
---
# <a name="installing-a-powershell-module"></a><span data-ttu-id="51150-102">Instalación de un módulo de PowerShell</span><span class="sxs-lookup"><span data-stu-id="51150-102">Installing a PowerShell Module</span></span>

<span data-ttu-id="51150-103">Después de haber creado el módulo de PowerShell, probablemente deseará instalar el módulo en un sistema, para que usted u otros usuarios pueden usar.</span><span class="sxs-lookup"><span data-stu-id="51150-103">After you have created your PowerShell module, you will likely want to install the module on a system, so that you or others may use it.</span></span> <span data-ttu-id="51150-104">Por lo general, esto simplemente consiste en copiar los archivos de módulo (es decir, el. psm1, o el ensamblado binario, el manifiesto del módulo y los otros archivos asociados) en un directorio en el equipo.</span><span class="sxs-lookup"><span data-stu-id="51150-104">Generally speaking, this simply consists of copying the module files (ie, the .psm1, or the binary assembly, the module manifest, and any other associated files) onto a directory on that computer.</span></span> <span data-ttu-id="51150-105">Para un proyecto muy pequeño, esto puede ser tan sencillo como copiar y pegar los archivos con el Explorador de Windows en un único equipo remoto. Sin embargo, para las soluciones más grandes se puede usar un proceso de instalación más sofisticado.</span><span class="sxs-lookup"><span data-stu-id="51150-105">For a very small project, this may be as simple as copying and pasting the files with Windows Explorer onto a single remote computer; however, for larger solutions you may wish to use a more sophisticated installation process.</span></span> <span data-ttu-id="51150-106">Independientemente de cómo obtener el módulo en el sistema, PowerShell puede usar varias técnicas que permitirá a los usuarios a encontrar y usar los módulos.</span><span class="sxs-lookup"><span data-stu-id="51150-106">Regardless of how you get your module onto the system, PowerShell can use a number of techniques that will let users find and use your modules.</span></span> <span data-ttu-id="51150-107">(Para obtener más información, consulte [importar un módulo de PowerShell](./importing-a-powershell-module.md).) Por lo tanto, el principal problema para la instalación es asegurarse de que PowerShell pueda encontrar el módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-107">(For more information, see [Importing a PowerShell Module](./importing-a-powershell-module.md).) Therefore, the main issue for installation is ensuring that PowerShell will be able to find your module.</span></span>

<span data-ttu-id="51150-108">Este tema contiene las siguientes secciones:</span><span class="sxs-lookup"><span data-stu-id="51150-108">This topic contains the following sections:</span></span>

- <span data-ttu-id="51150-109">Reglas para la instalación de módulos</span><span class="sxs-lookup"><span data-stu-id="51150-109">Rules for Installing Modules</span></span>

- <span data-ttu-id="51150-110">¿Dónde instalar los módulos</span><span class="sxs-lookup"><span data-stu-id="51150-110">Where to Install Modules</span></span>

- <span data-ttu-id="51150-111">Instalar varias versiones de un módulo</span><span class="sxs-lookup"><span data-stu-id="51150-111">Installing Multiple Versions of a Module</span></span>

- <span data-ttu-id="51150-112">Control de conflictos de nombres de comando</span><span class="sxs-lookup"><span data-stu-id="51150-112">Handling Command Name Conflicts</span></span>

## <a name="rules-for-installing-modules"></a><span data-ttu-id="51150-113">Reglas para la instalación de módulos</span><span class="sxs-lookup"><span data-stu-id="51150-113">Rules for Installing Modules</span></span>

<span data-ttu-id="51150-114">La siguiente información se aplica a todos los módulos, incluidos los módulos que se crean para su propio uso, los módulos que se obtienen de otras partes y los módulos que se distribución a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="51150-114">The following information pertains to all modules, including modules that you create for your own use, modules that you get from other parties, and modules that you distribute to others.</span></span>

### <a name="install-modules-in-psmodulepath"></a><span data-ttu-id="51150-115">Instalación de módulos en PSModulePath</span><span class="sxs-lookup"><span data-stu-id="51150-115">Install Modules in PSModulePath</span></span>

<span data-ttu-id="51150-116">Siempre que sea posible, instale todos los módulos en una ruta de acceso que aparece en el **PSModulePath** variable de entorno o agregar la ruta de acceso del módulo a la **PSModulePath** valor de variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="51150-116">Whenever possible, install all modules in a path that is listed in the **PSModulePath** environment variable or add the module path to the **PSModulePath** environment variable value.</span></span>

<span data-ttu-id="51150-117">El **PSModulePath** variable de entorno ($Env: PSModulePath) contiene las ubicaciones de los módulos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51150-117">The **PSModulePath** environment variable ($Env:PSModulePath) contains the locations of Windows PowerShell modules.</span></span> <span data-ttu-id="51150-118">Los cmdlets se basan en el valor de esta variable de entorno para encontrar los módulos.</span><span class="sxs-lookup"><span data-stu-id="51150-118">Cmdlets rely on the value of this environment variable to find modules.</span></span>

<span data-ttu-id="51150-119">De forma predeterminada, el **PSModulePath** valor de variable de entorno contiene el siguiente sistema y los directorios del módulo de usuario, pero puede agregar a y edite el valor.</span><span class="sxs-lookup"><span data-stu-id="51150-119">By default, the **PSModulePath** environment variable value contains the following system and user module directories, but you can add to and edit the value.</span></span>

- <span data-ttu-id="51150-120">$PSHome\Modules (% Windir%\System32\WindowsPowerShell\v1.0\Modules)</span><span class="sxs-lookup"><span data-stu-id="51150-120">$PSHome\Modules (%Windir%\System32\WindowsPowerShell\v1.0\Modules)</span></span>

  > [!WARNING]
  > <span data-ttu-id="51150-121">Esta ubicación está reservada para módulos que se incluyen con Windows.</span><span class="sxs-lookup"><span data-stu-id="51150-121">This location is reserved for modules that ship with Windows.</span></span> <span data-ttu-id="51150-122">No instale los módulos a esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="51150-122">Do not install modules to this location.</span></span>

- <span data-ttu-id="51150-123">$Home\Documents\WindowsPowerShell\Modules (% UserProfile%\Documents\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="51150-123">$Home\Documents\WindowsPowerShell\Modules (%UserProfile%\Documents\WindowsPowerShell\Modules)</span></span>

- <span data-ttu-id="51150-124">$Env:ProgramFiles\WindowsPowerShell\Modules (%ProgramFiles%\WindowsPowerShell\Modules)</span><span class="sxs-lookup"><span data-stu-id="51150-124">$Env:ProgramFiles\WindowsPowerShell\Modules (%ProgramFiles%\WindowsPowerShell\Modules)</span></span>

  <span data-ttu-id="51150-125">Para obtener el valor de la **PSModulePath** variable de entorno, utilice uno de los siguientes comandos.</span><span class="sxs-lookup"><span data-stu-id="51150-125">To get the value of the **PSModulePath** environment variable, use either of the following commands.</span></span>

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  <span data-ttu-id="51150-126">Para agregar una ruta de acceso del módulo al valor de la **PSModulePath** variable de entorno de valor, use el siguiente formato de comando.</span><span class="sxs-lookup"><span data-stu-id="51150-126">To add a module path to value of the **PSModulePath** environment variable value, use the following command format.</span></span> <span data-ttu-id="51150-127">Este formato utiliza el **SetEnvironmentVariable** método de la **System.Environment** clase para realizar un cambio de sesión independiente en el **PSModulePath** entorno variable.</span><span class="sxs-lookup"><span data-stu-id="51150-127">This format uses the **SetEnvironmentVariable** method of the **System.Environment** class to make a session-independent change to the **PSModulePath** environment variable.</span></span>

  ```powershell

  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > <span data-ttu-id="51150-128">Una vez haya agregado la ruta de acceso **PSModulePath**, debe difundir un mensaje sobre el cambio del entorno.</span><span class="sxs-lookup"><span data-stu-id="51150-128">Once you have added the path to **PSModulePath**, you should broadcast an environment message about the change.</span></span> <span data-ttu-id="51150-129">Difunde el cambio permite que otras aplicaciones, como el shell recoger el cambio.</span><span class="sxs-lookup"><span data-stu-id="51150-129">Broadcasting the change allows other applications, such as the shell, to pick up the change.</span></span> <span data-ttu-id="51150-130">Para difundir el cambio, tener el código de instalación del producto enviar un **WM_SETTINGCHANGE** de mensajes con `lParam` establecido en la cadena "Entorno".</span><span class="sxs-lookup"><span data-stu-id="51150-130">To broadcast the change, have your product installation code send a **WM_SETTINGCHANGE** message with `lParam` set to the string "Environment".</span></span> <span data-ttu-id="51150-131">Asegúrese de enviar el mensaje después de que se ha actualizado el código de instalación del módulo **PSModulePath**.</span><span class="sxs-lookup"><span data-stu-id="51150-131">Be sure to send the message after your module installation code has updated **PSModulePath**.</span></span>

### <a name="use-the-correct-module-directory-name"></a><span data-ttu-id="51150-132">Utilice el nombre del directorio de módulo correcto</span><span class="sxs-lookup"><span data-stu-id="51150-132">Use the Correct Module Directory Name</span></span>

<span data-ttu-id="51150-133">Un módulo de "correcto" es un módulo que se almacena en un directorio que tiene el mismo nombre que el nombre de base de al menos un archivo en el directorio del módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-133">A "well-formed" module is a module that is stored in a directory that has the same name as the base name of at least one file in the module directory.</span></span> <span data-ttu-id="51150-134">Si un módulo no está bien formado, Windows PowerShell no la reconoce como un módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-134">If a module is not well-formed, Windows PowerShell does not recognize it as a module.</span></span>

<span data-ttu-id="51150-135">El "nombre de base" de un archivo es el nombre sin la extensión de nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="51150-135">The "base name" of a file is the name without the file name extension.</span></span> <span data-ttu-id="51150-136">En un módulo tiene el formato correcto, el nombre del directorio que contiene los archivos del módulo debe coincidir con el nombre de base de al menos un archivo en el módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-136">In a well-formed module, the name of the directory that contains the module files must match the base name of at least one file in the module.</span></span>

<span data-ttu-id="51150-137">Por ejemplo, en el módulo de ejemplo Fabrikam, el directorio que contiene los archivos de módulo se denomina "Fabrikam" y al menos un archivo tiene el nombre de base "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="51150-137">For example, in the sample Fabrikam module, the directory that contains the module files is named "Fabrikam" and at least one file has the "Fabrikam" base name.</span></span> <span data-ttu-id="51150-138">En este caso, Fabrikam.psd1 y Fabrikam.dll tienen el nombre de base "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="51150-138">In this case, both Fabrikam.psd1 and Fabrikam.dll have the "Fabrikam" base name.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a><span data-ttu-id="51150-139">Efecto de una instalación incorrecta</span><span class="sxs-lookup"><span data-stu-id="51150-139">Effect of Incorrect Installation</span></span>

<span data-ttu-id="51150-140">Si el módulo no es correcto y su ubicación no se incluye en el valor de la **PSModulePath** variable de entorno, las características básicas de detección de Windows PowerShell, como la siguiente, no funcionan.</span><span class="sxs-lookup"><span data-stu-id="51150-140">If the module is not well-formed and its location is not included in the value of the **PSModulePath** environment variable, basic discovery features of Windows PowerShell, such as the following, do not work.</span></span>

- <span data-ttu-id="51150-141">La característica de carga automática del módulo no puede importar el módulo automáticamente.</span><span class="sxs-lookup"><span data-stu-id="51150-141">The Module Auto-Loading feature cannot import the module automatically.</span></span>

- <span data-ttu-id="51150-142">El `ListAvailable` parámetro de la [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet no puede encontrar el módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-142">The `ListAvailable` parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet cannot find the module.</span></span>

- <span data-ttu-id="51150-143">El [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet no puede encontrar el módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-143">The [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet cannot find the module.</span></span> <span data-ttu-id="51150-144">Para importar el módulo, debe proporcionar la ruta de acceso completa al archivo de módulo raíz o archivo de manifiesto de módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-144">To import the module, you must provide the full path to the root module file or module manifest file.</span></span>

  <span data-ttu-id="51150-145">Características adicionales, como la siguiente, no funcionan a menos que el módulo se importa en la sesión.</span><span class="sxs-lookup"><span data-stu-id="51150-145">Additional features, such as the following, do not work unless the module is imported into the session.</span></span> <span data-ttu-id="51150-146">En los módulos correctos en el **PSModulePath** variable de entorno, estas características funcionan incluso cuando no se importa el módulo en la sesión.</span><span class="sxs-lookup"><span data-stu-id="51150-146">In well-formed modules in the **PSModulePath** environment variable, these features work even when the module is not imported into the session.</span></span>

- <span data-ttu-id="51150-147">El [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet no puede encontrar los comandos en el módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-147">The [Get-Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command) cmdlet cannot find commands in the module.</span></span>

- <span data-ttu-id="51150-148">El [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) y [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) no puede actualizar o guardar la Ayuda del módulo de cmdlets.</span><span class="sxs-lookup"><span data-stu-id="51150-148">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets cannot update or save help for the module.</span></span>

- <span data-ttu-id="51150-149">El [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet no puede buscar y mostrar los comandos en el módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-149">The [Show-Command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command) cmdlet cannot find and display the commands in the module.</span></span>

  <span data-ttu-id="51150-150">Faltan los comandos en el módulo en el `Show-Command` en Windows PowerShell Integrated Scripting Environment (ISE) de la ventana.</span><span class="sxs-lookup"><span data-stu-id="51150-150">The commands in the module are missing from the `Show-Command` window in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="where-to-install-modules"></a><span data-ttu-id="51150-151">¿Dónde instalar los módulos</span><span class="sxs-lookup"><span data-stu-id="51150-151">Where to Install Modules</span></span>

<span data-ttu-id="51150-152">En esta sección se explica dónde en el sistema de archivos para instalar los módulos de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51150-152">This section explains where in the file system to install Windows PowerShell modules.</span></span> <span data-ttu-id="51150-153">La ubicación depende de cómo se usa el módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-153">The location depends on how the module is used.</span></span>

### <a name="installing-modules-for-a-specific-user"></a><span data-ttu-id="51150-154">Instalación de módulos para un usuario específico</span><span class="sxs-lookup"><span data-stu-id="51150-154">Installing Modules for a Specific User</span></span>

<span data-ttu-id="51150-155">Si crea su propio módulo u obtener un módulo desde otra parte, como un sitio Web Comunidad de Windows PowerShell, y desea que el módulo está disponible para su cuenta de usuario solo, instale el módulo en el directorio de módulos específicos del usuario.</span><span class="sxs-lookup"><span data-stu-id="51150-155">If you create your own module or get a module from another party, such as a Windows PowerShell community website, and you want the module to be available for your user account only, install the module in your user-specific Modules directory.</span></span>

```
$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>
```

<span data-ttu-id="51150-156">El directorio de módulos específicos del usuario se agrega al valor de la **PSModulePath** variable de entorno de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="51150-156">The user-specific Modules directory is added to the value of the **PSModulePath** environment variable by default.</span></span>

### <a name="installing-modules-for-all-users-in-program-files"></a><span data-ttu-id="51150-157">Instalación de módulos para todos los usuarios en archivos de programa</span><span class="sxs-lookup"><span data-stu-id="51150-157">Installing Modules for all Users in Program Files</span></span>

<span data-ttu-id="51150-158">Si desea que un módulo que estén disponibles para todas las cuentas de usuario en el equipo, instale el módulo en la ubicación de archivos de programa.</span><span class="sxs-lookup"><span data-stu-id="51150-158">If you want a module to be available to all user accounts on the computer, install the module in the Program Files location.</span></span>

```
$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>
```

> [!NOTE]
> <span data-ttu-id="51150-159">De forma predeterminada en Windows PowerShell 4.0 y versiones posteriores, la ubicación de archivos de programa se agrega al valor de la variable de entorno PSModulePath.</span><span class="sxs-lookup"><span data-stu-id="51150-159">The Program Files location is added to the value of the PSModulePath environment variable by default in Windows PowerShell 4.0 and later.</span></span> <span data-ttu-id="51150-160">Las versiones anteriores de Windows PowerShell, manualmente puede crear el ((%ProgramFiles%\WindowsPowerShell\Modules) ubicación los archivos de programa y agregar esta ruta de acceso a la variable de entorno PSModulePath, como se describió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="51150-160">For earlier versions of Windows PowerShell, you can manually create the Program Files location ((%ProgramFiles%\WindowsPowerShell\Modules) and add this path to your PSModulePath environment variable as described above.</span></span>

### <a name="installing-modules-in-a-product-directory"></a><span data-ttu-id="51150-161">Instalación de módulos en un directorio de productos</span><span class="sxs-lookup"><span data-stu-id="51150-161">Installing Modules in a Product Directory</span></span>

<span data-ttu-id="51150-162">Si va a distribuir el módulo a otras partes, use la ubicación de archivos de programa predeterminado que se ha descrito anteriormente, o crear su propio subdirectorio específico de la compañía o específico del producto del directorio % ProgramFiles %.</span><span class="sxs-lookup"><span data-stu-id="51150-162">If you are distributing the module to other parties, use the default Program Files location described above, or create your own company-specific or product-specific subdirectory of the %ProgramFiles% directory.</span></span>

<span data-ttu-id="51150-163">Por ejemplo, las tecnologías de Fabrikam, una compañía ficticia, se envía a un módulo de Windows PowerShell para su producto del Administrador de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="51150-163">For example, Fabrikam Technologies, a fictitious company, is shipping a Windows PowerShell module for their Fabrikam Manager product.</span></span> <span data-ttu-id="51150-164">Instalador del módulo, crea un subdirectorio de módulos en el subdirectorio del producto de Fabrikam Manager.</span><span class="sxs-lookup"><span data-stu-id="51150-164">Their module installer creates a Modules subdirectory in the Fabrikam Manager product subdirectory.</span></span>

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

<span data-ttu-id="51150-165">Para habilitar las características de detección del módulo de Windows PowerShell encontrar el módulo de Fabrikam, el instalador del módulo Fabrikam agrega la ubicación de módulo en el valor de la **PSModulePath** variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="51150-165">To enable the Windows PowerShell module discovery features to find the Fabrikam module, the Fabrikam module installer adds the module location to the value of the **PSModulePath** environment variable.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += "C:\Program Files\Fabrikam Technolgies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a><span data-ttu-id="51150-166">Instalación de módulos en el directorio de archivos comunes</span><span class="sxs-lookup"><span data-stu-id="51150-166">Installing Modules in the Common Files Directory</span></span>

<span data-ttu-id="51150-167">Si se usa un módulo por varios componentes de un producto o por varias versiones de un producto, instale el módulo en un subdirectorio específico del módulo del subdirectorio Files\Modules %ProgramFiles%\Common.</span><span class="sxs-lookup"><span data-stu-id="51150-167">If a module is used by multiple components of a product or by multiple versions of a product, install the module in a module-specific subdirectory of the %ProgramFiles%\Common Files\Modules subdirectory.</span></span>

<span data-ttu-id="51150-168">En el ejemplo siguiente, se instala el módulo de Fabrikam en un subdirectorio de Fabrikam del subdirectorio Files\Modules %ProgramFiles%\Common.</span><span class="sxs-lookup"><span data-stu-id="51150-168">In the following example, the Fabrikam module is installed in a Fabrikam subdirectory of the %ProgramFiles%\Common Files\Modules subdirectory.</span></span> <span data-ttu-id="51150-169">Tenga en cuenta que cada módulo reside en su propio subdirectorio en el subdirectorio de módulos.</span><span class="sxs-lookup"><span data-stu-id="51150-169">Note that each module resides in its own subdirectory in the Modules subdirectory.</span></span>

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)

```

<span data-ttu-id="51150-170">A continuación, el programa de instalación garantiza que el valor de la **PSModulePath** variable de entorno incluye la ruta de acceso del subdirectorio de módulos comunes de archivos.</span><span class="sxs-lookup"><span data-stu-id="51150-170">Then, the installer assures the value of the **PSModulePath** environment variable includes the path of the common files modules subdirectory.</span></span>

```powershell
$m = $env:ProgramFiles + '\Common Files\Modules'
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$q = $p -split ';'
if ($q -notContains $m) {
    $q += ";$m"
}
$p = $q -join ';'
[Environment]::SetEnvironmentVariable("PSModulePath", $p)
```

## <a name="installing-multiple-versions-of-a-module"></a><span data-ttu-id="51150-171">Instalar varias versiones de un módulo</span><span class="sxs-lookup"><span data-stu-id="51150-171">Installing Multiple Versions of a Module</span></span>

<span data-ttu-id="51150-172">Para instalar varias versiones del mismo módulo, use el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="51150-172">To install multiple versions of the same module, use the following procedure.</span></span>

1. <span data-ttu-id="51150-173">Cree un directorio para cada versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-173">Create a directory for each version of the module.</span></span> <span data-ttu-id="51150-174">Incluya el número de versión en el nombre del directorio.</span><span class="sxs-lookup"><span data-stu-id="51150-174">Include the version number in the directory name.</span></span>

2. <span data-ttu-id="51150-175">Cree un manifiesto de módulo para cada versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-175">Create a module manifest for each version of the module.</span></span> <span data-ttu-id="51150-176">En el valor de la **ModuleVersion** en el manifiesto de la clave, escriba el número de versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-176">In the value of the **ModuleVersion** key in the manifest, enter the module version number.</span></span> <span data-ttu-id="51150-177">Guarde el archivo de manifiesto (. psd1) en el directorio específico de la versión del módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-177">Save the manifest file (.psd1) in the version-specific directory for the module.</span></span>

3. <span data-ttu-id="51150-178">Agregar la ruta de acceso de carpeta de módulo raíz en el valor de la **PSModulePath** variable de entorno, como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="51150-178">Add the module root folder path to the value of the **PSModulePath** environment variable, as shown in the following examples.</span></span>

<span data-ttu-id="51150-179">Para importar una versión concreta del módulo, el usuario final puede usar el `MinimumVersion` o `RequiredVersion` parámetros de la [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="51150-179">To import a particular version of the module, the end-user can use the `MinimumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="51150-180">Por ejemplo, si el módulo de Fabrikam está disponible en las versiones 8.0 y 9.0, la estructura de directorios del módulo de Fabrikam puede parecerse al siguiente.</span><span class="sxs-lookup"><span data-stu-id="51150-180">For example, if the Fabrikam module is available in versions 8.0 and 9.0, the Fabrikam module directory structure might resemble the following.</span></span>

 ```
C:\Program Files
Fabrikam Manager
  Fabrikam8
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "8.0")
      Fabrikam.dll (module assembly)
  Fabrikam9
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "9.0")
      Fabrikam.dll (module assembly)
```

<span data-ttu-id="51150-181">El instalador agrega tanto de las rutas de acceso del módulo a la **PSModulePath** valor de variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="51150-181">The installer adds both of the module paths to the **PSModulePath** environment variable value.</span></span>

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

<span data-ttu-id="51150-182">Cuando termine estos pasos, el **ListAvailable** parámetro de la [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) obtiene ambos de los módulos de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="51150-182">When these steps are complete, the **ListAvailable** parameter of the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet gets both of the Fabrikam modules.</span></span> <span data-ttu-id="51150-183">Para importar un módulo determinado, utilice el `MiminumVersion` o `RequiredVersion` parámetros de la [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="51150-183">To import a particular module, use the `MiminumVersion` or `RequiredVersion` parameters of the [Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module) cmdlet.</span></span>

<span data-ttu-id="51150-184">Si ambos módulos se importan en la misma sesión y los módulos contienen cmdlets con los mismos nombres, los cmdlets que se importa en último lugar son eficaces en la sesión.</span><span class="sxs-lookup"><span data-stu-id="51150-184">If both modules are imported into the same session, and the modules contain cmdlets with the same names, the cmdlets that are imported last are effective in the session.</span></span>

## <a name="handling-command-name-conflicts"></a><span data-ttu-id="51150-185">Control de conflictos de nombres de comando</span><span class="sxs-lookup"><span data-stu-id="51150-185">Handling Command Name Conflicts</span></span>

<span data-ttu-id="51150-186">Cuando los comandos que exporta un módulo tienen el mismo nombre que los comandos en la sesión del usuario, pueden producirse conflictos de nombre de comando.</span><span class="sxs-lookup"><span data-stu-id="51150-186">Command name conflicts can occur when the commands that a module exports have the same name as commands in the user's session.</span></span>

<span data-ttu-id="51150-187">Cuando una sesión contiene dos comandos que tienen el mismo nombre, Windows PowerShell se ejecuta el tipo de comando que tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="51150-187">When a session contains two commands that have the same name, Windows PowerShell runs the command type that takes precedence.</span></span> <span data-ttu-id="51150-188">Cuando una sesión contiene dos comandos que tienen el mismo nombre y el mismo tipo, Windows PowerShell se ejecuta el comando que se agregó a la sesión más recientemente.</span><span class="sxs-lookup"><span data-stu-id="51150-188">When a session contains two commands that have the same name and the same type, Windows PowerShell runs the command that was added to the session most recently.</span></span> <span data-ttu-id="51150-189">Para ejecutar un comando que no se ejecuta de forma predeterminada, los usuarios pueden calificar el nombre de comando con el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-189">To run a command that is not run by default, users can qualify the command name with the module name.</span></span>

<span data-ttu-id="51150-190">Por ejemplo, si la sesión contiene una `Get-Date` función y el `Get-Date` , Windows PowerShell ejecuta la función de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="51150-190">For example, if the session contains a `Get-Date` function and the `Get-Date` cmdlet, Windows PowerShell runs the function by default.</span></span> <span data-ttu-id="51150-191">Para ejecutar el cmdlet, escriba el comando precedido por el nombre del módulo, como:</span><span class="sxs-lookup"><span data-stu-id="51150-191">To run the cmdlet, preface the command with the module name, such as:</span></span>

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

<span data-ttu-id="51150-192">Para evitar conflictos de nombres, pueden utilizar los autores del módulo el **DefaultCommandPrefix** clave en el manifiesto de módulo para especificar un prefijo de sustantivo para todos los comandos exportados desde el módulo.</span><span class="sxs-lookup"><span data-stu-id="51150-192">To prevent name conflicts, module authors can use the **DefaultCommandPrefix** key in the module manifest to specify a noun prefix for all commands exported from the module.</span></span>

<span data-ttu-id="51150-193">Los usuarios pueden usar el **prefijo** parámetro de la `Import-Module` cmdlet para utilizar un prefijo alternativo.</span><span class="sxs-lookup"><span data-stu-id="51150-193">Users can use the **Prefix** parameter of the `Import-Module` cmdlet to use an alternate prefix.</span></span> <span data-ttu-id="51150-194">El valor de la **prefijo** parámetro tiene prioridad sobre el valor de la **DefaultCommandPrefix** clave.</span><span class="sxs-lookup"><span data-stu-id="51150-194">The value of the **Prefix** parameter takes precedence over the value of the **DefaultCommandPrefix** key.</span></span>

## <a name="see-also"></a><span data-ttu-id="51150-195">Véase también</span><span class="sxs-lookup"><span data-stu-id="51150-195">See Also</span></span>

[<span data-ttu-id="51150-196">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="51150-196">about_Command_Precedence</span></span>](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[<span data-ttu-id="51150-197">Escribir un módulo de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51150-197">Writing a Windows PowerShell Module</span></span>](./writing-a-windows-powershell-module.md)