---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: Método ResourceTest de la clase MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: e7645b0c6b93b96cb01f72c1c92d468f7642ea13
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078561"
---
# <a name="resourcetest-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="e4aa2-103">Método ResourceTest de la clase MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="e4aa2-103">ResourceTest method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="e4aa2-104">Llama directamente al método **Test** de un recurso de DSC.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-104">Directly calls the **Test** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="e4aa2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4aa2-105">Syntax</span></span>

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a><span data-ttu-id="e4aa2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4aa2-106">Parameters</span></span>

<span data-ttu-id="e4aa2-107">*ResourceType* \[in\] Nombre del recurso al que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="e4aa2-108">*ModuleName* \[in\] Nombre del módulo que contiene el recurso al que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="e4aa2-109">*resourceProperty* \[in\] Especifica el nombre de la propiedad del recurso y su valor en una tabla hash como clave y valor, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="e4aa2-110">Use el cmdlet [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) para descubrir las propiedades del recurso y sus tipos.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="e4aa2-111">*InDesiredState* \[out\] En la devolución, esta propiedad se establece en **true** si el nodo de destino está en el estado deseado.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-111">*InDesiredState* \[out\] On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="e4aa2-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e4aa2-112">Return value</span></span>

<span data-ttu-id="e4aa2-113">Devuelve cero si se ejecuta correctamente; de lo contrario, devuelve un código de error.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4aa2-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e4aa2-114">Remarks</span></span>

<span data-ttu-id="e4aa2-115">Se trata de un método estático.</span><span class="sxs-lookup"><span data-stu-id="e4aa2-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e4aa2-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4aa2-116">Requirements</span></span>

<span data-ttu-id="e4aa2-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="e4aa2-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="e4aa2-118">**Espacio de nombres**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="e4aa2-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="e4aa2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4aa2-119">See also</span></span>

[<span data-ttu-id="e4aa2-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="e4aa2-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)