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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45167a2b358b9a7a39390c07f552aa3f3dabce4f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108654"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="c7d52-102">Metodo IHostPolicyManager::OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="c7d52-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="c7d52-103">Notifica all'host che common language runtime (CLR) sta per eseguire l'azione predefinita che è stata impostata da una chiamata per il [SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) metodo in risposta a un'interruzione del thread o <xref:System.AppDomain> scaricare.</span><span class="sxs-lookup"><span data-stu-id="c7d52-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d52-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7d52-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7d52-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c7d52-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="c7d52-106">[in] Uno dei [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valori, che indica il tipo di evento a cui risponde il CLR.</span><span class="sxs-lookup"><span data-stu-id="c7d52-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="c7d52-107">[in] Uno dei [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valori, che indica l'azione che richiede CLR in risposta all'evento.</span><span class="sxs-lookup"><span data-stu-id="c7d52-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7d52-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c7d52-108">Return Value</span></span>  
  
|<span data-ttu-id="c7d52-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7d52-109">HRESULT</span></span>|<span data-ttu-id="c7d52-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7d52-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7d52-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7d52-111">S_OK</span></span>|`OnDefaultAction` <span data-ttu-id="c7d52-112">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c7d52-112">returned successfully.</span></span>|  
|<span data-ttu-id="c7d52-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c7d52-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c7d52-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c7d52-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="c7d52-115">successfully</span><span class="sxs-lookup"><span data-stu-id="c7d52-115">successfully</span></span>|  
|<span data-ttu-id="c7d52-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c7d52-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c7d52-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c7d52-117">The call timed out.</span></span>|  
|<span data-ttu-id="c7d52-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c7d52-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c7d52-119">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="c7d52-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c7d52-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c7d52-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c7d52-121">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c7d52-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c7d52-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7d52-122">E_FAIL</span></span>|<span data-ttu-id="c7d52-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c7d52-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7d52-124">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c7d52-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c7d52-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c7d52-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7d52-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7d52-126">Requirements</span></span>  
 <span data-ttu-id="c7d52-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7d52-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7d52-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7d52-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7d52-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c7d52-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c7d52-130">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c7d52-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c7d52-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7d52-131">See also</span></span>

- [<span data-ttu-id="c7d52-132">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="c7d52-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="c7d52-133">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="c7d52-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="c7d52-134">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c7d52-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="c7d52-135">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c7d52-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
