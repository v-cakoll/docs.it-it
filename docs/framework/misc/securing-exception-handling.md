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
# <a name="securing-exception-handling"></a>Protezione della gestione delle eccezioni
In Visual C++ e Visual Basic, un'espressione di filtro ulteriormente verso l'alto e viene eseguito prima di qualsiasi **infine** istruzione. Il **catch** blocco associato a tale filtro viene eseguito dopo il **infine** istruzione. Per ulteriori informazioni, vedere [eccezioni filtrate dall'utente](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md). In questa sezione vengono esaminate le implicazioni di sicurezza di questo ordine. Si consideri l'esempio di pseudocodice seguente è illustrato l'ordine delle istruzioni di filtro e **infine** le istruzioni vengono eseguite.  
  
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
  
 Il filtro viene eseguito prima il **infine** istruzione, in modo da problemi di sicurezza possono essere introdotti dal tutto ciò che viene in cui l'esecuzione di altro codice potrebbe sfruttare. Ad esempio:  
  
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
  
 Questo pseudo-codice consente un filtro di livello più alto lo stack di eseguire codice arbitrario. Altri esempi di operazioni che possono avere un effetto simile sono la rappresentazione temporanea di un'altra identità, l'impostazione di un flag interno che consente di ignorare un controllo di sicurezza o modificare le impostazioni cultura associate al thread. La soluzione consigliata consiste nell'introduzione di un gestore di eccezioni per isolare le modifiche del codice dello stato del thread da blocchi dei filtri. Tuttavia, è importante che il gestore di eccezioni sia introdotto o non verrà risolto il problema. Nell'esempio seguente passa le impostazioni cultura dell'interfaccia utente, ma qualsiasi tipo di modifica dello stato di thread potrebbe essere esposta in modo analogo.  
  
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
  
 Per eseguire il wrapping esistente è in questo caso è la soluzione corretta **provare**/**infine** blocco in un **provare**/**catch** blocco. La semplice introduzione di un **catch-throw** clausola in esistente **provare**/**infine** blocco il problema persiste, come illustrato nell'esempio seguente.  
  
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
  
 Ciò non risolve il problema, perché il **infine** istruzione non è stato eseguito prima il `FilterFunc` Ottiene controllo.  
  
 Nell'esempio seguente corregge il problema, verificare che il **infine** clausola sia eseguita prima della generazione di un'eccezione di blocchi di filtro delle eccezioni dei chiamanti.  
  
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
 [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md)
