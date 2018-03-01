---
title: Interfaccia ICLRPolicyManager
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
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ce37f9beb0901eaf1bc98f5af3f8f99a7fedf1c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="e1cc5-102">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="e1cc5-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="e1cc5-103">Fornisce metodi che consentono all'host specificare le azioni da intraprendere in caso di errori e i timeout dei criteri.</span><span class="sxs-lookup"><span data-stu-id="e1cc5-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e1cc5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e1cc5-104">Methods</span></span>  
  
|<span data-ttu-id="e1cc5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e1cc5-105">Method</span></span>|<span data-ttu-id="e1cc5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e1cc5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e1cc5-107">Metodo SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="e1cc5-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="e1cc5-108">Specifica l'azione di criteri che Common language runtime (CLR) deve intraprendere quando si verifica l'errore specificato.</span><span class="sxs-lookup"><span data-stu-id="e1cc5-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="e1cc5-109">Metodo SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="e1cc5-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="e1cc5-110">Specifica l'azione di criteri che CLR deve intraprendere quando timeout dell'operazione specificato.</span><span class="sxs-lookup"><span data-stu-id="e1cc5-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="e1cc5-111">Metodo SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="e1cc5-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="e1cc5-112">Specifica l'azione di criteri che CLR deve essere eseguita quando si verifica l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="e1cc5-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="e1cc5-113">Metodo SetTimeout</span><span class="sxs-lookup"><span data-stu-id="e1cc5-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="e1cc5-114">Imposta un valore di timeout per l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="e1cc5-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="e1cc5-115">Metodo SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="e1cc5-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="e1cc5-116">Imposta un valore di timeout per l'operazione specificata e specifica l'azione di criteri che CLR deve essere eseguita quando l'operazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="e1cc5-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="e1cc5-117">Metodo SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="e1cc5-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="e1cc5-118">Specifica il comportamento di CLR quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="e1cc5-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e1cc5-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1cc5-119">Requirements</span></span>  
 <span data-ttu-id="e1cc5-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1cc5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1cc5-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e1cc5-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e1cc5-122">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e1cc5-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1cc5-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1cc5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1cc5-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1cc5-124">See Also</span></span>  
 [<span data-ttu-id="e1cc5-125">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="e1cc5-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="e1cc5-126">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="e1cc5-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="e1cc5-127">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="e1cc5-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="e1cc5-128">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="e1cc5-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
