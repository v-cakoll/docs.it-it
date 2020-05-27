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
ms.openlocfilehash: 0e030a33a0a3368f35c82fad33f1ea2ce32446af
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841828"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="69828-102">Metodo IHostTaskManager::SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="69828-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="69828-103">Fornisce all'host un puntatore di interfaccia a un'istanza di [ICLRTaskManager](iclrtaskmanager-interface.md) implementata dal Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="69828-103">Provides the host with an interface pointer to an [ICLRTaskManager](iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69828-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69828-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69828-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="69828-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="69828-106">in Puntatore a un' `ICLRTaskManager` istanza implementata dal Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="69828-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69828-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="69828-107">Return Value</span></span>  
  
|<span data-ttu-id="69828-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="69828-108">HRESULT</span></span>|<span data-ttu-id="69828-109">Description</span><span class="sxs-lookup"><span data-stu-id="69828-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="69828-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="69828-110">S_OK</span></span>|<span data-ttu-id="69828-111">`SetCLRTaskManager`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="69828-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="69828-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="69828-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="69828-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="69828-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="69828-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="69828-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="69828-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="69828-115">The call timed out.</span></span>|  
|<span data-ttu-id="69828-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="69828-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="69828-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="69828-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="69828-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="69828-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="69828-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="69828-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="69828-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="69828-120">E_FAIL</span></span>|<span data-ttu-id="69828-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="69828-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="69828-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="69828-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="69828-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="69828-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69828-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="69828-124">Remarks</span></span>  
 <span data-ttu-id="69828-125">Il runtime chiama `SetCLRTaskManager` per fornire all'host un puntatore di interfaccia a un' `ICLRTaskManager` istanza di.</span><span class="sxs-lookup"><span data-stu-id="69828-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69828-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="69828-126">Requirements</span></span>  
 <span data-ttu-id="69828-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69828-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69828-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="69828-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69828-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="69828-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69828-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69828-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69828-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69828-131">See also</span></span>

- [<span data-ttu-id="69828-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="69828-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="69828-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="69828-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="69828-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="69828-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="69828-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="69828-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
