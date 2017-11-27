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
ms.openlocfilehash: 7e3f8d04a47607958ff5d439b501a6de9bbc5b02
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerthreadcontrol-interface"></a><span data-ttu-id="11bc9-102">Interfaccia IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="11bc9-102">IDebuggerThreadControl Interface</span></span>
<span data-ttu-id="11bc9-103">Fornisce metodi per notificare all'host di blocco e sblocco dei thread per i servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="11bc9-103">Provides methods for notifying the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="11bc9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="11bc9-104">Methods</span></span>  
  
|<span data-ttu-id="11bc9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="11bc9-105">Method</span></span>|<span data-ttu-id="11bc9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11bc9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="11bc9-107">ThreadIsBlockingForDebugger (metodo)</span><span class="sxs-lookup"><span data-stu-id="11bc9-107">ThreadIsBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|<span data-ttu-id="11bc9-108">Notifica all'host che il thread che ha inviato questo callback sta per bloccare nei servizi di debug.</span><span class="sxs-lookup"><span data-stu-id="11bc9-108">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>|  
|[<span data-ttu-id="11bc9-109">ReleaseAllRuntimeThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="11bc9-109">ReleaseAllRuntimeThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|<span data-ttu-id="11bc9-110">Notifica all'host che i servizi di debug stanno per rilasciare tutti i thread sono bloccati.</span><span class="sxs-lookup"><span data-stu-id="11bc9-110">Notifies the host that the debugging services are about to release all threads that are blocked.</span></span>|  
|[<span data-ttu-id="11bc9-111">StartBlockingForDebugger (metodo)</span><span class="sxs-lookup"><span data-stu-id="11bc9-111">StartBlockingForDebugger Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|<span data-ttu-id="11bc9-112">Notifica all'host che i servizi di debug stanno per avviare il blocco di tutti i thread.</span><span class="sxs-lookup"><span data-stu-id="11bc9-112">Notifies the host that the debugging services are about to start blocking all threads.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="11bc9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11bc9-113">Requirements</span></span>  
 <span data-ttu-id="11bc9-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11bc9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11bc9-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="11bc9-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="11bc9-116">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11bc9-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="11bc9-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11bc9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11bc9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11bc9-118">See Also</span></span>  
 [<span data-ttu-id="11bc9-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="11bc9-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
