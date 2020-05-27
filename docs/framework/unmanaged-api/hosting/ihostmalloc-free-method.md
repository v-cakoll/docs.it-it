---
title: Metodo IHostMAlloc::Free
ms.date: 03/30/2017
api_name:
- IHostMAlloc.Free
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc::Free
helpviewer_keywords:
- IHostMAlloc::Free method [.NET Framework hosting]
- Free method, IHostMAlloc interface [.NET Framework hosting]
ms.assetid: c89abf5b-1120-4437-8b57-4a99fb3ae7f9
topic_type:
- apiref
ms.openlocfilehash: 1dd5ed4c556a5a4d4425a9c0730cebf22ff1785b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804616"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="84313-102">Metodo IHostMAlloc::Free</span><span class="sxs-lookup"><span data-stu-id="84313-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="84313-103">Libera la memoria allocata tramite la funzione [Alloc](ihostmalloc-alloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="84313-103">Frees memory that was allocated by using the [Alloc](ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84313-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84313-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84313-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84313-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="84313-106">in Puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="84313-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84313-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="84313-107">Return Value</span></span>  
  
|<span data-ttu-id="84313-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84313-108">HRESULT</span></span>|<span data-ttu-id="84313-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84313-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="84313-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="84313-110">S_OK</span></span>|<span data-ttu-id="84313-111">`Free`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="84313-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="84313-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84313-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="84313-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="84313-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="84313-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="84313-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="84313-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="84313-115">The call timed out.</span></span>|  
|<span data-ttu-id="84313-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="84313-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="84313-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="84313-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="84313-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="84313-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="84313-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="84313-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="84313-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="84313-120">E_FAIL</span></span>|<span data-ttu-id="84313-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="84313-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="84313-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="84313-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="84313-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="84313-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="84313-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="84313-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="84313-125">È stato effettuato un tentativo di liberare la memoria non allocata tramite l'host.</span><span class="sxs-lookup"><span data-stu-id="84313-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84313-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="84313-126">Remarks</span></span>  
 <span data-ttu-id="84313-127">Se il `pMem` parametro fa riferimento a un'area di memoria non allocata tramite una chiamata a `Alloc` , l'host deve restituire HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="84313-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84313-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84313-128">Requirements</span></span>  
 <span data-ttu-id="84313-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84313-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84313-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="84313-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="84313-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84313-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84313-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84313-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84313-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84313-133">See also</span></span>

- [<span data-ttu-id="84313-134">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="84313-134">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="84313-135">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="84313-135">IHostMalloc Interface</span></span>](ihostmalloc-interface.md)
