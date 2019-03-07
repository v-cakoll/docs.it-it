---
title: Metodo IHostSecurityManager::SetThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e06a76b4d51245388bf36b8127a470f55ca645fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494701"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="453b6-102">Metodo IHostSecurityManager::SetThreadToken</span><span class="sxs-lookup"><span data-stu-id="453b6-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="453b6-103">Imposta un handle per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="453b6-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="453b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="453b6-104">Syntax</span></span>  
  
```  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="453b6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="453b6-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="453b6-106">[in] Handle per il token da impostare per il thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="453b6-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="453b6-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="453b6-107">Return Value</span></span>  
  
|<span data-ttu-id="453b6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="453b6-108">HRESULT</span></span>|<span data-ttu-id="453b6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="453b6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="453b6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="453b6-110">S_OK</span></span>|<span data-ttu-id="453b6-111">`SetThreadToken` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="453b6-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="453b6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="453b6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="453b6-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="453b6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="453b6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="453b6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="453b6-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="453b6-115">The call timed out.</span></span>|  
|<span data-ttu-id="453b6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="453b6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="453b6-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="453b6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="453b6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="453b6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="453b6-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="453b6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="453b6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="453b6-120">E_FAIL</span></span>|<span data-ttu-id="453b6-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="453b6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="453b6-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="453b6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="453b6-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="453b6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="453b6-124">Note</span><span class="sxs-lookup"><span data-stu-id="453b6-124">Remarks</span></span>  
 <span data-ttu-id="453b6-125">`IHostSecurityManager::SetThreadToken` si comporta in modo analogo alla funzione Win32 corrispondente con lo stesso nome, ad eccezione del fatto che la funzione Win32 consente al chiamante di passare un handle a un thread arbitrario, anche se `IHostSecurityManager::SetThreadToken` può associare un token solo al thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="453b6-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="453b6-126">Il `HANDLE` tipo non è compatibile con COM; vale a dire, delle dimensioni sono specifica per un sistema operativo e richiede il marshalling personalizzato.</span><span class="sxs-lookup"><span data-stu-id="453b6-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="453b6-127">Di conseguenza, questo token è destinata solo all'interno del processo, tra CLR e l'host.</span><span class="sxs-lookup"><span data-stu-id="453b6-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="453b6-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="453b6-128">Requirements</span></span>  
 <span data-ttu-id="453b6-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="453b6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="453b6-130">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="453b6-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="453b6-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="453b6-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="453b6-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="453b6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="453b6-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="453b6-133">See also</span></span>
- [<span data-ttu-id="453b6-134">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="453b6-134">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="453b6-135">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="453b6-135">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
