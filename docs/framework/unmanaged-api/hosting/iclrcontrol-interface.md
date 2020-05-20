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
ms.openlocfilehash: 54748fdeaf911591c21f4495335e54c777878f04
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615839"
---
# <a name="iclrcontrol-interface"></a><span data-ttu-id="c844e-102">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="c844e-102">ICLRControl Interface</span></span>
<span data-ttu-id="c844e-103">Fornisce metodi che consentono a un host di ottenere riferimenti e configurare aspetti di, il Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c844e-103">Provides methods that allow a host to get references to, and configure aspects of, the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c844e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c844e-104">Methods</span></span>  
  
|<span data-ttu-id="c844e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c844e-105">Method</span></span>|<span data-ttu-id="c844e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c844e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c844e-107">Metodo GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="c844e-107">GetCLRManager Method</span></span>](iclrcontrol-getclrmanager-method.md)|<span data-ttu-id="c844e-108">Ottiene un puntatore a interfaccia a un'istanza di uno dei tipi di gestione che l'host può utilizzare per configurare CLR.</span><span class="sxs-lookup"><span data-stu-id="c844e-108">Gets an interface pointer to an instance of any of the manager types the host can use to configure the CLR.</span></span>|  
|[<span data-ttu-id="c844e-109">Metodo SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="c844e-109">SetAppDomainManagerType Method</span></span>](iclrcontrol-setappdomainmanagertype-method.md)|<span data-ttu-id="c844e-110">Imposta un tipo derivato da <xref:System.AppDomainManager> come tipo per i gestori del dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c844e-110">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c844e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c844e-111">Requirements</span></span>  
 <span data-ttu-id="c844e-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c844e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c844e-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c844e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c844e-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c844e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c844e-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c844e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c844e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c844e-116">See also</span></span>

- [<span data-ttu-id="c844e-117">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="c844e-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c844e-118">Interfaccia ICLRDebugManager</span><span class="sxs-lookup"><span data-stu-id="c844e-118">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="c844e-119">Interfaccia ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="c844e-119">ICLRGCManager Interface</span></span>](iclrgcmanager-interface.md)
- [<span data-ttu-id="c844e-120">Interfaccia ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c844e-120">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
- [<span data-ttu-id="c844e-121">Interfaccia ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="c844e-121">ICLRHostProtectionManager Interface</span></span>](iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="c844e-122">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="c844e-122">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="c844e-123">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="c844e-123">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="c844e-124">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="c844e-124">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="c844e-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="c844e-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
