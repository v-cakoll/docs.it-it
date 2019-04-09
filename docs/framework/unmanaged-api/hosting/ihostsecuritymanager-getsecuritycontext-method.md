---
title: Metodo IHostSecurityManager::GetSecurityContext
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f4f923e868b72e9de33884e4814ebfa329a16e2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105833"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="ac517-102">Metodo IHostSecurityManager::GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="ac517-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="ac517-103">Ottiene l'oggetto richiesto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) dall'host.</span><span class="sxs-lookup"><span data-stu-id="ac517-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac517-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac517-104">Syntax</span></span>  
  
```  
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac517-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac517-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="ac517-106">[in] Uno dei [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valori, che indica il tipo di contesto di sicurezza da restituire.</span><span class="sxs-lookup"><span data-stu-id="ac517-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="ac517-107">[out] L'indirizzo del puntatore a interfaccia per il `IHostSecurityContext` di `eContextType`.</span><span class="sxs-lookup"><span data-stu-id="ac517-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac517-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ac517-108">Return Value</span></span>  
  
|<span data-ttu-id="ac517-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac517-109">HRESULT</span></span>|<span data-ttu-id="ac517-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac517-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac517-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac517-111">S_OK</span></span>|`GetSecurityContext` <span data-ttu-id="ac517-112">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ac517-112">returned successfully.</span></span>|  
|<span data-ttu-id="ac517-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ac517-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ac517-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="ac517-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ac517-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ac517-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ac517-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ac517-116">The call timed out.</span></span>|  
|<span data-ttu-id="ac517-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ac517-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ac517-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="ac517-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ac517-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ac517-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ac517-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ac517-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ac517-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac517-121">E_FAIL</span></span>|<span data-ttu-id="ac517-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ac517-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac517-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ac517-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ac517-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ac517-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac517-125">Note</span><span class="sxs-lookup"><span data-stu-id="ac517-125">Remarks</span></span>  
 <span data-ttu-id="ac517-126">Un host può controllare tutti gli accessi di codice ai token di thread da codice CLR e utente.</span><span class="sxs-lookup"><span data-stu-id="ac517-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="ac517-127">Inoltre possibile garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con l'accesso al codice con restrizioni.</span><span class="sxs-lookup"><span data-stu-id="ac517-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> `IHostSecurityContext` <span data-ttu-id="ac517-128">incapsula questo informazioni sul contesto di sicurezza, è opache al CLR.</span><span class="sxs-lookup"><span data-stu-id="ac517-128">encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="ac517-129">CLR consente di acquisire queste informazioni e lo sposta in invio elemento di lavoro del pool di thread, l'esecuzione del finalizzatore e creazione di moduli e delle classi.</span><span class="sxs-lookup"><span data-stu-id="ac517-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac517-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac517-130">Requirements</span></span>  
 <span data-ttu-id="ac517-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac517-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac517-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac517-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac517-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ac517-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="ac517-134">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ac517-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ac517-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac517-135">See also</span></span>

- [<span data-ttu-id="ac517-136">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="ac517-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="ac517-137">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="ac517-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="ac517-138">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="ac517-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
