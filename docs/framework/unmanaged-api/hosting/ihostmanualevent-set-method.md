---
title: Metodo IHostManualEvent::Set
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a10d7d5069b8fe42144517a028ed9258b0633da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440603"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="00a15-102">Metodo IHostManualEvent::Set</span><span class="sxs-lookup"><span data-stu-id="00a15-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="00a15-103">Imposta l'oggetto corrente [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza sullo stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="00a15-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00a15-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00a15-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="00a15-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="00a15-105">Return Value</span></span>  
  
|<span data-ttu-id="00a15-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="00a15-106">HRESULT</span></span>|<span data-ttu-id="00a15-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="00a15-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="00a15-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="00a15-108">S_OK</span></span>|<span data-ttu-id="00a15-109">`Set` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="00a15-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="00a15-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="00a15-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="00a15-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="00a15-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="00a15-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="00a15-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="00a15-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="00a15-113">The call timed out.</span></span>|  
|<span data-ttu-id="00a15-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="00a15-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="00a15-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="00a15-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="00a15-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="00a15-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="00a15-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="00a15-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="00a15-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="00a15-118">E_FAIL</span></span>|<span data-ttu-id="00a15-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="00a15-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="00a15-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="00a15-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="00a15-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="00a15-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="00a15-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00a15-122">Requirements</span></span>  
 <span data-ttu-id="00a15-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00a15-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00a15-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="00a15-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="00a15-125">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="00a15-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="00a15-126">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00a15-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a15-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00a15-127">See Also</span></span>  
 [<span data-ttu-id="00a15-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="00a15-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="00a15-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="00a15-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="00a15-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="00a15-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="00a15-131">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="00a15-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="00a15-132">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="00a15-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
