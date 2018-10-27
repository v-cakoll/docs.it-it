---
title: Interfaccia ICLRSyncManager
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ede896cdb93217fcfba9d66ed7102bcc1ba762e9
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50041830"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="504d9-102">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="504d9-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="504d9-103">Definisce i metodi che consentono all'host per ottenere informazioni sulle attività di richiesta e per rilevare i deadlock nell'implementazione della sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="504d9-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="504d9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="504d9-104">Methods</span></span>  
  
|<span data-ttu-id="504d9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="504d9-105">Method</span></span>|<span data-ttu-id="504d9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="504d9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="504d9-107">Metodo CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="504d9-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="504d9-108">Richieste che common language runtime (CLR) crea un iteratore per l'host da usare per determinare il set di attività in attesa di un blocco di lettura / scrittura.</span><span class="sxs-lookup"><span data-stu-id="504d9-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="504d9-109">Metodo DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="504d9-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="504d9-110">Richiede a CLR di eliminare un iteratore che è stato creato da una chiamata a `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="504d9-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="504d9-111">Metodo GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="504d9-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="504d9-112">Ottiene l'attività che possiede il monitoraggio specificato.</span><span class="sxs-lookup"><span data-stu-id="504d9-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="504d9-113">Metodo GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="504d9-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="504d9-114">Ottiene l'attività successiva in attesa di blocco in lettura-scrittura corrente.</span><span class="sxs-lookup"><span data-stu-id="504d9-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="504d9-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="504d9-115">Requirements</span></span>  
 <span data-ttu-id="504d9-116">**Piattaforme:** vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="504d9-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="504d9-117">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="504d9-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="504d9-118">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="504d9-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="504d9-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="504d9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="504d9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="504d9-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="504d9-121">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="504d9-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="504d9-122">[Threading gestito e non gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="504d9-122">[Managed and Unmanaged Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>  
 [<span data-ttu-id="504d9-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="504d9-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
