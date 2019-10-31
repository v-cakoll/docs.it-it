---
title: Metodo IHostIoCompletionManager::CreateIoCompletionPort
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.CreateIoCompletionPort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type:
- apiref
ms.openlocfilehash: c3fa8aeebe529564c0ecc4a970f586fffc97ee05
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133872"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="87d2e-102">Metodo IHostIoCompletionManager::CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="87d2e-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="87d2e-103">Richiede che l'host crei una nuova porta di completamento di I/O.</span><span class="sxs-lookup"><span data-stu-id="87d2e-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87d2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="87d2e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87d2e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="87d2e-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="87d2e-106">out Puntatore a un handle per la porta di completamento I/O appena creato oppure 0 (zero) se non è stato possibile creare la porta.</span><span class="sxs-lookup"><span data-stu-id="87d2e-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87d2e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="87d2e-107">Return Value</span></span>  
  
|<span data-ttu-id="87d2e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="87d2e-108">HRESULT</span></span>|<span data-ttu-id="87d2e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="87d2e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="87d2e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="87d2e-110">S_OK</span></span>|<span data-ttu-id="87d2e-111">`CreateIoCompletionPort` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="87d2e-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="87d2e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="87d2e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="87d2e-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="87d2e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="87d2e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="87d2e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="87d2e-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="87d2e-115">The call timed out.</span></span>|  
|<span data-ttu-id="87d2e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="87d2e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="87d2e-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="87d2e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="87d2e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="87d2e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="87d2e-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="87d2e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="87d2e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="87d2e-120">E_FAIL</span></span>|<span data-ttu-id="87d2e-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="87d2e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="87d2e-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="87d2e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="87d2e-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="87d2e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="87d2e-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="87d2e-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="87d2e-125">Memoria insufficiente per l'allocazione della risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="87d2e-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87d2e-126">Note</span><span class="sxs-lookup"><span data-stu-id="87d2e-126">Remarks</span></span>  
 <span data-ttu-id="87d2e-127">CLR chiama il metodo `CreateIoCompletionPort` per richiedere che l'host crei una nuova porta di completamento I/O.</span><span class="sxs-lookup"><span data-stu-id="87d2e-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="87d2e-128">Associa le operazioni di I/O a questa porta tramite una chiamata al metodo [IHostIoCompletionManager:: bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="87d2e-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="87d2e-129">L'host riporta lo stato a CLR chiamando [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="87d2e-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87d2e-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="87d2e-130">Requirements</span></span>  
 <span data-ttu-id="87d2e-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87d2e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87d2e-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="87d2e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="87d2e-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="87d2e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87d2e-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87d2e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d2e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87d2e-135">See also</span></span>

- [<span data-ttu-id="87d2e-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="87d2e-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="87d2e-137">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="87d2e-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
