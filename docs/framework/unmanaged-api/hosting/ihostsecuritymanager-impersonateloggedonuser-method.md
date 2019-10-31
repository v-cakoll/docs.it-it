---
title: Metodo IHostSecurityManager::ImpersonateLoggedOnUser
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.ImpersonateLoggedOnUser
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::ImpersonateLoggedOnUser
helpviewer_keywords:
- ImpersonateLoggedOnUser method [.NET Framework hosting]
- IHostSecurityManager::ImpersonateLoggedOnUser method [.NET Framework hosting]
ms.assetid: acc49ba0-f1d9-45ad-871f-9d053a89dcbe
topic_type:
- apiref
ms.openlocfilehash: 93051ca9a0b6f57f41d0d17335a838fe92832d8d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121491"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="6de41-102">Metodo IHostSecurityManager::ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="6de41-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="6de41-103">Richiede che il codice venga eseguito utilizzando le credenziali dell'identità utente corrente.</span><span class="sxs-lookup"><span data-stu-id="6de41-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de41-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6de41-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6de41-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6de41-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="6de41-106">in Token che rappresenta le credenziali dell'utente da rappresentare.</span><span class="sxs-lookup"><span data-stu-id="6de41-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6de41-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6de41-107">Return Value</span></span>  
  
|<span data-ttu-id="6de41-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6de41-108">HRESULT</span></span>|<span data-ttu-id="6de41-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6de41-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6de41-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6de41-110">S_OK</span></span>|<span data-ttu-id="6de41-111">`ImpersonateLoggedOnUser` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="6de41-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="6de41-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6de41-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6de41-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="6de41-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6de41-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6de41-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6de41-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6de41-115">The call timed out.</span></span>|  
|<span data-ttu-id="6de41-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6de41-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6de41-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="6de41-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6de41-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6de41-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6de41-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6de41-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6de41-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6de41-120">E_FAIL</span></span>|<span data-ttu-id="6de41-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6de41-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6de41-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6de41-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6de41-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6de41-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6de41-124">Note</span><span class="sxs-lookup"><span data-stu-id="6de41-124">Remarks</span></span>  
 <span data-ttu-id="6de41-125">Chiamare `LogonUser` o una funzione Win32 correlata per ottenere un handle per le credenziali dell'identità utente corrente.</span><span class="sxs-lookup"><span data-stu-id="6de41-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="6de41-126">Il tipo di `HANDLE` non è conforme a COM, ovvero la sua dimensione è specifica di un sistema operativo e richiede il marshalling personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6de41-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="6de41-127">Questo token viene quindi utilizzato solo all'interno del processo, tra CLR e l'host.</span><span class="sxs-lookup"><span data-stu-id="6de41-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de41-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6de41-128">Requirements</span></span>  
 <span data-ttu-id="6de41-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6de41-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de41-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6de41-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6de41-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6de41-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6de41-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de41-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de41-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6de41-133">See also</span></span>

- [<span data-ttu-id="6de41-134">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="6de41-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="6de41-135">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="6de41-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="6de41-136">Metodo RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="6de41-136">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)
