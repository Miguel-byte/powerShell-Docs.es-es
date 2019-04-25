---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Recursos de DSC Package
ms.openlocfilehash: 9285df71a303c9a53dd50d450272575a64e962e7
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077201"
---
# <a name="dsc-package-resource"></a>Recursos de DSC Package

_Se aplica a: Windows PowerShell 4.0, Windows PowerShell 5.0_

El recurso **Package** de la configuración de estado deseado (DSC) de Windows PowerShell ofrece un mecanismo para instalar o desinstalar paquetes, como los paquetes de Windows Installer y setup.exe, en un nodo de destino.

## <a name="syntax"></a>Sintaxis

```
Package [string] #ResourceName
{
    Name = [string]
    Path = [string]
    ProductId = [string]
    [ Arguments = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ ReturnCode = [UInt32[]] ]
}
```

## <a name="properties"></a>Propiedades

| Propiedad | Descripción |
| --- | --- |
| Nombre| Indica el nombre del paquete para el que quiere garantizar un estado específico.|
| Ruta| Indica la ruta de acceso donde reside el paquete.|
| ProductId| Indica el id. de producto que identifica el paquete.|
| Argumentos| Muestra una cadena de argumentos que se pasarán al paquete tal y como se faciliten.|
| Credential| Proporciona acceso al paquete en un origen remoto. Esta propiedad no se utiliza para instalar el paquete. El paquete siempre se instala en el sistema local.|
| Ensure| Indica si el paquete está instalado. Establezca esta propiedad en "Absent" para asegurarse de que el paquete no esté instalado (o se desinstale el paquete si está instalado). Establézcala en "Present" (el valor predeterminado) para asegurarse de que el paquete esté instalado.|
| LogPath| Indica la ruta de acceso completa donde quiere que el proveedor guarde un archivo de registro para instalar o desinstalar el paquete.|
| DependsOn | Indica que la configuración de otro recurso debe ejecutarse antes de que se configure este recurso. Por ejemplo, si el elemento ID del bloque del script de configuración del recurso que quiere ejecutar primero es **ResourceName** y su tipo es **ResourceType**, la sintaxis para usar esta propiedad es `DependsOn = "[ResourceType]ResourceName"`.|
| ReturnCode| Indica el código de retorno esperado. Si el código de retorno real no a coincide con el valor esperado facilitado aquí, la configuración devolverá un error.|

## <a name="example"></a>Ejemplo

En este ejemplo se ejecuta al instalador .msi que se encuentra en la ruta de acceso especificada y tiene el identificador de producto especificado.

```powershell
Configuration PackageTest
{
    Package PackageExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Path        = "$Env:SystemDrive\TestFolder\TestProject.msi"
        Name        = "TestPackage"
        ProductId   = "ACDDCDAF-80C6-41E6-A1B9-8ABD8A05027E"
    }
}
```