---
title: Metodo ICLRGCManager::GetStats
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9df9263a0356b0c3c1a6d1da950c670f5a020d1e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966222"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="3e84c-102">Metodo ICLRGCManager::GetStats</span><span class="sxs-lookup"><span data-stu-id="3e84c-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="3e84c-103">Ottiene un set di statistiche correnti sul sistema Garbage Collection del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3e84c-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e84c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e84c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e84c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3e84c-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="3e84c-106">[in, out] Istanza di [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) che contiene le statistiche richieste.</span><span class="sxs-lookup"><span data-stu-id="3e84c-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e84c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3e84c-107">Return Value</span></span>  
  
|<span data-ttu-id="3e84c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e84c-108">HRESULT</span></span>|<span data-ttu-id="3e84c-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="3e84c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e84c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e84c-110">S_OK</span></span>|<span data-ttu-id="3e84c-111">`GetStats`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3e84c-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="3e84c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3e84c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3e84c-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3e84c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3e84c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e84c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3e84c-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3e84c-115">The call timed out.</span></span>|  
|<span data-ttu-id="3e84c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3e84c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3e84c-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="3e84c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3e84c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3e84c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3e84c-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3e84c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3e84c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3e84c-120">E_FAIL</span></span>|<span data-ttu-id="3e84c-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3e84c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3e84c-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3e84c-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3e84c-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3e84c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e84c-124">Note</span><span class="sxs-lookup"><span data-stu-id="3e84c-124">Remarks</span></span>  
 <span data-ttu-id="3e84c-125">CLR calcola e restituisce solo le statistiche specificate dal `Flags` `pStats`campo.</span><span class="sxs-lookup"><span data-stu-id="3e84c-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="3e84c-126">Impostare il `Flags` campo su uno o più valori dell'enumerazione [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) per specificare le statistiche nella struttura [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) da impostare.</span><span class="sxs-lookup"><span data-stu-id="3e84c-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="3e84c-127">Di seguito è riportato un esempio di utilizzo:</span><span class="sxs-lookup"><span data-stu-id="3e84c-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3e84c-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e84c-128">Requirements</span></span>  
 <span data-ttu-id="3e84c-129">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e84c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e84c-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3e84c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e84c-131">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3e84c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e84c-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e84c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e84c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e84c-133">See also</span></span>

- [<span data-ttu-id="3e84c-134">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="3e84c-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="3e84c-135">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="3e84c-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [<span data-ttu-id="3e84c-136">Enumerazione COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="3e84c-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="3e84c-137">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="3e84c-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="3e84c-138">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="3e84c-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="3e84c-139">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="3e84c-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="3e84c-140">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="3e84c-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="3e84c-141">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="3e84c-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="3e84c-142">Hosting</span><span class="sxs-lookup"><span data-stu-id="3e84c-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
