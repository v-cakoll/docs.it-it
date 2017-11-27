---
title: Metodo IHostIoCompletionManager::CreateIoCompletionPort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.CreateIoCompletionPort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::CreateIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CreateIoCompletionPort method [.NET Framework hosting]
- CreateIoCompletionPort method [.NET Framework hosting]
ms.assetid: 907a2b43-68db-44a7-acac-89e792e7bb3c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1942c34b0807b76bbe25aedc60b7b1c6fecc87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagercreateiocompletionport-method"></a><span data-ttu-id="c8c1b-102">Metodo IHostIoCompletionManager::CreateIoCompletionPort</span><span class="sxs-lookup"><span data-stu-id="c8c1b-102">IHostIoCompletionManager::CreateIoCompletionPort Method</span></span>
<span data-ttu-id="c8c1b-103">Richieste all'host di creare una nuova porta di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-103">Requests that the host create a new I/O completion port.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8c1b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8c1b-104">Syntax</span></span>  
  
```  
HRESULT CreateIoCompletionPort (  
    [out] HANDLE *phPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8c1b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8c1b-105">Parameters</span></span>  
 `phPort`  
 <span data-ttu-id="c8c1b-106">[out] Puntatore a un handle per la porta di completamento i/o appena creata, oppure 0 (zero), se non è stato possibile creare la porta.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-106">[out] A pointer to a handle to the newly created I/O completion port, or 0 (zero), if the port could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8c1b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c8c1b-107">Return Value</span></span>  
  
|<span data-ttu-id="c8c1b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c8c1b-108">HRESULT</span></span>|<span data-ttu-id="c8c1b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8c1b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c8c1b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c8c1b-110">S_OK</span></span>|<span data-ttu-id="c8c1b-111">`CreateIoCompletionPort`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-111">`CreateIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="c8c1b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c8c1b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c8c1b-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c8c1b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c8c1b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c8c1b-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-115">The call timed out.</span></span>|  
|<span data-ttu-id="c8c1b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c8c1b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c8c1b-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c8c1b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c8c1b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c8c1b-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c8c1b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c8c1b-120">E_FAIL</span></span>|<span data-ttu-id="c8c1b-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c8c1b-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c8c1b-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c8c1b-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c8c1b-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c8c1b-125">Memoria insufficiente è disponibile per la risorsa richiesta.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-125">Not enough memory was available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8c1b-126">Note</span><span class="sxs-lookup"><span data-stu-id="c8c1b-126">Remarks</span></span>  
 <span data-ttu-id="c8c1b-127">CLR chiama il `CreateIoCompletionPort` metodo per richiedere che l'host crea una nuova porta di completamento i/o.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-127">The CLR calls the `CreateIoCompletionPort` method to request that the host create a new I/O completion port.</span></span> <span data-ttu-id="c8c1b-128">Associa a questa porta mediante una chiamata a operazioni dei / o il [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="c8c1b-128">It binds I/O operations to this port through a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span> <span data-ttu-id="c8c1b-129">L'host segnala lo stato nuovo a CLR chiamando [ICLRIoCompletionManager::](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="c8c1b-129">The host reports status back to the CLR by calling [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8c1b-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8c1b-130">Requirements</span></span>  
 <span data-ttu-id="c8c1b-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8c1b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8c1b-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="c8c1b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8c1b-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8c1b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8c1b-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8c1b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8c1b-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8c1b-135">See Also</span></span>  
 [<span data-ttu-id="c8c1b-136">ICLRIoCompletionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c8c1b-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="c8c1b-137">IHostIoCompletionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="c8c1b-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
