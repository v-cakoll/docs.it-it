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
ms.openlocfilehash: 8d987614c1a5a2c90ccb3faa11c605767ae5cfda
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178026"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="d598c-102">Metodo IHostPolicyManager::OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="d598c-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="d598c-103">Notifica all'host che Common Language Runtime (CLR) sta per eseguire l'azione predefinita impostata da una chiamata al metodo [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in risposta all'interruzione o <xref:System.AppDomain> allo scaricamento di un thread.</span><span class="sxs-lookup"><span data-stu-id="d598c-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d598c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d598c-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d598c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d598c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="d598c-106">[in] Uno dei valori [di EClrOperation,](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) che indica il tipo di evento a cui CLR risponde.</span><span class="sxs-lookup"><span data-stu-id="d598c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="d598c-107">[in] Uno dei valori di [EPolicyAction,](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) che indica l'azione che CLR sta intraprendendo in risposta all'evento.</span><span class="sxs-lookup"><span data-stu-id="d598c-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d598c-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d598c-108">Return Value</span></span>  
  
|<span data-ttu-id="d598c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d598c-109">HRESULT</span></span>|<span data-ttu-id="d598c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d598c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d598c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d598c-111">S_OK</span></span>|<span data-ttu-id="d598c-112">`OnDefaultAction`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="d598c-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="d598c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d598c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d598c-114">CLR non è stato caricato in un processo o CLR si trova in uno stato in cui non può eseguire codice gestito o elaborare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d598c-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="d598c-115">Correttamente</span><span class="sxs-lookup"><span data-stu-id="d598c-115">successfully</span></span>|  
|<span data-ttu-id="d598c-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d598c-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d598c-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d598c-117">The call timed out.</span></span>|  
|<span data-ttu-id="d598c-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d598c-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d598c-119">Il chiamante non è proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="d598c-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d598c-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d598c-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d598c-121">Un evento è stato annullato mentre un thread bloccato o una fibra era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d598c-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d598c-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d598c-122">E_FAIL</span></span>|<span data-ttu-id="d598c-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d598c-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d598c-124">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d598c-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d598c-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d598c-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d598c-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d598c-126">Requirements</span></span>  
 <span data-ttu-id="d598c-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d598c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d598c-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d598c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d598c-129">**Biblioteca:** Incluso come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d598c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d598c-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d598c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d598c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d598c-131">See also</span></span>

- [<span data-ttu-id="d598c-132">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="d598c-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="d598c-133">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="d598c-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="d598c-134">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="d598c-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="d598c-135">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="d598c-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
