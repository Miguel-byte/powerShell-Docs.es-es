---
ms.date: 06/12/2017
keywords: wmf,powershell,setup
ms.openlocfilehash: ec4ae8e4b2ef0ec226cb75607f7aaf34b48f6b76
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62085650"
---
# <a name="authoring-improvements-using-powershell-ise"></a>Mejoras de creación mediante PowerShell ISE

La creación de configuraciones de DSC en Windows PowerShell ISE es mucho más fácil gracias a las siguientes mejoras:

- Para enumerar todos los recursos de DSC en un bloque de **configuración** o un bloque de **nodo**, escriba **Ctrl+Space** en una línea en blanco dentro de él.
- Finalización automática de propiedades de recurso de tipo **enumeración**.
- Finalización automática de la propiedad **DependsOn** de los recursos de DSC, en función de otras instancias de recurso de la configuración.
- Mejor finalización con tabulación de los valores de propiedad de recurso.

**Nota:** Debe tener una cadena vacía para los valores de propiedad de recurso para poder usar Ctrl+Space para mostrar las opciones. Presione **Tabulador** para recorrer las opciones.
