---
title: MDA contextSwitchDeadlock
ms.date: 03/30/2017
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdbad4a5eb9a9d0c81ae8d29394652e9f6df136e
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935858"
---
# <a name="contextswitchdeadlock-mda"></a><span data-ttu-id="c1edc-102">MDA contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="c1edc-102">contextSwitchDeadlock MDA</span></span>

<span data-ttu-id="c1edc-103">L'assistente al debug gestito `contextSwitchDeadlock` viene attivato quando viene rilevato un deadlock durante un tentativo di transizione del contesto COM.</span><span class="sxs-lookup"><span data-stu-id="c1edc-103">The `contextSwitchDeadlock` managed debugging assistant (MDA) is activated when a deadlock is detected during an attempted COM context transition.</span></span>

## <a name="symptoms"></a><span data-ttu-id="c1edc-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="c1edc-104">Symptoms</span></span>

<span data-ttu-id="c1edc-105">Il sintomo più comune è che una chiamata su un componente COM non gestito dal codice gestito non restituisce risultati.</span><span class="sxs-lookup"><span data-stu-id="c1edc-105">The most common symptom is that a call on an unmanaged COM component from managed code does not return.</span></span>  <span data-ttu-id="c1edc-106">Un altro sintomo è l'aumento dell'utilizzo della memoria nel tempo.</span><span class="sxs-lookup"><span data-stu-id="c1edc-106">Another symptom is memory usage increasing over time.</span></span>

## <a name="cause"></a><span data-ttu-id="c1edc-107">Causa</span><span class="sxs-lookup"><span data-stu-id="c1edc-107">Cause</span></span>

<span data-ttu-id="c1edc-108">La causa più probabile è che il thread di un apartment a thread singolo non stia distribuendo i messaggi.</span><span class="sxs-lookup"><span data-stu-id="c1edc-108">The most probable cause is that a single-threaded apartment (STA) thread is not pumping messages.</span></span> <span data-ttu-id="c1edc-109">Il thread dell'apartment a thread singolo potrebbe essere in attesa senza distribuire i messaggi o eseguire operazioni prolungate che non consentono la distribuzione della coda dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="c1edc-109">The STA thread is either waiting without pumping messages or is performing lengthy operations and is not allowing the message queue to pump.</span></span>

<span data-ttu-id="c1edc-110">L'aumento dell'utilizzo della memoria nel tempo è determinato dal thread finalizzatore che tenta di chiamare `Release` su un componente COM non gestito e che il componente non restituisca risultati.</span><span class="sxs-lookup"><span data-stu-id="c1edc-110">Memory usage increasing over time is caused by the finalizer thread attempting to call `Release` on an unmanaged COM component and that component is not returning.</span></span>  <span data-ttu-id="c1edc-111">Questo impedisce al finalizzatore di recuperare altri oggetti.</span><span class="sxs-lookup"><span data-stu-id="c1edc-111">This prevents the finalizer from reclaiming other objects.</span></span>

<span data-ttu-id="c1edc-112">Per impostazione predefinita, il modello di threading per il thread principale delle applicazioni console Visual Basic è l'apartment a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="c1edc-112">By default, the threading model for the main thread of Visual Basic console applications is STA.</span></span> <span data-ttu-id="c1edc-113">L'assistente al debug gestito viene attivato se un thread dell'apartment a thread singolo usa l'interoperabilità COM direttamente o indirettamente tramite Common Language Runtime o un controllo di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c1edc-113">This MDA is activated if an STA thread uses COM interoperability either directly or indirectly through the common language runtime or a third-party control.</span></span>  <span data-ttu-id="c1edc-114">Per evitare di attivare l'assistente al debug gestito in un'applicazione console Visual Basic, applicare l'attributo <xref:System.MTAThreadAttribute> al metodo principale o modificare l'applicazione affinché distribuisca i messaggi.</span><span class="sxs-lookup"><span data-stu-id="c1edc-114">To avoid activating this MDA in a Visual Basic console application, apply the <xref:System.MTAThreadAttribute> attribute to the main method or modify the application to pump messages.</span></span>

