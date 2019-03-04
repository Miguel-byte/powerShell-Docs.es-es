---
title: Crea el archivo Web.config para un servicio web de IIS Management OData | Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d569f5d5-9746-40c0-be5e-f218bc4560f7
caps.latest.revision: 4
ms.openlocfilehash: f52953ee091f05df5f355719ecba788d3d5ee055
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856721"
---
# <a name="authoring-the-webconfig-file-for-a-management-odata-web-service"></a>Creación del archivo Web.config para un servicio web de Management OData

Antes de implementar el servicio web de IIS Management OData, debe configurar el archivo web.config para que apunte a los archivos de esquema XML y los archivos DLL que implementan la [Microsoft.Management.Odata.Customauthorization](/dotnet/api/Microsoft.Management.Odata.CustomAuthorization) y [ System.Management.Automation.Remoting.Pssessionconfiguration](/dotnet/api/System.Management.Automation.Remoting.PSSessionConfiguration) interfaces.

## <a name="sample-config-file"></a>Archivo de configuración de ejemplo

El siguiente es un ejemplo del aspecto del archivo web.config para el servicio web.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
   <configSections>
      <section name="managementOdata" type="Microsoft.Management.Odata.Core.DSConfiguration, Microsoft.Management.OData, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL" />
   </configSections>
   <managementOdata schemaFileName="Schema.mof" resourceMappingFileName="Schema.xml">
      <customAuthorization type="Microsoft.Samples.Management.OData.RoleBasedPlugins.CustomAuthorization" assembly=".\Microsoft.Samples.Management.OData.RoleBasedPlugins.dll" />
      <powershell>
         <sessionConfiguration type="Microsoft.Samples.Management.OData.RoleBasedPlugins.SessionConfiguration" assembly=".\Microsoft.Samples.Management.OData.RoleBasedPlugins.dll" />
      </powershell>
      <commandInvocation enabled="true" />
      <wcfDataServicesConfig>
      </wcfDataServicesConfig>
   </managementOdata>
   <system.serviceModel>
      <behaviors>
         <serviceBehaviors>
            <behavior>
                  <serviceAuthorization serviceAuthorizationManagerType="Microsoft.Management.Odata.Core.CustomAuthorizationManager, Microsoft.Management.OData, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
            </behavior>
         </serviceBehaviors>
      </behaviors>
      <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
   </system.serviceModel>
   <system.webServer>
      <security>
         <authentication>
            <anonymousAuthentication enabled="false" />
            <basicAuthentication enabled="true" />
            <windowsAuthentication enabled="false" />
         </authentication>
      </security>
  </system.webServer>
</configuration>

```

## <a name="see-also"></a>Véase también

[Implementación de la autorización personalizada para un servicio web de IIS Management OData](./implementing-custom-authorization-for-a-management-odata-web-service.md)

[Implementación de Configuracióndesesión para un servicio web de IIS Management OData](./implementing-sessionconfiguration-for-a-management-odata-web-service.md)

[Crea el archivo de esquema MOF para un servicio web de IIS Management OData](./authoring-the-mof-schema-file-for-a-management-odata-web-service.md)

[Crea el archivo de esquema XML para un servicio web de IIS Management OData](./authoring-the-xml-schema-file-for-a-management-odata-web-service.md)

[Creación de un servicio de administración Web de OData](./creating-a-management-odata-web-service.md)