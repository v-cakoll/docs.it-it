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
ms.openlocfilehash: b379bb2a9512cd1bd3344ed7f5130f96c0ccfa87
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855574"
---
# <a name="ihostsecuritymanagergetsecuritycontext-method"></a><span data-ttu-id="64587-102">Metodo IHostSecurityManager::GetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="64587-102">IHostSecurityManager::GetSecurityContext Method</span></span>
<span data-ttu-id="64587-103">Ottiene l'oggetto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) richiesto dall'host.</span><span class="sxs-lookup"><span data-stu-id="64587-103">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64587-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64587-104">Syntax</span></span>  
  
```cpp
HRESULT GetSecurityContext (  
    [in]  EContextType eContextType,   
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64587-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="64587-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="64587-106">in Uno dei valori di [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) , che indica il tipo di contesto di sicurezza da restituire.</span><span class="sxs-lookup"><span data-stu-id="64587-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of security context to return.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="64587-107">out Indirizzo di un puntatore a `IHostSecurityContext` `eContextType`interfaccia di.</span><span class="sxs-lookup"><span data-stu-id="64587-107">[out] The address of an interface pointer to the `IHostSecurityContext` of `eContextType`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64587-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="64587-108">Return Value</span></span>  
  
|<span data-ttu-id="64587-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64587-109">HRESULT</span></span>|<span data-ttu-id="64587-110">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="64587-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64587-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="64587-111">S_OK</span></span>|<span data-ttu-id="64587-112">`GetSecurityContext`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="64587-112">`GetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="64587-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="64587-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="64587-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="64587-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="64587-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="64587-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="64587-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="64587-116">The call timed out.</span></span>|  
|<span data-ttu-id="64587-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="64587-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="64587-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="64587-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="64587-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="64587-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="64587-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="64587-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="64587-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64587-121">E_FAIL</span></span>|<span data-ttu-id="64587-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="64587-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64587-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="64587-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="64587-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="64587-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64587-125">Note</span><span class="sxs-lookup"><span data-stu-id="64587-125">Remarks</span></span>  
 <span data-ttu-id="64587-126">Un host può controllare l'accesso al codice a token di thread sia dal codice CLR che dal codice utente.</span><span class="sxs-lookup"><span data-stu-id="64587-126">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="64587-127">Può inoltre garantire che le informazioni complete sul contesto di sicurezza vengano passate tra le operazioni asincrone o i punti di codice con accesso limitato al codice.</span><span class="sxs-lookup"><span data-stu-id="64587-127">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="64587-128">`IHostSecurityContext`incapsula queste informazioni sul contesto di sicurezza, che è opaco per CLR.</span><span class="sxs-lookup"><span data-stu-id="64587-128">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span> <span data-ttu-id="64587-129">CLR acquisisce queste informazioni e le sposta attraverso la distribuzione degli elementi di lavoro del pool di thread, l'esecuzione del finalizzatore e la costruzione del modulo e della classe.</span><span class="sxs-lookup"><span data-stu-id="64587-129">The CLR captures this information and moves it across thread pool worker item dispatch, finalizer execution, and module and class construction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64587-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64587-130">Requirements</span></span>  
 <span data-ttu-id="64587-131">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64587-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64587-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="64587-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64587-133">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="64587-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64587-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64587-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64587-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64587-135">See also</span></span>

- [<span data-ttu-id="64587-136">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="64587-136">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="64587-137">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="64587-137">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="64587-138">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="64587-138">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
