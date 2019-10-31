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
ms.openlocfilehash: 516ba1325404e757af8e38de239864b21b1640f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140752"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="05631-102">Metodo ICLRPolicyManager::SetTimeout</span><span class="sxs-lookup"><span data-stu-id="05631-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="05631-103">Imposta un valore di timeout per l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="05631-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05631-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05631-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05631-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="05631-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="05631-106">in Uno dei valori di [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , che indica l'operazione di Common Language Runtime (CLR) per la quale impostare un timeout.</span><span class="sxs-lookup"><span data-stu-id="05631-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="05631-107">Sono supportati i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="05631-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="05631-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="05631-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="05631-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="05631-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="05631-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="05631-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="05631-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="05631-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="05631-112">in Nuovo valore di timeout, in millisecondi.</span><span class="sxs-lookup"><span data-stu-id="05631-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="05631-113">Il valore infinito causa il timeout dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="05631-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05631-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="05631-114">Return Value</span></span>  
  
|<span data-ttu-id="05631-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05631-115">HRESULT</span></span>|<span data-ttu-id="05631-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="05631-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05631-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="05631-117">S_OK</span></span>|<span data-ttu-id="05631-118">`SetTimeout` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="05631-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="05631-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="05631-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="05631-120">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="05631-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="05631-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="05631-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="05631-122">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="05631-122">The call timed out.</span></span>|  
|<span data-ttu-id="05631-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="05631-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="05631-124">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="05631-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="05631-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="05631-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="05631-126">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="05631-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="05631-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="05631-127">E_FAIL</span></span>|<span data-ttu-id="05631-128">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="05631-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="05631-129">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="05631-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="05631-130">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="05631-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="05631-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="05631-131">E_INVALIDARG</span></span>|<span data-ttu-id="05631-132">Impossibile impostare un timeout per la `operation`specificata oppure è stato fornito un valore non valido per `operation`.</span><span class="sxs-lookup"><span data-stu-id="05631-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05631-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="05631-133">Requirements</span></span>  
 <span data-ttu-id="05631-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05631-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05631-135">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="05631-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05631-136">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="05631-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05631-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05631-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05631-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05631-138">See also</span></span>

- [<span data-ttu-id="05631-139">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="05631-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="05631-140">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="05631-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="05631-141">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="05631-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
