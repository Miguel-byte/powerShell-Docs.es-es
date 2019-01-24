---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Importación de una versión específica de un recurso instalado
ms.openlocfilehash: 5ed81e11aa67eb6590d958647f48a33b1b5f1c0e
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402209"
---
# <a name="import-a-specific-version-of-an-installed-resource"></a><span data-ttu-id="24c26-103">Importación de una versión específica de un recurso instalado</span><span class="sxs-lookup"><span data-stu-id="24c26-103">Import a specific version of an installed resource</span></span>

> <span data-ttu-id="24c26-104">Se aplica a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="24c26-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="24c26-105">En PowerShell 5.0, versiones independientes de los recursos de DSC pueden instalarse en un equipo en paralelo.</span><span class="sxs-lookup"><span data-stu-id="24c26-105">In PowerShell 5.0, separate versions of DSC resources can be installed on a computer side by side.</span></span> <span data-ttu-id="24c26-106">Un módulo de recursos puede almacenar versiones independientes de un recurso en carpetas denominada de versión.</span><span class="sxs-lookup"><span data-stu-id="24c26-106">A resource module can store separate versions of a resource in version named folders.</span></span>

## <a name="installing-separate-resource-versions-side-by-side"></a><span data-ttu-id="24c26-107">Instalación de versiones de recursos independiente en paralelo</span><span class="sxs-lookup"><span data-stu-id="24c26-107">Installing separate resource versions side by side</span></span>

<span data-ttu-id="24c26-108">Puede usar los parámetros **MinimumVersion**, **MaximumVersion** y **RequiredVersion** del cmdlet [Install-Module](/powershell/module/PowershellGet/Install-Module) para especificar la versión de un módulo que se va a instalar.</span><span class="sxs-lookup"><span data-stu-id="24c26-108">You can use the **MinimumVersion**, **MaximumVersion**, and **RequiredVersion** parameters of the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to specify which version of a module to install.</span></span> <span data-ttu-id="24c26-109">Llamar a **Install-Module** sin especificar una versión instala la versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="24c26-109">Calling **Install-Module** without specifying a version installs the most recent version.</span></span>

<span data-ttu-id="24c26-110">Por ejemplo, hay varias versiones del módulo **xFailOverCluster**, cada una de las cuales contiene un recurso **xCluster**.</span><span class="sxs-lookup"><span data-stu-id="24c26-110">For example, there are multiple versions of the **xFailOverCluster** module, each of which contains an **xCluster** resource.</span></span> <span data-ttu-id="24c26-111">Una llamada a **Install-Module** sin especificar la versión número instala la versión más reciente del módulo.</span><span class="sxs-lookup"><span data-stu-id="24c26-111">Calling **Install-Module** without specifying the version number installs the most recent version of the module.</span></span>

```powershell
PS> Install-Module xFailOverCluster
PS> Get-DscResource xCluster
```

```output
ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, ...
```

<span data-ttu-id="24c26-112">Para instalar una versión específica de un módulo, especifique un **RequiredVersion** de 1.1.0.0.</span><span class="sxs-lookup"><span data-stu-id="24c26-112">To install a specific version of a module, specify a **RequiredVersion** of 1.1.0.0.</span></span> <span data-ttu-id="24c26-113">Esto instala la versión especificada en paralelo con la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="24c26-113">This installs the specified version side by side with the installed version.</span></span>

```powershell
PS> Install-Module xFailOverCluster -RequiredVersion 1.1
```

<span data-ttu-id="24c26-114">Ahora, puede ver tanto la versión del módulo que se enumera cuando se utiliza `Get-DSCResource`.</span><span class="sxs-lookup"><span data-stu-id="24c26-114">Now, you see both version of the module listed when you use `Get-DSCResource`.</span></span>

```powershell
PS> Get-DscResource xCluster
```

```output
ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.1        {DomainAdministratorCredential, Name, ...
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, Name, ...
```

