---
title: Metodo IHostManualEvent::Set
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Set
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f093e1278e74553ed78445e0cb83127a219e622
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="1e345-102">Metodo IHostManualEvent::Set</span><span class="sxs-lookup"><span data-stu-id="1e345-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="1e345-103">Imposta l'oggetto corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza sullo stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="1e345-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e345-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e345-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1e345-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1e345-105">Return Value</span></span>  
  
|<span data-ttu-id="1e345-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e345-106">HRESULT</span></span>|<span data-ttu-id="1e345-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e345-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e345-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e345-108">S_OK</span></span>|<span data-ttu-id="1e345-109">`Set`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1e345-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="1e345-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1e345-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1e345-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1e345-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1e345-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1e345-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1e345-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1e345-113">The call timed out.</span></span>|  
|<span data-ttu-id="1e345-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1e345-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1e345-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="1e345-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1e345-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1e345-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1e345-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="1e345-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1e345-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1e345-118">E_FAIL</span></span>|<span data-ttu-id="1e345-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1e345-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1e345-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="1e345-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1e345-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1e345-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e345-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e345-122">Requirements</span></span>  
 <span data-ttu-id="1e345-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e345-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e345-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="1e345-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e345-125">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e345-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e345-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e345-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e345-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e345-127">See Also</span></span>  
 [<span data-ttu-id="1e345-128">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1e345-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="1e345-129">IHostAutoEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1e345-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="1e345-130">IHostManualEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1e345-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="1e345-131">IHostSemaphore (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1e345-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="1e345-132">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1e345-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
