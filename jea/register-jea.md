---
ms.date: 06/12/2017
keywords: jea,powershell,security
title: Registro de configuraciones de JEA
ms.openlocfilehash: 6fa0ce434c8e70eb718545e99417bfe034cda6bf
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084834"
---
# <a name="registering-jea-configurations"></a><span data-ttu-id="7e067-103">Registro de configuraciones de JEA</span><span class="sxs-lookup"><span data-stu-id="7e067-103">Registering JEA Configurations</span></span>

> <span data-ttu-id="7e067-104">Se aplica a: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="7e067-104">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="7e067-105">El último paso antes de poder usar JEA una vez que ha creado las [funcionalidades de rol](role-capabilities.md) y el [archivo de configuración de sesión](session-configurations.md) es registrar el punto de conexión de JEA.</span><span class="sxs-lookup"><span data-stu-id="7e067-105">Once you have your [role capabilities](role-capabilities.md) and [session configuration file](session-configurations.md) created, the last step before you can use JEA is to register the JEA endpoint.</span></span>
<span data-ttu-id="7e067-106">El registro del punto de conexión de JEA en el sistema pone a disposición el punto de conexión para que lo usen los motores de automatización y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7e067-106">Registering the JEA endpoint with the system makes the endpoint available for use by users and automation engines.</span></span>

## <a name="single-machine-configuration"></a><span data-ttu-id="7e067-107">Configuración de la máquina sencilla</span><span class="sxs-lookup"><span data-stu-id="7e067-107">Single machine configuration</span></span>

<span data-ttu-id="7e067-108">Para entornos pequeños, puede implementar JEA al registrar el archivo de configuración de sesión mediante el cmdlet [Register-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/register-pssessionconfiguration).</span><span class="sxs-lookup"><span data-stu-id="7e067-108">For small environments, you can deploy JEA by registering the session configuration file using the [Register-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/register-pssessionconfiguration) cmdlet.</span></span>

<span data-ttu-id="7e067-109">Antes de comenzar, asegúrese de que se cumplen los requisitos previos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e067-109">Before you begin, ensure that the following prerequisites have been met:</span></span>
- <span data-ttu-id="7e067-110">Se han creado uno o varios roles y se han colocado en la carpeta "RoleCapabilities" de un módulo de PowerShell válido.</span><span class="sxs-lookup"><span data-stu-id="7e067-110">One or more roles has been created and placed in the 'RoleCapabilities' folder of a valid PowerShell module.</span></span>
- <span data-ttu-id="7e067-111">Se ha creado y probado un archivo de configuración de sesión.</span><span class="sxs-lookup"><span data-stu-id="7e067-111">A session configuration file has been created and tested.</span></span>
- <span data-ttu-id="7e067-112">El usuario que registra la configuración de JEA tiene derechos de administrador en los sistemas.</span><span class="sxs-lookup"><span data-stu-id="7e067-112">The user registering the JEA configuration has administrator rights on the system(s).</span></span>

<span data-ttu-id="7e067-113">También necesita seleccionar un nombre para el punto de conexión de JEA.</span><span class="sxs-lookup"><span data-stu-id="7e067-113">You also need to select a name for your JEA endpoint.</span></span>
<span data-ttu-id="7e067-114">El nombre del punto de conexión de JEA es necesario cuando los usuarios quieran conectarse al sistema mediante JEA.</span><span class="sxs-lookup"><span data-stu-id="7e067-114">The name of the JEA endpoint is required when users want to connect to the system using JEA.</span></span>
<span data-ttu-id="7e067-115">Puede usar el cmdlet [Get-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/get-pssessionconfiguration) para comprobar los nombres de los puntos de conexión existentes en el sistema.</span><span class="sxs-lookup"><span data-stu-id="7e067-115">You can use the [Get-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/get-pssessionconfiguration) cmdlet to check the names of existing endpoints on the system.</span></span>
<span data-ttu-id="7e067-116">Los puntos de conexión que empiezan por "microsoft" se entregan normalmente con Windows.</span><span class="sxs-lookup"><span data-stu-id="7e067-116">Endpoints that start with 'microsoft' are typically shipped with Windows.</span></span>
<span data-ttu-id="7e067-117">El punto de conexión "microsoft.powershell" es el que se usa de manera predeterminada al conectarse a un punto de conexión remoto de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7e067-117">The 'microsoft.powershell' endpoint is the default endpoint used when connecting to a remote PowerShell endpoint.</span></span>

