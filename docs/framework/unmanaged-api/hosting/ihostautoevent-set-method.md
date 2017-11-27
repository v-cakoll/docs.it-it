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
ms.openlocfilehash: 07de2321c1c7760293c53ad77dd3bbdf7f82a564
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="51410-102">Metodo IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="51410-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="51410-103">Imposta l'oggetto corrente [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) istanza sullo stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="51410-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51410-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51410-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="51410-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="51410-105">Return Value</span></span>  
  
|<span data-ttu-id="51410-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51410-106">HRESULT</span></span>|<span data-ttu-id="51410-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51410-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51410-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="51410-108">S_OK</span></span>|<span data-ttu-id="51410-109">`Set`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="51410-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="51410-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="51410-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="51410-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="51410-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="51410-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="51410-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="51410-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="51410-113">The call timed out.</span></span>|  
|<span data-ttu-id="51410-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="51410-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="51410-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="51410-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="51410-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="51410-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="51410-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="51410-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="51410-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51410-118">E_FAIL</span></span>|<span data-ttu-id="51410-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="51410-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51410-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="51410-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="51410-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="51410-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51410-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51410-122">Requirements</span></span>  
 <span data-ttu-id="51410-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51410-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51410-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="51410-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51410-125">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="51410-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51410-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51410-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51410-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51410-127">See Also</span></span>  
 [<span data-ttu-id="51410-128">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="51410-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="51410-129">IHostAutoEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="51410-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="51410-130">IHostManualEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="51410-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="51410-131">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="51410-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
