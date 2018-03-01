---
title: Metodo IHostSecurityManager::GetSecurityContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSecurityManager.GetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4a5fcdf0d0244694a52cf1964d0e7c4be692df2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="b3e57-102">Metodo IHostSecurityManager::GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="b3e57-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="b3e57-103">Ottiene l'oggetto richiesto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) dall'host.</span><span class="sxs-lookup"><span data-stu-id="b3e57-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3e57-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3e57-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3e57-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b3e57-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="b3e57-106">[in] Uno del [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valori, che indica il tipo di contesto di sicurezza da restituire.</span><span class="sxs-lookup"><span data-stu-id="b3e57-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="b3e57-107">[out] L'indirizzo di un puntatore a interfaccia per il `IHostSecurityContext` di `eContextType`.</span><span class="sxs-lookup"><span data-stu-id="b3e57-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3e57-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b3e57-108">Return Value</span></span>  
  
|<span data-ttu-id="b3e57-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3e57-109">HRESULT</span></span>|<span data-ttu-id="b3e57-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3e57-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3e57-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3e57-111">S_OK</span></span>|<span data-ttu-id="b3e57-112">`GetSecurityContext`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b3e57-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="b3e57-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3e57-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3e57-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b3e57-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b3e57-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b3e57-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b3e57-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b3e57-116">The call timed out.</span></span>|  
|<span data-ttu-id="b3e57-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b3e57-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b3e57-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="b3e57-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b3e57-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b3e57-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b3e57-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b3e57-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b3e57-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3e57-121">E_FAIL</span></span>|<span data-ttu-id="b3e57-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b3e57-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b3e57-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b3e57-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b3e57-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b3e57-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3e57-125">Note</span><span class="sxs-lookup"><span data-stu-id="b3e57-125">Remarks</span></span>  
 <span data-ttu-id="b3e57-126">Un host può controllare l'accesso di codice ai token di thread da codice CLR e utente.</span><span class="sxs-lookup"><span data-stu-id="b3e57-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="b3e57-127">Può inoltre garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con accesso di codice con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="b3e57-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="b3e57-128">`IHostSecurityContext`incapsula queste informazioni di contesto di sicurezza, sono opache a CLR.</span><span class="sxs-lookup"><span data-stu-id="b3e57-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="b3e57-129">CLR consente di acquisire queste informazioni e lo sposta in invio elemento di lavoro del pool di thread, esecuzione dei finalizzatori e creazione di moduli e delle classi.</span><span class="sxs-lookup"><span data-stu-id="b3e57-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3e57-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3e57-130">Requirements</span></span>  
 <span data-ttu-id="b3e57-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3e57-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3e57-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="b3e57-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3e57-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3e57-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3e57-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3e57-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3e57-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3e57-135">See Also</span></span>  
 [<span data-ttu-id="b3e57-136">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="b3e57-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="b3e57-137">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="b3e57-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="b3e57-138">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="b3e57-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
