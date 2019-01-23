---
title: Metodo IDebuggerThreadControl::ReleaseAllRuntimeThreads
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5e2501a5ab62c6aaef2b3f754f9eed10e4e4b97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505023"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="85109-102">Metodo IDebuggerThreadControl::ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="85109-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="85109-103">Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread bloccati.</span><span class="sxs-lookup"><span data-stu-id="85109-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85109-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85109-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="85109-105">Note</span><span class="sxs-lookup"><span data-stu-id="85109-105">Remarks</span></span>  
 <span data-ttu-id="85109-106">Il `ReleaseAllRuntimeThreads` (metodo) non verrà mai chiamato su un thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="85109-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="85109-107">Se l'host dispone di un thread di runtime bloccato, deve rilasciare ora.</span><span class="sxs-lookup"><span data-stu-id="85109-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85109-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85109-108">Requirements</span></span>  
 <span data-ttu-id="85109-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85109-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85109-110">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85109-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85109-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="85109-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85109-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85109-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85109-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85109-113">See also</span></span>
- [<span data-ttu-id="85109-114">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="85109-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
