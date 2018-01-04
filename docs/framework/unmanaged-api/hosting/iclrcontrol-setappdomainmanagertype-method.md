---
title: Metodo ICLRControl::SetAppDomainManagerType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRControl.SetAppDomainManagerType
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbddefa4211d63f012bce3532d7133b59c4ee1b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="52669-102">Metodo ICLRControl::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="52669-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="52669-103">Imposta un tipo derivato da <xref:System.AppDomainManager> come tipo di gestione dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="52669-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52669-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52669-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52669-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="52669-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="52669-106">[in] Il nome dell'assembly in cui il tipo richiesto è derivato da <xref:System.AppDomainManager> viene implementato.</span><span class="sxs-lookup"><span data-stu-id="52669-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="52669-107">[in] Il nome del tipo implementato della `pwzAppDomainManagerAssembly` parametro che implementa le funzionalità di <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="52669-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52669-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="52669-108">Return Value</span></span>  
  
|<span data-ttu-id="52669-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52669-109">HRESULT</span></span>|<span data-ttu-id="52669-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52669-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52669-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="52669-111">S_OK</span></span>|<span data-ttu-id="52669-112">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="52669-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="52669-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52669-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52669-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="52669-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52669-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52669-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52669-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="52669-116">The call timed out.</span></span>|  
|<span data-ttu-id="52669-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52669-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52669-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="52669-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52669-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52669-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52669-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="52669-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52669-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52669-121">E_FAIL</span></span>|<span data-ttu-id="52669-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="52669-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52669-123">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="52669-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52669-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="52669-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52669-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52669-125">Requirements</span></span>  
 <span data-ttu-id="52669-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52669-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52669-127">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="52669-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52669-128">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="52669-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52669-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52669-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52669-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52669-130">See Also</span></span>  
 [<span data-ttu-id="52669-131">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="52669-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="52669-132">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="52669-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
