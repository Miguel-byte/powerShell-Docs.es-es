---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Recurso WindowsPackageCab de DSC
ms.openlocfilehash: 035944e7ca5c7469250c48a19b79f2f2d5d38e9a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076946"
---
# <a name="dsc-windowspackagecab-resource"></a>Recurso WindowsPackageCab de DSC

> Se aplica a: Windows PowerShell 5.1 y posterior

El recurso **WindowsPackageCab** de Desired State Configuration (DSC) de Windows PowerShell ofrece un mecanismo para instalar o desinstalar paquetes de archivos .cab de Windows en un nodo de destino.

El nodo de destino debe tener instalado el módulo PowerShell de DISM. Para información, consulte [Use DISM in Windows PowerShell](https://msdn.microsoft.com/en-us/windows/hardware/commercialize/manufacture/desktop/use-dism-in-windows-powershell-s14) (Uso de DISM en Windows PowerShell).


## <a name="syntax"></a>Sintaxis

```
{
    Name = [string]
    Ensure = [string] { Absent | Present }
    SourcePath = [string]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a>Propiedades

|  Propiedad  |  Descripción   |
|---|---|
| Nombre| Indica el nombre del paquete para el que quiere garantizar un estado específico.|
| Ensure| Indica si el paquete está instalado. Establezca esta propiedad en "Absent" para asegurarse de que el paquete no esté instalado (o se desinstale el paquete si está instalado). Establézcala en "Present" (el valor predeterminado) para asegurarse de que el paquete esté instalado.|
| Ruta| Indica la ruta de acceso donde reside el paquete.|
| LogPath| Indica la ruta de acceso completa donde quiere que el proveedor guarde un archivo de registro para instalar o desinstalar el paquete.|
| DependsOn | Indica que la configuración de otro recurso debe ejecutarse antes de que se configure este recurso. Por ejemplo, si el elemento ID del bloque del script de configuración del recurso que quiere ejecutar primero es **ResourceName** y su tipo es **ResourceType**, la sintaxis para usar esta propiedad es `DependsOn = "[ResourceType]ResourceName"``.|

## <a name="example"></a>Ejemplo

La configuración de ejemplo siguiente toma parámetros de entrada y se asegura de que el archivo .cab especificado en el parámetro `$Name` esté instalado.

```powershell
Configuration Sample_WindowsPackageCab
{
    param
    (
        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $Name,

        [Parameter (Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $SourcePath,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $LogPath
    )

    Import-DscResource -ModuleName 'PSDscResources'

    WindowsPackageCab WindowsPackageCab1
    {
        Name = $Name
        Ensure = 'Present'
        SourcePath = $SourcePath
        LogPath = $LogPath
    }
}
```