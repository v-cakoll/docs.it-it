---
title: Metodo IDebuggerThreadControl::ReleaseAllRuntimeThreads
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl.ReleaseAllRuntimeThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: ReleaseAllRuntimeThreads
helpviewer_keywords:
- ReleaseAllRuntimeThreads method [.NET Framework hosting]
- IDebuggerThreadControl::ReleaseAllRuntimeThreads method [.NET Framework hosting]
ms.assetid: 1a2995ff-5f02-4b49-84dc-3a5f9cfd7d55
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a087dbcff961ca1ac1cf03d30fdc336ec9ca0515
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="2bf10-102">Metodo IDebuggerThreadControl::ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="2bf10-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="2bf10-103">Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread sono bloccati.</span><span class="sxs-lookup"><span data-stu-id="2bf10-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bf10-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2bf10-104">Syntax</span></span>  
  
```  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="2bf10-105">Note</span><span class="sxs-lookup"><span data-stu-id="2bf10-105">Remarks</span></span>  
 <span data-ttu-id="2bf10-106">Il `ReleaseAllRuntimeThreads` (metodo) non verrà mai chiamato su un thread di runtime.</span><span class="sxs-lookup"><span data-stu-id="2bf10-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="2bf10-107">Se l'host dispone di un thread di runtime bloccato, è necessario rilasciare ora.</span><span class="sxs-lookup"><span data-stu-id="2bf10-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bf10-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2bf10-108">Requirements</span></span>  
 <span data-ttu-id="2bf10-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bf10-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bf10-110">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="2bf10-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bf10-111">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2bf10-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bf10-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bf10-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf10-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bf10-113">See Also</span></span>  
 [<span data-ttu-id="2bf10-114">IDebuggerThreadControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2bf10-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
