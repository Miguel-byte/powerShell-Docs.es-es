---
ms.date: 06/12/2017
keywords: wmf,powershell,setup
ms.openlocfilehash: 7a1725e3858c59a6d31699add22b042359c48463
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058206"
---
# <a name="separation-of-node-and-configuration-ids"></a>Separación de los identificadores de nodo y de configuración

## <a name="overview"></a>Introducción

Con el fin de proporcionar una experiencia más flexible y simplificada al usar DSC en modo de extracción, hemos agregado una serie de características en esta versión. Estas características están diseñadas para que pueda tener la flexibilidad de configurar e implementar con facilidad las configuraciones en varios nodos, y seguir realizando el seguimiento de la información de estado y generación de informes de cada nodo individualmente.
Estas características son:

* Un nombre de configuración que identifica la configuración de un equipo. Este nombre pueden compartirlo varios nodos de destino.
* Un identificador de agente que identifica de forma única un solo nodo.
* Un paso de registro que solo se produce la primera vez que un nodo de destino se conecta a un servidor de extracción.

**Nota:** Estas características y funciones se han agregado, pero no reemplazan los conceptos ni las características de extracción existentes. Puede usar estas nuevas características o las anteriores con el nuevo servidor de extracción que se incluye en esta versión.

Para más información, consulte [Configuración de un cliente de extracción mediante nombres de configuración](https://msdn.microsoft.com/powershell/dsc/pullclientconfignames)
