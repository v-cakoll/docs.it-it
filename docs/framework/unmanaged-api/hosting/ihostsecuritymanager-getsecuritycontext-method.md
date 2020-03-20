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
ms.openlocfilehash: 7198698edce48546c4f9a82ace18d5a6e71891ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176253"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="c89c1-102">Metodo IHostSecurityManager::GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="c89c1-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="c89c1-103">Ottiene [l'oggetto iHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) richiesto dall'host.</span><span class="sxs-lookup"><span data-stu-id="c89c1-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c89c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c89c1-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c89c1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c89c1-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="c89c1-106">[in] Uno dei valori [di EContextType,](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) che indica il tipo di contesto di sicurezza da restituire.</span><span class="sxs-lookup"><span data-stu-id="c89c1-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="c89c1-107">[fuori] Indirizzo di un puntatore `IHostSecurityContext` `eContextType`a interfaccia all'oggetto di .</span><span class="sxs-lookup"><span data-stu-id="c89c1-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c89c1-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c89c1-108">Return Value</span></span>  
  
|<span data-ttu-id="c89c1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c89c1-109">HRESULT</span></span>|<span data-ttu-id="c89c1-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c89c1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c89c1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c89c1-111">S_OK</span></span>|<span data-ttu-id="c89c1-112">`GetSecurityContext`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="c89c1-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="c89c1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c89c1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c89c1-114">Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c89c1-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c89c1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c89c1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c89c1-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c89c1-116">The call timed out.</span></span>|  
|<span data-ttu-id="c89c1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c89c1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c89c1-118">Il chiamante non è proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c89c1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c89c1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c89c1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c89c1-120">Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c89c1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c89c1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c89c1-121">E_FAIL</span></span>|<span data-ttu-id="c89c1-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c89c1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c89c1-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c89c1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c89c1-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c89c1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c89c1-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c89c1-125">Remarks</span></span>  
 <span data-ttu-id="c89c1-126">Un host può controllare tutto l'accesso al codice ai token di thread da CLR e dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="c89c1-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="c89c1-127">Può inoltre garantire che le informazioni complete sul contesto di sicurezza vengano passate attraverso operazioni asincrone o punti di codice con accesso al codice limitato.</span><span class="sxs-lookup"><span data-stu-id="c89c1-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="c89c1-128">`IHostSecurityContext`incapsula queste informazioni sul contesto di sicurezza, che è opaco per CLR.</span><span class="sxs-lookup"><span data-stu-id="c89c1-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="c89c1-129">CLR acquisisce queste informazioni e le sposta tra l'invio di elementi di lavoro del pool di thread, l'esecuzione del finalizzatore e la costruzione di moduli e classi.</span><span class="sxs-lookup"><span data-stu-id="c89c1-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c89c1-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c89c1-130">Requirements</span></span>  
 <span data-ttu-id="c89c1-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c89c1-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c89c1-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c89c1-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c89c1-133">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c89c1-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c89c1-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c89c1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c89c1-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c89c1-135">See also</span></span>

- [<span data-ttu-id="c89c1-136">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="c89c1-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="c89c1-137">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="c89c1-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="c89c1-138">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="c89c1-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
