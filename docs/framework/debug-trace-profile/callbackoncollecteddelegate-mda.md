---
title: callbackOnCollectedDelegate (MDA)
description: Esaminare l'assistente al debug gestito di callbackOnCollectedDelegate in .NET, che viene richiamato se si verifica un callback dopo che il delegato è stato sottoposta a Garbage Collection.
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- managed debugging assistants (MDAs), callback on collected delegates
- MDAs (managed debugging assistants), callback on collected delegates
- callback on delegate after garbage collection
- callbackOnCollectedDelegate MDA
- managed debugging assistants (MDAs), garbage collection
- call back collected delegates
- garbage collection, run-time errors
- delegates [.NET Framework], garbage collection
ms.assetid: 398b0ce0-5cc9-4518-978d-b8263aa21e5b
ms.openlocfilehash: 32f02a4e65455f11f3bfa9260caae8b4e48f494e
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416031"
---
# <a name="callbackoncollecteddelegate-mda"></a><span data-ttu-id="1bb83-103">callbackOnCollectedDelegate (MDA)</span><span class="sxs-lookup"><span data-stu-id="1bb83-103">callbackOnCollectedDelegate MDA</span></span>
<span data-ttu-id="1bb83-104">L'Assistente al debug gestito (MDA) `callbackOnCollectedDelegate` viene attivato se viene effettuato il marshalling di un delegato da un codice gestito a un codice non gestito, ad esempio un puntatore a funzione, e se viene inserito un callback in tale puntatore dopo che il delegato è stato sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1bb83-104">The `callbackOnCollectedDelegate` managed debugging assistant (MDA) is activated if a delegate is marshaled from managed to unmanaged code as a function pointer and a callback is placed on that function pointer after the delegate has been garbage collected.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="1bb83-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="1bb83-105">Symptoms</span></span>  
 <span data-ttu-id="1bb83-106">Le violazioni di accesso si verificano durante il tentativo di chiamare codice gestito mediante puntatori a funzione ottenuti da delegati gestiti.</span><span class="sxs-lookup"><span data-stu-id="1bb83-106">Access violations occur when attempting to call into managed code through function pointers that were obtained from managed delegates.</span></span> <span data-ttu-id="1bb83-107">Questi errori possono sembrare bug di Common Language Runtime (CLR), anche se non lo sono, perché la violazione di accesso si verifica nel codice CLR.</span><span class="sxs-lookup"><span data-stu-id="1bb83-107">These failures, while not common language runtime (CLR) bugs, may appear to be so because the access violation occurs in the CLR code.</span></span>  
  
 <span data-ttu-id="1bb83-108">L'errore non è coerente. L’esito della chiamata sul puntatore a funzione è a volte positivo e a volte negativo.</span><span class="sxs-lookup"><span data-stu-id="1bb83-108">The failure is not consistent; sometimes the call on the function pointer succeeds and sometimes it fails.</span></span> <span data-ttu-id="1bb83-109">L'errore può verificarsi solo in situazioni di carico eccessivo o in un numero casuale di tentativi.</span><span class="sxs-lookup"><span data-stu-id="1bb83-109">The failure might occur only under heavy load or on a random number of attempts.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="1bb83-110">Causa</span><span class="sxs-lookup"><span data-stu-id="1bb83-110">Cause</span></span>  
 <span data-ttu-id="1bb83-111">Il delegato dal quale il puntatore a funzione è stato creato ed esposto al codice non gestito è stato sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1bb83-111">The delegate from which the function pointer was created and exposed to unmanaged code was garbage collected.</span></span> <span data-ttu-id="1bb83-112">Quando il componente non gestito tenta una chiamata sul puntatore a funzione, viene generata una violazione di accesso.</span><span class="sxs-lookup"><span data-stu-id="1bb83-112">When the unmanaged component tries to call on the function pointer, it generates an access violation.</span></span>  
  
 <span data-ttu-id="1bb83-113">L'errore viene visualizzato in modo casuale perché dipende da quando si verifica la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1bb83-113">The failure appears random because it depends on when garbage collection occurs.</span></span> <span data-ttu-id="1bb83-114">Se un delegato è idoneo per la raccolta, la Garbage Collection può verificarsi dopo il callback e la chiamata ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="1bb83-114">If a delegate is eligible for collection, the garbage collection can occur after the callback and the call succeeds.</span></span> <span data-ttu-id="1bb83-115">In altri casi, le Garbage Collection vengono eseguite prima del callback, che genera una violazione di accesso e causa l’arresto del programma.</span><span class="sxs-lookup"><span data-stu-id="1bb83-115">At other times, the garbage collection occurs before the callback, the callback generates an access violation, and the program stops.</span></span>  
  
 <span data-ttu-id="1bb83-116">La probabilità di errore dipende dal tempo compreso tra il marshalling del delegato e il callback sul puntatore a funzione, nonché dalla frequenza delle Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1bb83-116">The probability of the failure depends on the time between marshaling the delegate and the callback on the function pointer as well as the frequency of garbage collections.</span></span> <span data-ttu-id="1bb83-117">L'errore si verifica raramente se il tempo compreso tra il marshalling del delegato e il callback è breve.</span><span class="sxs-lookup"><span data-stu-id="1bb83-117">The failure is sporadic if the time between marshaling the delegate and the ensuing callback is short.</span></span> <span data-ttu-id="1bb83-118">Spesso accade quando il metodo non gestito che riceve il puntatore a funzione non lo salva per un utilizzo futuro ma esegue subito il callback sul puntatore a funzione per completare l'operazione prima della restituzione.</span><span class="sxs-lookup"><span data-stu-id="1bb83-118">This is usually the case if the unmanaged method receiving the function pointer does not save the function pointer for later use but instead calls back on the function pointer immediately to complete its operation before returning.</span></span> <span data-ttu-id="1bb83-119">Analogamente, si verificano altre Garbage Collection quando un sistema è sottoposto a un carico eccessivo che rende più probabile che si verifichi una Garbage Collection prima del callback.</span><span class="sxs-lookup"><span data-stu-id="1bb83-119">Similarly, more garbage collections occur when a system is under heavy load, which makes it more likely that a garbage collection will occur before the callback.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="1bb83-120">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="1bb83-120">Resolution</span></span>  
 <span data-ttu-id="1bb83-121">Dopo il marshalling di un delegato come puntatore a funzione non gestito, il Garbage Collector non può più registrarne la durata.</span><span class="sxs-lookup"><span data-stu-id="1bb83-121">Once a delegate has been marshaled out as an unmanaged function pointer, the garbage collector cannot track its lifetime.</span></span> <span data-ttu-id="1bb83-122">È invece necessario che il codice mantenga un riferimento al delegato per la durata del puntatore a funzione non gestito.</span><span class="sxs-lookup"><span data-stu-id="1bb83-122">Instead, your code must keep a reference to the delegate for the lifetime of the unmanaged function pointer.</span></span> <span data-ttu-id="1bb83-123">Tuttavia, è necessario prima identificare quale delegato sia stato raccolto.</span><span class="sxs-lookup"><span data-stu-id="1bb83-123">But before you can do that, you first must identify which delegate was collected.</span></span> <span data-ttu-id="1bb83-124">Quando l'MDA è attivato, fornisce il nome del tipo del delegato.</span><span class="sxs-lookup"><span data-stu-id="1bb83-124">When the MDA is activated, it provides the type name of the delegate.</span></span> <span data-ttu-id="1bb83-125">Usare questo nome per cercare il codice per pInvoke o per le firme COM che passano il delegato al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="1bb83-125">Use this name to search your code for platform invoke or COM signatures that pass that delegate out to unmanaged code.</span></span> <span data-ttu-id="1bb83-126">Il delegato interessato viene passato attraverso uno di questi siti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1bb83-126">The offending delegate is passed out through one of these call sites.</span></span> <span data-ttu-id="1bb83-127">È anche possibile abilitare l'MDA `gcUnmanagedToManaged` per imporre una Garbage Collection prima di ogni callback nel runtime.</span><span class="sxs-lookup"><span data-stu-id="1bb83-127">You can also enable the `gcUnmanagedToManaged` MDA to force a garbage collection before every callback into the runtime.</span></span> <span data-ttu-id="1bb83-128">Questa operazione rimuoverà le incertezze introdotte dalla Garbage Collection garantendone l'esecuzione sempre prima del callback.</span><span class="sxs-lookup"><span data-stu-id="1bb83-128">This will remove the uncertainty introduced by the garbage collection by ensuring that a garbage collection always occurs before the callback.</span></span> <span data-ttu-id="1bb83-129">Quando si è certi che il delegato sia stato raccolto, modificare il codice per mantenere un riferimento al delegato sul lato gestito per la durata del puntatore a funzione non gestito sottoposto a marshalling.</span><span class="sxs-lookup"><span data-stu-id="1bb83-129">Once you know what delegate was collected, change your code to keep a reference to that delegate on the managed side for the lifetime of the marshaled unmanaged function pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="1bb83-130">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="1bb83-130">Effect on the Runtime</span></span>  
 <span data-ttu-id="1bb83-131">Quando viene eseguito il marshalling dei delegati come puntatori a funzione, il runtime alloca un thunk che effettua la transizione da non gestito a gestito.</span><span class="sxs-lookup"><span data-stu-id="1bb83-131">When delegates are marshaled as function pointers, the runtime allocates a thunk that does the transition from unmanaged to managed.</span></span> <span data-ttu-id="1bb83-132">Questo thunk è l'oggetto effettivamente chiamato dal codice non gestito prima di richiamare il delegato gestito.</span><span class="sxs-lookup"><span data-stu-id="1bb83-132">This thunk is what the unmanaged code actually calls before the managed delegate is finally invoked.</span></span> <span data-ttu-id="1bb83-133">Senza l'MDA `callbackOnCollectedDelegate` abilitato, il codice di marshalling non gestito viene eliminato quando il delegato viene raccolto.</span><span class="sxs-lookup"><span data-stu-id="1bb83-133">Without the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is deleted when the delegate is collected.</span></span> <span data-ttu-id="1bb83-134">Con l'MDA `callbackOnCollectedDelegate` abilitato, il codice di marshalling non gestito non viene eliminato immediatamente dopo aver raccolto il delegato.</span><span class="sxs-lookup"><span data-stu-id="1bb83-134">With the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is not immediately deleted when the delegate is collected.</span></span> <span data-ttu-id="1bb83-135">Per impostazione predefinita le ultime 1.000 istanze vengono invece conservate e modificate per attivare l'MDA quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="1bb83-135">Instead, the last 1,000 instances are kept alive by default and changed to activate the MDA when called.</span></span> <span data-ttu-id="1bb83-136">Il thunk viene infine eliminato dopo che vengono raccolti altri 1.001 delegati sottoposti a marshalling.</span><span class="sxs-lookup"><span data-stu-id="1bb83-136">The thunk is eventually deleted after 1,001 more marshaled delegates are collected.</span></span>  
  
