---
title: Metodo IGCHost2::SetGCStartupLimitsEx
ms.date: 03/30/2017
api_name:
- IGCHost2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2::SetGCStartupLimitsEx
helpviewer_keywords:
- IGCHost2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, IGCHost2 interface [.NET Framework hosting]
ms.assetid: bba941c2-1c57-46d3-bbf5-5fb92700c490
topic_type:
- apiref
ms.openlocfilehash: d78f81093e61c40eaec334f957d8583eeb593f5e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134809"
---
# <a name="igchost2setgcstartuplimitsex-method"></a><span data-ttu-id="58828-102">Metodo IGCHost2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="58828-102">IGCHost2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="58828-103">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="58828-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58828-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58828-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,  
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58828-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58828-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="58828-106">in Dimensioni del segmento utilizzato dal sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="58828-106">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="58828-107">in Dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="58828-107">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58828-108">Note</span><span class="sxs-lookup"><span data-stu-id="58828-108">Remarks</span></span>  
 <span data-ttu-id="58828-109">È possibile specificare i valori che `SetGCStartupLimitsEx` imposta solo prima dell'avvio dell'host.</span><span class="sxs-lookup"><span data-stu-id="58828-109">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="58828-110">Questi valori non possono essere modificati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="58828-110">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58828-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58828-111">Requirements</span></span>  
 <span data-ttu-id="58828-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58828-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58828-113">**Intestazione:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="58828-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="58828-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="58828-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="58828-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58828-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58828-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58828-116">See also</span></span>

- [<span data-ttu-id="58828-117">Interfaccia IGCHost2</span><span class="sxs-lookup"><span data-stu-id="58828-117">IGCHost2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-interface.md)
