---
title: Metodo IGCHost::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- IGCHost.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbe94aa67c9cf9ac587b7fca9f5cbeca4870506b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437209"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="8b9d5-102">Metodo IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="8b9d5-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="8b9d5-103">Imposta le dimensioni del segmento e la dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="8b9d5-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8b9d5-104">A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile impostare una dimensione del segmento e dimensione massima di generazione 0 a valori maggiori di `DWORD` utilizzando il [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="8b9d5-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b9d5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b9d5-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b9d5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b9d5-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="8b9d5-107">[in] Dimensione del segmento utilizzata dal sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="8b9d5-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="8b9d5-108">[in] La dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="8b9d5-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b9d5-109">Note</span><span class="sxs-lookup"><span data-stu-id="8b9d5-109">Remarks</span></span>  
 <span data-ttu-id="8b9d5-110">Il `SetGCStartupLimits` metodo può essere chiamato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="8b9d5-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="8b9d5-111">Questi valori non possono essere modificati successivamente.</span><span class="sxs-lookup"><span data-stu-id="8b9d5-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b9d5-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b9d5-112">Requirements</span></span>  
 <span data-ttu-id="8b9d5-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b9d5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b9d5-114">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="8b9d5-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8b9d5-115">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8b9d5-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b9d5-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b9d5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b9d5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b9d5-117">See Also</span></span>  
 [<span data-ttu-id="8b9d5-118">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="8b9d5-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
