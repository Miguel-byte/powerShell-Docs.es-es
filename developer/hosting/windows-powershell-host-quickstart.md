---
title: Guía de inicio rápido de Windows PowerShell Host | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a134b81-bd0c-4e1c-a2f0-9acbe852745a
caps.latest.revision: 9
ms.openlocfilehash: 390eb2d0153c65967d8c0711c852aa6e13fe4660
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855101"
---
# <a name="windows-powershell-host-quickstart"></a>Inicio rápido de Host de Windows PowerShell

Para hospedar Windows PowerShell en la aplicación, usa el [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) clase.
Esta clase proporciona métodos que se creación una canalización de comandos y, a continuación, ejecutan esos comandos en un espacio de ejecución.
La manera más sencilla de crear una aplicación host es usar el espacio de ejecución predeterminado.
El espacio de ejecución predeterminada contiene todos los comandos de Windows PowerShell core.
Si desea que la aplicación para exponer solo un subconjunto de los comandos de Windows PowerShell, debe crear un espacio de ejecución personalizado.

## <a name="using-the-default-runspace"></a>Uso de espacio de ejecución predeterminado

Para empezar, se utilizará el espacio de ejecución de forma predeterminada y utilice los métodos de la [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) clase para agregar los comandos, parámetros, instrucciones y secuencias de comandos a una canalización.

### <a name="addcommand"></a>AddCommand

Usa el [System.Management.Automation.Powershell.AddCommand](/dotnet/api/System.Management.Automation.PowerShell.AddCommand) método para agregar comandos a la canalización.
Por ejemplo, suponga que desea obtener la lista de procesos en ejecución en el equipo.
La forma de ejecutar este comando es como sigue.

1. Crear un [System.Management.Automation.PowerShell](/dotnet/api/System.Management.Automation.PowerShell) objeto.

   ```csharp
   PowerShell ps = PowerShell.Create();
   ```

2. Agregue el comando que desea ejecutar.

   ```csharp
   ps.AddCommand("Get-Process");
   ```

3. Invoque el comando.

   ```csharp
   ps.Invoke();
   ```

Si se llama al método AddCommand más de una vez antes de llamar a la [System.Management.Automation.Powershell.Invoke](/dotnet/api/System.Management.Automation.PowerShell.Invoke) método, el resultado del primer comando se canaliza hacia el segundo y así sucesivamente.
Si no desea canalizar el resultado de un comando a un comando anterior, puede agregarlo mediante una llamada a la [System.Management.Automation.Powershell.AddStatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) en su lugar.

### <a name="addparameter"></a>AddParameter

El ejemplo anterior ejecuta un comando único sin ningún parámetro.
Puede agregar parámetros al comando mediante el [System.Management.Automation.PSCommand.AddParameter](/dotnet/api/System.Management.Automation.PSCommand.AddParameter) método.
Por ejemplo, el código siguiente obtiene una lista de todos los procesos que se denominan `PowerShell` que se ejecuta en la máquina.

```csharp
PowerShell.Create().AddCommand("Get-Process")
                   .AddParameter("Name", "PowerShell")
                   .Invoke();
```

Puede agregar parámetros adicionales llamando al método AddParameter repetidamente.

```csharp                   
PowerShell.Create().AddCommand("Get-ChildItem")
                   .AddParameter("Path", @"c:\Windows")
                   .AddParameter("Filter", "*.exe")
                   .Invoke();
```

También puede agregar un diccionario de nombres de parámetros y valores mediante una llamada a la [System.Management.Automation.PowerShell.AddParameters](/dotnet/api/System.Management.Automation.PowerShell.AddParameters) método.

```csharp
IDictionary parameters = new Dictionary<String, String>();
parameters.Add("Path", @"c:\Windows");
parameters.Add("Filter", "*.exe");

PowerShell.Create().AddCommand("Get-Process")
   .AddParameters(parameters)
      .Invoke()

```

### <a name="addstatement"></a>AddStatement

Puede simular el procesamiento por lotes utilizando el [System.Management.Automation.PowerShell.AddStatement](/dotnet/api/System.Management.Automation.PowerShell.AddStatement) método, que agrega una instrucción adicional al final de la canalización.
El código siguiente obtiene una lista de procesos en ejecución con el nombre `PowerShell`y, a continuación, obtiene la lista de servicios en ejecución.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddCommand("Get-Process").AddParameter("Name", "PowerShell");
ps.AddStatement().AddCommand("Get-Service");
ps.Invoke();
```

### <a name="addscript"></a>AddScript

Puede ejecutar un script existente mediante una llamada a la [System.Management.Automation.PowerShell.AddScript](/dotnet/api/System.Management.Automation.PowerShell.AddScript) método.
El ejemplo siguiente agrega una secuencia de comandos a la canalización y lo ejecuta.
En este ejemplo se da por supuesto que ya hay un script denominado `MyScript.ps1` en una carpeta denominada `D:\PSScripts`.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript("D:\PSScripts\MyScript.ps1").Invoke();
```

