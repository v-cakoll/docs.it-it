---
title: Interfaccia ICLRControl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b93d87107e1a69b0a047dbf156124fe49cd95d16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="12ad4-102">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="12ad4-102">ICLRControl Interface</span></span>
<span data-ttu-id="12ad4-103">Fornisce metodi che consentono a un host ottenere riferimenti a e configurare gli aspetti, common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="12ad4-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12ad4-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="12ad4-104">Methods</span></span>  
  
|<span data-ttu-id="12ad4-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="12ad4-105">Method</span></span>|<span data-ttu-id="12ad4-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12ad4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12ad4-107">Metodo GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="12ad4-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="12ad4-108">Ottiene un puntatore a interfaccia a un'istanza di uno dei tipi di gestione, che l'host può utilizzare per configurare CLR.</span><span class="sxs-lookup"><span data-stu-id="12ad4-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="12ad4-109">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="12ad4-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="12ad4-110">Imposta un tipo derivato da <xref:System.AppDomainManager> come tipo di gestione dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="12ad4-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12ad4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12ad4-111">Requirements</span></span>  
 <span data-ttu-id="12ad4-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12ad4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12ad4-113">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="12ad4-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12ad4-114">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12ad4-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12ad4-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12ad4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12ad4-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12ad4-116">See Also</span></span>  
 [<span data-ttu-id="12ad4-117">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="12ad4-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="12ad4-118">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="12ad4-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="12ad4-119">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="12ad4-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="12ad4-120">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="12ad4-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="12ad4-121">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="12ad4-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="12ad4-122">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="12ad4-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="12ad4-123">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="12ad4-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="12ad4-124">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="12ad4-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="12ad4-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="12ad4-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
