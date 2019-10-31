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
ms.openlocfilehash: b84e92ca356ad83421d788a732926b614ffa4a8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133780"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="45d1d-102">Metodo IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="45d1d-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="45d1d-103">Fornisce all'host un puntatore di interfaccia all'istanza di [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) implementata dal Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="45d1d-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45d1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45d1d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45d1d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="45d1d-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="45d1d-106">in Puntatore a un'interfaccia a un'istanza di `ICLRIoCompletionManager` fornita da CLR.</span><span class="sxs-lookup"><span data-stu-id="45d1d-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45d1d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="45d1d-107">Return Value</span></span>  
  
|<span data-ttu-id="45d1d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45d1d-108">HRESULT</span></span>|<span data-ttu-id="45d1d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45d1d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45d1d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="45d1d-110">S_OK</span></span>|<span data-ttu-id="45d1d-111">`SetCLRIoCompletionManager` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="45d1d-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="45d1d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="45d1d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="45d1d-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="45d1d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="45d1d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="45d1d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="45d1d-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="45d1d-115">The call timed out.</span></span>|  
|<span data-ttu-id="45d1d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="45d1d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="45d1d-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="45d1d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="45d1d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="45d1d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="45d1d-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="45d1d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="45d1d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="45d1d-120">E_FAIL</span></span>|<span data-ttu-id="45d1d-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="45d1d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="45d1d-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="45d1d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="45d1d-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="45d1d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45d1d-124">Note</span><span class="sxs-lookup"><span data-stu-id="45d1d-124">Remarks</span></span>  
 <span data-ttu-id="45d1d-125">Dopo che CLR ha chiamato `SetCLRIoCompletionManager`, l'host deve chiamare [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) per inviare una notifica a CLR quando è stata completata una richiesta di I/O.</span><span class="sxs-lookup"><span data-stu-id="45d1d-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45d1d-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45d1d-126">Requirements</span></span>  
 <span data-ttu-id="45d1d-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45d1d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45d1d-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="45d1d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="45d1d-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="45d1d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45d1d-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45d1d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d1d-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45d1d-131">See also</span></span>

- [<span data-ttu-id="45d1d-132">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="45d1d-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="45d1d-133">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="45d1d-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
