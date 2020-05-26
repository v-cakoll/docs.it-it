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
ms.openlocfilehash: ada12a35691e0897a44f4f00e2e439fc08ef18af
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803899"
---
# <a name="ihostsecuritymanagerimpersonateloggedonuser-method"></a><span data-ttu-id="6724b-102">Metodo IHostSecurityManager::ImpersonateLoggedOnUser</span><span class="sxs-lookup"><span data-stu-id="6724b-102">IHostSecurityManager::ImpersonateLoggedOnUser Method</span></span>
<span data-ttu-id="6724b-103">Richiede che il codice venga eseguito utilizzando le credenziali dell'identità utente corrente.</span><span class="sxs-lookup"><span data-stu-id="6724b-103">Requests that code be executed using the credentials of the current user identity.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6724b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6724b-104">Syntax</span></span>  
  
```cpp  
HRESULT ImpersonateLoggedOnUser (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6724b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6724b-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="6724b-106">in Token che rappresenta le credenziali dell'utente da rappresentare.</span><span class="sxs-lookup"><span data-stu-id="6724b-106">[in] A token representing the credentials of the user to be impersonated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6724b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6724b-107">Return Value</span></span>  
  
|<span data-ttu-id="6724b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6724b-108">HRESULT</span></span>|<span data-ttu-id="6724b-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6724b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6724b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6724b-110">S_OK</span></span>|<span data-ttu-id="6724b-111">`ImpersonateLoggedOnUser`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="6724b-111">`ImpersonateLoggedOnUser` returned successfully.</span></span>|  
|<span data-ttu-id="6724b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6724b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6724b-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="6724b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6724b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6724b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6724b-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6724b-115">The call timed out.</span></span>|  
|<span data-ttu-id="6724b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6724b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6724b-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="6724b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6724b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6724b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6724b-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6724b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6724b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6724b-120">E_FAIL</span></span>|<span data-ttu-id="6724b-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6724b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6724b-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6724b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6724b-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6724b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6724b-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6724b-124">Remarks</span></span>  
 <span data-ttu-id="6724b-125">Chiamare `LogonUser` o una funzione Win32 correlata per ottenere un handle per le credenziali dell'identità dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="6724b-125">Call `LogonUser` or a related Win32 function to get a handle to the credentials of the current user identity.</span></span>  
  
 <span data-ttu-id="6724b-126">Il `HANDLE` tipo non è conforme a com, ovvero la sua dimensione è specifica di un sistema operativo e richiede il marshalling personalizzato.</span><span class="sxs-lookup"><span data-stu-id="6724b-126">The `HANDLE` type is not COM-compliant, that is, its size is specific to an operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="6724b-127">Questo token viene quindi utilizzato solo all'interno del processo, tra CLR e l'host.</span><span class="sxs-lookup"><span data-stu-id="6724b-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6724b-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6724b-128">Requirements</span></span>  
 <span data-ttu-id="6724b-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6724b-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6724b-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6724b-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6724b-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6724b-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6724b-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6724b-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6724b-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6724b-133">See also</span></span>

- [<span data-ttu-id="6724b-134">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="6724b-134">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="6724b-135">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="6724b-135">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="6724b-136">Metodo RevertToSelf</span><span class="sxs-lookup"><span data-stu-id="6724b-136">RevertToSelf Method</span></span>](ihostsecuritymanager-reverttoself-method.md)
