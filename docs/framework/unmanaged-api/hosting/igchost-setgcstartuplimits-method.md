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
ms.openlocfilehash: 365261883f0b81884bb7cf70614628c05f9067c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221007"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="e77f3-102">Metodo IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="e77f3-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="e77f3-103">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="e77f3-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e77f3-104">Inizia con il [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile impostare le dimensioni dei segmenti e dimensioni del numero massimo di generazioni 0 per i valori maggiori `DWORD` tramite il [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="e77f3-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e77f3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e77f3-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e77f3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e77f3-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="e77f3-107">[in] Le dimensioni del segmento usato dal sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e77f3-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="e77f3-108">[in] La dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="e77f3-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e77f3-109">Note</span><span class="sxs-lookup"><span data-stu-id="e77f3-109">Remarks</span></span>  
 <span data-ttu-id="e77f3-110">Il `SetGCStartupLimits` metodo può essere chiamato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="e77f3-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="e77f3-111">Questi valori non possono essere modificati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="e77f3-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e77f3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e77f3-112">Requirements</span></span>  
 <span data-ttu-id="e77f3-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e77f3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e77f3-114">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="e77f3-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e77f3-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e77f3-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e77f3-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e77f3-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e77f3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e77f3-117">See also</span></span>

- [<span data-ttu-id="e77f3-118">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="e77f3-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
