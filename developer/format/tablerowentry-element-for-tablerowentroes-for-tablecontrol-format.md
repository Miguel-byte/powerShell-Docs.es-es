---
title: Elemento TableRowEntry para TableRowEntroes para TableControl (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18d86af7-7ff9-4968-81be-2caa61937d49
caps.latest.revision: 10
ms.openlocfilehash: 001d46debde61f928c338b2f68112fb201f96216
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853591"
---
# <a name="tablerowentry-element-for-tablerowentroes-for-tablecontrol-format"></a><span data-ttu-id="15f47-102">Elemento TableRowEntry para TableRowEntries for TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-102">TableRowEntry Element for TableRowEntroes for TableControl (Format)</span></span>

<span data-ttu-id="15f47-103">Define los datos que se muestran en una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="15f47-103">Defines the data that is displayed in a row of the table.</span></span>

<span data-ttu-id="15f47-104">Elemento (formato) elemento ViewDefinitions (formato) vista elemento (formato) elemento TableControl (formato) TableRowEntries elemento de configuración (elemento) TableRowEntry TableControl (formato) para TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element for TableControl (Format) TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="15f47-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15f47-105">Syntax</span></span>

```xml
<TableRowEntry>
  <Wrap/>
  <EntrySelectedBy>...</EntrySelectedBy>
  <TableColumnItems>...</TableColumnItems>
</TableRowEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="15f47-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="15f47-106">Attributes and Elements</span></span>

<span data-ttu-id="15f47-107">Las secciones siguientes describen los atributos, elementos secundarios y elemento primario de la `TableRowEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="15f47-107">The following sections describe attributes, child elements, and parent element of the `TableRowEntry` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="15f47-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="15f47-108">Attributes</span></span>

<span data-ttu-id="15f47-109">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="15f47-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="15f47-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="15f47-110">Child Elements</span></span>

|<span data-ttu-id="15f47-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="15f47-111">Element</span></span>|<span data-ttu-id="15f47-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="15f47-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15f47-113">Elemento EntrySelectedBy para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-113">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="15f47-114">Elemento necesario.</span><span class="sxs-lookup"><span data-stu-id="15f47-114">Required element.</span></span><br /><br /> <span data-ttu-id="15f47-115">Define los objetos cuyos valores de propiedad se muestran en la fila.</span><span class="sxs-lookup"><span data-stu-id="15f47-115">Defines the objects whose property values are displayed in the row.</span></span>|
|[<span data-ttu-id="15f47-116">Elemento TableColumnItems para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-116">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="15f47-117">Elemento necesario.</span><span class="sxs-lookup"><span data-stu-id="15f47-117">Required element.</span></span><br /><br /> <span data-ttu-id="15f47-118">Define las propiedades o scripts cuyos valores se muestran.</span><span class="sxs-lookup"><span data-stu-id="15f47-118">Defines the properties or scripts whose values are displayed.</span></span>|
|[<span data-ttu-id="15f47-119">Ajuste el elemento para TableRowEntry para TableCntrol (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-119">Wrap Element for TableRowEntry for TableCntrol (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrl-format.md)|<span data-ttu-id="15f47-120">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="15f47-120">Optional element.</span></span><br /><br /> <span data-ttu-id="15f47-121">Especifica que el texto que supera el ancho de columna se muestra en la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="15f47-121">Specifies that text that exceeds the column width is displayed on the next line.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="15f47-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="15f47-122">Parent Elements</span></span>

|<span data-ttu-id="15f47-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="15f47-123">Element</span></span>|<span data-ttu-id="15f47-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="15f47-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="15f47-125">Elemento TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-125">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)|<span data-ttu-id="15f47-126">Define las filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="15f47-126">Defines the rows of the table.</span></span>|

## <a name="remarks"></a><span data-ttu-id="15f47-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15f47-127">Remarks</span></span>

<span data-ttu-id="15f47-128">Una `TableColumnItems` y un elemento `EntrySelectedBy` debe especificarse el elemento.</span><span class="sxs-lookup"><span data-stu-id="15f47-128">One `TableColumnItems` element and one `EntrySelectedBy` element must be specified.</span></span>

<span data-ttu-id="15f47-129">Para obtener más información acerca de los componentes de una vista de tabla, vea [crear una vista de tabla](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="15f47-129">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="15f47-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15f47-130">Example</span></span>

<span data-ttu-id="15f47-131">El ejemplo siguiente se muestra un `TableRowEntry` elemento que define una fila que muestra los valores de las dos propiedades de la [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objeto.</span><span class="sxs-lookup"><span data-stu-id="15f47-131">The following example shows a `TableRowEntry` element that defines a row that displays the values of two properties of the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) object.</span></span>

```xml
<TableRowEntry>
  <EntrySelectedBy>
    <TypeName>System.Diagnostics.Process</TypeName>
  </EntrySelectedBy>
  <TableColumnItems>
    <TableColumnItem>
      <PropertyName> Property for first column</PropertyName>
    </TableColumnItem>
    <TableColumnItem>
      <PropertyName> Property for second column</PropertyName>
    </TableColumnItem>
  </TableColumnItems>
</TableRowEntry>
```

## <a name="see-also"></a><span data-ttu-id="15f47-132">Véase también</span><span class="sxs-lookup"><span data-stu-id="15f47-132">See Also</span></span>

[<span data-ttu-id="15f47-133">Creación de una vista de tabla</span><span class="sxs-lookup"><span data-stu-id="15f47-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="15f47-134">Elemento EntrySelectedBy para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-134">EntrySelectedBy Element for TableRowEntry for TableControl (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="15f47-135">Elemento TableColumnItems para TableRowEntry para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-135">TableColumnItems Element for TableRowEntry for TableControl (Format)</span></span>](./tablecolumnitems-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="15f47-136">Elemento TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-136">TableRowEntries Element for TableControl (Format)</span></span>](./tablerowentries-element-for-tablecontrol-format.md)

[<span data-ttu-id="15f47-137">Elemento TableRowEntry para TableRowEntries para TableControl (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-137">TableRowEntry Element for TableRowEntries for TableControl (Format)</span></span>](./tablerowentry-element-for-tablerowentroes-for-tablecontrol-format.md)

[<span data-ttu-id="15f47-138">Ajuste el elemento para TableRowEntry para TableCntrol (formato)</span><span class="sxs-lookup"><span data-stu-id="15f47-138">Wrap Element for TableRowEntry for TableCntrol (Format)</span></span>](./wrap-element-for-tablerowentry-for-tablecontrl-format.md)

[<span data-ttu-id="15f47-139">Escribir un archivo de formato de PowerShell</span><span class="sxs-lookup"><span data-stu-id="15f47-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)