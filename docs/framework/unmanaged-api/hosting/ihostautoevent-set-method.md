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
ms.openlocfilehash: 792b735522580eb7460da703899a00781e525419
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124441"
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="5884d-102">Metodo IHostAutoEvent::Set</span><span class="sxs-lookup"><span data-stu-id="5884d-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="5884d-103">Imposta l'istanza corrente di [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) su uno stato segnalato.</span><span class="sxs-lookup"><span data-stu-id="5884d-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5884d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5884d-104">Syntax</span></span>  
  
```cpp  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5884d-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5884d-105">Return Value</span></span>  
  
|<span data-ttu-id="5884d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5884d-106">HRESULT</span></span>|<span data-ttu-id="5884d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5884d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5884d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5884d-108">S_OK</span></span>|<span data-ttu-id="5884d-109">`Set` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5884d-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="5884d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5884d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5884d-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5884d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5884d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5884d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5884d-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5884d-113">The call timed out.</span></span>|  
|<span data-ttu-id="5884d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5884d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5884d-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="5884d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5884d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5884d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5884d-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5884d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5884d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5884d-118">E_FAIL</span></span>|<span data-ttu-id="5884d-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5884d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5884d-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5884d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5884d-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5884d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5884d-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5884d-122">Requirements</span></span>  
 <span data-ttu-id="5884d-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5884d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5884d-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5884d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5884d-125">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5884d-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5884d-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5884d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5884d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5884d-127">See also</span></span>

- [<span data-ttu-id="5884d-128">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="5884d-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="5884d-129">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="5884d-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="5884d-130">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="5884d-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="5884d-131">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="5884d-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
