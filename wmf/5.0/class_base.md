---
ms.date: 06/12/2017
keywords: wmf,powershell,setup
ms.openlocfilehash: 8b3ebd22e03bf9bdd5f26965137a1b1ce9f47c3e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058784"
---
# <a name="declare-base-class"></a><span data-ttu-id="ebe71-102">Declarar una clase base</span><span class="sxs-lookup"><span data-stu-id="ebe71-102">Declare Base Class</span></span>
<span data-ttu-id="ebe71-103">Puede declarar una clase de Windows PowerShell como un tipo base para otra clase de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ebe71-103">You can declare a Windows PowerShell class as a base type for another Windows PowerShell class.</span></span>

```powershell
class bar
{
   [int]foo()
       {
           return 100500
       }
}

class baz : bar {}

[baz]::new().foo() # return 100500
```

<span data-ttu-id="ebe71-104">También puede usar los tipos de .NET Framework existentes como clases base:</span><span class="sxs-lookup"><span data-stu-id="ebe71-104">You can also use existing .NET Framework types as base classes:</span></span>

```powershell
class MyIntList : system.collections.generic.list[int]
{

}

$list = [MyIntList]::new()

$list.Add(100)

$list[0] # return 100
```