<span data-ttu-id="c1edc-115">È possibile che l'assistente al debug gestito venga attivato quando vengono soddisfatte tutte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1edc-115">It is possible for this MDA to be falsely activated when all of the following conditions are met:</span></span>

-   <span data-ttu-id="c1edc-116">Un'applicazione crea componenti COM da thread dell'apartment a thread singolo direttamente o indirettamente tramite le librerie.</span><span class="sxs-lookup"><span data-stu-id="c1edc-116">An application creates COM components from STA threads either directly or indirectly through libraries.</span></span>

-   <span data-ttu-id="c1edc-117">L'applicazione è stata interrotta nel debugger e l'utente ha continuato l'applicazione o eseguito un'operazione del passaggio.</span><span class="sxs-lookup"><span data-stu-id="c1edc-117">The application was stopped in the debugger and the user either continued the application or performed a step operation.</span></span>

-   <span data-ttu-id="c1edc-118">Il debug non gestito non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="c1edc-118">Unmanaged debugging is not enabled.</span></span>

<span data-ttu-id="c1edc-119">Per stabilire se l'assistente al debug gestito è stato falsamente abilitato, disabilitare tutti i punti di interruzione, riavviare l'applicazione e consentirne l'esecuzione senza interruzioni.</span><span class="sxs-lookup"><span data-stu-id="c1edc-119">To determine if the MDA is being falsely activated, disable all breakpoints, restart the application, and allow it to run without stopping.</span></span> <span data-ttu-id="c1edc-120">Se l'assistente al debug gestito non è attivata, è probabile che l'attivazione iniziale fosse falsa.</span><span class="sxs-lookup"><span data-stu-id="c1edc-120">If the MDA is not activated, it is likely the initial activation was false.</span></span> <span data-ttu-id="c1edc-121">In questo caso, disabilitare l'assistente al debug gestito per evitare interferenze con la sessione di debug.</span><span class="sxs-lookup"><span data-stu-id="c1edc-121">In this case, disable the MDA to avoid interference with the debugging session.</span></span>

> [!NOTE]
> <span data-ttu-id="c1edc-122">Questo assistente al debug gestito è il valore predefinito impostato per Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c1edc-122">This MDA is in the default set for Visual Studio.</span></span> <span data-ttu-id="c1edc-123">Per informazioni sulla disabilitazione di assistenti al debug gestito, vedere [diagnostica degli errori con assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span><span class="sxs-lookup"><span data-stu-id="c1edc-123">For information about how to disable MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span></span>

## <a name="resolution"></a><span data-ttu-id="c1edc-124">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="c1edc-124">Resolution</span></span>

<span data-ttu-id="c1edc-125">Seguire le regole COM relative alla distribuzione di messaggi di apartment a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="c1edc-125">Follow COM rules regarding STA message pumping.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="c1edc-126">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="c1edc-126">Effect on the Runtime</span></span>

<span data-ttu-id="c1edc-127">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="c1edc-127">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="c1edc-128">Fornisce solo dati sui contesti COM.</span><span class="sxs-lookup"><span data-stu-id="c1edc-128">It only reports data about COM contexts.</span></span>

## <a name="output"></a><span data-ttu-id="c1edc-129">Output</span><span class="sxs-lookup"><span data-stu-id="c1edc-129">Output</span></span>

<span data-ttu-id="c1edc-130">Messaggio che descrive il contesto corrente e il contesto di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c1edc-130">A message describing the current context and the target context.</span></span>

## <a name="configuration"></a><span data-ttu-id="c1edc-131">Configurazione</span><span class="sxs-lookup"><span data-stu-id="c1edc-131">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <contextSwitchDeadlock />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="c1edc-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1edc-132">See Also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="c1edc-133">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="c1edc-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="c1edc-134">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="c1edc-134">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
