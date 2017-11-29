---
title: Enumerazione EClrEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EClrEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: EClrEvent
helpviewer_keywords: EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0585cea00865f4798c57ef5276076c2b0a5ff284
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="7d287-102">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="7d287-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="7d287-103">Descrive gli eventi di common language runtime (CLR) per il quale l'host può registrare callback.</span><span class="sxs-lookup"><span data-stu-id="7d287-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d287-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d287-104">Syntax</span></span>  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="7d287-105">Membri</span><span class="sxs-lookup"><span data-stu-id="7d287-105">Members</span></span>  
  
|<span data-ttu-id="7d287-106">Membro</span><span class="sxs-lookup"><span data-stu-id="7d287-106">Member</span></span>|<span data-ttu-id="7d287-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d287-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="7d287-108">Specifica un errore irreversibile di CLR.</span><span class="sxs-lookup"><span data-stu-id="7d287-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="7d287-109">Specifica lo scaricamento di un particolare <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="7d287-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="7d287-110">Specifica che è stato generato un messaggio gestiti (Assistente al debug).</span><span class="sxs-lookup"><span data-stu-id="7d287-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="7d287-111">Specifica che si è verificato un errore di overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="7d287-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d287-112">Note</span><span class="sxs-lookup"><span data-stu-id="7d287-112">Remarks</span></span>  
 <span data-ttu-id="7d287-113">L'host può registrare i callback per uno qualsiasi dei tipi di evento descritti da `EClrEvent` chiamando i metodi del [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="7d287-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="7d287-114">L'host ottiene un puntatore all'interfaccia tramite la chiamata di [ICLRControl::](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="7d287-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="7d287-115">Il `Event_CLRDisabled` e `Event_DomainUnload` eventi possono essere generati più volte da thread diversi per segnalare uno scaricamento o la disattivazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="7d287-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="7d287-116">Il `Event_MDAFired` evento genera la creazione di un [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) istanza che contiene i dettagli del messaggio MDA.</span><span class="sxs-lookup"><span data-stu-id="7d287-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="7d287-117">Per ulteriori informazioni su MDA, vedere [la diagnosi di errori con assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="7d287-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d287-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7d287-118">Requirements</span></span>  
 <span data-ttu-id="7d287-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d287-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d287-120">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7d287-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7d287-121">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d287-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d287-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d287-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d287-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d287-123">See Also</span></span>  
 [<span data-ttu-id="7d287-124">IActionOnCLREvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7d287-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="7d287-125">ICLRControl (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="7d287-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="7d287-126">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="7d287-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
