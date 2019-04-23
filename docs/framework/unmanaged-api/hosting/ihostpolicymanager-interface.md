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
ms.openlocfilehash: cf9d903b4e44ea7a185ad8b3b71b7a5da2f2bda3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126347"
---
# <a name="ihostpolicymanager-interface"></a><span data-ttu-id="0ee38-102">Interfaccia IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="0ee38-102">IHostPolicyManager Interface</span></span>
<span data-ttu-id="0ee38-103">Fornisce metodi per notificare all'host le azioni eseguite da common language runtime (CLR) in caso di interruzioni, timeout o errori.</span><span class="sxs-lookup"><span data-stu-id="0ee38-103">Provides methods that notify the host of the actions the common language runtime (CLR) performs in case of aborts, timeouts, or failures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0ee38-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0ee38-104">Methods</span></span>  
  
|<span data-ttu-id="0ee38-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0ee38-105">Method</span></span>|<span data-ttu-id="0ee38-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0ee38-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0ee38-107">Metodo OnDefaultAction</span><span class="sxs-lookup"><span data-stu-id="0ee38-107">OnDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ondefaultaction-method.md)|<span data-ttu-id="0ee38-108">Notifica all'host che sta CLR per eseguire l'azione predefinita specificata da una chiamata a [SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in risposta a un thread di interruzione o <xref:System.AppDomain> unload.</span><span class="sxs-lookup"><span data-stu-id="0ee38-108">Notifies the host that the CLR is about to take the default action specified by a call to [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) in response to a thread abort or <xref:System.AppDomain> unload.</span></span>|  
|[<span data-ttu-id="0ee38-109">Metodo OnFailure</span><span class="sxs-lookup"><span data-stu-id="0ee38-109">OnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-onfailure-method.md)|<span data-ttu-id="0ee38-110">Notifica all'host che sta CLR per eseguire l'azione specificata da una chiamata a [SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in risposta a un errore di allocazione o recupero di risorse.</span><span class="sxs-lookup"><span data-stu-id="0ee38-110">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) in response to a resource allocation or reclamation failure.</span></span>|  
|[<span data-ttu-id="0ee38-111">Metodo OnTimeout</span><span class="sxs-lookup"><span data-stu-id="0ee38-111">OnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-ontimeout-method.md)|<span data-ttu-id="0ee38-112">Notifica all'host che sta CLR per eseguire l'azione specificata da una chiamata a [SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in risposta a un timeout.</span><span class="sxs-lookup"><span data-stu-id="0ee38-112">Notifies the host that the CLR is about to take the action specified by a call to [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) in response to a timeout.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0ee38-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ee38-113">Requirements</span></span>  
 <span data-ttu-id="0ee38-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ee38-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ee38-115">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ee38-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ee38-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0ee38-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ee38-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ee38-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ee38-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ee38-118">See also</span></span>

- [<span data-ttu-id="0ee38-119">Enumerazione EClrFailure</span><span class="sxs-lookup"><span data-stu-id="0ee38-119">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="0ee38-120">Enumerazione EClrOperation</span><span class="sxs-lookup"><span data-stu-id="0ee38-120">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="0ee38-121">Enumerazione EPolicyAction</span><span class="sxs-lookup"><span data-stu-id="0ee38-121">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="0ee38-122">Interfaccia ICLRPolicyManager</span><span class="sxs-lookup"><span data-stu-id="0ee38-122">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="0ee38-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="0ee38-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
