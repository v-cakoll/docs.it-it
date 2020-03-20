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
ms.openlocfilehash: 88acd50c83eb1ff4d59aa50d677db2383912659a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176279"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a><span data-ttu-id="19706-102">Metodo IHostMemoryManager::GetMemoryLoad</span><span class="sxs-lookup"><span data-stu-id="19706-102">IHostMemoryManager::GetMemoryLoad Method</span></span>
<span data-ttu-id="19706-103">Ottiene la quantità di memoria fisica attualmente in uso e quindi non disponibile, come indicato dall'host.</span><span class="sxs-lookup"><span data-stu-id="19706-103">Gets the amount of physical memory that is currently in use, and therefore unavailable, as reported by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19706-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19706-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19706-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="19706-105">Parameters</span></span>  
 `pMemoryLoad`  
 <span data-ttu-id="19706-106">[fuori] Puntatore alla percentuale approssimativa della memoria fisica totale attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="19706-106">[out] A pointer to the approximate percentage of total physical memory that is currently in use.</span></span>  
  
 `pAvailableBytes`  
 <span data-ttu-id="19706-107">[fuori] Puntatore al numero di byte disponibili per Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="19706-107">[out] A pointer to the number of bytes available to the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19706-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="19706-108">Return Value</span></span>  
  
|<span data-ttu-id="19706-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="19706-109">HRESULT</span></span>|<span data-ttu-id="19706-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="19706-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="19706-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="19706-111">S_OK</span></span>|<span data-ttu-id="19706-112">`GetMemoryLoad`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="19706-112">`GetMemoryLoad` returned successfully.</span></span>|  
|<span data-ttu-id="19706-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="19706-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="19706-114">CLR non è stato caricato in un processo o CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="19706-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="19706-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="19706-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="19706-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="19706-116">The call timed out.</span></span>|  
|<span data-ttu-id="19706-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="19706-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="19706-118">Il chiamante non è proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="19706-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="19706-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="19706-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="19706-120">Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="19706-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="19706-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="19706-121">E_FAIL</span></span>|<span data-ttu-id="19706-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="19706-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="19706-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="19706-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="19706-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="19706-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19706-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="19706-125">Remarks</span></span>  
 <span data-ttu-id="19706-126">`GetMemoryLoad`esegue il wrapping `GlobalMemoryStatus` della funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="19706-126">`GetMemoryLoad` wraps the Win32 `GlobalMemoryStatus` function.</span></span> <span data-ttu-id="19706-127">Il valore `pMemoryLoad` di è `dwMemoryLoad` l'equivalente `MEMORYSTATUS` del campo `GlobalMemoryStatus`nella struttura restituita da .</span><span class="sxs-lookup"><span data-stu-id="19706-127">The value of `pMemoryLoad` is the equivalent of the `dwMemoryLoad` field in the `MEMORYSTATUS` structure returned from `GlobalMemoryStatus`.</span></span>  
  
 <span data-ttu-id="19706-128">Il runtime utilizza il valore restituito come euristica per il Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="19706-128">The runtime uses the return value as a heuristic for the garbage collector.</span></span> <span data-ttu-id="19706-129">Ad esempio, se l'host segnala che la maggior parte della memoria è in uso, il Garbage Collector può scegliere di raccogliere da più generazioni per aumentare la quantità di memoria che può potenzialmente diventare disponibile.</span><span class="sxs-lookup"><span data-stu-id="19706-129">For example, if the host reports that the majority of memory is in use, the garbage collector may elect to collect from multiple generations to increase the amount of memory that can potentially become available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19706-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="19706-130">Requirements</span></span>  
 <span data-ttu-id="19706-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19706-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19706-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19706-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19706-133">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19706-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19706-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19706-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19706-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19706-135">See also</span></span>

- <xref:System.GC?displayProperty=nameWithType>
- [<span data-ttu-id="19706-136">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="19706-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
