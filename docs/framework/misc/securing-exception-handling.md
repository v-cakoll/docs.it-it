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
ms.openlocfilehash: c406edcef393d3c2b9e4cf6dbeee9d572c0951f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679383"
---
# <a name="securing-exception-handling"></a>Protezione della gestione delle eccezioni
In Visual C++ e Visual Basic, un'espressione di filtro ulteriormente verso l'alto e viene eseguito prima di qualsiasi **infine** istruzione. Il **intercettare** blocco associato a tale filtro viene eseguito dopo il **infine** istruzione. Per altre informazioni, vedere [eccezioni filtrate dall'utente](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md). In questa sezione esamina le implicazioni di sicurezza di quest'ordine. Si consideri l'esempio di pseudocodice seguente è illustrato l'ordine delle istruzioni di filtro e **infine** le istruzioni vengono eseguite.  
  
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
  
 Questo codice visualizza quanto segue.  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 Il filtro viene eseguito prima il **infine** istruzione, in modo che i problemi di sicurezza possono essere introdotti dal tutto ciò che rende uno stato di modifica in cui l'esecuzione di altro codice è stato possibile sfruttare i vantaggi. Ad esempio:  
  
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
  
 Questo pseudocodice consente a un filtro di livello più alto lo stack per l'esecuzione arbitraria di codice. Altri esempi di operazioni che possono avere un effetto simile sono la rappresentazione temporanea di un'altra identità, impostando un flag interno che consente di ignorare un controllo di sicurezza o modificare le impostazioni cultura associate al thread. La soluzione consigliata è introdurre un gestore di eccezioni per isolare le modifiche del codice dello stato del thread da blocchi dei filtri. Tuttavia, è importante che il gestore di eccezioni è lecito correttamente o non verrà risolto questo problema. Nell'esempio seguente passa le impostazioni cultura dell'interfaccia utente, ma qualsiasi tipo di modifica dello stato di thread potrebbe essere esposta in modo analogo.  
  
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
  
 In questo caso la soluzione corretta consiste nell'inserire l'oggetto esistente **provare**/**infine** blocco in un **provare**/**catch** blocco. La semplice introduzione di un **catch-throw** clausola esistente **provare**/**infine** blocco non risolve il problema, come illustrato nell'esempio seguente.  
  
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
  
 Non viene risolto il problema in quanto il **infine** istruzione non è stato eseguito prima il `FilterFunc` Ottiene controllo.  
  
 Nell'esempio seguente corregge il problema, verificare che il **infine** clausola è stata eseguita prima della generazione di un'eccezione di blocchi di filtro delle eccezioni dei chiamanti.  
  
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
  
## <a name="see-also"></a>Vedere anche
- [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md)
