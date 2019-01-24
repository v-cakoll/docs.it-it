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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eaf5a0061b068d9adea3f6aeb28f9b6bb20c3174
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710255"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="b3268-102">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="b3268-102">IHostGCManager Interface</span></span>
<span data-ttu-id="b3268-103">Fornisce metodi per notificare all'host gli eventi nel meccanismo di garbage collection implementato da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="b3268-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="b3268-104">Membri</span><span class="sxs-lookup"><span data-stu-id="b3268-104">Members</span></span>  
  
|<span data-ttu-id="b3268-105">Membro</span><span class="sxs-lookup"><span data-stu-id="b3268-105">Member</span></span>|<span data-ttu-id="b3268-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3268-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3268-107">Metodo SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="b3268-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="b3268-108">Notifica all'host che CLR viene ripresa l'esecuzione delle attività nei thread che erano stati sospesi per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b3268-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="b3268-109">Metodo SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="b3268-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="b3268-110">Notifica all'host che Common Language Runtime sta per sospendere l'esecuzione di attività, per eseguire un'operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b3268-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="b3268-111">Metodo ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="b3268-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="b3268-112">Notifica all'host che è il thread da cui è stata effettuata la chiamata al metodo per essere bloccato per una garbage collection.</span><span class="sxs-lookup"><span data-stu-id="b3268-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3268-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3268-113">Requirements</span></span>  
 <span data-ttu-id="b3268-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3268-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3268-115">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b3268-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3268-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b3268-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3268-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3268-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3268-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3268-118">See also</span></span>
- [<span data-ttu-id="b3268-119">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b3268-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b3268-120">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b3268-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b3268-121">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="b3268-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b3268-122">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b3268-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="b3268-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="b3268-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