```powershell
PS C:\> Get-PSSessionConfiguration | Select-Object Name

Name
----
microsoft.powershell
microsoft.powershell.workflow
microsoft.powershell32
```

<span data-ttu-id="7e067-118">Cuando haya determinado un nombre adecuado para el punto de conexión de JEA, ejecute el siguiente comando para registrarlo.</span><span class="sxs-lookup"><span data-stu-id="7e067-118">When you have determined an appropriate name for your JEA endpoint, run the following command to register the endpoint.</span></span>

```powershell
Register-PSSessionConfiguration -Path .\MyJEAConfig.pssc -Name 'JEAMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="7e067-119">El comando anterior reinicia el servicio WinRM en el sistema.</span><span class="sxs-lookup"><span data-stu-id="7e067-119">The above command restarts the WinRM service on the system.</span></span>
> <span data-ttu-id="7e067-120">Esto finaliza todas las sesiones de comunicación remota de PowerShell, así como las configuraciones de DSC en curso.</span><span class="sxs-lookup"><span data-stu-id="7e067-120">This terminates all PowerShell remoting sessions as well as any ongoing DSC configurations.</span></span>
> <span data-ttu-id="7e067-121">Se recomienda que desconecte todas las máquinas de producción antes de ejecutar el comando para evitar interrumpir operaciones empresariales.</span><span class="sxs-lookup"><span data-stu-id="7e067-121">It is recommended that you take any production machines offline before running the command to avoid disrupting business operations.</span></span>

<span data-ttu-id="7e067-122">Si el registro se realiza correctamente, está listo para [usar JEA](using-jea.md).</span><span class="sxs-lookup"><span data-stu-id="7e067-122">If registration is successful, you are ready to [use JEA](using-jea.md).</span></span>
<span data-ttu-id="7e067-123">Puede eliminar el archivo de configuración de sesión en cualquier momento; no se usa después del registro del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7e067-123">You may delete the session configuration file at any time; it is not used after registration of the end point.</span></span>

## <a name="multi-machine-configuration-with-dsc"></a><span data-ttu-id="7e067-124">Configuración de varios equipos con DSC</span><span class="sxs-lookup"><span data-stu-id="7e067-124">Multi-machine configuration with DSC</span></span>

<span data-ttu-id="7e067-125">Si va a implementar JEA en varios equipos, el modelo de implementación más sencillo es usar el recurso de [configuración de estado deseado](https://msdn.microsoft.com/powershell/dsc/overview) de JEA para implementar JEA en todos los equipos de forma rápida y coherente.</span><span class="sxs-lookup"><span data-stu-id="7e067-125">If you are deploying JEA on multiple machines, the simplest deployment model is to use the JEA [Desired State Configuration](https://msdn.microsoft.com/powershell/dsc/overview) resource to quickly and consistently deploy JEA on each machine.</span></span>

<span data-ttu-id="7e067-126">Para implementar JEA con DSC, debe asegurarse de que se cumplen los requisitos previos siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e067-126">To deploy JEA with DSC, you need to ensure the following prerequisites are met:</span></span>
- <span data-ttu-id="7e067-127">Se han creado una o varias funcionalidades de rol y se han agregado a un módulo de PowerShell válido.</span><span class="sxs-lookup"><span data-stu-id="7e067-127">One or more role capabilities have been authored and added to a valid PowerShell module.</span></span>
- <span data-ttu-id="7e067-128">El módulo de PowerShell que contiene los roles se almacena en un recurso compartido de archivo (de solo lectura) al que pueden obtener acceso todos los equipos.</span><span class="sxs-lookup"><span data-stu-id="7e067-128">The PowerShell module containing the roles is stored on a (read-only) file share accessible by each machine.</span></span>
- <span data-ttu-id="7e067-129">Se ha determinado la configuración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="7e067-129">Settings for the session configuration have been determined.</span></span> <span data-ttu-id="7e067-130">No es necesario crear un archivo de configuración de sesión cuando se usa el recurso DSC de JEA.</span><span class="sxs-lookup"><span data-stu-id="7e067-130">You do not need to create a session configuration file when using the JEA DSC resource.</span></span>
- <span data-ttu-id="7e067-131">Tiene credenciales que le permiten realizar acciones administrativas en todos los equipos, o tiene acceso a un servidor de extracción de DSC usado para administrar los equipos.</span><span class="sxs-lookup"><span data-stu-id="7e067-131">You have credentials that allow you to perform administrative actions on each machine, or have access to a DSC pull server used to manage the machines.</span></span>
- <span data-ttu-id="7e067-132">Ha descargado el [recurso de DSC de JEA](https://github.com/PowerShell/JEA/tree/master/DSC%20Resource).</span><span class="sxs-lookup"><span data-stu-id="7e067-132">You have downloaded the [JEA DSC resource](https://github.com/PowerShell/JEA/tree/master/DSC%20Resource)</span></span>

<span data-ttu-id="7e067-133">En un equipo de destino (o servidor de incorporación de cambios, si usa uno), cree una configuración de DSC para el punto de conexión de JEA.</span><span class="sxs-lookup"><span data-stu-id="7e067-133">On a target machine (or pull server, if you are using one), create a DSC configuration for your JEA endpoint.</span></span>
<span data-ttu-id="7e067-134">En esta configuración, se usa el recurso de DSC JustEnoughAdministration para configurar el archivo de configuración de sesión y el recurso de archivos para copiar mediante las funcionalidades de rol desde el recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="7e067-134">In this configuration, you use the JustEnoughAdministration DSC resource to set up the session configuration file and the File resource to copy over the role capabilities from the file share.</span></span>

<span data-ttu-id="7e067-135">Se pueden configurar las siguientes propiedades con el recurso de DSC:</span><span class="sxs-lookup"><span data-stu-id="7e067-135">The following properties are configurable using the DSC resource:</span></span>
- <span data-ttu-id="7e067-136">Definiciones de roles</span><span class="sxs-lookup"><span data-stu-id="7e067-136">Role Definitions</span></span>
- <span data-ttu-id="7e067-137">Grupos de cuenta virtual</span><span class="sxs-lookup"><span data-stu-id="7e067-137">Virtual Account groups</span></span>
- <span data-ttu-id="7e067-138">Nombre de cuenta de servicio administrada de grupo</span><span class="sxs-lookup"><span data-stu-id="7e067-138">Group Managed Service Account name</span></span>
- <span data-ttu-id="7e067-139">Directorio de transcripciones</span><span class="sxs-lookup"><span data-stu-id="7e067-139">Transcript directory</span></span>
- <span data-ttu-id="7e067-140">Unidad de usuario</span><span class="sxs-lookup"><span data-stu-id="7e067-140">User drive</span></span>
- <span data-ttu-id="7e067-141">Reglas de acceso condicional</span><span class="sxs-lookup"><span data-stu-id="7e067-141">Conditional access rules</span></span>
- <span data-ttu-id="7e067-142">Scripts de inicio de la sesión de JEA</span><span class="sxs-lookup"><span data-stu-id="7e067-142">Startup scripts for the JEA session</span></span>

<span data-ttu-id="7e067-143">La sintaxis de cada una de estas propiedades en una configuración de DSC es coherente con el archivo de configuración de sesión de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7e067-143">The syntax for each of these properties in a DSC configuration is consistent with the PowerShell session configuration file.</span></span>

<span data-ttu-id="7e067-144">A continuación se muestra un ejemplo de configuración de DSC de un módulo de mantenimiento general del servidor.</span><span class="sxs-lookup"><span data-stu-id="7e067-144">Below is a sample DSC configuration for a general server maintenance module.</span></span>

<span data-ttu-id="7e067-145">Supone que un módulo de PowerShell válido que contiene las funcionalidades de rol en una subcarpeta "RoleCapabilities" se encuentra en el recurso compartido de archivos "\\\\mirecursocompartidodearchivos\\JEA".</span><span class="sxs-lookup"><span data-stu-id="7e067-145">It assumes that a valid PowerShell module containing role capabilities in a 'RoleCapabilities' subfolder is located on the '\\\\myfileshare\\JEA' file share.</span></span>


```powershell
Configuration JEAMaintenance
{
    Import-DscResource -Module JustEnoughAdministration, PSDesiredStateConfiguration

    File MaintenanceModule
    {
        SourcePath = "\\myfileshare\JEA\ContosoMaintenance"
        DestinationPath = "C:\Program Files\WindowsPowerShell\Modules\ContosoMaintenance"
        Checksum = "SHA-256"
        Ensure = "Present"
        Type = "Directory"
        Recurse = $true
    }

    JeaEndpoint JEAMaintenanceEndpoint
    {
        EndpointName = "JEAMaintenance"
        RoleDefinitions = "@{ 'CONTOSO\JEAMaintenanceAuditors' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit' }; 'CONTOSO\JEAMaintenanceAdmins' = @{ RoleCapabilities = 'GeneralServerMaintenance-Audit', 'GeneralServerMaintenance-Admin' } }"
        TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
        DependsOn = '[File]MaintenanceModule'
    }
}
```

<span data-ttu-id="7e067-146">Después, se puede aplicar esta configuración en un sistema al [invocar directamente el administrador de configuración local](https://msdn.microsoft.com/powershell/dsc/metaconfig) o actualizar la [configuración del servidor de incorporación de cambios](https://msdn.microsoft.com/powershell/dsc/pullserver).</span><span class="sxs-lookup"><span data-stu-id="7e067-146">This configuration can then be applied on a system by [directly invoking the Local Configuration Manager](https://msdn.microsoft.com/powershell/dsc/metaconfig) or updating the [pull server configuration](https://msdn.microsoft.com/powershell/dsc/pullserver).</span></span>

<span data-ttu-id="7e067-147">El recurso de DSC también permite reemplazar el punto de conexión de comunicación remota Microsoft.PowerShell predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7e067-147">The DSC resource also allows you to replace the default Microsoft.PowerShell remoting endpoint.</span></span>
<span data-ttu-id="7e067-148">Si lo hace, el recurso registra de forma automática un punto de conexión sin restricciones de copia de seguridad denominado "Microsoft.PowerShell.Restricted", que tiene la ACL de WinRM predeterminada (que permite que los miembros del grupo de administradores locales y usuarios de administración remota obtengan acceso a él).</span><span class="sxs-lookup"><span data-stu-id="7e067-148">If you do this, the resource automatically registers a backup unconstrained endpoint named "Microsoft.PowerShell.Restricted" which has the default WinRM ACL (allowing Remote Management Users and local Administrators group members to access it).</span></span>

## <a name="unregistering-jea-configurations"></a><span data-ttu-id="7e067-149">Anular el registro de configuraciones de JEA</span><span class="sxs-lookup"><span data-stu-id="7e067-149">Unregistering JEA configurations</span></span>

<span data-ttu-id="7e067-150">Para quitar un punto de conexión de JEA de un sistema, use el cmdlet [Unregister-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/Unregister-PSSessionConfiguration).</span><span class="sxs-lookup"><span data-stu-id="7e067-150">To remove a JEA endpoint on a system, use the [Unregister-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/Unregister-PSSessionConfiguration) cmdlet.</span></span>
<span data-ttu-id="7e067-151">Si anula el registro de un punto de conexión de JEA, evitará que nuevos usuarios creen sesiones de JEA en el sistema.</span><span class="sxs-lookup"><span data-stu-id="7e067-151">Unregistering a JEA endpoint prevents new users from creating new JEA sessions on the system.</span></span>
<span data-ttu-id="7e067-152">También permite actualizar una configuración de JEA al volver a registrar un archivo de configuración de sesión actualizado con el mismo nombre de punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="7e067-152">It also allows you to update a JEA configuration by re-registering an updated session configuration file using the same endpoint name.</span></span>

```powershell
# Unregister the JEA endpoint called "ContosoMaintenance"
Unregister-PSSessionConfiguration -Name 'ContosoMaintenance' -Force
```

> [!WARNING]
> <span data-ttu-id="7e067-153">Anular el registro de un punto de conexión de JEA provocará que se reinicie el servicio WinRM.</span><span class="sxs-lookup"><span data-stu-id="7e067-153">Unregistering a JEA endpoint causes the WinRM service to restart.</span></span>
> <span data-ttu-id="7e067-154">Esto interrumpe la mayoría de las operaciones de administración remotas en curso, incluidas otras sesiones de PowerShell, invocaciones de WMI y algunas herramientas de administración.</span><span class="sxs-lookup"><span data-stu-id="7e067-154">This interrupts most remote management operations in progress, including other PowerShell sessions, WMI invocations, and some management tools.</span></span>
> <span data-ttu-id="7e067-155">Anule el registro de puntos de conexión de PowerShell solo durante ventanas de mantenimiento planificadas.</span><span class="sxs-lookup"><span data-stu-id="7e067-155">Only unregister PowerShell endpoints during planned maintenance windows.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7e067-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7e067-156">Next steps</span></span>

- [<span data-ttu-id="7e067-157">Probar el punto de conexión de JEA</span><span class="sxs-lookup"><span data-stu-id="7e067-157">Test the JEA endpoint</span></span>](using-jea.md)
