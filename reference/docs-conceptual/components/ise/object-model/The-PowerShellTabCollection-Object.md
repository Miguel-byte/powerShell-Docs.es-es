---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: El objeto PowerShellTabCollection
ms.assetid: 81f4bf4a-83bf-415e-8378-1703792fbb58
ms.openlocfilehash: d9088b26de35360b8258d3f15924b3010a986d15
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403153"
---
# <a name="the-powershelltabcollection-object"></a><span data-ttu-id="8c976-103">El objeto PowerShellTabCollection</span><span class="sxs-lookup"><span data-stu-id="8c976-103">The PowerShellTabCollection Object</span></span>

<span data-ttu-id="8c976-104">El objeto de colección **PowerShellTab** es una colección de objetos **PowerShellTab**.</span><span class="sxs-lookup"><span data-stu-id="8c976-104">The **PowerShellTab** collection object is a collection of **PowerShellTab** objects.</span></span> <span data-ttu-id="8c976-105">Cada objeto **PowerShellTab** funciona como un entorno de runtime independiente.</span><span class="sxs-lookup"><span data-stu-id="8c976-105">Each **PowerShellTab** object functions as a separate runtime environment.</span></span> <span data-ttu-id="8c976-106">Es una instancia de la clase Microsoft.PowerShell.Host.ISE.PowerShellTabs.</span><span class="sxs-lookup"><span data-stu-id="8c976-106">It is an instance of Microsoft.PowerShell.Host.ISE.PowerShellTabs class.</span></span> <span data-ttu-id="8c976-107">Un ejemplo es el objeto **$psISE.PowerShellTabs**.</span><span class="sxs-lookup"><span data-stu-id="8c976-107">An example is the **$psISE.PowerShellTabs** object.</span></span>

## <a name="methods"></a><span data-ttu-id="8c976-108">Métodos</span><span class="sxs-lookup"><span data-stu-id="8c976-108">Methods</span></span>

### <a name="add"></a><span data-ttu-id="8c976-109">Add\(\)</span><span class="sxs-lookup"><span data-stu-id="8c976-109">Add\(\)</span></span>

<span data-ttu-id="8c976-110">Se admite en Windows PowerShell ISE 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8c976-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="8c976-111">Agrega una nueva pestaña de PowerShell a la colección.</span><span class="sxs-lookup"><span data-stu-id="8c976-111">Adds a new PowerShell tab to the collection.</span></span> <span data-ttu-id="8c976-112">Devuelve la pestaña recién agregada.</span><span class="sxs-lookup"><span data-stu-id="8c976-112">It returns the newly added tab.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="8c976-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="8c976-113">Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="8c976-114">Se admite en Windows PowerShell ISE 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8c976-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="8c976-115">Quita la pestaña especificada por el parámetro **psTab**.</span><span class="sxs-lookup"><span data-stu-id="8c976-115">Removes the tab that is specified by the **psTab** parameter.</span></span>

<span data-ttu-id="8c976-116">**psTab** Pestaña de PowerShell que se quitará.</span><span class="sxs-lookup"><span data-stu-id="8c976-116">**psTab** The PowerShell tab to remove.</span></span>

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a><span data-ttu-id="8c976-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span><span class="sxs-lookup"><span data-stu-id="8c976-117">SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)</span></span>

<span data-ttu-id="8c976-118">Se admite en Windows PowerShell ISE 2.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="8c976-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="8c976-119">Selecciona la pestaña de PowerShell especificada por el parámetro **psTab** para que sea la pestaña activa de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c976-119">Selects the PowerShell tab that is specified by the **psTab** parameter to make it the currently active PowerShell tab.</span></span>

<span data-ttu-id="8c976-120">**psTab** Pestaña de PowerShell que se seleccionará.</span><span class="sxs-lookup"><span data-stu-id="8c976-120">**psTab** The PowerShell tab to select.</span></span>

```powershell
# Save the current tab in a variable and rename it
$oldTab = $psISE.CurrentPowerShellTab
$psISE.CurrentPowerShellTab.DisplayName = 'Old Tab'
# Create a new tab and give it a new display name
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
# Switch back to the original tab
$psISE.PowerShellTabs.SelectedPowerShellTab = $oldTab
```

## <a name="see-also"></a><span data-ttu-id="8c976-121">Véase también</span><span class="sxs-lookup"><span data-stu-id="8c976-121">See Also</span></span>

- [<span data-ttu-id="8c976-122">El objeto PowerShellTab</span><span class="sxs-lookup"><span data-stu-id="8c976-122">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="8c976-123">Finalidad del modelo de objetos de scripting de Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="8c976-123">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="8c976-124">La jerarquía del modelo de objetos de ISE</span><span class="sxs-lookup"><span data-stu-id="8c976-124">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)