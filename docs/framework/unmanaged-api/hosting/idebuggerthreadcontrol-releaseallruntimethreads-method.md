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
ms.openlocfilehash: 9ae1aa6590366468166916e6a92d0b356eb37c27
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133150"
---
# <a name="idebuggerthreadcontrolreleaseallruntimethreads-method"></a><span data-ttu-id="b5af5-102">Metodo IDebuggerThreadControl::ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="b5af5-102">IDebuggerThreadControl::ReleaseAllRuntimeThreads Method</span></span>
<span data-ttu-id="b5af5-103">Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread bloccati.</span><span class="sxs-lookup"><span data-stu-id="b5af5-103">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5af5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5af5-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseAllRuntimeThreads ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="b5af5-105">Note</span><span class="sxs-lookup"><span data-stu-id="b5af5-105">Remarks</span></span>  
 <span data-ttu-id="b5af5-106">Il metodo `ReleaseAllRuntimeThreads` non verrà mai chiamato su un thread runtime.</span><span class="sxs-lookup"><span data-stu-id="b5af5-106">The `ReleaseAllRuntimeThreads` method will never be called on a runtime thread.</span></span> <span data-ttu-id="b5af5-107">Se l'host dispone di un thread di runtime bloccato, dovrebbe rilasciarlo ora.</span><span class="sxs-lookup"><span data-stu-id="b5af5-107">If the host has a runtime thread blocked, it should release it now.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5af5-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5af5-108">Requirements</span></span>  
 <span data-ttu-id="b5af5-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5af5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5af5-110">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b5af5-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5af5-111">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b5af5-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5af5-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5af5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5af5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5af5-113">See also</span></span>

- [<span data-ttu-id="b5af5-114">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="b5af5-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
