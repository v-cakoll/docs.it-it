---
title: Metodo ICLRPolicyManager::SetUnhandledExceptionPolicy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59ff5cfd93d8077388694ee2e155133a88319c47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="411af-102">Metodo ICLRPolicyManager::SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="411af-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="411af-103">Specifica il comportamento di common language runtime (CLR) quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="411af-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="411af-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="411af-104">Syntax</span></span>  
  
```  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="411af-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="411af-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="411af-106">[in] Uno del [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) valori, che indica se il comportamento viene impostato da CLR o dall'host.</span><span class="sxs-lookup"><span data-stu-id="411af-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="411af-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="411af-107">Return Value</span></span>  
  
|<span data-ttu-id="411af-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="411af-108">HRESULT</span></span>|<span data-ttu-id="411af-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="411af-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="411af-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="411af-110">S_OK</span></span>|<span data-ttu-id="411af-111">`SetUnhandledExceptionPolicy`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="411af-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="411af-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="411af-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="411af-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="411af-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="411af-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="411af-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="411af-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="411af-115">The call timed out.</span></span>|  
|<span data-ttu-id="411af-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="411af-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="411af-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="411af-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="411af-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="411af-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="411af-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="411af-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="411af-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="411af-120">E_FAIL</span></span>|<span data-ttu-id="411af-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="411af-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="411af-122">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="411af-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="411af-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="411af-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="411af-124">Note</span><span class="sxs-lookup"><span data-stu-id="411af-124">Remarks</span></span>  
 <span data-ttu-id="411af-125">Per impostazione predefinita, CLR è il gestore finale per tutte le eccezioni non gestite e il comportamento predefinito consiste nell'eliminare il processo.</span><span class="sxs-lookup"><span data-stu-id="411af-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="411af-126">L'host può modificare questo comportamento impostando la `policy` valore eHostDeterminedPolicy.</span><span class="sxs-lookup"><span data-stu-id="411af-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="411af-127">Questo valore consente all'host di implementare il proprio comportamento predefinito, come nelle precedenti versioni di CLR.</span><span class="sxs-lookup"><span data-stu-id="411af-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="411af-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="411af-128">Requirements</span></span>  
 <span data-ttu-id="411af-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="411af-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="411af-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="411af-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="411af-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="411af-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="411af-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="411af-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411af-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="411af-133">See Also</span></span>  
 [<span data-ttu-id="411af-134">EClrUnhandledException (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="411af-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)  
 [<span data-ttu-id="411af-135">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="411af-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="411af-136">ICLRPolicyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="411af-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="411af-137">IHostPolicyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="411af-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
