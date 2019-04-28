---
title: Metodo IHostMemoryManager::VirtualAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualAlloc
helpviewer_keywords:
- VirtualAlloc method [.NET Framework hosting]
- IHostMemoryManager::VirtualAlloc method [.NET Framework hosting]
ms.assetid: 4dff3646-a050-4bd9-ac31-fe307e8637ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5407a9d23833d73b2d6ef0038454f56f01d56867
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760207"
---
# <a name="ihostmemorymanagervirtualalloc-method"></a><span data-ttu-id="65427-102">Metodo IHostMemoryManager::VirtualAlloc</span><span class="sxs-lookup"><span data-stu-id="65427-102">IHostMemoryManager::VirtualAlloc Method</span></span>
<span data-ttu-id="65427-103">Funge da wrapper logico per la funzione Win32 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="65427-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="65427-104">L'implementazione di Win32 di `VirtualAlloc` riserva o impegna un'area di pagine nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="65427-104">The Win32 implementation of `VirtualAlloc` reserves or commits a region of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65427-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65427-105">Syntax</span></span>  
  
```  
HRESULT VirtualAlloc (  
    [in]  void*   pAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flAllocationType,  
    [in]  DWORD   flProtect,  
    [in]  EMemoryCriticalLevel dwCriticalLevel,  
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65427-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="65427-106">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="65427-107">[in] Un puntatore all'indirizzo iniziale dell'area da allocare.</span><span class="sxs-lookup"><span data-stu-id="65427-107">[in] A pointer to the starting address of the region to allocate.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="65427-108">[in] Le dimensioni, in byte, dell'area.</span><span class="sxs-lookup"><span data-stu-id="65427-108">[in] The size, in bytes, of the region.</span></span>  
  
 `flAllocationType`  
 <span data-ttu-id="65427-109">[in] Il tipo di allocazione della memoria.</span><span class="sxs-lookup"><span data-stu-id="65427-109">[in] The type of memory allocation.</span></span>  
  
 `flProtect`  
 <span data-ttu-id="65427-110">[in] Protezione della memoria per l'area delle pagine da allocare.</span><span class="sxs-lookup"><span data-stu-id="65427-110">[in] Memory protection for the region of pages to be allocated.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="65427-111">[in] Un' [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valore che indica l'impatto di un errore di allocazione.</span><span class="sxs-lookup"><span data-stu-id="65427-111">[in] An [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) value that indicates the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="65427-112">[out] Puntatore all'indirizzo iniziale della memoria allocata, o null se non è stato possibile soddisfare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="65427-112">[out] Pointer to the starting address of the allocated memory, or null if the request could not be satisfied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65427-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="65427-113">Return Value</span></span>  
  
|<span data-ttu-id="65427-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65427-114">HRESULT</span></span>|<span data-ttu-id="65427-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65427-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65427-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="65427-116">S_OK</span></span>|<span data-ttu-id="65427-117">`VirtualAlloc` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="65427-117">`VirtualAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="65427-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="65427-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="65427-119">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="65427-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="65427-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="65427-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="65427-121">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="65427-121">The call timed out.</span></span>|  
|<span data-ttu-id="65427-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="65427-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="65427-123">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="65427-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="65427-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="65427-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="65427-125">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="65427-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="65427-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="65427-126">E_FAIL</span></span>|<span data-ttu-id="65427-127">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="65427-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="65427-128">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="65427-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="65427-129">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="65427-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="65427-130">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="65427-130">E_OUTOFMEMORY</span></span>|<span data-ttu-id="65427-131">Memoria insufficiente era disponibile per completare la richiesta di allocazione</span><span class="sxs-lookup"><span data-stu-id="65427-131">Not enough memory was available to complete the allocation request</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65427-132">Note</span><span class="sxs-lookup"><span data-stu-id="65427-132">Remarks</span></span>  
 <span data-ttu-id="65427-133">È possibile riservare un'area nello spazio degli indirizzi del processo chiamando `VirtualAlloc`.</span><span class="sxs-lookup"><span data-stu-id="65427-133">You reserve a region in the address space of your process by calling `VirtualAlloc`.</span></span> <span data-ttu-id="65427-134">Il `pAddress` parametro contiene l'indirizzo iniziale del blocco di memoria desiderata.</span><span class="sxs-lookup"><span data-stu-id="65427-134">The `pAddress` parameter contains the beginning address of the memory block you want.</span></span> <span data-ttu-id="65427-135">Questo parametro viene in genere impostato su null.</span><span class="sxs-lookup"><span data-stu-id="65427-135">This parameter is typically set to null.</span></span> <span data-ttu-id="65427-136">Il sistema operativo conserva un record di intervalli di indirizzi liberi disponibili per il processo.</span><span class="sxs-lookup"><span data-stu-id="65427-136">The operating system keeps a record of free address ranges available to your process.</span></span> <span data-ttu-id="65427-137">Oggetto `pAddress` valore null indica al sistema di riserva l'area, ove opportuno.</span><span class="sxs-lookup"><span data-stu-id="65427-137">A `pAddress` value of null instructs the system to reserve the region wherever it sees fit.</span></span> <span data-ttu-id="65427-138">In alternativa, è possibile fornire uno specifico indirizzo inizio per il blocco di memoria.</span><span class="sxs-lookup"><span data-stu-id="65427-138">Alternatively, you can provide a specific starting address for the memory block.</span></span> <span data-ttu-id="65427-139">In entrambi i casi, il parametro di output `ppMem` viene restituito come un puntatore alla memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="65427-139">In both cases, the output parameter `ppMem` is returned as a pointer to the allocated memory.</span></span> <span data-ttu-id="65427-140">La funzione restituisce un valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="65427-140">The function itself returns an HRESULT value.</span></span>  
  
 <span data-ttu-id="65427-141">Win32 `VirtualAlloc` la funzione non ha un `ppMem` parametro e restituisce invece il puntatore alla memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="65427-141">The Win32 `VirtualAlloc` function does not have a `ppMem` parameter, and returns the pointer to the allocated memory instead.</span></span> <span data-ttu-id="65427-142">Per altre informazioni, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="65427-142">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65427-143">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65427-143">Requirements</span></span>  
 <span data-ttu-id="65427-144">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65427-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65427-145">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65427-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65427-146">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="65427-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65427-147">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65427-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65427-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65427-148">See also</span></span>

- [<span data-ttu-id="65427-149">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="65427-149">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
