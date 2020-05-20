---
title: Enumerazione EClrEvent
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
ms.openlocfilehash: 388f0de26983f8bb876f40a527f60d8bc59191a3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616349"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="8de1f-102">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="8de1f-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="8de1f-103">Vengono descritti gli eventi di Common Language Runtime (CLR) per i quali l'host può registrare i callback.</span><span class="sxs-lookup"><span data-stu-id="8de1f-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de1f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8de1f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="8de1f-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8de1f-105">Members</span></span>  
  
|<span data-ttu-id="8de1f-106">Membro</span><span class="sxs-lookup"><span data-stu-id="8de1f-106">Member</span></span>|<span data-ttu-id="8de1f-107">Description</span><span class="sxs-lookup"><span data-stu-id="8de1f-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="8de1f-108">Specifica un errore CLR irreversibile.</span><span class="sxs-lookup"><span data-stu-id="8de1f-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="8de1f-109">Specifica lo scaricamento di un particolare <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="8de1f-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="8de1f-110">Specifica che è stato generato un messaggio assistente al debug gestito (MDA).</span><span class="sxs-lookup"><span data-stu-id="8de1f-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="8de1f-111">Specifica che si è verificato un errore di overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="8de1f-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8de1f-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8de1f-112">Remarks</span></span>  
 <span data-ttu-id="8de1f-113">L'host può registrare callback per qualsiasi tipo di evento descritto da `EClrEvent` chiamando i metodi dell'interfaccia [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="8de1f-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="8de1f-114">L'host ottiene un puntatore a questa interfaccia chiamando il metodo [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8de1f-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="8de1f-115">Gli `Event_CLRDisabled` `Event_DomainUnload` eventi e possono essere generati più di una volta e da thread diversi per segnalare uno scaricamento o la disabilitazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="8de1f-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="8de1f-116">L' `Event_MDAFired` evento genera la creazione di un'istanza di [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) che contiene i dettagli del messaggio dell'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8de1f-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="8de1f-117">Per ulteriori informazioni su MDA, vedere la pagina relativa alla [diagnosi degli errori con gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="8de1f-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8de1f-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8de1f-118">Requirements</span></span>  
 <span data-ttu-id="8de1f-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8de1f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8de1f-120">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8de1f-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8de1f-121">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8de1f-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8de1f-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8de1f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de1f-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8de1f-123">See also</span></span>

- [<span data-ttu-id="8de1f-124">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="8de1f-124">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="8de1f-125">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="8de1f-125">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="8de1f-126">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="8de1f-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
