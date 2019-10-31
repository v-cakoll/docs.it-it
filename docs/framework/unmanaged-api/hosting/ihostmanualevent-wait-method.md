---
title: Metodo IHostManualEvent::Wait
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Wait
helpviewer_keywords:
- IHostManualEvent::Wait method [.NET Framework hosting]
- Wait method, IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 1fbb7d8b-8a23-4c2b-8376-1a70cd2d6030
topic_type:
- apiref
ms.openlocfilehash: f39a5af706ef49e3f6e4bd040d752e5698063b29
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136752"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="82e70-102">Metodo IHostManualEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="82e70-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="82e70-103">Fa in modo che l'istanza corrente di [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) attenda fino a quando non è di proprietà o che trascorre un intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="82e70-103">Causes the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82e70-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="82e70-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82e70-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="82e70-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="82e70-106">in Numero di millisecondi di attesa prima che venga restituito, se l'istanza di `IHostManualEvent` corrente non è di proprietà.</span><span class="sxs-lookup"><span data-stu-id="82e70-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="82e70-107">in Uno dei valori di [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) , che indica l'azione che l'host deve eseguire se questa operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="82e70-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82e70-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="82e70-108">Return Value</span></span>  
  
|<span data-ttu-id="82e70-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82e70-109">HRESULT</span></span>|<span data-ttu-id="82e70-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="82e70-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82e70-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="82e70-111">S_OK</span></span>|<span data-ttu-id="82e70-112">`Wait` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="82e70-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="82e70-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="82e70-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="82e70-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="82e70-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="82e70-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="82e70-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="82e70-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="82e70-116">The call timed out.</span></span>|  
|<span data-ttu-id="82e70-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="82e70-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="82e70-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="82e70-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="82e70-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="82e70-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="82e70-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="82e70-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="82e70-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="82e70-121">E_FAIL</span></span>|<span data-ttu-id="82e70-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="82e70-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="82e70-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="82e70-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="82e70-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="82e70-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="82e70-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="82e70-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="82e70-126">L'host ha rilevato un deadlock durante l'intervallo di attesa e ha scelto l'istanza `IHostManualEvent` corrente come vittima del deadlock.</span><span class="sxs-lookup"><span data-stu-id="82e70-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82e70-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="82e70-127">Requirements</span></span>  
 <span data-ttu-id="82e70-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82e70-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82e70-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="82e70-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="82e70-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="82e70-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82e70-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82e70-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e70-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="82e70-132">See also</span></span>

- [<span data-ttu-id="82e70-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="82e70-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="82e70-134">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="82e70-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="82e70-135">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="82e70-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="82e70-136">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="82e70-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="82e70-137">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="82e70-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
