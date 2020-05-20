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
ms.openlocfilehash: 0dce86a12ed3e93983ee62620fa0ddf7dfbc48f5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616944"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="c8c79-102">Metodo ICLRGCManager::SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="c8c79-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="c8c79-103">Imposta la dimensione di un segmento di Garbage Collection e la dimensione massima della generazione 0 del sistema Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c8c79-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c8c79-104">A partire da .NET Framework 4,5, è possibile impostare dimensioni del segmento e dimensioni massime 0 di generazione su valori maggiori di `DWORD` usando il metodo [ICLRGCManager2:: SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c8c79-104">Starting with the .NET Framework 4.5, you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c79-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8c79-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8c79-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8c79-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="c8c79-107">in Dimensione specificata di un segmento di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c8c79-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="c8c79-108">La dimensione minima del segmento è 4 MB.</span><span class="sxs-lookup"><span data-stu-id="c8c79-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="c8c79-109">I segmenti possono essere aumentati con incrementi di 1 MB o più grandi.</span><span class="sxs-lookup"><span data-stu-id="c8c79-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="c8c79-110">in Dimensione massima specificata per la generazione 0.</span><span class="sxs-lookup"><span data-stu-id="c8c79-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="c8c79-111">La dimensione minima di generazione 0 è 64 KB.</span><span class="sxs-lookup"><span data-stu-id="c8c79-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8c79-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c8c79-112">Return Value</span></span>  
  
|<span data-ttu-id="c8c79-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8c79-113">HRESULT</span></span>|<span data-ttu-id="c8c79-114">Description</span><span class="sxs-lookup"><span data-stu-id="c8c79-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8c79-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8c79-115">S_OK</span></span>|<span data-ttu-id="c8c79-116">`SetGCStartupLimits`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c8c79-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="c8c79-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c8c79-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c8c79-118">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c8c79-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c8c79-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c8c79-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c8c79-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c8c79-120">The call timed out.</span></span>|  
|<span data-ttu-id="c8c79-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c8c79-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c8c79-122">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c8c79-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c8c79-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c8c79-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c8c79-124">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c8c79-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c8c79-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8c79-125">E_FAIL</span></span>|<span data-ttu-id="c8c79-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c8c79-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c8c79-127">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c8c79-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c8c79-128">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c8c79-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8c79-129">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c8c79-129">Remarks</span></span>  
 <span data-ttu-id="c8c79-130">I valori `SetGCStartupLimits` impostati possono essere specificati una sola volta.</span><span class="sxs-lookup"><span data-stu-id="c8c79-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="c8c79-131">Le chiamate successive a `SetGCStartupLimits` vengono ignorate.</span><span class="sxs-lookup"><span data-stu-id="c8c79-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8c79-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8c79-132">Requirements</span></span>  
 <span data-ttu-id="c8c79-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8c79-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8c79-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c8c79-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8c79-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c8c79-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8c79-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8c79-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c79-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8c79-137">See also</span></span>

- [<span data-ttu-id="c8c79-138">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="c8c79-138">Automatic Memory Management</span></span>](../../../standard/automatic-memory-management.md)
- [<span data-ttu-id="c8c79-139">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="c8c79-139">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="c8c79-140">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="c8c79-140">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="c8c79-141">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="c8c79-141">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
