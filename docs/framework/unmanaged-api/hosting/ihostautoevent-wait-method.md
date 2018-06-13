---
title: Metodo IHostAutoEvent::Wait
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Wait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7921f0361d7369cddf14dd1ab477529d1bbac481
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439361"
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="30d6b-102">Metodo IHostAutoEvent::Wait</span><span class="sxs-lookup"><span data-stu-id="30d6b-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="30d6b-103">Fa sì che l'oggetto corrente [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) in attesa fino a quando non è di proprietà istanza o un determinato periodo di tempo specificato.</span><span class="sxs-lookup"><span data-stu-id="30d6b-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30d6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30d6b-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30d6b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30d6b-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="30d6b-106">[in] Il numero di millisecondi corrente `IHostAutoEvent` istanza deve attendere prima della restituzione, se nessun thread o fiber acquisisce la proprietà.</span><span class="sxs-lookup"><span data-stu-id="30d6b-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="30d6b-107">[in] Uno del [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori, che specifica l'azione che l'host deve avere se questa operazione.</span><span class="sxs-lookup"><span data-stu-id="30d6b-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30d6b-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="30d6b-108">Return Value</span></span>  
  
|<span data-ttu-id="30d6b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30d6b-109">HRESULT</span></span>|<span data-ttu-id="30d6b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30d6b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30d6b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="30d6b-111">S_OK</span></span>|<span data-ttu-id="30d6b-112">`Wait` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="30d6b-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="30d6b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30d6b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30d6b-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="30d6b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30d6b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30d6b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30d6b-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="30d6b-116">The call timed out.</span></span>|  
|<span data-ttu-id="30d6b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30d6b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30d6b-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="30d6b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30d6b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30d6b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30d6b-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="30d6b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30d6b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30d6b-121">E_FAIL</span></span>|<span data-ttu-id="30d6b-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="30d6b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30d6b-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="30d6b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30d6b-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30d6b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="30d6b-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="30d6b-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="30d6b-126">L'host ha rilevato un deadlock durante l'intervallo di attesa e ha scelto l'evento rappresentato dall'oggetto corrente `IHostAutoEvent` istanza come vittima del deadlock.</span><span class="sxs-lookup"><span data-stu-id="30d6b-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30d6b-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30d6b-127">Requirements</span></span>  
 <span data-ttu-id="30d6b-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30d6b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30d6b-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="30d6b-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30d6b-130">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="30d6b-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30d6b-131">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30d6b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d6b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30d6b-132">See Also</span></span>  
 [<span data-ttu-id="30d6b-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="30d6b-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="30d6b-134">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="30d6b-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="30d6b-135">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="30d6b-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="30d6b-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="30d6b-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
