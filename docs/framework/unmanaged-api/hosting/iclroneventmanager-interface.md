---
title: Interfaccia ICLROnEventManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLROnEventManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLROnEventManager
helpviewer_keywords: ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02a19a3daf72cdfa493b09fa984fe7b50865ed30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="73514-102">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="73514-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="73514-103">Fornisce metodi che consentono all'host registrare e annullare la registrazione di callback per gli eventi di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="73514-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73514-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="73514-104">Methods</span></span>  
  
|<span data-ttu-id="73514-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="73514-105">Method</span></span>|<span data-ttu-id="73514-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73514-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73514-107">Metodo RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="73514-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="73514-108">Registra un puntatore di callback per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="73514-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="73514-109">Metodo UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="73514-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="73514-110">Annulla la registrazione di un puntatore di callback registrato in precedenza per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="73514-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73514-111">Note</span><span class="sxs-lookup"><span data-stu-id="73514-111">Remarks</span></span>  
 <span data-ttu-id="73514-112">Per registrare e annullare la registrazione del callback di evento, l'host ottiene un riferimento a `ICLROnEventManager` chiamando il [ICLRControl::](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="73514-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73514-113">Gli eventi descritti da [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) possono essere generati più volte da thread diversi per segnalare uno scaricamento o la disattivazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="73514-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73514-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73514-114">Requirements</span></span>  
 <span data-ttu-id="73514-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73514-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73514-116">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="73514-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73514-117">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="73514-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73514-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73514-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73514-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73514-119">See Also</span></span>  
 [<span data-ttu-id="73514-120">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="73514-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="73514-121">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="73514-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="73514-122">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="73514-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="73514-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="73514-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
