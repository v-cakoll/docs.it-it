---
title: Metodo IHostSyncManager::CreateSemaphore
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
ms.openlocfilehash: 02066d3923714e66bf287f1435b7854280c97cb7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195822"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="2d157-102">Metodo IHostSyncManager::CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="2d157-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="2d157-103">Crea un oggetto [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) per il Common Language Runtime (CLR) da utilizzare come semaforo per gli eventi di attesa.</span><span class="sxs-lookup"><span data-stu-id="2d157-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d157-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d157-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d157-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2d157-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="2d157-106">in Conteggio iniziale per `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="2d157-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="2d157-107">in Numero massimo di `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="2d157-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="2d157-108">out Puntatore all'indirizzo di un'istanza di `IHostSemaphore` o null se non è stato possibile creare il semaforo.</span><span class="sxs-lookup"><span data-stu-id="2d157-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d157-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2d157-109">Return Value</span></span>  
  
|<span data-ttu-id="2d157-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d157-110">HRESULT</span></span>|<span data-ttu-id="2d157-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d157-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d157-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d157-112">S_OK</span></span>|<span data-ttu-id="2d157-113">`CreateSemaphore` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2d157-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="2d157-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d157-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d157-115">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2d157-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d157-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d157-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d157-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2d157-117">The call timed out.</span></span>|  
|<span data-ttu-id="2d157-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d157-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d157-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="2d157-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d157-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d157-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d157-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2d157-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d157-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d157-122">E_FAIL</span></span>|<span data-ttu-id="2d157-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2d157-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d157-124">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2d157-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d157-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2d157-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2d157-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="2d157-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="2d157-127">Memoria insufficiente per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="2d157-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d157-128">Note</span><span class="sxs-lookup"><span data-stu-id="2d157-128">Remarks</span></span>  
 <span data-ttu-id="2d157-129">`CreateSemaphore` rispecchia la funzione Win32 con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="2d157-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="2d157-130">I parametri `dwInitial` e `dwMax` utilizzano la stessa semantica del conteggio dei semafori come i parametri Win32 `lInitialCount` e `lMaximumCount`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="2d157-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="2d157-131">`dwInitial` deve essere compreso tra zero e `dwMax`, inclusi.</span><span class="sxs-lookup"><span data-stu-id="2d157-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="2d157-132">`dwMax` deve essere maggiore di zero.</span><span class="sxs-lookup"><span data-stu-id="2d157-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d157-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d157-133">Requirements</span></span>  
 <span data-ttu-id="2d157-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d157-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d157-135">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2d157-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d157-136">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2d157-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d157-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d157-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d157-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d157-138">See also</span></span>

- [<span data-ttu-id="2d157-139">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="2d157-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="2d157-140">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="2d157-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="2d157-141">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="2d157-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
