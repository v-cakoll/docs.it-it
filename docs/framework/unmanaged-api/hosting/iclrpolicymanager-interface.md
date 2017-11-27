---
title: Interfaccia ICLRPolicyManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager
helpviewer_keywords: ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f3dd904184b730a5b0f5b2dfcac4197e708544d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="f0c4f-102">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="f0c4f-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="f0c4f-103">Fornisce metodi che consentono all'host specificare le azioni da intraprendere in caso di errori e i timeout dei criteri.</span><span class="sxs-lookup"><span data-stu-id="f0c4f-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0c4f-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f0c4f-104">Methods</span></span>  
  
|<span data-ttu-id="f0c4f-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f0c4f-105">Method</span></span>|<span data-ttu-id="f0c4f-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0c4f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0c4f-107">SetActionOnFailure (metodo)</span><span class="sxs-lookup"><span data-stu-id="f0c4f-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="f0c4f-108">Specifica l'azione di criteri che Common language runtime (CLR) deve intraprendere quando si verifica l'errore specificato.</span><span class="sxs-lookup"><span data-stu-id="f0c4f-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="f0c4f-109">SetActionOnTimeout (metodo)</span><span class="sxs-lookup"><span data-stu-id="f0c4f-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="f0c4f-110">Specifica l'azione di criteri che CLR deve intraprendere quando timeout dell'operazione specificato.</span><span class="sxs-lookup"><span data-stu-id="f0c4f-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="f0c4f-111">SetDefaultAction (metodo)</span><span class="sxs-lookup"><span data-stu-id="f0c4f-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="f0c4f-112">Specifica l'azione di criteri che CLR deve essere eseguita quando si verifica l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="f0c4f-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="f0c4f-113">SetTimeout (metodo)</span><span class="sxs-lookup"><span data-stu-id="f0c4f-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="f0c4f-114">Imposta un valore di timeout per l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="f0c4f-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="f0c4f-115">SetTimeoutAndAction (metodo)</span><span class="sxs-lookup"><span data-stu-id="f0c4f-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="f0c4f-116">Imposta un valore di timeout per l'operazione specificata e specifica l'azione di criteri che CLR deve essere eseguita quando l'operazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="f0c4f-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="f0c4f-117">SetUnhandledExceptionPolicy (metodo)</span><span class="sxs-lookup"><span data-stu-id="f0c4f-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="f0c4f-118">Specifica il comportamento di CLR quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="f0c4f-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0c4f-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0c4f-119">Requirements</span></span>  
 <span data-ttu-id="f0c4f-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0c4f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0c4f-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f0c4f-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0c4f-122">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f0c4f-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0c4f-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0c4f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0c4f-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0c4f-124">See Also</span></span>  
 [<span data-ttu-id="f0c4f-125">EClrFailure (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="f0c4f-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="f0c4f-126">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="f0c4f-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="f0c4f-127">EPolicyAction (enumerazione)</span><span class="sxs-lookup"><span data-stu-id="f0c4f-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="f0c4f-128">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f0c4f-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
