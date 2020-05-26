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
ms.openlocfilehash: 428e4cf8997713b08e40d9376c34ae5eee8cfa32
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804849"
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="84a4d-102">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="84a4d-102">IHostGCManager Interface</span></span>
<span data-ttu-id="84a4d-103">Fornisce metodi che notificano all'host degli eventi nel meccanismo di Garbage Collection implementato dall'Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="84a4d-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="84a4d-104">Membri</span><span class="sxs-lookup"><span data-stu-id="84a4d-104">Members</span></span>  
  
|<span data-ttu-id="84a4d-105">Membro</span><span class="sxs-lookup"><span data-stu-id="84a4d-105">Member</span></span>|<span data-ttu-id="84a4d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84a4d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84a4d-107">Metodo SuspensionEnding</span><span class="sxs-lookup"><span data-stu-id="84a4d-107">SuspensionEnding Method</span></span>](ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="84a4d-108">Notifica all'host che CLR sta riprendendo l'esecuzione delle attività nei thread che sono stati sospesi per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="84a4d-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="84a4d-109">Metodo SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="84a4d-109">SuspensionStarting Method</span></span>](ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="84a4d-110">Notifica all'host che CLR sta sospendendo l'esecuzione delle attività, per eseguire un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="84a4d-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="84a4d-111">Metodo ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="84a4d-111">ThreadIsBlockingForSuspension Method</span></span>](ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="84a4d-112">Notifica all'host che il thread da cui è stata effettuata la chiamata al metodo sta per essere bloccato per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="84a4d-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84a4d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84a4d-113">Requirements</span></span>  
 <span data-ttu-id="84a4d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84a4d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a4d-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="84a4d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84a4d-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84a4d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84a4d-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a4d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a4d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84a4d-118">See also</span></span>

- [<span data-ttu-id="84a4d-119">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="84a4d-119">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="84a4d-120">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="84a4d-120">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="84a4d-121">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="84a4d-121">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="84a4d-122">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="84a4d-122">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="84a4d-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="84a4d-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
