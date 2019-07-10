---
title: Metodo ICLRPolicyManager::SetTimeout
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9c2ebb2bc9c1137a4e3716d98387278959f77d2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757326"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="b3f26-102">Metodo ICLRPolicyManager::SetTimeout</span><span class="sxs-lookup"><span data-stu-id="b3f26-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="b3f26-103">Imposta un valore di timeout per l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="b3f26-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3f26-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3f26-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b3f26-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="b3f26-106">[in] Uno dei [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valori, che indica l'operazione di common language runtime (CLR) per cui impostare un timeout.</span><span class="sxs-lookup"><span data-stu-id="b3f26-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="b3f26-107">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="b3f26-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="b3f26-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="b3f26-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="b3f26-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="b3f26-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="b3f26-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b3f26-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="b3f26-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b3f26-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="b3f26-112">[in] Il nuovo valore di timeout, espresso in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="b3f26-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="b3f26-113">Un valore infinito fa in modo che l'operazione non scada mai.</span><span class="sxs-lookup"><span data-stu-id="b3f26-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3f26-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b3f26-114">Return Value</span></span>  
  
|<span data-ttu-id="b3f26-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3f26-115">HRESULT</span></span>|<span data-ttu-id="b3f26-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b3f26-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3f26-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3f26-117">S_OK</span></span>|<span data-ttu-id="b3f26-118">`SetTimeout` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b3f26-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="b3f26-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3f26-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3f26-120">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b3f26-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b3f26-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b3f26-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b3f26-122">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b3f26-122">The call timed out.</span></span>|  
|<span data-ttu-id="b3f26-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b3f26-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b3f26-124">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b3f26-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b3f26-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b3f26-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b3f26-126">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b3f26-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b3f26-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3f26-127">E_FAIL</span></span>|<span data-ttu-id="b3f26-128">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b3f26-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b3f26-129">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b3f26-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b3f26-130">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b3f26-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b3f26-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b3f26-131">E_INVALIDARG</span></span>|<span data-ttu-id="b3f26-132">Non è possibile impostare un timeout per l'oggetto specificato `operation`, o è stato specificato un valore non valido per `operation`.</span><span class="sxs-lookup"><span data-stu-id="b3f26-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b3f26-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b3f26-133">Requirements</span></span>  
 <span data-ttu-id="b3f26-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3f26-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f26-135">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b3f26-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3f26-136">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b3f26-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3f26-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f26-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f26-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3f26-138">See also</span></span>

- [<span data-ttu-id="b3f26-139">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="b3f26-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="b3f26-140">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="b3f26-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="b3f26-141">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="b3f26-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
