---
title: Elemento CustomEntry para CustomEntries para el control personalizado para la vista (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac3c0a25-f2ca-4e28-b3dc-9cb06a76d92a
caps.latest.revision: 11
ms.openlocfilehash: 7804155bffeb1f0df8339f797bf59f8def56a3fc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861821"
---
# <a name="customentry-element-for-customentries-for-customcontrol-for-view-format"></a><span data-ttu-id="816ee-102">Elemento CustomEntry para CustomEntries for CustomControl for View (formato)</span><span class="sxs-lookup"><span data-stu-id="816ee-102">CustomEntry Element for CustomEntries for CustomControl for View (Format)</span></span>

<span data-ttu-id="816ee-103">Proporciona una definición de la vista de control personalizado.</span><span class="sxs-lookup"><span data-stu-id="816ee-103">Provides a definition of the custom control view.</span></span>

<span data-ttu-id="816ee-104">Elemento (formato) elemento ViewDefinitions (formato) vista elemento (formato) el elemento de control personalizado (formato) CustomEntries elemento de configuración control personalizado de vista (formato) del elemento CustomEntry para CustomEntries para vista (formato)</span><span class="sxs-lookup"><span data-stu-id="816ee-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="816ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="816ee-105">Syntax</span></span>

```xml
<CustomEntry>
  <EntrySelectedBy>...</EntrySelectedBy>
  <CustomItem>...</CustomItem>
</CustomEntry>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="816ee-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="816ee-106">Attributes and Elements</span></span>

<span data-ttu-id="816ee-107">Las secciones siguientes describen los atributos, elementos secundarios y el elemento primario de la `CustomEntry` elemento.</span><span class="sxs-lookup"><span data-stu-id="816ee-107">The following sections describe attributes, child elements, and the parent element of the `CustomEntry` element.</span></span> <span data-ttu-id="816ee-108">Debe especificar los elementos mostrados por la definición.</span><span class="sxs-lookup"><span data-stu-id="816ee-108">You must specify the items displayed by the definition.</span></span>

### <a name="attributes"></a><span data-ttu-id="816ee-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="816ee-109">Attributes</span></span>

<span data-ttu-id="816ee-110">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="816ee-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="816ee-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="816ee-111">Child Elements</span></span>

|<span data-ttu-id="816ee-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="816ee-112">Element</span></span>|<span data-ttu-id="816ee-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="816ee-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="816ee-114">Elemento EntrySelectedBy para CustomEntry para vista (formato)</span><span class="sxs-lookup"><span data-stu-id="816ee-114">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="816ee-115">Elemento opcional.</span><span class="sxs-lookup"><span data-stu-id="816ee-115">Optional element.</span></span><br /><br /> <span data-ttu-id="816ee-116">Define los tipos de .NET que usan la definición de la vista de control personalizado o la condición que debe existir para que esta definición para usarse.</span><span class="sxs-lookup"><span data-stu-id="816ee-116">Defines the .NET types that use the definition of the custom control view or the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="816ee-117">Elemento CustomItem para CustomEntry para vista (formato)</span><span class="sxs-lookup"><span data-stu-id="816ee-117">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="816ee-118">Define un control para la definición de un control personalizado.</span><span class="sxs-lookup"><span data-stu-id="816ee-118">Defines a control for the custom control definition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="816ee-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="816ee-119">Parent Elements</span></span>

|<span data-ttu-id="816ee-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="816ee-120">Element</span></span>|<span data-ttu-id="816ee-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="816ee-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="816ee-122">Elemento CustomEntries para el control personalizado para la vista (formato)</span><span class="sxs-lookup"><span data-stu-id="816ee-122">CustomEntries Element for CustomControl for View (Format)</span></span>](./customentries-element-for-customcontrol-for-view-format.md)|<span data-ttu-id="816ee-123">Proporciona las definiciones de la vista de control personalizado.</span><span class="sxs-lookup"><span data-stu-id="816ee-123">Provides the definitions of the custom control view.</span></span> <span data-ttu-id="816ee-124">La vista de control personalizado debe especificar una o varias definiciones.</span><span class="sxs-lookup"><span data-stu-id="816ee-124">The custom control view must specify one or more definitions.</span></span>|

## <a name="remarks"></a><span data-ttu-id="816ee-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="816ee-125">Remarks</span></span>

<span data-ttu-id="816ee-126">En la mayoría de los casos, solo una definición es necesaria para cada vista de control personalizado, pero es posible tener varias definiciones si desea usar la misma vista para mostrar diferentes objetos. NET.</span><span class="sxs-lookup"><span data-stu-id="816ee-126">In most cases, only one definition is required for each custom control view, but it is possible to have multiple definitions if you want to use the same view to display different .NET objects.</span></span> <span data-ttu-id="816ee-127">En esos casos, puede proporcionar una definición independiente para cada objeto o conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="816ee-127">In those cases, you can provide a separate definition for each object or set of objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="816ee-128">Véase también</span><span class="sxs-lookup"><span data-stu-id="816ee-128">See Also</span></span>

[<span data-ttu-id="816ee-129">Elemento de control personalizado para la vista (formato)</span><span class="sxs-lookup"><span data-stu-id="816ee-129">CustomControl Element for View (Format)</span></span>](./customcontrol-element-for-view-format.md)

[<span data-ttu-id="816ee-130">Elemento CustomItem para CustomEntry para vista (formato)</span><span class="sxs-lookup"><span data-stu-id="816ee-130">CustomItem Element for CustomEntry for View (Format)</span></span>](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="816ee-131">Elemento EntrySelectedBy para CustomEntry para vista (formato)</span><span class="sxs-lookup"><span data-stu-id="816ee-131">EntrySelectedBy Element for CustomEntry for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="816ee-132">Escribir un archivo de formato de PowerShell</span><span class="sxs-lookup"><span data-stu-id="816ee-132">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)