---
title: Elemento EntrySelectedBy para CustomEntry para los controles de vista (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3d80a7d-3797-4c46-ae74-ae5cda79b24f
caps.latest.revision: 8
ms.openlocfilehash: efb20c3f2077547e6eb3cb28240512b444f9c481
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859541"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="aeacf-102">Elemento EntrySelectedBy para CustomEntry for Controls for View (formato)</span><span class="sxs-lookup"><span data-stu-id="aeacf-102">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="aeacf-103">Define los tipos de .NET que usan esta definición de control o la condición que debe existir para que esta definición para usarse.</span><span class="sxs-lookup"><span data-stu-id="aeacf-103">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="aeacf-104">Este elemento se usa al definir los controles que pueden usarse en una vista.</span><span class="sxs-lookup"><span data-stu-id="aeacf-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="aeacf-105">Elemento (formato) elemento ViewDefinitions (formato) vista elemento (formato) controles (formato) del elemento Control elemento de configuración para los controles de elemento de control personalizado (formato) de la vista de Control para los controles de elemento de vista (formato) CustomEntries para Control personalizado para los controles de elemento de vista (formato) CustomEntry para CustomEntries para los controles de elemento de vista (formato) EntrySelectedBy para CustomEntry para los controles de vista (formato)</span><span class="sxs-lookup"><span data-stu-id="aeacf-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aeacf-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aeacf-106">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aeacf-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aeacf-107">Attributes and Elements</span></span>

<span data-ttu-id="aeacf-108">Las secciones siguientes describen los atributos, elementos secundarios y elemento primario de la `EntrySelectedBy` elemento.</span><span class="sxs-lookup"><span data-stu-id="aeacf-108">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="aeacf-109">Debe especificar al menos un tipo, el conjunto de selección o condición de selección de una definición.</span><span class="sxs-lookup"><span data-stu-id="aeacf-109">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="aeacf-110">No hay ningún límite máximo para el número de elementos secundarios que puede usar.</span><span class="sxs-lookup"><span data-stu-id="aeacf-110">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="aeacf-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="aeacf-111">Attributes</span></span>

<span data-ttu-id="aeacf-112">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="aeacf-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aeacf-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aeacf-113">Child Elements</span></span>

|<span data-ttu-id="aeacf-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="aeacf-114">Element</span></span>|<span data-ttu-id="aeacf-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="aeacf-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aeacf-116">Elemento SelectionCondition para EntrySelectedBy para los controles de vista (formato)</span><span class="sxs-lookup"><span data-stu-id="aeacf-116">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="aeacf-117">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="aeacf-117">Optional element.</span></span><br /><br /> <span data-ttu-id="aeacf-118">Define la condición que debe existir para que esta definición para usarse.</span><span class="sxs-lookup"><span data-stu-id="aeacf-118">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="aeacf-119">Elemento SelectionSetName para EntrySelectedBy para los controles de vista (formato)</span><span class="sxs-lookup"><span data-stu-id="aeacf-119">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="aeacf-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="aeacf-120">Optional element.</span></span><br /><br /> <span data-ttu-id="aeacf-121">Especifica un conjunto de tipos de .NET que usan esta definición del control.</span><span class="sxs-lookup"><span data-stu-id="aeacf-121">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="aeacf-122">Elemento TypeName para EntrySelectedBy para los controles de vista (formato)</span><span class="sxs-lookup"><span data-stu-id="aeacf-122">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="aeacf-123">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="aeacf-123">Optional element.</span></span><br /><br /> <span data-ttu-id="aeacf-124">Especifica un tipo .NET que usa esta definición del control.</span><span class="sxs-lookup"><span data-stu-id="aeacf-124">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aeacf-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aeacf-125">Parent Elements</span></span>

|<span data-ttu-id="aeacf-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="aeacf-126">Element</span></span>|<span data-ttu-id="aeacf-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="aeacf-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aeacf-128">Elemento CustomEntry para CustomEntries para los controles de vista (formato)</span><span class="sxs-lookup"><span data-stu-id="aeacf-128">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="aeacf-129">Proporciona una definición del control.</span><span class="sxs-lookup"><span data-stu-id="aeacf-129">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aeacf-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="aeacf-130">Remarks</span></span>

<span data-ttu-id="aeacf-131">Condiciones de selección se usan para definir una condición que debe existir para la definición que se usará, por ejemplo, cuando un objeto tiene una propiedad específica o cuando un valor de propiedad específicos o secuencias de comandos se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="aeacf-131">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="aeacf-132">Para obtener más información acerca de las condiciones de selección, consulte [definir condiciones para cuando una entrada de la vista o se usa el elemento](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="aeacf-132">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aeacf-133">Véase también</span><span class="sxs-lookup"><span data-stu-id="aeacf-133">See Also</span></span>

[<span data-ttu-id="aeacf-134">Elemento CustomEntry para CustomEntries para los controles de vista (formato)</span><span class="sxs-lookup"><span data-stu-id="aeacf-134">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="aeacf-135">Escribir un archivo de formato de PowerShell</span><span class="sxs-lookup"><span data-stu-id="aeacf-135">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)