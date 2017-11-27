---
title: Struttura MDAInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: MDAInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: MDAInfo
helpviewer_keywords: MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d303bcbee0b0c769fe2bc45663356b759fc91669
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mdainfo-structure"></a><span data-ttu-id="55e9d-102">Struttura MDAInfo</span><span class="sxs-lookup"><span data-stu-id="55e9d-102">MDAInfo Structure</span></span>
<span data-ttu-id="55e9d-103">Vengono fornite informazioni dettagliate sul `Event_MDAFired` evento, che genera la creazione di un assistente al debug gestito (MDA).</span><span class="sxs-lookup"><span data-stu-id="55e9d-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55e9d-104">Syntax</span></span>  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="55e9d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="55e9d-105">Members</span></span>  
  
|<span data-ttu-id="55e9d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="55e9d-106">Member</span></span>|<span data-ttu-id="55e9d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="55e9d-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="55e9d-108">Il titolo dell'Assistente al debug gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="55e9d-108">The title of the current MDA.</span></span> <span data-ttu-id="55e9d-109">Il titolo descrive il tipo di errore che ha generato il `Event_MDAFired` evento.</span><span class="sxs-lookup"><span data-stu-id="55e9d-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="55e9d-110">Il messaggio di output fornito dall'Assistente al debug gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="55e9d-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55e9d-111">Note</span><span class="sxs-lookup"><span data-stu-id="55e9d-111">Remarks</span></span>  
 <span data-ttu-id="55e9d-112">Esegue il debug che funzionano in combinazione con common language runtime (CLR) per eseguire attività quali l'identificazione delle condizioni non valide nel motore di esecuzione runtime o dump di informazioni aggiuntive sullo stato di assistenti al debug gestiti (MDA) il motore.</span><span class="sxs-lookup"><span data-stu-id="55e9d-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="55e9d-113">Assistenti al debug gestito genera messaggi XML su eventi che altrimenti sarebbero difficili da rilevare.</span><span class="sxs-lookup"><span data-stu-id="55e9d-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="55e9d-114">Sono particolarmente utili per il debug di transizioni tra codice gestito e gestito.</span><span class="sxs-lookup"><span data-stu-id="55e9d-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="55e9d-115">Quando viene generato un evento che attiva la creazione di un assistente al debug gestito, il runtime effettua le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="55e9d-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
-   <span data-ttu-id="55e9d-116">Se l'host non ha registrato un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) istanza chiamando [ICLROnEventManager::](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) per ricevere una notifica di un `Event_MDAFired` evento, il runtime continua con relativo Per impostazione predefinita, il comportamento non sia ospitato.</span><span class="sxs-lookup"><span data-stu-id="55e9d-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
-   <span data-ttu-id="55e9d-117">Se l'host ha registrato un gestore per questo evento, il runtime controlla per vedere se un debugger è collegato al processo.</span><span class="sxs-lookup"><span data-stu-id="55e9d-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="55e9d-118">Questo caso, il debugger si interrompe il runtime.</span><span class="sxs-lookup"><span data-stu-id="55e9d-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="55e9d-119">Quando il debugger continua, viene chiamato nell'host.</span><span class="sxs-lookup"><span data-stu-id="55e9d-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="55e9d-120">Se è connesso alcun debugger, il runtime chiama `IActionOnCLREvent::OnEvent` e passa un puntatore a un `MDAInfo` l'istanza come il `data` parametro.</span><span class="sxs-lookup"><span data-stu-id="55e9d-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="55e9d-121">L'host può scegliere di attivare assistenti al debug gestito e di ricevere una notifica quando viene attivato un assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="55e9d-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="55e9d-122">Ciò consente all'host la possibilità di ignorare il comportamento predefinito e di interrompere il thread gestito che ha generato l'evento, per evitare di danneggiare lo stato del processo.</span><span class="sxs-lookup"><span data-stu-id="55e9d-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="55e9d-123">Per ulteriori informazioni sull'utilizzo di assistenti al debug gestito, vedere [la diagnosi di errori con assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="55e9d-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e9d-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55e9d-124">Requirements</span></span>  
 <span data-ttu-id="55e9d-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55e9d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e9d-126">**Intestazione:** Mscoree</span><span class="sxs-lookup"><span data-stu-id="55e9d-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="55e9d-127">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55e9d-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55e9d-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55e9d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e9d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55e9d-129">See Also</span></span>  
 [<span data-ttu-id="55e9d-130">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="55e9d-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="55e9d-131">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="55e9d-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
