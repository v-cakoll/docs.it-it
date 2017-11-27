---
title: Interfaccia IHostMemoryManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager
helpviewer_keywords: IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 415539be0dbed8e0cf3f9d6e5c79bf4cfac09fe2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="21938-102">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="21938-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="21938-103">Fornisce metodi che consentono a common language runtime (CLR) per effettuare richieste di memoria virtuale tramite l'host, invece di usare le funzioni di memoria virtuale Win32 standard.</span><span class="sxs-lookup"><span data-stu-id="21938-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="21938-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="21938-104">Methods</span></span>  
  
|<span data-ttu-id="21938-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="21938-105">Method</span></span>|<span data-ttu-id="21938-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="21938-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="21938-107">AcquiredVirtualAddressSpace (metodo)</span><span class="sxs-lookup"><span data-stu-id="21938-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="21938-108">Notifica all'host che common language runtime (CLR) ha acquisito la memoria specificata dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="21938-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="21938-109">Metodo CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="21938-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="21938-110">Ottiene un puntatore a interfaccia a un [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) istanza che viene usato per richiedere le allocazioni di memoria da un heap creato dall'host.</span><span class="sxs-lookup"><span data-stu-id="21938-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="21938-111">GetMemoryLoad (metodo)</span><span class="sxs-lookup"><span data-stu-id="21938-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="21938-112">Ottiene la quantità di memoria fisica che è attualmente in uso, come riportato dall'host.</span><span class="sxs-lookup"><span data-stu-id="21938-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="21938-113">NeedsVirtualAddressSpace (metodo)</span><span class="sxs-lookup"><span data-stu-id="21938-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="21938-114">Notifica all'host che CLR tenterà di utilizzare la memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="21938-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="21938-115">RegisterMemoryNotificationCallback (metodo)</span><span class="sxs-lookup"><span data-stu-id="21938-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="21938-116">Registra un puntatore a una funzione di callback che l'host richiama per notificare a CLR il carico di memoria corrente nel computer.</span><span class="sxs-lookup"><span data-stu-id="21938-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="21938-117">ReleasedVirtualAddressSpace (metodo)</span><span class="sxs-lookup"><span data-stu-id="21938-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="21938-118">Notifica all'host che CLR ha terminato di utilizzare la memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="21938-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="21938-119">VirtualAlloc (metodo)</span><span class="sxs-lookup"><span data-stu-id="21938-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="21938-120">Funge da wrapper logico per la funzione Win32 corrispondente, che si riserva o esegue il commit di una regione di pagine nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="21938-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="21938-121">VirtualFree (metodo)</span><span class="sxs-lookup"><span data-stu-id="21938-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="21938-122">Funge da wrapper logico per la funzione Win32 corrispondente, che rilascia, libera o rilascia e libera un'area di pagine all'interno di spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="21938-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="21938-123">VirtualProtect (metodo)</span><span class="sxs-lookup"><span data-stu-id="21938-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="21938-124">Funge da wrapper logico per la funzione Win32 corrispondente, che modifica la protezione in un'area di pagine salvate nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="21938-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="21938-125">VirtualQuery (metodo)</span><span class="sxs-lookup"><span data-stu-id="21938-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="21938-126">Funge da wrapper logico per la funzione Win32 corrispondente, che recupera informazioni su un intervallo di pagine nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="21938-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21938-127">Note</span><span class="sxs-lookup"><span data-stu-id="21938-127">Remarks</span></span>  
 <span data-ttu-id="21938-128">`IHostMemoryManager`fornisce inoltre metodi per ottenere un puntatore attraverso il quale per effettuare richieste di memoria nell'heap e di ottenere il livello di utilizzo della memoria del processo, come riportato dall'host CLR.</span><span class="sxs-lookup"><span data-stu-id="21938-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21938-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="21938-129">Requirements</span></span>  
 <span data-ttu-id="21938-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21938-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21938-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="21938-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21938-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="21938-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21938-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21938-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21938-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21938-134">See Also</span></span>  
 [<span data-ttu-id="21938-135">IHostMalloc (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="21938-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="21938-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="21938-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
