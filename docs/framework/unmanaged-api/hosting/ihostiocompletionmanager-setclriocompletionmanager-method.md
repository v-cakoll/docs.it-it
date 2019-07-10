---
title: Metodo IHostIoCompletionManager::SetCLRIoCompletionManager
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97d4561c34c03eefc7487f5f96b7a490a480ac19
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780765"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="63bb3-102">Metodo IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="63bb3-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="63bb3-103">Fornisce l'host con un puntatore a interfaccia per il [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) istanza implementato da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="63bb3-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63bb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63bb3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63bb3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="63bb3-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="63bb3-106">[in] Un puntatore a interfaccia per un `ICLRIoCompletionManager` istanza fornita da CLR.</span><span class="sxs-lookup"><span data-stu-id="63bb3-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63bb3-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="63bb3-107">Return Value</span></span>  
  
|<span data-ttu-id="63bb3-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="63bb3-108">HRESULT</span></span>|<span data-ttu-id="63bb3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63bb3-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="63bb3-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="63bb3-110">S_OK</span></span>|<span data-ttu-id="63bb3-111">`SetCLRIoCompletionManager` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="63bb3-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="63bb3-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="63bb3-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="63bb3-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="63bb3-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="63bb3-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="63bb3-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="63bb3-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="63bb3-115">The call timed out.</span></span>|  
|<span data-ttu-id="63bb3-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="63bb3-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="63bb3-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="63bb3-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="63bb3-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="63bb3-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="63bb3-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="63bb3-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="63bb3-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="63bb3-120">E_FAIL</span></span>|<span data-ttu-id="63bb3-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="63bb3-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="63bb3-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="63bb3-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="63bb3-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="63bb3-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63bb3-124">Note</span><span class="sxs-lookup"><span data-stu-id="63bb3-124">Remarks</span></span>  
 <span data-ttu-id="63bb3-125">Dopo che ha chiamato CLR `SetCLRIoCompletionManager`, l'host deve chiamare [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) per notificare a CLR quando è stata completata una richiesta dei / o.</span><span class="sxs-lookup"><span data-stu-id="63bb3-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63bb3-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63bb3-126">Requirements</span></span>  
 <span data-ttu-id="63bb3-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63bb3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63bb3-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63bb3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63bb3-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="63bb3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63bb3-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63bb3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63bb3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63bb3-131">See also</span></span>

- [<span data-ttu-id="63bb3-132">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="63bb3-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="63bb3-133">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="63bb3-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
