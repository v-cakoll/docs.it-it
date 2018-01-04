---
title: Metodo IHostAutoEvent::Set
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAutoEvent.Set
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e83da6d4e360291eca501b5af34541f9e44543f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="39391-102">Metodo IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="39391-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="39391-103">Imposta l'oggetto corrente [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) istanza sullo stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="39391-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39391-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39391-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="39391-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="39391-105">Return Value</span></span>  
  
|<span data-ttu-id="39391-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39391-106">HRESULT</span></span>|<span data-ttu-id="39391-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39391-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39391-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="39391-108">S_OK</span></span>|<span data-ttu-id="39391-109">`Set`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="39391-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="39391-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="39391-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="39391-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="39391-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="39391-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="39391-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="39391-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="39391-113">The call timed out.</span></span>|  
|<span data-ttu-id="39391-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="39391-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="39391-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="39391-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="39391-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="39391-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="39391-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="39391-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="39391-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="39391-118">E_FAIL</span></span>|<span data-ttu-id="39391-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="39391-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="39391-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="39391-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="39391-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="39391-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="39391-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39391-122">Requirements</span></span>  
 <span data-ttu-id="39391-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39391-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39391-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="39391-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39391-125">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="39391-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="39391-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39391-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39391-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39391-127">See Also</span></span>  
 [<span data-ttu-id="39391-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="39391-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="39391-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="39391-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="39391-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="39391-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="39391-131">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="39391-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
