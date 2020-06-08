---
title: Struttura MDAInfo
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
ms.openlocfilehash: 517e0ae7fb5d5151f94f82d9146ebbf40bad2ef9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503861"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="ebf13-102">Struttura MDAInfo</span><span class="sxs-lookup"><span data-stu-id="ebf13-102">MDAInfo Structure</span></span>
<span data-ttu-id="ebf13-103">Fornisce informazioni dettagliate sull' `Event_MDAFired` evento, che attiva la creazione di un assistente al debug gestito (MDA).</span><span class="sxs-lookup"><span data-stu-id="ebf13-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf13-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ebf13-104">Syntax</span></span>  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="ebf13-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ebf13-105">Members</span></span>  
  
|<span data-ttu-id="ebf13-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ebf13-106">Member</span></span>|<span data-ttu-id="ebf13-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ebf13-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="ebf13-108">Titolo dell'assistente al debug gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="ebf13-108">The title of the current MDA.</span></span> <span data-ttu-id="ebf13-109">Il titolo descrive il tipo di errore che ha attivato l' `Event_MDAFired` evento.</span><span class="sxs-lookup"><span data-stu-id="ebf13-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="ebf13-110">Messaggio di output fornito dall'assistente al debug gestito corrente.</span><span class="sxs-lookup"><span data-stu-id="ebf13-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebf13-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ebf13-111">Remarks</span></span>  
 <span data-ttu-id="ebf13-112">Gli assistenti al debug gestito (MDA) sono strumenti di debug che interagiscono con il Common Language Runtime (CLR) per eseguire attività quali l'identificazione di condizioni non valide nel motore di esecuzione di runtime o il dump di informazioni aggiuntive sullo stato del motore.</span><span class="sxs-lookup"><span data-stu-id="ebf13-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="ebf13-113">MDA generano messaggi XML sugli eventi altrimenti difficili da intercettare.</span><span class="sxs-lookup"><span data-stu-id="ebf13-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="ebf13-114">Sono particolarmente utili per il debug di transizioni tra codice gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="ebf13-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="ebf13-115">Il runtime esegue i passaggi seguenti quando viene attivato un evento che attiva la creazione di un assistente al debug gestito:</span><span class="sxs-lookup"><span data-stu-id="ebf13-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
- <span data-ttu-id="ebf13-116">Se l'host non ha registrato un'istanza di [IActionOnCLREvent](iactiononclrevent-interface.md) chiamando [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) per ricevere una notifica di un `Event_MDAFired` evento, il runtime procede con il comportamento predefinito non ospitato.</span><span class="sxs-lookup"><span data-stu-id="ebf13-116">If the host has not registered an [IActionOnCLREvent](iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
- <span data-ttu-id="ebf13-117">Se l'host ha registrato un gestore per questo evento, il runtime verifica se un debugger è collegato al processo.</span><span class="sxs-lookup"><span data-stu-id="ebf13-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="ebf13-118">In caso contrario, il runtime si interrompe nel debugger.</span><span class="sxs-lookup"><span data-stu-id="ebf13-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="ebf13-119">Quando il debugger continua, chiama nell'host.</span><span class="sxs-lookup"><span data-stu-id="ebf13-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="ebf13-120">Se non è stato collegato alcun debugger, il runtime chiama `IActionOnCLREvent::OnEvent` e passa un puntatore a un' `MDAInfo` istanza come `data` parametro.</span><span class="sxs-lookup"><span data-stu-id="ebf13-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="ebf13-121">L'host può scegliere di attivare MDA e di ricevere una notifica quando viene attivato un assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="ebf13-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="ebf13-122">Questo consente all'host di eseguire l'override del comportamento predefinito e di interrompere il thread gestito che ha generato l'evento, per impedire che danneggi lo stato del processo.</span><span class="sxs-lookup"><span data-stu-id="ebf13-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="ebf13-123">Per ulteriori informazioni sull'utilizzo di MDA, vedere la pagina relativa alla [diagnosi degli errori con gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="ebf13-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebf13-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ebf13-124">Requirements</span></span>  
 <span data-ttu-id="ebf13-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebf13-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebf13-126">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="ebf13-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="ebf13-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ebf13-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebf13-128">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebf13-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf13-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebf13-129">See also</span></span>

- [<span data-ttu-id="ebf13-130">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="ebf13-130">Hosting Structures</span></span>](hosting-structures.md)
- [<span data-ttu-id="ebf13-131">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="ebf13-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
