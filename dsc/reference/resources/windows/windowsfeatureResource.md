---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Recurso de DSC WindowsFeature
ms.openlocfilehash: 7a57f4b2797ab3bb202aea8b2543d1e3f14074e9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076708"
---
# <a name="dsc-windowsfeature-resource"></a>Recurso de DSC WindowsFeature

> Se aplica a: Windows PowerShell 4.0, Windows PowerShell 5.0

El recurso **WindowsFeature** de la configuración de estado deseado (DSC) de Windows PowerShell ofrece un mecanismo para asegurarse de que los roles y las características se agreguen o quiten en un nodo de destino.

## <a name="syntax"></a>Sintaxis

```
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Source = [string] ]
}
```

## <a name="properties"></a>Propiedades

|  Propiedad  |  Descripción   |
|---|---|
| Nombre| Indica el nombre del rol o la característica que quiere garantizar que se agregue o se quite. Esto es el mismo que la propiedad __Name__ del cmdlet [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) y no el nombre para mostrar del rol o la característica.|
| Credential| Indica las credenciales que se usarán para agregar o quitar el rol o la característica.|
| Ensure| Indica si se agrega el rol o la característica. Para asegurarse de que el rol o la característica se agregue, establezca esta propiedad en "Present"; para asegurarse de que se quite el rol o característica, establezca la propiedad a "Absent".|
| IncludeAllSubFeature| Establezca esta propiedad en __$true__ para garantizar el estado de todas las subcaracterísticas requeridas con el estado de la característica que se especifique con la propiedad __Name__.|
| LogPath| Indica la ruta de acceso a un archivo de registro donde quiera que el proveedor de recursos registre la operación.|
| DependsOn| Indica que la configuración de otro recurso debe ejecutarse antes de que se configure este recurso. Por ejemplo, si el elemento ID del bloque del script de configuración del recurso que quiere ejecutar primero es __ResourceName__ y su tipo es __ResourceType__, la sintaxis para usar esta propiedad es `DependsOn = "[ResourceType]ResourceName"`.|
| Origen| Indica la ubicación del archivo de origen que se utilizará para la instalación, si es necesario.|

## <a name="example"></a>Ejemplo
```powershell
WindowsFeature RoleExample
{
    Ensure = "Present"
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature
}
```