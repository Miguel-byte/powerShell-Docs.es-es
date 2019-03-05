---
title: GetProc02 (C#) código de ejemplo | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e4e1eee3-316b-43a4-8a60-313391619be6
caps.latest.revision: 6
ms.openlocfilehash: 740e8d60b71654b82020d16b2964165f3ee1e600
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862311"
---
# <a name="getproc02-c-sample-code"></a><span data-ttu-id="29940-102">Código de ejemplo GetProc02 (C#)</span><span class="sxs-lookup"><span data-stu-id="29940-102">GetProc02 (C#) Sample Code</span></span>

<span data-ttu-id="29940-103">El código siguiente muestra la implementación de un `Get-Process` cmdlet que acepta la entrada de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="29940-103">The following code shows the implementation of a `Get-Process` cmdlet that accepts command-line input.</span></span> <span data-ttu-id="29940-104">Tenga en cuenta que esta implementación define un `Name` parámetro para permitir la entrada de línea de comandos y lo utiliza el [System.Management.Automation.Cmdlet.Writeobject%28System.Object%2Csystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) método como salida mecanismo para enviar el resultado de los objetos a la canalización.</span><span class="sxs-lookup"><span data-stu-id="29940-104">Notice that this implementation defines a `Name` parameter to allow command-line input, and it uses the [System.Management.Automation.Cmdlet.Writeobject%28System.Object%2Csystem.Boolean%29](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject%28System.Object%2CSystem.Boolean%29) method as the output mechanism for sending output objects to the pipeline.</span></span>

## <a name="code-sample"></a><span data-ttu-id="29940-105">Ejemplo de código</span><span class="sxs-lookup"><span data-stu-id="29940-105">Code Sample</span></span>

[!code-csharp[GetProcessSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/GetProcessSample02/GetProcessSample02.cs#L11-L76 "GetProcessSample02.cs")]

## <a name="see-also"></a><span data-ttu-id="29940-106">Véase también</span><span class="sxs-lookup"><span data-stu-id="29940-106">See Also</span></span>

[<span data-ttu-id="29940-107">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="29940-107">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)