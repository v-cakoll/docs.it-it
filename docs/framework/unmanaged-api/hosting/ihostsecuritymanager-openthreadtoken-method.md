---
title: Metodo IHostSecurityManager::OpenThreadToken
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 886e47028ec445b0a96af367afccd09c0759d0d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727599"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="c9e1d-102">Metodo IHostSecurityManager::OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="c9e1d-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="c9e1d-103">Apre il token di accesso discrezionale associato al thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9e1d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9e1d-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9e1d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9e1d-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="c9e1d-106">[in] Maschera di valori di accesso che specificano i tipi di richiesti di accesso ai token del thread.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="c9e1d-107">Questi valori sono definiti in Win32 `OpenThreadToken` (funzione).</span><span class="sxs-lookup"><span data-stu-id="c9e1d-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="c9e1d-108">I tipi di richiesta di accesso vengono riconciliati con elenco di controllo di accesso discrezionale (DACL) per determinare i tipi di accesso per concedere o negare del token.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="c9e1d-109">[in] `true` per specificare che il controllo di accesso deve essere effettuato utilizzando il contesto di sicurezza del processo per il thread chiamante; `false` per specificare che il controllo di accesso deve essere eseguito utilizzando il contesto di sicurezza per il thread chiamante se stesso.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="c9e1d-110">Se il thread è una rappresentazione di un client, il contesto di sicurezza può essere quello di un processo client.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="c9e1d-111">[out] Puntatore al token di accesso appena aperta.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9e1d-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c9e1d-112">Return Value</span></span>  
  
|<span data-ttu-id="c9e1d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9e1d-113">HRESULT</span></span>|<span data-ttu-id="c9e1d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c9e1d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9e1d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9e1d-115">S_OK</span></span>|<span data-ttu-id="c9e1d-116">`OpenThreadToken` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="c9e1d-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9e1d-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9e1d-118">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9e1d-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9e1d-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9e1d-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-120">The call timed out.</span></span>|  
|<span data-ttu-id="c9e1d-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9e1d-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9e1d-122">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9e1d-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9e1d-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9e1d-124">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9e1d-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9e1d-125">E_FAIL</span></span>|<span data-ttu-id="c9e1d-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9e1d-127">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9e1d-128">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9e1d-129">Note</span><span class="sxs-lookup"><span data-stu-id="c9e1d-129">Remarks</span></span>  
 <span data-ttu-id="c9e1d-130">`IHostSecurityManager::OpenThreadToken` si comporta in modo analogo alla funzione Win32 corrispondente con lo stesso nome, ad eccezione del fatto che la funzione Win32 consente al chiamante di passare un handle a un thread arbitrario, anche se `IHostSecurityManager::OpenThreadToken` apre solo il token associato al thread chiama.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="c9e1d-131">Il `HANDLE` tipo non è compatibile con COM, vale a dire, la dimensione è specifica per il sistema operativo e richiede il marshalling personalizzato.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="c9e1d-132">Di conseguenza, questo token è destinata solo all'interno del processo, tra CLR e l'host.</span><span class="sxs-lookup"><span data-stu-id="c9e1d-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9e1d-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9e1d-133">Requirements</span></span>  
 <span data-ttu-id="c9e1d-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9e1d-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9e1d-135">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c9e1d-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9e1d-136">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c9e1d-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9e1d-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9e1d-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e1d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9e1d-138">See also</span></span>
- [<span data-ttu-id="c9e1d-139">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="c9e1d-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="c9e1d-140">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="c9e1d-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
