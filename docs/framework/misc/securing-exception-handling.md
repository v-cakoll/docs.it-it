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
# <a name="securing-exception-handling"></a>Protezione della gestione delle eccezioni
In Visual C++ e Visual Basic, un'espressione di filtro più avanti lo stack viene eseguita prima di qualsiasi istruzione **finally** . Il blocco **catch** associato a tale filtro viene eseguito dopo l'istruzione **finally** . Per ulteriori informazioni, vedere [utilizzo di eccezioni filtrate dall'utente](../../standard/exceptions/using-user-filtered-exception-handlers.md). In questa sezione vengono esaminate le implicazioni di sicurezza di questo ordine. Si consideri l'esempio di pseudocodice seguente che illustra l'ordine in cui vengono eseguite le istruzioni di filtro e le istruzioni **finally** .  
  
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
  
 Questo codice stampa quanto segue.  
  
```output
Throw  
Filter  
Finally  
Catch  
```  
  
 Il filtro viene eseguito prima dell'istruzione **finally** , quindi i problemi di sicurezza possono essere introdotti da qualsiasi elemento che apporta una modifica dello stato in cui l'esecuzione di altro codice potrebbe trarre vantaggio. Ad esempio:  
  
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
  
 Questo pseudocodice consente a un filtro di ottenere un livello superiore dello stack per eseguire codice arbitrario. Altri esempi di operazioni che hanno un effetto simile sono la rappresentazione temporanea di un'altra identità, l'impostazione di un flag interno che ignora un controllo di sicurezza o la modifica delle impostazioni cultura associate al thread. La soluzione consigliata consiste nell'introdurre un gestore di eccezioni per isolare le modifiche del codice nello stato del thread dai blocchi di filtro dei chiamanti. Tuttavia, è importante che il gestore di eccezioni venga introdotto correttamente o che il problema non venga risolto. Nell'esempio seguente vengono modificate le impostazioni cultura dell'interfaccia utente, ma qualsiasi tipo di modifica dello stato del thread potrebbe essere esposto in modo analogo.  
  
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
  
 La correzione corretta in questo caso consiste nel eseguire il wrapping del blocco **try**/**finally** esistente in un blocco **try**/**catch** . La semplice introduzione di una clausola **catch-throw** nel blocco **try**/**finally** non risolve il problema, come illustrato nell'esempio seguente.  
  
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
  
 Questo non risolve il problema perché l'istruzione **finally** non è stata eseguita prima che l'`FilterFunc` ottenga il controllo.  
  
 Nell'esempio seguente viene risolto il problema garantendo che la clausola **finally** sia stata eseguita prima di offrire un'eccezione per i blocchi di filtro eccezioni dei chiamanti.  
  
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

- [Linee guida per la generazione di codice sicuro](../../standard/security/secure-coding-guidelines.md)
