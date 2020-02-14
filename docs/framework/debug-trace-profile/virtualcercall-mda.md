---
title: virtualCERCall (MDA)
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- virtualCERCall MDA
- virtual CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
ms.openlocfilehash: 49ba4e7ca0b8ed2e433053130bc9ca2742c72ec9
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217199"
---
# <a name="virtualcercall-mda"></a><span data-ttu-id="352d1-102">virtualCERCall (MDA)</span><span class="sxs-lookup"><span data-stu-id="352d1-102">virtualCERCall MDA</span></span>
<span data-ttu-id="352d1-103">L'assistente al debug gestito `virtualCERCall` viene attivato come avviso che indica che un sito di chiamata all'interno di un grafico chiamate di un'area a esecuzione vincolata fa riferimento a una destinazione virtuale, ovvero una chiamata virtuale a un metodo virtuale non finale o a una chiamata che usa un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="352d1-103">The `virtualCERCall` managed debugging assistant (MDA) is activated as a warning indicating that a call site within a constrained execution region (CER) call graph refers to a virtual target, that is, a virtual call to a non-final virtual method or a call using an interface.</span></span> <span data-ttu-id="352d1-104">Common Language Runtime (CLR) non può prevedere il metodo di destinazione di queste chiamate solo dal linguaggio intermedio e dall'analisi dei metadati.</span><span class="sxs-lookup"><span data-stu-id="352d1-104">The common language runtime (CLR) cannot predict the destination method of these calls from the intermediate language and metadata analysis alone.</span></span> <span data-ttu-id="352d1-105">Di conseguenza, non è possibile preparare l'albero delle chiamate come parte del grafico dell'area a esecuzione vincolata e le interruzioni dei thread in tale sottoalbero non possono essere bloccate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="352d1-105">As a result, the call tree cannot be prepared as part of the CER graph and thread aborts in that subtree cannot be automatically blocked.</span></span> <span data-ttu-id="352d1-106">Questo assistente al debug gestito segnala i casi in cui un'area a esecuzione vincolata potrebbe dover essere estesa usando chiamate esplicite al metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> una volta che le informazioni aggiuntive necessarie per calcolare la destinazione della chiamata sono note in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="352d1-106">This MDA warns of cases where a CER might need to be extended by using explicit calls to the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> method once the additional information required to compute the call target is known at run time.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="352d1-107">Sintomi</span><span class="sxs-lookup"><span data-stu-id="352d1-107">Symptoms</span></span>  
 <span data-ttu-id="352d1-108">Le aree a esecuzione vincolata non vengono eseguite quando un thread viene interrotto o quando viene scaricato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="352d1-108">CERs that do not run when a thread is aborted or an application domain is unloaded.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="352d1-109">Causa</span><span class="sxs-lookup"><span data-stu-id="352d1-109">Cause</span></span>  
 <span data-ttu-id="352d1-110">Un'area a esecuzione vincolata contiene una chiamata a un metodo virtuale che non è possibile preparare automaticamente.</span><span class="sxs-lookup"><span data-stu-id="352d1-110">A CER contains a call to a virtual method that cannot be prepared automatically.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="352d1-111">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="352d1-111">Resolution</span></span>  
 <span data-ttu-id="352d1-112">Chiamare <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> per il metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="352d1-112">Call <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> for the virtual method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="352d1-113">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="352d1-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="352d1-114">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="352d1-114">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="352d1-115">Output</span><span class="sxs-lookup"><span data-stu-id="352d1-115">Output</span></span>  
  
```output
Method 'MethodWithCer', while executing within a constrained execution region, makes a call  
at IL offset 0x0024 to 'VirtualMethod', which is virtual and cannot be prepared automatically  
at compile time. The caller must ensure this method is prepared explicitly at  
runtime before entering the constrained execution region.  
method name="VirtualMethod"  
declaringType name="VirtualCERCall+MyClass"  
  declaringModule name="mda"  
    callsite name="MethodWithCer" offset="0x0024"  
```  
  
## <a name="configuration"></a><span data-ttu-id="352d1-116">Configurazione</span><span class="sxs-lookup"><span data-stu-id="352d1-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="352d1-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="352d1-117">Example</span></span>  
  
```csharp
class MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    virtual void VirtualMethod()  
    {  
        ...  
    }  
}  
  
class MyDerivedClass : MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    override void VirtualMethod()  
    {  
        ...  
    }  
}  
  
void MethodWithCer(MyClass object)  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    try  
    {  
        ...  
    }  
    finally  
    {  
        // Start of the CER.  
  
        // Cannot tell at analysis time whether object is a MyClass  
        // or a MyDerivedClass, so we do not know which version of   
        // VirtualMethod we are going to call.  
        object.VirtualMethod();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="352d1-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="352d1-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="352d1-119">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="352d1-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="352d1-120">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="352d1-120">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
