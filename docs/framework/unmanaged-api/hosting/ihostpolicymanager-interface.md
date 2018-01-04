---
title: Interfaccia IHostPolicyManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager
helpviewer_keywords: IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0efbc0c51121156d112c63ba4ae59c6c9e95cd95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="4d3ed-102">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4d3ed-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="4d3ed-103">Fornisce metodi per notificare all'host le azioni eseguite da common language runtime (CLR) in caso di interruzioni, timeout o errori.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d3ed-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4d3ed-104">Methods</span></span>  
  
|<span data-ttu-id="4d3ed-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4d3ed-105">Method</span></span>|<span data-ttu-id="4d3ed-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4d3ed-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d3ed-107">Metodo OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="4d3ed-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="4d3ed-108">Notifica all'host che Common Language Runtime sta per eseguire l'azione predefinita specificata da una chiamata a [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in risposta a un thread di interruzione o <xref:System.AppDomain> scaricare.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="4d3ed-109">Metodo OnFailure</span><span class="sxs-lookup"><span data-stu-id="4d3ed-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="4d3ed-110">Notifica all'host che Common Language Runtime sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager:: SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in risposta a un errore di allocazione o il recupero di risorse.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="4d3ed-111">Metodo OnTimeout</span><span class="sxs-lookup"><span data-stu-id="4d3ed-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="4d3ed-112">Notifica all'host che Common Language Runtime sta per eseguire l'azione specificata da una chiamata a [ICLRPolicyManager::](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in risposta a un timeout.</span><span class="sxs-lookup"><span data-stu-id="4d3ed-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4d3ed-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d3ed-113">Requirements</span></span>  
 <span data-ttu-id="4d3ed-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d3ed-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d3ed-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="4d3ed-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d3ed-116">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4d3ed-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d3ed-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d3ed-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d3ed-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d3ed-118">See Also</span></span>  
 [<span data-ttu-id="4d3ed-119">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="4d3ed-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="4d3ed-120">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="4d3ed-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="4d3ed-121">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="4d3ed-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="4d3ed-122">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="4d3ed-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="4d3ed-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="4d3ed-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
