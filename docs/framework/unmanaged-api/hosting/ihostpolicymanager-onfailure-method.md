---
title: Metodo IHostPolicyManager::OnFailure
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
ms.openlocfilehash: 8ad4943aa9bf1b66b34bcd83a5422a977b16518d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804224"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="b28d7-102">Metodo IHostPolicyManager::OnFailure</span><span class="sxs-lookup"><span data-stu-id="b28d7-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="b28d7-103">Notifica all'host che la Common Language Runtime (CLR) sta per eseguire l'azione specificata da una chiamata al metodo [ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in risposta a un errore di allocazione delle risorse o di recupero.</span><span class="sxs-lookup"><span data-stu-id="b28d7-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b28d7-104">Syntax</span></span>  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b28d7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b28d7-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="b28d7-106">in Uno dei valori di [EClrFailure](eclrfailure-enumeration.md) , che indica il tipo di errore a cui CLR risponde.</span><span class="sxs-lookup"><span data-stu-id="b28d7-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="b28d7-107">in Uno dei valori di [EPolicyAction](epolicyaction-enumeration.md) , che indica l'azione che CLR sta prendendo in risposta `failure` .</span><span class="sxs-lookup"><span data-stu-id="b28d7-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b28d7-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b28d7-108">Return Value</span></span>  
  
|<span data-ttu-id="b28d7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b28d7-109">HRESULT</span></span>|<span data-ttu-id="b28d7-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b28d7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b28d7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b28d7-111">S_OK</span></span>|<span data-ttu-id="b28d7-112">`OnFailure`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b28d7-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="b28d7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b28d7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b28d7-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b28d7-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b28d7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b28d7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b28d7-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b28d7-116">The call timed out.</span></span>|  
|<span data-ttu-id="b28d7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b28d7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b28d7-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="b28d7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b28d7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b28d7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b28d7-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b28d7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b28d7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b28d7-121">E_FAIL</span></span>|<span data-ttu-id="b28d7-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b28d7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b28d7-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b28d7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b28d7-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b28d7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b28d7-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b28d7-125">Requirements</span></span>  
 <span data-ttu-id="b28d7-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b28d7-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b28d7-127">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b28d7-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b28d7-128">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b28d7-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b28d7-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b28d7-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28d7-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b28d7-130">See also</span></span>

- [<span data-ttu-id="b28d7-131">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="b28d7-131">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="b28d7-132">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="b28d7-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="b28d7-133">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="b28d7-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="b28d7-134">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="b28d7-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
