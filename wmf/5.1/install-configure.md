---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,setup
contributor: keithb
title: Instalación y configuración de WMF 5.1
ms.openlocfilehash: c439d0851189a89a81fa38194632dc54475a001d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085004"
---
# <a name="install-and-configure-wmf-51"></a><span data-ttu-id="b1c10-103">Instalación y configuración de WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="b1c10-103">Install and Configure WMF 5.1</span></span>

## <a name="download-and-install-the-wmf-51-package"></a><span data-ttu-id="b1c10-104">Descarga e instalación del paquete WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="b1c10-104">Download and install the WMF 5.1 package</span></span>

<span data-ttu-id="b1c10-105">Descargue el paquete WMF 5.1 para el sistema operativo y la arquitectura en la que se va a instalar en:</span><span class="sxs-lookup"><span data-stu-id="b1c10-105">Download the WMF 5.1 package for the operating system and architecture you wish to install it on:</span></span>

| <span data-ttu-id="b1c10-106">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="b1c10-106">Operating System</span></span>       | <span data-ttu-id="b1c10-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b1c10-107">Prerequisites</span></span>           | <span data-ttu-id="b1c10-108">Vínculos de paquete</span><span class="sxs-lookup"><span data-stu-id="b1c10-108">Package Links</span></span>                          |
|------------------------|-------------------------|----------------------------------------|
| <span data-ttu-id="b1c10-109">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b1c10-109">Windows Server 2012 R2</span></span> |                         | <span data-ttu-id="b1c10-110">[Win8.1AndW2K12R2-KB3191564-x64.msu][]</span><span class="sxs-lookup"><span data-stu-id="b1c10-110">[Win8.1AndW2K12R2-KB3191564-x64.msu][]</span></span> |
| <span data-ttu-id="b1c10-111">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b1c10-111">Windows Server 2012</span></span>    |                         | <span data-ttu-id="b1c10-112">[W2K12-KB3191565-x64.msu][]</span><span class="sxs-lookup"><span data-stu-id="b1c10-112">[W2K12-KB3191565-x64.msu][]</span></span>            |
| <span data-ttu-id="b1c10-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b1c10-113">Windows Server 2008 R2</span></span> | <span data-ttu-id="b1c10-114">[.NET Framework 4.5.2][]</span><span class="sxs-lookup"><span data-stu-id="b1c10-114">[.NET Framework 4.5.2][]</span></span>| <span data-ttu-id="b1c10-115">[Win7AndW2K8R2-KB3191566-x64.ZIP][]</span><span class="sxs-lookup"><span data-stu-id="b1c10-115">[Win7AndW2K8R2-KB3191566-x64.ZIP][]</span></span>    |
| <span data-ttu-id="b1c10-116">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b1c10-116">Windows 8.1</span></span>            |                         | <span data-ttu-id="b1c10-117">**x64:** [Win8.1AndW2K12R2-KB3191564-x64.msu][]</span><span class="sxs-lookup"><span data-stu-id="b1c10-117">**x64:** [Win8.1AndW2K12R2-KB3191564-x64.msu][]</span></span></br><span data-ttu-id="b1c10-118">**x86:** [Win8.1-KB3191564-x86.msu][]</span><span class="sxs-lookup"><span data-stu-id="b1c10-118">**x86:** [Win8.1-KB3191564-x86.msu][]</span></span> |
| <span data-ttu-id="b1c10-119">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="b1c10-119">Windows 7 SP1</span></span>          | <span data-ttu-id="b1c10-120">[.NET Framework 4.5.2][]</span><span class="sxs-lookup"><span data-stu-id="b1c10-120">[.NET Framework 4.5.2][]</span></span>| <span data-ttu-id="b1c10-121">**x64:** [Win7AndW2K8R2-KB3191566-x64.ZIP][]</span><span class="sxs-lookup"><span data-stu-id="b1c10-121">**x64:** [Win7AndW2K8R2-KB3191566-x64.ZIP][]</span></span></br><span data-ttu-id="b1c10-122">**x86:** [Win7-KB3191566-x86.ZIP][]</span><span class="sxs-lookup"><span data-stu-id="b1c10-122">**x86:** [Win7-KB3191566-x86.ZIP][]</span></span> |

[.NET Framework 4.5.2]: https://www.microsoft.com/download/details.aspx?id=42642
[W2K12-KB3191565-x64.msu]: https://go.microsoft.com/fwlink/?linkid=839513
[Win7-KB3191566-x86.ZIP]: https://go.microsoft.com/fwlink/?linkid=839522
[Win7AndW2K8R2-KB3191566-x64.ZIP]: https://go.microsoft.com/fwlink/?linkid=839523
[Win8.1-KB3191564-x86.msu]: https://go.microsoft.com/fwlink/?linkid=839521
[Win8.1AndW2K12R2-KB3191564-x64.msu]: https://go.microsoft.com/fwlink/?linkid=839516

