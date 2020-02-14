---
title: Protezione della gestione delle eccezioni
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
ms.openlocfilehash: e0465f2eb6be61e161f5e6b8cadf629a53f11906
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215793"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="c6dfe-102">Protezione della gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="c6dfe-102">Securing Exception Handling</span></span>
<span data-ttu-id="c6dfe-103">In Visual C++ e Visual Basic, un'espressione di filtro più avanti lo stack viene eseguita prima di qualsiasi istruzione **finally** .</span><span class="sxs-lookup"><span data-stu-id="c6dfe-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="c6dfe-104">Il blocco **catch** associato a tale filtro viene eseguito dopo l'istruzione **finally** .</span><span class="sxs-lookup"><span data-stu-id="c6dfe-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="c6dfe-105">Per ulteriori informazioni, vedere [utilizzo di eccezioni filtrate dall'utente](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="c6dfe-105">For more information, see [Using User-Filtered Exceptions](../../standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="c6dfe-106">In questa sezione vengono esaminate le implicazioni di sicurezza di questo ordine.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="c6dfe-107">Si consideri l'esempio di pseudocodice seguente che illustra l'ordine in cui vengono eseguite le istruzioni di filtro e le istruzioni **finally** .</span><span class="sxs-lookup"><span data-stu-id="c6dfe-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
```cpp  
void Main()   
{  
    try   
    {  
        Sub();  
    }   
    except (Filter())   
    {  
        Console.WriteLine("catch");  
    }  
}  
bool Filter () {  
    Console.WriteLine("filter");  
    return true;  
}  
void Sub()   
{  
    try   
    {  
        Console.WriteLine("throw");  
        throw new Exception();  
    }   
    finally   
    {  
        Console.WriteLine("finally");  
    }  
}                        
```  
  
 <span data-ttu-id="c6dfe-108">Questo codice stampa quanto segue.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-108">This code prints the following.</span></span>  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="c6dfe-109">Il filtro viene eseguito prima dell'istruzione **finally** , quindi i problemi di sicurezza possono essere introdotti da qualsiasi elemento che apporta una modifica dello stato in cui l'esecuzione di altro codice potrebbe trarre vantaggio.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="c6dfe-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c6dfe-110">For example:</span></span>  
  
```cpp  
try   
{  
    Alter_Security_State();  
    // This means changing anything (state variables,  
    // switching unmanaged context, impersonation, and   
    // so on) that could be exploited if malicious   
    // code ran before state is restored.  
    Do_some_work();  
}   
finally   
{  
    Restore_Security_State();  
    // This simply restores the state change above.  
}  
```  
  
 <span data-ttu-id="c6dfe-111">Questo pseudocodice consente a un filtro di ottenere un livello superiore dello stack per eseguire codice arbitrario.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="c6dfe-112">Altri esempi di operazioni che hanno un effetto simile sono la rappresentazione temporanea di un'altra identità, l'impostazione di un flag interno che ignora un controllo di sicurezza o la modifica delle impostazioni cultura associate al thread.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="c6dfe-113">La soluzione consigliata consiste nell'introdurre un gestore di eccezioni per isolare le modifiche del codice nello stato del thread dai blocchi di filtro dei chiamanti.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="c6dfe-114">Tuttavia, è importante che il gestore di eccezioni venga introdotto correttamente o che il problema non venga risolto.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="c6dfe-115">Nell'esempio seguente vengono modificate le impostazioni cultura dell'interfaccia utente, ma qualsiasi tipo di modifica dello stato del thread potrebbe essere esposto in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
   CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
   try {  
      Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
      // Do something that throws an exception.  
}  
   finally {  
      Thread.CurrentThread.CurrentUICulture = saveCulture;  
   }  
}  
```  
  
```vb  
Public Class UserCode  
   Public Shared Sub Main()  
      Try  
         Dim obj As YourObject = new YourObject  
         obj.YourMethod()  
      Catch e As Exception When FilterFunc  
         Console.WriteLine("An error occurred: '{0}'", e)  
         Console.WriteLine("Current Culture: {0}",   
Thread.CurrentThread.CurrentUICulture)  
      End Try  
   End Sub  
  
   Public Function FilterFunc As Boolean  
      Console.WriteLine("Current Culture: {0}", Thread.CurrentThread.CurrentUICulture)  
      Return True  
   End Sub  
  
End Class  
```  
  
 <span data-ttu-id="c6dfe-116">La correzione corretta in questo caso consiste nel eseguire il wrapping del blocco **try**/**finally** esistente in un blocco **try**/**catch** .</span><span class="sxs-lookup"><span data-stu-id="c6dfe-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="c6dfe-117">La semplice introduzione di una clausola **catch-throw** nel blocco **try**/**finally** non risolve il problema, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
  
    try   
    {  
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
        // Do something that throws an exception.  
    }  
    catch { throw; }  
    finally   
    {  
        Thread.CurrentThread.CurrentUICulture = saveCulture;  
    }  
}  
```  
  
 <span data-ttu-id="c6dfe-118">Questo non risolve il problema perché l'istruzione **finally** non è stata eseguita prima che l'`FilterFunc` ottenga il controllo.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="c6dfe-119">Nell'esempio seguente viene risolto il problema garantendo che la clausola **finally** sia stata eseguita prima di offrire un'eccezione per i blocchi di filtro eccezioni dei chiamanti.</span><span class="sxs-lookup"><span data-stu-id="c6dfe-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
    try    
    {  
        try   
        {  
            Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
            // Do something that throws an exception.  
        }  
        finally   
        {  
            Thread.CurrentThread.CurrentUICulture = saveCulture;  
        }  
    }  
    catch { throw; }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6dfe-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6dfe-120">See also</span></span>

- [<span data-ttu-id="c6dfe-121">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="c6dfe-121">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
