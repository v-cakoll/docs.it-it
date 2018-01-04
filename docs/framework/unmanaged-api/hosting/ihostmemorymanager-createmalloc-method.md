---
title: Metodo IHostMemoryManager::CreateMAlloc
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.CreateMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 19b43ccf7cb2429c28c052ab8ab3a009ec4a30a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="727cd-102">Metodo IHostMemoryManager::CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="727cd-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="727cd-103">Ottiene un puntatore a interfaccia a un [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) istanza utilizzato per effettuare richieste di allocazione da un heap creato dall'host.</span><span class="sxs-lookup"><span data-stu-id="727cd-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="727cd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="727cd-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="727cd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="727cd-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="727cd-106">[in] Una combinazione di [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flag che specifica le caratteristiche della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="727cd-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="727cd-107">[out] Un puntatore all'indirizzo di un `IHostMAlloc` istanza fornito dall'host.</span><span class="sxs-lookup"><span data-stu-id="727cd-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="727cd-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="727cd-108">Return Value</span></span>  
  
|<span data-ttu-id="727cd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="727cd-109">HRESULT</span></span>|<span data-ttu-id="727cd-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="727cd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="727cd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="727cd-111">S_OK</span></span>|<span data-ttu-id="727cd-112">`CreateMAlloc`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="727cd-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="727cd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="727cd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="727cd-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="727cd-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="727cd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="727cd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="727cd-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="727cd-116">The call timed out.</span></span>|  
|<span data-ttu-id="727cd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="727cd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="727cd-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="727cd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="727cd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="727cd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="727cd-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="727cd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="727cd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="727cd-121">E_FAIL</span></span>|<span data-ttu-id="727cd-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="727cd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="727cd-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="727cd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="727cd-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="727cd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="727cd-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="727cd-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="727cd-126">Memoria fisica insufficiente è disponibile per completare la richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="727cd-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="727cd-127">Note</span><span class="sxs-lookup"><span data-stu-id="727cd-127">Remarks</span></span>  
 <span data-ttu-id="727cd-128">`CreateMAlloc`Restituisce un oggetto che consente a CLR può effettuare richieste di allocazione tramite l'host anziché utilizzare le funzioni Win32 standard.</span><span class="sxs-lookup"><span data-stu-id="727cd-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="727cd-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="727cd-129">Requirements</span></span>  
 <span data-ttu-id="727cd-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="727cd-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="727cd-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="727cd-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="727cd-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="727cd-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="727cd-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="727cd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="727cd-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="727cd-134">See Also</span></span>  
 [<span data-ttu-id="727cd-135">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="727cd-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="727cd-136">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="727cd-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
