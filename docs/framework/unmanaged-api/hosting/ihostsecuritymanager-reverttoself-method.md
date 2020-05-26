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
ms.openlocfilehash: 456553e4cb5a6c6a557b5c3ac677fad12a5798bf
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803823"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a><span data-ttu-id="bb11b-102">Metodo IHostSecurityManager::RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="bb11b-102">IHostSecurityManager::RevertToSelf Method</span></span>
<span data-ttu-id="bb11b-103">Termina la rappresentazione dell'identità dell'utente corrente e restituisce il token del thread originale.</span><span class="sxs-lookup"><span data-stu-id="bb11b-103">Terminates impersonation of the current user identity and returns the original thread token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb11b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb11b-104">Syntax</span></span>  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bb11b-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bb11b-105">Return Value</span></span>  
  
|<span data-ttu-id="bb11b-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bb11b-106">HRESULT</span></span>|<span data-ttu-id="bb11b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb11b-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bb11b-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="bb11b-108">S_OK</span></span>|<span data-ttu-id="bb11b-109">`RevertToSelf`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="bb11b-109">`RevertToSelf` returned successfully.</span></span>|  
|<span data-ttu-id="bb11b-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bb11b-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bb11b-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="bb11b-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bb11b-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bb11b-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bb11b-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bb11b-113">The call timed out.</span></span>|  
|<span data-ttu-id="bb11b-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bb11b-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bb11b-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="bb11b-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bb11b-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bb11b-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bb11b-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="bb11b-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bb11b-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bb11b-118">E_FAIL</span></span>|<span data-ttu-id="bb11b-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="bb11b-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bb11b-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="bb11b-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bb11b-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bb11b-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb11b-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bb11b-122">Remarks</span></span>  
 <span data-ttu-id="bb11b-123">`RevertToSelf`viene chiamato per tornare al token del thread originale, dopo una chiamata precedente al metodo [ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bb11b-123">`RevertToSelf` is called to return to the original thread token, after an earlier call to the [ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb11b-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb11b-124">Requirements</span></span>  
 <span data-ttu-id="bb11b-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb11b-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb11b-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bb11b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bb11b-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bb11b-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bb11b-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb11b-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb11b-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb11b-129">See also</span></span>

- [<span data-ttu-id="bb11b-130">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="bb11b-130">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="bb11b-131">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="bb11b-131">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="bb11b-132">Metodo ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="bb11b-132">ImpersonateLoggedOnUser Method</span></span>](ihostsecuritymanager-impersonateloggedonuser-method.md)
