---
title: Metodo ICLRGCManager::GetStats
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6ba88eebb963749247b318f14ef52bb116e3f0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="22ba2-102">Metodo ICLRGCManager::GetStats</span><span class="sxs-lookup"><span data-stu-id="22ba2-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="22ba2-103">Ottiene un set di statistiche sul sistema di garbage collection di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="22ba2-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22ba2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22ba2-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22ba2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22ba2-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="22ba2-106">[in, out] Oggetto [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) istanza che contiene le statistiche richieste.</span><span class="sxs-lookup"><span data-stu-id="22ba2-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22ba2-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="22ba2-107">Return Value</span></span>  
  
|<span data-ttu-id="22ba2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22ba2-108">HRESULT</span></span>|<span data-ttu-id="22ba2-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22ba2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22ba2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="22ba2-110">S_OK</span></span>|<span data-ttu-id="22ba2-111">`GetStats`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="22ba2-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="22ba2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22ba2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22ba2-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="22ba2-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22ba2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22ba2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22ba2-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22ba2-115">The call timed out.</span></span>|  
|<span data-ttu-id="22ba2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22ba2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22ba2-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="22ba2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22ba2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22ba2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22ba2-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="22ba2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22ba2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22ba2-120">E_FAIL</span></span>|<span data-ttu-id="22ba2-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="22ba2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22ba2-122">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="22ba2-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22ba2-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="22ba2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22ba2-124">Note</span><span class="sxs-lookup"><span data-stu-id="22ba2-124">Remarks</span></span>  
 <span data-ttu-id="22ba2-125">CLR calcola e restituisce solo le statistiche specificati tramite il `Flags` campo `pStats`.</span><span class="sxs-lookup"><span data-stu-id="22ba2-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="22ba2-126">Impostare il `Flags` uno o più valori di campo di [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumerazione per specificare le statistiche nel [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) struttura devono essere impostate.</span><span class="sxs-lookup"><span data-stu-id="22ba2-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="22ba2-127">Un esempio dell'utilizzo è come segue:</span><span class="sxs-lookup"><span data-stu-id="22ba2-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="22ba2-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22ba2-128">Requirements</span></span>  
 <span data-ttu-id="22ba2-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22ba2-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ba2-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="22ba2-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22ba2-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="22ba2-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22ba2-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22ba2-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ba2-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22ba2-133">See Also</span></span>  
 [<span data-ttu-id="22ba2-134">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="22ba2-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="22ba2-135">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="22ba2-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="22ba2-136">Enumerazione COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="22ba2-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 [<span data-ttu-id="22ba2-137">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="22ba2-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="22ba2-138">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="22ba2-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="22ba2-139">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="22ba2-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="22ba2-140">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="22ba2-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="22ba2-141">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="22ba2-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="22ba2-142">Hosting</span><span class="sxs-lookup"><span data-stu-id="22ba2-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
