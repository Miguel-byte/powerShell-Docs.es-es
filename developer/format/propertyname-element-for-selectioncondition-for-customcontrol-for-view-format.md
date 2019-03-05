---
title: Elemento PropertyName para SelectionCondition para el control personalizado para la vista (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc48a417-2083-46d4-ac38-16c12e65b6b9
caps.latest.revision: 7
ms.openlocfilehash: e08037d5d051d3be51e90193c7e87cc2e738f78a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860971"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="db9ec-102">Elemento PropertyName para SelectionCondition for CustomControl for View (formato)</span><span class="sxs-lookup"><span data-stu-id="db9ec-102">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="db9ec-103">Especifica la propiedad de .NET que desencadena la condición.</span><span class="sxs-lookup"><span data-stu-id="db9ec-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="db9ec-104">Cuando esta propiedad está presente o cuando se evalúa como `true`, se cumple la condición y se usa la definición.</span><span class="sxs-lookup"><span data-stu-id="db9ec-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="db9ec-105">Este elemento se usa al definir una vista de control personalizado.</span><span class="sxs-lookup"><span data-stu-id="db9ec-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="db9ec-106">Configuración (formato) elemento ViewDefinitions (formato) Vista (formato) del elemento control personalizado elemento de vista (formato) del elemento CustomEntries para el control personalizado de vista (formato) del elemento CustomEntry para CustomEntries para el control personalizado para la vista ( Elemento de formato) CustomItem para CustomEntry para el control personalizado de vista (formato) del elemento EntrySelectedBy para CustomEntry para el control personalizado de vista (formato) del elemento SelectionCondition para EntrySelectedBy para el control personalizado para PropertyName vista (formato) Elemento para SelectionCondition para el control personalizado para la vista (formato)</span><span class="sxs-lookup"><span data-stu-id="db9ec-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="db9ec-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db9ec-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="db9ec-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="db9ec-108">Attributes and Elements</span></span>

<span data-ttu-id="db9ec-109">Las secciones siguientes describen los atributos, elementos secundarios y el elemento primario de la `PropertyName` elemento.</span><span class="sxs-lookup"><span data-stu-id="db9ec-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="db9ec-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="db9ec-110">Attributes</span></span>

<span data-ttu-id="db9ec-111">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="db9ec-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="db9ec-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="db9ec-112">Child Elements</span></span>

<span data-ttu-id="db9ec-113">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="db9ec-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="db9ec-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="db9ec-114">Parent Elements</span></span>

|<span data-ttu-id="db9ec-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="db9ec-115">Element</span></span>|<span data-ttu-id="db9ec-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="db9ec-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="db9ec-117">Elemento SelectionCondition para EntrySelectedBy para el control personalizado para la vista (formato)</span><span class="sxs-lookup"><span data-stu-id="db9ec-117">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="db9ec-118">Define una condición que debe cumplirse para que se usará la definición del control.</span><span class="sxs-lookup"><span data-stu-id="db9ec-118">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="db9ec-119">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="db9ec-119">Text Value</span></span>

<span data-ttu-id="db9ec-120">Especifique el nombre de propiedad. NET.</span><span class="sxs-lookup"><span data-stu-id="db9ec-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="db9ec-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="db9ec-121">Remarks</span></span>

<span data-ttu-id="db9ec-122">La condición de selección debe especificar un nombre de una propiedad mínimos o una secuencia de comandos, pero no puede especificar ambos.</span><span class="sxs-lookup"><span data-stu-id="db9ec-122">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="db9ec-123">Para obtener más información acerca de cómo se pueden utilizar condiciones de selección, consulte [definir condiciones para mostrar datos](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="db9ec-123">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="db9ec-124">Véase también</span><span class="sxs-lookup"><span data-stu-id="db9ec-124">See Also</span></span>

[<span data-ttu-id="db9ec-125">Elemento SelectionCondition para EntrySelectedBy para el control personalizado para la vista (formato)</span><span class="sxs-lookup"><span data-stu-id="db9ec-125">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="db9ec-126">Escribir un archivo de formato de PowerShell</span><span class="sxs-lookup"><span data-stu-id="db9ec-126">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)