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
ms.openlocfilehash: e443ec3f743d56f0fe7e4e1c794f16bab2db8314
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763959"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="9f955-102">Metodo IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="9f955-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="9f955-103">Imposta l'oggetto corrente [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) istanza da uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="9f955-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f955-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f955-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9f955-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f955-105">Return Value</span></span>  
  
|<span data-ttu-id="9f955-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f955-106">HRESULT</span></span>|<span data-ttu-id="9f955-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f955-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f955-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9f955-108">S_OK</span></span>|<span data-ttu-id="9f955-109">`Set` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="9f955-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="9f955-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9f955-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9f955-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f955-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9f955-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9f955-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9f955-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9f955-113">The call timed out.</span></span>|  
|<span data-ttu-id="9f955-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9f955-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9f955-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="9f955-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9f955-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9f955-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9f955-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9f955-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9f955-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9f955-118">E_FAIL</span></span>|<span data-ttu-id="9f955-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9f955-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9f955-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9f955-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9f955-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9f955-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9f955-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f955-122">Requirements</span></span>  
 <span data-ttu-id="9f955-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f955-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f955-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9f955-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f955-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9f955-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f955-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f955-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f955-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f955-127">See also</span></span>

- [<span data-ttu-id="9f955-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="9f955-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9f955-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="9f955-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="9f955-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="9f955-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="9f955-131">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="9f955-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
