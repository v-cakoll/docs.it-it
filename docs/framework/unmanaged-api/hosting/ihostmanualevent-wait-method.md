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
ms.openlocfilehash: 6d0276764a07d5bb202d66b653fdf5cb96320c08
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804559"
---
# <a name="ihostmanualeventwait-method"></a><span data-ttu-id="2d790-102">Metodo IHostManualEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="2d790-102">IHostManualEvent::Wait Method</span></span>
<span data-ttu-id="2d790-103">Fa in modo che l'istanza corrente di [IHostManualEvent](ihostmanualevent-interface.md) attenda fino a quando non è di proprietà o che trascorre un intervallo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="2d790-103">Causes the current [IHostManualEvent](ihostmanualevent-interface.md) instance to wait until it is owned, or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d790-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2d790-104">Syntax</span></span>  
  
```cpp  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d790-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2d790-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="2d790-106">in Numero di millisecondi di attesa prima che venga restituito, se l' `IHostManualEvent` istanza corrente non è di proprietà.</span><span class="sxs-lookup"><span data-stu-id="2d790-106">[in] The number of milliseconds to wait before returning, if the current `IHostManualEvent` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="2d790-107">in Uno dei valori [WAIT_OPTION](wait-option-enumeration.md) , che indica l'azione che l'host deve eseguire se questa operazione si blocca.</span><span class="sxs-lookup"><span data-stu-id="2d790-107">[in] One of the [WAIT_OPTION](wait-option-enumeration.md) values, indicating the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d790-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2d790-108">Return Value</span></span>  
  
|<span data-ttu-id="2d790-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d790-109">HRESULT</span></span>|<span data-ttu-id="2d790-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d790-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d790-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d790-111">S_OK</span></span>|<span data-ttu-id="2d790-112">`Wait`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="2d790-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="2d790-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d790-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d790-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2d790-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2d790-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2d790-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2d790-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2d790-116">The call timed out.</span></span>|  
|<span data-ttu-id="2d790-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2d790-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2d790-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="2d790-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2d790-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2d790-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2d790-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2d790-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2d790-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d790-121">E_FAIL</span></span>|<span data-ttu-id="2d790-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2d790-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2d790-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2d790-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2d790-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2d790-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2d790-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="2d790-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="2d790-126">L'host ha rilevato un deadlock durante l'intervallo di attesa e ha scelto l' `IHostManualEvent` istanza corrente come vittima del deadlock.</span><span class="sxs-lookup"><span data-stu-id="2d790-126">The host detected a deadlock during the wait interval, and chose the current `IHostManualEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d790-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2d790-127">Requirements</span></span>  
 <span data-ttu-id="2d790-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d790-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d790-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2d790-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d790-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2d790-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d790-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d790-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d790-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d790-132">See also</span></span>

- [<span data-ttu-id="2d790-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="2d790-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="2d790-134">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="2d790-134">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="2d790-135">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="2d790-135">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="2d790-136">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="2d790-136">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="2d790-137">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="2d790-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
