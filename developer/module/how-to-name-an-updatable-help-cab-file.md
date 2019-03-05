---
title: Cómo denominar un archivo .cab de ayuda actualizable | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: de302da0-c17a-4d31-a8ef-14a626738993
caps.latest.revision: 7
ms.openlocfilehash: 23303489372cfe7e036fdea842ae75f7e47503c8
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861291"
---
# <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="c94f5-102">Cómo asignar un nombre a un archivo CAB de Ayuda actualizable</span><span class="sxs-lookup"><span data-stu-id="c94f5-102">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="c94f5-103">En este tema se explica el formato de nombre requerido para el gabinete de ayuda actualizable (. Archivos CAB).</span><span class="sxs-lookup"><span data-stu-id="c94f5-103">This topic explains the required name format for the Updatable Help cabinet (.CAB) files.</span></span>

## <a name="how-to-name-an-updatable-help-cab-file"></a><span data-ttu-id="c94f5-104">Cómo asignar un nombre a un archivo CAB de Ayuda actualizable</span><span class="sxs-lookup"><span data-stu-id="c94f5-104">How to Name an Updatable Help CAB File</span></span>

<span data-ttu-id="c94f5-105">Un archivador actualizable (. Archivo .cab) debe tener un nombre con el formato siguiente.</span><span class="sxs-lookup"><span data-stu-id="c94f5-105">A Updatable cabinet (.CAB) file must have a name with the following format.</span></span>

`<ModuleName>_<ModuleGUID>_<UICulture>_HelpContent.cab`

<span data-ttu-id="c94f5-106">Los elementos del nombre son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="c94f5-106">The elements of the name are as follows.</span></span>

<span data-ttu-id="c94f5-107">ModuleName el valor de la **nombre** propiedad de la **ModuleInfo** objeto al que el [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet devuelve.</span><span class="sxs-lookup"><span data-stu-id="c94f5-107">ModuleName The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>
<span data-ttu-id="c94f5-108">El valor de la **nombre** propiedad de la **ModuleInfo** objeto al que el [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet devuelve.</span><span class="sxs-lookup"><span data-stu-id="c94f5-108">The value of the **Name** property of the **ModuleInfo** object that the [Get-Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module) cmdlet returns.</span></span>

<span data-ttu-id="c94f5-109">ModuleGUID el valor de la **GUID** clave en el manifiesto del módulo.</span><span class="sxs-lookup"><span data-stu-id="c94f5-109">ModuleGUID The value of the **GUID** key in the module manifest.</span></span>

<span data-ttu-id="c94f5-110">Referencia cultural de la interfaz de usuario UICulture de los archivos de ayuda en el archivo CAB.</span><span class="sxs-lookup"><span data-stu-id="c94f5-110">UICulture The UI culture of the help files in the CAB file.</span></span> <span data-ttu-id="c94f5-111">Este valor debe coincidir con el valor de uno de los **UICulture** elementos en el archivo XML HelpInfo para el módulo.</span><span class="sxs-lookup"><span data-stu-id="c94f5-111">This value must match the value of one of the **UICulture** elements in the HelpInfo XML file for the module.</span></span>

<span data-ttu-id="c94f5-112">Por ejemplo, si el nombre del módulo es "TestModule", el GUID del módulo es 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9 y la referencia cultural de interfaz de usuario es "en-US", el nombre del archivo .cab sería:</span><span class="sxs-lookup"><span data-stu-id="c94f5-112">For example, if the module name is "TestModule," the module GUID is 9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9, and the UI culture is "en-US", the name of the CAB file would be:</span></span>

`TestModule_9cabb9ad-f2ac-4914-a46b-bfc1bebf07f9_en-US_HelpContent.cab`