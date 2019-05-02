---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Recurso WindowsOptionalFeatureSet de DSC
ms.openlocfilehash: c27d026e01bbb443a82112e37f1d199fb3482e49
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076980"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a>Recurso WindowsOptionalFeatureSet de DSC

> Se aplica a: Windows PowerShell 5.0

El recurso **WindowsOptionalFeatureSet** de la configuración de estado deseado (DSC) de Windows PowerShell proporciona un mecanismo para asegurarse de que las características óptimas están habilitadas en un nodo de destino.
Este es un [recurso compuesto](../../../resources/authoringResourceComposite.md) que llama el [recurso WindowsOptionalFeature](windowsOptionalFeatureResource.md) de cada una de las características especificadas en la propiedad `Name`.

Este recurso se usa cuando se desea configurar varias características opcionales de Windows para que tengan el mismo estado.

## <a name="syntax"></a>Sintaxis

```
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string[]]
    [ Ensure = [string] { Enable | Disable }  ]
    [ Source = [string] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]

}
```

## <a name="properties"></a>Propiedades

|  Propiedad  |  Descripción   |
|---|---|
| Nombre| Indica el nombre de las características que desea asegurarse de que están habilitadas o deshabilitadas.|
| Ensure| Especifica si las características están habilitadas. Para asegurarse de que las características están habilitada, establezca esta propiedad en "Enable"; para asegurarse de que están deshabilitadas, establezca la propiedad en "Disable".|
| Origen| Sin implementar.|
| NoWindowsUpdateCheck| Especifica si DISM se pone en contacto con Windows Update (WU) al buscar los archivos de origen para habilitar características. Si el valor es $true, DISM no se pone en contacto con WU.|
| RemoveFilesOnDisable| Establézcalo en **$true** para quitar todos los archivos asociados con las características cuando se deshabiliten (es decir, cuando el valor de **Ensure** (Asegurar) sea "Absent").|
| LogLevel| El nivel de salida máximo que se muestra en los registros. Los valores aceptados son: "ErrorsOnly" (solo se registran los errores), "ErrorsAndWarning" (se registran los errores y las advertencias) y "ErrorsAndWarningAndInformation" (se registran los errores, las advertencias y la información de depuración).|
| LogPath| La ruta de acceso al archivo de registro en el que desea que el proveedor de recursos registre la operación.|
| DependsOn| Especifica que debe ejecutarse la configuración de otro recurso antes de que se configure este recurso. Por ejemplo, si el elemento ID del bloque del script de configuración del recurso que quiere ejecutar primero es __ResourceName__ y su tipo es __ResourceType__, la sintaxis para usar esta propiedad es `DependsOn = "[ResourceType]ResourceName"`.|
