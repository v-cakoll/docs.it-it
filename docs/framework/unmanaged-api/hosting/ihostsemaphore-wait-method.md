---
title: Metodo IHostSemaphore::Wait
ms.date: 03/30/2017
api_name:
- IHostSemaphore.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type:
- apiref
ms.openlocfilehash: 22d570711c293dd8c0cc6fefd198dd46d6489bea
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803544"
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="4b2f5-102">Metodo IHostSemaphore::Wait</span><span class="sxs-lookup"><span data-stu-id="4b2f5-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="4b2f5-103">Fa in modo che l'istanza corrente di [IHostSemaphore](ihostsemaphore-interface.md) attenda finché non è di proprietà o la quantità di tempo specificata scade.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-103">Causes the current [IHostSemaphore](ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b2f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b2f5-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b2f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b2f5-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="4b2f5-106">in Numero di millisecondi di attesa prima che venga restituito, se l' `IHostSemaphore` istanza corrente non è di proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="4b2f5-107">in Uno dei valori [WAIT_OPTION](wait-option-enumeration.md) , che specifica l'azione che l'host deve eseguire se questa operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b2f5-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4b2f5-108">Return Value</span></span>  
  
|<span data-ttu-id="4b2f5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b2f5-109">HRESULT</span></span>|<span data-ttu-id="4b2f5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b2f5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b2f5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b2f5-111">S_OK</span></span>|<span data-ttu-id="4b2f5-112">`Wait`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="4b2f5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4b2f5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4b2f5-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4b2f5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4b2f5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4b2f5-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-116">The call timed out.</span></span>|  
|<span data-ttu-id="4b2f5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4b2f5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4b2f5-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4b2f5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4b2f5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4b2f5-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4b2f5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b2f5-121">E_FAIL</span></span>|<span data-ttu-id="4b2f5-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4b2f5-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4b2f5-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4b2f5-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="4b2f5-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="4b2f5-126">L'host ha rilevato un deadlock durante l'intervallo di attesa e ha scelto l' `IHostSemaphore` istanza corrente come vittima del deadlock.</span><span class="sxs-lookup"><span data-stu-id="4b2f5-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4b2f5-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b2f5-127">Requirements</span></span>  
 <span data-ttu-id="4b2f5-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b2f5-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b2f5-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4b2f5-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b2f5-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4b2f5-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b2f5-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b2f5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b2f5-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b2f5-132">See also</span></span>

- [<span data-ttu-id="4b2f5-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="4b2f5-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="4b2f5-134">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="4b2f5-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="4b2f5-135">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="4b2f5-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="4b2f5-136">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="4b2f5-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="4b2f5-137">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="4b2f5-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
