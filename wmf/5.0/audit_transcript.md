---
ms.date: 06/12/2017
keywords: wmf,powershell,setup
ms.openlocfilehash: f655cd7aa9b14bd38924d55c8f1246b55ef83756
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085864"
---
# <a name="enhanced-transcription-options"></a><span data-ttu-id="325b4-102">Opciones de transcripción mejoradas</span><span class="sxs-lookup"><span data-stu-id="325b4-102">Enhanced Transcription Options</span></span>

<span data-ttu-id="325b4-103">La transcripción de Windows PowerShell se mejoró para aplicarse a todas las aplicaciones de hospedaje (como Windows PowerShell ISE) en lugar de solo al host de consola (powershell.exe).</span><span class="sxs-lookup"><span data-stu-id="325b4-103">Windows PowerShell transcription has been improved to apply to all hosting applications (such as Windows PowerShell ISE) rather than just the console host (powershell.exe).</span></span>

<span data-ttu-id="325b4-104">Además de extenderse para la transcripción, la propia funcionalidad de transcripción se actualizó para admitir el anidamiento arbitrario de transcripciones, los metadatos adicionales en el encabezado de transcripción resultante y la configuración de un directorio de salida de transcripción (para admitir la recopilación de registro centralizada).</span><span class="sxs-lookup"><span data-stu-id="325b4-104">In addition to extending for transcripting, the transcripting functionality itself has been updated to support arbitrary nesting of transcripts, additional metadata in the resulting transcript header, and setting a transcription output directory (to support centralized log collection).</span></span>

<span data-ttu-id="325b4-105">Las opciones de transcripción (incluida la habilitación de una transcripción de todo el sistema) pueden configurarse con la opción de Directiva de grupo **Activar la transcripción de PowerShell** (en Plantillas administrativas -> Componentes de Windows -> Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="325b4-105">Transcription options (including enabling a system-wide transcript) can be configured with the **Turn on PowerShell Transcription** Group Policy setting (in Administrative Templates -> Windows Components -> Windows PowerShell).</span></span>
