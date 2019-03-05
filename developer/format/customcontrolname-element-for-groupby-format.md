---
title: Elemento CustomControlName para GroupBy (formato) | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 473d9b56-521b-479a-8010-67fe9f040063
caps.latest.revision: 8
ms.openlocfilehash: 3a386eff95044eae573c255a451c5c8b8f16714d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860311"
---
# <a name="customcontrolname-element-for-groupby-format"></a><span data-ttu-id="b7057-102">Elemento CustomControlName para GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b7057-102">CustomControlName Element for GroupBy (Format)</span></span>

<span data-ttu-id="b7057-103">Especifica el nombre de un control personalizado que se usa para mostrar el grupo nuevo.</span><span class="sxs-lookup"><span data-stu-id="b7057-103">Specifies the name of a custom control that is used to display the new group.</span></span> <span data-ttu-id="b7057-104">Este elemento se usa al definir una tabla, lista, vista de control personalizado o anchos.</span><span class="sxs-lookup"><span data-stu-id="b7057-104">This element is used when defining a table, list, wide or custom control view.</span></span>

<span data-ttu-id="b7057-105">Configuración (formato) elemento ViewDefinitions (formato) vista elemento (formato) GroupBy elemento de vista (formato) del elemento CustomControlName de GroupBy (formato)</span><span class="sxs-lookup"><span data-stu-id="b7057-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControlName Element of GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="b7057-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7057-106">Syntax</span></span>

```xml
<CustomControlName>ControlName</CustomControlName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b7057-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b7057-107">Attributes and Elements</span></span>

<span data-ttu-id="b7057-108">Las secciones siguientes describen los atributos, elementos secundarios y elementos primarios de la `CustomControlName` elemento.</span><span class="sxs-lookup"><span data-stu-id="b7057-108">The following sections describe the attributes, child elements, and parent elements of the `CustomControlName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="b7057-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="b7057-109">Attributes</span></span>

<span data-ttu-id="b7057-110">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="b7057-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="b7057-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b7057-111">Child Elements</span></span>

<span data-ttu-id="b7057-112">Ninguna.</span><span class="sxs-lookup"><span data-stu-id="b7057-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b7057-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b7057-113">Parent Elements</span></span>

|<span data-ttu-id="b7057-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7057-114">Element</span></span>|<span data-ttu-id="b7057-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7057-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b7057-116">Elemento GroupBy para vista (formato)</span><span class="sxs-lookup"><span data-stu-id="b7057-116">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="b7057-117">Define cómo Windows PowerShell muestra un nuevo grupo de objetos.</span><span class="sxs-lookup"><span data-stu-id="b7057-117">Defines how Windows PowerShell displays a new group of objects.</span></span>|

## <a name="text-value"></a><span data-ttu-id="b7057-118">Valor de texto</span><span class="sxs-lookup"><span data-stu-id="b7057-118">Text Value</span></span>

<span data-ttu-id="b7057-119">Especifique el nombre del control personalizado que se usa para mostrar un nuevo grupo.</span><span class="sxs-lookup"><span data-stu-id="b7057-119">Specify the name of the custom control that is used to display a new group.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7057-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b7057-120">Remarks</span></span>

<span data-ttu-id="b7057-121">Puede crear controles comunes que pueden usarse en todas las vistas de un archivo de formato, y puede crear controles de vista que se pueden utilizar una vista específica.</span><span class="sxs-lookup"><span data-stu-id="b7057-121">You can create common controls that can be used by all the views of a formatting file, and you can create view controls that can be used by a specific view.</span></span> <span data-ttu-id="b7057-122">Los siguientes elementos especifican los nombres de estos controles personalizados:</span><span class="sxs-lookup"><span data-stu-id="b7057-122">The following elements specify the names of these custom controls:</span></span>

- [<span data-ttu-id="b7057-123">Elemento Name de Control para los controles de configuración (formato)</span><span class="sxs-lookup"><span data-stu-id="b7057-123">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

- [<span data-ttu-id="b7057-124">Elemento Name de Control para los controles de vista (formato)</span><span class="sxs-lookup"><span data-stu-id="b7057-124">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

## <a name="see-also"></a><span data-ttu-id="b7057-125">Véase también</span><span class="sxs-lookup"><span data-stu-id="b7057-125">See Also</span></span>

[<span data-ttu-id="b7057-126">Elemento GroupBy para vista (formato)</span><span class="sxs-lookup"><span data-stu-id="b7057-126">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="b7057-127">Elemento Name de Control para los controles de configuración (formato)</span><span class="sxs-lookup"><span data-stu-id="b7057-127">Name Element for Control for Controls for Configuration (Format)</span></span>](./name-element-for-control-for-controls-for-configuration-format.md)

[<span data-ttu-id="b7057-128">Elemento Name de Control para los controles de vista (formato)</span><span class="sxs-lookup"><span data-stu-id="b7057-128">Name Element for Control for Controls for View (Format)</span></span>](./name-element-for-control-for-controls-for-view-format.md)

[<span data-ttu-id="b7057-129">Escribir un archivo de formato de PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7057-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)