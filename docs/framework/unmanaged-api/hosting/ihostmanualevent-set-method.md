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
ms.openlocfilehash: 1114fc744ac1811585f2c5a94858b75eda00815c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136764"
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="25391-102">Metodo IHostManualEvent::Set</span><span class="sxs-lookup"><span data-stu-id="25391-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="25391-103">Imposta l'istanza corrente di [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) su uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="25391-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25391-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25391-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="25391-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="25391-105">Return Value</span></span>  
  
|<span data-ttu-id="25391-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25391-106">HRESULT</span></span>|<span data-ttu-id="25391-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25391-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25391-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="25391-108">S_OK</span></span>|<span data-ttu-id="25391-109">`Set` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="25391-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="25391-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="25391-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="25391-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="25391-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="25391-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="25391-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="25391-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="25391-113">The call timed out.</span></span>|  
|<span data-ttu-id="25391-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="25391-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="25391-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="25391-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="25391-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="25391-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="25391-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="25391-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="25391-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="25391-118">E_FAIL</span></span>|<span data-ttu-id="25391-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="25391-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="25391-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="25391-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="25391-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="25391-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="25391-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25391-122">Requirements</span></span>  
 <span data-ttu-id="25391-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25391-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25391-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="25391-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25391-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="25391-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25391-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25391-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25391-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25391-127">See also</span></span>

- [<span data-ttu-id="25391-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="25391-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="25391-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="25391-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="25391-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="25391-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="25391-131">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="25391-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="25391-132">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="25391-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
