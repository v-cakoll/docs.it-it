---
title: Metodo IHostAutoEvent::Set
ms.date: 03/30/2017
api_name:
- IHostAutoEvent.Set
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5af9f55bdcfe23f0b2a051b33cb1280f312820a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227015"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="1e94f-102">Metodo IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="1e94f-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="1e94f-103">Imposta l'oggetto corrente [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) istanza da uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="1e94f-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e94f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e94f-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1e94f-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1e94f-105">Return Value</span></span>  
  
|<span data-ttu-id="1e94f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e94f-106">HRESULT</span></span>|<span data-ttu-id="1e94f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1e94f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1e94f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1e94f-108">S_OK</span></span>|<span data-ttu-id="1e94f-109">`Set` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1e94f-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="1e94f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1e94f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1e94f-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1e94f-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1e94f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1e94f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1e94f-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1e94f-113">The call timed out.</span></span>|  
|<span data-ttu-id="1e94f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1e94f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1e94f-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="1e94f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1e94f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1e94f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1e94f-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="1e94f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1e94f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1e94f-118">E_FAIL</span></span>|<span data-ttu-id="1e94f-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1e94f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1e94f-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="1e94f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1e94f-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1e94f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e94f-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e94f-122">Requirements</span></span>  
 <span data-ttu-id="1e94f-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e94f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e94f-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1e94f-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1e94f-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1e94f-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1e94f-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e94f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e94f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e94f-127">See also</span></span>

- [<span data-ttu-id="1e94f-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="1e94f-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="1e94f-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="1e94f-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="1e94f-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="1e94f-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="1e94f-131">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="1e94f-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
