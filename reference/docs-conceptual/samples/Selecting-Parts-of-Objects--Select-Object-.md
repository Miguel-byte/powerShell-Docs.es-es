---
ms.date: 06/05/2017
keywords: powershell, cmdlet
title: Seleccionar partes de objetos Select Object
ms.assetid: 72e64b1a-d351-4500-9da3-24d8a71d7a92
ms.openlocfilehash: 323c57ba4462e20d9713fb74732989584f5a993f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057907"
---
# <a name="selecting-parts-of-objects-select-object"></a><span data-ttu-id="f4c58-103">Seleccionar partes de objetos (Select-Object)</span><span class="sxs-lookup"><span data-stu-id="f4c58-103">Selecting Parts of Objects (Select-Object)</span></span>

<span data-ttu-id="f4c58-104">Puede usar el cmdlet **Select-Object** para crear nuevos objetos de Windows PowerShell personalizados que contengan las propiedades seleccionadas de los objetos que use para crearlos.</span><span class="sxs-lookup"><span data-stu-id="f4c58-104">You can use the **Select-Object** cmdlet to create new, custom Windows PowerShell objects that contain properties selected from the objects you use to create them.</span></span> <span data-ttu-id="f4c58-105">Escriba el siguiente comando para crear un nuevo objeto que incluya solamente las propiedades Name y FreeSpace de la clase WMI Win32_LogicalDisk:</span><span class="sxs-lookup"><span data-stu-id="f4c58-105">Type the following command to create a new object that includes only the Name and FreeSpace properties of the Win32_LogicalDisk WMI class:</span></span>

```
PS> Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace

Name                                    FreeSpace
----                                    ---------
C:                                      50664845312
```

<span data-ttu-id="f4c58-106">No puede ver el tipo de datos después de emitir este comando, pero si canaliza la salida para Get-Member después de Select-Object, puede indicar que tiene un nuevo tipo de objeto, PSCustomObject:</span><span class="sxs-lookup"><span data-stu-id="f4c58-106">You cannot see the type of data after issuing that command, but if you pipe the result to Get-Member after the Select-Object, you can tell that you have a new type of object, a PSCustomObject:</span></span>

```
PS> Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace| Get-Member

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       System.Boolean Equals(Object obj)
GetHashCode Method       System.Int32 GetHashCode()
GetType     Method       System.Type GetType()
ToString    Method       System.String ToString()
FreeSpace   NoteProperty  FreeSpace=...
Name        NoteProperty System.String Name=C:
```

<span data-ttu-id="f4c58-107">Select-Object tiene muchos usos.</span><span class="sxs-lookup"><span data-stu-id="f4c58-107">Select-Object has many uses.</span></span> <span data-ttu-id="f4c58-108">Uno de ellos es replicar datos que se puedan modificar posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f4c58-108">One of them is replicating data that you can then modify.</span></span> <span data-ttu-id="f4c58-109">Ahora podemos gestionar el problema detectado a través de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="f4c58-109">We can now handle the problem we ran across in the previous section.</span></span> <span data-ttu-id="f4c58-110">Podemos actualizar el valor de FreeSpace en nuestros objetos recién creados y la salida incluirá la etiqueta descriptiva:</span><span class="sxs-lookup"><span data-stu-id="f4c58-110">We can update the value of FreeSpace in our newly-created objects and the output will include the descriptive label:</span></span>

```
Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace | ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1024.0/1024.0; $_}
Name                                                                  FreeSpace
----                                                                  ---------
C:                                                                48317.7265625
```