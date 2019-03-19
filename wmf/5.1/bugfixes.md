---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,setup
title: Corrección de errores de WMF 5.1
ms.openlocfilehash: f53fc40b79a3906ac2025b0eff342c0705b82655
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795375"
---
# <a name="bug-fixes-in-wmf-51"></a>Corrección de errores de WMF 5.1

## <a name="bug-fixes"></a>Correcciones de errores

Se han corregido los siguientes errores importantes en WMF 5.1:

### <a name="module-auto-discovery-fully-honors-envpsmodulepath"></a>La detección automática de módulos usa `$env:PSModulePath` completamente

La detección automática de módulos (carga de módulos automáticamente sin un cmdlet Import-Module explícito al llamar a un comando) se introdujo en WMF 3.
Cuando se introdujo, PowerShell comprobaba los comandos en `$PSHome\Modules` antes de usar `$env:PSModulePath`.

WMF 5.1 cambia este comportamiento para usar `$env:PSModulePath` completamente.
Esto permite que un módulo creado por el usuario que define los comandos que proporciona PowerShell (por ejemplo, `Get-ChildItem`) se cargue automáticamente y reemplace correctamente el comando integrado.

### <a name="file-redirection-no-longer-hard-codes--encoding-unicode"></a>El redireccionamiento de archivos deja de integrar `-Encoding Unicode` como parte del código

En todas las versiones anteriores de PowerShell, era imposible controlar la codificación de archivos usada por el operador de redireccionamiento de archivos (p. ej., `Get-ChildItem > out.txt` porque PowerShell agregó `-Encoding Unicode`).

A partir de WMF 5.1, se puede cambiar la codificación de archivos del redireccionamiento mediante el establecimiento de `$PSDefaultParameterValues`:

```powershell
$PSDefaultParameterValues["Out-File:Encoding"] = "Ascii"
```

### <a name="fixed-a-regression-in-accessing-members-of-systemreflectiontypeinfo"></a>Se ha corregido una regresión en el acceso de los miembros de `System.Reflection.TypeInfo`

Una regresión introducida en WMF 5.0 interrumpía el acceso de los miembros de `System.Reflection.RuntimeType`, por ejemplo, `[int].ImplementedInterfaces`.
Este error se ha corregido en WMF 5.1.


### <a name="fixed-some-issues-with-com-objects"></a>Se han corregido algunos problemas con objetos COM

WMF 5.0 introdujo un nuevo enlazador COM para invocar métodos en objetos COM y acceder a propiedades de objetos COM.
Este nuevo enlazador ha mejorado considerablemente el rendimiento, pero también ha presentado algunos errores que se han corregido en WMF 5.1.

#### <a name="argument-conversions-were-not-always-performed-correctly"></a>Las conversiones de argumentos no siempre se realizaban correctamente

En el ejemplo siguiente:

```powershell
$obj = New-Object -ComObject WScript.Shell
$obj.SendKeys([char]173)
```

El método SendKeys espera una cadena, pero PowerShell no ha convertido el carácter en una cadena, lo que aplaza la conversión a IDispatch:: Invoke, que usa VariantChangeType para realizar la conversión, lo que en este ejemplo provocó el envío de las claves '1', '7' y '3', en lugar de la clave Volume.Mute, que era la que se esperaba.

#### <a name="enumerable-com-objects-not-always-handled-correctly"></a>Los objetos COM enumerables no siempre se controlan correctamente

PowerShell normalmente enumera la mayoría de los objetos enumerables, pero una regresión introducida en WMF 5.0 impidió la enumeración de objetos COM que implementan IEnumerable.  Por ejemplo:

```powershell
function Get-COMDictionary
{
    $d = New-Object -ComObject Scripting.Dictionary
    $d.Add('a', 2)
    $d.Add('b', 2)
    return $d
}

$x = Get-COMDictionary
```

En el ejemplo anterior, WMF 5.0 escribió incorrectamente Scripting.Dictionary en la canalización, en lugar de enumerar los pares clave-valor.

Este cambio también permite solucionar el [problema 1752224 en Connect](https://connect.microsoft.com/PowerShell/feedback/details/1752224)

### <a name="ordered-was-not-allowed-inside-classes"></a>`[ordered]` no se permitía en las clases

WMF 5.0 introdujo clases con una validación de los literales de tipo que se usan en las clases.
`[ordered]` parece un literal de tipo, pero no es un verdadero tipo .NET.
WMF 5.0 informaba incorrectamente de un error en `[ordered]` dentro de una clase:

```powershell
class CThing
{
    [object] foo($i)
    {
        [ordered]@{ Thing = $i }
    }
}
```


### <a name="help-on-about-topics-with-multiple-versions-does-not-work"></a>Los temas de ayuda con varias versiones no funcionan

Antes de WMF 5.1, si había varias versiones de un módulo instaladas y todas compartían un tema de ayuda, por ejemplo, about_PSReadline, `help about_PSReadline` devolvía varios temas sin ninguna forma obvia de ver la ayuda real.

WMF 5.1 corrige este problema, para lo que devuelve la ayuda de la versión más reciente del tema.

`Get-Help` no proporciona una forma de especificar para qué versión se quiere la ayuda.
Para solucionar este problema, navegue hasta el directorio modules y vea la ayuda directamente con una herramienta como su editor favorito.

### <a name="powershellexe-reading-from-stdin-stopped-working"></a>La lectura de powerShell.exe desde STDIN dejó de funcionar

Los clientes utilizan `powershell -command -` de las aplicaciones nativas para ejecutar PowerShell pasando el script a través de STDIN. Desafortunadamente esto se ha interrumpido debido a otros cambios en el host de consola.

https://windowsserver.uservoice.com/forums/301869-powershell/suggestions/15854689-powershell-exe-command-is-broken-on-windows-10

### <a name="powershellexe-creates-spike-in-cpu-usage-on-startup"></a>powershell.exe origina un punto máximo en el uso de CPU en el inicio

PowerShell usa una consulta WMI para comprobar que se ha iniciado a través de la directiva de grupo para evitar los retrasos en el inicio de sesión.
La consulta WMI termina con la inyección de tzres.mui.dll en todos los procesos del sistema, puesto que la clase Win32_Process de WMI intenta recuperar la información de la zona horaria local.
Esto produce un gran aumento de la CPU en wmiprvse (el host del proveedor WMI).
La solución consiste en utilizar llamadas a la API de Win32 para obtener la misma información en lugar de usar WMI.
