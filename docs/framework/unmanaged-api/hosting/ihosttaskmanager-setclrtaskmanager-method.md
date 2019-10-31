---
title: Metodo IHostTaskManager::SetCLRTaskManager
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
ms.openlocfilehash: c674cc43065bf8ea102bec1c5134757380454913
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141235"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="c56ad-102">Metodo IHostTaskManager::SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c56ad-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="c56ad-103">Fornisce all'host un puntatore di interfaccia a un'istanza di [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) implementata dal Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c56ad-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c56ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c56ad-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c56ad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c56ad-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="c56ad-106">in Puntatore a un'istanza di `ICLRTaskManager` implementata dall'Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="c56ad-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c56ad-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c56ad-107">Return Value</span></span>  
  
|<span data-ttu-id="c56ad-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c56ad-108">HRESULT</span></span>|<span data-ttu-id="c56ad-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c56ad-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c56ad-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c56ad-110">S_OK</span></span>|<span data-ttu-id="c56ad-111">`SetCLRTaskManager` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c56ad-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="c56ad-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c56ad-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c56ad-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c56ad-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c56ad-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c56ad-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c56ad-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c56ad-115">The call timed out.</span></span>|  
|<span data-ttu-id="c56ad-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c56ad-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c56ad-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c56ad-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c56ad-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c56ad-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c56ad-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c56ad-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c56ad-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c56ad-120">E_FAIL</span></span>|<span data-ttu-id="c56ad-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c56ad-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c56ad-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c56ad-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c56ad-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c56ad-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c56ad-124">Note</span><span class="sxs-lookup"><span data-stu-id="c56ad-124">Remarks</span></span>  
 <span data-ttu-id="c56ad-125">Il runtime chiama `SetCLRTaskManager` per fornire all'host un puntatore di interfaccia a un'istanza di `ICLRTaskManager`.</span><span class="sxs-lookup"><span data-stu-id="c56ad-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c56ad-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c56ad-126">Requirements</span></span>  
 <span data-ttu-id="c56ad-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c56ad-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c56ad-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c56ad-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c56ad-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c56ad-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c56ad-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c56ad-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c56ad-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c56ad-131">See also</span></span>

- [<span data-ttu-id="c56ad-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c56ad-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="c56ad-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c56ad-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="c56ad-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="c56ad-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="c56ad-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c56ad-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
