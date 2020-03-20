---
title: Metodo IHostMAlloc::Alloc
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Alloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Alloc
helpviewer_keywords:
- Alloc method, IHostMAlloc interface [.NET Framework hosting]
- IHostMAlloc::Alloc method [.NET Framework hosting]
ms.assetid: a3007f5e-d75d-4b37-842b-704e9edced5e
topic_type:
- apiref
ms.openlocfilehash: dded37fdef02963f60883b289462aa6a96693b3d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176305"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="c325e-102">Metodo IHostMAlloc::Alloc</span><span class="sxs-lookup"><span data-stu-id="c325e-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="c325e-103">Richiede che l'host allochi la quantità di memoria specificata dall'heap.</span><span class="sxs-lookup"><span data-stu-id="c325e-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c325e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c325e-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c325e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c325e-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="c325e-106">[in] Dimensione, in byte, della richiesta di allocazione della memoria corrente.</span><span class="sxs-lookup"><span data-stu-id="c325e-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="c325e-107">[in] Uno dei valori [di EMemoryCriticalLevel,](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) che indica l'impatto di un errore di allocazione.</span><span class="sxs-lookup"><span data-stu-id="c325e-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="c325e-108">[fuori] Puntatore alla memoria allocata o null se non è stato possibile completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="c325e-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c325e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c325e-109">Return Value</span></span>  
  
|<span data-ttu-id="c325e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c325e-110">HRESULT</span></span>|<span data-ttu-id="c325e-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c325e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c325e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c325e-112">S_OK</span></span>|<span data-ttu-id="c325e-113">`Alloc`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="c325e-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="c325e-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c325e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c325e-115">Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c325e-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c325e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c325e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c325e-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c325e-117">The call timed out.</span></span>|  
|<span data-ttu-id="c325e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c325e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c325e-119">Il chiamante non è proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c325e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c325e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c325e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c325e-121">Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c325e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c325e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c325e-122">E_FAIL</span></span>|<span data-ttu-id="c325e-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c325e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c325e-124">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c325e-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c325e-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c325e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c325e-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c325e-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c325e-127">Memoria insufficiente per completare la richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="c325e-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c325e-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c325e-128">Remarks</span></span>  
 <span data-ttu-id="c325e-129">CLR ottiene un puntatore `IHostMalloc` a interfaccia a un'istanza chiamando il [metodo IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c325e-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c325e-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c325e-130">Requirements</span></span>  
 <span data-ttu-id="c325e-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c325e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c325e-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c325e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c325e-133">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c325e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c325e-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c325e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c325e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c325e-135">See also</span></span>

- [<span data-ttu-id="c325e-136">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="c325e-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="c325e-137">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="c325e-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
