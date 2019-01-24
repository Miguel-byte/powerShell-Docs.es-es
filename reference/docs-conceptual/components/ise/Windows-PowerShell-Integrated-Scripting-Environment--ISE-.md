---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Entorno de scripting integrado (ISE) de Windows PowerShell
ms.assetid: f156b92d-0203-46d2-89c7-b4989d32e3d2
ms.openlocfilehash: a5fcc8c813349d0b85cc3af29047424fe787d168
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402186"
---
# <a name="windows-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="233ff-103">Entorno de scripting integrado (ISE) de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="233ff-103">Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

<span data-ttu-id="233ff-104">El Entorno de scripting integrado (ISE ) de Windows PowerShell es uno de los dos hosts para el motor y el lenguaje de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="233ff-104">The Windows PowerShell Integrated Scripting Environment (ISE) is one of two hosts for the Windows PowerShell engine and language.</span></span> <span data-ttu-id="233ff-105">Puede escribir, ejecutar y probar scripts de maneras que no están disponibles en la consola de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="233ff-105">With it you can write, run, and test scripts in ways that are not available in the Windows PowerShell Console.</span></span> <span data-ttu-id="233ff-106">El ISE agrega color de sintaxis, finalización con tabulación, IntelliSense, depuración visual y ayuda contextual.</span><span class="sxs-lookup"><span data-stu-id="233ff-106">The ISE adds syntax-coloring, tab completion, IntelliSense, visual debugging, and context sensitive Help.</span></span>

<span data-ttu-id="233ff-107">El ISE permite ejecutar comandos en un panel de consola, pero también admite paneles que se pueden usar para ver simultáneamente el código fuente del script y otras herramientas que pueden conectarse al ISE.</span><span class="sxs-lookup"><span data-stu-id="233ff-107">The ISE lets you run commands in a console pane, but it also supports panes that you can use to simultaneously view the source code of your script and other tools that can plug into the ISE.</span></span> <span data-ttu-id="233ff-108">También puede abrir varias ventanas de script al mismo tiempo, lo cual es especialmente útil cuando se depura un script que usa las funciones definidas en otros scripts o módulos.</span><span class="sxs-lookup"><span data-stu-id="233ff-108">You can even open up multiple script windows at the same time, which is especially helpful when you are debugging a script that uses functions defined in other scripts or modules.</span></span>

## <a name="whats-new"></a><span data-ttu-id="233ff-109">Novedades</span><span class="sxs-lookup"><span data-stu-id="233ff-109">What’s New</span></span>

<span data-ttu-id="233ff-110">Estas son algunas de las características que se agregaron al ISE en las versiones más recientes de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="233ff-110">Here are some of the features that have been added to the ISE in the most recent releases of PowerShell.</span></span>

### <a name="added-in-powershell-30-windows-server-2012-windows-8"></a><span data-ttu-id="233ff-111">Agregado en PowerShell 3.0 (Windows Server 2012, Windows 8)</span><span class="sxs-lookup"><span data-stu-id="233ff-111">Added in PowerShell 3.0 (Windows Server 2012, Windows 8)</span></span>

<span data-ttu-id="233ff-112">**Intellisense** completa automáticamente sus comandos mostrando menús de cmdlets, parámetros, valores de parámetros, archivos o carpetas coincidentes a medida que escribe.</span><span class="sxs-lookup"><span data-stu-id="233ff-112">**IntelliSense** automatically completes your commands by displaying menus of matching cmdlets, parameters, parameter values, files, or folders as you type.</span></span>

<span data-ttu-id="233ff-113">**Fragmentos de código** son secciones de código breves que puede insertar fácilmente en los scripts que escribe.</span><span class="sxs-lookup"><span data-stu-id="233ff-113">**Snippets** are short sections of code that you can easily insert into the scripts your write.</span></span> <span data-ttu-id="233ff-114">Una colección de fragmentos de código útiles se incluye en el cuadro y puede agregar más mediante el cmdlet **New-Snippet**.</span><span class="sxs-lookup"><span data-stu-id="233ff-114">A collection of useful snippets is included in the box and you can more by using the **New-Snippet** cmdlet.</span></span>

