---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Método RemoveConfiguration
ms.openlocfilehash: aacbed96beb960d7e0d449423a4de9a27f0a287e
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734390"
---
# <a name="removeconfiguration-method"></a><span data-ttu-id="168ae-103">Método RemoveConfiguration</span><span class="sxs-lookup"><span data-stu-id="168ae-103">RemoveConfiguration method</span></span>

<span data-ttu-id="168ae-104">Quita los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="168ae-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="168ae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="168ae-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="168ae-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="168ae-106">Parameters</span></span>

<span data-ttu-id="168ae-107">*Stage* \[in\] Especifica qué documento de configuración quiere quitar.</span><span class="sxs-lookup"><span data-stu-id="168ae-107">*Stage* \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="168ae-108">Los valores siguientes son válidos:</span><span class="sxs-lookup"><span data-stu-id="168ae-108">The following values are valid:</span></span>

|<span data-ttu-id="168ae-109">Value</span><span class="sxs-lookup"><span data-stu-id="168ae-109">Value</span></span> |<span data-ttu-id="168ae-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="168ae-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="168ae-111">**1**</span><span class="sxs-lookup"><span data-stu-id="168ae-111">**1**</span></span> | <span data-ttu-id="168ae-112">Documento de configuración **Current** (current.mof).</span><span class="sxs-lookup"><span data-stu-id="168ae-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="168ae-113">**2**</span><span class="sxs-lookup"><span data-stu-id="168ae-113">**2**</span></span> | <span data-ttu-id="168ae-114">Documento de configuración **Pending** (pending.mof).</span><span class="sxs-lookup"><span data-stu-id="168ae-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="168ae-115">**4**</span><span class="sxs-lookup"><span data-stu-id="168ae-115">**4**</span></span> | <span data-ttu-id="168ae-116">Documento de configuración **Previous** (previous.mof).</span><span class="sxs-lookup"><span data-stu-id="168ae-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="168ae-117">*Force* \[in\] **true** para forzar la eliminación de la configuración.</span><span class="sxs-lookup"><span data-stu-id="168ae-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="168ae-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="168ae-118">Return value</span></span>

<span data-ttu-id="168ae-119">Devuelve cero si se ejecuta correctamente; de lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="168ae-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="168ae-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="168ae-120">Remarks</span></span>

<span data-ttu-id="168ae-121">Se trata de un método estático.</span><span class="sxs-lookup"><span data-stu-id="168ae-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="168ae-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="168ae-122">Requirements</span></span>

<span data-ttu-id="168ae-123">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="168ae-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="168ae-124">**Espacio de nombres**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="168ae-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="168ae-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="168ae-125">See also</span></span>

[<span data-ttu-id="168ae-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="168ae-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
