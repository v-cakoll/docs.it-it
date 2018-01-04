---
title: Metodo ICLRIoCompletionManager::OnComplete
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRIoCompletionManager.OnComplete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6f933172e9de5aa18d880791c439d51cce919e83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="015d7-102">Metodo ICLRIoCompletionManager::OnComplete</span><span class="sxs-lookup"><span data-stu-id="015d7-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="015d7-103">Notifica lo stato di una richiesta dei / o che è stato effettuato mediante una chiamata a common language runtime (CLR) di [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="015d7-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="015d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="015d7-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="015d7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="015d7-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="015d7-106">[in] Valore HRESULT che indica lo stato dell'operazione di associazione.</span><span class="sxs-lookup"><span data-stu-id="015d7-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
-   <span data-ttu-id="015d7-107">S_OK indica che l'operazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="015d7-107">S_OK indicates that the operation completed successfully.</span></span>  
  
-   <span data-ttu-id="015d7-108">HOST_E_INTERRUPTED indica che la chiamata è terminata prima del completamento.</span><span class="sxs-lookup"><span data-stu-id="015d7-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
-   <span data-ttu-id="015d7-109">E_FAIL indica che si è verificato un errore sconosciuto e irreversibile.</span><span class="sxs-lookup"><span data-stu-id="015d7-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="015d7-110">[in] Il numero di byte trasferiti durante l'elaborazione della richiesta dei / o.</span><span class="sxs-lookup"><span data-stu-id="015d7-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="015d7-111">[in] Un puntatore al `OVERLAPPED` struttura che è stato passato alla chiamata di `IHostIoCompletionManager::Bind` (metodo).</span><span class="sxs-lookup"><span data-stu-id="015d7-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="015d7-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="015d7-112">Return Value</span></span>  
  
|<span data-ttu-id="015d7-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="015d7-113">HRESULT</span></span>|<span data-ttu-id="015d7-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="015d7-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="015d7-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="015d7-115">S_OK</span></span>|<span data-ttu-id="015d7-116">`OnComplete`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="015d7-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="015d7-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="015d7-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="015d7-118">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="015d7-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="015d7-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="015d7-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="015d7-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="015d7-120">The call timed out.</span></span>|  
|<span data-ttu-id="015d7-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="015d7-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="015d7-122">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="015d7-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="015d7-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="015d7-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="015d7-124">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="015d7-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="015d7-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="015d7-125">E_FAIL</span></span>|<span data-ttu-id="015d7-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="015d7-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="015d7-127">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="015d7-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="015d7-128">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="015d7-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="015d7-129">Note</span><span class="sxs-lookup"><span data-stu-id="015d7-129">Remarks</span></span>  
 <span data-ttu-id="015d7-130">Se l'host implementa un'astrazione di completamento i/o, CLR effettua le richieste dei / o tramite l'host utilizzando i metodi di [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="015d7-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="015d7-131">L'host chiama quindi il `OnComplete` metodo per notificare il runtime del risultato di tali richieste.</span><span class="sxs-lookup"><span data-stu-id="015d7-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="015d7-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="015d7-132">Requirements</span></span>  
 <span data-ttu-id="015d7-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="015d7-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="015d7-134">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="015d7-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="015d7-135">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="015d7-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="015d7-136">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="015d7-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="015d7-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="015d7-137">See Also</span></span>  
 [<span data-ttu-id="015d7-138">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="015d7-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="015d7-139">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="015d7-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="015d7-140">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="015d7-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
