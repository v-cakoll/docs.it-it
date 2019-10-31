---
title: Metodo ICLRPolicyManager::SetUnhandledExceptionPolicy
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
ms.openlocfilehash: 7b6a4be94e526e7b464b336d221eff936808635a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120578"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="2e6a4-102">Metodo ICLRPolicyManager::SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="2e6a4-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="2e6a4-103">Specifica il comportamento del Common Language Runtime (CLR) quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e6a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e6a4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e6a4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2e6a4-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="2e6a4-106">in Uno dei valori di [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) , che indica se il comportamento è impostato da CLR o dall'host.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e6a4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2e6a4-107">Return Value</span></span>  
  
|<span data-ttu-id="2e6a4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e6a4-108">HRESULT</span></span>|<span data-ttu-id="2e6a4-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e6a4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e6a4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2e6a4-110">S_OK</span></span>|<span data-ttu-id="2e6a4-111">`SetUnhandledExceptionPolicy` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="2e6a4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2e6a4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2e6a4-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2e6a4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2e6a4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2e6a4-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-115">The call timed out.</span></span>|  
|<span data-ttu-id="2e6a4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2e6a4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2e6a4-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2e6a4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2e6a4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2e6a4-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2e6a4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2e6a4-120">E_FAIL</span></span>|<span data-ttu-id="2e6a4-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2e6a4-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2e6a4-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e6a4-124">Note</span><span class="sxs-lookup"><span data-stu-id="2e6a4-124">Remarks</span></span>  
 <span data-ttu-id="2e6a4-125">Per impostazione predefinita, CLR è il gestore finale per tutte le eccezioni non gestite e il comportamento predefinito prevede la rimozione del processo.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="2e6a4-126">L'host può modificare questo comportamento impostando il valore `policy` su eHostDeterminedPolicy.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="2e6a4-127">Questo valore consente all'host di implementare il proprio comportamento predefinito, come con le versioni precedenti di CLR.</span><span class="sxs-lookup"><span data-stu-id="2e6a4-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e6a4-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e6a4-128">Requirements</span></span>  
 <span data-ttu-id="2e6a4-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e6a4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e6a4-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2e6a4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e6a4-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2e6a4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e6a4-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e6a4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e6a4-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e6a4-133">See also</span></span>

- [<span data-ttu-id="2e6a4-134">Enumerazione EClrUnhandledException</span><span class="sxs-lookup"><span data-stu-id="2e6a4-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="2e6a4-135">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="2e6a4-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="2e6a4-136">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="2e6a4-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="2e6a4-137">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="2e6a4-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
