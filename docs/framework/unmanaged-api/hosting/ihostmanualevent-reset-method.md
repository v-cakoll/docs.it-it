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
ms.openlocfilehash: 049a0ae6d860c7c431d08af8ba4539656b8e5592
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804579"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="8c282-102">Metodo IHostManualEvent::Reset</span><span class="sxs-lookup"><span data-stu-id="8c282-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="8c282-103">Reimposta l'istanza corrente di [IHostManualEvent](ihostmanualevent-interface.md) su uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="8c282-103">Resets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c282-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c282-104">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8c282-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8c282-105">Return Value</span></span>  
  
|<span data-ttu-id="8c282-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c282-106">HRESULT</span></span>|<span data-ttu-id="8c282-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8c282-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8c282-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8c282-108">S_OK</span></span>|<span data-ttu-id="8c282-109">`Reset`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="8c282-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="8c282-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8c282-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8c282-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8c282-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8c282-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8c282-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8c282-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8c282-113">The call timed out.</span></span>|  
|<span data-ttu-id="8c282-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8c282-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8c282-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="8c282-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8c282-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8c282-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8c282-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8c282-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8c282-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8c282-118">E_FAIL</span></span>|<span data-ttu-id="8c282-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8c282-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8c282-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8c282-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8c282-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8c282-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c282-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8c282-122">Requirements</span></span>  
 <span data-ttu-id="8c282-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c282-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c282-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8c282-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8c282-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8c282-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8c282-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c282-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c282-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c282-127">See also</span></span>

- [<span data-ttu-id="8c282-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="8c282-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="8c282-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="8c282-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="8c282-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="8c282-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="8c282-131">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="8c282-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="8c282-132">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="8c282-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
