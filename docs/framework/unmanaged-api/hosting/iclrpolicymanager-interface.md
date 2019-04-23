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
ms.openlocfilehash: 2eeccc4dfd7a7147fe791444eeeca2bd3a844305
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211048"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="0c281-102">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="0c281-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="0c281-103">Fornisce metodi che consentono all'host specificare le azioni dei criteri da eseguire in caso di errori o timeout.</span><span class="sxs-lookup"><span data-stu-id="0c281-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c281-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0c281-104">Methods</span></span>  
  
|<span data-ttu-id="0c281-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0c281-105">Method</span></span>|<span data-ttu-id="0c281-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c281-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c281-107">Metodo SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="0c281-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="0c281-108">Specifica l'azione di criteri che Common language runtime (CLR) deve essere intrapresa quando si verifica l'errore specificato.</span><span class="sxs-lookup"><span data-stu-id="0c281-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="0c281-109">Metodo SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="0c281-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="0c281-110">Specifica l'azione di criteri che CLR deve essere intrapresa quando scade l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="0c281-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="0c281-111">Metodo SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="0c281-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="0c281-112">Specifica l'azione di criteri che CLR deve essere intrapresa quando si verifica l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="0c281-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="0c281-113">Metodo SetTimeout</span><span class="sxs-lookup"><span data-stu-id="0c281-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="0c281-114">Imposta un valore di timeout per l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="0c281-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="0c281-115">Metodo SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="0c281-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="0c281-116">Imposta un valore di timeout per l'operazione specificata e specifica l'azione di criteri che CLR deve intraprendere quando l'operazione viene eseguita.</span><span class="sxs-lookup"><span data-stu-id="0c281-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="0c281-117">Metodo SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="0c281-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="0c281-118">Specifica il comportamento di CLR quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="0c281-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c281-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c281-119">Requirements</span></span>  
 <span data-ttu-id="0c281-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c281-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c281-121">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c281-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c281-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0c281-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c281-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c281-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c281-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c281-124">See also</span></span>

- [<span data-ttu-id="0c281-125">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="0c281-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="0c281-126">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="0c281-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="0c281-127">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="0c281-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="0c281-128">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="0c281-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
