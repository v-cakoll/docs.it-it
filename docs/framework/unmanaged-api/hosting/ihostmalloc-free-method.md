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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8bd7b16f06433970d1222dbeaa843e187715faa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438997"
---
# <a name="ihostmallocfree-method"></a><span data-ttu-id="0f850-102">Metodo IHostMAlloc::Free</span><span class="sxs-lookup"><span data-stu-id="0f850-102">IHostMAlloc::Free Method</span></span>
<span data-ttu-id="0f850-103">Libera la memoria allocata tramite il [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="0f850-103">Frees memory that was allocated by using the [Alloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f850-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f850-104">Syntax</span></span>  
  
```  
HRESULT Free (  
    [in] void* pMem  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f850-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f850-105">Parameters</span></span>  
 `pMem`  
 <span data-ttu-id="0f850-106">[in] Puntatore alla memoria da liberare.</span><span class="sxs-lookup"><span data-stu-id="0f850-106">[in] A pointer to the memory to be freed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f850-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0f850-107">Return Value</span></span>  
  
|<span data-ttu-id="0f850-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f850-108">HRESULT</span></span>|<span data-ttu-id="0f850-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f850-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f850-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f850-110">S_OK</span></span>|<span data-ttu-id="0f850-111">`Free` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0f850-111">`Free` returned successfully.</span></span>|  
|<span data-ttu-id="0f850-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f850-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f850-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0f850-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f850-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f850-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f850-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0f850-115">The call timed out.</span></span>|  
|<span data-ttu-id="0f850-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f850-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f850-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="0f850-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f850-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f850-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f850-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0f850-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f850-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f850-120">E_FAIL</span></span>|<span data-ttu-id="0f850-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0f850-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f850-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0f850-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f850-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0f850-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0f850-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="0f850-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="0f850-125">È stato effettuato un tentativo di liberare la memoria non allocata tramite l'host.</span><span class="sxs-lookup"><span data-stu-id="0f850-125">An attempt was made to free memory that was not allocated through the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f850-126">Note</span><span class="sxs-lookup"><span data-stu-id="0f850-126">Remarks</span></span>  
 <span data-ttu-id="0f850-127">Se il `pMem` parametro fa riferimento a un'area di memoria che non è stata allocata mediante una chiamata a `Alloc`, l'host deve restituire HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="0f850-127">If the `pMem` parameter refers to a region of memory that was not allocated by using a call to `Alloc`, the host should return HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f850-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f850-128">Requirements</span></span>  
 <span data-ttu-id="0f850-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f850-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f850-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="0f850-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f850-131">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0f850-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f850-132">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f850-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f850-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f850-133">See Also</span></span>  
 [<span data-ttu-id="0f850-134">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="0f850-134">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="0f850-135">Interfaccia IHostMalloc</span><span class="sxs-lookup"><span data-stu-id="0f850-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
