---
title: Metodo ICLRSyncManager::DeleteRWLockOwnerIterator
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.DeleteRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5ee4a09902be093bdbfe0b367f4add35bdda571c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434067"
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="5a93b-102">Metodo ICLRSyncManager::DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="5a93b-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="5a93b-103">Richiede che common language runtime (CLR) di eliminare un iteratore che è stato creato da una chiamata a [ICLRSyncManager:: CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="5a93b-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a93b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a93b-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a93b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a93b-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="5a93b-106">[in] Iteratore che è stato creato utilizzando una chiamata a `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="5a93b-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a93b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5a93b-107">Return Value</span></span>  
  
|<span data-ttu-id="5a93b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a93b-108">HRESULT</span></span>|<span data-ttu-id="5a93b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a93b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a93b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a93b-110">S_OK</span></span>|<span data-ttu-id="5a93b-111">`DeleteRWLockOwnerIterator` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5a93b-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="5a93b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a93b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a93b-113">CLR non è stato caricato in un processo o è in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5a93b-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="5a93b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a93b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a93b-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5a93b-115">The call timed out.</span></span>|  
|<span data-ttu-id="5a93b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a93b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a93b-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="5a93b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a93b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a93b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a93b-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5a93b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a93b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a93b-120">E_FAIL</span></span>|<span data-ttu-id="5a93b-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5a93b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a93b-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5a93b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a93b-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5a93b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a93b-124">Note</span><span class="sxs-lookup"><span data-stu-id="5a93b-124">Remarks</span></span>  
 <span data-ttu-id="5a93b-125">L'host può chiamare questo metodo e `CreateRWLockOwnerIterator` per garantire che l'implementazione threading rimanga sincronizzata.</span><span class="sxs-lookup"><span data-stu-id="5a93b-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a93b-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a93b-126">Requirements</span></span>  
 <span data-ttu-id="5a93b-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a93b-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a93b-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="5a93b-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a93b-129">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5a93b-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a93b-130">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a93b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a93b-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a93b-131">See Also</span></span>  
 [<span data-ttu-id="5a93b-132">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="5a93b-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="5a93b-133">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="5a93b-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
