---
title: rientranza (MDA)
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged code, debugging
- transitioning threads unmanaged to managed code
- reentrancy MDA
- reentrancy without an orderly transition
- managed debugging assistants (MDAs), reentrancy
- illegal reentrancy
- MDAs (managed debugging assistants), reentrancy
- threading [.NET Framework], managed debugging assistants
- managed code, debugging
- native debugging, MDAs
ms.assetid: 7240c3f3-7df8-4b03-bbf1-17cdce142d45
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d14ba8724659172711da44e7bb249e9d20768dbc
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052330"
---
# <a name="reentrancy-mda"></a><span data-ttu-id="17aea-102">rientranza (MDA)</span><span class="sxs-lookup"><span data-stu-id="17aea-102">reentrancy MDA</span></span>
<span data-ttu-id="17aea-103">L'assistente al debug gestito `reentrancy` viene attivato quando viene effettuato un tentativo di transizione da codice nativo a codice gestito nei casi in cui un precedente passaggio da codice gestito a nativo non è stato eseguito mediante una transizione ordinata.</span><span class="sxs-lookup"><span data-stu-id="17aea-103">The `reentrancy` managed debugging assistant (MDA) is activated when an attempt is made to transition from native to managed code in cases where a prior switch from managed to native code was not performed through an orderly transition.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="17aea-104">Sintomi</span><span class="sxs-lookup"><span data-stu-id="17aea-104">Symptoms</span></span>  
 <span data-ttu-id="17aea-105">L'heap di oggetti è danneggiato o si stanno verificando altri errori gravi durante la transizione da codice nativo a codice gestito.</span><span class="sxs-lookup"><span data-stu-id="17aea-105">The object heap is corrupted or other serious errors are occurring when transitioning from native to managed code.</span></span>  
  
 <span data-ttu-id="17aea-106">I thread che passano da codice nativo a codice gestito e viceversa devono eseguire una transizione ordinata.</span><span class="sxs-lookup"><span data-stu-id="17aea-106">Threads that switch between native and managed code in either direction must perform an orderly transition.</span></span> <span data-ttu-id="17aea-107">Alcuni punti di estendibilità di basso livello nel sistema operativo, ad esempio il gestore di eccezioni con vettori, consentono tuttavia il passaggio da codice gestito a codice nativo senza eseguire una transizione ordinata.</span><span class="sxs-lookup"><span data-stu-id="17aea-107">However, certain low-level extensibility points in the operating system, such as the vectored exception handler, allow switches from managed to native code without performing an orderly transition.</span></span>  <span data-ttu-id="17aea-108">Questi passaggi avvengono sotto il controllo del sistema operativo, invece che di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="17aea-108">These switches are under operating system control, rather than under common language runtime (CLR) control.</span></span>  <span data-ttu-id="17aea-109">Il codice nativo eseguito in questi punti di estendibilità deve evitare il callback nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="17aea-109">Any native code that executes inside these extensibility points must avoid calling back into managed code.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="17aea-110">Causa</span><span class="sxs-lookup"><span data-stu-id="17aea-110">Cause</span></span>  
 <span data-ttu-id="17aea-111">Un punto di estendibilità di basso livello del sistema operativo, ad esempio il gestore di eccezioni con vettori, è stato attivato durante l'esecuzione di codice gestito.</span><span class="sxs-lookup"><span data-stu-id="17aea-111">A low-level operating system extensibility point, such as the vectored exception handler, has activated while executing managed code.</span></span>  <span data-ttu-id="17aea-112">Il codice dell'applicazione che viene richiamato tramite tale punto di estendibilità sta cercando di eseguire il callback nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="17aea-112">The application code that is invoked through that extensibility point is attempting to call back into managed code.</span></span>  
  
 <span data-ttu-id="17aea-113">Questo problema è sempre causato dal codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="17aea-113">This problem is always caused by application code.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="17aea-114">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="17aea-114">Resolution</span></span>  
 <span data-ttu-id="17aea-115">Esaminare l'analisi dello stack per il thread che ha attivato questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="17aea-115">Examine the stack trace for the thread that has activated this MDA.</span></span>  <span data-ttu-id="17aea-116">Il thread sta cercando di eseguire una chiamata non valida nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="17aea-116">The thread is attempting to illegally call into managed code.</span></span>  <span data-ttu-id="17aea-117">L'analisi dello stack indica il codice dell'applicazione che usa il punto di estendibilità, il codice del sistema operativo che fornisce il punto di estendibilità e il codice gestito interrotto dal punto di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="17aea-117">The stack trace should reveal the application code using this extensibility point, the operating system code that provides this extensibility point, and the managed code that was interrupted by the extensibility point.</span></span>  
  
 <span data-ttu-id="17aea-118">Si noterà, ad esempio, che l'assistente al debug gestito viene attivato in un tentativo di chiamare il codice gestito da un gestore di eccezioni con vettori.</span><span class="sxs-lookup"><span data-stu-id="17aea-118">For example, you will see the MDA activated in an attempt to call managed code from inside a vectored exception handler.</span></span>  <span data-ttu-id="17aea-119">Nello stack sarà possibile vedere il codice di gestione delle eccezioni del sistema operativo e il codice gestito che genera un'eccezione come <xref:System.DivideByZeroException> o <xref:System.AccessViolationException>.</span><span class="sxs-lookup"><span data-stu-id="17aea-119">On the stack you will see the operating system exception handling code and some managed code triggering an exception such as a <xref:System.DivideByZeroException> or an <xref:System.AccessViolationException>.</span></span>  
  
 <span data-ttu-id="17aea-120">In questo esempio la risoluzione corretta consiste nell'implementare il gestore di eccezioni con vettori completamente nel codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="17aea-120">In this example, the correct resolution is to implement the vectored exception handler completely in unmanaged code.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="17aea-121">Effetto sull'ambiente di esecuzione</span><span class="sxs-lookup"><span data-stu-id="17aea-121">Effect on the Runtime</span></span>  
 <span data-ttu-id="17aea-122">L'assistente al debug gestito non ha alcun effetto su CLR.</span><span class="sxs-lookup"><span data-stu-id="17aea-122">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="17aea-123">Output</span><span class="sxs-lookup"><span data-stu-id="17aea-123">Output</span></span>  
 <span data-ttu-id="17aea-124">L'assistente al debug gestito indica il tentativo di reentrancy non valida.</span><span class="sxs-lookup"><span data-stu-id="17aea-124">The MDA reports that illegal reentrancy is being attempted.</span></span>  <span data-ttu-id="17aea-125">Esaminare lo stack del thread per determinare il motivo per cui ciò si verifica e come risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="17aea-125">Examine the thread's stack to determine why this is happening and how to correct the problem.</span></span> <span data-ttu-id="17aea-126">Di seguito è riportato l'output di esempio.</span><span class="sxs-lookup"><span data-stu-id="17aea-126">The following is sample output.</span></span>  
  
