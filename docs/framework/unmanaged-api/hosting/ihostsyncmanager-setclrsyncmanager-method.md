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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aef7866d912951972ec9c66efccca671c3787da6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443687"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="95dbd-102">Metodo IHostSyncManager::SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="95dbd-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="95dbd-103">Imposta il [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) istanza da associare all'oggetto corrente [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="95dbd-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95dbd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95dbd-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95dbd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95dbd-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="95dbd-106">[in] Un puntatore a un `ICLRSyncManager` istanza fornita da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="95dbd-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95dbd-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="95dbd-107">Return Value</span></span>  
  
|<span data-ttu-id="95dbd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95dbd-108">HRESULT</span></span>|<span data-ttu-id="95dbd-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95dbd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95dbd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="95dbd-110">S_OK</span></span>|<span data-ttu-id="95dbd-111">`SetCLRSyncManager` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="95dbd-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="95dbd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95dbd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95dbd-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="95dbd-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95dbd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95dbd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95dbd-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="95dbd-115">The call timed out.</span></span>|  
|<span data-ttu-id="95dbd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95dbd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95dbd-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="95dbd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95dbd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95dbd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95dbd-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="95dbd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95dbd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95dbd-120">E_FAIL</span></span>|<span data-ttu-id="95dbd-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="95dbd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95dbd-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="95dbd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95dbd-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="95dbd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95dbd-124">Note</span><span class="sxs-lookup"><span data-stu-id="95dbd-124">Remarks</span></span>  
 <span data-ttu-id="95dbd-125">Per facilitare la comunicazione tra l'host e CLR, interfacce di hosting sono generalmente di coppie.</span><span class="sxs-lookup"><span data-stu-id="95dbd-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="95dbd-126">Un membro della coppia viene implementato dall'host e l'altro membro viene implementato da CLR.</span><span class="sxs-lookup"><span data-stu-id="95dbd-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="95dbd-127">Come implementazione sul lato host, il `IHostSyncManager` interfaccia corrisponde alla `ICLRSyncManager` interfaccia implementata da CLR.</span><span class="sxs-lookup"><span data-stu-id="95dbd-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="95dbd-128">CLR chiama `SetCLRSyncManager` per fornire un `ICLRSyncManager` istanza dell'host da associare corrente `IHostSyncManager` istanza.</span><span class="sxs-lookup"><span data-stu-id="95dbd-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95dbd-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95dbd-129">Requirements</span></span>  
 <span data-ttu-id="95dbd-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95dbd-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95dbd-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="95dbd-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95dbd-132">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="95dbd-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95dbd-133">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95dbd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95dbd-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95dbd-134">See Also</span></span>  
 [<span data-ttu-id="95dbd-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="95dbd-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="95dbd-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="95dbd-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
