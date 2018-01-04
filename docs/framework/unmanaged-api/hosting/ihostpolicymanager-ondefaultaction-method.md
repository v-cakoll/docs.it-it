---
title: Metodo IHostPolicyManager::OnDefaultAction
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager.OnDefaultAction
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1fded3d986e6505d0a321c47b03b5cdf9d881a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="61c86-102">Metodo IHostPolicyManager::OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="61c86-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="61c86-103">Notifica all'host che common language runtime (CLR) sta per eseguire l'azione predefinita che è stata impostata da una chiamata al [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) metodo in risposta a un'interruzione del thread o <xref:System.AppDomain> scaricare.</span><span class="sxs-lookup"><span data-stu-id="61c86-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61c86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61c86-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61c86-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="61c86-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="61c86-106">[in] Uno del [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valori, che indica il tipo di evento a cui risponde il CLR.</span><span class="sxs-lookup"><span data-stu-id="61c86-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="61c86-107">[in] Uno del [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione che Common Language Runtime in risposta all'evento.</span><span class="sxs-lookup"><span data-stu-id="61c86-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61c86-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="61c86-108">Return Value</span></span>  
  
|<span data-ttu-id="61c86-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61c86-109">HRESULT</span></span>|<span data-ttu-id="61c86-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61c86-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="61c86-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="61c86-111">S_OK</span></span>|<span data-ttu-id="61c86-112">`OnDefaultAction`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="61c86-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="61c86-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="61c86-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="61c86-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="61c86-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="61c86-115">correttamente</span><span class="sxs-lookup"><span data-stu-id="61c86-115">successfully</span></span>|  
|<span data-ttu-id="61c86-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="61c86-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="61c86-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="61c86-117">The call timed out.</span></span>|  
|<span data-ttu-id="61c86-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="61c86-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="61c86-119">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="61c86-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="61c86-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="61c86-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="61c86-121">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="61c86-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="61c86-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="61c86-122">E_FAIL</span></span>|<span data-ttu-id="61c86-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="61c86-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="61c86-124">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="61c86-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="61c86-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="61c86-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61c86-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61c86-126">Requirements</span></span>  
 <span data-ttu-id="61c86-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61c86-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61c86-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="61c86-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61c86-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61c86-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61c86-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61c86-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c86-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61c86-131">See Also</span></span>  
 [<span data-ttu-id="61c86-132">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="61c86-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="61c86-133">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="61c86-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="61c86-134">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="61c86-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="61c86-135">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="61c86-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
