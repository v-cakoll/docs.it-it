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
ms.openlocfilehash: b5cd02f54a930942e1892f88fb3d8e926a6f3e1b
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804561"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="3408b-102">Metodo IHostManualEvent::Set</span><span class="sxs-lookup"><span data-stu-id="3408b-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="3408b-103">Imposta l'istanza corrente di [IHostManualEvent](ihostmanualevent-interface.md) su uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="3408b-103">Sets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3408b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3408b-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3408b-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3408b-105">Return Value</span></span>  
  
|<span data-ttu-id="3408b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3408b-106">HRESULT</span></span>|<span data-ttu-id="3408b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3408b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3408b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3408b-108">S_OK</span></span>|<span data-ttu-id="3408b-109">`Set`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="3408b-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="3408b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3408b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3408b-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3408b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3408b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3408b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3408b-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3408b-113">The call timed out.</span></span>|  
|<span data-ttu-id="3408b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3408b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3408b-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="3408b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3408b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3408b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3408b-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3408b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3408b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3408b-118">E_FAIL</span></span>|<span data-ttu-id="3408b-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3408b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3408b-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3408b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3408b-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3408b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3408b-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3408b-122">Requirements</span></span>  
 <span data-ttu-id="3408b-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3408b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3408b-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3408b-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3408b-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3408b-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3408b-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3408b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3408b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3408b-127">See also</span></span>

- [<span data-ttu-id="3408b-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="3408b-128">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="3408b-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="3408b-129">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="3408b-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="3408b-130">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="3408b-131">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="3408b-131">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="3408b-132">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="3408b-132">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
