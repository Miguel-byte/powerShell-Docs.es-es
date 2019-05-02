---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Novedades de PowerShell ISE
ms.assetid: 38648d47-7c27-4b37-a40e-ad29948519c2
ms.openlocfilehash: 2d953bc4553de7720c590304d29750b84a1ef3b2
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058189"
---
# <a name="what39s-new-in-the-windows-powershell-ise"></a><span data-ttu-id="dabd3-103">Novedades de Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="dabd3-103">What&#39;s New in the Windows PowerShell ISE</span></span>
<span data-ttu-id="dabd3-104">En este tema se explican las características nuevas y actualizadas que se introdujeron en las versiones de Entorno de scripting integrado (ISE) de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dabd3-104">This topic explains the new and updated features that have been introduced in versions of Windows PowerShell  Integrated Scripting Environment (ISE).</span></span>

## <a name="feature-description"></a><span data-ttu-id="dabd3-105">Descripción de la característica</span><span class="sxs-lookup"><span data-stu-id="dabd3-105">Feature description</span></span>
<span data-ttu-id="dabd3-106">Windows PowerShell ISE es una aplicación host que permite escribir, ejecutar y probar scripts y módulos en un entorno gráfico e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="dabd3-106">The Windows PowerShell ISE is a host application that enables you to write, run, and test scripts and modules in a graphical and intuitive environment.</span></span> <span data-ttu-id="dabd3-107">Las características principales, como el coloreado de la sintaxis, el procedimiento para completar con el tabulador, la depuración visual, la compatibilidad con Unicode y la Ayuda contextual, proporcionan una rica experiencia de scripting.</span><span class="sxs-lookup"><span data-stu-id="dabd3-107">Key features such as syntax-coloring, tab completion, visual debugging, Unicode compliance, and context-sensitive Help provide a rich scripting experience.</span></span>

