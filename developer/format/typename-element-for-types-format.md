---
title: Elemento TypeName para tipos (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0595b99e-b438-4240-b47b-555cf0316f33
caps.latest.revision: 15
ms.openlocfilehash: 4f463ac6b70a00f628c5b93b112c5fa510ff3bfb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853581"
---
# <a name="typename-element-for-types-format"></a><span data-ttu-id="acd47-102">Elemento TypeName para Types (formato)</span><span class="sxs-lookup"><span data-stu-id="acd47-102">TypeName Element for Types (Format)</span></span>

<span data-ttu-id="acd47-103">Especifica el tipo de .NET de un objeto que pertenece al conjunto de selección.</span><span class="sxs-lookup"><span data-stu-id="acd47-103">Specifies the .NET type of an object that belongs to the selection set.</span></span>

<span data-ttu-id="acd47-104">Tipos de elemento SelectionSets (formato) SelectionSet elemento (formato) de configuración (formato) del elemento elemento TypeName de elemento (formato) de tipos (formato)</span><span class="sxs-lookup"><span data-stu-id="acd47-104">Configuration Element (Format) SelectionSets Element (Format) SelectionSet Element (Format) Types Element (Format) TypeName Element of Types (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="acd47-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acd47-105">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</Name>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="acd47-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="acd47-106">Attributes and Elements</span></span>

<span data-ttu-id="acd47-107">Las secciones siguientes describen los atributos, elementos secundarios y el elemento primario de la `TypeName` elemento.</span><span class="sxs-lookup"><span data-stu-id="acd47-107">The following sections describe the attributes, child elements, and the parent element of the `TypeName` element.</span></span> <span data-ttu-id="acd47-108">Al menos un `TypeName` elemento debe incluirse en el conjunto de selección.</span><span class="sxs-lookup"><span data-stu-id="acd47-108">At least one `TypeName` element must be included in the selection set.</span></span>

### <a name="attributes"></a><span data-ttu-id="acd47-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="acd47-109">Attributes</span></span>

<span data-ttu-id="acd47-110">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="acd47-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="acd47-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="acd47-111">Child Elements</span></span>

<span data-ttu-id="acd47-112">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="acd47-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="acd47-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="acd47-113">Parent Elements</span></span>

|<span data-ttu-id="acd47-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="acd47-114">Element</span></span>|<span data-ttu-id="acd47-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="acd47-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="acd47-116">Tipos de elemento (formato)</span><span class="sxs-lookup"><span data-stu-id="acd47-116">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)|<span data-ttu-id="acd47-117">Define los objetos de .NET que están en la selección de conjunto.</span><span class="sxs-lookup"><span data-stu-id="acd47-117">Defines the .NET objects that are in the selection set.</span></span>|

## <a name="text-value"></a><span data-ttu-id="acd47-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="acd47-118">Text Value</span></span>

<span data-ttu-id="acd47-119">Especifique el nombre completo del tipo. NET.</span><span class="sxs-lookup"><span data-stu-id="acd47-119">Specify the fully qualified name for the .NET type.</span></span>

## <a name="remarks"></a><span data-ttu-id="acd47-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="acd47-120">Remarks</span></span>

<span data-ttu-id="acd47-121">Puede usar conjuntos de selección cuando tenga un conjunto de objetos relacionados que desea hacer referencia mediante un nombre único, como un conjunto de objetos que están relacionadas mediante herencia.</span><span class="sxs-lookup"><span data-stu-id="acd47-121">You can use selection sets when you have a set of related objects that you want to reference by using a single name, such as a set of objects that are related through inheritance.</span></span> <span data-ttu-id="acd47-122">Al definir las vistas, puede especificar el conjunto de objetos con el nombre de la selección de conjunto en lugar de enumerar todos los objetos dentro de cada vista.</span><span class="sxs-lookup"><span data-stu-id="acd47-122">When defining your views, you can specify the set of objects by using the name of the selection set instead of listing all the objects within each view.</span></span>

<span data-ttu-id="acd47-123">Al definir las vistas del archivo de formato, se especifican conjuntos comunes de selección por su nombre.</span><span class="sxs-lookup"><span data-stu-id="acd47-123">Common selection sets are specified by their name when defining the views of the formatting file.</span></span> <span data-ttu-id="acd47-124">En estos casos, el `SelectionSetName` elemento secundario de la `ViewSelectedBy` (elemento) para la vista especifica el conjunto.</span><span class="sxs-lookup"><span data-stu-id="acd47-124">In these cases, the `SelectionSetName` child element of the `ViewSelectedBy` element for the view specifies the set.</span></span> <span data-ttu-id="acd47-125">Sin embargo, las entradas diferentes de una vista también pueden especificar un conjunto de selección que se aplica solo a esa entrada de la vista.</span><span class="sxs-lookup"><span data-stu-id="acd47-125">However, different entries of a view can also specify a selection set that applies to only that entry of the view.</span></span> <span data-ttu-id="acd47-126">Para obtener más información acerca de los conjuntos de selección, consulte [definir se establece los objetos](./defining-selection-sets.md).</span><span class="sxs-lookup"><span data-stu-id="acd47-126">For more information about selection sets, see [Defining Sets of Objects](./defining-selection-sets.md).</span></span>

## <a name="example"></a><span data-ttu-id="acd47-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="acd47-127">Example</span></span>

<span data-ttu-id="acd47-128">El ejemplo siguiente se muestra un `SelectionSet` elemento que define cuatro tipos. NET.</span><span class="sxs-lookup"><span data-stu-id="acd47-128">The following example shows a `SelectionSet` element that defines four .NET types.</span></span>

```
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a><span data-ttu-id="acd47-129">Véase también</span><span class="sxs-lookup"><span data-stu-id="acd47-129">See Also</span></span>

[<span data-ttu-id="acd47-130">Definir conjuntos de selección</span><span class="sxs-lookup"><span data-stu-id="acd47-130">Defining Selection Sets</span></span>](./defining-selection-sets.md)

[<span data-ttu-id="acd47-131">Elemento SelectionSet (formato)</span><span class="sxs-lookup"><span data-stu-id="acd47-131">SelectionSet Element (Format)</span></span>](./selectionset-element-format.md)

[<span data-ttu-id="acd47-132">Elemento SelectionSets (formato)</span><span class="sxs-lookup"><span data-stu-id="acd47-132">SelectionSets Element (Format)</span></span>](./selectionsets-element-format.md)

[<span data-ttu-id="acd47-133">Tipos de elemento (formato)</span><span class="sxs-lookup"><span data-stu-id="acd47-133">Types Element (Format)</span></span>](./types-element-for-selectionset-format.md)

[<span data-ttu-id="acd47-134">Escribir un conjunto de PowDefining de Windows de ObjecterShell archivo de formato</span><span class="sxs-lookup"><span data-stu-id="acd47-134">Writing a Windows PowDefining Sets of ObjecterShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)