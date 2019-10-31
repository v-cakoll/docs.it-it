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
ms.openlocfilehash: 6ba7b7adc104db528293d77c3591370c6ce02c25
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128594"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="e9ce7-102">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="e9ce7-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="e9ce7-103">Fornisce metodi che notificano all'host le azioni eseguite dal Common Language Runtime (CLR) in caso di interruzioni, timeout o errori.</span><span class="sxs-lookup"><span data-stu-id="e9ce7-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9ce7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e9ce7-104">Methods</span></span>  
  
|<span data-ttu-id="e9ce7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e9ce7-105">Method</span></span>|<span data-ttu-id="e9ce7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9ce7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9ce7-107">Metodo OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="e9ce7-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="e9ce7-108">Notifica all'host che il CLR sta per eseguire l'azione predefinita specificata da una chiamata a [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in risposta a un'interruzione del thread o a <xref:System.AppDomain> Unload.</span><span class="sxs-lookup"><span data-stu-id="e9ce7-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="e9ce7-109">Metodo OnFailure</span><span class="sxs-lookup"><span data-stu-id="e9ce7-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="e9ce7-110">Notifica all'host che il CLR sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in risposta a un errore di allocazione delle risorse o di recupero.</span><span class="sxs-lookup"><span data-stu-id="e9ce7-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="e9ce7-111">Metodo OnTimeout</span><span class="sxs-lookup"><span data-stu-id="e9ce7-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="e9ce7-112">Notifica all'host che il CLR sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in risposta a un timeout.</span><span class="sxs-lookup"><span data-stu-id="e9ce7-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9ce7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9ce7-113">Requirements</span></span>  
 <span data-ttu-id="e9ce7-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9ce7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9ce7-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e9ce7-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9ce7-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e9ce7-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9ce7-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9ce7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9ce7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9ce7-118">See also</span></span>

- [<span data-ttu-id="e9ce7-119">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="e9ce7-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="e9ce7-120">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="e9ce7-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="e9ce7-121">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="e9ce7-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="e9ce7-122">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="e9ce7-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="e9ce7-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="e9ce7-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
