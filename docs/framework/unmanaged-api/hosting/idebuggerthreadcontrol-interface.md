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
ms.openlocfilehash: 619a28d2382aa9cc3130a3130c07fa1e283119e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437915"
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="89269-102">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="89269-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="89269-103">Fornisce metodi per notificare all'host di blocco e sblocco dei thread per i servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="89269-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="89269-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="89269-104">Methods</span></span>  
  
|<span data-ttu-id="89269-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="89269-105">Method</span></span>|<span data-ttu-id="89269-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89269-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="89269-107">Metodo ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="89269-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="89269-108">Notifica all'host che il thread che ha inviato questo callback sta per bloccare nei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="89269-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="89269-109">Metodo ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="89269-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="89269-110">Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread sono bloccati.</span><span class="sxs-lookup"><span data-stu-id="89269-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="89269-111">Metodo StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="89269-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="89269-112">Notifica all'host che i servizi di debug stanno per avviare il blocco di tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="89269-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89269-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89269-113">Requirements</span></span>  
 <span data-ttu-id="89269-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89269-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89269-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="89269-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89269-116">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="89269-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89269-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89269-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89269-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89269-118">See Also</span></span>  
 [<span data-ttu-id="89269-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="89269-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
