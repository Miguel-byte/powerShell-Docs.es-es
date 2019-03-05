---
title: Archivos de formato de PowerShell de Windows | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d4c8f84-ebd2-4405-bb10-cfc5400d4ad6
caps.latest.revision: 6
ms.openlocfilehash: 35efd36fd70c209e3cbeb9eff0ddf978615fffd6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854271"
---
# <a name="windows-powershell-formatting-files"></a><span data-ttu-id="780f5-102">Archivos de formato de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="780f5-102">Windows PowerShell Formatting Files</span></span>

<span data-ttu-id="780f5-103">Windows PowerShell proporciona varios archivos de formato (. format.ps1xml) que se encuentran en el directorio de instalación (`$pshome`).</span><span class="sxs-lookup"><span data-stu-id="780f5-103">Windows PowerShell provides several formatting files (.format.ps1xml) that are located in the installation directory (`$pshome`).</span></span> <span data-ttu-id="780f5-104">Cada uno de estos archivos define la visualización predeterminada para un conjunto específico de objetos. NET.</span><span class="sxs-lookup"><span data-stu-id="780f5-104">Each of these files defines the default display for a specific set of .NET objects.</span></span> <span data-ttu-id="780f5-105">Estos archivos no deben modificarse nunca.</span><span class="sxs-lookup"><span data-stu-id="780f5-105">These files should never be changed.</span></span> <span data-ttu-id="780f5-106">Sin embargo, puede usar ellos como referencia para crear sus propios archivos de formato personalizados.</span><span class="sxs-lookup"><span data-stu-id="780f5-106">However, you can use them as a reference for creating your own custom formatting files.</span></span>

<span data-ttu-id="780f5-107">Certificate.Format.ps1xml define la visualización de objetos en el almacén de certificados como los certificados x.509 y almacenes de certificados.</span><span class="sxs-lookup"><span data-stu-id="780f5-107">Certificate.Format.ps1xml Defines the display of objects in the Certificate store such as x.509 certificates and certificate stores.</span></span>

<span data-ttu-id="780f5-108">DotNetTypes.Format.ps1xml define la presentación de varios objetos. NET, como los objetos CultureInfo, FileVersionInfo y EventLogEntry.</span><span class="sxs-lookup"><span data-stu-id="780f5-108">DotNetTypes.Format.ps1xml Defines the display of miscellaneous .NET objects such as CultureInfo, FileVersionInfo, and EventLogEntry objects.</span></span>

<span data-ttu-id="780f5-109">FileSystem.Format.ps1xml define la presentación de los objetos de sistema de archivos como archivos y directorios de los objetos.</span><span class="sxs-lookup"><span data-stu-id="780f5-109">FileSystem.Format.ps1xml Defines the display of file system objects such as file and directory objects.</span></span>

<span data-ttu-id="780f5-110">Define Help.Format.ps1xml las distintas vistas utilizadas por el [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet, como las vistas detalladas, ejemplo, parámetros y completo.</span><span class="sxs-lookup"><span data-stu-id="780f5-110">Help.Format.ps1xml Defines the different views used by the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet, such as the detailed, full, parameters, and example views.</span></span>
<span data-ttu-id="780f5-111">Define las distintas vistas que usa el [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet, como las vistas detalladas, ejemplo, parámetros y completo.</span><span class="sxs-lookup"><span data-stu-id="780f5-111">Defines the different views used by the [Get-Help](/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet, such as the detailed, full, parameters, and example views.</span></span>

<span data-ttu-id="780f5-112">PowerShellCore.Format.ps1xml define la presentación de los objetos generados por los cmdlets principales de Windows PowerShell, como los objetos devueltos por la [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) y [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) cmdlets.</span><span class="sxs-lookup"><span data-stu-id="780f5-112">PowerShellCore.Format.ps1xml Defines the display of the objects generated by Windows PowerShell core cmdlets, such as the objects returned by the [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) and [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) cmdlets.</span></span>
<span data-ttu-id="780f5-113">Define la presentación de los objetos generados por los cmdlets principales de Windows PowerShell, como los objetos devueltos por la [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) y [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) cmdlets.</span><span class="sxs-lookup"><span data-stu-id="780f5-113">Defines the display of the objects generated by Windows PowerShell core cmdlets, such as the objects returned by the [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) and [Get-History](/powershell/module/Microsoft.PowerShell.Core/Get-History) cmdlets.</span></span>

<span data-ttu-id="780f5-114">PowerShellTrace.Format.ps1xml define la visualización de objetos de seguimiento, como las generadas por el [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="780f5-114">PowerShellTrace.Format.ps1xml Defines the display of trace objects such as those generated by the [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) cmdlet.</span></span>
<span data-ttu-id="780f5-115">Define la visualización de objetos de seguimiento, como las generadas por el [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) cmdlet.</span><span class="sxs-lookup"><span data-stu-id="780f5-115">Defines the display of trace objects such as those generated by the [Trace-Command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command) cmdlet.</span></span>

<span data-ttu-id="780f5-116">Registry.Format.ps1xml define la presentación de los objetos del registro como entradas y claves.</span><span class="sxs-lookup"><span data-stu-id="780f5-116">Registry.Format.ps1xml Defines the display of registry objects such as key and entry objects.</span></span>

## <a name="see-also"></a><span data-ttu-id="780f5-117">Véase también</span><span class="sxs-lookup"><span data-stu-id="780f5-117">See Also</span></span>

[<span data-ttu-id="780f5-118">Escribir un cmdlet de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="780f5-118">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/writing-a-windows-powershell-cmdlet.md)