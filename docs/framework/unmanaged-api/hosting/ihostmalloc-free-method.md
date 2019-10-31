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
ms.openlocfilehash: f7ae4e4cbb757edea242c57720baeb70ced5c428
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192063"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="cf1f6-102">Metodo IHostMAlloc::Free</span><span class="sxs-lookup"><span data-stu-id="cf1f6-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="cf1f6-103">Libera la memoria allocata tramite la funzione [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cf1f6-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf1f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf1f6-104">Syntax</span></span>  
  
```cpp  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf1f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf1f6-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="cf1f6-106">in Puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cf1f6-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cf1f6-107">Return Value</span></span>  
  
|<span data-ttu-id="cf1f6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cf1f6-108">HRESULT</span></span>|<span data-ttu-id="cf1f6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf1f6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cf1f6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cf1f6-110">S_OK</span></span>|<span data-ttu-id="cf1f6-111">`Free` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="cf1f6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cf1f6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cf1f6-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cf1f6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cf1f6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cf1f6-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-115">The call timed out.</span></span>|  
|<span data-ttu-id="cf1f6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cf1f6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cf1f6-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cf1f6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cf1f6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cf1f6-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cf1f6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cf1f6-120">E_FAIL</span></span>|<span data-ttu-id="cf1f6-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cf1f6-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cf1f6-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="cf1f6-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="cf1f6-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="cf1f6-125">È stato effettuato un tentativo di liberare la memoria non allocata tramite l'host.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf1f6-126">Note</span><span class="sxs-lookup"><span data-stu-id="cf1f6-126">Remarks</span></span>  
 <span data-ttu-id="cf1f6-127">Se il `pMem` parametro fa riferimento a un'area di memoria non allocata tramite una chiamata a `Alloc`, l'host deve restituire HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="cf1f6-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf1f6-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf1f6-128">Requirements</span></span>  
 <span data-ttu-id="cf1f6-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf1f6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf1f6-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cf1f6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf1f6-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cf1f6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf1f6-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf1f6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1f6-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf1f6-133">See also</span></span>

- [<span data-ttu-id="cf1f6-134">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="cf1f6-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="cf1f6-135">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="cf1f6-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