## <a name="install-wmf-51-for-windows-server-2008-r2-and-windows-7"></a><span data-ttu-id="b1c10-129">Instalación de WMF 5.1 para Windows Server 2008 R2 y Windows 7</span><span class="sxs-lookup"><span data-stu-id="b1c10-129">Install WMF 5.1 for Windows Server 2008 R2 and Windows 7</span></span>

> [!NOTE]
> <span data-ttu-id="b1c10-130">Las instrucciones de instalación de Windows Server 2008 R2 y Windows 7 han cambiado y se diferencian de las instrucciones para los otros paquetes.</span><span class="sxs-lookup"><span data-stu-id="b1c10-130">Installation instructions for Windows Server 2008 R2 and Windows 7 have changed, and differ from the instructions for the other packages.</span></span> <span data-ttu-id="b1c10-131">Las instrucciones de instalación de Windows Server 2012 R2, Windows Server 2012 y Windows 8.1 se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="b1c10-131">Installation instructions for Windows Server 2012 R2, Windows Server 2012, and Windows 8.1 are below.</span></span>

<span data-ttu-id="b1c10-132">**Instalación de WMF 5.1 para Windows Server 2008 R2 y Windows 7**</span><span class="sxs-lookup"><span data-stu-id="b1c10-132">**Installing WMF 5.1 on Windows Server 2008 R2 and Windows 7**</span></span>

1. <span data-ttu-id="b1c10-133">Desplácese a la carpeta en la que descargó el archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="b1c10-133">Navigate to the folder into which you downloaded the ZIP file.</span></span>

2. <span data-ttu-id="b1c10-134">Haga clic con el botón derecho en el archivo ZIP y seleccione "Extraer todo...".</span><span class="sxs-lookup"><span data-stu-id="b1c10-134">Right-click on the ZIP file, and select "Extract All...".</span></span> <span data-ttu-id="b1c10-135">El archivo Zip contiene dos archivos: un archivo MSU y el archivo de script Install-WMF5.1.PS1.</span><span class="sxs-lookup"><span data-stu-id="b1c10-135">The Zip contains 2 files: an MSU and the Install-WMF5.1.PS1 script file.</span></span>
<span data-ttu-id="b1c10-136">Después de desempaquetar el archivo ZIP, puede copiar el contenido en cualquier máquina que ejecuta Windows 7 o Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="b1c10-136">Once you have unpacked the ZIP file, you can copy the contents to any machine running Windows 7 or Windows Server 2008 R2.</span></span>

3. <span data-ttu-id="b1c10-137">Después de extraer el contenido del archivo ZIP, abra PowerShell como administrador y navegue hasta la carpeta que contiene el contenido del archivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="b1c10-137">After extracting the ZIP file contents, open PowerShell as administrator, then navigate to the folder containing the contents of the ZIP file.</span></span>

4. <span data-ttu-id="b1c10-138">Ejecute el script Install-Wmf5.1.ps1 en esa carpeta y siga las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b1c10-138">Run the Install-Wmf5.1.ps1 script in that folder, and follow the instructions.</span></span> <span data-ttu-id="b1c10-139">Este script comprobará los requisitos previos en la máquina local e instalará WMF 5.1 si se cumplen esos requisitos.</span><span class="sxs-lookup"><span data-stu-id="b1c10-139">This script will check the prerequisites on the local machine, and install WMF 5.1 if the prerequisites have been met.</span></span> <span data-ttu-id="b1c10-140">A continuación, se enumeran los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="b1c10-140">The prerequisites are listed below.</span></span>

<span data-ttu-id="b1c10-141">Install-WMF5.1.ps1 toma los parámetros siguientes para facilitar la automatización de la instalación en Windows Server 2008 R2 y Windows 7:</span><span class="sxs-lookup"><span data-stu-id="b1c10-141">Install-WMF5.1.ps1 takes the following parameters to ease automating the installation on Windows Server 2008 R2 and Windows 7:</span></span>

