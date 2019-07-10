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
ms.openlocfilehash: c9104550438a2a066cdf052b8d6592e86b831194
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749992"
---
# <a name="igchostsetgcstartuplimits-method"></a><span data-ttu-id="47978-102">Metodo IGCHost::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="47978-102">IGCHost::SetGCStartupLimits Method</span></span>
<span data-ttu-id="47978-103">Imposta le dimensioni del segmento e le dimensioni massime per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="47978-103">Sets the segment size and the maximum size for generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47978-104">A partire da .NET Framework 4.5, è possibile impostare dimensioni segmento e del numero massimo di generazioni 0 per i valori maggiori `DWORD` usando il [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="47978-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47978-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="47978-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,  
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47978-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="47978-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="47978-107">[in] Le dimensioni del segmento usato dal sistema di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="47978-107">[in] The size of the segment used by the garbage collection system.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="47978-108">[in] La dimensione massima per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="47978-108">[in] The maximum size for generation 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47978-109">Note</span><span class="sxs-lookup"><span data-stu-id="47978-109">Remarks</span></span>  
 <span data-ttu-id="47978-110">Il `SetGCStartupLimits` metodo può essere chiamato una sola volta.</span><span class="sxs-lookup"><span data-stu-id="47978-110">The `SetGCStartupLimits` method may be called only once.</span></span> <span data-ttu-id="47978-111">Questi valori non possono essere modificati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="47978-111">These values cannot be changed later.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47978-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="47978-112">Requirements</span></span>  
 <span data-ttu-id="47978-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47978-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47978-114">**Intestazione:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="47978-114">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="47978-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="47978-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47978-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47978-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47978-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47978-117">See also</span></span>

- [<span data-ttu-id="47978-118">Interfaccia IGCHost</span><span class="sxs-lookup"><span data-stu-id="47978-118">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
