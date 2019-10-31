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
ms.openlocfilehash: 914a2f6103fb0ffb9a7b9fcb895ecf0cd62f3c43
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126599"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="3ed9d-102">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="3ed9d-102">ICLRControl Interface</span></span>
<span data-ttu-id="3ed9d-103">Fornisce metodi che consentono a un host di ottenere riferimenti e configurare aspetti di, il Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3ed9d-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ed9d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3ed9d-104">Methods</span></span>  
  
|<span data-ttu-id="3ed9d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3ed9d-105">Method</span></span>|<span data-ttu-id="3ed9d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3ed9d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ed9d-107">Metodo GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="3ed9d-107">GetCLRManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="3ed9d-108">Ottiene un puntatore a interfaccia a un'istanza di uno dei tipi di gestione che l'host può utilizzare per configurare CLR.</span><span class="sxs-lookup"><span data-stu-id="3ed9d-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="3ed9d-109">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="3ed9d-109">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="3ed9d-110">Imposta un tipo derivato da <xref:System.AppDomainManager> come tipo per i gestori del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ed9d-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ed9d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ed9d-111">Requirements</span></span>  
 <span data-ttu-id="3ed9d-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ed9d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ed9d-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3ed9d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ed9d-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3ed9d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ed9d-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ed9d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ed9d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ed9d-116">See also</span></span>

- [<span data-ttu-id="3ed9d-117">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="3ed9d-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="3ed9d-118">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="3ed9d-118">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="3ed9d-119">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="3ed9d-119">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="3ed9d-120">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="3ed9d-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="3ed9d-121">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="3ed9d-121">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="3ed9d-122">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="3ed9d-122">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="3ed9d-123">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="3ed9d-123">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="3ed9d-124">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="3ed9d-124">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="3ed9d-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="3ed9d-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
