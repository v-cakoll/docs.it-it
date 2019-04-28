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
ms.openlocfilehash: 7486a094deab16ebbc05f19f1b652126479ce11c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638580"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="c8635-102">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="c8635-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="c8635-103">Fornisce metodi che consentono all'host registrare e annullare la registrazione dei callback per gli eventi di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c8635-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c8635-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c8635-104">Methods</span></span>  
  
|<span data-ttu-id="c8635-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c8635-105">Method</span></span>|<span data-ttu-id="c8635-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8635-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c8635-107">Metodo RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="c8635-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="c8635-108">Registra un puntatore di richiamata per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="c8635-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="c8635-109">Metodo UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="c8635-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="c8635-110">Annulla la registrazione di un puntatore di callback registrato in precedenza per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="c8635-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8635-111">Note</span><span class="sxs-lookup"><span data-stu-id="c8635-111">Remarks</span></span>  
 <span data-ttu-id="c8635-112">Per registrare e annullare la registrazione di callback degli eventi, l'host ottiene un riferimento al `ICLROnEventManager` chiamando il [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c8635-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8635-113">Gli eventi descritti da [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) possono essere generati più di una volta e da thread diversi da segnalare uno scaricamento o la disattivazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="c8635-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8635-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8635-114">Requirements</span></span>  
 <span data-ttu-id="c8635-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8635-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8635-116">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c8635-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c8635-117">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c8635-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8635-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8635-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8635-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8635-119">See also</span></span>

- [<span data-ttu-id="c8635-120">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="c8635-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="c8635-121">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="c8635-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="c8635-122">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="c8635-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c8635-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="c8635-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
