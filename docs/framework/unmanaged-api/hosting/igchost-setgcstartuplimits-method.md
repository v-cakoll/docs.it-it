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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993265"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="65e76-102">Metodo IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="65e76-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="65e76-103">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="65e76-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="65e76-104">Inizia con il [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile impostare le dimensioni dei segmenti e dimensioni del numero massimo di generazioni 0 per i valori maggiori `DWORD` tramite il [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="65e76-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65e76-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65e76-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65e76-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="65e76-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="65e76-107">[in] Le dimensioni del segmento usato dal sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="65e76-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="65e76-108">[in] La dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="65e76-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65e76-109">Note</span><span class="sxs-lookup"><span data-stu-id="65e76-109">Remarks</span></span>  
 <span data-ttu-id="65e76-110">Il `SetGCStartupLimits` metodo può essere chiamato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="65e76-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="65e76-111">Questi valori non possono essere modificati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="65e76-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65e76-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65e76-112">Requirements</span></span>  
 <span data-ttu-id="65e76-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65e76-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65e76-114">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="65e76-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="65e76-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="65e76-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65e76-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65e76-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65e76-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65e76-117">See also</span></span>

- [<span data-ttu-id="65e76-118">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="65e76-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
