---
title: Interfaccia ICLRPolicyManager
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e8a1b1bcf4470f5e754775b1137b8221ae1d0b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435147"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="e9071-102">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="e9071-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="e9071-103">Fornisce metodi che consentono all'host specificare le azioni da intraprendere in caso di errori e i timeout dei criteri.</span><span class="sxs-lookup"><span data-stu-id="e9071-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9071-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e9071-104">Methods</span></span>  
  
|<span data-ttu-id="e9071-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e9071-105">Method</span></span>|<span data-ttu-id="e9071-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9071-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9071-107">Metodo SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="e9071-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="e9071-108">Specifica l'azione di criteri che Common language runtime (CLR) deve intraprendere quando si verifica l'errore specificato.</span><span class="sxs-lookup"><span data-stu-id="e9071-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="e9071-109">Metodo SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="e9071-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="e9071-110">Specifica l'azione di criteri che CLR deve intraprendere quando timeout dell'operazione specificato.</span><span class="sxs-lookup"><span data-stu-id="e9071-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="e9071-111">Metodo SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="e9071-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="e9071-112">Specifica l'azione di criteri che CLR deve essere eseguita quando si verifica l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="e9071-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="e9071-113">Metodo SetTimeout</span><span class="sxs-lookup"><span data-stu-id="e9071-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="e9071-114">Imposta un valore di timeout per l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="e9071-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="e9071-115">Metodo SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="e9071-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="e9071-116">Imposta un valore di timeout per l'operazione specificata e specifica l'azione di criteri che CLR deve essere eseguita quando l'operazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="e9071-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="e9071-117">Metodo SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="e9071-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="e9071-118">Specifica il comportamento di CLR quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="e9071-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9071-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9071-119">Requirements</span></span>  
 <span data-ttu-id="e9071-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9071-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9071-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e9071-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9071-122">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e9071-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9071-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9071-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9071-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9071-124">See Also</span></span>  
 [<span data-ttu-id="e9071-125">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="e9071-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="e9071-126">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="e9071-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="e9071-127">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="e9071-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="e9071-128">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="e9071-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
