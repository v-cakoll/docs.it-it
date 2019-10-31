---
title: Metodo IHostSemaphore::ReleaseSemaphore
ms.date: 03/30/2017
api_name:
- IHostSemaphore.ReleaseSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type:
- apiref
ms.openlocfilehash: 33a92365e7765befe669439eabefac607232ff15
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139471"
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="0f949-102">Metodo IHostSemaphore::ReleaseSemaphore</span><span class="sxs-lookup"><span data-stu-id="0f949-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="0f949-103">Aumenta il numero dell'istanza corrente di [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) in base al valore specificato.</span><span class="sxs-lookup"><span data-stu-id="0f949-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f949-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f949-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f949-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f949-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="0f949-106">in Valore in base al quale aumentare il numero dell'istanza del `IHostSemaphore` corrente.</span><span class="sxs-lookup"><span data-stu-id="0f949-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="0f949-107">Questa quantità deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="0f949-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="0f949-108">out Puntatore al conteggio precedente oppure null se il chiamante non richiede il conteggio precedente.</span><span class="sxs-lookup"><span data-stu-id="0f949-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f949-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0f949-109">Return Value</span></span>  
  
|<span data-ttu-id="0f949-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0f949-110">HRESULT</span></span>|<span data-ttu-id="0f949-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f949-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f949-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0f949-112">S_OK</span></span>|<span data-ttu-id="0f949-113">`ReleaseSemaphore` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0f949-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="0f949-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0f949-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0f949-115">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0f949-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0f949-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0f949-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0f949-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0f949-117">The call timed out.</span></span>|  
|<span data-ttu-id="0f949-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0f949-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0f949-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="0f949-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0f949-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0f949-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0f949-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0f949-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0f949-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0f949-122">E_FAIL</span></span>|<span data-ttu-id="0f949-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0f949-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0f949-124">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0f949-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0f949-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0f949-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f949-126">Note</span><span class="sxs-lookup"><span data-stu-id="0f949-126">Remarks</span></span>  
 <span data-ttu-id="0f949-127">CLR chiama in genere `ReleaseSemaphore` per notificare all'host che ha terminato l'uso di una risorsa, passando il valore 1 per il parametro di `lReleaseCount`.</span><span class="sxs-lookup"><span data-stu-id="0f949-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f949-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f949-128">Requirements</span></span>  
 <span data-ttu-id="0f949-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f949-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f949-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0f949-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0f949-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0f949-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0f949-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f949-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f949-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f949-133">See also</span></span>

- [<span data-ttu-id="0f949-134">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="0f949-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0f949-135">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="0f949-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="0f949-136">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="0f949-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="0f949-137">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="0f949-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="0f949-138">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="0f949-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
