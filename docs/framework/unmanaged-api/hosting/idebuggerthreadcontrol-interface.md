---
title: Interfaccia IDebuggerThreadControl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl
api_location: mscoree.dll
api_type: COM
f1_keywords: IDebuggerThreadControl
helpviewer_keywords: IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 297a66f9466b00dec4d32f7d8a6e2bd13b6e5655
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="be739-102">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="be739-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="be739-103">Fornisce metodi per notificare all'host di blocco e sblocco dei thread per i servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="be739-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="be739-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="be739-104">Methods</span></span>  
  
|<span data-ttu-id="be739-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="be739-105">Method</span></span>|<span data-ttu-id="be739-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be739-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="be739-107">Metodo ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="be739-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="be739-108">Notifica all'host che il thread che ha inviato questo callback sta per bloccare nei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="be739-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="be739-109">Metodo ReleaseAllRuntimeThreads</span><span class="sxs-lookup"><span data-stu-id="be739-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="be739-110">Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread sono bloccati.</span><span class="sxs-lookup"><span data-stu-id="be739-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="be739-111">Metodo StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="be739-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="be739-112">Notifica all'host che i servizi di debug stanno per avviare il blocco di tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="be739-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be739-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be739-113">Requirements</span></span>  
 <span data-ttu-id="be739-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be739-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be739-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="be739-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="be739-116">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="be739-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be739-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be739-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be739-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be739-118">See Also</span></span>  
 [<span data-ttu-id="be739-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="be739-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
