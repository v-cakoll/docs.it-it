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
ms.openlocfilehash: b7994757a127686967d9863a574d0e1f8425ca86
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521218"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="63f19-102">Metodo IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="63f19-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="63f19-103">Imposta l'oggetto corrente [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) istanza da uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="63f19-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63f19-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63f19-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="63f19-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="63f19-105">Return Value</span></span>  
  
|<span data-ttu-id="63f19-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63f19-106">HRESULT</span></span>|<span data-ttu-id="63f19-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63f19-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63f19-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="63f19-108">S_OK</span></span>|<span data-ttu-id="63f19-109">`Set` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="63f19-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="63f19-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63f19-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63f19-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="63f19-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63f19-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63f19-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63f19-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="63f19-113">The call timed out.</span></span>|  
|<span data-ttu-id="63f19-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63f19-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63f19-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="63f19-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63f19-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63f19-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63f19-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="63f19-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63f19-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63f19-118">E_FAIL</span></span>|<span data-ttu-id="63f19-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="63f19-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63f19-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="63f19-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="63f19-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="63f19-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63f19-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63f19-122">Requirements</span></span>  
 <span data-ttu-id="63f19-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63f19-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63f19-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63f19-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63f19-125">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="63f19-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63f19-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63f19-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f19-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63f19-127">See also</span></span>
- [<span data-ttu-id="63f19-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="63f19-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="63f19-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="63f19-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="63f19-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="63f19-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="63f19-131">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="63f19-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
