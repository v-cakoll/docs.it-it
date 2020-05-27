---
title: Metodo IHostMemoryManager::CreateMAlloc
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.CreateMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type:
- apiref
ms.openlocfilehash: 89c1d7b043d4369bf16a851924711c3c9d75791e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804523"
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="55f7a-102">Metodo IHostMemoryManager::CreateMAlloc</span><span class="sxs-lookup"><span data-stu-id="55f7a-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="55f7a-103">Ottiene un puntatore a interfaccia a un'istanza di [IHostMalloc](ihostmalloc-interface.md) utilizzata per eseguire richieste di allocazione da un heap creato dall'host.</span><span class="sxs-lookup"><span data-stu-id="55f7a-103">Gets an interface pointer to an [IHostMAlloc](ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55f7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55f7a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55f7a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="55f7a-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="55f7a-106">in Combinazione di flag di [MALLOC_TYPE](malloc-type-enumeration.md) che specifica le caratteristiche della memoria da allocare.</span><span class="sxs-lookup"><span data-stu-id="55f7a-106">[in] A combination of [MALLOC_TYPE](malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="55f7a-107">out Puntatore all'indirizzo di un' `IHostMAlloc` istanza fornita dall'host.</span><span class="sxs-lookup"><span data-stu-id="55f7a-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55f7a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="55f7a-108">Return Value</span></span>  
  
|<span data-ttu-id="55f7a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55f7a-109">HRESULT</span></span>|<span data-ttu-id="55f7a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55f7a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55f7a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="55f7a-111">S_OK</span></span>|<span data-ttu-id="55f7a-112">`CreateMAlloc`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="55f7a-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="55f7a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55f7a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55f7a-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="55f7a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55f7a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55f7a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55f7a-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="55f7a-116">The call timed out.</span></span>|  
|<span data-ttu-id="55f7a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55f7a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55f7a-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="55f7a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55f7a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55f7a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55f7a-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="55f7a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55f7a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55f7a-121">E_FAIL</span></span>|<span data-ttu-id="55f7a-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="55f7a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55f7a-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="55f7a-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55f7a-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="55f7a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="55f7a-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="55f7a-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="55f7a-126">Memoria fisica insufficiente per completare la richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="55f7a-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55f7a-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="55f7a-127">Remarks</span></span>  
 <span data-ttu-id="55f7a-128">`CreateMAlloc`Restituisce un oggetto che consente a CLR di eseguire richieste di allocazione tramite l'host anziché utilizzare le funzioni Win32 standard.</span><span class="sxs-lookup"><span data-stu-id="55f7a-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55f7a-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55f7a-129">Requirements</span></span>  
 <span data-ttu-id="55f7a-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55f7a-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55f7a-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="55f7a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55f7a-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="55f7a-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55f7a-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55f7a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f7a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55f7a-134">See also</span></span>

- [<span data-ttu-id="55f7a-135">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="55f7a-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
- [<span data-ttu-id="55f7a-136">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="55f7a-136">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
