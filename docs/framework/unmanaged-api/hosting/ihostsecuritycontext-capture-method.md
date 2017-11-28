---
title: Metodo IHostSecurityContext::Capture
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext.Capture
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 100ce151b81fb240434b1072be8fe8c354f85440
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="1d8c4-102">Metodo IHostSecurityContext::Capture</span><span class="sxs-lookup"><span data-stu-id="1d8c4-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="1d8c4-103">Ottiene un clone di [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) istanza restituita da una chiamata a [IHostSecurityManager::](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="1d8c4-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d8c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1d8c4-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d8c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1d8c4-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="1d8c4-106">[out] Un puntatore all'indirizzo di un clone di `IHostSecurityContext` oggetto devono essere acquisiti.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d8c4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1d8c4-107">Return Value</span></span>  
  
|<span data-ttu-id="1d8c4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1d8c4-108">HRESULT</span></span>|<span data-ttu-id="1d8c4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1d8c4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d8c4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d8c4-110">S_OK</span></span>|<span data-ttu-id="1d8c4-111">`Capture`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="1d8c4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1d8c4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1d8c4-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1d8c4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1d8c4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1d8c4-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-115">The call timed out.</span></span>|  
|<span data-ttu-id="1d8c4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1d8c4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1d8c4-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1d8c4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1d8c4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1d8c4-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1d8c4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1d8c4-120">E_FAIL</span></span>|<span data-ttu-id="1d8c4-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1d8c4-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1d8c4-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d8c4-124">Note</span><span class="sxs-lookup"><span data-stu-id="1d8c4-124">Remarks</span></span>  
 <span data-ttu-id="1d8c4-125">Il puntatore a interfaccia restituito da `Capture` è un clone del contesto acquisito.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="1d8c4-126">Quando queste informazioni viene spostate su un punto di codice asincrono, la relativa durata è separata da quello del puntatore rispetto al quale è stata effettuata la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="1d8c4-127">Il puntatore originale può quindi essere rilasciato.</span><span class="sxs-lookup"><span data-stu-id="1d8c4-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d8c4-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1d8c4-128">Requirements</span></span>  
 <span data-ttu-id="1d8c4-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d8c4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d8c4-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="1d8c4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d8c4-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d8c4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d8c4-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d8c4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d8c4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d8c4-133">See Also</span></span>  
 [<span data-ttu-id="1d8c4-134">IHostSecurityContext (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1d8c4-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="1d8c4-135">IHostSecurityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="1d8c4-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
