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
ms.openlocfilehash: 9c08a790d4dad748e5d09271bd870add22255b4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132617"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="4e3b1-102">Metodo IHostSyncManager::SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="4e3b1-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="4e3b1-103">Imposta l'istanza di [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) da associare all'istanza corrente di [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="4e3b1-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e3b1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e3b1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e3b1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e3b1-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="4e3b1-106">in Puntatore a un'istanza di `ICLRSyncManager` fornita dall'Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4e3b1-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e3b1-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4e3b1-107">Return Value</span></span>  
  
|<span data-ttu-id="4e3b1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e3b1-108">HRESULT</span></span>|<span data-ttu-id="4e3b1-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4e3b1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e3b1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e3b1-110">S_OK</span></span>|<span data-ttu-id="4e3b1-111">`SetCLRSyncManager` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="4e3b1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4e3b1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4e3b1-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4e3b1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4e3b1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4e3b1-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-115">The call timed out.</span></span>|  
|<span data-ttu-id="4e3b1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4e3b1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4e3b1-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4e3b1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4e3b1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4e3b1-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4e3b1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4e3b1-120">E_FAIL</span></span>|<span data-ttu-id="4e3b1-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4e3b1-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4e3b1-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e3b1-124">Note</span><span class="sxs-lookup"><span data-stu-id="4e3b1-124">Remarks</span></span>  
 <span data-ttu-id="4e3b1-125">Per facilitare la comunicazione tra l'host e CLR, le interfacce di hosting sono in genere in coppia.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="4e3b1-126">Un membro della coppia viene implementato dall'host e l'altro membro viene implementato da CLR.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="4e3b1-127">Come implementazione lato host, l'interfaccia `IHostSyncManager` corrisponde all'interfaccia `ICLRSyncManager` implementata da CLR.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="4e3b1-128">CLR chiama `SetCLRSyncManager` per fornire un'istanza di `ICLRSyncManager` per l'host da associare all'istanza di `IHostSyncManager` corrente.</span><span class="sxs-lookup"><span data-stu-id="4e3b1-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e3b1-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e3b1-129">Requirements</span></span>  
 <span data-ttu-id="4e3b1-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e3b1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e3b1-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4e3b1-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e3b1-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4e3b1-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e3b1-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e3b1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3b1-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e3b1-134">See also</span></span>

- [<span data-ttu-id="4e3b1-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="4e3b1-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="4e3b1-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="4e3b1-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
