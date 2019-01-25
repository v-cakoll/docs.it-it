---
title: Interfaccia IActionOnCLREvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f547d1bafa37c2cbb285a5d55cef8e1a6e29d0a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688246"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="63f64-102">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="63f64-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="63f64-103">Fornisce il [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) metodo, che esegue i callback degli eventi che sono state registrate con una chiamata ai [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="63f64-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63f64-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="63f64-104">Methods</span></span>  
  
|<span data-ttu-id="63f64-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="63f64-105">Method</span></span>|<span data-ttu-id="63f64-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63f64-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63f64-107">Metodo OnEvent</span><span class="sxs-lookup"><span data-stu-id="63f64-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="63f64-108">Esegue un callback per un evento registrato.</span><span class="sxs-lookup"><span data-stu-id="63f64-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63f64-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63f64-109">Requirements</span></span>  
 <span data-ttu-id="63f64-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63f64-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63f64-111">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="63f64-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="63f64-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="63f64-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63f64-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63f64-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f64-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63f64-114">See also</span></span>
- [<span data-ttu-id="63f64-115">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="63f64-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="63f64-116">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="63f64-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="63f64-117">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="63f64-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="63f64-118">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="63f64-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
