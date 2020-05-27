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
ms.openlocfilehash: 6f58e2290afa166d48306c0bbb50edd1df36888b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804642"
---
# <a name="ihostmallocalloc-method"></a><span data-ttu-id="862f0-102">Metodo IHostMAlloc::Alloc</span><span class="sxs-lookup"><span data-stu-id="862f0-102">IHostMAlloc::Alloc Method</span></span>
<span data-ttu-id="862f0-103">Richiede che l'host allochi la quantità di memoria specificata dall'heap.</span><span class="sxs-lookup"><span data-stu-id="862f0-103">Requests that the host allocate the specified amount of memory from the heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="862f0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="862f0-104">Syntax</span></span>  
  
```cpp  
HRESULT Alloc (  
    [in] SIZE_T  cbSize,
    [in] EMemoryCriticalLevel dwCriticalLevel,
    [out] void** ppMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="862f0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="862f0-105">Parameters</span></span>  
 `cbSize`  
 <span data-ttu-id="862f0-106">in Dimensione, in byte, della richiesta di allocazione di memoria corrente.</span><span class="sxs-lookup"><span data-stu-id="862f0-106">[in] The size, in bytes, of the current memory allocation request.</span></span>  
  
 `dwCriticalLevel`  
 <span data-ttu-id="862f0-107">in Uno dei valori di [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) , che indica l'effetto di un errore di allocazione.</span><span class="sxs-lookup"><span data-stu-id="862f0-107">[in] One of the [EMemoryCriticalLevel](ememorycriticallevel-enumeration.md) values, indicating the impact of an allocation failure.</span></span>  
  
 `ppMem`  
 <span data-ttu-id="862f0-108">out Puntatore alla memoria allocata o null se non è stato possibile completare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="862f0-108">[out] A pointer to the allocated memory, or null if the request could not be completed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="862f0-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="862f0-109">Return Value</span></span>  
  
|<span data-ttu-id="862f0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="862f0-110">HRESULT</span></span>|<span data-ttu-id="862f0-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="862f0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="862f0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="862f0-112">S_OK</span></span>|<span data-ttu-id="862f0-113">`Alloc`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="862f0-113">`Alloc` returned successfully.</span></span>|  
|<span data-ttu-id="862f0-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="862f0-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="862f0-115">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="862f0-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="862f0-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="862f0-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="862f0-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="862f0-117">The call timed out.</span></span>|  
|<span data-ttu-id="862f0-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="862f0-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="862f0-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="862f0-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="862f0-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="862f0-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="862f0-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="862f0-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="862f0-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="862f0-122">E_FAIL</span></span>|<span data-ttu-id="862f0-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="862f0-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="862f0-124">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="862f0-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="862f0-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="862f0-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="862f0-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="862f0-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="862f0-127">Memoria insufficiente per completare la richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="862f0-127">Not enough memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="862f0-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="862f0-128">Remarks</span></span>  
 <span data-ttu-id="862f0-129">CLR ottiene un puntatore a interfaccia a un' `IHostMalloc` istanza di chiamando il metodo [IHostMemoryManager:: CreateMAlloc](ihostmemorymanager-createmalloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="862f0-129">The CLR gets an interface pointer to an `IHostMalloc` instance by calling the [IHostMemoryManager::CreateMalloc](ihostmemorymanager-createmalloc-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="862f0-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="862f0-130">Requirements</span></span>  
 <span data-ttu-id="862f0-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="862f0-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="862f0-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="862f0-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="862f0-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="862f0-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="862f0-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="862f0-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="862f0-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="862f0-135">See also</span></span>

- [<span data-ttu-id="862f0-136">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="862f0-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="862f0-137">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="862f0-137">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