<span data-ttu-id="dabd3-108">Para ver una introducción de Windows PowerShell ISE, consulte [Introducción a Windows PowerShell Integrated Scripting Environment](https://technet.microsoft.com/library/3c1892c2-bf84-4cb6-af26-1f453be9e671).</span><span class="sxs-lookup"><span data-stu-id="dabd3-108">For an overview of Windows PowerShell ISE, see [Windows PowerShell Integrated Scripting Environment overview](https://technet.microsoft.com/library/3c1892c2-bf84-4cb6-af26-1f453be9e671).</span></span>

## <a name="new-and-changed-functionality-in-windows-powershell-ise"></a><span data-ttu-id="dabd3-109">Funciones nuevas y modificadas en Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="dabd3-109">New and changed functionality in Windows PowerShell ISE</span></span>
<span data-ttu-id="dabd3-110">En la tabla siguiente se enumeran las características nuevas y modificadas de esta versión de Windows PowerShell ISE en Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dabd3-110">The following table lists the new and changed features for this release of Windows PowerShell ISE in Windows PowerShell.</span></span>

|<span data-ttu-id="dabd3-111">Característica/funcionalidad</span><span class="sxs-lookup"><span data-stu-id="dabd3-111">Feature/functionality</span></span>|<span data-ttu-id="dabd3-112">Windows PowerShell ISE 4.0</span><span class="sxs-lookup"><span data-stu-id="dabd3-112">Windows PowerShell ISE 4.0</span></span>|<span data-ttu-id="dabd3-113">Windows PowerShell ISE 3.0</span><span class="sxs-lookup"><span data-stu-id="dabd3-113">Windows PowerShell ISE 3.0</span></span>|<span data-ttu-id="dabd3-114">Windows PowerShell ISE 2.0</span><span class="sxs-lookup"><span data-stu-id="dabd3-114">Windows PowerShell ISE 2.0</span></span>|
|--------------------------|-----------------------------------------------|-----------------------------------------------|-----------------------------------------------|
|<span data-ttu-id="dabd3-115">**[IntelliSense](#intellisense)**</span><span class="sxs-lookup"><span data-stu-id="dabd3-115">**[IntelliSense](#intellisense)**</span></span>|<span data-ttu-id="dabd3-116">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-116">X</span></span>|<span data-ttu-id="dabd3-117">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-117">X</span></span>||
|<span data-ttu-id="dabd3-118">**[Fragmentos de código](#snippets)**</span><span class="sxs-lookup"><span data-stu-id="dabd3-118">**[Snippets](#snippets)**</span></span>|<span data-ttu-id="dabd3-119">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-119">X</span></span>|<span data-ttu-id="dabd3-120">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-120">X</span></span>||
|<span data-ttu-id="dabd3-121">**[Herramientas de complemento](#add-on-tools)**</span><span class="sxs-lookup"><span data-stu-id="dabd3-121">**[Add-on Tools](#add-on-tools)**</span></span>|<span data-ttu-id="dabd3-122">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-122">X</span></span>|<span data-ttu-id="dabd3-123">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-123">X</span></span>||
|<span data-ttu-id="dabd3-124">**[Administrador de reinicio y guardado automático](#restart-manager-and-auto-save)**</span><span class="sxs-lookup"><span data-stu-id="dabd3-124">**[Restart Manager and Auto-save](#restart-manager-and-auto-save)**</span></span>|<span data-ttu-id="dabd3-125">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-125">X</span></span>|<span data-ttu-id="dabd3-126">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-126">X</span></span>||
|<span data-ttu-id="dabd3-127">**[Lista Usados más recientemente](#most-recently-used-list)**</span><span class="sxs-lookup"><span data-stu-id="dabd3-127">**[Most-recently used list](#most-recently-used-list)**</span></span>|<span data-ttu-id="dabd3-128">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-128">X</span></span>|<span data-ttu-id="dabd3-129">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-129">X</span></span>||
|<span data-ttu-id="dabd3-130">**[Panel de consola](#console-pane)**</span><span class="sxs-lookup"><span data-stu-id="dabd3-130">**[Console Pane](#console-pane)**</span></span>|<span data-ttu-id="dabd3-131">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-131">X</span></span>|<span data-ttu-id="dabd3-132">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-132">X</span></span>||
|<span data-ttu-id="dabd3-133">**[Modificadores de la línea de comandos](#command-line-switches)**</span><span class="sxs-lookup"><span data-stu-id="dabd3-133">**[Command-line switches](#command-line-switches)**</span></span>|<span data-ttu-id="dabd3-134">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-134">X</span></span>|<span data-ttu-id="dabd3-135">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-135">X</span></span>||
|<span data-ttu-id="dabd3-136">**[Nuevas características del editor](#new-editor-features)**</span><span class="sxs-lookup"><span data-stu-id="dabd3-136">**[New editor features](#new-editor-features)**</span></span>|<span data-ttu-id="dabd3-137">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-137">X</span></span>|<span data-ttu-id="dabd3-138">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-138">X</span></span>||
|<span data-ttu-id="dabd3-139">**[Ventana del nuevo visor de Ayuda](#new-help-viewer-window)**</span><span class="sxs-lookup"><span data-stu-id="dabd3-139">**[New Help viewer window](#new-help-viewer-window)**</span></span>|<span data-ttu-id="dabd3-140">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-140">X</span></span>|<span data-ttu-id="dabd3-141">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-141">X</span></span>||
|<span data-ttu-id="dabd3-142">**[Cmdlet Show-Command](#show-command-cmdlet)**</span><span class="sxs-lookup"><span data-stu-id="dabd3-142">**[Show-Command cmdlet](#show-command-cmdlet)**</span></span>|<span data-ttu-id="dabd3-143">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-143">X</span></span>|<span data-ttu-id="dabd3-144">X</span><span class="sxs-lookup"><span data-stu-id="dabd3-144">X</span></span>||

### <a name="intellisense"></a><span data-ttu-id="dabd3-145">Intellisense</span><span class="sxs-lookup"><span data-stu-id="dabd3-145">IntelliSense</span></span>
<span data-ttu-id="dabd3-146">**Agregado en ISE 3.0**</span><span class="sxs-lookup"><span data-stu-id="dabd3-146">**Added in ISE 3.0**</span></span>

<span data-ttu-id="dabd3-147">IntelliSense es una característica de asistencia de finalización automática que forma parte de Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="dabd3-147">IntelliSense is an automatic-completion assistance feature that is part of Windows PowerShell ISE.</span></span> <span data-ttu-id="dabd3-148">Intellisense muestra menús en los que se pueden hacer clic de los cmdlets, parámetros, valores de parámetros, archivos o carpetas potencialmente coincidentes a medida que escribe.</span><span class="sxs-lookup"><span data-stu-id="dabd3-148">IntelliSense displays clickable menus of potentially matching cmdlets, parameters, parameter values, files, or folders as you type.</span></span>

<span data-ttu-id="dabd3-149">**¿Qué valor aporta este cambio?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-149">**What value does this change add?**</span></span>

<span data-ttu-id="dabd3-150">Con la adición de IntelliSense, es más fácil detectar cmdlets y la sintaxis cuando se usa Windows PowerShell ISE para crear scripts.</span><span class="sxs-lookup"><span data-stu-id="dabd3-150">With the addition of IntelliSense, it is easier to discover cmdlets and syntax when you use Windows PowerShell ISE to create scripts.</span></span> <span data-ttu-id="dabd3-151">También puede usar Windows PowerShell ISE para obtener información sobre Windows PowerShell al crear nuevos scripts.</span><span class="sxs-lookup"><span data-stu-id="dabd3-151">You can also use Windows PowerShell ISE to learn Windows PowerShell while you create new scripts.</span></span>

<span data-ttu-id="dabd3-152">**¿Qué funciona de manera diferente?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-152">**What works differently?**</span></span>

<span data-ttu-id="dabd3-153">Si escribe cmdlets en Windows PowerShell ISE 3.0 o posterior, se muestra un menú desplazable en el que puede realizar sus selecciones, que permite examinar y seleccionar los comandos adecuados.</span><span class="sxs-lookup"><span data-stu-id="dabd3-153">When you type cmdlets in the Windows PowerShell ISE 3.0 or later, a scrollable and clickable menu displays, allowing you to browse and select the appropriate commands.</span></span>

### <a name="snippets"></a><span data-ttu-id="dabd3-154">Fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="dabd3-154">Snippets</span></span>
<span data-ttu-id="dabd3-155">**Agregado en ISE 3.0**</span><span class="sxs-lookup"><span data-stu-id="dabd3-155">**Added in ISE 3.0**</span></span>

<span data-ttu-id="dabd3-156">Los *fragmentos de código* son secciones de código de Windows PowerShell breves que puede insertar fácilmente en los scripts que crea en Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="dabd3-156">*Snippets* are short sections of Windows PowerShell code that you can insert into the scripts you create in Windows PowerShell ISE.</span></span> <span data-ttu-id="dabd3-157">Windows PowerShell ISE incluye un conjunto predeterminado de fragmentos de código.</span><span class="sxs-lookup"><span data-stu-id="dabd3-157">Windows PowerShell ISE comes with a default set of snippets.</span></span> <span data-ttu-id="dabd3-158">Puede agregar fragmentos de código mediante el cmdlet **New-Snippet** mientras trabaja en Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="dabd3-158">You can add snippets by using the **New-Snippet** cmdlet while working in Windows PowerShell ISE.</span></span>

<span data-ttu-id="dabd3-159">**¿Qué valor aporta este cambio?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-159">**What value does this change add?**</span></span>

<span data-ttu-id="dabd3-160">El uso de fragmentos de código permite ensamblar y crear rápidamente scripts para automatizar el entorno.</span><span class="sxs-lookup"><span data-stu-id="dabd3-160">By using snippets, you can quickly assemble and create scripts to automate your environment.</span></span>

<span data-ttu-id="dabd3-161">**¿Qué funciona de manera diferente?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-161">**What works differently?**</span></span>

<span data-ttu-id="dabd3-162">Para usar fragmentos de código en Windows PowerShell 3.0 o posterior, en el menú **Edición**, haga clic en **Iniciar fragmentos de código** o presione **Ctrl\-J**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-162">To use snippets in Windows PowerShell 3.0 or later, on the **Edit** menu, click **Start Snippets**, or press **Ctrl-J**.</span></span>

### <a name="add-on-tools"></a><span data-ttu-id="dabd3-163">Herramientas de complemento</span><span class="sxs-lookup"><span data-stu-id="dabd3-163">Add-on tools</span></span>
<span data-ttu-id="dabd3-164">**Agregado en PowerShell 3.0**</span><span class="sxs-lookup"><span data-stu-id="dabd3-164">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="dabd3-165">Windows PowerShell ISE es ahora compatible con las herramientas de complemento, que son controles de Windows Presentation Foundation (WPF) que se agregan mediante el modelo de objetos.</span><span class="sxs-lookup"><span data-stu-id="dabd3-165">Windows PowerShell ISE now supports add-on tools, which are Windows Presentation Foundation (WPF) controls that are added by using the object model.</span></span> <span data-ttu-id="dabd3-166">Las herramientas de complemento se pueden visualizar en la consola en un panel vertical u horizontal.</span><span class="sxs-lookup"><span data-stu-id="dabd3-166">Add-on tools can be displayed as a vertical or horizontal pane in the console.</span></span> <span data-ttu-id="dabd3-167">Si hay varias herramientas de complemento en un panel, se mostrarán como un control de pestaña.</span><span class="sxs-lookup"><span data-stu-id="dabd3-167">Multiple add-on tools in a pane are displayed as a tabbed control.</span></span> <span data-ttu-id="dabd3-168">También puede agregar o quitar herramientas de complemento no producidas por Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dabd3-168">You can also add or remove add-on tools that are produced by non-Microsoft parties.</span></span> <span data-ttu-id="dabd3-169">Para más información sobre cómo importar o quitar herramientas de complemento, consulte el tema sobre las [operaciones de Windows PowerShell ISE](https://technet.microsoft.com/library/cc732148.aspx).</span><span class="sxs-lookup"><span data-stu-id="dabd3-169">For more information about how to import or remove add-on tools, see [Windows PowerShell ISE Operations](https://technet.microsoft.com/library/cc732148.aspx).</span></span>

<span data-ttu-id="dabd3-170">**¿Qué valor aporta este cambio?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-170">**What value does this change add?**</span></span>

<span data-ttu-id="dabd3-171">Los complementos permiten ampliar y personalizar Windows PowerShell ISE con herramientas que pueden mejorar su experiencia de scripting o agregar funcionalidad a Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="dabd3-171">Add-ons allow you to extend and customize Windows PowerShell ISE with tools that can enhance your scripting experience or add functionality to Windows PowerShell ISE.</span></span>

<span data-ttu-id="dabd3-172">**¿Qué funciona de manera diferente?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-172">**What works differently?**</span></span>

<span data-ttu-id="dabd3-173">Windows PowerShell ISE 3.0 y versiones posteriores incluyen el complemento **Commands**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-173">Windows PowerShell ISE 3.0 and later come with the **Commands** add-on.</span></span> <span data-ttu-id="dabd3-174">El complemento **Commands** permite examinar cmdlets y acceder a la ayuda sobre los cmdlets en paralelo con los paneles de **scripts** y de **consola**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-174">The **Commands** add-on allows you to browse cmdlets, and access help about the cmdlets side-by-side with the **Script** and **Console** Panes.</span></span>

<span data-ttu-id="dabd3-175">Puede encontrar complementos adicionales mediante el comando **Abrir sitio web de herramientas de complemento** del menú **Complementos**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-175">Additional add-ons can be found by using the **Open Add-on Tools Website** command on the **Add-ons** menu.</span></span>

### <a name="restart-manager-and-auto-save"></a><span data-ttu-id="dabd3-176">Administrador de reinicio y Autoguardar</span><span class="sxs-lookup"><span data-stu-id="dabd3-176">Restart manager and auto-save</span></span>
<span data-ttu-id="dabd3-177">**Agregado en PowerShell 3.0**</span><span class="sxs-lookup"><span data-stu-id="dabd3-177">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="dabd3-178">Windows PowerShell ISE ahora guarda automáticamente los scripts abiertos cada dos minutos en una ubicación aparte.</span><span class="sxs-lookup"><span data-stu-id="dabd3-178">Windows PowerShell ISE now automatically saves your open scripts every two minutes, in a separate location.</span></span>  <span data-ttu-id="dabd3-179">Si Windows PowerShell ISE deja de funcionar o si el sistema operativo se reinicia, una vez que se reinicia, se recuperarán los scripts que estaban abiertos en la última sesión, aunque no se hayan guardado.</span><span class="sxs-lookup"><span data-stu-id="dabd3-179">If Windows PowerShell ISE stops working, or if the operating system is restarted, after Windows PowerShell ISE restarts, it recovers scripts that were open in the last session, even if the scripts were not saved.</span></span>

<span data-ttu-id="dabd3-180">Para cambiar el intervalo de guardado automático, ejecute el siguiente comando en el panel de consola: **$psise.Options.AutoSaveMinuteInterval**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-180">To change the automatic saving interval, run the following command in the Console pane: **$psise.Options.AutoSaveMinuteInterval**.</span></span>

<span data-ttu-id="dabd3-181">**¿Qué valor aporta este cambio?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-181">**What value does this change add?**</span></span>

<span data-ttu-id="dabd3-182">Ahora puede trabajar en Windows PowerShell ISE con la tranquilidad de saber que los scripts abiertos se guardan automáticamente en el caso de un reinicio inesperado.</span><span class="sxs-lookup"><span data-stu-id="dabd3-182">You can now work within Windows PowerShell ISE knowing that your open scripts are automatically saved in the event of an unexpected restart.</span></span>

<span data-ttu-id="dabd3-183">**¿Qué funciona de manera diferente?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-183">**What works differently?**</span></span>

<span data-ttu-id="dabd3-184">Windows PowerShell ISE 2.0 no guarda los scripts automáticamente en caso de un reinicio.</span><span class="sxs-lookup"><span data-stu-id="dabd3-184">Windows PowerShell ISE 2.0 does not save the scripts automatically in the event of a restart.</span></span>

### <a name="most-recently-used-list"></a><span data-ttu-id="dabd3-185">Lista Usados más recientemente</span><span class="sxs-lookup"><span data-stu-id="dabd3-185">Most-recently used list</span></span>
<span data-ttu-id="dabd3-186">**Agregado en PowerShell 3.0**</span><span class="sxs-lookup"><span data-stu-id="dabd3-186">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="dabd3-187">Windows PowerShell ISE tiene ahora una lista Usados más recientemente para los archivos.</span><span class="sxs-lookup"><span data-stu-id="dabd3-187">Windows PowerShell ISE now has a most-recently used list for files.</span></span> <span data-ttu-id="dabd3-188">Cuando se abre un archivo en Windows PowerShell ISE, este se agrega a la lista Usados más recientemente en el menú **Archivo**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-188">When you open a file in Windows PowerShell ISE, the file is added to the most-recently used list on the **File** menu.</span></span>

<span data-ttu-id="dabd3-189">Para cambiar el número predeterminado de archivos en la lista Usados más recientemente, ejecute el siguiente comando en el panel de consola: **$psise.Options.MruCount**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-189">To change the default number of files in the most-recently used list, run the following command in the Console Pane: **$psise.Options.MruCount**.</span></span>

<span data-ttu-id="dabd3-190">**¿Qué valor aporta este cambio?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-190">**What value does this change add?**</span></span>

<span data-ttu-id="dabd3-191">Ahora puede usar la lista Usados más recientemente para acceder fácilmente a los archivos que usa con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="dabd3-191">You can now use the most-recently used list to easily access your frequently-used files.</span></span>

<span data-ttu-id="dabd3-192">**¿Qué funciona de manera diferente?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-192">**What works differently?**</span></span>

<span data-ttu-id="dabd3-193">Windows PowerShell ISE 2.0 no tiene una lista Usados más recientemente.</span><span class="sxs-lookup"><span data-stu-id="dabd3-193">Windows PowerShell ISE 2.0 does not have a most-recently used list.</span></span>

### <a name="console-pane"></a><span data-ttu-id="dabd3-194">Panel de consola</span><span class="sxs-lookup"><span data-stu-id="dabd3-194">Console Pane</span></span>
<span data-ttu-id="dabd3-195">**Agregado en PowerShell 3.0**</span><span class="sxs-lookup"><span data-stu-id="dabd3-195">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="dabd3-196">Los paneles de comandos y de salida separados que estaban disponibles en la primera versión de Windows PowerShell ISE se combinaron en un solo panel de consola.</span><span class="sxs-lookup"><span data-stu-id="dabd3-196">The separate Command and Output Panes that were available in the first release of Windows PowerShell ISE have been combined into a single Console Pane.</span></span> <span data-ttu-id="dabd3-197">El panel de consola es similar en funciones y apariencia a una consola típica de Windows PowerShell, pero incluye las siguientes mejoras (la mayoría se describen en este tema).</span><span class="sxs-lookup"><span data-stu-id="dabd3-197">The Console Pane is similar in function and appearance to a typical Windows PowerShell console, but it includes the following enhancements (most are described in this topic).</span></span>

- <span data-ttu-id="dabd3-198">El color de la sintaxis del texto de entrada (no texto de salida), incluida la sintaxis XML</span><span class="sxs-lookup"><span data-stu-id="dabd3-198">Syntax coloring for input text (not output text), including XML syntax</span></span>

- <span data-ttu-id="dabd3-199">Intellisense</span><span class="sxs-lookup"><span data-stu-id="dabd3-199">IntelliSense</span></span>

- <span data-ttu-id="dabd3-200">Coincidencia de llaves</span><span class="sxs-lookup"><span data-stu-id="dabd3-200">Brace matching</span></span>

- <span data-ttu-id="dabd3-201">Indicación de errores</span><span class="sxs-lookup"><span data-stu-id="dabd3-201">Error indication</span></span>

- <span data-ttu-id="dabd3-202">Compatibilidad total con Unicode</span><span class="sxs-lookup"><span data-stu-id="dabd3-202">Full Unicode support</span></span>

- <span data-ttu-id="dabd3-203">**F1**: ayuda contextual</span><span class="sxs-lookup"><span data-stu-id="dabd3-203">**F1** context-sensitive help</span></span>

- <span data-ttu-id="dabd3-204">**Ctrl+F1**: cmdlet Show-Command contextual</span><span class="sxs-lookup"><span data-stu-id="dabd3-204">**Ctrl+F1** context-sensitive Show-Command</span></span>

- <span data-ttu-id="dabd3-205">Compatibilidad con scripts complejos y de derecha a izquierda</span><span class="sxs-lookup"><span data-stu-id="dabd3-205">Complex script and right-to-left support</span></span>

- <span data-ttu-id="dabd3-206">Compatibilidad con fuentes</span><span class="sxs-lookup"><span data-stu-id="dabd3-206">Font support</span></span>

- <span data-ttu-id="dabd3-207">Zoom</span><span class="sxs-lookup"><span data-stu-id="dabd3-207">Zoom</span></span>

- <span data-ttu-id="dabd3-208">Modos de selección de líneas y bloques</span><span class="sxs-lookup"><span data-stu-id="dabd3-208">Line-select and block-select modes</span></span>

- <span data-ttu-id="dabd3-209">Conservación del contenido escrito en la línea de comandos cuando presiona la flecha **Arriba** para ver el historial en la consola</span><span class="sxs-lookup"><span data-stu-id="dabd3-209">Preservation of typed content at the command line when you press the **Up** arrow to view history in the console</span></span>

<span data-ttu-id="dabd3-210">**¿Qué valor aporta este cambio?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-210">**What value does this change add?**</span></span>

<span data-ttu-id="dabd3-211">La adición de estos cambios del panel de consola proporciona una experiencia de scripting más coherente con la interfaz de la consola.</span><span class="sxs-lookup"><span data-stu-id="dabd3-211">The addition of these Console Pane changes provides a scripting experience that is more consistent with the console interface.</span></span>

<span data-ttu-id="dabd3-212">**¿Qué funciona de manera diferente?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-212">**What works differently?**</span></span>

<span data-ttu-id="dabd3-213">Windows PowerShell ISE 2.0 presenta paneles de comandos y de salida independientes.</span><span class="sxs-lookup"><span data-stu-id="dabd3-213">Windows PowerShell ISE 2.0 has separate Command and Output Panes.</span></span>

### <a name="command-line-switches"></a><span data-ttu-id="dabd3-214">Modificadores de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="dabd3-214">Command-line switches</span></span>
<span data-ttu-id="dabd3-215">**Agregado en PowerShell 3.0**</span><span class="sxs-lookup"><span data-stu-id="dabd3-215">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="dabd3-216">Si inicia Windows PowerShell ISE desde la línea de comandos (escribiendo **Powershell_ise.exe**), puede agregar los siguientes modificadores de línea de comandos nuevos.</span><span class="sxs-lookup"><span data-stu-id="dabd3-216">If you start Windows PowerShell ISE from the command line (by typing **powershell_ise.exe**), you can add the following new command-line switches.</span></span>

- <span data-ttu-id="dabd3-217">*-NoProfile*: inicia Windows PowerShell ISE sin ejecutar **$profile**</span><span class="sxs-lookup"><span data-stu-id="dabd3-217">*-NoProfile*: Starts Windows PowerShell ISE without running **$profile**</span></span>

- <span data-ttu-id="dabd3-218">*-Help*: muestra una ventana de Ayuda</span><span class="sxs-lookup"><span data-stu-id="dabd3-218">*-Help*: Displays a Help window</span></span>

- <span data-ttu-id="dabd3-219">*-mta*: inicia Windows PowerShell ISE en modo de contenedor multiproceso.</span><span class="sxs-lookup"><span data-stu-id="dabd3-219">*-mta*: Starts Windows PowerShell ISE in multithreaded apartment mode.</span></span> <span data-ttu-id="dabd3-220">El modo de operación predeterminado de Windows PowerShell ISE es el modo de contenedor uniproceso o *-sta*.</span><span class="sxs-lookup"><span data-stu-id="dabd3-220">The default operation mode for Windows PowerShell ISE is single-threaded apartment mode, or *-sta*.</span></span>

<span data-ttu-id="dabd3-221">**¿Qué valor aporta este cambio?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-221">**What value does this change add?**</span></span>

<span data-ttu-id="dabd3-222">La adición de estos modificadores de línea de comandos permite controlar el entorno en el que se ejecuta Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="dabd3-222">The addition of these command-line switches allows you to control the environment in which the Windows PowerShell ISE runs.</span></span>

<span data-ttu-id="dabd3-223">**¿Qué funciona de manera diferente?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-223">**What works differently?**</span></span>

<span data-ttu-id="dabd3-224">Windows PowerShell ISE 2.0 no reconoce estos modificadores de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="dabd3-224">Windows PowerShell ISE 2.0 does not recognize these command-line switches.</span></span>

### <a name="new-editor-features"></a><span data-ttu-id="dabd3-225">Nuevas características del editor</span><span class="sxs-lookup"><span data-stu-id="dabd3-225">New editor features</span></span>
<span data-ttu-id="dabd3-226">**Agregado en PowerShell 3.0**</span><span class="sxs-lookup"><span data-stu-id="dabd3-226">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="dabd3-227">Otras características de edición de Windows PowerShell ISE son:</span><span class="sxs-lookup"><span data-stu-id="dabd3-227">Other Windows PowerShell ISE editing features include:</span></span>

- <span data-ttu-id="dabd3-228">**Color de la sintaxis XML**: Windows PowerShell ISE ahora colorea la sintaxis XML de la misma manera que la sintaxis de código de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dabd3-228">**XML syntax coloring**Windows PowerShell ISE now colors XML syntax in the same way as it colors Windows PowerShell syntax.</span></span>

- <span data-ttu-id="dabd3-229">**Coincidencia de llaves**: Windows PowerShell ISE incluye la coincidencia de llaves y el resaltado, y se pueden usar de las siguientes maneras: (por ejemplo, con el comando **Ir a Igualar** o **Ctrl + ]** se localiza la llave de cierre, si hay alguna llave de apertura seleccionada).</span><span class="sxs-lookup"><span data-stu-id="dabd3-229">**Brace matching** Windows PowerShell ISE includes brace matching and highlighting, and can be used in the following ways: (for example, using the **Go to Match** command or **Ctrl + ]** locates the closing brace, if you have an opening brace selected).</span></span>

- <span data-ttu-id="dabd3-230">**Vista Esquema**: el panel de scripts admite la esquematización, que permite expandir y contraer secciones de código al hacer clic en los signos más o menos en el margen izquierdo.</span><span class="sxs-lookup"><span data-stu-id="dabd3-230">**Outline view** The Script Pane supports outlining, which allows collapsing or expanding sections of code by clicking plus or minus signs in the left margin.</span></span> <span data-ttu-id="dabd3-231">Puede usar llaves o las etiquetas **#region** y **#endregion** para marcar el inicio o el final de una sección contraíble.</span><span class="sxs-lookup"><span data-stu-id="dabd3-231">You can use braces or the **#region** and **#endregion** tags to mark the beginning or end of a collapsible section.</span></span> <span data-ttu-id="dabd3-232">Para expandir o contraer todas las regiones, presione **Ctrl + M**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-232">To expand or collapse all regions, press **Ctrl + M**.</span></span>

- <span data-ttu-id="dabd3-233">**Edición de texto con arrastrar y colocar**: Windows PowerShell ISE permite ahora la edición de texto con arrastrar y colocar.</span><span class="sxs-lookup"><span data-stu-id="dabd3-233">**Drag and drop text editing**Windows PowerShell ISE now supports drag and drop text editing.</span></span> <span data-ttu-id="dabd3-234">Puede seleccionar cualquier bloque de texto y arrastrar el texto a otra ubicación en el editor o la consola para mover el texto.</span><span class="sxs-lookup"><span data-stu-id="dabd3-234">You can select any block of text and drag that text to another location in the editor or the console to move the text.</span></span> <span data-ttu-id="dabd3-235">Si mantiene presionada la tecla Ctrl mientras arrastra el texto seleccionado, al soltar el botón del mouse, el texto se copiará en la nueva ubicación.</span><span class="sxs-lookup"><span data-stu-id="dabd3-235">If you hold down the Ctrl key while you drag the selected text, when you release the mouse button the text is copied to the new location.</span></span> <span data-ttu-id="dabd3-236">En esta versión de Windows PowerShell ISE, así como en su versión anterior, al arrastrar y colocar archivos en Windows PowerShell ISE, el archivo se abre.</span><span class="sxs-lookup"><span data-stu-id="dabd3-236">In this version of Windows PowerShell ISE, as well as the previous version of Windows PowerShell ISE, when you drag and drop files onto Windows PowerShell ISE, Windows PowerShell ISE opens the file.</span></span>

- <span data-ttu-id="dabd3-237">**Presentación de errores de análisis**: los errores de análisis se indican con un subrayado rojo.</span><span class="sxs-lookup"><span data-stu-id="dabd3-237">**Parse error display** Parse errors are indicated with red underlines.</span></span> <span data-ttu-id="dabd3-238">Cuando desplaza el cursor sobre un error indicado, el texto de información sobre herramientas muestra el problema que se encontró en el código.</span><span class="sxs-lookup"><span data-stu-id="dabd3-238">When you hover over an indicated error, tooltip text displays the problem that was found in the code.</span></span>

- <span data-ttu-id="dabd3-239">**Zoom**: el porcentaje de zoom del contenido de la consola puede establecerse mediante el control deslizante del zoom (en la esquina inferior derecha de la ventana de Windows PowerShell ISE) o escribiendo el comando **$psise.options.Zoom** en el panel de consola.</span><span class="sxs-lookup"><span data-stu-id="dabd3-239">**Zoom** The zoom percentage of the console's content can be set by using the zoom slider (in the lower right corner of Windows PowerShell ISE window), or by entering the command **$psise.options.Zoom** in the Console Pane.</span></span>

- <span data-ttu-id="dabd3-240">**Copiar y pegar texto enriquecido**: la copia en el Portapapeles de Windows PowerShell ISE conserva la información de fuente, tamaño y color de la selección original.</span><span class="sxs-lookup"><span data-stu-id="dabd3-240">**Rich text copy and paste** Copying to the clipboard in Windows PowerShell ISE preserves the font, size, and color information of the original selection.</span></span>

- <span data-ttu-id="dabd3-241">**Selección de bloques**: para seleccionar un bloque de texto puede mantener presionada la tecla ALT y seleccionar texto en el panel de scripts con el mouse, o bien presionar **Alt+Mayús+Flecha**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-241">**Block selection** You can select a block of text by holding down the ALT key while selecting text in the Script Pane with your mouse, or by pressing **Alt+Shift+Arrow**.</span></span>

<span data-ttu-id="dabd3-242">**¿Qué valor aporta este cambio?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-242">**What value does this change add?**</span></span>

<span data-ttu-id="dabd3-243">Las características de edición adicionales proporcionan un entorno de edición más coherente y eficaz.</span><span class="sxs-lookup"><span data-stu-id="dabd3-243">The additional editing features provide a more consistent and powerful editing environment.</span></span>

<span data-ttu-id="dabd3-244">**¿Qué funciona de manera diferente?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-244">**What works differently?**</span></span>

<span data-ttu-id="dabd3-245">Estas mejoras de edición no estaban presentes en Windows PowerShell ISE 2.0.</span><span class="sxs-lookup"><span data-stu-id="dabd3-245">These editing enhancements were not present in Windows PowerShell ISE 2.0.</span></span>

### <a name="new-help-viewer-window"></a><span data-ttu-id="dabd3-246">Ventana del nuevo visor de Ayuda</span><span class="sxs-lookup"><span data-stu-id="dabd3-246">New Help viewer window</span></span>
<span data-ttu-id="dabd3-247">**Agregado en PowerShell 3.0**</span><span class="sxs-lookup"><span data-stu-id="dabd3-247">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="dabd3-248">Si presiona **F1** cuando el cursor está en un cmdlet, o si tiene parte de un cmdlet resaltado, el nuevo visor de Ayuda abre la ayuda contextual sobre el cmdlet resaltado.</span><span class="sxs-lookup"><span data-stu-id="dabd3-248">If you press **F1** when your cursor is in a cmdlet, or you have part of a cmdlet highlighted, the new Help viewer opens context-sensitive Help about the highlighted cmdlet.</span></span> <span data-ttu-id="dabd3-249">Para ver la Ayuda acerca de Windows PowerShell, escriba **operators** en el panel de consola y, después, presione **F1**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-249">To display Windows PowerShell About help, type  **operators** in the console pane, and then press **F1**.</span></span>

<span data-ttu-id="dabd3-250">Antes de usar esta característica, descargue la versión más actual de los temas de Ayuda de Windows PowerShell desde el sitio web de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dabd3-250">Before you use this feature, download the most current version of Windows PowerShell Help topics from the Microsoft website.</span></span> <span data-ttu-id="dabd3-251">El método más sencillo para la descarga de los temas de Ayuda es ejecutar el cmdlet **Update-Help** en el panel de consola al ejecutar Windows PowerShell ISE como administrador.</span><span class="sxs-lookup"><span data-stu-id="dabd3-251">The simplest method for downloading the Help topics is to run the **Update-Help** cmdlet in the Console Pane when running Windows PowerShell ISE as administrator.</span></span>

<span data-ttu-id="dabd3-252">Puede modificar donde busca ayuda la tecla **F1**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-252">You can alter where the **F1** key looks for Help.</span></span> <span data-ttu-id="dabd3-253">En el menú **Herramientas**/**Opciones**, en la pestaña **Configuración general**, debajo de **Otra configuración**, puede activar o desactivar la casilla **Usar Ayuda local en lugar de contenido en línea**.</span><span class="sxs-lookup"><span data-stu-id="dabd3-253">In the **Tools**/**Options** menu, on the **General Settings** tab, under **Other Settings**, you can set or clear the checkbox **Use local help content instead of online content**.</span></span> <span data-ttu-id="dabd3-254">Si la activa, el cliente busca la Ayuda del cmdlet en la Ayuda descargada en la carpeta de módulos.</span><span class="sxs-lookup"><span data-stu-id="dabd3-254">If checked, then the client looks for the cmdlet Help in the downloaded Help found in the modules folder.</span></span>  <span data-ttu-id="dabd3-255">Si la casilla se desactiva, el cliente busca en la biblioteca de TechNet para obtener la Ayuda del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="dabd3-255">If the checkbox is cleared, then the client looks on the TechNet library for the cmdlet help.</span></span>

<span data-ttu-id="dabd3-256">**¿Qué valor aporta este cambio?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-256">**What value does this change add?**</span></span>

<span data-ttu-id="dabd3-257">La ayuda contextual sin salir del cmdlet o script actual proporciona una experiencia de aprendizaje sin problemas.</span><span class="sxs-lookup"><span data-stu-id="dabd3-257">Context-sensitive Help without leaving your current cmdlet or script provides a seamless learning experience.</span></span>

<span data-ttu-id="dabd3-258">**¿Qué funciona de manera diferente?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-258">**What works differently?**</span></span>

<span data-ttu-id="dabd3-259">Al presionar F1 en versiones anteriores de Windows PowerShell ISE, se abría el archivo de Ayuda en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="dabd3-259">Pressing F1 in previous versions of Windows PowerShell ISE opened the help file on the local computer.</span></span> <span data-ttu-id="dabd3-260">En Windows PowerShell ISE 3.0 y versiones posteriores, se abre una ventana que contiene la Ayuda del cmdlet, que es configurable y permite realizar búsquedas.</span><span class="sxs-lookup"><span data-stu-id="dabd3-260">In Windows PowerShell ISE 3.0 and later, a window opens that contains the help for the cmdlet that is searchable and configurable.</span></span> <span data-ttu-id="dabd3-261">Esta experiencia de la Ayuda es una novedad de Windows PowerShell ISE 3.0 y la ayuda actualizable es una novedad de Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="dabd3-261">This Help experience is new for Windows PowerShell ISE 3.0, and Updatable Help is new for Windows PowerShell 3.0.</span></span>

### <a name="show-command-cmdlet"></a><span data-ttu-id="dabd3-262">Cmdlet Show-Command</span><span class="sxs-lookup"><span data-stu-id="dabd3-262">Show-Command cmdlet</span></span>
<span data-ttu-id="dabd3-263">**Agregado en PowerShell 3.0**</span><span class="sxs-lookup"><span data-stu-id="dabd3-263">**Added in PowerShell 3.0**</span></span>

<span data-ttu-id="dabd3-264">El cmdlet **Show-Command** permite crear o ejecutar un cmdlet o una función rellenando un formulario gráfico.</span><span class="sxs-lookup"><span data-stu-id="dabd3-264">The **Show-Command** cmdlet enables you to compose or run a cmdlet or function by filling in a graphical form.</span></span> <span data-ttu-id="dabd3-265">El formato permite a los usuarios trabajar con Windows PowerShell en un entorno gráfico.</span><span class="sxs-lookup"><span data-stu-id="dabd3-265">The form lets users work with Windows PowerShell in a graphical environment.</span></span> <span data-ttu-id="dabd3-266">**Show-Command** también permite a los generadores de scripts avanzados crear una GUI rápida basada en Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dabd3-266">**Show-Command** also enables advanced scripters to create a quick Windows PowerShell-based GUI.</span></span>

<span data-ttu-id="dabd3-267">**¿Qué valor aporta este cambio?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-267">**What value does this change add?**</span></span>

<span data-ttu-id="dabd3-268">Si usa **Show-Command** en sus scripts de Windows PowerShell, puede proporcionar a los usuarios el entorno gráfico con que están familiarizados.</span><span class="sxs-lookup"><span data-stu-id="dabd3-268">By using **Show-Command** in your Windows PowerShell scripts, you can provide your users with the graphical environment with which they are familiar.</span></span> <span data-ttu-id="dabd3-269">**Show-Command** también puede ayudar a los nuevos usuarios a aprender a usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dabd3-269">**Show-Command** can also help introductory users learn Windows PowerShell.</span></span>

<span data-ttu-id="dabd3-270">**¿Qué funciona de manera diferente?**</span><span class="sxs-lookup"><span data-stu-id="dabd3-270">**What works differently?**</span></span>

<span data-ttu-id="dabd3-271">Show-Command es una novedad de Windows PowerShell ISE 3.0.</span><span class="sxs-lookup"><span data-stu-id="dabd3-271">Show-Command is new Windows PowerShell ISE 3.0.</span></span>

## <a name="see-also"></a><span data-ttu-id="dabd3-272">Vea también</span><span class="sxs-lookup"><span data-stu-id="dabd3-272">See also</span></span>
<span data-ttu-id="dabd3-273">Para más información sobre cómo usar Windows PowerShell ISE en Windows PowerShell, consulte los siguientes vínculos.</span><span class="sxs-lookup"><span data-stu-id="dabd3-273">For more information about using Windows PowerShell ISE in Windows PowerShell, see the following links.</span></span>

- [<span data-ttu-id="dabd3-274">Exploración del Entorno de scripting integrado de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dabd3-274">Exploring the Windows PowerShell Integrated Scripting Environment</span></span>](../getting-started/fundamental/exploring-the-windows-powershell-ise.md)
- [<span data-ttu-id="dabd3-275">ISE en el Wiki de TechNet</span><span class="sxs-lookup"><span data-stu-id="dabd3-275">ISE on the TechNet Wiki</span></span>](https://social.technet.microsoft.com/wiki/search/searchresults.aspx?q=ISE)
- [<span data-ttu-id="dabd3-276">Centro de scripts</span><span class="sxs-lookup"><span data-stu-id="dabd3-276">Script Center</span></span>](https://technet.microsoft.com/scriptcenter/default)