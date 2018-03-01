---
title: Metodo IHostManualEvent::Set
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostManualEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30dcb7232d6e0f7d42de48fefd2fbb9433a50405
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="8733a-102">Metodo IHostManualEvent::Set</span><span class="sxs-lookup"><span data-stu-id="8733a-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="8733a-103">Imposta l'oggetto corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza sullo stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="8733a-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8733a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8733a-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8733a-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8733a-105">Return Value</span></span>  
  
|<span data-ttu-id="8733a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8733a-106">HRESULT</span></span>|<span data-ttu-id="8733a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8733a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8733a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8733a-108">S_OK</span></span>|<span data-ttu-id="8733a-109">`Set`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8733a-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="8733a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8733a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8733a-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8733a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8733a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8733a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8733a-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8733a-113">The call timed out.</span></span>|  
|<span data-ttu-id="8733a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8733a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8733a-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="8733a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8733a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8733a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8733a-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8733a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8733a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8733a-118">E_FAIL</span></span>|<span data-ttu-id="8733a-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8733a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8733a-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8733a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8733a-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8733a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8733a-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8733a-122">Requirements</span></span>  
 <span data-ttu-id="8733a-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8733a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8733a-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8733a-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8733a-125">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8733a-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8733a-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8733a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8733a-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8733a-127">See Also</span></span>  
 [<span data-ttu-id="8733a-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="8733a-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="8733a-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="8733a-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="8733a-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="8733a-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="8733a-131">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="8733a-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="8733a-132">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="8733a-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