- <span data-ttu-id="b1c10-142">AcceptEula: cuando se incluye este parámetro, el CLUF se acepta automáticamente y no se muestra.</span><span class="sxs-lookup"><span data-stu-id="b1c10-142">AcceptEula: When this parameter is included, the EULA is automatically accepted and will not be displayed.</span></span>
- <span data-ttu-id="b1c10-143">AllowRestart: este parámetro solo se utiliza si se especifica AcceptEula.</span><span class="sxs-lookup"><span data-stu-id="b1c10-143">AllowRestart: This parameter can only be used if AcceptEula is specified.</span></span> <span data-ttu-id="b1c10-144">Si se incluye este parámetro y se requiere un reinicio después de instalar WMF 5.1, el reinicio se realizará sin pedir confirmación, inmediatamente después de finaliza la instalación.</span><span class="sxs-lookup"><span data-stu-id="b1c10-144">If this parameter is included, and a restart is required after installing WMF 5.1, the restart will happen without prompting immediately after the installation is completed.</span></span>

<span data-ttu-id="b1c10-145">**Requisitos previos de WMF 5.1 para Windows Server 2008 R2 SP1 y Windows 7 SP1**</span><span class="sxs-lookup"><span data-stu-id="b1c10-145">**WMF 5.1 Prerequisites for Windows Server 2008 R2 SP1 and Windows 7 SP1**</span></span>