También hay una versión del método AddScript que toma un parámetro booleano denominado `useLocalScope`.
Si este parámetro se establece en `true`, a continuación, el script se ejecuta en el ámbito local.
El siguiente código ejecutará el script en el ámbito local.

```csharp
PowerShell ps = PowerShell.Create();
ps.AddScript(@"D:\PSScripts\MyScript.ps1", true).Invoke();
```

## <a name="creating-a-custom-runspace"></a>Creación de un espacio de ejecución personalizado

Mientras todos los comandos de Windows PowerShell core carga en el espacio de ejecución predeterminado utilizado en los ejemplos anteriores, puede crear un espacio de ejecución personalizado que solo un subconjunto especificado de todos los comandos de carga.
Es posible que desee hacer esto para mejorar el rendimiento (cargando un mayor número de comandos es una disminución del rendimiento), o para restringir la capacidad del usuario para realizar operaciones.
Un espacio de ejecución que expone sólo un número limitado de comandos se llama a un espacio de ejecución restringido.
Para crear un espacio de ejecución restringido, utilice el [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) y [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) clases.

### <a name="creating-an-initialsessionstate-object"></a>Creación de un objeto InitialSessionState

Para crear un espacio de ejecución personalizado, debe crear primero un [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) objeto.
En el ejemplo siguiente, usamos el [System.Management.Automation.Runspaces.RunspaceFactory](/dotnet/api/System.Management.Automation.Runspaces.RunspaceFactory) para crear un espacio de ejecución después de crear un objeto de InitialSessionState predeterminado.

```csharp
InitialSessionState iss = InitialSessionState.CreateDefault();
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
ps.Invoke();
```

### <a name="constraining-the-runspace"></a>Restringir el espacio de ejecución

En el ejemplo anterior, creamos un valor predeterminado [System.Management.Automation.Runspaces.InitialSessionState](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) objeto que se carga todo el núcleo integrado de Windows PowerShell.
Llamamos también podríamos haber a la [System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.CreateDefault2) método para crear un objeto InitialSessionState que se pueda cargar solo los comandos en el Microsoft.PowerShell.Core complemento.
Para crear un espacio de ejecución más restringido, debe crear un objeto InitialSessionState vacío llamando el [System.Management.Automation.Runspaces.InitialSessionState.Create](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState.Create) método y, a continuación, agregar comandos a la InitialSessionState.

Uso de un espacio de ejecución que carga únicamente los comandos que especifique proporciona mejora significativa del rendimiento.

Utilice los métodos de la [System.Management.Automation.Runspaces.SessionStateCmdletEntry](/dotnet/api/System.Management.Automation.Runspaces.SessionStateCmdletEntry) clase para definir los cmdlets de para el estado de sesión inicial.
En el ejemplo siguiente se crea un estado de sesión inicial vacío, a continuación, define y agrega el `Get-Command` y `Import-Module` comandos para el estado de sesión inicial.
A continuación, crear un espacio de ejecución restringido por ese estado de sesión inicial y ejecute los comandos en ese espacio de ejecución.

Crear el estado de sesión inicial.

```csharp
InitialSessionState iss = InitialSessionState.Create();
```

Definir y agregar comandos para el estado de sesión inicial.

```csharp
SessionStateCmdletEntry getCommand = new SessionStateCmdletEntry(
        "Get-Command", typeof(Microsoft.PowerShell.Commands.GetCommandCommand), "");
SessionStateCmdletEntry importModule = new SessionStateCmdletEntry(
        "Import-Module", typeof(Microsoft.PowerShell.Commands.ImportModuleCommand), "");
iss.Commands.Add(getCommand);
iss.Commands.Add(importModule);
```

Crear y abrir el espacio de ejecución.

```csharp
Runspace rs = RunspaceFactory.CreateRunspace(iss);
rs.Open();
```

Ejecutar un comando y muestra el resultado.

```csharp
PowerShell ps = PowerShell.Create();
ps.Runspace = rs;
ps.AddCommand("Get-Command");
Collection<CommandInfo> result = ps.Invoke<CommandInfo>();
foreach (var entry in result)
{
       Console.WriteLine(entry.Name);
}
```

Cuando se ejecuta, el resultado de este código tendrá un aspecto como sigue.

```powershell
Get-Command
Import-Module
```
