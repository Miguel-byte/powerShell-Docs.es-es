---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Método TestConfiguration de la clase MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: d746832b01310f43a7aae33dd0fa70c0928bb3e0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078085"
---
# <a name="testconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="fd141-103">Método TestConfiguration de la clase MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="fd141-103">TestConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="fd141-104">Envía el documento de configuración al nodo administrado y prueba la configuración actual frente al documento.</span><span class="sxs-lookup"><span data-stu-id="fd141-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd141-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd141-105">Syntax</span></span>

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a><span data-ttu-id="fd141-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd141-106">Parameters</span></span>

<span data-ttu-id="fd141-107">*configurationData* \[in\] Datos del entorno para la configuración.</span><span class="sxs-lookup"><span data-stu-id="fd141-107">*configurationData* \[in\] Environment data for the confuguration.</span></span>

<span data-ttu-id="fd141-108">*InDesiredState* \[out\] En la devolución, especifica si el nodo administrado está en el estado especificado por el documento de configuración.</span><span class="sxs-lookup"><span data-stu-id="fd141-108">*InDesiredState* \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="fd141-109">*ResourcesInDesiredState* \[out\] En la devolución, contiene una instancia insertada de la clase **MSFT_ResourceInDesiredState**, que especifica los recursos que están en el estado deseado.</span><span class="sxs-lookup"><span data-stu-id="fd141-109">*ResourcesInDesiredState* \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="fd141-110">*ResourcesNotInDesiredState* \[out\] En la devolución, contiene una instancia insertada de la clase **MSFT_ResourceNotInDesiredState**, que especifica los recursos que no están en el estado deseado.</span><span class="sxs-lookup"><span data-stu-id="fd141-110">*ResourcesNotInDesiredState* \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="fd141-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd141-111">Return value</span></span>

<span data-ttu-id="fd141-112">Devuelve cero si se ejecuta correctamente; de lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="fd141-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd141-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fd141-113">Remarks</span></span>

<span data-ttu-id="fd141-114">Se trata de un método estático.</span><span class="sxs-lookup"><span data-stu-id="fd141-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd141-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd141-115">Requirements</span></span>

<span data-ttu-id="fd141-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="fd141-116">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="fd141-117">**Espacio de nombres**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="fd141-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="fd141-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd141-118">See also</span></span>

[<span data-ttu-id="fd141-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="fd141-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)