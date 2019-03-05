---
title: Colocación de Ayuda basada en comentarios en las secuencias de comandos | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 49f8267c-d887-4d7d-b9b7-80dc624b1261
caps.latest.revision: 4
ms.openlocfilehash: d199c53a748ac57bb2a5f998b5056e39d3e80c0d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860771"
---
# <a name="placing-comment-based-help-in-scripts"></a><span data-ttu-id="70b9e-102">Colocación de la Ayuda basada en comentarios en los scripts</span><span class="sxs-lookup"><span data-stu-id="70b9e-102">Placing Comment-Based Help in Scripts</span></span>

<span data-ttu-id="70b9e-103">En este tema se explica dónde colocar Ayuda basada en comentarios de un script para que el `Get-Help` cmdlet asocia el tema de Ayuda basada en comentarios con secuencias de comandos y no con todas las funciones que podrían estar en la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="70b9e-103">This topic explains where to place comment-based help for a script so that the `Get-Help` cmdlet associates the comment-based help topic with scripts and not with any functions that might be in the script.</span></span>

## <a name="where-to-place-comment-based-help-for-a-script"></a><span data-ttu-id="70b9e-104">Dónde colocar Ayuda basada en comentarios de un Script</span><span class="sxs-lookup"><span data-stu-id="70b9e-104">Where to Place Comment-Based Help for a Script</span></span>

- <span data-ttu-id="70b9e-105">Al principio del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="70b9e-105">At the beginning of the script file.</span></span> <span data-ttu-id="70b9e-106">Ayuda de la secuencia de comandos puede ir precedida de la secuencia de comandos sólo comentarios y las líneas en blanco.</span><span class="sxs-lookup"><span data-stu-id="70b9e-106">Script Help can be preceded in the script only by comments and blank lines.</span></span>

- <span data-ttu-id="70b9e-107">Al final del archivo de script.</span><span class="sxs-lookup"><span data-stu-id="70b9e-107">At the end of the script file.</span></span>

  <span data-ttu-id="70b9e-108">Si el primer elemento en el cuerpo de la secuencia de comandos (después de la Ayuda) es una declaración de función, debe haber al menos dos líneas en blanco entre el final de la Ayuda de la secuencia de comandos y la declaración de función.</span><span class="sxs-lookup"><span data-stu-id="70b9e-108">If the first item in the script body (after the Help) is a function declaration, there must be at least two blank lines between the end of the script Help and the function declaration.</span></span> <span data-ttu-id="70b9e-109">En caso contrario, la Ayuda se interpreta como ayuda para la función, no ayuda para la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="70b9e-109">Otherwise, the Help is interpreted as being Help for the function, not Help for the script.</span></span>

## <a name="examples-of-help-placement-in-a-script"></a><span data-ttu-id="70b9e-110">Ejemplos de una posición de la Ayuda en una secuencia de comandos</span><span class="sxs-lookup"><span data-stu-id="70b9e-110">Examples of Help Placement in a Script</span></span>

 <span data-ttu-id="70b9e-111">Los ejemplos siguientes muestran cada una de las opciones de selección de ubicación para Ayuda basada en comentarios de un script.</span><span class="sxs-lookup"><span data-stu-id="70b9e-111">The following examples show each of the placement options for comment-based help for a script.</span></span>

### <a name="help-at-the-beginning-of-a-script"></a><span data-ttu-id="70b9e-112">Ayuda al principio de una secuencia de comandos</span><span class="sxs-lookup"><span data-stu-id="70b9e-112">Help at the Beginning of a Script</span></span>

 <span data-ttu-id="70b9e-113">El ejemplo siguiente se muestra basada en comentarios al principio de una secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="70b9e-113">The following example shows comment-based at the beginning of a script.</span></span>

```
<#
.Description
This script performs a series of network connection tests.
#>

param [string]$ComputerName
...
```

### <a name="help-at-the-end-of-a-script"></a><span data-ttu-id="70b9e-114">Ayuda al final de una secuencia de comandos</span><span class="sxs-lookup"><span data-stu-id="70b9e-114">Help at the End of a Script</span></span>

 <span data-ttu-id="70b9e-115">El ejemplo siguiente se muestra basada en comentarios al final de una secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="70b9e-115">The following example shows comment-based at the end of a script.</span></span>

```powershell
...
function Ping { Test-Connection -ComputerName $ComputerName }

<#
.Description
This script performs a series of network connection tests.
#>

```