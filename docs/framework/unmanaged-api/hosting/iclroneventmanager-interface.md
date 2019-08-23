---
title: Interfaccia ICLROnEventManager
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3633db69877db771d919c9f43da4809f8321f77c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951193"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="04acd-102">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="04acd-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="04acd-103">Fornisce metodi che consentono all'host di registrare e annullare la registrazione di callback per gli eventi di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="04acd-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04acd-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="04acd-104">Methods</span></span>  
  
|<span data-ttu-id="04acd-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="04acd-105">Method</span></span>|<span data-ttu-id="04acd-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="04acd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04acd-107">Metodo RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="04acd-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="04acd-108">Registra un puntatore di callback per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="04acd-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="04acd-109">Metodo UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="04acd-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="04acd-110">Annulla la registrazione di un puntatore di callback registrato in precedenza per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="04acd-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04acd-111">Note</span><span class="sxs-lookup"><span data-stu-id="04acd-111">Remarks</span></span>  
 <span data-ttu-id="04acd-112">Per registrare e annullare la registrazione di callback di evento, l'host ottiene un `ICLROnEventManager` riferimento a chiamando il metodo [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="04acd-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04acd-113">Gli eventi descritti da [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) possono essere generati più di una volta e da thread diversi per segnalare uno scaricamento o la disabilitazione del CLR.</span><span class="sxs-lookup"><span data-stu-id="04acd-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04acd-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="04acd-114">Requirements</span></span>  
 <span data-ttu-id="04acd-115">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04acd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04acd-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04acd-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04acd-117">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04acd-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04acd-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04acd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04acd-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04acd-119">See also</span></span>

- [<span data-ttu-id="04acd-120">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="04acd-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="04acd-121">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="04acd-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="04acd-122">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="04acd-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="04acd-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="04acd-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
