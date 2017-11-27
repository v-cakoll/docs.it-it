---
title: Interfaccia ICLRControl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRControl
helpviewer_keywords: ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 98b41ea0062534d9e990a7fe366e8f746ae87f38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="7bfae-102">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="7bfae-102">ICLRControl Interface</span></span>
<span data-ttu-id="7bfae-103">Fornisce metodi che consentono a un host ottenere riferimenti a e configurare gli aspetti, common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="7bfae-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7bfae-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="7bfae-104">Methods</span></span>  
  
|<span data-ttu-id="7bfae-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="7bfae-105">Method</span></span>|<span data-ttu-id="7bfae-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7bfae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7bfae-107">GetCLRManager (metodo)</span><span class="sxs-lookup"><span data-stu-id="7bfae-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="7bfae-108">Ottiene un puntatore a interfaccia a un'istanza di uno dei tipi di gestione, che l'host può utilizzare per configurare CLR.</span><span class="sxs-lookup"><span data-stu-id="7bfae-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="7bfae-109">SetAppDomainManagerType (metodo)</span><span class="sxs-lookup"><span data-stu-id="7bfae-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="7bfae-110">Imposta un tipo derivato da <xref:System.AppDomainManager> come tipo di gestione dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="7bfae-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7bfae-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7bfae-111">Requirements</span></span>  
 <span data-ttu-id="7bfae-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bfae-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bfae-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7bfae-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7bfae-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7bfae-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7bfae-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bfae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bfae-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bfae-116">See Also</span></span>  
 [<span data-ttu-id="7bfae-117">ICLRAssemblyIdentityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7bfae-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="7bfae-118">ICLRDebugManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7bfae-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="7bfae-119">ICLRGCManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7bfae-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="7bfae-120">ICLRHostBindingPolicyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7bfae-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="7bfae-121">ICLRHostProtectionManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7bfae-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="7bfae-122">ICLROnEventManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7bfae-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="7bfae-123">ICLRPolicyManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7bfae-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="7bfae-124">IHostControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7bfae-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="7bfae-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="7bfae-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
