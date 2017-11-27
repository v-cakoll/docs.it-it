---
title: Metodo ICLRDebugManager::IsDebuggerAttached
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager.IsDebuggerAttached
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager::IsDebuggerAttached
helpviewer_keywords:
- IsDebuggerAttached method, ICLRDebugManager interface [.NET Framework hosting]
- ICLRDebugManager::IsDebuggerAttached method [.NET Framework hosting]
ms.assetid: 2f105fe0-f52d-49c5-bda5-583fb27e3aa6
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 986c9ab7853324d1a2f0fc104399141068ae9a09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugmanagerisdebuggerattached-method"></a><span data-ttu-id="01e19-102">Metodo ICLRDebugManager::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="01e19-102">ICLRDebugManager::IsDebuggerAttached Method</span></span>
<span data-ttu-id="01e19-103">Ottiene un valore che indica se un debugger è collegato al processo.</span><span class="sxs-lookup"><span data-stu-id="01e19-103">Gets a value that indicates whether a debugger is attached to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01e19-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01e19-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01e19-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01e19-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="01e19-106">[out] `true` se un debugger è collegato al processo; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="01e19-106">[out] `true` if a debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01e19-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="01e19-107">Return Value</span></span>  
  
|<span data-ttu-id="01e19-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01e19-108">HRESULT</span></span>|<span data-ttu-id="01e19-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01e19-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01e19-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="01e19-110">S_OK</span></span>|<span data-ttu-id="01e19-111">`IsDebuggerAttached`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="01e19-111">`IsDebuggerAttached` returned successfully.</span></span>|  
|<span data-ttu-id="01e19-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01e19-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01e19-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="01e19-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01e19-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01e19-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01e19-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="01e19-115">The call timed out.</span></span>|  
|<span data-ttu-id="01e19-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01e19-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01e19-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="01e19-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01e19-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01e19-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01e19-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="01e19-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01e19-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01e19-120">E_FAIL</span></span>|<span data-ttu-id="01e19-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="01e19-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01e19-122">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="01e19-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01e19-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="01e19-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01e19-124">Note</span><span class="sxs-lookup"><span data-stu-id="01e19-124">Remarks</span></span>  
 <span data-ttu-id="01e19-125">`IsDebuggerAttached`consente all'host di CLR per determinare se un debugger è collegato al processo di query.</span><span class="sxs-lookup"><span data-stu-id="01e19-125">`IsDebuggerAttached` allows the host to query the CLR to determine whether a debugger is attached to the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01e19-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01e19-126">Requirements</span></span>  
 <span data-ttu-id="01e19-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01e19-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01e19-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="01e19-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01e19-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01e19-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01e19-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01e19-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e19-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01e19-131">See Also</span></span>  
 [<span data-ttu-id="01e19-132">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="01e19-132">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="01e19-133">ICLRDebugManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="01e19-133">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="01e19-134">IHostControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="01e19-134">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