```output
Additional Information: Attempting to call into managed code without   
transitioning out first.  Do not attempt to run managed code inside   
low-level native extensibility points. Managed Debugging Assistant   
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## <a name="configuration"></a><span data-ttu-id="17aea-127">Configurazione</span><span class="sxs-lookup"><span data-stu-id="17aea-127">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="17aea-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="17aea-128">Example</span></span>  
 <span data-ttu-id="17aea-129">Il codice seguente causa la generazione di un'eccezione <xref:System.AccessViolationException>.</span><span class="sxs-lookup"><span data-stu-id="17aea-129">The following code example causes an <xref:System.AccessViolationException> to be thrown.</span></span>  <span data-ttu-id="17aea-130">Nelle versioni di Windows che supportano la gestione delle eccezioni con vettori, ciò causa la chiamata del gestore di eccezioni con vettori gestito.</span><span class="sxs-lookup"><span data-stu-id="17aea-130">On versions of Windows that support vectored exception handling, this will cause the managed vectored exception handler to be called.</span></span>  <span data-ttu-id="17aea-131">Se l'assistente al debug gestito `reentrancy` è abilitato, verrà attivato durante il tentativo di chiamata a `MyHandler` dal codice di supporto di gestione delle eccezioni con vettori del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="17aea-131">If the `reentrancy` MDA is enabled, the MDA will activate during the attempted call to `MyHandler` from the operating system's vectored exception handling support code.</span></span>  
  
```csharp
using System;  
public delegate int ExceptionHandler(IntPtr ptrExceptionInfo);  
  
public class Reenter   
{  
    public static ExceptionHandler keepAlive;  
  
    [System.Runtime.InteropServices.DllImport("kernel32", ExactSpelling=true,   
        CharSet=System.Runtime.InteropServices.CharSet.Auto)]  
    public static extern IntPtr AddVectoredExceptionHandler(int bFirst,   
        ExceptionHandler handler);  
  
    static int MyHandler(IntPtr ptrExceptionInfo)   
    {  
        // EXCEPTION_CONTINUE_SEARCH  
        return 0;  
    }  
    void Run() {}  
  
    static void Main()   
    {  
        keepAlive = new ExceptionHandler(Reenter.MyHandler);  
        IntPtr ret = AddVectoredExceptionHandler(1, keepAlive);  
        try   
        {  
            // Dispatch on null should AV.  
            Reenter r = null;   
            r.Run();  
        }   
        catch { }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="17aea-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17aea-132">See also</span></span>

- [<span data-ttu-id="17aea-133">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="17aea-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
