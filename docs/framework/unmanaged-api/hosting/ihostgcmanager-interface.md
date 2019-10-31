---
title: Interfaccia IHostGCManager
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: 6f7158bcac7ad22647104e2041da959285d2be8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130486"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="d473a-102">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="d473a-102">IHostGCManager Interface</span></span>
<span data-ttu-id="d473a-103">Fornisce metodi che notificano all'host degli eventi nel meccanismo di Garbage Collection implementato dall'Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d473a-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="d473a-104">Members</span><span class="sxs-lookup"><span data-stu-id="d473a-104">Members</span></span>  
  
|<span data-ttu-id="d473a-105">Member</span><span class="sxs-lookup"><span data-stu-id="d473a-105">Member</span></span>|<span data-ttu-id="d473a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d473a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d473a-107">Metodo SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="d473a-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="d473a-108">Notifica all'host che CLR sta riprendendo l'esecuzione delle attività nei thread che sono stati sospesi per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d473a-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="d473a-109">Metodo SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="d473a-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="d473a-110">Notifica all'host che CLR sta sospendendo l'esecuzione delle attività, per eseguire un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d473a-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="d473a-111">Metodo ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="d473a-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="d473a-112">Notifica all'host che il thread da cui è stata effettuata la chiamata al metodo sta per essere bloccato per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d473a-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d473a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d473a-113">Requirements</span></span>  
 <span data-ttu-id="d473a-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d473a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d473a-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d473a-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d473a-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d473a-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d473a-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d473a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d473a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d473a-118">See also</span></span>

- [<span data-ttu-id="d473a-119">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="d473a-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="d473a-120">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d473a-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="d473a-121">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="d473a-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="d473a-122">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="d473a-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="d473a-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="d473a-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
