---
title: Metodo IHostManualEvent::Reset
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b2dcc342c218b3d6999d777e2658424c92f7e07a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438789"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="0c62e-102">Metodo IHostManualEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="0c62e-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="0c62e-103">Reimposta corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza da uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="0c62e-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c62e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c62e-104">Syntax</span></span>  
  
```  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0c62e-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0c62e-105">Return Value</span></span>  
  
|<span data-ttu-id="0c62e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c62e-106">HRESULT</span></span>|<span data-ttu-id="0c62e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c62e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c62e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c62e-108">S_OK</span></span>|<span data-ttu-id="0c62e-109">`Reset` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0c62e-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="0c62e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0c62e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0c62e-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0c62e-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0c62e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0c62e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0c62e-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0c62e-113">The call timed out.</span></span>|  
|<span data-ttu-id="0c62e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0c62e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0c62e-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="0c62e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0c62e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0c62e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0c62e-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0c62e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0c62e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0c62e-118">E_FAIL</span></span>|<span data-ttu-id="0c62e-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0c62e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0c62e-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0c62e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0c62e-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0c62e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c62e-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c62e-122">Requirements</span></span>  
 <span data-ttu-id="0c62e-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c62e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c62e-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="0c62e-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c62e-125">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0c62e-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c62e-126">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c62e-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c62e-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c62e-127">See Also</span></span>  
 [<span data-ttu-id="0c62e-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="0c62e-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="0c62e-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="0c62e-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="0c62e-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="0c62e-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="0c62e-131">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="0c62e-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="0c62e-132">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="0c62e-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
