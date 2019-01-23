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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3ce303e8bcf33d192dbc7e2447ea6737577dcc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554877"
---
# <a name="ihostmallocdebugalloc-method"></a><span data-ttu-id="ce6e1-102">Metodo IHostMAlloc::DebugAlloc</span><span class="sxs-lookup"><span data-stu-id="ce6e1-102">IHostMAlloc::DebugAlloc Method</span></span>
<span data-ttu-id="ce6e1-103">Richiede che l'host di alloca la quantità specificata di memoria dall'heap e tenere traccia della posizione di allocazione della memoria.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-103">Requests that the host allocate the specified amount of memory from the heap, and additionally track where the memory was allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce6e1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce6e1-104">Syntax</span></span>  
  
```  
HRESULT DebugAlloc (  
    [in]  SIZE_T  cbSize,   
    [in]  EMemoryCriticalLevel dwCriticalLevel,   
    [in]  char*   pszFileName,   
    [in]  int     iLineNo,   
    [out] void**  ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce6e1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ce6e1-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="ce6e1-106">[in] Le dimensioni, in byte, della richiesta di allocazione di memoria corrente.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="ce6e1-107">[in] Uno dei [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) i valori, che indicano l'impatto di un errore di allocazione.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="ce6e1-108">[in] Il file di codice del file eseguibile sottoposto a debug.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-108">[in] The code file of the executable being debugged.</span></span>  
  
 `iLineNo`  
 <span data-ttu-id="ce6e1-109">[in] Numero di riga nel `pszFileName` in cui è stata richiesta l'allocazione.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-109">[in] The line number in `pszFileName` where the allocation was requested.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="ce6e1-110">[out] Puntatore alla memoria allocata, oppure null se non è stato possibile completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-110">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce6e1-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ce6e1-111">Return Value</span></span>  
  
|<span data-ttu-id="ce6e1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce6e1-112">HRESULT</span></span>|<span data-ttu-id="ce6e1-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce6e1-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce6e1-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce6e1-114">S_OK</span></span>|<span data-ttu-id="ce6e1-115">`DebugAlloc` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-115">`DebugAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="ce6e1-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce6e1-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce6e1-117">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ce6e1-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce6e1-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce6e1-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-119">The call timed out.</span></span>|  
|<span data-ttu-id="ce6e1-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce6e1-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce6e1-121">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce6e1-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce6e1-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce6e1-123">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce6e1-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce6e1-124">E_FAIL</span></span>|<span data-ttu-id="ce6e1-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce6e1-126">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce6e1-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ce6e1-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ce6e1-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ce6e1-129">Memoria insufficiente era disponibile per completare la richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-129">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce6e1-130">Note</span><span class="sxs-lookup"><span data-stu-id="ce6e1-130">Remarks</span></span>  
 <span data-ttu-id="ce6e1-131">Common Language Runtime Ottiene un puntatore a interfaccia a un [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) istanza chiamando il [CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="ce6e1-131">The CLR gets an interface pointer to an [IHostMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span> <span data-ttu-id="ce6e1-132">`DebugAlloc` consente al runtime di ottenere informazioni sul file di codice per l'uso durante il debug.</span><span class="sxs-lookup"><span data-stu-id="ce6e1-132">`DebugAlloc` allows the runtime to get code file information for use during debugging.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce6e1-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce6e1-133">Requirements</span></span>  
 <span data-ttu-id="ce6e1-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce6e1-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce6e1-135">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce6e1-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce6e1-136">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ce6e1-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce6e1-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce6e1-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce6e1-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce6e1-138">See also</span></span>
- [<span data-ttu-id="ce6e1-139">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="ce6e1-139">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="ce6e1-140">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="ce6e1-140">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
