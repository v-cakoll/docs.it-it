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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cf7978af4081b84a361e0a96a6c9da7180cb217
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951723"
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="4303a-102">Metodo IHostIoCompletionManager::CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="4303a-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="4303a-103">Richieste all'host di creare una nuova porta di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="4303a-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4303a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4303a-104">Syntax</span></span>  
  
```  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4303a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4303a-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="4303a-106">[out] Un puntatore a un handle per la porta di completamento i/o appena creata, oppure 0 (zero), se non è stato possibile creare la porta.</span><span class="sxs-lookup"><span data-stu-id="4303a-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4303a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4303a-107">Return Value</span></span>  
  
|<span data-ttu-id="4303a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4303a-108">HRESULT</span></span>|<span data-ttu-id="4303a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4303a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4303a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4303a-110">S_OK</span></span>|<span data-ttu-id="4303a-111">`CreateIoCompletionPort` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="4303a-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="4303a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4303a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4303a-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4303a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4303a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4303a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4303a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4303a-115">The call timed out.</span></span>|  
|<span data-ttu-id="4303a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4303a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4303a-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="4303a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4303a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4303a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4303a-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4303a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4303a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4303a-120">E_FAIL</span></span>|<span data-ttu-id="4303a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4303a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4303a-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4303a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4303a-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4303a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4303a-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4303a-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4303a-125">Memoria insufficiente era disponibile da allocare alla risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="4303a-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4303a-126">Note</span><span class="sxs-lookup"><span data-stu-id="4303a-126">Remarks</span></span>  
 <span data-ttu-id="4303a-127">CLR chiama il `CreateIoCompletionPort` metodo per richiedere che l'host, creare una nuova porta di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="4303a-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="4303a-128">Associa a questa porta tramite una chiamata a operazioni i/o le [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="4303a-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="4303a-129">L'host segnala stato al CLR chiamando [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="4303a-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4303a-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4303a-130">Requirements</span></span>  
 <span data-ttu-id="4303a-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4303a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4303a-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4303a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4303a-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4303a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4303a-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4303a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4303a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4303a-135">See also</span></span>

- [<span data-ttu-id="4303a-136">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="4303a-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="4303a-137">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="4303a-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
