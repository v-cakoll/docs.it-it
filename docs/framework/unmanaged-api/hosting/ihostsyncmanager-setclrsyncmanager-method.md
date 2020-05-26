---
title: Metodo IHostSyncManager::SetCLRSyncManager
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
ms.openlocfilehash: bbeae2561d2d340c1a7dfed38e740dcc6838e4da
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803104"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="98972-102">Metodo IHostSyncManager::SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="98972-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="98972-103">Imposta l'istanza di [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) da associare all'istanza corrente di [IHostSyncManager](ihostsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="98972-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98972-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98972-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98972-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="98972-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="98972-106">in Puntatore a un' `ICLRSyncManager` istanza fornita dalla Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="98972-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98972-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="98972-107">Return Value</span></span>  
  
|<span data-ttu-id="98972-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98972-108">HRESULT</span></span>|<span data-ttu-id="98972-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98972-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98972-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="98972-110">S_OK</span></span>|<span data-ttu-id="98972-111">`SetCLRSyncManager`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="98972-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="98972-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="98972-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="98972-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="98972-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="98972-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="98972-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="98972-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="98972-115">The call timed out.</span></span>|  
|<span data-ttu-id="98972-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="98972-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="98972-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="98972-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="98972-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="98972-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="98972-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="98972-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="98972-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="98972-120">E_FAIL</span></span>|<span data-ttu-id="98972-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="98972-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="98972-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="98972-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="98972-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="98972-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98972-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="98972-124">Remarks</span></span>  
 <span data-ttu-id="98972-125">Per facilitare la comunicazione tra l'host e CLR, le interfacce di hosting sono in genere in coppia.</span><span class="sxs-lookup"><span data-stu-id="98972-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="98972-126">Un membro della coppia viene implementato dall'host e l'altro membro viene implementato da CLR.</span><span class="sxs-lookup"><span data-stu-id="98972-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="98972-127">Come implementazione lato host, l' `IHostSyncManager` interfaccia corrisponde all' `ICLRSyncManager` interfaccia implementata da CLR.</span><span class="sxs-lookup"><span data-stu-id="98972-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="98972-128">CLR chiama `SetCLRSyncManager` per fornire un' `ICLRSyncManager` istanza dell'host da associare all' `IHostSyncManager` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="98972-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98972-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98972-129">Requirements</span></span>  
 <span data-ttu-id="98972-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98972-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98972-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="98972-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98972-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="98972-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98972-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98972-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98972-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98972-134">See also</span></span>

- [<span data-ttu-id="98972-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="98972-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="98972-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="98972-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
