---
title: Elemento de bloque de script para WideItem para WideControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e00e8f36-76f2-49a0-9b02-3a2a7fceb2dd
caps.latest.revision: 8
ms.openlocfilehash: 6534e9dbfbe0dedf60dadd6467cff9ad9b447ba4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858031"
---
# <a name="scriptblock-element-for-wideitem-for-widecontrol-format"></a><span data-ttu-id="448c4-102">Elemento ScriptBlock para WideItem for WideControl (formato)</span><span class="sxs-lookup"><span data-stu-id="448c4-102">ScriptBlock Element for WideItem for WideControl (Format)</span></span>

<span data-ttu-id="448c4-103">Especifica la secuencia de comandos cuyo valor se muestra en la vista ampliada.</span><span class="sxs-lookup"><span data-stu-id="448c4-103">Specifies the script whose value is displayed in the wide view.</span></span>

<span data-ttu-id="448c4-104">Elemento (formato) elemento ViewDefinitions (formato) vista elemento (formato) elemento WideControl (formato) elemento WideEntries (formato) elemento WideEntry (formato) elemento WideItem (formato) ScriptBlock elemento de configuración para WideItem (formato)</span><span class="sxs-lookup"><span data-stu-id="448c4-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) WideItem Element (Format) ScriptBlock Element for WideItem (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="448c4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="448c4-105">Syntax</span></span>

```xml
<ScriptBlock>ScriptToExecute</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="448c4-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="448c4-106">Attributes and Elements</span></span>

<span data-ttu-id="448c4-107">Las secciones siguientes describen los atributos, elementos secundarios y elemento primario de la `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="448c4-107">The following sections describe the attributes, child elements, and parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="448c4-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="448c4-108">Attributes</span></span>

<span data-ttu-id="448c4-109">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="448c4-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="448c4-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="448c4-110">Child Elements</span></span>

<span data-ttu-id="448c4-111">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="448c4-111">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="448c4-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="448c4-112">Parent Elements</span></span>

|<span data-ttu-id="448c4-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="448c4-113">Element</span></span>|<span data-ttu-id="448c4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="448c4-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="448c4-115">Elemento WideItem (formato)</span><span class="sxs-lookup"><span data-stu-id="448c4-115">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)|<span data-ttu-id="448c4-116">Define el bloque de script o la propiedad cuyo valor se muestra en la vista ampliada.</span><span class="sxs-lookup"><span data-stu-id="448c4-116">Defines the property or script block whose value is displayed in the wide view.</span></span>|

## <a name="text-value"></a><span data-ttu-id="448c4-117">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="448c4-117">Text Value</span></span>

<span data-ttu-id="448c4-118">Especifique el script cuyo valor se muestra.</span><span class="sxs-lookup"><span data-stu-id="448c4-118">Specify the script whose value is displayed.</span></span>

## <a name="remarks"></a><span data-ttu-id="448c4-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="448c4-119">Remarks</span></span>

<span data-ttu-id="448c4-120">Para obtener más información acerca de los componentes de una vista amplia, consulte [crear una vista amplia](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="448c4-120">For more information about the components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="448c4-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="448c4-121">Example</span></span>

<span data-ttu-id="448c4-122">Este ejemplo se muestra un `WideItem` elemento que define una secuencia de comandos cuyo valor se muestra en la vista.</span><span class="sxs-lookup"><span data-stu-id="448c4-122">This example shows a `WideItem` element that defines a script whose value is displayed in the view.</span></span>

```xml
<WideItem>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
</WideItem>
```

## <a name="see-also"></a><span data-ttu-id="448c4-123">Véase también</span><span class="sxs-lookup"><span data-stu-id="448c4-123">See Also</span></span>

[<span data-ttu-id="448c4-124">Elemento WideItem (formato)</span><span class="sxs-lookup"><span data-stu-id="448c4-124">WideItem Element (Format)</span></span>](./wideitem-element-for-widecontrol-format.md)

[<span data-ttu-id="448c4-125">Creación de una vista amplia</span><span class="sxs-lookup"><span data-stu-id="448c4-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="448c4-126">Escribir un archivo de formato de PowerShell</span><span class="sxs-lookup"><span data-stu-id="448c4-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)