---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Información general sobre la configuración de estado deseado para responsables de toma de decisiones
ms.openlocfilehash: ce554d4bb994d4b1816d9d9c24599e4ef0e1c593
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62079598"
---
# <a name="desired-state-configuration-overview-for-decision-makers"></a>Información general sobre la configuración de estado deseado para responsables de toma de decisiones

En este documento se describen los beneficios de negocio del uso de la configuración de estado deseado (DSC) de Windows PowerShell. No se trata de una guía técnica.

## <a name="what-is-desired-state-configuration"></a>¿Qué es la configuración de estado deseado?

La configuración de estado deseado de PowerShell ofrece una plataforma de administración de configuración integrada en Windows que se basa en estándares abiertos. DSC es lo suficientemente flexible como para funcionar de forma confiable y coherente en cada una de las etapas del ciclo de vida de implementación (desarrollo, prueba, preproducción, producción), así como durante el escalado horizontal.

Centros de DSC alrededor de [configuraciones](../configurations/configurations.md).
Una configuración es un documento fácil de leer que describe un entorno compuesto por equipos ("nodos") con características específicas.
Estas características pueden ser tan sencillas como garantizar que una característica concreta de Windows está habilitada o tan complejas como la implementación de SharePoint.

DSC también tiene supervisión y generación de informes integradas.
Si un sistema ya no es conforme, DSC puede generar una alerta y actuar para corregir el sistema.

## <a name="benefits-of-using-desired-state-configuration"></a>Ventajas de usar la configuración de estado deseado

Las configuraciones están diseñadas para que se puedan leer, almacenar y actualizar fácilmente.
Las configuraciones declaran el estado en que deberían estar los dispositivos de destino, en lugar de escribir instrucciones sobre cómo hacer que lleguen a ese estado.
Esto permite que la configuración mediante DSC sea mucho menos costosa de aprender, adoptar, implementar y mantener.

La creación de configuraciones implica que se capturen los pasos de implementación complejos como un "origen único de verdad" en una ubicación única.
Esto hace que las implementaciones repetidas de un conjunto concreto de máquinas sean mucho menos propensas a errores.
A su vez, hace que las implementaciones sean más rápidas y confiables, lo que permite un tiempo de entrega rápido en las implementaciones complejas.

Las configuraciones también se pueden compartir mediante la [Galería de PowerShell](https://powershellgallery.com), lo que significa que es posible que ya existan escenarios comunes y procedimientos recomendados para el trabajo que hay que realizar.


## <a name="desired-state-configuration-and-devops"></a>Configuración de estado deseado y DevOps

DSC se diseñó pensando en [DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx), una combinación de personas, procesos y herramientas que permiten una rápida implementación e iteración centrada en la entrega de valor a los usuarios finales, ya sean internos o externos.
Que una sola configuración defina un entorno significa que los desarrolladores pueden codificar sus requisitos en una configuración, incorporar esa configuración en el control de código fuente, y los equipos de operaciones pueden implementar fácilmente el código sin tener que realizar procesos manuales propensos a errores.

Las configuraciones también están [controladas por datos](../configurations/configData.md), lo que facilita que los equipos de operaciones identifiquen y cambien los entornos sin intervención del programador.

## <a name="desired-state-configuration-on-premises-and-off-premises"></a>Instancia de Desired State Configuration local y remota
DSC se puede utilizar para administrar implementaciones locales y remotas.
Para las soluciones locales, DSC tiene un [servidor de extracción](../pull-server/pullServer.md) que puede utilizarse para centralizar la administración de máquinas e informar sobre su estado.
Para las soluciones de nube, DSC se puede utilizar siempre que se pueda usar Windows.
También hay ofertas específicas de Azure basadas en la configuración de estado deseado, como [Azure Automation](https://azure.microsoft.com/en-us/documentation/services/automation/), que centraliza la creación de informes de DSC.

## <a name="dsc-and-compatibility"></a>DSC y la compatibilidad

Aunque DSC se introdujo en Windows Server 2012 R2, está disponible para los sistemas operativos inferiores mediante el paquete Windows Management Framework (WMF).
Puede encontrar más información sobre WMF en la [página principal de PowerShell](/powershell/).

DSC también se puede usar para administrar Linux. Para más información, consulte [Introducción a la configuración de estado deseado (DSC) para Linux](../getting-started/lnxGettingStarted.md).