## <a name="specifying-a-resource-version-in-a-configuration"></a><span data-ttu-id="24c26-115">Especificación de una versión de recursos en una configuración</span><span class="sxs-lookup"><span data-stu-id="24c26-115">Specifying a resource version in a configuration</span></span>

<span data-ttu-id="24c26-116">Si tiene instaladas en un equipo de versiones de recursos independiente, debe especificar la versión de ese recurso cuando se usa en una configuración.</span><span class="sxs-lookup"><span data-stu-id="24c26-116">If you have separate resource versions installed on a computer, you must specify the version of that resource when you use it in a configuration.</span></span> <span data-ttu-id="24c26-117">Esto se hace mediante la especificación del parámetro **ModuleVersion** de la palabra clave **Import-DscResource**.</span><span class="sxs-lookup"><span data-stu-id="24c26-117">You do this by specifying the **ModuleVersion** parameter of the **Import-DscResource** keyword.</span></span> <span data-ttu-id="24c26-118">Si tiene instaladas varias versiones de un recurso y no especifica la versión del módulo de recursos que quiere usar, la configuración generará un error.</span><span class="sxs-lookup"><span data-stu-id="24c26-118">If you fail to specify the version of a resource module of a resource of which you have more than one version installed, the configuration generates an error.</span></span>

<span data-ttu-id="24c26-119">La configuración siguiente muestra cómo especificar la versión del recurso al que se va a llamar:</span><span class="sxs-lookup"><span data-stu-id="24c26-119">The following configuration shows how to specify the version of the resource to call:</span></span>

```powershell
configuration VersionTest
{
    Import-DscResource -ModuleName xFailOverCluster -ModuleVersion 1.1

    Node 'localhost'
    {
       xCluster ClusterTest
       {
            Name                          = 'TestCluster'
            StaticIPAddress               = '10.0.0.3'
            DomainAdministratorCredential = Get-Credential
        }
     }
}
```

><span data-ttu-id="24c26-120">Nota: El parámetro ModuleVersion de Import-DscResource no está disponible en PowerShell 4.0.</span><span class="sxs-lookup"><span data-stu-id="24c26-120">Note: The ModuleVersion parameter of Import-DscResource is not available in PowerShell 4.0.</span></span> <span data-ttu-id="24c26-121">En PowerShell 4.0, puede especificar una versión de módulo pasando un objeto de especificación de módulo al parámetro ModuleName de Import-DscResource.</span><span class="sxs-lookup"><span data-stu-id="24c26-121">In PowerShell 4.0, you can specify a module version by passing a module specification object to the ModuleName parameter of Import-DscResource.</span></span> <span data-ttu-id="24c26-122">Un objeto de especificación de módulo es una tabla hash que contiene las claves ModuleName y RequiredVersion.</span><span class="sxs-lookup"><span data-stu-id="24c26-122">A module specification object is a hash table that contains ModuleName and RequiredVersion  keys.</span></span> <span data-ttu-id="24c26-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="24c26-123">For example:</span></span>

```powershell
configuration VersionTest
{
    Import-DscResource -ModuleName (@{ModuleName='xFailOverCluster'; RequiredVersion='1.1'} )

    Node 'localhost'
    {
       xCluster ClusterTest
       {
            Name                          = 'TestCluster'
            StaticIPAddress               = '10.0.0.3'
            DomainAdministratorCredential = Get-Credential
        }
     }
}
```

<span data-ttu-id="24c26-124">Esto también funcionará en PowerShell 5.0, pero se recomienda que use el parámetro **ModuleVersion**.</span><span class="sxs-lookup"><span data-stu-id="24c26-124">This will also work in PowerShell 5.0, but it is recommended that you use the **ModuleVersion** parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="24c26-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="24c26-125">See also</span></span>

- [<span data-ttu-id="24c26-126">Configuraciones DSC</span><span class="sxs-lookup"><span data-stu-id="24c26-126">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="24c26-127">Recursos de DSC</span><span class="sxs-lookup"><span data-stu-id="24c26-127">DSC Resources</span></span>](../resources/resources.md)