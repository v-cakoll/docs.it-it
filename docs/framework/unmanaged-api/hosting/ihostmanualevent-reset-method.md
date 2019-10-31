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
ms.openlocfilehash: 464093291648d7c5c1f2001fbaef85fcd5d592de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136798"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="51c48-102">Metodo IHostManualEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="51c48-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="51c48-103">Reimposta l'istanza corrente di [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) su uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="51c48-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51c48-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51c48-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="51c48-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="51c48-105">Return Value</span></span>  
  
|<span data-ttu-id="51c48-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51c48-106">HRESULT</span></span>|<span data-ttu-id="51c48-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51c48-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51c48-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="51c48-108">S_OK</span></span>|<span data-ttu-id="51c48-109">`Reset` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="51c48-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="51c48-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="51c48-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="51c48-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="51c48-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="51c48-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="51c48-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="51c48-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="51c48-113">The call timed out.</span></span>|  
|<span data-ttu-id="51c48-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="51c48-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="51c48-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="51c48-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="51c48-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="51c48-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="51c48-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="51c48-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="51c48-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51c48-118">E_FAIL</span></span>|<span data-ttu-id="51c48-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="51c48-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51c48-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="51c48-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="51c48-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="51c48-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="51c48-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51c48-122">Requirements</span></span>  
 <span data-ttu-id="51c48-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51c48-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51c48-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="51c48-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51c48-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="51c48-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51c48-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51c48-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51c48-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51c48-127">See also</span></span>

- [<span data-ttu-id="51c48-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="51c48-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="51c48-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="51c48-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="51c48-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="51c48-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="51c48-131">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="51c48-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="51c48-132">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="51c48-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
