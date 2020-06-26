---
title: MDA disconnectedContext
description: Esaminare l'assistente al debug gestito di disconnectedContext in .NET, che viene richiamato quando CLR tenta di eseguire la transizione a un apartment o a un contesto disconnesso.
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
ms.openlocfilehash: 0b24aadefab7a7cb2a5294f25e674d188beec814
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416083"
---
# <a name="disconnectedcontext-mda"></a><span data-ttu-id="10296-103">MDA disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="10296-103">disconnectedContext MDA</span></span>
<span data-ttu-id="10296-104">L'assistente al debug gestito `disconnectedContext` è attivato quando CLR tenta la transizione a un apartment o contesto disconnesso durante la gestione di una richiesta relativa a un oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="10296-104">The `disconnectedContext` managed debugging assistant (MDA) is activated when the CLR attempts to transition into a disconnected apartment or context while servicing a request concerning a COM object.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="10296-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="10296-105">Symptoms</span></span>  
 <span data-ttu-id="10296-106">Le chiamate effettuate a un [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) sono recapitate al componente COM sottostante nell'apartment o contesto corrente invece che a quello in cui si trovano.</span><span class="sxs-lookup"><span data-stu-id="10296-106">Calls made on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) are delivered to the underlying COM component in the current apartment or context instead of the one in which they exist.</span></span> <span data-ttu-id="10296-107">Ciò può provocare il danneggiamento o la perdita di dati, se il componente COM non è a thread multipli, ad esempio nel caso di componenti di tipo apartment a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="10296-107">This can cause corruption and or data loss if the COM component is not multithreaded, as in the case of single-threaded apartment (STA) components.</span></span> <span data-ttu-id="10296-108">In alternativa, se l'oggetto RCW stesso è un proxy, la chiamata potrebbe provocare la generazione di un'eccezione <xref:System.Runtime.InteropServices.COMException> con HRESULT di tipo RPC_E_WRONG_THREAD.</span><span class="sxs-lookup"><span data-stu-id="10296-108">Alternatively, if the RCW is itself a proxy, the call might result in the throwing of a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="10296-109">Causa</span><span class="sxs-lookup"><span data-stu-id="10296-109">Cause</span></span>  
 <span data-ttu-id="10296-110">L'apartment o contesto OLE è stato arrestato quando CLR ha tentato di eseguirvi la transizione.</span><span class="sxs-lookup"><span data-stu-id="10296-110">The OLE apartment or context has been shut down when the CLR attempts to transition into it.</span></span> <span data-ttu-id="10296-111">Nella maggior parte dei casi, ciò è dovuto dall'arresto di apartment STA prima del rilascio completo di tutti i componenti COM di proprietà dell'apartment. Questo può essere il risultato di una chiamata esplicita da codice utente a un oggetto RCW oppure può verificarsi quando CLR sta modificando il componente COM, ad esempio quando CLR rilascia il componente COM dopo che l'oggetto RCW associato è stato sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="10296-111">This is most commonly caused by STA apartments being shut down before all the COM components owned by the apartment were completely released This can occur as a result of an explicit call from user code on an RCW or while the CLR itself is manipulating the COM component, for example when the CLR is releasing the COM component when the associated RCW has been garbage collected.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="10296-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="10296-112">Resolution</span></span>  
 <span data-ttu-id="10296-113">Per evitare questo problema, assicurarsi che il thread proprietario dell'apartment STA non termini prima che l'applicazione abbia completato le operazioni relative a tutti gli oggetti presenti nell'apartment.</span><span class="sxs-lookup"><span data-stu-id="10296-113">To avoid this problem, ensure the thread that owns the STA does not terminate before the application has finished with all the objects that live in the apartment.</span></span> <span data-ttu-id="10296-114">Anche nel caso dei contesti, è necessario assicurarsi che non siano arrestati prima che l'applicazione abbia completato le operazioni relative a tutti i componenti COM presenti nel contesto.</span><span class="sxs-lookup"><span data-stu-id="10296-114">The same applies to contexts; ensure contexts are not shut down before the application is completely finished with any COM components that live inside the context.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="10296-115">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="10296-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="10296-116">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="10296-116">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="10296-117">Fornisce solo dati sul contesto disconnesso.</span><span class="sxs-lookup"><span data-stu-id="10296-117">It only reports data about the disconnected context.</span></span>  
  
## <a name="output"></a><span data-ttu-id="10296-118">Output</span><span class="sxs-lookup"><span data-stu-id="10296-118">Output</span></span>  
 <span data-ttu-id="10296-119">Fornisce il cookie del contesto dell'apartment o del contesto disconnesso.</span><span class="sxs-lookup"><span data-stu-id="10296-119">Reports the context cookie of the disconnected apartment or context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="10296-120">Configurazione</span><span class="sxs-lookup"><span data-stu-id="10296-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10296-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="10296-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="10296-122">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="10296-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="10296-123">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="10296-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
