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
ms.openlocfilehash: 30312e6e09535cee2968b1f9e8ac87b461c5ff40
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703514"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="fec5c-102">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="fec5c-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="fec5c-103">Fornisce metodi che consentono all'host di registrare e annullare la registrazione di callback per gli eventi di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="fec5c-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fec5c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="fec5c-104">Methods</span></span>  
  
|<span data-ttu-id="fec5c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="fec5c-105">Method</span></span>|<span data-ttu-id="fec5c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fec5c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fec5c-107">Metodo RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="fec5c-107">RegisterActionOnEvent Method</span></span>](iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="fec5c-108">Registra un puntatore di callback per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="fec5c-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="fec5c-109">Metodo UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="fec5c-109">UnregisterActionOnEvent Method</span></span>](iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="fec5c-110">Annulla la registrazione di un puntatore di callback registrato in precedenza per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="fec5c-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fec5c-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fec5c-111">Remarks</span></span>  
 <span data-ttu-id="fec5c-112">Per registrare e annullare la registrazione di callback di evento, l'host ottiene un riferimento a chiamando `ICLROnEventManager` il metodo [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fec5c-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fec5c-113">Gli eventi descritti da [EClrEvent](eclrevent-enumeration.md) possono essere generati più di una volta e da thread diversi per segnalare uno scaricamento o la disabilitazione del CLR.</span><span class="sxs-lookup"><span data-stu-id="fec5c-113">The events described by [EClrEvent](eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fec5c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fec5c-114">Requirements</span></span>  
 <span data-ttu-id="fec5c-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fec5c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fec5c-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fec5c-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fec5c-117">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fec5c-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fec5c-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fec5c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec5c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fec5c-119">See also</span></span>

- [<span data-ttu-id="fec5c-120">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="fec5c-120">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="fec5c-121">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="fec5c-121">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="fec5c-122">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="fec5c-122">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="fec5c-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="fec5c-123">Hosting Interfaces</span></span>](hosting-interfaces.md)
