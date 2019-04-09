---
title: Interfaccia ICLRControl
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f70e7958cc9ac198738ed72732fe7b6563c89067
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175422"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="a7b0c-102">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="a7b0c-102">ICLRControl Interface</span></span>
<span data-ttu-id="a7b0c-103">Fornisce metodi che consentono a un host ottenere riferimenti a e configurarne, common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a7b0c-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7b0c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="a7b0c-104">Methods</span></span>  
  
|<span data-ttu-id="a7b0c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="a7b0c-105">Method</span></span>|<span data-ttu-id="a7b0c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7b0c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7b0c-107">Metodo GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="a7b0c-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="a7b0c-108">Ottiene un puntatore a interfaccia a un'istanza di uno qualsiasi dei tipi di gestione che di host può utilizzare per configurare il CLR.</span><span class="sxs-lookup"><span data-stu-id="a7b0c-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="a7b0c-109">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="a7b0c-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="a7b0c-110">Imposta un tipo derivato da <xref:System.AppDomainManager> come tipo per i gestori di dominio di applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7b0c-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7b0c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7b0c-111">Requirements</span></span>  
 <span data-ttu-id="a7b0c-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7b0c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7b0c-113">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7b0c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7b0c-114">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a7b0c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a7b0c-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a7b0c-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7b0c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7b0c-116">See also</span></span>

- [<span data-ttu-id="a7b0c-117">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="a7b0c-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="a7b0c-118">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="a7b0c-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="a7b0c-119">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="a7b0c-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="a7b0c-120">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a7b0c-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="a7b0c-121">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="a7b0c-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="a7b0c-122">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="a7b0c-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="a7b0c-123">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="a7b0c-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="a7b0c-124">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="a7b0c-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="a7b0c-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="a7b0c-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
