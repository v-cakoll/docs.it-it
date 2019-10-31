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
ms.openlocfilehash: b53c0bb38922ae8de048c131807eb32f97423d6c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128585"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="90db6-102">Metodo IHostMemoryManager::VirtualFree</span><span class="sxs-lookup"><span data-stu-id="90db6-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="90db6-103">Funge da wrapper logico per la funzione Win32 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="90db6-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="90db6-104">L'implementazione Win32 di `VirtualFree` rilascia, effettua il commit o rilascia un'area di pagine all'interno dello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="90db6-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90db6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90db6-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90db6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="90db6-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="90db6-107">in Puntatore all'indirizzo di base delle pagine di memoria virtuale da liberare.</span><span class="sxs-lookup"><span data-stu-id="90db6-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="90db6-108">in Dimensione, in byte, dell'area da liberare.</span><span class="sxs-lookup"><span data-stu-id="90db6-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="90db6-109">in Tipo di operazione di liberazione.</span><span class="sxs-lookup"><span data-stu-id="90db6-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90db6-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="90db6-110">Return Value</span></span>  
  
|<span data-ttu-id="90db6-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="90db6-111">HRESULT</span></span>|<span data-ttu-id="90db6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90db6-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="90db6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="90db6-113">S_OK</span></span>|<span data-ttu-id="90db6-114">`VirtualFree` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="90db6-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="90db6-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="90db6-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="90db6-116">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="90db6-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="90db6-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="90db6-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="90db6-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="90db6-118">The call timed out.</span></span>|  
|<span data-ttu-id="90db6-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="90db6-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="90db6-120">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="90db6-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="90db6-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="90db6-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="90db6-122">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="90db6-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="90db6-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="90db6-123">E_FAIL</span></span>|<span data-ttu-id="90db6-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="90db6-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="90db6-125">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="90db6-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="90db6-126">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="90db6-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="90db6-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="90db6-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="90db6-128">È stato effettuato un tentativo di liberare la memoria non allocata tramite l'host.</span><span class="sxs-lookup"><span data-stu-id="90db6-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90db6-129">Note</span><span class="sxs-lookup"><span data-stu-id="90db6-129">Remarks</span></span>  
 <span data-ttu-id="90db6-130">`VirtualFree` libera le pagine di memoria virtuale associate al parametro `lpAddress` tramite una chiamata precedente alla funzione [IHostMemoryManager:: VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="90db6-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="90db6-131">I tentativi di liberare memoria non allocata tramite l'host devono restituire HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="90db6-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="90db6-132">La semantica è identica a quella dell'implementazione Win32 di `VirtualFree`.</span><span class="sxs-lookup"><span data-stu-id="90db6-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="90db6-133">Per ulteriori informazioni, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="90db6-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90db6-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90db6-134">Requirements</span></span>  
 <span data-ttu-id="90db6-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90db6-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90db6-136">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="90db6-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="90db6-137">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="90db6-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90db6-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90db6-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90db6-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90db6-139">See also</span></span>

- [<span data-ttu-id="90db6-140">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="90db6-140">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="90db6-141">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="90db6-141">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