## <a name="output"></a><span data-ttu-id="1bb83-137">Output</span><span class="sxs-lookup"><span data-stu-id="1bb83-137">Output</span></span>  
 <span data-ttu-id="1bb83-138">L'MDA indica il nome del tipo del delegato raccolto prima di un tentativo di callback al relativo puntatore a funzione non gestito.</span><span class="sxs-lookup"><span data-stu-id="1bb83-138">The MDA reports the type name of the delegate that was collected before a callback was attempted on its unmanaged function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="1bb83-139">Configurazione</span><span class="sxs-lookup"><span data-stu-id="1bb83-139">Configuration</span></span>  
 <span data-ttu-id="1bb83-140">L'esempio seguente mostra le opzioni di configurazione dell’applicazione.</span><span class="sxs-lookup"><span data-stu-id="1bb83-140">The following example shows the application configuration options.</span></span> <span data-ttu-id="1bb83-141">Imposta il numero di thunk mantenuto attivo dall'MDA su 1.500.</span><span class="sxs-lookup"><span data-stu-id="1bb83-141">It sets the number of thunks the MDA keeps alive to 1,500.</span></span> <span data-ttu-id="1bb83-142">Il valore predefinito `listSize` è 1.000, il valore minimo è 50 e il valore massimo è 2.000.</span><span class="sxs-lookup"><span data-stu-id="1bb83-142">The default `listSize` value is 1,000, the minimum is 50, and the maximum is 2,000.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <callbackOnCollectedDelegate listSize="1500" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="1bb83-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bb83-143">Example</span></span>  
 <span data-ttu-id="1bb83-144">L'esempio seguente illustra una situazione in cui è possibile attivare questo MDA:</span><span class="sxs-lookup"><span data-stu-id="1bb83-144">The following example demonstrates a situation that can activate this MDA:</span></span>  
  
```cpp
// Library.cpp : Defines the unmanaged entry point for the DLL application.  
#include "windows.h"  
#include "stdio.h"  
  
void (__stdcall *g_pfTarget)();  
  
void __stdcall Initialize(void __stdcall pfTarget())  
{  
    g_pfTarget = pfTarget;  
}  
  
void __stdcall Callback()  
{  
    g_pfTarget();  
}
```

```csharp
// C# Client  
using System;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public delegate void DCallback();  
  
    public static void Main()  
    {  
        new Entry();  
        Initialize(Target);  
        GC.Collect();  
        GC.WaitForPendingFinalizers();  
        Callback();  
    }  
  
    public static void Target()  
    {
    }  
  
    [DllImport("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Initialize(DCallback pfDelegate);  
  
    [DllImport ("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Callback();  
  
    ~Entry() { Console.Error.WriteLine("Entry Collected"); }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bb83-145">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1bb83-145">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="1bb83-146">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="1bb83-146">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="1bb83-147">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="1bb83-147">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
- [<span data-ttu-id="1bb83-148">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="1bb83-148">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)
