---
title: MDA illegalPrepareConstrainedRegion
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23a36d1709f03583ce39af0e7c80bb1ecd7cf809
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158977"
---
# <a name="illegalprepareconstrainedregion-mda"></a><span data-ttu-id="3f49b-102">MDA illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="3f49b-102">illegalPrepareConstrainedRegion MDA</span></span>
<span data-ttu-id="3f49b-103">L'assistente al debug gestito `illegalPrepareConstrainedRegion` viene attivato quando una chiamata al metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> non precede immediatamente l'istruzione `try` del gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="3f49b-103">The `illegalPrepareConstrainedRegion` managed debugging assistant (MDA) is activated when a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> method call does not immediately precede the `try` statement of the exception handler.</span></span> <span data-ttu-id="3f49b-104">Poiché questa restrizione è a livello MSIL, è consentita la presenza di un'origine che non genera codice tra la chiamata e l'istruzione `try`, ad esempio commenti.</span><span class="sxs-lookup"><span data-stu-id="3f49b-104">This restriction is at the MSIL level, so it is permissible to have non-code-generating source between the call and the `try`, such as comments.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="3f49b-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="3f49b-105">Symptoms</span></span>  
 <span data-ttu-id="3f49b-106">Area a esecuzione vincolata che non viene mai considerata come tale, ma come semplice blocco di gestione delle eccezioni (`finally` o `catch`).</span><span class="sxs-lookup"><span data-stu-id="3f49b-106">A constrained execution region (CER) that is never treated as such, but as a simple exception handling block (`finally` or `catch`).</span></span> <span data-ttu-id="3f49b-107">Di conseguenza, l'area non viene eseguita nel caso di una condizione di memoria insufficiente o di interruzione del thread.</span><span class="sxs-lookup"><span data-stu-id="3f49b-107">As a consequence, the region does not run in the event of an out-of-memory condition or a thread abort.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="3f49b-108">Causa</span><span class="sxs-lookup"><span data-stu-id="3f49b-108">Cause</span></span>  
 <span data-ttu-id="3f49b-109">Il modello di preparazione per un'area a esecuzione vincolata non è stato applicato correttamente.</span><span class="sxs-lookup"><span data-stu-id="3f49b-109">The preparation pattern for a CER is not followed correctly.</span></span>  <span data-ttu-id="3f49b-110">Si tratta di un evento di errore.</span><span class="sxs-lookup"><span data-stu-id="3f49b-110">This is an error event.</span></span> <span data-ttu-id="3f49b-111">Il <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> chiamata al metodo usato per contrassegnare i gestori di eccezioni come introduzione a un'area a esecuzione vincolata in loro `catch` / `finally` / `fault` / `filter` blocchi devono essere usati immediatamente prima di `try` istruzione.</span><span class="sxs-lookup"><span data-stu-id="3f49b-111">The <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method call used to mark exception handlers as introducing a CER in their `catch`/`finally`/`fault`/`filter` blocks must be used immediately before the `try` statement.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="3f49b-112">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="3f49b-112">Resolution</span></span>  
 <span data-ttu-id="3f49b-113">Assicurarsi che la chiamata a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> avvenga immediatamente prima dell'istruzione `try`.</span><span class="sxs-lookup"><span data-stu-id="3f49b-113">Ensure that the call to <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> happens immediately before the `try` statement.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3f49b-114">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="3f49b-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="3f49b-115">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="3f49b-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3f49b-116">Output</span><span class="sxs-lookup"><span data-stu-id="3f49b-116">Output</span></span>  
 <span data-ttu-id="3f49b-117">L'assistente al debug gestito visualizza il nome del metodo che chiama il metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, l'offset MSIL e un messaggio indicante che la chiamata non precede immediatamente l'inizio del blocco try.</span><span class="sxs-lookup"><span data-stu-id="3f49b-117">The MDA displays the name of the method calling the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> method, the MSIL offset, and a message indicating the call does not immediately precede the beginning of the try block.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3f49b-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="3f49b-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="3f49b-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f49b-119">Example</span></span>  
 <span data-ttu-id="3f49b-120">Il codice di esempio seguente mostra il modello che causa l'attivazione di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="3f49b-120">The following code example demonstrates the pattern that causes this MDA to be activated.</span></span>  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f49b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f49b-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [<span data-ttu-id="3f49b-122">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="3f49b-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3f49b-123">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="3f49b-123">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
