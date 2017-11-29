---
title: Metodo ICLRRuntimeHost::UnloadAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.UnloadAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ec5e32ccc9311f2f89252c0db5849304f2186de2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="d05cf-102">Metodo ICLRRuntimeHost::UnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="d05cf-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="d05cf-103">Scarica la classe gestita <xref:System.AppDomain> che corrisponde all'identificatore numerico specificato.</span><span class="sxs-lookup"><span data-stu-id="d05cf-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d05cf-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d05cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d05cf-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="d05cf-106">[in] L'identificatore numerico del dominio applicazione da scaricare.</span><span class="sxs-lookup"><span data-stu-id="d05cf-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="d05cf-107">[in] `true` per indicare che common language runtime (CLR) deve attendere finché termina l'esecuzione del thread dell'applicazione corrente prima di tentare di scaricare il dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="d05cf-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d05cf-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d05cf-108">Return Value</span></span>  
  
|<span data-ttu-id="d05cf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d05cf-109">HRESULT</span></span>|<span data-ttu-id="d05cf-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d05cf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d05cf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d05cf-111">S_OK</span></span>|<span data-ttu-id="d05cf-112">`UnloadAppDomain`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d05cf-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="d05cf-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d05cf-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d05cf-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d05cf-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d05cf-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d05cf-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d05cf-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d05cf-116">The call timed out.</span></span>|  
|<span data-ttu-id="d05cf-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d05cf-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d05cf-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="d05cf-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d05cf-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d05cf-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d05cf-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d05cf-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d05cf-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d05cf-121">E_FAIL</span></span>|<span data-ttu-id="d05cf-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d05cf-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d05cf-123">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d05cf-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d05cf-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d05cf-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d05cf-125">Note</span><span class="sxs-lookup"><span data-stu-id="d05cf-125">Remarks</span></span>  
 <span data-ttu-id="d05cf-126">È possibile ottenere l'identificatore numerico del dominio dell'applicazione in cui è in esecuzione il thread corrente chiamando [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="d05cf-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="d05cf-127">L'identificatore corrisponde al <xref:System.AppDomain.Id%2A> proprietà di gestito <xref:System.AppDomain> tipo.</span><span class="sxs-lookup"><span data-stu-id="d05cf-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d05cf-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d05cf-128">Requirements</span></span>  
 <span data-ttu-id="d05cf-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d05cf-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d05cf-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="d05cf-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d05cf-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d05cf-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d05cf-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d05cf-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d05cf-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d05cf-133">See Also</span></span>  
 [<span data-ttu-id="d05cf-134">ICLRRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d05cf-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
