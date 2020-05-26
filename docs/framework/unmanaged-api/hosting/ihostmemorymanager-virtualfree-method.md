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
ms.openlocfilehash: 4d37b7d803509ebfa861b7502d419f868bd12e11
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804379"
---
# <a name="ihostmemorymanagervirtualfree-method"></a><span data-ttu-id="c6f27-102">Metodo IHostMemoryManager::VirtualFree</span><span class="sxs-lookup"><span data-stu-id="c6f27-102">IHostMemoryManager::VirtualFree Method</span></span>
<span data-ttu-id="c6f27-103">Funge da wrapper logico per la funzione Win32 corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c6f27-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="c6f27-104">L'implementazione Win32 di `VirtualFree` rilascia, effettua il commit o rilascia un'area di pagine all'interno dello spazio degli indirizzi virtuali del processo chiamante.</span><span class="sxs-lookup"><span data-stu-id="c6f27-104">The Win32 implementation of `VirtualFree` releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f27-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6f27-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualFree (  
    [in] LPVOID  lpAddress,  
    [in] SIZE_T  dwSize,  
    [in] DWORD   dwFreeType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6f27-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6f27-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="c6f27-107">in Puntatore all'indirizzo di base delle pagine di memoria virtuale da liberare.</span><span class="sxs-lookup"><span data-stu-id="c6f27-107">[in] A pointer to the base address of the virtual memory pages to be freed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="c6f27-108">in Dimensione, in byte, dell'area da liberare.</span><span class="sxs-lookup"><span data-stu-id="c6f27-108">[in] The size, in bytes, of the region to be freed.</span></span>  
  
 `dwFreeType`  
 <span data-ttu-id="c6f27-109">in Tipo di operazione di liberazione.</span><span class="sxs-lookup"><span data-stu-id="c6f27-109">[in] The type of freeing operation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6f27-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c6f27-110">Return Value</span></span>  
  
|<span data-ttu-id="c6f27-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6f27-111">HRESULT</span></span>|<span data-ttu-id="c6f27-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6f27-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6f27-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6f27-113">S_OK</span></span>|<span data-ttu-id="c6f27-114">`VirtualFree`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c6f27-114">`VirtualFree` returned successfully.</span></span>|  
|<span data-ttu-id="c6f27-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6f27-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6f27-116">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c6f27-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c6f27-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c6f27-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c6f27-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c6f27-118">The call timed out.</span></span>|  
|<span data-ttu-id="c6f27-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c6f27-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c6f27-120">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c6f27-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c6f27-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c6f27-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c6f27-122">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c6f27-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c6f27-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6f27-123">E_FAIL</span></span>|<span data-ttu-id="c6f27-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c6f27-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c6f27-125">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c6f27-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c6f27-126">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c6f27-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c6f27-127">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="c6f27-127">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="c6f27-128">È stato effettuato un tentativo di liberare la memoria non allocata tramite l'host.</span><span class="sxs-lookup"><span data-stu-id="c6f27-128">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6f27-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c6f27-129">Remarks</span></span>  
 <span data-ttu-id="c6f27-130">`VirtualFree`libera le pagine di memoria virtuale associate al `lpAddress` parametro tramite una chiamata precedente alla funzione [IHostMemoryManager:: VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c6f27-130">`VirtualFree` frees virtual memory pages associated with the `lpAddress` parameter through an earlier call to the [IHostMemoryManager::VirtualAlloc](ihostmemorymanager-virtualalloc-method.md) function.</span></span> <span data-ttu-id="c6f27-131">I tentativi di liberare memoria non allocata tramite l'host devono restituire HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="c6f27-131">Attempts to free memory that was not allocated through the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
 <span data-ttu-id="c6f27-132">La semantica è identica a quella dell'implementazione Win32 di `VirtualFree` .</span><span class="sxs-lookup"><span data-stu-id="c6f27-132">The semantics are identical to those of the Win32 implementation of `VirtualFree`.</span></span> <span data-ttu-id="c6f27-133">Per ulteriori informazioni, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="c6f27-133">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6f27-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6f27-134">Requirements</span></span>  
 <span data-ttu-id="c6f27-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6f27-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6f27-136">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c6f27-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6f27-137">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c6f27-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6f27-138">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6f27-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f27-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6f27-139">See also</span></span>

- [<span data-ttu-id="c6f27-140">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="c6f27-140">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="c6f27-141">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="c6f27-141">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
