---
title: Metodo IHostMemoryManager::VirtualFree
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualFree
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualFree
helpviewer_keywords:
- IHostMemoryManager::VirtualFree method [.NET Framework hosting]
- VirtualFree method [.NET Framework hosting]
ms.assetid: 1a436e89-eb28-4d15-bcf1-a072f86dbd99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03cac2b8433d6491d1fa474a0d4064ef4e260d6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59099911"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="25b7a-102">Metodo IHostMemoryManager::VirtualFree</span><span class="sxs-lookup"><span data-stu-id="25b7a-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="25b7a-103">Funge da wrapper logico per la funzione Win32 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="25b7a-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="25b7a-104">L'implementazione di Win32 di `VirtualFree` rilascia, libera o rilascia e libera un'area di pagine nello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="25b7a-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25b7a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25b7a-105">Syntax</span></span>  
  
```  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25b7a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="25b7a-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="25b7a-107">[in] Un puntatore all'indirizzo di base delle pagine della memoria virtuale da liberare.</span><span class="sxs-lookup"><span data-stu-id="25b7a-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="25b7a-108">[in] Le dimensioni, in byte, dell'area da liberare.</span><span class="sxs-lookup"><span data-stu-id="25b7a-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="25b7a-109">[in] Tipo di operazione di rilascio.</span><span class="sxs-lookup"><span data-stu-id="25b7a-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25b7a-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="25b7a-110">Return Value</span></span>  
  
|<span data-ttu-id="25b7a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25b7a-111">HRESULT</span></span>|<span data-ttu-id="25b7a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25b7a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25b7a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="25b7a-113">S_OK</span></span>|<span data-ttu-id="25b7a-114">`VirtualFree` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="25b7a-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="25b7a-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="25b7a-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="25b7a-116">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25b7a-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="25b7a-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="25b7a-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="25b7a-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="25b7a-118">The call timed out.</span></span>|  
|<span data-ttu-id="25b7a-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="25b7a-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="25b7a-120">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="25b7a-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="25b7a-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="25b7a-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="25b7a-122">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="25b7a-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="25b7a-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="25b7a-123">E_FAIL</span></span>|<span data-ttu-id="25b7a-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="25b7a-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="25b7a-125">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="25b7a-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="25b7a-126">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="25b7a-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="25b7a-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="25b7a-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="25b7a-128">È stato effettuato un tentativo per liberare la memoria non allocata tramite l'host.</span><span class="sxs-lookup"><span data-stu-id="25b7a-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25b7a-129">Note</span><span class="sxs-lookup"><span data-stu-id="25b7a-129">Remarks</span></span>  
 <span data-ttu-id="25b7a-130">`VirtualFree` Consente di liberare le pagine di memoria virtuale associate la `lpAddress` al parametro tramite una chiamata precedente al [IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="25b7a-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="25b7a-131">Tenta di liberare la memoria non allocata tramite l'host deve restituire HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="25b7a-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="25b7a-132">La semantica è identica a quelle dell'implementazione di Win32 `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="25b7a-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="25b7a-133">Per altre informazioni, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="25b7a-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25b7a-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25b7a-134">Requirements</span></span>  
 <span data-ttu-id="25b7a-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25b7a-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25b7a-136">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25b7a-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25b7a-137">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="25b7a-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25b7a-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25b7a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25b7a-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25b7a-139">See also</span></span>

- [<span data-ttu-id="25b7a-140">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="25b7a-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="25b7a-141">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="25b7a-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
