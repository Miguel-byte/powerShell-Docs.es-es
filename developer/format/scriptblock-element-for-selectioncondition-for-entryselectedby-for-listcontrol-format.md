---
title: Elemento de bloque de script para SelectionCondition para EntrySelectedBy para ListControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1adad7-e864-4892-9d26-a6476a9698d2
caps.latest.revision: 7
ms.openlocfilehash: fd708473d04a76bcf6cf3a8f8278e1d15fb9addf
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858661"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="1413e-102">Elemento ScriptBlock para SelectionCondition for EntrySelectedBy for ListControl (formato)</span><span class="sxs-lookup"><span data-stu-id="1413e-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="1413e-103">Especifica la secuencia de comandos que desencadena la condición.</span><span class="sxs-lookup"><span data-stu-id="1413e-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="1413e-104">Cuando se evalúa esta secuencia de comandos para `true`, se cumple la condición y se usa la entrada de la lista.</span><span class="sxs-lookup"><span data-stu-id="1413e-104">When this script is evaluated to `true`, the condition is met, and the list entry is used.</span></span>

<span data-ttu-id="1413e-105">Elemento (formato) elemento ViewDefinitions (formato) vista elemento (formato) elemento ListControl (formato) elemento ListEntries (formato) elemento ListEntry (formato) EntrySelectedBy elemento de configuración para ListEntry (formato) SelectionCondition (elemento) para EntrySelectedBy para elemento de bloque de script de ListEntry (formato) de SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="1413e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="1413e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1413e-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1413e-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1413e-107">Attributes and Elements</span></span>

<span data-ttu-id="1413e-108">Las secciones siguientes describen los atributos, elementos secundarios y el elemento primario de la `ScriptBlock` elemento.</span><span class="sxs-lookup"><span data-stu-id="1413e-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="1413e-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="1413e-109">Attributes</span></span>

<span data-ttu-id="1413e-110">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="1413e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="1413e-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1413e-111">Child Elements</span></span>

<span data-ttu-id="1413e-112">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="1413e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1413e-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1413e-113">Parent Elements</span></span>

|<span data-ttu-id="1413e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="1413e-114">Element</span></span>|<span data-ttu-id="1413e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="1413e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="1413e-116">Elemento SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="1413e-116">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="1413e-117">Define la condición que debe existir para que esta entrada de lista para usarse.</span><span class="sxs-lookup"><span data-stu-id="1413e-117">Defines the condition that must exist for this list entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="1413e-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="1413e-118">Text Value</span></span>

<span data-ttu-id="1413e-119">Especifique el script que se evalúa.</span><span class="sxs-lookup"><span data-stu-id="1413e-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="1413e-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1413e-120">Remarks</span></span>

<span data-ttu-id="1413e-121">La condición de selección debe especificar un nombre de la secuencia de comandos o la propiedad del uno menor para evaluar, pero no se pueden especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="1413e-121">The selection condition must specify a least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="1413e-122">(Para obtener más información acerca de cómo se pueden utilizar condiciones de selección, consulte [definir condiciones para cuando una entrada de la vista o se usa el elemento](./defining-conditions-for-displaying-data.md).)</span><span class="sxs-lookup"><span data-stu-id="1413e-122">(For more information about how selection conditions can be used, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).)</span></span>

<span data-ttu-id="1413e-123">Para obtener más información acerca de los demás componentes de una vista de lista, consulte [vista de lista](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="1413e-123">For more information about the other components of a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1413e-124">Véase también</span><span class="sxs-lookup"><span data-stu-id="1413e-124">See Also</span></span>

[<span data-ttu-id="1413e-125">Elemento ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="1413e-125">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="1413e-126">Elemento PropertyName para SelectionCondition para EmtrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="1413e-126">PropertyName Element for SelectionCondition for EmtrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="1413e-127">Elemento SelectionCondition para EntrySelectedBy para ListEntry (formato)</span><span class="sxs-lookup"><span data-stu-id="1413e-127">SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="1413e-128">Vista de lista</span><span class="sxs-lookup"><span data-stu-id="1413e-128">List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="1413e-129">Definir condiciones para cuando se usa un movimiento de la vista o un elemento</span><span class="sxs-lookup"><span data-stu-id="1413e-129">Defining Conditions for when a View Entry or Item is Used</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="1413e-130">Escribir un formato de Windows PowerShell y los tipos de archivo</span><span class="sxs-lookup"><span data-stu-id="1413e-130">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)