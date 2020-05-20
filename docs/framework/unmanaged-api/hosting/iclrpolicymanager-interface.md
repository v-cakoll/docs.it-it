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
ms.openlocfilehash: 631301a10aee96bb00aeda6b0b8695f0aea186a8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703485"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="bd963-102">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="bd963-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="bd963-103">Fornisce metodi che consentono all'host di specificare le azioni dei criteri da intraprendere in caso di errori e timeout.</span><span class="sxs-lookup"><span data-stu-id="bd963-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bd963-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="bd963-104">Methods</span></span>  
  
|<span data-ttu-id="bd963-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="bd963-105">Method</span></span>|<span data-ttu-id="bd963-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bd963-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bd963-107">Metodo SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="bd963-107">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="bd963-108">Specifica l'azione del criterio che il Common Language Runtime (CLR) deve eseguire quando si verifica l'errore specificato.</span><span class="sxs-lookup"><span data-stu-id="bd963-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="bd963-109">Metodo SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="bd963-109">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="bd963-110">Specifica l'azione del criterio che CLR deve eseguire quando si verifica il timeout dell'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="bd963-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="bd963-111">Metodo SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="bd963-111">SetDefaultAction Method</span></span>](iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="bd963-112">Specifica l'azione del criterio che CLR deve eseguire quando si verifica l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="bd963-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="bd963-113">Metodo SetTimeout</span><span class="sxs-lookup"><span data-stu-id="bd963-113">SetTimeout Method</span></span>](iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="bd963-114">Imposta un valore di timeout per l'operazione specificata.</span><span class="sxs-lookup"><span data-stu-id="bd963-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="bd963-115">Metodo SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="bd963-115">SetTimeoutAndAction Method</span></span>](iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="bd963-116">Imposta un valore di timeout per l'operazione specificata e specifica l'azione del criterio che CLR deve eseguire quando si verifica l'operazione.</span><span class="sxs-lookup"><span data-stu-id="bd963-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="bd963-117">Metodo SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="bd963-117">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="bd963-118">Specifica il comportamento di CLR quando si verifica un'eccezione non gestita.</span><span class="sxs-lookup"><span data-stu-id="bd963-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd963-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd963-119">Requirements</span></span>  
 <span data-ttu-id="bd963-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd963-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd963-121">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bd963-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd963-122">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bd963-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd963-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd963-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd963-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd963-124">See also</span></span>

- [<span data-ttu-id="bd963-125">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="bd963-125">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="bd963-126">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="bd963-126">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="bd963-127">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="bd963-127">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="bd963-128">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="bd963-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
