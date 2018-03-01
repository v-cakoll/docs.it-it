---
title: Metodo IHostMAlloc::Alloc
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7d999425be2bc5963aaa9f15b82bd951f6f564af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="4a28c-102">Metodo IHostMAlloc::Alloc</span><span class="sxs-lookup"><span data-stu-id="4a28c-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="4a28c-103">Richieste all'host di allocare la quantità specificata di memoria dall'heap.</span><span class="sxs-lookup"><span data-stu-id="4a28c-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a28c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a28c-104">Syntax</span></span>  
  
```  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,   
    [in] EMemoryCriticalLevel dwCriticalLevel,   
    [out] void** ppMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a28c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a28c-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="4a28c-106">[in] Le dimensioni in byte, della richiesta di allocazione di memoria corrente.</span><span class="sxs-lookup"><span data-stu-id="4a28c-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="4a28c-107">[in] Uno del [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) valori, che indica l'impatto di un errore di allocazione.</span><span class="sxs-lookup"><span data-stu-id="4a28c-107">[in] One of the [EMemoryCriticalLevel](../../../../docs/framework/unmanaged-api/hosting/ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="4a28c-108">[out] Puntatore alla memoria allocata, oppure null se non è stato possibile completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="4a28c-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a28c-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a28c-109">Return Value</span></span>  
  
|<span data-ttu-id="4a28c-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a28c-110">HRESULT</span></span>|<span data-ttu-id="4a28c-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a28c-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a28c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a28c-112">S_OK</span></span>|<span data-ttu-id="4a28c-113">`Alloc`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="4a28c-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="4a28c-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a28c-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a28c-115">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a28c-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a28c-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a28c-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a28c-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a28c-117">The call timed out.</span></span>|  
|<span data-ttu-id="4a28c-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a28c-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a28c-119">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="4a28c-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a28c-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a28c-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a28c-121">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4a28c-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a28c-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a28c-122">E_FAIL</span></span>|<span data-ttu-id="4a28c-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4a28c-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a28c-124">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4a28c-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a28c-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4a28c-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4a28c-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4a28c-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4a28c-127">Memoria insufficiente è disponibile per completare la richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="4a28c-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a28c-128">Note</span><span class="sxs-lookup"><span data-stu-id="4a28c-128">Remarks</span></span>  
 <span data-ttu-id="4a28c-129">CLR ottiene un puntatore a interfaccia a un `IHostMalloc` istanza chiamando il [IHostMemoryManager::](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="4a28c-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a28c-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a28c-130">Requirements</span></span>  
 <span data-ttu-id="4a28c-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a28c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a28c-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="4a28c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a28c-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a28c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a28c-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a28c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a28c-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a28c-135">See Also</span></span>  
 [<span data-ttu-id="4a28c-136">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="4a28c-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="4a28c-137">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="4a28c-137">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
