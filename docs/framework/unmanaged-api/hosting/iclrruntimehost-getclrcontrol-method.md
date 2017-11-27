---
title: Metodo ICLRRuntimeHost::GetCLRControl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.GetCLRControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4072c21ea002523fe8086151a40c4e17b775ebbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="a0f2e-102">Metodo ICLRRuntimeHost::GetCLRControl</span><span class="sxs-lookup"><span data-stu-id="a0f2e-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="a0f2e-103">Ottiene un puntatore a interfaccia di tipo [interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) che gli host possono usare per personalizzare gli aspetti di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a0f2e-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0f2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0f2e-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0f2e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0f2e-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="a0f2e-106">[out] Un puntatore a interfaccia di tipo [interfaccia ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) che consente agli host di configurare altri aspetti di CLR.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0f2e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a0f2e-107">Return Value</span></span>  
  
|<span data-ttu-id="a0f2e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0f2e-108">HRESULT</span></span>|<span data-ttu-id="a0f2e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a0f2e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0f2e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0f2e-110">S_OK</span></span>|<span data-ttu-id="a0f2e-111">`GetCLRControl`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="a0f2e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0f2e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0f2e-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0f2e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0f2e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0f2e-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-115">The call timed out.</span></span>|  
|<span data-ttu-id="a0f2e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0f2e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0f2e-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0f2e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0f2e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0f2e-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0f2e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0f2e-120">E_FAIL</span></span>|<span data-ttu-id="a0f2e-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0f2e-122">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0f2e-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a0f2e-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="a0f2e-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="a0f2e-125">CLR è già avviato.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0f2e-126">Note</span><span class="sxs-lookup"><span data-stu-id="a0f2e-126">Remarks</span></span>  
 <span data-ttu-id="a0f2e-127">`ICLRControl`fornisce il [GetCLRManager (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) metodo, che consente all'host di ottenere un puntatore a interfaccia a uno dei tipi di gestore.</span><span class="sxs-lookup"><span data-stu-id="a0f2e-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0f2e-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0f2e-128">Requirements</span></span>  
 <span data-ttu-id="a0f2e-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0f2e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0f2e-130">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a0f2e-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0f2e-131">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a0f2e-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0f2e-132">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0f2e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f2e-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0f2e-133">See Also</span></span>  
 [<span data-ttu-id="a0f2e-134">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a0f2e-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="a0f2e-135">ICLRRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a0f2e-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
