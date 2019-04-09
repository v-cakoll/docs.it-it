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
ms.openlocfilehash: bc8cd20a4183ffd002f1399b6b50c8956208a21b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173676"
---
# <a name="securing-exception-handling"></a><span data-ttu-id="8d476-102">Protezione della gestione delle eccezioni</span><span class="sxs-lookup"><span data-stu-id="8d476-102">Securing Exception Handling</span></span>
<span data-ttu-id="8d476-103">In Visual C++ e Visual Basic, un'espressione di filtro ulteriormente verso l'alto e viene eseguito prima di qualsiasi **infine** istruzione.</span><span class="sxs-lookup"><span data-stu-id="8d476-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="8d476-104">Il **intercettare** blocco associato a tale filtro viene eseguito dopo il **infine** istruzione.</span><span class="sxs-lookup"><span data-stu-id="8d476-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="8d476-105">Per altre informazioni, vedere [eccezioni filtrate dall'utente](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="8d476-105">For more information, see [Using User-Filtered Exceptions](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="8d476-106">In questa sezione esamina le implicazioni di sicurezza di quest'ordine.</span><span class="sxs-lookup"><span data-stu-id="8d476-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="8d476-107">Si consideri l'esempio di pseudocodice seguente è illustrato l'ordine delle istruzioni di filtro e **infine** le istruzioni vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="8d476-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
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
  
 <span data-ttu-id="8d476-108">Questo codice visualizza quanto segue.</span><span class="sxs-lookup"><span data-stu-id="8d476-108">This code prints the following.</span></span>  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="8d476-109">Il filtro viene eseguito prima il **infine** istruzione, in modo che i problemi di sicurezza possono essere introdotti dal tutto ciò che rende uno stato di modifica in cui l'esecuzione di altro codice è stato possibile sfruttare i vantaggi.</span><span class="sxs-lookup"><span data-stu-id="8d476-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="8d476-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8d476-110">For example:</span></span>  
  
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
  
 <span data-ttu-id="8d476-111">Questo pseudocodice consente a un filtro di livello più alto lo stack per l'esecuzione arbitraria di codice.</span><span class="sxs-lookup"><span data-stu-id="8d476-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="8d476-112">Altri esempi di operazioni che possono avere un effetto simile sono la rappresentazione temporanea di un'altra identità, impostando un flag interno che consente di ignorare un controllo di sicurezza o modificare le impostazioni cultura associate al thread.</span><span class="sxs-lookup"><span data-stu-id="8d476-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="8d476-113">La soluzione consigliata è introdurre un gestore di eccezioni per isolare le modifiche del codice dello stato del thread da blocchi dei filtri.</span><span class="sxs-lookup"><span data-stu-id="8d476-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="8d476-114">Tuttavia, è importante che il gestore di eccezioni è lecito correttamente o non verrà risolto questo problema.</span><span class="sxs-lookup"><span data-stu-id="8d476-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="8d476-115">Nell'esempio seguente passa le impostazioni cultura dell'interfaccia utente, ma qualsiasi tipo di modifica dello stato di thread potrebbe essere esposta in modo analogo.</span><span class="sxs-lookup"><span data-stu-id="8d476-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
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
  
 <span data-ttu-id="8d476-116">In questo caso la soluzione corretta consiste nell'inserire l'oggetto esistente **provare**/**infine** blocco in un **provare**/**catch** blocco.</span><span class="sxs-lookup"><span data-stu-id="8d476-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="8d476-117">La semplice introduzione di un **catch-throw** clausola esistente **provare**/**infine** blocco non risolve il problema, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8d476-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="8d476-118">Non viene risolto il problema in quanto il **infine** istruzione non è stato eseguito prima il `FilterFunc` Ottiene controllo.</span><span class="sxs-lookup"><span data-stu-id="8d476-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="8d476-119">Nell'esempio seguente corregge il problema, verificare che il **infine** clausola è stata eseguita prima della generazione di un'eccezione di blocchi di filtro delle eccezioni dei chiamanti.</span><span class="sxs-lookup"><span data-stu-id="8d476-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8d476-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d476-120">See also</span></span>

- [<span data-ttu-id="8d476-121">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="8d476-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
