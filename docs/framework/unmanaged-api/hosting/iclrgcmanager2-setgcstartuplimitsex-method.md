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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cba7b4a34835eb2f394aa71be8b907973cb1cd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700189"
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="30f45-102">Metodo ICLRGCManager2::SetGCStartupLimitsEx</span><span class="sxs-lookup"><span data-stu-id="30f45-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="30f45-103">Imposta le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0.</span><span class="sxs-lookup"><span data-stu-id="30f45-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30f45-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30f45-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30f45-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30f45-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="30f45-106">[in] La dimensione specificata per un segmento di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="30f45-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="30f45-107">Le dimensioni del segmento minimo sono 4 MB.</span><span class="sxs-lookup"><span data-stu-id="30f45-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="30f45-108">Segmenti possono essere un aumento con incrementi di 1 MB o maggiori.</span><span class="sxs-lookup"><span data-stu-id="30f45-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="30f45-109">[in] Le dimensioni massime specificata per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="30f45-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="30f45-110">La dimensione minima per la generazione 0 è 64 KB.</span><span class="sxs-lookup"><span data-stu-id="30f45-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30f45-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="30f45-111">Return Value</span></span>  
  
|<span data-ttu-id="30f45-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30f45-112">HRESULT</span></span>|<span data-ttu-id="30f45-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30f45-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30f45-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="30f45-114">S_OK</span></span>|<span data-ttu-id="30f45-115">`SetGCStartupLimitsEx` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="30f45-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="30f45-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30f45-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30f45-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="30f45-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30f45-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30f45-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30f45-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="30f45-119">The call timed out.</span></span>|  
|<span data-ttu-id="30f45-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30f45-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30f45-121">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="30f45-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30f45-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30f45-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30f45-123">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="30f45-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30f45-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30f45-124">E_FAIL</span></span>|<span data-ttu-id="30f45-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="30f45-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30f45-126">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="30f45-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30f45-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30f45-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30f45-128">Note</span><span class="sxs-lookup"><span data-stu-id="30f45-128">Remarks</span></span>  
 <span data-ttu-id="30f45-129">I valori che `SetGCStartupLimitsEx` set possono essere specificati solo prima dell'avvio dell'host.</span><span class="sxs-lookup"><span data-stu-id="30f45-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="30f45-130">Le chiamate successive a `SetGCStartupLimitsEx` vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="30f45-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="30f45-131">Per impostare dei parametri senza influire su altro, specificare 0 (zero) per il parametro che non si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="30f45-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30f45-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30f45-132">Requirements</span></span>  
 <span data-ttu-id="30f45-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30f45-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30f45-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30f45-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30f45-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="30f45-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30f45-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30f45-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f45-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30f45-137">See also</span></span>

- [<span data-ttu-id="30f45-138">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="30f45-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="30f45-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="30f45-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="30f45-140">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="30f45-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="30f45-141">Interfaccia ICLRGCManager2</span><span class="sxs-lookup"><span data-stu-id="30f45-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
