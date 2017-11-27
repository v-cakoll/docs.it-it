---
title: Metodo ICLRSyncManager::DeleteRWLockOwnerIterator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager.DeleteRWLockOwnerIterator
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3df37a9572c47ce4b4a5080f6aed3f307adba360
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="3fa90-102">Metodo ICLRSyncManager::DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="3fa90-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="3fa90-103">Richiede che common language runtime (CLR) di eliminare un iteratore che è stato creato da una chiamata a [ICLRSyncManager:: CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="3fa90-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fa90-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fa90-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fa90-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3fa90-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="3fa90-106">[in] Iteratore che è stato creato utilizzando una chiamata a `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="3fa90-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fa90-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3fa90-107">Return Value</span></span>  
  
|<span data-ttu-id="3fa90-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fa90-108">HRESULT</span></span>|<span data-ttu-id="3fa90-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3fa90-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fa90-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fa90-110">S_OK</span></span>|<span data-ttu-id="3fa90-111">`DeleteRWLockOwnerIterator`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3fa90-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="3fa90-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3fa90-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3fa90-113">CLR non è stato caricato in un processo o è in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3fa90-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="3fa90-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3fa90-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3fa90-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3fa90-115">The call timed out.</span></span>|  
|<span data-ttu-id="3fa90-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3fa90-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3fa90-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="3fa90-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3fa90-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3fa90-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3fa90-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3fa90-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3fa90-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3fa90-120">E_FAIL</span></span>|<span data-ttu-id="3fa90-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3fa90-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3fa90-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3fa90-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3fa90-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3fa90-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fa90-124">Note</span><span class="sxs-lookup"><span data-stu-id="3fa90-124">Remarks</span></span>  
 <span data-ttu-id="3fa90-125">L'host può chiamare questo metodo e `CreateRWLockOwnerIterator` per garantire che l'implementazione threading rimanga sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="3fa90-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fa90-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3fa90-126">Requirements</span></span>  
 <span data-ttu-id="3fa90-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fa90-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fa90-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="3fa90-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fa90-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3fa90-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fa90-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fa90-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa90-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fa90-131">See Also</span></span>  
 [<span data-ttu-id="3fa90-132">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3fa90-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="3fa90-133">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3fa90-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
