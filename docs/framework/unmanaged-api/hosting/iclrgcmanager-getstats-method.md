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
ms.openlocfilehash: 1e881b4a55a99bac3f9ca0e8db1556807b888f13
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616967"
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="00ed7-102">Metodo ICLRGCManager::GetStats</span><span class="sxs-lookup"><span data-stu-id="00ed7-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="00ed7-103">Ottiene un set di statistiche correnti sul sistema Garbage Collection del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="00ed7-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ed7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00ed7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00ed7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="00ed7-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="00ed7-106">[in, out] Istanza [COR_GC_STATS](cor-gc-stats-structure.md) contenente le statistiche richieste.</span><span class="sxs-lookup"><span data-stu-id="00ed7-106">[in, out] A [COR_GC_STATS](cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00ed7-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="00ed7-107">Return Value</span></span>  
  
|<span data-ttu-id="00ed7-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00ed7-108">HRESULT</span></span>|<span data-ttu-id="00ed7-109">Description</span><span class="sxs-lookup"><span data-stu-id="00ed7-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00ed7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="00ed7-110">S_OK</span></span>|<span data-ttu-id="00ed7-111">`GetStats`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="00ed7-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="00ed7-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00ed7-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00ed7-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="00ed7-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="00ed7-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="00ed7-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="00ed7-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="00ed7-115">The call timed out.</span></span>|  
|<span data-ttu-id="00ed7-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="00ed7-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="00ed7-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="00ed7-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="00ed7-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="00ed7-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="00ed7-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="00ed7-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="00ed7-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00ed7-120">E_FAIL</span></span>|<span data-ttu-id="00ed7-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="00ed7-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="00ed7-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="00ed7-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="00ed7-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="00ed7-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00ed7-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="00ed7-124">Remarks</span></span>  
 <span data-ttu-id="00ed7-125">CLR calcola e restituisce solo le statistiche specificate dal `Flags` campo `pStats` .</span><span class="sxs-lookup"><span data-stu-id="00ed7-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="00ed7-126">Impostare il `Flags` campo su uno o più valori dell'enumerazione [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) per specificare le statistiche nella struttura [COR_GC_STATS](cor-gc-stats-structure.md) da impostare.</span><span class="sxs-lookup"><span data-stu-id="00ed7-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="00ed7-127">Di seguito è riportato un esempio di utilizzo:</span><span class="sxs-lookup"><span data-stu-id="00ed7-127">An example of the usage is as follows:</span></span>  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="00ed7-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00ed7-128">Requirements</span></span>  
 <span data-ttu-id="00ed7-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00ed7-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00ed7-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="00ed7-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00ed7-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="00ed7-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00ed7-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00ed7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ed7-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00ed7-133">See also</span></span>

- [<span data-ttu-id="00ed7-134">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="00ed7-134">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="00ed7-135">Struttura COR_GC_STATS</span><span class="sxs-lookup"><span data-stu-id="00ed7-135">COR_GC_STATS Structure</span></span>](cor-gc-stats-structure.md)
- [<span data-ttu-id="00ed7-136">Enumerazione COR_GC_STAT_TYPES</span><span class="sxs-lookup"><span data-stu-id="00ed7-136">COR_GC_STAT_TYPES Enumeration</span></span>](cor-gc-stat-types-enumeration.md)
- [<span data-ttu-id="00ed7-137">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="00ed7-137">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="00ed7-138">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="00ed7-138">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="00ed7-139">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="00ed7-139">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="00ed7-140">Interfacce di hosting CLR</span><span class="sxs-lookup"><span data-stu-id="00ed7-140">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="00ed7-141">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="00ed7-141">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="00ed7-142">Hosting</span><span class="sxs-lookup"><span data-stu-id="00ed7-142">Hosting</span></span>](index.md)
