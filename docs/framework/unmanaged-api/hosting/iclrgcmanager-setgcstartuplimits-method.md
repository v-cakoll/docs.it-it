---
title: Metodo ICLRGCManager::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf68d2284a6b2603ab97b5be27d6659857fd6c63
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656479"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="73e06-102">Metodo ICLRGCManager::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="73e06-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="73e06-103">Imposta le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0.</span><span class="sxs-lookup"><span data-stu-id="73e06-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="73e06-104">Inizia con il [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], è possibile impostare le dimensioni dei segmenti e dimensioni del numero massimo di generazioni 0 per i valori maggiori `DWORD` tramite il [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="73e06-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73e06-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="73e06-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="73e06-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="73e06-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="73e06-107">[in] La dimensione specificata per un segmento di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="73e06-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="73e06-108">Le dimensioni del segmento minimo sono 4 MB.</span><span class="sxs-lookup"><span data-stu-id="73e06-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="73e06-109">Segmenti possono essere un aumento con incrementi di 1 MB o maggiori.</span><span class="sxs-lookup"><span data-stu-id="73e06-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="73e06-110">[in] Le dimensioni massime specificata per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="73e06-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="73e06-111">La dimensione minima per la generazione 0 è 64 KB.</span><span class="sxs-lookup"><span data-stu-id="73e06-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="73e06-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="73e06-112">Return Value</span></span>  
  
|<span data-ttu-id="73e06-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="73e06-113">HRESULT</span></span>|<span data-ttu-id="73e06-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73e06-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="73e06-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="73e06-115">S_OK</span></span>|<span data-ttu-id="73e06-116">`SetGCStartupLimits` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="73e06-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="73e06-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="73e06-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="73e06-118">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="73e06-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="73e06-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="73e06-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="73e06-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="73e06-120">The call timed out.</span></span>|  
|<span data-ttu-id="73e06-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="73e06-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="73e06-122">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="73e06-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="73e06-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="73e06-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="73e06-124">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="73e06-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="73e06-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="73e06-125">E_FAIL</span></span>|<span data-ttu-id="73e06-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="73e06-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="73e06-127">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="73e06-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="73e06-128">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="73e06-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73e06-129">Note</span><span class="sxs-lookup"><span data-stu-id="73e06-129">Remarks</span></span>  
 <span data-ttu-id="73e06-130">I valori che `SetGCStartupLimits` set possono essere specificati una sola volta.</span><span class="sxs-lookup"><span data-stu-id="73e06-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="73e06-131">Le chiamate successive a `SetGCStartupLimits` vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="73e06-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73e06-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73e06-132">Requirements</span></span>  
 <span data-ttu-id="73e06-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73e06-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73e06-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="73e06-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73e06-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="73e06-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73e06-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73e06-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73e06-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73e06-137">See also</span></span>
- [<span data-ttu-id="73e06-138">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="73e06-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="73e06-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="73e06-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="73e06-140">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="73e06-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="73e06-141">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="73e06-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
