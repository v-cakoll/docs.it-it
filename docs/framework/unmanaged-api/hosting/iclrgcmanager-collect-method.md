---
title: Metodo ICLRGCManager::Collect
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.Collect
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96f99855654a3a86873ca4623d8617f74030938b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="48a5a-102">Metodo ICLRGCManager::Collect</span><span class="sxs-lookup"><span data-stu-id="48a5a-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="48a5a-103">Forza un'operazione di garbage collection per la generazione specificata.</span><span class="sxs-lookup"><span data-stu-id="48a5a-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48a5a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48a5a-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48a5a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="48a5a-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="48a5a-106">[in] La generazione di raccogliere.</span><span class="sxs-lookup"><span data-stu-id="48a5a-106">[in] The generation to collect.</span></span> <span data-ttu-id="48a5a-107">Il valore-1 forza una raccolta di tutte le generazioni.</span><span class="sxs-lookup"><span data-stu-id="48a5a-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48a5a-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="48a5a-108">Return Value</span></span>  
  
|<span data-ttu-id="48a5a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48a5a-109">HRESULT</span></span>|<span data-ttu-id="48a5a-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48a5a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48a5a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="48a5a-111">S_OK</span></span>|<span data-ttu-id="48a5a-112">`Collect`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="48a5a-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="48a5a-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48a5a-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48a5a-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="48a5a-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48a5a-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48a5a-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48a5a-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="48a5a-116">The call timed out.</span></span>|  
|<span data-ttu-id="48a5a-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48a5a-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48a5a-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="48a5a-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48a5a-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48a5a-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48a5a-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="48a5a-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48a5a-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48a5a-121">E_FAIL</span></span>|<span data-ttu-id="48a5a-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="48a5a-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48a5a-123">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="48a5a-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48a5a-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="48a5a-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48a5a-125">Note</span><span class="sxs-lookup"><span data-stu-id="48a5a-125">Remarks</span></span>  
 <span data-ttu-id="48a5a-126">Il `Collect` metodo forza il garbage collector di CLR per eseguire una raccolta indipendentemente dallo stato corrente.</span><span class="sxs-lookup"><span data-stu-id="48a5a-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48a5a-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48a5a-127">Requirements</span></span>  
 <span data-ttu-id="48a5a-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48a5a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48a5a-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="48a5a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48a5a-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48a5a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48a5a-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48a5a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48a5a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48a5a-132">See Also</span></span>  
 [<span data-ttu-id="48a5a-133">Gestione automatica della memoria</span><span class="sxs-lookup"><span data-stu-id="48a5a-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="48a5a-134">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="48a5a-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="48a5a-135">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="48a5a-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="48a5a-136">ICLRGCManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="48a5a-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="48a5a-137">Interfacce di Hosting CLR</span><span class="sxs-lookup"><span data-stu-id="48a5a-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="48a5a-138">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="48a5a-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="48a5a-139">Hosting</span><span class="sxs-lookup"><span data-stu-id="48a5a-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
