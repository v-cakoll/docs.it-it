---
title: Metodo ICLRRuntimeHost::Start
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Start
helpviewer_keywords:
- ICLRRuntimeHost::Start method [.NET Framework hosting]
- Start method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: c0a6dce5-0a8d-42e8-808b-6ca14df9d289
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a9705e4449da3b485bef7e7250ca08473d51387b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehoststart-method"></a><span data-ttu-id="746de-102">Metodo ICLRRuntimeHost::Start</span><span class="sxs-lookup"><span data-stu-id="746de-102">ICLRRuntimeHost::Start Method</span></span>
<span data-ttu-id="746de-103">Inizializza common language runtime (CLR) in un processo.</span><span class="sxs-lookup"><span data-stu-id="746de-103">Initializes the common language runtime (CLR) into a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="746de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="746de-104">Syntax</span></span>  
  
```  
HRESULT Start();  
```  
  
## <a name="return-value"></a><span data-ttu-id="746de-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="746de-105">Return Value</span></span>  
  
|<span data-ttu-id="746de-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="746de-106">HRESULT</span></span>|<span data-ttu-id="746de-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="746de-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="746de-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="746de-108">S_OK</span></span>|<span data-ttu-id="746de-109">`Start`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="746de-109">`Start` returned successfully.</span></span>|  
|<span data-ttu-id="746de-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="746de-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="746de-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="746de-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="746de-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="746de-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="746de-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="746de-113">The call timed out.</span></span>|  
|<span data-ttu-id="746de-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="746de-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="746de-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="746de-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="746de-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="746de-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="746de-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="746de-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="746de-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="746de-118">E_FAIL</span></span>|<span data-ttu-id="746de-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="746de-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="746de-120">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="746de-120">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="746de-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="746de-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="746de-122">Note</span><span class="sxs-lookup"><span data-stu-id="746de-122">Remarks</span></span>  
 <span data-ttu-id="746de-123">In molti scenari non è necessario chiamare `Start`, perché il runtime viene inizializzato automaticamente alla prima richiesta per eseguire il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="746de-123">In many scenarios it is not necessary to call `Start`, because the runtime will initialize itself automatically upon the first request to run managed code.</span></span> <span data-ttu-id="746de-124">Tuttavia, è possibile utilizzare `Start` per specificare esattamente quando deve essere inizializzato il runtime.</span><span class="sxs-lookup"><span data-stu-id="746de-124">You can, however, use `Start` to specify exactly when the runtime should be initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="746de-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="746de-125">Requirements</span></span>  
 <span data-ttu-id="746de-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="746de-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="746de-127">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="746de-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="746de-128">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="746de-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="746de-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="746de-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="746de-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="746de-130">See Also</span></span>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="746de-131">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="746de-131">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
