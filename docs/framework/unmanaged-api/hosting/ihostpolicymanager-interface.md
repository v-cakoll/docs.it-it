---
title: Interfaccia IHostPolicyManager
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: d6b34403a45cc40863d79b59396041e496989045
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503939"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="a3c36-102">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a3c36-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="a3c36-103">Fornisce metodi che notificano all'host le azioni eseguite dal Common Language Runtime (CLR) in caso di interruzioni, timeout o errori.</span><span class="sxs-lookup"><span data-stu-id="a3c36-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a3c36-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a3c36-104">Methods</span></span>  
  
|<span data-ttu-id="a3c36-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a3c36-105">Method</span></span>|<span data-ttu-id="a3c36-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3c36-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a3c36-107">Metodo OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="a3c36-107">OnDefaultAction Method</span></span>](ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="a3c36-108">Notifica all'host che il CLR sta per eseguire l'azione predefinita specificata da una chiamata a [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in risposta a un'interruzione o a uno scaricamento di un thread <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="a3c36-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="a3c36-109">Metodo OnFailure</span><span class="sxs-lookup"><span data-stu-id="a3c36-109">OnFailure Method</span></span>](ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="a3c36-110">Notifica all'host che il CLR sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in risposta a un errore di allocazione delle risorse o di recupero.</span><span class="sxs-lookup"><span data-stu-id="a3c36-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="a3c36-111">Metodo OnTimeout</span><span class="sxs-lookup"><span data-stu-id="a3c36-111">OnTimeout Method</span></span>](ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="a3c36-112">Notifica all'host che il CLR sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in risposta a un timeout.</span><span class="sxs-lookup"><span data-stu-id="a3c36-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a3c36-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3c36-113">Requirements</span></span>  
 <span data-ttu-id="a3c36-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3c36-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3c36-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a3c36-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3c36-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a3c36-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3c36-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3c36-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c36-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3c36-118">See also</span></span>

- [<span data-ttu-id="a3c36-119">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="a3c36-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="a3c36-120">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="a3c36-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="a3c36-121">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="a3c36-121">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="a3c36-122">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a3c36-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="a3c36-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="a3c36-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
