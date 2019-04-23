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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13d564be68d6b49a1616be97710312f33f828d48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176345"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="541ea-102">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="541ea-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="541ea-103">Descrive gli eventi di common language runtime (CLR) per il quale l'host può registrare i callback.</span><span class="sxs-lookup"><span data-stu-id="541ea-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="541ea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="541ea-104">Syntax</span></span>  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="541ea-105">Membri</span><span class="sxs-lookup"><span data-stu-id="541ea-105">Members</span></span>  
  
|<span data-ttu-id="541ea-106">Member</span><span class="sxs-lookup"><span data-stu-id="541ea-106">Member</span></span>|<span data-ttu-id="541ea-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="541ea-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="541ea-108">Specifica un errore irreversibile di CLR.</span><span class="sxs-lookup"><span data-stu-id="541ea-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="541ea-109">Specifica lo scaricamento di un particolare <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="541ea-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="541ea-110">Specifica che un messaggio al debug gestito Assistant (MDA) sia stato generato.</span><span class="sxs-lookup"><span data-stu-id="541ea-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="541ea-111">Specifica che si è verificato un errore di overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="541ea-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="541ea-112">Note</span><span class="sxs-lookup"><span data-stu-id="541ea-112">Remarks</span></span>  
 <span data-ttu-id="541ea-113">L'host può registrare i callback per uno qualsiasi dei tipi di eventi descritti da `EClrEvent` chiamando i metodi del [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="541ea-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="541ea-114">L'host ottiene un puntatore all'interfaccia chiamando il [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="541ea-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="541ea-115">Il `Event_CLRDisabled` e `Event_DomainUnload` eventi possono essere generati più di una volta e da thread diversi da segnalare uno scaricamento o la disattivazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="541ea-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="541ea-116">Il `Event_MDAFired` eventi genera la creazione di un' [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) istanza che contiene i dettagli del messaggio assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="541ea-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="541ea-117">Per altre informazioni sulle assistenti al debug gestito, vedere [diagnostica degli errori con assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="541ea-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="541ea-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="541ea-118">Requirements</span></span>  
 <span data-ttu-id="541ea-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="541ea-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="541ea-120">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="541ea-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="541ea-121">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="541ea-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="541ea-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="541ea-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="541ea-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="541ea-123">See also</span></span>

- [<span data-ttu-id="541ea-124">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="541ea-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="541ea-125">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="541ea-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="541ea-126">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="541ea-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
