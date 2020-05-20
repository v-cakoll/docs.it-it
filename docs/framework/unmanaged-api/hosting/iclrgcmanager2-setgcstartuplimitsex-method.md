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
ms.openlocfilehash: f71c3b738d8e1f1670ac870d5e8c23ea9182d924
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703978"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="c9af2-102">Metodo ICLRGCManager2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="c9af2-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="c9af2-103">Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c9af2-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9af2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9af2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9af2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9af2-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="c9af2-106">in Dimensione specificata di un segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c9af2-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="c9af2-107">La dimensione minima del segmento è 4 MB.</span><span class="sxs-lookup"><span data-stu-id="c9af2-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="c9af2-108">I segmenti possono essere aumentati con incrementi di 1 MB o più grandi.</span><span class="sxs-lookup"><span data-stu-id="c9af2-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="c9af2-109">in Dimensione massima specificata per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="c9af2-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="c9af2-110">La dimensione minima di generazione 0 è 64 KB.</span><span class="sxs-lookup"><span data-stu-id="c9af2-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9af2-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c9af2-111">Return Value</span></span>  
  
|<span data-ttu-id="c9af2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9af2-112">HRESULT</span></span>|<span data-ttu-id="c9af2-113">Description</span><span class="sxs-lookup"><span data-stu-id="c9af2-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9af2-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9af2-114">S_OK</span></span>|<span data-ttu-id="c9af2-115">`SetGCStartupLimitsEx`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c9af2-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="c9af2-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9af2-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9af2-117">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c9af2-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9af2-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9af2-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9af2-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9af2-119">The call timed out.</span></span>|  
|<span data-ttu-id="c9af2-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9af2-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9af2-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c9af2-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9af2-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9af2-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9af2-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c9af2-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9af2-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9af2-124">E_FAIL</span></span>|<span data-ttu-id="c9af2-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c9af2-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9af2-126">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c9af2-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9af2-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c9af2-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9af2-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c9af2-128">Remarks</span></span>  
 <span data-ttu-id="c9af2-129">`SetGCStartupLimitsEx`È possibile specificare i valori impostati solo prima dell'avvio dell'host.</span><span class="sxs-lookup"><span data-stu-id="c9af2-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="c9af2-130">Le chiamate successive a `SetGCStartupLimitsEx` vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="c9af2-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="c9af2-131">Per impostare uno dei due parametri senza influire sull'altro, specificare 0 (zero) per il parametro che non si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="c9af2-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9af2-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9af2-132">Requirements</span></span>  
 <span data-ttu-id="c9af2-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9af2-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9af2-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c9af2-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9af2-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c9af2-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9af2-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9af2-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9af2-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9af2-137">See also</span></span>

- [<span data-ttu-id="c9af2-138">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="c9af2-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="c9af2-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="c9af2-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="c9af2-140">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="c9af2-140">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="c9af2-141">Interfaccia ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="c9af2-141">ICLRGCManager2 Interface</span></span>](iclrgcmanager2-interface.md)
