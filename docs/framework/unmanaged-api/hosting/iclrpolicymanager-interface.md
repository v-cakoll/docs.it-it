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
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140800"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="6e9fd-102">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="6e9fd-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="6e9fd-103">Fornisce metodi che consentono all'host di specificare le azioni dei criteri da intraprendere in caso di errori e timeout.</span><span class="sxs-lookup"><span data-stu-id="6e9fd-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6e9fd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6e9fd-104">Methods</span></span>  
  
|<span data-ttu-id="6e9fd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6e9fd-105">Method</span></span>|<span data-ttu-id="6e9fd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e9fd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6e9fd-107">Metodo SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="6e9fd-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="6e9fd-108">Specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica l'errore specificato.</span><span class="sxs-lookup"><span data-stu-id="6e9fd-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="6e9fd-109">Metodo SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="6e9fd-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="6e9fd-110">Specifica l'azione del criterio che CLR deve eseguire quando si verifica il timeout dell'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="6e9fd-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="6e9fd-111">Metodo SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="6e9fd-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="6e9fd-112">Specifica l'azione del criterio che CLR deve eseguire quando si verifica l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="6e9fd-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="6e9fd-113">Metodo SetTimeout</span><span class="sxs-lookup"><span data-stu-id="6e9fd-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="6e9fd-114">Imposta un valore di timeout per l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="6e9fd-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="6e9fd-115">Metodo SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="6e9fd-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="6e9fd-116">Imposta un valore di timeout per l'operazione specificata e specifica l'azione del criterio che CLR deve eseguire quando si verifica l'operazione.</span><span class="sxs-lookup"><span data-stu-id="6e9fd-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="6e9fd-117">Metodo SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="6e9fd-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="6e9fd-118">Specifica il comportamento di CLR quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="6e9fd-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e9fd-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e9fd-119">Requirements</span></span>  
 <span data-ttu-id="6e9fd-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e9fd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e9fd-121">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6e9fd-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6e9fd-122">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6e9fd-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e9fd-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e9fd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9fd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e9fd-124">See also</span></span>

- [<span data-ttu-id="6e9fd-125">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="6e9fd-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="6e9fd-126">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="6e9fd-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="6e9fd-127">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="6e9fd-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="6e9fd-128">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="6e9fd-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
