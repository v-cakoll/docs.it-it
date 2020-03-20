---
title: Metodo IHostMAlloc::DebugAlloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc.DebugAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::DebugAlloc
helpviewer_keywords:
- DebugAlloc method [.NET Framework hosting]
- IHostMAlloc::DebugAlloc method [.NET Framework hosting]
ms.assetid: 0bfbc527-bea2-43ce-b041-69186f4440dd
topic_type:
- apiref
ms.openlocfilehash: 20ad5485b8603cc7de1c27c00d53c8939871d525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178030"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="40203-102">Metodo IHostMAlloc::DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="40203-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="40203-103">Richiede che l'host allochi la quantità di memoria specificata dall'heap e inoltre tiene traccia della posizione in cui è stata allocata la memoria.</span><span class="sxs-lookup"><span data-stu-id="40203-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40203-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40203-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,
    [in]  EMemoryCriticalLevel dwCriticalLevel,
    [in]  char*   pszFileName,
    [in]  int     iLineNo,
    [out] void**  ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40203-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="40203-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="40203-106">[in] Dimensione, in byte, della richiesta di allocazione della memoria corrente.</span><span class="sxs-lookup"><span data-stu-id="40203-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="40203-107">[in] Uno dei valori [di EMemoryCriticalLevel,](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) che indica l'impatto di un errore di allocazione.</span><span class="sxs-lookup"><span data-stu-id="40203-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="40203-108">[in] File di codice dell'eseguibile sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="40203-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="40203-109">[in] Numero di `pszFileName` riga in cui è stata richiesta l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="40203-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="40203-110">[fuori] Puntatore alla memoria allocata o null se non è stato possibile completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="40203-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40203-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="40203-111">Return Value</span></span>  
  
|<span data-ttu-id="40203-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="40203-112">HRESULT</span></span>|<span data-ttu-id="40203-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="40203-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="40203-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="40203-114">S_OK</span></span>|<span data-ttu-id="40203-115">`DebugAlloc`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="40203-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="40203-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="40203-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="40203-117">CLR non è stato caricato in un processo o CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="40203-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="40203-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="40203-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="40203-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="40203-119">The call timed out.</span></span>|  
|<span data-ttu-id="40203-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="40203-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="40203-121">Il chiamante non è proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="40203-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="40203-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="40203-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="40203-123">Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="40203-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="40203-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="40203-124">E_FAIL</span></span>|<span data-ttu-id="40203-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="40203-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="40203-126">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="40203-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="40203-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="40203-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="40203-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="40203-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="40203-129">Memoria insufficiente per completare la richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="40203-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40203-130">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="40203-130">Remarks</span></span>  
 <span data-ttu-id="40203-131">CLR ottiene un puntatore a interfaccia a [un'istanza di IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) chiamando il metodo [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="40203-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="40203-132">`DebugAlloc`consente al runtime di ottenere informazioni sul file di codice da utilizzare durante il debug.</span><span class="sxs-lookup"><span data-stu-id="40203-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40203-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="40203-133">Requirements</span></span>  
 <span data-ttu-id="40203-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40203-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40203-135">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="40203-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40203-136">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="40203-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40203-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40203-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40203-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40203-138">See also</span></span>

- [<span data-ttu-id="40203-139">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="40203-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="40203-140">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="40203-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
