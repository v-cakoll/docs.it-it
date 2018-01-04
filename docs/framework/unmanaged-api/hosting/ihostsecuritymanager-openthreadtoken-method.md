---
title: Metodo IHostSecurityManager::OpenThreadToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.OpenThreadToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b5c39632d7628d30149a0a0278f9bf6c865bc29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="e16bc-102">Metodo IHostSecurityManager::OpenThreadToken</span><span class="sxs-lookup"><span data-stu-id="e16bc-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="e16bc-103">Apre il token di accesso discrezionale associato al thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e16bc-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e16bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e16bc-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e16bc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e16bc-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="e16bc-106">[in] Una maschera di valori di accesso che specificano i tipi di richiesti di accesso per il token del thread.</span><span class="sxs-lookup"><span data-stu-id="e16bc-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="e16bc-107">Questi valori sono definiti in Win32 `OpenThreadToken` (funzione).</span><span class="sxs-lookup"><span data-stu-id="e16bc-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="e16bc-108">Tipi di accesso richiesti vengono riconciliati con elenco di controllo del token di accesso discrezionale (DACL) per determinare quali tipi di accesso per concedere o negare.</span><span class="sxs-lookup"><span data-stu-id="e16bc-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="e16bc-109">[in] `true` per specificare che il controllo di accesso deve essere effettuato utilizzando il contesto di sicurezza del processo per il thread chiamante. `false` per specificare che il controllo di accesso deve essere eseguito utilizzando il contesto di sicurezza per il thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="e16bc-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="e16bc-110">Se il thread rappresenta un client, il contesto di sicurezza può essere di un processo client.</span><span class="sxs-lookup"><span data-stu-id="e16bc-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="e16bc-111">[out] Puntatore al token di accesso appena aperto.</span><span class="sxs-lookup"><span data-stu-id="e16bc-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e16bc-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e16bc-112">Return Value</span></span>  
  
|<span data-ttu-id="e16bc-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e16bc-113">HRESULT</span></span>|<span data-ttu-id="e16bc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e16bc-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e16bc-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e16bc-115">S_OK</span></span>|<span data-ttu-id="e16bc-116">`OpenThreadToken`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e16bc-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="e16bc-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e16bc-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e16bc-118">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e16bc-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e16bc-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e16bc-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e16bc-120">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e16bc-120">The call timed out.</span></span>|  
|<span data-ttu-id="e16bc-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e16bc-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e16bc-122">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="e16bc-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e16bc-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e16bc-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e16bc-124">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e16bc-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e16bc-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e16bc-125">E_FAIL</span></span>|<span data-ttu-id="e16bc-126">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e16bc-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e16bc-127">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e16bc-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e16bc-128">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e16bc-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e16bc-129">Note</span><span class="sxs-lookup"><span data-stu-id="e16bc-129">Remarks</span></span>  
 <span data-ttu-id="e16bc-130">`IHostSecurityManager::OpenThreadToken`si comporta in modo analogo alla funzione Win32 con lo stesso nome, con la differenza che la funzione Win32 consente al chiamante di passare un handle a un thread arbitrario, mentre `IHostSecurityManager::OpenThreadToken` apre solo il token associato al thread chiamante.</span><span class="sxs-lookup"><span data-stu-id="e16bc-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="e16bc-131">Il `HANDLE` tipo non è compatibile con COM, ovvero la dimensione è specifica per il sistema operativo e richiede marshalling personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e16bc-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="e16bc-132">Di conseguenza, questo token è utilizzato solo all'interno del processo, tra CLR e l'host.</span><span class="sxs-lookup"><span data-stu-id="e16bc-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e16bc-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e16bc-133">Requirements</span></span>  
 <span data-ttu-id="e16bc-134">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e16bc-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e16bc-135">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e16bc-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e16bc-136">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e16bc-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e16bc-137">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e16bc-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e16bc-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e16bc-138">See Also</span></span>  
 [<span data-ttu-id="e16bc-139">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="e16bc-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="e16bc-140">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="e16bc-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
