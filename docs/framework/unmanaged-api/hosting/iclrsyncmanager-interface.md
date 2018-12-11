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
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129324"
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="a0209-102">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a0209-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="a0209-103">Definisce i metodi che consentono all'host per ottenere informazioni sulle attività di richiesta e per rilevare i deadlock nell'implementazione della sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="a0209-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0209-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a0209-104">Methods</span></span>  
  
|<span data-ttu-id="a0209-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a0209-105">Method</span></span>|<span data-ttu-id="a0209-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0209-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0209-107">Metodo CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="a0209-107">CreateRWLockOwnerIterator Method</span></span>](iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="a0209-108">Richieste che common language runtime (CLR) crea un iteratore per l'host da usare per determinare il set di attività in attesa di un blocco di lettura / scrittura.</span><span class="sxs-lookup"><span data-stu-id="a0209-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="a0209-109">Metodo DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="a0209-109">DeleteRWLockOwnerIterator Method</span></span>](iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="a0209-110">Richiede a CLR di eliminare un iteratore che è stato creato da una chiamata a `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="a0209-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="a0209-111">Metodo GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="a0209-111">GetMonitorOwner Method</span></span>](iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="a0209-112">Ottiene l'attività che possiede il monitoraggio specificato.</span><span class="sxs-lookup"><span data-stu-id="a0209-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="a0209-113">Metodo GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="a0209-113">GetRWLockOwnerNext Method</span></span>](iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="a0209-114">Ottiene l'attività successiva in attesa di blocco in lettura-scrittura corrente.</span><span class="sxs-lookup"><span data-stu-id="a0209-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a0209-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0209-115">Requirements</span></span>  
 <span data-ttu-id="a0209-116">**Piattaforme:** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0209-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0209-117">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a0209-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0209-118">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a0209-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0209-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0209-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0209-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0209-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="a0209-121">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a0209-121">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)  
 <span data-ttu-id="a0209-122">[Threading gestito e non gestito](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a0209-122">[Managed and Unmanaged Threading](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))</span></span>  
 [<span data-ttu-id="a0209-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="a0209-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