<span data-ttu-id="233ff-115">Se pueden crear **herramientas de complemento** que agreguen características al ISE mediante la escritura de código que interactúe con el [modelo de objetos de scripting de Windows PowerShell ISE](../../core-powershell/ise/The-ISE-Object-Model-Hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="233ff-115">**Add-on tools** that add features to the ISE can be created by writing code that interacts with [The Windows PowerShell ISE Scripting Object Model](../../core-powershell/ise/The-ISE-Object-Model-Hierarchy.md).</span></span>

<span data-ttu-id="233ff-116">Estas herramientas pueden mostrar controles en un panel con fichas o funcionar de manera invisible en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="233ff-116">These tools can display controls in a tabbed pane or work invisibly in the background.</span></span> <span data-ttu-id="233ff-117">El complemento **Comandos** es un buen ejemplo. Se incluye con la versión 3.0 y posteriores, que muestra una lista de los comandos disponibles y su ayuda.</span><span class="sxs-lookup"><span data-stu-id="233ff-117">The **Commands** add-on is a good example and is included with version 3.0 and later that displays a list of the available commands and their Help.</span></span>

<span data-ttu-id="233ff-118">**Administrador de reinicio y Autoguardar** permite guardar automáticamente los scripts cada dos minutos para ayudar a evitar la pérdida del trabajo en caso de un bloqueo o reinicio inesperado.</span><span class="sxs-lookup"><span data-stu-id="233ff-118">**Restart Manager and Auto-save** automatically save your scripts every two minutes to help you avoid the loss of your work in the event of a crash or unexpected restart.</span></span>

<span data-ttu-id="233ff-119">Ahora, la **lista Usados más recientemente** forma parte del menú Abrir archivo para que sea más fácil obtener acceso a los archivos que se usan con mayor frecuencia.</span><span class="sxs-lookup"><span data-stu-id="233ff-119">**Most Recently Used list** is now part of the File Open menu to make it easier to get to the files you use most often.</span></span>

<span data-ttu-id="233ff-120">**Panel de consola combinado**.</span><span class="sxs-lookup"><span data-stu-id="233ff-120">**Merged Console pane**.</span></span> <span data-ttu-id="233ff-121">En versiones anteriores del ISE, los paneles de comandos y salida eran independientes.</span><span class="sxs-lookup"><span data-stu-id="233ff-121">In previous versions of the ISE there were separate Command and Output panes.</span></span> <span data-ttu-id="233ff-122">Ahora se combinan en un solo panel que representa más directamente lo que se ve en la consola de Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="233ff-122">They are now combined into a single pane that more directly mimics what you see in the Windows Powershell Console.</span></span>

<span data-ttu-id="233ff-123">**Modificadores de la línea de comandos**.</span><span class="sxs-lookup"><span data-stu-id="233ff-123">**Command-line switches**.</span></span> <span data-ttu-id="233ff-124">Varios modificadores de la línea de comandos nuevos ofrecen un mayor control sobre el funcionamiento del ISE.</span><span class="sxs-lookup"><span data-stu-id="233ff-124">Several new command-line switches give you more control over the way the ISE works.</span></span> <span data-ttu-id="233ff-125">-NoProfile inicia el ISE sin ejecutar un script de perfil.</span><span class="sxs-lookup"><span data-stu-id="233ff-125">-NoProfile starts the ISE without running a profile script.</span></span> <span data-ttu-id="233ff-126">-Help abre una ventana de ayuda con el ISE.</span><span class="sxs-lookup"><span data-stu-id="233ff-126">-Help opens up a help window with the ISE.</span></span> <span data-ttu-id="233ff-127">-mta inicia el ISE en "modo de contenedor multiproceso".</span><span class="sxs-lookup"><span data-stu-id="233ff-127">-mta starts the ISE in “multi-threaded apartment mode”.</span></span> <span data-ttu-id="233ff-128">El modo predeterminado es el de uniproceso.</span><span class="sxs-lookup"><span data-stu-id="233ff-128">The default is single-threaded.</span></span>

<span data-ttu-id="233ff-129">Las **nuevas características del editor** facilitan la creación y lectura del código:</span><span class="sxs-lookup"><span data-stu-id="233ff-129">**New editor features** make it easier to create and read your code:</span></span>

- <span data-ttu-id="233ff-130">**Color de la sintaxis XML**.</span><span class="sxs-lookup"><span data-stu-id="233ff-130">**XML syntax coloring**.</span></span> <span data-ttu-id="233ff-131">El editor de ISE colorea ahora la sintaxis XML de la misma manera que la sintaxis de código de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="233ff-131">The ISE editor now colors XML syntax in the same way as it colors Windows PowerShell code syntax.</span></span>

- <span data-ttu-id="233ff-132">**Coincidencia de llaves**.</span><span class="sxs-lookup"><span data-stu-id="233ff-132">**Brace matching**.</span></span> <span data-ttu-id="233ff-133">Windows PowerShell ISE resalta las llaves coincidentes para que pueda asegurarse de tener la cantidad correcta de llaves de cierre según la cantidad de llaves de apertura.</span><span class="sxs-lookup"><span data-stu-id="233ff-133">The ISEWindows PowerShell ISE highlights matching braces to help you ensure you have the right number of closing braces to match your opening ones.</span></span> <span data-ttu-id="233ff-134">Use CTRL-\[ para ubicar la llave de cierre que coincida con la llave de apertura en la que se encuentra en cursor.</span><span class="sxs-lookup"><span data-stu-id="233ff-134">Use CTRL-\[ to locate the closing brace that matches the opening brace that the cursor is on.</span></span>

- <span data-ttu-id="233ff-135">**Vista Esquema**.</span><span class="sxs-lookup"><span data-stu-id="233ff-135">**Outline view**.</span></span> <span data-ttu-id="233ff-136">Puede contraer o expandir las secciones del código haciendo clic en los signos más y menos del margen izquierdo.</span><span class="sxs-lookup"><span data-stu-id="233ff-136">You can collapse or expand sections of your code by clicking the plus and minus signs in the left margin.</span></span> <span data-ttu-id="233ff-137">De este modo, podrá encontrar fácilmente el código que busca en un script largo.</span><span class="sxs-lookup"><span data-stu-id="233ff-137">This makes it easier to find the code you’re looking for in a long script.</span></span>

- <span data-ttu-id="233ff-138">**Editar texto con arrastrar y colocar**.</span><span class="sxs-lookup"><span data-stu-id="233ff-138">**Drag and drop text editing**.</span></span> <span data-ttu-id="233ff-139">Puede seleccionar un bloque de texto y arrastrarlo a otra ubicación para moverlo.</span><span class="sxs-lookup"><span data-stu-id="233ff-139">You can select a block of text and drag it to another location to move it.</span></span> <span data-ttu-id="233ff-140">Si mantiene presionada la tecla Ctrl mientras arrastra el texto seleccionado, lo copiará en lugar de moverlo.</span><span class="sxs-lookup"><span data-stu-id="233ff-140">If you hold down the Ctrl key while you drag the selected text you copy instead of move.</span></span>

- <span data-ttu-id="233ff-141">**Presentación de errores de análisis**.</span><span class="sxs-lookup"><span data-stu-id="233ff-141">**Parse error display**.</span></span> <span data-ttu-id="233ff-142">Windows PowerShell examina el script a medida que escribe.</span><span class="sxs-lookup"><span data-stu-id="233ff-142">Windows PowerShell examines your script as you type.</span></span> <span data-ttu-id="233ff-143">Si detecta un error, muestra un zigzag rojo bajo el código incorrecto.</span><span class="sxs-lookup"><span data-stu-id="233ff-143">If it detects an error, it shows a red squiggle under the offending code.</span></span> <span data-ttu-id="233ff-144">Al mantener el puntero sobre el error indicado, la información sobre herramientas muestra el problema encontrado.</span><span class="sxs-lookup"><span data-stu-id="233ff-144">When you hover over the indicated error, a tooltip shows you the problem that was found.</span></span>

- <span data-ttu-id="233ff-145">**Zoom**.</span><span class="sxs-lookup"><span data-stu-id="233ff-145">**Zoom**.</span></span> <span data-ttu-id="233ff-146">Puede acercar el texto para que resulte más fácil de leer o alejarlo para ver la imagen más grande mediante el control deslizante de la esquina inferior derecha de la ventana del ISE.</span><span class="sxs-lookup"><span data-stu-id="233ff-146">You can zoom in on your text to make it easier to read or zoom out to see the bigger picture by using the slider in the bottom-right corner of the ISE window.</span></span>

- <span data-ttu-id="233ff-147">**Copia y pegado de texto enriquecido**.</span><span class="sxs-lookup"><span data-stu-id="233ff-147">**Rich text copy and paste**.</span></span> <span data-ttu-id="233ff-148">Al copia texto del ISE en el Portapapeles, se incluye la información de fuente, tamaño y de color del texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="233ff-148">When you copy from the ISE to the clipboard, the font, size, and color information of the selected text is included.</span></span>

- <span data-ttu-id="233ff-149">**Selección de bloques**.</span><span class="sxs-lookup"><span data-stu-id="233ff-149">**Block selection**.</span></span> <span data-ttu-id="233ff-150">Para seleccionar un fragmento de texto en forma de bloque, puede mantener presionada la tecla ALT y seleccionar texto en el panel de scripts con el ratón, o bien presionar **Alt+Mayús+Flecha**.</span><span class="sxs-lookup"><span data-stu-id="233ff-150">You can select a block-shaped chunk of text by holding down the ALT key while selecting text in the script pane with your mouse, or by pressing **Alt+Shift+Arrow**.</span></span>

### <a name="added-in-powershell-20-windows-server-2008-r2-windows-7"></a><span data-ttu-id="233ff-151">Agregado en PowerShell 2.0 (Windows Server 2008 R2, Windows 7)</span><span class="sxs-lookup"><span data-stu-id="233ff-151">Added in PowerShell 2.0 (Windows Server 2008 R2, Windows 7)</span></span>

<span data-ttu-id="233ff-152">El ISE se introdujo con PowerShell 2.0.</span><span class="sxs-lookup"><span data-stu-id="233ff-152">The ISE was introduced with PowerShell v2.0.</span></span>

## <a name="requirements-for-running-the-windows-powershell-ise"></a><span data-ttu-id="233ff-153">Requisitos para ejecutar Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="233ff-153">Requirements for running the Windows PowerShell ISE</span></span>

<span data-ttu-id="233ff-154">El ISE está disponible en cualquier equipo Windows que puede ejecutar Windows PowerShell 2.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="233ff-154">The ISE is available on any Windows computer that can run Windows PowerShell v2.0 or later.</span></span> <span data-ttu-id="233ff-155">Cada versión de Windows y Windows Server incluye una versión de Windows PowerShell y el ISE, pero se puede actualizar a la versión más reciente disponible mediante la instalación de Windows Management Framework (WMF).</span><span class="sxs-lookup"><span data-stu-id="233ff-155">Each version of Windows and Windows Server includes a version of Windows PowerShell and the ISE, but you can upgrade to the latest available by installing the Windows Management Framework (WMF).</span></span> <span data-ttu-id="233ff-156">Consulte la documentación del [WMF](/powershell/wmf) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="233ff-156">See the [WMF](/powershell/wmf) documentation for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="233ff-157">Dado que Windows PowerShell ISE requiere una interfaz gráfica de usuario, no puede ejecutar la opción Server Core de Windows Server.</span><span class="sxs-lookup"><span data-stu-id="233ff-157">Because Windows PowerShell ISE requires a graphical user interface, you can’t run it on the Server Core option of Windows Server.</span></span>

## <a name="see-also"></a><span data-ttu-id="233ff-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="233ff-158">See also</span></span>

[<span data-ttu-id="233ff-159">Finalidad del modelo de objetos de scripting de Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="233ff-159">Purpose of the windows power shell ise scripting object model</span></span>](../../core-powershell/ise/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)