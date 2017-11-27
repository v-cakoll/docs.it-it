---
title: Metodo IHostSecurityManager::ImpersonateLoggedOnUser
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.ImpersonateLoggedOnUser
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8c5956dcad6908f0117de7f5ff0c6632ad3bb925
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="95c61-102">Metodo IHostSecurityManager::ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="95c61-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="95c61-103">Le richieste di codice da eseguire utilizzando le credenziali dell'identità dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="95c61-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95c61-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95c61-104">Syntax</span></span>  
  
```  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95c61-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95c61-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="95c61-106">[in] Un token che rappresenta le credenziali dell'utente da rappresentare.</span><span class="sxs-lookup"><span data-stu-id="95c61-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95c61-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="95c61-107">Return Value</span></span>  
  
|<span data-ttu-id="95c61-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="95c61-108">HRESULT</span></span>|<span data-ttu-id="95c61-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="95c61-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="95c61-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="95c61-110">S_OK</span></span>|<span data-ttu-id="95c61-111">`ImpersonateLoggedOnUser`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="95c61-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="95c61-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="95c61-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="95c61-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="95c61-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="95c61-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="95c61-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="95c61-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="95c61-115">The call timed out.</span></span>|  
|<span data-ttu-id="95c61-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="95c61-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="95c61-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="95c61-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="95c61-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="95c61-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="95c61-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="95c61-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="95c61-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="95c61-120">E_FAIL</span></span>|<span data-ttu-id="95c61-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="95c61-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="95c61-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="95c61-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="95c61-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="95c61-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95c61-124">Note</span><span class="sxs-lookup"><span data-stu-id="95c61-124">Remarks</span></span>  
 <span data-ttu-id="95c61-125">Chiamare `LogonUser` o una funzione Win32 correlata per ottenere un handle per le credenziali dell'identità dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="95c61-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="95c61-126">Il `HANDLE` tipo non è compatibile con COM, ovvero la dimensione è specifica per un sistema operativo e richiede marshalling personalizzato.</span><span class="sxs-lookup"><span data-stu-id="95c61-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="95c61-127">Di conseguenza, questo token è utilizzato solo all'interno del processo, tra CLR e l'host.</span><span class="sxs-lookup"><span data-stu-id="95c61-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c61-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95c61-128">Requirements</span></span>  
 <span data-ttu-id="95c61-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95c61-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95c61-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="95c61-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95c61-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95c61-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95c61-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95c61-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c61-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95c61-133">See Also</span></span>  
 [<span data-ttu-id="95c61-134">IHostSecurityContext (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="95c61-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="95c61-135">IHostSecurityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="95c61-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="95c61-136">RevertToSelf (metodo)</span><span class="sxs-lookup"><span data-stu-id="95c61-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
