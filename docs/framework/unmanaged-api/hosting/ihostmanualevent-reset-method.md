---
title: Metodo IHostManualEvent::Reset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Reset
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e41922cb1732fe4e6727408692bbc7b99288e6dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="c3c23-102">Metodo IHostManualEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="c3c23-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="c3c23-103">Reimposta corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza da uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="c3c23-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3c23-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3c23-104">Syntax</span></span>  
  
```  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c3c23-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c3c23-105">Return Value</span></span>  
  
|<span data-ttu-id="c3c23-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3c23-106">HRESULT</span></span>|<span data-ttu-id="c3c23-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c3c23-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3c23-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3c23-108">S_OK</span></span>|<span data-ttu-id="c3c23-109">`Reset`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c3c23-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="c3c23-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c3c23-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c3c23-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c3c23-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c3c23-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c3c23-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c3c23-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c3c23-113">The call timed out.</span></span>|  
|<span data-ttu-id="c3c23-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c3c23-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c3c23-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="c3c23-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c3c23-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c3c23-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c3c23-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c3c23-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c3c23-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c3c23-118">E_FAIL</span></span>|<span data-ttu-id="c3c23-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c3c23-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c3c23-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c3c23-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c3c23-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c3c23-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3c23-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3c23-122">Requirements</span></span>  
 <span data-ttu-id="c3c23-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3c23-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3c23-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="c3c23-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3c23-125">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3c23-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3c23-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3c23-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3c23-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3c23-127">See Also</span></span>  
 [<span data-ttu-id="c3c23-128">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c3c23-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="c3c23-129">IHostAutoEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c3c23-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="c3c23-130">IHostManualEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c3c23-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="c3c23-131">IHostSemaphore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c3c23-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="c3c23-132">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c3c23-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
