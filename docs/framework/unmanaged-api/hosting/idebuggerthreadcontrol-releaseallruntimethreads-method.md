---
title: Metodo IDebuggerThreadControl::ReleaseAllRuntimeThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e6e2c4032a0765083177df9a6d7d5206448f566
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="4fc33-102">Metodo IDebuggerThreadControl::ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="4fc33-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="4fc33-103">Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread sono bloccati.</span><span class="sxs-lookup"><span data-stu-id="4fc33-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc33-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4fc33-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="4fc33-105">Note</span><span class="sxs-lookup"><span data-stu-id="4fc33-105">Remarks</span></span>  
 <span data-ttu-id="4fc33-106">Il `ReleaseAllRuntimeThreads` (metodo) non verrà mai chiamato su un thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="4fc33-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="4fc33-107">Se l'host dispone di un thread di runtime bloccato, è necessario rilasciare ora.</span><span class="sxs-lookup"><span data-stu-id="4fc33-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fc33-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4fc33-108">Requirements</span></span>  
 <span data-ttu-id="4fc33-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fc33-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fc33-110">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="4fc33-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fc33-111">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4fc33-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fc33-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fc33-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc33-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4fc33-113">See Also</span></span>  
 [<span data-ttu-id="4fc33-114">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="4fc33-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
