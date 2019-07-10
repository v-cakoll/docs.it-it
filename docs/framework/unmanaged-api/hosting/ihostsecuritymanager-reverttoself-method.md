---
title: Metodo IHostSecurityManager::RevertToSelf
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f098d8462229a405d5775203368478c7ee7e9f3c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769396"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="d23d7-102">Metodo IHostSecurityManager::RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="d23d7-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="d23d7-103">Termina la rappresentazione dell'identità dell'utente corrente e restituisce il token del thread originale.</span><span class="sxs-lookup"><span data-stu-id="d23d7-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d23d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d23d7-104">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d23d7-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d23d7-105">Return Value</span></span>  
  
|<span data-ttu-id="d23d7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d23d7-106">HRESULT</span></span>|<span data-ttu-id="d23d7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d23d7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d23d7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d23d7-108">S_OK</span></span>|<span data-ttu-id="d23d7-109">`RevertToSelf` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d23d7-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="d23d7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d23d7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d23d7-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d23d7-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d23d7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d23d7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d23d7-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d23d7-113">The call timed out.</span></span>|  
|<span data-ttu-id="d23d7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d23d7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d23d7-115">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="d23d7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d23d7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d23d7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d23d7-117">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d23d7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d23d7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d23d7-118">E_FAIL</span></span>|<span data-ttu-id="d23d7-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d23d7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d23d7-120">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d23d7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d23d7-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d23d7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d23d7-122">Note</span><span class="sxs-lookup"><span data-stu-id="d23d7-122">Remarks</span></span>  
 <span data-ttu-id="d23d7-123">`RevertToSelf` viene chiamato per restituire il token del thread originale, dopo una chiamata precedente al [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="d23d7-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d23d7-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d23d7-124">Requirements</span></span>  
 <span data-ttu-id="d23d7-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d23d7-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d23d7-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d23d7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d23d7-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d23d7-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d23d7-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d23d7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d23d7-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d23d7-129">See also</span></span>

- [<span data-ttu-id="d23d7-130">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="d23d7-130">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="d23d7-131">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="d23d7-131">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="d23d7-132">Metodo ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="d23d7-132">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)
