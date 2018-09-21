---
ms.date: 08/23/2018
keywords: powershell, cmdlet
title: Descripción de los conceptos importantes de PowerShell
ms.assetid: 3e601e38-4520-4578-a48d-b6779f1d35ee
ms.openlocfilehash: 577ea0764a172e1821bc492417d8b4e546e31b0b
ms.sourcegitcommit: c170a1608d20d3c925d79c35fa208f650d014146
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2018
ms.locfileid: "43353201"
---
# <a name="understanding-important-powershell-concepts"></a><span data-ttu-id="a113c-103">Descripción de los conceptos importantes de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a113c-103">Understanding important PowerShell concepts</span></span>

<span data-ttu-id="a113c-104">El diseño de PowerShell integra los conceptos de numerosos entornos diferentes.</span><span class="sxs-lookup"><span data-stu-id="a113c-104">The PowerShell design integrates concepts from many different environments.</span></span> <span data-ttu-id="a113c-105">Varios de los conceptos serán familiares para personas con experiencia en shells o entornos de programación.</span><span class="sxs-lookup"><span data-stu-id="a113c-105">Several of the concepts will be familiar to people with experience in shells or programming environments.</span></span> <span data-ttu-id="a113c-106">Sin embargo, pocas personas los conocerán todos.</span><span class="sxs-lookup"><span data-stu-id="a113c-106">However, few people will know about all of them.</span></span> <span data-ttu-id="a113c-107">Observar algunos de estos conceptos nos proporcionará una práctica introducción del shell.</span><span class="sxs-lookup"><span data-stu-id="a113c-107">Looking at some of these concepts provides a useful overview of the shell.</span></span>

## <a name="output-is-object-based"></a><span data-ttu-id="a113c-108">La salida está basada en objetos</span><span class="sxs-lookup"><span data-stu-id="a113c-108">Output is object-based</span></span>

<span data-ttu-id="a113c-109">A diferencia de las interfaces tradicionales de la línea de comandos, los cmdlets de PowerShell están diseñados para tratar con objetos.</span><span class="sxs-lookup"><span data-stu-id="a113c-109">Unlike traditional command-line interfaces, PowerShell cmdlets are designed to deal with objects.</span></span>
<span data-ttu-id="a113c-110">Un objeto es información estructurada que es algo más que la cadena de caracteres que aparece en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="a113c-110">An object is structured information that is more than just the string of characters appearing on the screen.</span></span> <span data-ttu-id="a113c-111">La salida del comando siempre incluye información adicional que puede usarse si es necesaria.</span><span class="sxs-lookup"><span data-stu-id="a113c-111">Command output always carries extra information that you can use if you need it.</span></span>

<span data-ttu-id="a113c-112">Si ha utilizado herramientas de procesamiento de texto para procesar datos en el pasado, verá que se comportan de forma diferente cuando se utilizan en PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a113c-112">If you've used text-processing tools to process data in the past, you'll find that they behave differently when used in PowerShell.</span></span> <span data-ttu-id="a113c-113">En la mayoría de los casos, no necesita herramientas de procesamiento de texto para extraer información específica.</span><span class="sxs-lookup"><span data-stu-id="a113c-113">In most cases, you don't need text-processing tools to extract specific information.</span></span> <span data-ttu-id="a113c-114">Se accede directamente a partes de los datos mediante la sintaxis de objetos estándar de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a113c-114">You directly access portions of the data using standard PowerShell object syntax.</span></span>

## <a name="the-command-family-is-extensible"></a><span data-ttu-id="a113c-115">La familia de comandos es extensible</span><span class="sxs-lookup"><span data-stu-id="a113c-115">The command family is extensible</span></span>

<span data-ttu-id="a113c-116">Las interfaces como **cmd.exe** no proporcionan una manera de extender directamente el conjunto de comandos integrado.</span><span class="sxs-lookup"><span data-stu-id="a113c-116">Interfaces such as **cmd.exe**don't provide a way for you to directly extend the built-in command set.</span></span> <span data-ttu-id="a113c-117">Puede crear herramientas externas de línea de comandos que se ejecuten en **cmd.exe**.</span><span class="sxs-lookup"><span data-stu-id="a113c-117">You can create external command-line tools that run in **cmd.exe**.</span></span> <span data-ttu-id="a113c-118">Pero estas herramientas externas no tienen servicios, como la integración de la ayuda.</span><span class="sxs-lookup"><span data-stu-id="a113c-118">But these external tools don't have services, such as Help integration.</span></span> <span data-ttu-id="a113c-119">**cmd.exe** no sabe automáticamente que estas herramientas externas son comandos válidos.</span><span class="sxs-lookup"><span data-stu-id="a113c-119">**cmd.exe**doesn't automatically know that these external tools are valid commands.</span></span>

<span data-ttu-id="a113c-120">Los comandos nativos de PowerShell nativos se conocen como *cmdlets*.</span><span class="sxs-lookup"><span data-stu-id="a113c-120">The native commands in PowerShell are known as *cmdlets* (pronounced command-lets).</span></span> <span data-ttu-id="a113c-121">Puede crear sus propios módulos y funciones de cmdlets mediante el código compilado o scripts.</span><span class="sxs-lookup"><span data-stu-id="a113c-121">You can create your own cmdlets modules and functions using compiled code or scripts.</span></span> <span data-ttu-id="a113c-122">Los módulos pueden agregar cmdlets y proveedores al shell.</span><span class="sxs-lookup"><span data-stu-id="a113c-122">Modules can add cmdlets and providers to the shell.</span></span> <span data-ttu-id="a113c-123">PowerShell también admite scripts que son análogos a los scripts de shell de UNIX y los archivos por lotes de **cmd.exe**.</span><span class="sxs-lookup"><span data-stu-id="a113c-123">PowerShell also supports scripts that are analogous to UNIX shell scripts and **cmd.exe** batch files.</span></span>

