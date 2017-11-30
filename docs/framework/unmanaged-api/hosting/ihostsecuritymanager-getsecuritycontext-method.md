---
title: Metodo IHostSecurityManager::GetSecurityContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.GetSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::GetSecurityContext
helpviewer_keywords:
- GetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::GetSecurityContext method [.NET Framework hosting]
ms.assetid: 958970d6-f6a2-4b84-b32a-f555cbaf8f61
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b150700c50842791a2413688583e7e1289852d62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="77dd1-102">Metodo IHostSecurityManager::GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="77dd1-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="77dd1-103">Ottiene l'oggetto richiesto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) dall'host.</span><span class="sxs-lookup"><span data-stu-id="77dd1-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77dd1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="77dd1-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77dd1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="77dd1-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="77dd1-106">[in] Uno del [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valori, che indica il tipo di contesto di sicurezza da restituire.</span><span class="sxs-lookup"><span data-stu-id="77dd1-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="77dd1-107">[out] L'indirizzo di un puntatore a interfaccia per il `IHostSecurityContext` di `eContextType`.</span><span class="sxs-lookup"><span data-stu-id="77dd1-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77dd1-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="77dd1-108">Return Value</span></span>  
  
|<span data-ttu-id="77dd1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77dd1-109">HRESULT</span></span>|<span data-ttu-id="77dd1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="77dd1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="77dd1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="77dd1-111">S_OK</span></span>|<span data-ttu-id="77dd1-112">`GetSecurityContext`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="77dd1-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="77dd1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="77dd1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="77dd1-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="77dd1-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="77dd1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="77dd1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="77dd1-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="77dd1-116">The call timed out.</span></span>|  
|<span data-ttu-id="77dd1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="77dd1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="77dd1-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="77dd1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="77dd1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="77dd1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="77dd1-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="77dd1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="77dd1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="77dd1-121">E_FAIL</span></span>|<span data-ttu-id="77dd1-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="77dd1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="77dd1-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="77dd1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="77dd1-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="77dd1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77dd1-125">Note</span><span class="sxs-lookup"><span data-stu-id="77dd1-125">Remarks</span></span>  
 <span data-ttu-id="77dd1-126">Un host può controllare l'accesso di codice ai token di thread da codice CLR e utente.</span><span class="sxs-lookup"><span data-stu-id="77dd1-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="77dd1-127">Può inoltre garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con accesso di codice con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="77dd1-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="77dd1-128">`IHostSecurityContext`incapsula queste informazioni di contesto di sicurezza, sono opache a CLR.</span><span class="sxs-lookup"><span data-stu-id="77dd1-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="77dd1-129">CLR consente di acquisire queste informazioni e lo sposta in invio elemento di lavoro del pool di thread, esecuzione dei finalizzatori e creazione di moduli e delle classi.</span><span class="sxs-lookup"><span data-stu-id="77dd1-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77dd1-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="77dd1-130">Requirements</span></span>  
 <span data-ttu-id="77dd1-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77dd1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77dd1-132">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="77dd1-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="77dd1-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77dd1-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77dd1-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77dd1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77dd1-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77dd1-135">See Also</span></span>  
 [<span data-ttu-id="77dd1-136">EContextType (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="77dd1-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="77dd1-137">IHostSecurityContext (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="77dd1-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="77dd1-138">IHostSecurityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="77dd1-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
