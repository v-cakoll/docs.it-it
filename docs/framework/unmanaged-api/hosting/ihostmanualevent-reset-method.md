---
title: Metodo IHostManualEvent::Reset
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
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d1bbd10437662fc8b7fbb52d65d196d7a519538b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="0b62c-102">Metodo IHostManualEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="0b62c-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="0b62c-103">Reimposta corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza da uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="0b62c-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b62c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b62c-104">Syntax</span></span>  
  
```  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0b62c-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0b62c-105">Return Value</span></span>  
  
|<span data-ttu-id="0b62c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b62c-106">HRESULT</span></span>|<span data-ttu-id="0b62c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b62c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b62c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b62c-108">S_OK</span></span>|<span data-ttu-id="0b62c-109">`Reset`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0b62c-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="0b62c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b62c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b62c-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0b62c-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b62c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b62c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b62c-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0b62c-113">The call timed out.</span></span>|  
|<span data-ttu-id="0b62c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b62c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b62c-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="0b62c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b62c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b62c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b62c-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0b62c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b62c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b62c-118">E_FAIL</span></span>|<span data-ttu-id="0b62c-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0b62c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b62c-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0b62c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b62c-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0b62c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b62c-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b62c-122">Requirements</span></span>  
 <span data-ttu-id="0b62c-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b62c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b62c-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="0b62c-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b62c-125">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b62c-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b62c-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b62c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b62c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b62c-127">See Also</span></span>  
 [<span data-ttu-id="0b62c-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="0b62c-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="0b62c-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="0b62c-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="0b62c-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="0b62c-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="0b62c-131">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="0b62c-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="0b62c-132">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="0b62c-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
