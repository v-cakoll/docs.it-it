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
ms.openlocfilehash: e6aa8cb814e509d310c2f5b5524e0fd6727fc43f
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804277"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="e5818-102">Metodo IHostPolicyManager::OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="e5818-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="e5818-103">Notifica all'host che la Common Language Runtime (CLR) sta per eseguire l'azione predefinita impostata da una chiamata al metodo [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in risposta a un'interruzione del thread o a uno <xref:System.AppDomain> scaricamento.</span><span class="sxs-lookup"><span data-stu-id="e5818-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5818-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5818-104">Syntax</span></span>  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5818-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5818-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="e5818-106">in Uno dei valori di [EClrOperation](eclroperation-enumeration.md) , che indica il tipo di evento a cui CLR risponde.</span><span class="sxs-lookup"><span data-stu-id="e5818-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="e5818-107">in Uno dei valori di [EPolicyAction](epolicyaction-enumeration.md) , che indica l'azione che CLR sta prendendo in risposta all'evento.</span><span class="sxs-lookup"><span data-stu-id="e5818-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5818-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e5818-108">Return Value</span></span>  
  
|<span data-ttu-id="e5818-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e5818-109">HRESULT</span></span>|<span data-ttu-id="e5818-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e5818-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e5818-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e5818-111">S_OK</span></span>|<span data-ttu-id="e5818-112">`OnDefaultAction`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e5818-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="e5818-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e5818-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e5818-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e5818-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="e5818-115">correttamente</span><span class="sxs-lookup"><span data-stu-id="e5818-115">successfully</span></span>|  
|<span data-ttu-id="e5818-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e5818-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e5818-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e5818-117">The call timed out.</span></span>|  
|<span data-ttu-id="e5818-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e5818-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e5818-119">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e5818-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e5818-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e5818-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e5818-121">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e5818-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e5818-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e5818-122">E_FAIL</span></span>|<span data-ttu-id="e5818-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e5818-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e5818-124">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e5818-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e5818-125">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e5818-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5818-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5818-126">Requirements</span></span>  
 <span data-ttu-id="e5818-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5818-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5818-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e5818-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e5818-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e5818-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5818-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5818-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5818-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5818-131">See also</span></span>

- [<span data-ttu-id="e5818-132">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="e5818-132">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="e5818-133">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="e5818-133">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="e5818-134">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="e5818-134">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="e5818-135">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="e5818-135">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