<span data-ttu-id="b1c10-146">La instalación de WMF 5.1 en Windows Server 2008 R2 SP1 o Windows 7 SP1, requiere lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b1c10-146">Installation of WMF 5.1 on either Windows Server 2008 R2 SP1 or Windows 7 SP1, requires the following:</span></span>
- <span data-ttu-id="b1c10-147">Debe instalarse el service pack más reciente.</span><span class="sxs-lookup"><span data-stu-id="b1c10-147">Latest service pack must be installed.</span></span>
- <span data-ttu-id="b1c10-148">WMF 3.0 **no debe** instalarse.</span><span class="sxs-lookup"><span data-stu-id="b1c10-148">WMF 3.0 **must not** be installed.</span></span> <span data-ttu-id="b1c10-149">La instalación de WMF 5.1 en WMF 3.0 provocará la pérdida de PSModulePath, lo que puede producir errores en otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="b1c10-149">Installing WMF 5.1 over WMF 3.0 will result in the loss of the PSModulePath, which can cause other applications to fail.</span></span> <span data-ttu-id="b1c10-150">Antes de instalar WMF 5.1, debe desinstalar WMF 3.0 o guardar PSModulePath y restaurarlo manualmente una vez completada la instalación de WMF 5.1.</span><span class="sxs-lookup"><span data-stu-id="b1c10-150">Before installing WMF 5.1, you must either un-install WMF 3.0, or save the PSModulePath and then restore it manually after WMF 5.1 installation is complete.</span></span>
- <span data-ttu-id="b1c10-151">WMF 5.1 requiere al menos [.NET Framework 4.5.2](https://www.microsoft.com/en-ca/download/details.aspx?id=42642).</span><span class="sxs-lookup"><span data-stu-id="b1c10-151">WMF 5.1 requires at least [.NET Framework 4.5.2](https://www.microsoft.com/en-ca/download/details.aspx?id=42642).</span></span>
<span data-ttu-id="b1c10-152">Puede instalar Microsoft .NET Framework 4.5.2 mediante las instrucciones que se proporcionan en la ubicación de descarga.</span><span class="sxs-lookup"><span data-stu-id="b1c10-152">You can install Microsoft .NET Framework 4.5.2 by following the instructions at the download location.</span></span>

<span data-ttu-id="b1c10-153">**Dependencia de WinRM**</span><span class="sxs-lookup"><span data-stu-id="b1c10-153">**WinRM Dependency**</span></span>

<span data-ttu-id="b1c10-154">La configuración de estado deseado (DSC) de Windows PowerShell depende de WinRM.</span><span class="sxs-lookup"><span data-stu-id="b1c10-154">Windows PowerShell Desired State Configuration (DSC) depends on WinRM.</span></span>
<span data-ttu-id="b1c10-155">WinRM no está habilitado de forma predeterminada en Windows Server 2008 R2 y Windows 7.</span><span class="sxs-lookup"><span data-stu-id="b1c10-155">WinRM is not enabled by default on Windows Server 2008 R2 and Windows 7.</span></span>
<span data-ttu-id="b1c10-156">Para habilitar WinRM, ejecute `Set-WSManQuickConfig` en una sesión de Windows PowerShell con permisos elevados.</span><span class="sxs-lookup"><span data-stu-id="b1c10-156">Run `Set-WSManQuickConfig`, in a Windows PowerShell elevated session, to enable WinRM.</span></span>

## <a name="install-wmf-51-for-windows-server-2012-r2-windows-server-2012-and-windows-81"></a><span data-ttu-id="b1c10-157">Instalación de WMF 5.1 para Windows Server 2012 R2, Windows 2012 y Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b1c10-157">Install WMF 5.1 for Windows Server 2012 R2, Windows Server 2012, and Windows 8.1</span></span>

<span data-ttu-id="b1c10-158">**Instalación desde el Explorador de Windows (o el Explorador de archivos en Windows Server 2012 R2 o Windows 8.1)**</span><span class="sxs-lookup"><span data-stu-id="b1c10-158">**Install from Windows Explorer (or File Explorer in Windows Server 2012 R2 or Windows 8.1)**</span></span>

1. <span data-ttu-id="b1c10-159">Desplácese a la carpeta en la que descargó el archivo MSU.</span><span class="sxs-lookup"><span data-stu-id="b1c10-159">Navigate to the folder into which you downloaded the MSU file.</span></span>
2. <span data-ttu-id="b1c10-160">Haga doble clic en el archivo MSU para ejecutarlo.</span><span class="sxs-lookup"><span data-stu-id="b1c10-160">Double-click the MSU to run it.</span></span>

<span data-ttu-id="b1c10-161">**Instalación desde el símbolo del sistema**</span><span class="sxs-lookup"><span data-stu-id="b1c10-161">**Installing from the Command Prompt**</span></span>

1. <span data-ttu-id="b1c10-162">Después de descargar el paquete correcto para la arquitectura del equipo, abra una ventana del símbolo del sistema con derechos de usuario elevados (Ejecutar como administrador).</span><span class="sxs-lookup"><span data-stu-id="b1c10-162">After downloading the correct package for your computer's architecture, open a Command Prompt window with elevated user rights (Run as Administrator).</span></span> <span data-ttu-id="b1c10-163">En las opciones de instalación de Server Core de Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2 SP1, el símbolo del sistema se abre de forma predeterminada con derechos de usuario elevados.</span><span class="sxs-lookup"><span data-stu-id="b1c10-163">On the Server Core installation options of Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1, Command Prompt opens with elevated user rights by default.</span></span>
2. <span data-ttu-id="b1c10-164">Cambie los directorios a la carpeta en la que descargó o copió el paquete de instalación de WMF 5.1.</span><span class="sxs-lookup"><span data-stu-id="b1c10-164">Change directories to the folder into which you have downloaded or copied the WMF 5.1 installation package.</span></span>
3. <span data-ttu-id="b1c10-165">Ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="b1c10-165">Run one of the following commands:</span></span>
   - <span data-ttu-id="b1c10-166">En los equipos que están ejecutando Windows Server 2012 R2 o Windows 8.1 x64, ejecute `Win8.1AndW2K12R2-KB3191564-x64.msu /quiet`.</span><span class="sxs-lookup"><span data-stu-id="b1c10-166">On computers that are running Windows Server 2012 R2 or Windows 8.1 x64, run `Win8.1AndW2K12R2-KB3191564-x64.msu /quiet`.</span></span>
   - <span data-ttu-id="b1c10-167">En los equipos que están ejecutando Windows Server 2012, ejecute `W2K12-KB3191565-x64.msu /quiet`.</span><span class="sxs-lookup"><span data-stu-id="b1c10-167">On computers that are running Windows Server 2012, run `W2K12-KB3191565-x64.msu /quiet`.</span></span>
   - <span data-ttu-id="b1c10-168">En los equipos que están ejecutando Windows 8.1 x86, ejecute `Win8.1-KB3191564-x86.msu /quiet`.</span><span class="sxs-lookup"><span data-stu-id="b1c10-168">On computers that are running Windows 8.1 x86, run `Win8.1-KB3191564-x86.msu /quiet`.</span></span>

> [!NOTE]
> <span data-ttu-id="b1c10-169">La instalación de WMF 5.1 requiere un reinicio.</span><span class="sxs-lookup"><span data-stu-id="b1c10-169">Installing WMF 5.1 requires a reboot.</span></span> <span data-ttu-id="b1c10-170">Con la opción `/quiet` se reiniciará el sistema sin advertencias.</span><span class="sxs-lookup"><span data-stu-id="b1c10-170">Using the `/quiet` option will reboot the system without warning.</span></span>
> <span data-ttu-id="b1c10-171">Utilice la opción `/norestart` para evitar reiniciar el sistema.</span><span class="sxs-lookup"><span data-stu-id="b1c10-171">Use the `/norestart` option to avoid rebooting.</span></span> <span data-ttu-id="b1c10-172">Sin embargo, no se instalará WMF 5.1 hasta que haya reiniciado el sistema.</span><span class="sxs-lookup"><span data-stu-id="b1c10-172">However, WMF 5.1 will not be installed until you have rebooted.</span></span>
