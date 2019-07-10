---
title: Metodo ICLRControl::GetCLRManager
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86299a1f64120b3ca0ec858975b824b7e7288af9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773255"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="6aa26-102">Metodo ICLRControl::GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="6aa26-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="6aa26-103">Ottiene un puntatore a interfaccia a un'istanza di uno qualsiasi dei tipi di gestione che di host può utilizzare per configurare common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="6aa26-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa26-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6aa26-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aa26-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6aa26-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="6aa26-106">[in] Il `IID` del tipo di gestione da restituire.</span><span class="sxs-lookup"><span data-stu-id="6aa26-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="6aa26-107">Nell'esempio `IID` sono supportati i valori.</span><span class="sxs-lookup"><span data-stu-id="6aa26-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="6aa26-108">IID_ICLRDebugManager: Specifica che `ppObject` sarà di tipo [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6aa26-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="6aa26-109">IID_ICLRErrorReportingManager: Specifica che `ppObject` sarà di tipo [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6aa26-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="6aa26-110">IID_ICLRGCManager: Specifica che `ppObject` sarà di tipo [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6aa26-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="6aa26-111">IID_ICLRHostProtectionManager: Specifica che `ppObject` sarà di tipo [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6aa26-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="6aa26-112">IID_ICLROnEventManager: Specifica che `ppObject` sarà di tipo [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6aa26-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="6aa26-113">IID_ICLRPolicyManager: Specifica che `ppObject` sarà di tipo [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6aa26-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="6aa26-114">IID_ICLRTaskManager: Specifica che `ppObject` sarà di tipo [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6aa26-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="6aa26-115">[out] Un puntatore a interfaccia per il gestore richiesto o null, se è stato richiesto un tipo di gestione non è valido.</span><span class="sxs-lookup"><span data-stu-id="6aa26-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6aa26-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6aa26-116">Return Value</span></span>  
  
|<span data-ttu-id="6aa26-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6aa26-117">HRESULT</span></span>|<span data-ttu-id="6aa26-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6aa26-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6aa26-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="6aa26-119">S_OK</span></span>|<span data-ttu-id="6aa26-120">Il metodo è stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6aa26-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="6aa26-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6aa26-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6aa26-122">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6aa26-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6aa26-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6aa26-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6aa26-124">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6aa26-124">The call timed out.</span></span>|  
|<span data-ttu-id="6aa26-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6aa26-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6aa26-126">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="6aa26-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6aa26-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6aa26-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6aa26-128">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6aa26-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6aa26-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6aa26-129">E_FAIL</span></span>|<span data-ttu-id="6aa26-130">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6aa26-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6aa26-131">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6aa26-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6aa26-132">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6aa26-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6aa26-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="6aa26-133">E_NOINTERFACE</span></span>|<span data-ttu-id="6aa26-134">Il tipo di interfaccia non è supportato.</span><span class="sxs-lookup"><span data-stu-id="6aa26-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6aa26-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6aa26-135">Requirements</span></span>  
 <span data-ttu-id="6aa26-136">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6aa26-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aa26-137">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6aa26-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6aa26-138">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6aa26-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6aa26-139">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aa26-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa26-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6aa26-140">See also</span></span>

- [<span data-ttu-id="6aa26-141">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="6aa26-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="6aa26-142">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="6aa26-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
