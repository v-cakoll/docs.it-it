---
title: Metodo IGCHost::SetGCStartupLimits
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.SetGCStartupLimits
api_location: mscoree.dll
api_type: COM
f1_keywords: SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, IGCHost interface [.NET Framework hosting]
- IGCHost::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: cae53926-82ac-4d1d-b297-0bde0bd1bebb
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f95e5afa1297602e4ef12ed0dfb3f98aa5c762ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="b130c-102">Metodo IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="b130c-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="b130c-103">Imposta le dimensioni del segmento e la dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="b130c-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b130c-104">A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile impostare una dimensione del segmento e dimensione massima di generazione 0 a valori maggiori di `DWORD` utilizzando il [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="b130c-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b130c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b130c-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b130c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b130c-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="b130c-107">[in] Dimensione del segmento utilizzata dal sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b130c-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="b130c-108">[in] La dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="b130c-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b130c-109">Note</span><span class="sxs-lookup"><span data-stu-id="b130c-109">Remarks</span></span>  
 <span data-ttu-id="b130c-110">Il `SetGCStartupLimits` metodo può essere chiamato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="b130c-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="b130c-111">Questi valori non possono essere modificati successivamente.</span><span class="sxs-lookup"><span data-stu-id="b130c-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b130c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b130c-112">Requirements</span></span>  
 <span data-ttu-id="b130c-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b130c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b130c-114">**Intestazione:** GCHost. idl, GCHost. H</span><span class="sxs-lookup"><span data-stu-id="b130c-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b130c-115">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b130c-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b130c-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b130c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b130c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b130c-117">See Also</span></span>  
 [<span data-ttu-id="b130c-118">IGCHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="b130c-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
