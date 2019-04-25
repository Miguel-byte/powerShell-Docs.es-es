---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Recurso nxGroup de DSC para Linux
ms.openlocfilehash: c61b6ab4a8c56d085b5297dcfc7582187d54f946
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077870"
---
# <a name="dsc-for-linux-nxgroup-resource"></a>Recurso nxGroup de DSC para Linux

El recurso **nxGroup** de la configuración de estado deseado (DSC) de PowerShell ofrece un mecanismo para administrar grupos locales en un nodo de Linux.

## <a name="syntax"></a>Sintaxis

```
nxGroup <string> #ResourceName
{
    GroupName = <string>
    [ Ensure = <string> { Absent | Present } ]
    [ Members = <string[]> ]
    [ MembersToInclude = <string[]> ]
    [ MembersToExclude = <string[]> ]
    [ DependsOn = <string[]> ]
}
```

## <a name="properties"></a>Propiedades

|  Propiedad |  Descripción |
|---|---|
| NombreDeGrupo| Especifica el nombre del grupo para el que quiere garantizar un estado específico.|
| Ensure| Determina si se debe comprobar si existe el grupo. Establezca esta propiedad en "Present" para asegurarse de que el grupo exista. Establézcala en "Absent" para asegurarse de que el grupo no exista. El valor predeterminado es "Present".|
| Miembros| Especifica a los miembros que forman el grupo.|
| MembersToInclude| Especifica los usuarios que quiera garantizar que sean miembros del grupo.|
| MembersToExclude| Especifica los usuarios que quiera garantizar que no sean miembros del grupo.|
| PreferredGroupID| Establece el identificador de grupo en el valor proporcionado, si es posible. Si el identificador de grupo está actualmente en uso, se utiliza el siguiente identificador de grupo disponible.|
| DependsOn | Indica que la configuración de otro recurso debe ejecutarse antes de que se configure este recurso. Por ejemplo, si el elemento **ID** del bloque del script de configuración del recurso que quiere ejecutar primero es **ResourceName** y su tipo es **ResourceType**, la sintaxis para usar esta propiedad es `DependsOn = '[ResourceType]ResourceName'`.|

## <a name="example"></a>Ejemplo

El ejemplo siguiente se asegura de que el usuario "monuser" exista y de que sea un miembro del grupo "DBusers".

```powershell
Import-DSCResource -Module nx

Node $node {
    nxUser UserExample {
       UserName = 'monuser'
       Description = 'Monitoring user'
       Password = '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
       Ensure = 'Present'
       HomeDirectory = '/home/monuser'
    }

    nxGroup GroupExample {
       GroupName = 'DBusers'
       Ensure = 'Present'
       MembersToInclude = 'monuser'
       DependsOn = '[nxUser]UserExample'
    }
}
```