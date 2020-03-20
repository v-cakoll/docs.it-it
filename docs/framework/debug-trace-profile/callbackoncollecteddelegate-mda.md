---
title: callbackOnCollectedDelegate (MDA)
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
ms.openlocfilehash: d4ca777fa5b41433eec227762fe315f22ab33cf6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174225"
---
# <a name="callbackoncollecteddelegate-mda"></a><span data-ttu-id="7f187-102">callbackOnCollectedDelegate (MDA)</span><span class="sxs-lookup"><span data-stu-id="7f187-102">callbackOnCollectedDelegate MDA</span></span>
<span data-ttu-id="7f187-103">L'Assistente al debug gestito (MDA) `callbackOnCollectedDelegate` viene attivato se viene effettuato il marshalling di un delegato da un codice gestito a un codice non gestito, ad esempio un puntatore a funzione, e se viene inserito un callback in tale puntatore dopo che il delegato è stato sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7f187-103">The `callbackOnCollectedDelegate` managed debugging assistant (MDA) is activated if a delegate is marshaled from managed to unmanaged code as a function pointer and a callback is placed on that function pointer after the delegate has been garbage collected.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="7f187-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="7f187-104">Symptoms</span></span>  
 <span data-ttu-id="7f187-105">Le violazioni di accesso si verificano durante il tentativo di chiamare codice gestito mediante puntatori a funzione ottenuti da delegati gestiti.</span><span class="sxs-lookup"><span data-stu-id="7f187-105">Access violations occur when attempting to call into managed code through function pointers that were obtained from managed delegates.</span></span> <span data-ttu-id="7f187-106">Questi errori possono sembrare bug di Common Language Runtime (CLR), anche se non lo sono, perché la violazione di accesso si verifica nel codice CLR.</span><span class="sxs-lookup"><span data-stu-id="7f187-106">These failures, while not common language runtime (CLR) bugs, may appear to be so because the access violation occurs in the CLR code.</span></span>  
  
 <span data-ttu-id="7f187-107">L'errore non è coerente. L’esito della chiamata sul puntatore a funzione è a volte positivo e a volte negativo.</span><span class="sxs-lookup"><span data-stu-id="7f187-107">The failure is not consistent; sometimes the call on the function pointer succeeds and sometimes it fails.</span></span> <span data-ttu-id="7f187-108">L'errore può verificarsi solo in situazioni di carico eccessivo o in un numero casuale di tentativi.</span><span class="sxs-lookup"><span data-stu-id="7f187-108">The failure might occur only under heavy load or on a random number of attempts.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="7f187-109">Causa</span><span class="sxs-lookup"><span data-stu-id="7f187-109">Cause</span></span>  
 <span data-ttu-id="7f187-110">Il delegato dal quale il puntatore a funzione è stato creato ed esposto al codice non gestito è stato sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7f187-110">The delegate from which the function pointer was created and exposed to unmanaged code was garbage collected.</span></span> <span data-ttu-id="7f187-111">Quando il componente non gestito tenta una chiamata sul puntatore a funzione, viene generata una violazione di accesso.</span><span class="sxs-lookup"><span data-stu-id="7f187-111">When the unmanaged component tries to call on the function pointer, it generates an access violation.</span></span>  
  
 <span data-ttu-id="7f187-112">L'errore viene visualizzato in modo casuale perché dipende da quando si verifica la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7f187-112">The failure appears random because it depends on when garbage collection occurs.</span></span> <span data-ttu-id="7f187-113">Se un delegato è idoneo per la raccolta, la Garbage Collection può verificarsi dopo il callback e la chiamata ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7f187-113">If a delegate is eligible for collection, the garbage collection can occur after the callback and the call succeeds.</span></span> <span data-ttu-id="7f187-114">In altri casi, le Garbage Collection vengono eseguite prima del callback, che genera una violazione di accesso e causa l’arresto del programma.</span><span class="sxs-lookup"><span data-stu-id="7f187-114">At other times, the garbage collection occurs before the callback, the callback generates an access violation, and the program stops.</span></span>  
  
 <span data-ttu-id="7f187-115">La probabilità di errore dipende dal tempo compreso tra il marshalling del delegato e il callback sul puntatore a funzione, nonché dalla frequenza delle Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7f187-115">The probability of the failure depends on the time between marshaling the delegate and the callback on the function pointer as well as the frequency of garbage collections.</span></span> <span data-ttu-id="7f187-116">L'errore si verifica raramente se il tempo compreso tra il marshalling del delegato e il callback è breve.</span><span class="sxs-lookup"><span data-stu-id="7f187-116">The failure is sporadic if the time between marshaling the delegate and the ensuing callback is short.</span></span> <span data-ttu-id="7f187-117">Spesso accade quando il metodo non gestito che riceve il puntatore a funzione non lo salva per un utilizzo futuro ma esegue subito il callback sul puntatore a funzione per completare l'operazione prima della restituzione.</span><span class="sxs-lookup"><span data-stu-id="7f187-117">This is usually the case if the unmanaged method receiving the function pointer does not save the function pointer for later use but instead calls back on the function pointer immediately to complete its operation before returning.</span></span> <span data-ttu-id="7f187-118">Analogamente, si verificano altre Garbage Collection quando un sistema è sottoposto a un carico eccessivo che rende più probabile che si verifichi una Garbage Collection prima del callback.</span><span class="sxs-lookup"><span data-stu-id="7f187-118">Similarly, more garbage collections occur when a system is under heavy load, which makes it more likely that a garbage collection will occur before the callback.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="7f187-119">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="7f187-119">Resolution</span></span>  
 <span data-ttu-id="7f187-120">Dopo il marshalling di un delegato come puntatore a funzione non gestito, il Garbage Collector non può più registrarne la durata.</span><span class="sxs-lookup"><span data-stu-id="7f187-120">Once a delegate has been marshaled out as an unmanaged function pointer, the garbage collector cannot track its lifetime.</span></span> <span data-ttu-id="7f187-121">È invece necessario che il codice mantenga un riferimento al delegato per la durata del puntatore a funzione non gestito.</span><span class="sxs-lookup"><span data-stu-id="7f187-121">Instead, your code must keep a reference to the delegate for the lifetime of the unmanaged function pointer.</span></span> <span data-ttu-id="7f187-122">Tuttavia, è necessario prima identificare quale delegato sia stato raccolto.</span><span class="sxs-lookup"><span data-stu-id="7f187-122">But before you can do that, you first must identify which delegate was collected.</span></span> <span data-ttu-id="7f187-123">Quando l'MDA è attivato, fornisce il nome del tipo del delegato.</span><span class="sxs-lookup"><span data-stu-id="7f187-123">When the MDA is activated, it provides the type name of the delegate.</span></span> <span data-ttu-id="7f187-124">Usare questo nome per cercare il codice per pInvoke o per le firme COM che passano il delegato al codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="7f187-124">Use this name to search your code for platform invoke or COM signatures that pass that delegate out to unmanaged code.</span></span> <span data-ttu-id="7f187-125">Il delegato interessato viene passato attraverso uno di questi siti di chiamata.</span><span class="sxs-lookup"><span data-stu-id="7f187-125">The offending delegate is passed out through one of these call sites.</span></span> <span data-ttu-id="7f187-126">È anche possibile abilitare l'MDA `gcUnmanagedToManaged` per imporre una Garbage Collection prima di ogni callback nel runtime.</span><span class="sxs-lookup"><span data-stu-id="7f187-126">You can also enable the `gcUnmanagedToManaged` MDA to force a garbage collection before every callback into the runtime.</span></span> <span data-ttu-id="7f187-127">Questa operazione rimuoverà le incertezze introdotte dalla Garbage Collection garantendone l'esecuzione sempre prima del callback.</span><span class="sxs-lookup"><span data-stu-id="7f187-127">This will remove the uncertainty introduced by the garbage collection by ensuring that a garbage collection always occurs before the callback.</span></span> <span data-ttu-id="7f187-128">Quando si è certi che il delegato sia stato raccolto, modificare il codice per mantenere un riferimento al delegato sul lato gestito per la durata del puntatore a funzione non gestito sottoposto a marshalling.</span><span class="sxs-lookup"><span data-stu-id="7f187-128">Once you know what delegate was collected, change your code to keep a reference to that delegate on the managed side for the lifetime of the marshaled unmanaged function pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7f187-129">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="7f187-129">Effect on the Runtime</span></span>  
 <span data-ttu-id="7f187-130">Quando viene eseguito il marshalling dei delegati come puntatori a funzione, il runtime alloca un thunk che effettua la transizione da non gestito a gestito.</span><span class="sxs-lookup"><span data-stu-id="7f187-130">When delegates are marshaled as function pointers, the runtime allocates a thunk that does the transition from unmanaged to managed.</span></span> <span data-ttu-id="7f187-131">Questo thunk è l'oggetto effettivamente chiamato dal codice non gestito prima di richiamare il delegato gestito.</span><span class="sxs-lookup"><span data-stu-id="7f187-131">This thunk is what the unmanaged code actually calls before the managed delegate is finally invoked.</span></span> <span data-ttu-id="7f187-132">Senza l'MDA `callbackOnCollectedDelegate` abilitato, il codice di marshalling non gestito viene eliminato quando il delegato viene raccolto.</span><span class="sxs-lookup"><span data-stu-id="7f187-132">Without the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is deleted when the delegate is collected.</span></span> <span data-ttu-id="7f187-133">Con l'MDA `callbackOnCollectedDelegate` abilitato, il codice di marshalling non gestito non viene eliminato immediatamente dopo aver raccolto il delegato.</span><span class="sxs-lookup"><span data-stu-id="7f187-133">With the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is not immediately deleted when the delegate is collected.</span></span> <span data-ttu-id="7f187-134">Per impostazione predefinita le ultime 1.000 istanze vengono invece conservate e modificate per attivare l'MDA quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="7f187-134">Instead, the last 1,000 instances are kept alive by default and changed to activate the MDA when called.</span></span> <span data-ttu-id="7f187-135">Il thunk viene infine eliminato dopo che vengono raccolti altri 1.001 delegati sottoposti a marshalling.</span><span class="sxs-lookup"><span data-stu-id="7f187-135">The thunk is eventually deleted after 1,001 more marshaled delegates are collected.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7f187-136">Output</span><span class="sxs-lookup"><span data-stu-id="7f187-136">Output</span></span>  
 <span data-ttu-id="7f187-137">L'MDA indica il nome del tipo del delegato raccolto prima di un tentativo di callback al relativo puntatore a funzione non gestito.</span><span class="sxs-lookup"><span data-stu-id="7f187-137">The MDA reports the type name of the delegate that was collected before a callback was attempted on its unmanaged function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7f187-138">Configurazione</span><span class="sxs-lookup"><span data-stu-id="7f187-138">Configuration</span></span>  
 <span data-ttu-id="7f187-139">L'esempio seguente mostra le opzioni di configurazione dell’applicazione.</span><span class="sxs-lookup"><span data-stu-id="7f187-139">The following example shows the application configuration options.</span></span> <span data-ttu-id="7f187-140">Imposta il numero di thunk mantenuto attivo dall'MDA su 1.500.</span><span class="sxs-lookup"><span data-stu-id="7f187-140">It sets the number of thunks the MDA keeps alive to 1,500.</span></span> <span data-ttu-id="7f187-141">Il valore predefinito `listSize` è 1.000, il valore minimo è 50 e il valore massimo è 2.000.</span><span class="sxs-lookup"><span data-stu-id="7f187-141">The default `listSize` value is 1,000, the minimum is 50, and the maximum is 2,000.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <callbackOnCollectedDelegate listSize="1500" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="7f187-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="7f187-142">Example</span></span>  
 <span data-ttu-id="7f187-143">L'esempio seguente illustra una situazione in cui è possibile attivare questo MDA:</span><span class="sxs-lookup"><span data-stu-id="7f187-143">The following example demonstrates a situation that can activate this MDA:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7f187-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f187-144">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="7f187-145">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="7f187-145">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7f187-146">Marshalling di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="7f187-146">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
- [<span data-ttu-id="7f187-147">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="7f187-147">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)
