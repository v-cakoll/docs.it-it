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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe978930a9f84e0084f79f5fe585a1ecc3bf4eb2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393042"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="92e88-102">Protezione della gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="92e88-102">Securing Exception Handling</span></span>
<span data-ttu-id="92e88-103">In Visual C++ e Visual Basic, un'espressione di filtro ulteriormente verso l'alto e viene eseguito prima di qualsiasi **infine** istruzione.</span><span class="sxs-lookup"><span data-stu-id="92e88-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="92e88-104">Il **catch** blocco associato a tale filtro viene eseguito dopo il **infine** istruzione.</span><span class="sxs-lookup"><span data-stu-id="92e88-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="92e88-105">Per ulteriori informazioni, vedere [eccezioni filtrate dall'utente](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="92e88-105">For more information, see [Using User-Filtered Exceptions](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="92e88-106">In questa sezione vengono esaminate le implicazioni di sicurezza di questo ordine.</span><span class="sxs-lookup"><span data-stu-id="92e88-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="92e88-107">Si consideri l'esempio di pseudocodice seguente è illustrato l'ordine delle istruzioni di filtro e **infine** le istruzioni vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="92e88-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="92e88-108">Questo codice visualizza quanto segue.</span><span class="sxs-lookup"><span data-stu-id="92e88-108">This code prints the following.</span></span>  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="92e88-109">Il filtro viene eseguito prima il **infine** istruzione, in modo da problemi di sicurezza possono essere introdotti dal tutto ciò che viene in cui l'esecuzione di altro codice potrebbe sfruttare.</span><span class="sxs-lookup"><span data-stu-id="92e88-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="92e88-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="92e88-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="92e88-111">Questo pseudo-codice consente un filtro di livello più alto lo stack di eseguire codice arbitrario.</span><span class="sxs-lookup"><span data-stu-id="92e88-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="92e88-112">Altri esempi di operazioni che possono avere un effetto simile sono la rappresentazione temporanea di un'altra identità, l'impostazione di un flag interno che consente di ignorare un controllo di sicurezza o modificare le impostazioni cultura associate al thread.</span><span class="sxs-lookup"><span data-stu-id="92e88-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="92e88-113">La soluzione consigliata consiste nell'introduzione di un gestore di eccezioni per isolare le modifiche del codice dello stato del thread da blocchi dei filtri.</span><span class="sxs-lookup"><span data-stu-id="92e88-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="92e88-114">Tuttavia, è importante che il gestore di eccezioni sia introdotto o non verrà risolto il problema.</span><span class="sxs-lookup"><span data-stu-id="92e88-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="92e88-115">Nell'esempio seguente passa le impostazioni cultura dell'interfaccia utente, ma qualsiasi tipo di modifica dello stato di thread potrebbe essere esposta in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="92e88-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="92e88-116">Per eseguire il wrapping esistente è in questo caso è la soluzione corretta **provare**/**infine** blocco in un **provare**/**catch** blocco.</span><span class="sxs-lookup"><span data-stu-id="92e88-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="92e88-117">La semplice introduzione di un **catch-throw** clausola in esistente **provare**/**infine** blocco il problema persiste, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="92e88-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="92e88-118">Ciò non risolve il problema, perché il **infine** istruzione non è stato eseguito prima il `FilterFunc` Ottiene controllo.</span><span class="sxs-lookup"><span data-stu-id="92e88-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="92e88-119">Nell'esempio seguente corregge il problema, verificare che il **infine** clausola sia eseguita prima della generazione di un'eccezione di blocchi di filtro delle eccezioni dei chiamanti.</span><span class="sxs-lookup"><span data-stu-id="92e88-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="92e88-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92e88-120">See Also</span></span>  
 [<span data-ttu-id="92e88-121">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="92e88-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
