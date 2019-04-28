---
title: Metodo IHostMemoryManager::GetMemoryLoad
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c43fd1c63b14fc3254044247213bf09453da870e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599381"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="6c023-102">Metodo IHostMemoryManager::GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="6c023-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="6c023-103">Ottiene la quantità di memoria fisica che è attualmente in uso e pertanto non disponibile, come indicato dall'host.</span><span class="sxs-lookup"><span data-stu-id="6c023-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c023-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c023-104">Syntax</span></span>  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c023-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c023-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="6c023-106">[out] Puntatore alla percentuale approssimativa di memoria fisica totale che è attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="6c023-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="6c023-107">[out] Puntatore al numero di byte disponibili per common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6c023-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c023-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6c023-108">Return Value</span></span>  
  
|<span data-ttu-id="6c023-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c023-109">HRESULT</span></span>|<span data-ttu-id="6c023-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c023-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c023-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c023-111">S_OK</span></span>|<span data-ttu-id="6c023-112">`GetMemoryLoad` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6c023-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="6c023-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6c023-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6c023-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6c023-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6c023-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6c023-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6c023-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6c023-116">The call timed out.</span></span>|  
|<span data-ttu-id="6c023-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6c023-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6c023-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="6c023-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6c023-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6c023-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6c023-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6c023-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6c023-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6c023-121">E_FAIL</span></span>|<span data-ttu-id="6c023-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6c023-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6c023-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6c023-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6c023-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6c023-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c023-125">Note</span><span class="sxs-lookup"><span data-stu-id="6c023-125">Remarks</span></span>  
 <span data-ttu-id="6c023-126">`GetMemoryLoad` esegue il wrapping di Win32 `GlobalMemoryStatus` (funzione).</span><span class="sxs-lookup"><span data-stu-id="6c023-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="6c023-127">Il valore di `pMemoryLoad` equivale al `dwMemoryLoad` campo le `MEMORYSTATUS` struttura restituita da `GlobalMemoryStatus`.</span><span class="sxs-lookup"><span data-stu-id="6c023-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="6c023-128">Il runtime usa il valore restituito come un'euristica per il garbage collector.</span><span class="sxs-lookup"><span data-stu-id="6c023-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="6c023-129">Ad esempio, se l'host segnala che la maggior parte della memoria è in uso, il garbage collector può scegliere di raccogliere dai più generazioni per aumentare la quantità di memoria che può potenzialmente diventano disponibile.</span><span class="sxs-lookup"><span data-stu-id="6c023-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c023-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c023-130">Requirements</span></span>  
 <span data-ttu-id="6c023-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c023-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c023-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c023-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c023-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6c023-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c023-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c023-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c023-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c023-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="6c023-136">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="6c023-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
