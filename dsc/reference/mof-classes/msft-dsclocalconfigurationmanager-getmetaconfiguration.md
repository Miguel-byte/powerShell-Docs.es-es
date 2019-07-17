---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Método GetMetaConfiguration
ms.openlocfilehash: bd280cb8ebd7b0522e4e01cbd24bd9bdcfddf4c2
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734433"
---
# <a name="getmetaconfiguration-method"></a><span data-ttu-id="c4e8e-103">Método GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="c4e8e-103">GetMetaConfiguration method</span></span>

<span data-ttu-id="c4e8e-104">Obtiene la configuración del Administrador de configuración local que se usa para controlar el agente de configuración.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="c4e8e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4e8e-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="c4e8e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4e8e-106">Parameters</span></span>

<span data-ttu-id="c4e8e-107">*MetaConfiguration* \[out\] En la devolución, contiene una instancia insertada de la clase **MSFT_DSCMetaConfiguration** que define la configuración.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="c4e8e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c4e8e-108">Return value</span></span>

<span data-ttu-id="c4e8e-109">Devuelve cero si se ejecuta correctamente; de lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4e8e-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c4e8e-110">Remarks</span></span>

<span data-ttu-id="c4e8e-111">Se trata de un método estático.</span><span class="sxs-lookup"><span data-stu-id="c4e8e-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c4e8e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4e8e-112">Requirements</span></span>

<span data-ttu-id="c4e8e-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="c4e8e-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="c4e8e-114">**Espacio de nombres**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="c4e8e-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="c4e8e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4e8e-115">See also</span></span>

[<span data-ttu-id="c4e8e-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="c4e8e-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
