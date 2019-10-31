---
title: Metodo IHostPolicyManager::OnDefaultAction
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
ms.openlocfilehash: cdf0a720ac440d156b5b8bdc8dc2c78d3bb5ba86
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128565"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="02530-102">Metodo IHostPolicyManager::OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="02530-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="02530-103">Notifica all'host che la Common Language Runtime (CLR) sta per eseguire l'azione predefinita impostata da una chiamata al metodo [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in risposta a un'interruzione di thread o a <xref:System.AppDomain> Unload.</span><span class="sxs-lookup"><span data-stu-id="02530-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02530-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="02530-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02530-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="02530-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="02530-106">in Uno dei valori di [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) , che indica il tipo di evento a cui CLR risponde.</span><span class="sxs-lookup"><span data-stu-id="02530-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="02530-107">in Uno dei valori di [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , che indica l'azione che CLR sta prendendo in risposta all'evento.</span><span class="sxs-lookup"><span data-stu-id="02530-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02530-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="02530-108">Return Value</span></span>  
  
|<span data-ttu-id="02530-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02530-109">HRESULT</span></span>|<span data-ttu-id="02530-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="02530-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="02530-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="02530-111">S_OK</span></span>|<span data-ttu-id="02530-112">`OnDefaultAction` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="02530-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="02530-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="02530-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="02530-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="02530-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="02530-115">correttamente</span><span class="sxs-lookup"><span data-stu-id="02530-115">successfully</span></span>|  
|<span data-ttu-id="02530-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="02530-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="02530-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="02530-117">The call timed out.</span></span>|  
|<span data-ttu-id="02530-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="02530-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="02530-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="02530-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="02530-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="02530-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="02530-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="02530-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="02530-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="02530-122">E_FAIL</span></span>|<span data-ttu-id="02530-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="02530-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="02530-124">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="02530-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="02530-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="02530-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02530-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="02530-126">Requirements</span></span>  
 <span data-ttu-id="02530-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02530-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02530-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="02530-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="02530-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="02530-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="02530-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02530-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02530-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02530-131">See also</span></span>

- [<span data-ttu-id="02530-132">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="02530-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="02530-133">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="02530-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="02530-134">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="02530-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="02530-135">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="02530-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
