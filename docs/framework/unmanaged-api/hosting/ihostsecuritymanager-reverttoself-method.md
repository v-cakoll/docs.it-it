---
title: Metodo IHostSecurityManager::RevertToSelf
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.RevertToSelf
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0fad325bc3df54f412a797e9944f5b1f38615786
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="1bcbf-102">Metodo IHostSecurityManager::RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="1bcbf-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="1bcbf-103">Termina la rappresentazione dell'identità dell'utente corrente e restituisce il token thread originale.</span><span class="sxs-lookup"><span data-stu-id="1bcbf-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bcbf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1bcbf-104">Syntax</span></span>  
  
```  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="1bcbf-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1bcbf-105">Return Value</span></span>  
  
|<span data-ttu-id="1bcbf-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1bcbf-106">HRESULT</span></span>|<span data-ttu-id="1bcbf-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1bcbf-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1bcbf-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1bcbf-108">S_OK</span></span>|<span data-ttu-id="1bcbf-109">`RevertToSelf`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1bcbf-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="1bcbf-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1bcbf-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1bcbf-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1bcbf-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1bcbf-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1bcbf-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1bcbf-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1bcbf-113">The call timed out.</span></span>|  
|<span data-ttu-id="1bcbf-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1bcbf-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1bcbf-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="1bcbf-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1bcbf-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1bcbf-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1bcbf-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="1bcbf-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1bcbf-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1bcbf-118">E_FAIL</span></span>|<span data-ttu-id="1bcbf-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1bcbf-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1bcbf-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="1bcbf-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1bcbf-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1bcbf-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bcbf-122">Note</span><span class="sxs-lookup"><span data-stu-id="1bcbf-122">Remarks</span></span>  
 <span data-ttu-id="1bcbf-123">`RevertToSelf`viene chiamato per restituire il token thread originale, dopo una chiamata precedente al [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="1bcbf-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bcbf-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1bcbf-124">Requirements</span></span>  
 <span data-ttu-id="1bcbf-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bcbf-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bcbf-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="1bcbf-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1bcbf-127">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1bcbf-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1bcbf-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bcbf-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bcbf-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bcbf-129">See Also</span></span>  
 [<span data-ttu-id="1bcbf-130">IHostSecurityContext (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1bcbf-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="1bcbf-131">IHostSecurityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1bcbf-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="1bcbf-132">ImpersonateLoggedOnUser (metodo)</span><span class="sxs-lookup"><span data-stu-id="1bcbf-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
