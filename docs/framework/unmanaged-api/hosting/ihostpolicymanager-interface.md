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
ms.openlocfilehash: db089a55128fa675ceedf157b046fe205d8c6b51
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804335"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="15021-102">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="15021-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="15021-103">Fornisce metodi che notificano all'host le azioni eseguite dal Common Language Runtime (CLR) in caso di interruzioni, timeout o errori.</span><span class="sxs-lookup"><span data-stu-id="15021-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15021-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="15021-104">Methods</span></span>  
  
|<span data-ttu-id="15021-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="15021-105">Method</span></span>|<span data-ttu-id="15021-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="15021-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15021-107">Metodo OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="15021-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="15021-108">Notifica all'host che il CLR sta per eseguire l'azione predefinita specificata da una chiamata a [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in risposta a un'interruzione o a uno scaricamento di un thread <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="15021-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="15021-109">Metodo OnFailure</span><span class="sxs-lookup"><span data-stu-id="15021-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="15021-110">Notifica all'host che il CLR sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager:: SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in risposta a un errore di allocazione delle risorse o di recupero.</span><span class="sxs-lookup"><span data-stu-id="15021-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="15021-111">Metodo OnTimeout</span><span class="sxs-lookup"><span data-stu-id="15021-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="15021-112">Notifica all'host che il CLR sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager:: SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in risposta a un timeout.</span><span class="sxs-lookup"><span data-stu-id="15021-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15021-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15021-113">Requirements</span></span>  
 <span data-ttu-id="15021-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15021-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15021-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="15021-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15021-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="15021-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15021-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15021-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15021-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15021-118">See also</span></span>

- [<span data-ttu-id="15021-119">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="15021-119">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="15021-120">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="15021-120">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="15021-121">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="15021-121">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="15021-122">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="15021-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="15021-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="15021-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