## <a name="powershell-handles-console-input-and-display"></a><span data-ttu-id="a113c-124">PowerShell controla la entrada y la presentación de la consola</span><span class="sxs-lookup"><span data-stu-id="a113c-124">PowerShell handles console input and display</span></span>

<span data-ttu-id="a113c-125">Cuando se escribe un comando, PowerShell siempre procesa la entrada directamente de línea de comandos directamente.</span><span class="sxs-lookup"><span data-stu-id="a113c-125">When you type a command, PowerShell always processes the command-line input directly.</span></span> <span data-ttu-id="a113c-126">PowerShell también formatea la salida que se ve en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="a113c-126">PowerShell also formats the output that you see on the screen.</span></span> <span data-ttu-id="a113c-127">Esta diferencia es significativa porque reduce el trabajo requerido de cada cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a113c-127">This difference is significant because it reduces the work required of each cmdlet.</span></span> <span data-ttu-id="a113c-128">Esto asegura que siempre se pueden hacer las cosas de la misma manera con cualquier cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a113c-128">It ensures that you can always do things the same way with any cmdlet.</span></span> <span data-ttu-id="a113c-129">Los desarrolladores de cmdlets no necesitan escribir código para analizar los argumentos de línea de comandos o formatear la salida.</span><span class="sxs-lookup"><span data-stu-id="a113c-129">Cmdlet developers don't need to write code to parse the command-line arguments or format the output.</span></span>

<span data-ttu-id="a113c-130">Las herramientas de línea de comandos tradicionales tienen sus propios esquemas para solicitar y mostrar la Ayuda.</span><span class="sxs-lookup"><span data-stu-id="a113c-130">Traditional command-line tools have their own schemes for requesting and displaying Help.</span></span> <span data-ttu-id="a113c-131">Algunas herramientas de línea de comandos usan **/?**</span><span class="sxs-lookup"><span data-stu-id="a113c-131">Some command-line tools use **/?**</span></span> <span data-ttu-id="a113c-132">para desencadenar la presentación de la Ayuda; otras usan **-?**, **/H** o incluso **//**.</span><span class="sxs-lookup"><span data-stu-id="a113c-132">to trigger the Help display; others use **-?**, **/H**, or even **//**.</span></span> <span data-ttu-id="a113c-133">Algunas mostrarán la Ayuda en una ventana de interfaz gráfica de usuario, en lugar de hacerlo en la pantalla de la consola.</span><span class="sxs-lookup"><span data-stu-id="a113c-133">Some will display Help in a GUI window, rather than in the console display.</span></span> <span data-ttu-id="a113c-134">Si usa un parámetro equivocado, la herramienta podría omitir la entrada y empezar a ejecutar una tarea automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a113c-134">If you use the wrong parameter, the tool might ignore what you typed and begin executing a task automatically.</span></span>
<span data-ttu-id="a113c-135">Dado que PowerShell analiza y procesa automáticamente la línea de comandos, el parámetro **-?**</span><span class="sxs-lookup"><span data-stu-id="a113c-135">Since PowerShell automatically parses and processes the command line, the **-?**</span></span> <span data-ttu-id="a113c-136">siempre significa "mostrar la Ayuda para este comando".</span><span class="sxs-lookup"><span data-stu-id="a113c-136">parameter always means "show me Help for this command".</span></span>

> [!NOTE]
> <span data-ttu-id="a113c-137">Si se ejecuta una aplicación de gráficos en PowerShell, se abre la ventana de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a113c-137">If you run a graphic application in PowerShell, the window for the application opens.</span></span>
> <span data-ttu-id="a113c-138">PowerShell interviene solo al procesar la entrada de línea de comandos que proporciona o la salida de la aplicación devuelta a la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="a113c-138">PowerShell intervenes only when processing the command-line input you supply or the application output returned to the console window.</span></span> <span data-ttu-id="a113c-139">No afecta al funcionamiento interno de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a113c-139">It does not affect how the application works internally.</span></span>

## <a name="powershell-uses-some-c-syntax"></a><span data-ttu-id="a113c-140">PowerShell usa la sintaxis de C#</span><span class="sxs-lookup"><span data-stu-id="a113c-140">PowerShell uses some C# syntax</span></span>

<span data-ttu-id="a113c-141">PowerShell se basa en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a113c-141">PowerShell is built on the .NET Framework.</span></span> <span data-ttu-id="a113c-142">Comparte algunas características de sintaxis y palabras clave con el lenguaje de programación C#.</span><span class="sxs-lookup"><span data-stu-id="a113c-142">It shares some syntax features and keywords with the C# programming language.</span></span> <span data-ttu-id="a113c-143">Aprender PowerShell puede hacer que sea mucho más fácil conocer C#.</span><span class="sxs-lookup"><span data-stu-id="a113c-143">Learning PowerShell can make it much easier to learn C#.</span></span> <span data-ttu-id="a113c-144">Para aquellos que ya estén familiarizados con C#, las similitudes pueden facilitar el aprendizaje de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a113c-144">If you're already familiar with C#, these similarities can make learning PowerShell easier.</span></span>