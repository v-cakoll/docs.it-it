---
title: Interfaccia IHostMemoryManager
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
ms.openlocfilehash: bc05d76795f20d28d6d2899d61dc4674ebfdca8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128653"
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="95873-102">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="95873-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="95873-103">Fornisce metodi che consentono all'Common Language Runtime (CLR) di effettuare richieste di memoria virtuale attraverso l'host, anziché utilizzare le funzioni di memoria virtuale Win32 standard.</span><span class="sxs-lookup"><span data-stu-id="95873-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="95873-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="95873-104">Methods</span></span>  
  
|<span data-ttu-id="95873-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="95873-105">Method</span></span>|<span data-ttu-id="95873-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95873-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="95873-107">Metodo AcquiredVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="95873-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="95873-108">Notifica all'host che la Common Language Runtime (CLR) ha acquisito la memoria specificata dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="95873-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="95873-109">Metodo CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="95873-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="95873-110">Ottiene un puntatore a interfaccia a un'istanza di [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) utilizzata per richiedere allocazioni di memoria da un heap creato dall'host.</span><span class="sxs-lookup"><span data-stu-id="95873-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="95873-111">Metodo GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="95873-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="95873-112">Ottiene la quantità di memoria fisica attualmente in uso, come segnalato dall'host.</span><span class="sxs-lookup"><span data-stu-id="95873-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="95873-113">Metodo NeedsVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="95873-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="95873-114">Notifica all'host che CLR tenterà di utilizzare la memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="95873-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="95873-115">Metodo RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="95873-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="95873-116">Registra un puntatore a una funzione di callback richiamata dall'host per notificare a CLR il carico di memoria corrente nel computer.</span><span class="sxs-lookup"><span data-stu-id="95873-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="95873-117">Metodo ReleasedVirtualAddressSpace</span><span class="sxs-lookup"><span data-stu-id="95873-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="95873-118">Notifica all'host che CLR ha terminato di utilizzare la memoria specificata.</span><span class="sxs-lookup"><span data-stu-id="95873-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="95873-119">Metodo VirtualAlloc</span><span class="sxs-lookup"><span data-stu-id="95873-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="95873-120">Funge da wrapper logico per la funzione Win32 corrispondente, che consente di riservare o eseguire il commit di un'area di pagine nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="95873-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="95873-121">Metodo VirtualFree</span><span class="sxs-lookup"><span data-stu-id="95873-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="95873-122">Funge da wrapper logico per la funzione Win32 corrispondente, che rilascia, decommit o rilascia un'area di pagine all'interno dello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="95873-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="95873-123">Metodo VirtualProtect</span><span class="sxs-lookup"><span data-stu-id="95873-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="95873-124">Funge da wrapper logico per la funzione Win32 corrispondente, che modifica la protezione in un'area di pagine di cui è stato eseguito il commit nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="95873-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="95873-125">Metodo VirtualQuery</span><span class="sxs-lookup"><span data-stu-id="95873-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="95873-126">Funge da wrapper logico per la funzione Win32 corrispondente, che recupera informazioni su un intervallo di pagine nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="95873-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95873-127">Note</span><span class="sxs-lookup"><span data-stu-id="95873-127">Remarks</span></span>  
 <span data-ttu-id="95873-128">`IHostMemoryManager` fornisce inoltre metodi che consentono a CLR di ottenere un puntatore tramite il quale eseguire richieste di memoria nell'heap e ottenere il livello di utilizzo di memoria nel processo, come riportato dall'host.</span><span class="sxs-lookup"><span data-stu-id="95873-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95873-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95873-129">Requirements</span></span>  
 <span data-ttu-id="95873-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95873-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95873-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="95873-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95873-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="95873-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95873-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95873-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95873-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95873-134">See also</span></span>

- [<span data-ttu-id="95873-135">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="95873-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [<span data-ttu-id="95873-136">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="95873-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
