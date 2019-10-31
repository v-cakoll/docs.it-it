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
ms.openlocfilehash: 3593e4d68058a1820f575c92ff9571d43560316a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133924"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="cb70f-102">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="cb70f-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="cb70f-103">Definisce i metodi che consentono all'host di ottenere informazioni sulle attività richieste e di rilevare i deadlock nell'implementazione della sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="cb70f-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb70f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cb70f-104">Methods</span></span>  
  
|<span data-ttu-id="cb70f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cb70f-105">Method</span></span>|<span data-ttu-id="cb70f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb70f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb70f-107">Metodo CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="cb70f-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="cb70f-108">Richiede che il Common Language Runtime (CLR) crei un iteratore per l'host da utilizzare per determinare il set di attività in attesa di un blocco in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="cb70f-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="cb70f-109">Metodo DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="cb70f-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="cb70f-110">Richiede che CLR elimini un iteratore creato da una chiamata a `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="cb70f-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="cb70f-111">Metodo GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="cb70f-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="cb70f-112">Ottiene l'attività che possiede il monitor specificato.</span><span class="sxs-lookup"><span data-stu-id="cb70f-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="cb70f-113">Metodo GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="cb70f-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="cb70f-114">Ottiene l'attività successiva in attesa del blocco di lettura/scrittura corrente.</span><span class="sxs-lookup"><span data-stu-id="cb70f-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb70f-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb70f-115">Requirements</span></span>  
 <span data-ttu-id="cb70f-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb70f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb70f-117">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cb70f-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb70f-118">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cb70f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb70f-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb70f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb70f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb70f-120">See also</span></span>

- <xref:System.Threading.Thread>
- [<span data-ttu-id="cb70f-121">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="cb70f-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <span data-ttu-id="cb70f-122">[Threading gestito e non gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cb70f-122">[Managed and Unmanaged Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>
- [<span data-ttu-id="cb70f-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="cb70f-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
