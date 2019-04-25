---
ms.date: 06/12/2017
keywords: wmf,powershell,setup
ms.openlocfilehash: 0bc085588190f134c4a687c952509aa256b5f840
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085208"
---
# <a name="just-enough-administration-jea"></a>Just Enough Administration (JEA)
Just Enough Administration es una nueva característica de WMF 5.0 que permite la administración basada en roles a través de la comunicación remota de PowerShell.  Amplía la infraestructura existente de punto de conexión restringida existente. Para hacerlo, permite que usuarios no administradores ejecuten comandos específicos, scripts y ejecutables como administrador.  Esto permite reducir el número de administradores totales en su entorno y mejorar su seguridad.  JEA funciona para todo lo que se administra a través de PowerShell; si puede administrar algo con PowerShell, JEA puede ayudarle a hacerlo de forma más segura.  Para obtener una visión detallada de Just Enough Administration, consulte la [guía de experiencias](http://aka.ms/JEA).

A diferencia de los puntos de conexión extremos restringidos antiguos, JEA es eficaz y fácil de configurar.  Las funcionalidades de usuario en JEA pueden controlarse de forma pormenorizada, hasta restringir los conjuntos de parámetros y los valores que se pueden proporcionar a un comando específico. Las acciones del usuario se ejecutan en el contexto de una cuenta virtual única que tiene derechos para realizar las acciones de administrador.  Los comandos que invoca el usuario se pueden registrar para auditorías de seguridad.

Para funcionar, JEA le permite crear puntos de conexión restringidos con una configuración especial.  Estos puntos de conexión tienen algunas características importantes:

1. Los usuarios que se conectan a ellos se "ejecutan como" una cuenta virtual con privilegios que existe mientras dure esta sesión remota.  De forma predeterminada, esta cuenta virtual es miembro del grupo de administradores integrado, así como un administrador de dominio en los controladores de dominio (Nota: Estos permisos son configurables). Al conectarse como un usuario y ejecutarse como un usuario con privilegios diferente, puede permitir que usuarios sin privilegios realicen tareas administrativas específicas sin concederles derechos administrativos en sus sistemas.
2. El punto de conexión está bloqueado.  Esto significa que PowerShell se ejecuta en modo sin lenguaje.  Solo determinados comandos, scripts y ejecutables son visibles para el usuario.
3. A los distintos usuarios que se conectan se les presenta un conjunto diferente de funcionalidades según la pertenencia a grupos.  Puede proporcionar a distintos roles distintas funcionalidades en el mismo punto de conexión.
