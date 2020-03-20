---
title: Metodo ICLRGCManager2::SetGCStartupLimitsEx
ms.date: 03/30/2017
api_name:
- ICLRGCManager2.SetGCStartupLimitsEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type:
- apiref
ms.openlocfilehash: 9885149a71147db6eef13958b8ef825caa1d6ec6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176383"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="8b898-102">Metodo ICLRGCManager2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="8b898-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="8b898-103">Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8b898-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b898-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b898-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b898-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b898-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="8b898-106">[in] Dimensione specificata di un segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="8b898-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="8b898-107">La dimensione minima del segmento è 4 MB.</span><span class="sxs-lookup"><span data-stu-id="8b898-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="8b898-108">I segmenti possono essere aumentati in incrementi di 1 MB o superiore.</span><span class="sxs-lookup"><span data-stu-id="8b898-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="8b898-109">[in] Dimensione massima specificata per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="8b898-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="8b898-110">La dimensione minima di generazione 0 è 64 KB.</span><span class="sxs-lookup"><span data-stu-id="8b898-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b898-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8b898-111">Return Value</span></span>  
  
|<span data-ttu-id="8b898-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b898-112">HRESULT</span></span>|<span data-ttu-id="8b898-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8b898-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b898-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b898-114">S_OK</span></span>|<span data-ttu-id="8b898-115">`SetGCStartupLimitsEx`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="8b898-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="8b898-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b898-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b898-117">Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b898-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8b898-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8b898-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8b898-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8b898-119">The call timed out.</span></span>|  
|<span data-ttu-id="8b898-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b898-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8b898-121">Il chiamante non è proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="8b898-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8b898-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8b898-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8b898-123">Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8b898-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8b898-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b898-124">E_FAIL</span></span>|<span data-ttu-id="8b898-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8b898-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8b898-126">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8b898-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8b898-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8b898-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b898-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8b898-128">Remarks</span></span>  
 <span data-ttu-id="8b898-129">I valori `SetGCStartupLimitsEx` impostati possono essere specificati solo prima dell'avvio dell'host.</span><span class="sxs-lookup"><span data-stu-id="8b898-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="8b898-130">Le chiamate `SetGCStartupLimitsEx` successive a vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="8b898-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="8b898-131">Per impostare uno dei due parametri senza influire sull'altro, specificare 0 (zero) per il parametro che non si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="8b898-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b898-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b898-132">Requirements</span></span>  
 <span data-ttu-id="8b898-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b898-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b898-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b898-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b898-135">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b898-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b898-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b898-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b898-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b898-137">See also</span></span>

- [<span data-ttu-id="8b898-138">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="8b898-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="8b898-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="8b898-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="8b898-140">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="8b898-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="8b898-141">Interfaccia ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="8b898-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
