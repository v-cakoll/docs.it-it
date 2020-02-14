---
title: openGenericCERCall (MDA)
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- open generic CER calls
- constrained execution regions
- openGenericCERCall MDA
- CER calls
- managed debugging assistants (MDAs), CER calls
- generics [.NET Framework], open generic CER calls
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
ms.openlocfilehash: de1735103314dfedbabe27623f579ce2c1e728af
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217274"
---
# <a name="opengenericcercall-mda"></a><span data-ttu-id="2b7e5-102">openGenericCERCall (MDA)</span><span class="sxs-lookup"><span data-stu-id="2b7e5-102">openGenericCERCall MDA</span></span>

<span data-ttu-id="2b7e5-103">L'assistente al debug gestito `openGenericCERCall` viene attivato per avvisare che il grafico dell'area a esecuzione vincolata con variabili di tipo generico in corrispondenza del metodo radice viene elaborato in fase di compilazione JIT o di generazione delle immagini native e almeno una delle variabili di tipo generico è un tipo riferimento oggetto.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-103">The `openGenericCERCall` managed debugging assistant is activated to warn that a constrained execution region (CER) graph with generic type variables at the root method is being processed at JIT-compilation or native image generation time and at least one of the generic type variables is an object reference type.</span></span>

## <a name="symptoms"></a><span data-ttu-id="2b7e5-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="2b7e5-104">Symptoms</span></span>

<span data-ttu-id="2b7e5-105">Il codice dell'area a esecuzione vincolata non viene eseguito quando un thread viene interrotto o quando viene scaricato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-105">CER code does not run when a thread is aborted or when an application domain is unloaded.</span></span>

## <a name="cause"></a><span data-ttu-id="2b7e5-106">Causa</span><span class="sxs-lookup"><span data-stu-id="2b7e5-106">Cause</span></span>

<span data-ttu-id="2b7e5-107">In fase di compilazione JIT, la creazione di un'istanza che contiene un tipo riferimento oggetto è rappresentativa solo perché il codice risultante è condiviso e ognuna delle variabili di tipo riferimento oggetto potrebbe essere qualsiasi tipo riferimento oggetto.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-107">At JIT-compilation time, an instantiation containing an object reference type is only representative because the resultant code is shared, and each of the object reference type variables might be any object reference type.</span></span> <span data-ttu-id="2b7e5-108">Ciò può impedire la preparazione anticipata di alcune risorse in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-108">This can prevent the preparation of some run-time resources ahead of time.</span></span>

<span data-ttu-id="2b7e5-109">In particolare, i metodi con variabili di tipo generico possono allocare risorse in background in modo differito.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-109">In particular, methods with generic type variables can lazily allocate resources in the background.</span></span> <span data-ttu-id="2b7e5-110">Queste sono note come voci di dizionario generiche.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-110">These are referred to as generic dictionary entries.</span></span> <span data-ttu-id="2b7e5-111">Ad esempio, per l'istruzione `List<T> list = new List<T>();` in cui `T` è una variabile di tipo generico, è necessario che il runtime cerchi la ricerca ed eventualmente crei la creazione di un'istanza esatta in fase di esecuzione, ad esempio `List<Object>, List<String>`e così via.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-111">For instance, for the statement `List<T> list = new List<T>();` where `T` is a generic type variable the runtime must look up and possibly create the exact instantiation at run time, for example, `List<Object>, List<String>`, and so forth.</span></span> <span data-ttu-id="2b7e5-112">Questa operazione può non riuscire per svariati motivi non sotto il controllo dello sviluppatore, ad esempio memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-112">This can fail for a variety of reasons beyond the developer's control, such as running out of memory.</span></span>

<span data-ttu-id="2b7e5-113">Questo assistente al debug gestito deve essere attivato solo in fase di compilazione JIT e non quando è prevista la creazione di un'istanza esatta.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-113">This MDA should only be activated at JIT-compilation time, not when there is an exact instantiation.</span></span>

<span data-ttu-id="2b7e5-114">Quando viene attivato questo assistente al debug gestito, i sintomi più probabili sono il mancato funzionamento delle aree a esecuzione vincolata per le creazioni di istanze non valide.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-114">When this MDA is activated, the likely symptoms are that CERs are not functional for the bad instantiations.</span></span> <span data-ttu-id="2b7e5-115">In effetti, il runtime non ha tentato di implementare un'area a esecuzione vincolata nelle circostanze che hanno causato l'attivazione dell'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-115">In fact, the runtime has not attempted to implement a CER under the circumstances that caused the MDA to be activated.</span></span> <span data-ttu-id="2b7e5-116">Pertanto, se lo sviluppatore usa la creazione d'istanza condivisa dell'area a esecuzione vincolata, gli errori di compilazione JIT, gli errori di caricamento di tipi generici o le interruzioni di thread all'interno dell'area a esecuzione vincolata prevista non vengono intercettati.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-116">So if the developer uses a shared instantiation of the CER, then JIT-compilation errors, generics type loading errors, or thread aborts within the region of the intended CER are not caught.</span></span>

## <a name="resolution"></a><span data-ttu-id="2b7e5-117">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="2b7e5-117">Resolution</span></span>

<span data-ttu-id="2b7e5-118">Non usare variabili di tipo generico che sono di tipo riferimento oggetto per i metodi che possono contenere un'area a esecuzione vincolata.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-118">Do not use generic type variables that are of object reference type for methods that may contain a CER.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="2b7e5-119">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="2b7e5-119">Effect on the Runtime</span></span>

<span data-ttu-id="2b7e5-120">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-120">This MDA has no effect on the CLR.</span></span>

## <a name="output"></a><span data-ttu-id="2b7e5-121">Output</span><span class="sxs-lookup"><span data-stu-id="2b7e5-121">Output</span></span>

<span data-ttu-id="2b7e5-122">Di seguito è riportato un esempio di output di questo assistente al debug gestito:</span><span class="sxs-lookup"><span data-stu-id="2b7e5-122">The following is a sample of output from this MDA:</span></span>
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution. 
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a><span data-ttu-id="2b7e5-123">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2b7e5-123">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a><span data-ttu-id="2b7e5-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="2b7e5-124">Example</span></span>

<span data-ttu-id="2b7e5-125">Il codice dell'area a esecuzione vincolata non viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="2b7e5-125">The CER code is not executed.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Runtime.CompilerServices;

class Program
{
    static void Main(string[] args)
    {
        CallGenericMethods();
    }
    static void CallGenericMethods()
    {
        // This call is correct. The instantiation of the method
        // contains only nonreference types.
        MyClass.GenericMethodWithCer<int>();

        // This call is incorrect. A shared version of the method that
        // cannot be completely analyzed will be JIT-compiled. The 
        // MDA will be activated at JIT-compile time, not at run time.
        MyClass.GenericMethodWithCer<String>();
    }
}

class MyClass
{
    public static void GenericMethodWithCer<T>()
    {
        RuntimeHelpers.PrepareConstrainedRegions();
        try
        {

        }
        finally
        {
            // This is the start of the CER.
            Console.WriteLine("In finally block.");
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="2b7e5-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b7e5-126">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [<span data-ttu-id="2b7e5-127">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="2b7e5-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
