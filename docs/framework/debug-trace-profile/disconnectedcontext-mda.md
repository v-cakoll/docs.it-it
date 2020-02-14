---
title: MDA disconnectedContext
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
ms.openlocfilehash: 3d04e304a6b30fe6fd4deeda5a97007f11ee7b13
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216540"
---
# <a name="disconnectedcontext-mda"></a><span data-ttu-id="c31ce-102">MDA disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="c31ce-102">disconnectedContext MDA</span></span>
<span data-ttu-id="c31ce-103">L'assistente al debug gestito `disconnectedContext` è attivato quando CLR tenta la transizione a un apartment o contesto disconnesso durante la gestione di una richiesta relativa a un oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="c31ce-103">The `disconnectedContext` managed debugging assistant (MDA) is activated when the CLR attempts to transition into a disconnected apartment or context while servicing a request concerning a COM object.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="c31ce-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="c31ce-104">Symptoms</span></span>  
 <span data-ttu-id="c31ce-105">Le chiamate effettuate a un [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) sono recapitate al componente COM sottostante nell'apartment o contesto corrente invece che a quello in cui si trovano.</span><span class="sxs-lookup"><span data-stu-id="c31ce-105">Calls made on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) are delivered to the underlying COM component in the current apartment or context instead of the one in which they exist.</span></span> <span data-ttu-id="c31ce-106">Ciò può provocare il danneggiamento o la perdita di dati, se il componente COM non è a thread multipli, ad esempio nel caso di componenti di tipo apartment a thread singolo.</span><span class="sxs-lookup"><span data-stu-id="c31ce-106">This can cause corruption and or data loss if the COM component is not multithreaded, as in the case of single-threaded apartment (STA) components.</span></span> <span data-ttu-id="c31ce-107">In alternativa, se l'oggetto RCW stesso è un proxy, la chiamata potrebbe provocare la generazione di un'eccezione <xref:System.Runtime.InteropServices.COMException> con HRESULT di tipo RPC_E_WRONG_THREAD.</span><span class="sxs-lookup"><span data-stu-id="c31ce-107">Alternatively, if the RCW is itself a proxy, the call might result in the throwing of a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="c31ce-108">Causa</span><span class="sxs-lookup"><span data-stu-id="c31ce-108">Cause</span></span>  
 <span data-ttu-id="c31ce-109">L'apartment o contesto OLE è stato arrestato quando CLR ha tentato di eseguirvi la transizione.</span><span class="sxs-lookup"><span data-stu-id="c31ce-109">The OLE apartment or context has been shut down when the CLR attempts to transition into it.</span></span> <span data-ttu-id="c31ce-110">Nella maggior parte dei casi, ciò è dovuto dall'arresto di apartment STA prima del rilascio completo di tutti i componenti COM di proprietà dell'apartment. Questo può essere il risultato di una chiamata esplicita da codice utente a un oggetto RCW oppure può verificarsi quando CLR sta modificando il componente COM, ad esempio quando CLR rilascia il componente COM dopo che l'oggetto RCW associato è stato sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c31ce-110">This is most commonly caused by STA apartments being shut down before all the COM components owned by the apartment were completely released This can occur as a result of an explicit call from user code on an RCW or while the CLR itself is manipulating the COM component, for example when the CLR is releasing the COM component when the associated RCW has been garbage collected.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="c31ce-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="c31ce-111">Resolution</span></span>  
 <span data-ttu-id="c31ce-112">Per evitare questo problema, assicurarsi che il thread proprietario dell'apartment STA non termini prima che l'applicazione abbia completato le operazioni relative a tutti gli oggetti presenti nell'apartment.</span><span class="sxs-lookup"><span data-stu-id="c31ce-112">To avoid this problem, ensure the thread that owns the STA does not terminate before the application has finished with all the objects that live in the apartment.</span></span> <span data-ttu-id="c31ce-113">Anche nel caso dei contesti, è necessario assicurarsi che non siano arrestati prima che l'applicazione abbia completato le operazioni relative a tutti i componenti COM presenti nel contesto.</span><span class="sxs-lookup"><span data-stu-id="c31ce-113">The same applies to contexts; ensure contexts are not shut down before the application is completely finished with any COM components that live inside the context.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="c31ce-114">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="c31ce-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="c31ce-115">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="c31ce-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="c31ce-116">Fornisce solo dati sul contesto disconnesso.</span><span class="sxs-lookup"><span data-stu-id="c31ce-116">It only reports data about the disconnected context.</span></span>  
  
## <a name="output"></a><span data-ttu-id="c31ce-117">Output</span><span class="sxs-lookup"><span data-stu-id="c31ce-117">Output</span></span>  
 <span data-ttu-id="c31ce-118">Fornisce il cookie del contesto dell'apartment o del contesto disconnesso.</span><span class="sxs-lookup"><span data-stu-id="c31ce-118">Reports the context cookie of the disconnected apartment or context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="c31ce-119">Configurazione</span><span class="sxs-lookup"><span data-stu-id="c31ce-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c31ce-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c31ce-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="c31ce-121">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="c31ce-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="c31ce-122">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="c31ce-122">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
