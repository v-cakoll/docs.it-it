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
ms.openlocfilehash: 8b25f73e9af77faadbc691255cb3139498f5d25c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779703"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="a4ead-102">Metodo ICLRGCManager::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="a4ead-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="a4ead-103">Imposta le dimensioni di un segmento di garbage collection e le dimensioni massime della generazione del sistema di garbage collection 0.</span><span class="sxs-lookup"><span data-stu-id="a4ead-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4ead-104">A partire da .NET Framework 4.5, è possibile impostare dimensioni segmento e del numero massimo di generazioni 0 per i valori maggiori `DWORD` usando il [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="a4ead-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4ead-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4ead-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4ead-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4ead-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="a4ead-107">[in] La dimensione specificata per un segmento di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="a4ead-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="a4ead-108">Le dimensioni del segmento minimo sono 4 MB.</span><span class="sxs-lookup"><span data-stu-id="a4ead-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="a4ead-109">Segmenti possono essere un aumento con incrementi di 1 MB o maggiori.</span><span class="sxs-lookup"><span data-stu-id="a4ead-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="a4ead-110">[in] Le dimensioni massime specificata per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="a4ead-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="a4ead-111">La dimensione minima per la generazione 0 è 64 KB.</span><span class="sxs-lookup"><span data-stu-id="a4ead-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4ead-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a4ead-112">Return Value</span></span>  
  
|<span data-ttu-id="a4ead-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a4ead-113">HRESULT</span></span>|<span data-ttu-id="a4ead-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a4ead-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4ead-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a4ead-115">S_OK</span></span>|<span data-ttu-id="a4ead-116">`SetGCStartupLimits` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a4ead-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="a4ead-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a4ead-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a4ead-118">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a4ead-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a4ead-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a4ead-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a4ead-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a4ead-120">The call timed out.</span></span>|  
|<span data-ttu-id="a4ead-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a4ead-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a4ead-122">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="a4ead-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a4ead-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a4ead-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a4ead-124">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a4ead-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a4ead-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a4ead-125">E_FAIL</span></span>|<span data-ttu-id="a4ead-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a4ead-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a4ead-127">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a4ead-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a4ead-128">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a4ead-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4ead-129">Note</span><span class="sxs-lookup"><span data-stu-id="a4ead-129">Remarks</span></span>  
 <span data-ttu-id="a4ead-130">I valori che `SetGCStartupLimits` set possono essere specificati una sola volta.</span><span class="sxs-lookup"><span data-stu-id="a4ead-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="a4ead-131">Le chiamate successive a `SetGCStartupLimits` vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="a4ead-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4ead-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4ead-132">Requirements</span></span>  
 <span data-ttu-id="a4ead-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4ead-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4ead-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a4ead-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4ead-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a4ead-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4ead-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4ead-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ead-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4ead-137">See also</span></span>

- [<span data-ttu-id="a4ead-138">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="a4ead-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="a4ead-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="a4ead-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="a4ead-140">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="a4ead-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a4ead-141">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="a4ead-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
