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
ms.openlocfilehash: a76e807e6b316fc4b904e3f085a17b00d6a11c73
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804702"
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="271dc-102">Metodo IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="271dc-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="271dc-103">Fornisce all'host un puntatore di interfaccia all'istanza di [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) implementata dal Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="271dc-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="271dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="271dc-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="271dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="271dc-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="271dc-106">in Puntatore di interfaccia a un' `ICLRIoCompletionManager` istanza fornita da CLR.</span><span class="sxs-lookup"><span data-stu-id="271dc-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="271dc-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="271dc-107">Return Value</span></span>  
  
|<span data-ttu-id="271dc-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="271dc-108">HRESULT</span></span>|<span data-ttu-id="271dc-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="271dc-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="271dc-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="271dc-110">S_OK</span></span>|<span data-ttu-id="271dc-111">`SetCLRIoCompletionManager`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="271dc-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="271dc-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="271dc-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="271dc-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="271dc-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="271dc-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="271dc-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="271dc-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="271dc-115">The call timed out.</span></span>|  
|<span data-ttu-id="271dc-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="271dc-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="271dc-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="271dc-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="271dc-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="271dc-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="271dc-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="271dc-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="271dc-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="271dc-120">E_FAIL</span></span>|<span data-ttu-id="271dc-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="271dc-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="271dc-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="271dc-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="271dc-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="271dc-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="271dc-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="271dc-124">Remarks</span></span>  
 <span data-ttu-id="271dc-125">Dopo che CLR ha chiamato `SetCLRIoCompletionManager` , l'host deve chiamare [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md) per inviare una notifica a CLR quando è stata completata una richiesta di I/O.</span><span class="sxs-lookup"><span data-stu-id="271dc-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="271dc-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="271dc-126">Requirements</span></span>  
 <span data-ttu-id="271dc-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="271dc-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="271dc-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="271dc-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="271dc-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="271dc-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="271dc-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="271dc-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="271dc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="271dc-131">See also</span></span>

- [<span data-ttu-id="271dc-132">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="271dc-132">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="271dc-133">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="271dc-133">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
