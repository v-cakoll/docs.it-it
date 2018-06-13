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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7247dddc2d3313948fe6f49fbaa1440b141c4cf3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440765"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="1c1f3-102">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="1c1f3-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="1c1f3-103">Fornisce metodi per notificare all'host le azioni eseguite da common language runtime (CLR) in caso di interruzioni, timeout o errori.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c1f3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1c1f3-104">Methods</span></span>  
  
|<span data-ttu-id="1c1f3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1c1f3-105">Method</span></span>|<span data-ttu-id="1c1f3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1c1f3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c1f3-107">Metodo OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="1c1f3-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="1c1f3-108">Notifica all'host che Common Language Runtime sta per eseguire l'azione predefinita specificata da una chiamata a [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in risposta a un thread di interruzione o <xref:System.AppDomain> scaricare.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="1c1f3-109">Metodo OnFailure</span><span class="sxs-lookup"><span data-stu-id="1c1f3-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="1c1f3-110">Notifica all'host che Common Language Runtime sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in risposta a un errore di allocazione o il recupero di risorse.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="1c1f3-111">Metodo OnTimeout</span><span class="sxs-lookup"><span data-stu-id="1c1f3-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="1c1f3-112">Notifica all'host che Common Language Runtime sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager::](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in risposta a un timeout.</span><span class="sxs-lookup"><span data-stu-id="1c1f3-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c1f3-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c1f3-113">Requirements</span></span>  
 <span data-ttu-id="1c1f3-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c1f3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c1f3-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="1c1f3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c1f3-116">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1c1f3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c1f3-117">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c1f3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c1f3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c1f3-118">See Also</span></span>  
 [<span data-ttu-id="1c1f3-119">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="1c1f3-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="1c1f3-120">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="1c1f3-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="1c1f3-121">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="1c1f3-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="1c1f3-122">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="1c1f3-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="1c1f3-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="1c1f3-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
