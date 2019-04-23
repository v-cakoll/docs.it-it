---
title: Interfaccia IDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a551d3cc6ab3dd3887f232018f8201de4036d1b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096836"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="baefc-102">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="baefc-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="baefc-103">Fornisce metodi per notificare all'host di blocco e sblocco dei thread per i servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="baefc-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="baefc-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="baefc-104">Methods</span></span>  
  
|<span data-ttu-id="baefc-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="baefc-105">Method</span></span>|<span data-ttu-id="baefc-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="baefc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="baefc-107">Metodo ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="baefc-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="baefc-108">Notifica all'host che riguarda il thread che sta inviando il callback al blocco all'interno di servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="baefc-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="baefc-109">Metodo ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="baefc-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="baefc-110">Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread bloccati.</span><span class="sxs-lookup"><span data-stu-id="baefc-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="baefc-111">Metodo StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="baefc-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="baefc-112">Notifica all'host che i servizi di debug stanno per avviare il blocco di tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="baefc-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="baefc-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="baefc-113">Requirements</span></span>  
 <span data-ttu-id="baefc-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baefc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baefc-115">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="baefc-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="baefc-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="baefc-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="baefc-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baefc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baefc-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baefc-118">See also</span></span>

- [<span data-ttu-id="baefc-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="baefc-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
