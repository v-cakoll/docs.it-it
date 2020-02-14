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
ms.openlocfilehash: 8f1621090079c030e3c055a417ed9bcad882bf78
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217227"
---
# <a name="reentrancy-mda"></a>rientranza (MDA)
L'assistente al debug gestito `reentrancy` viene attivato quando viene effettuato un tentativo di transizione da codice nativo a codice gestito nei casi in cui un precedente passaggio da codice gestito a nativo non è stato eseguito mediante una transizione ordinata.  
  
## <a name="symptoms"></a>Sintomi  
 L'heap di oggetti è danneggiato o si stanno verificando altri errori gravi durante la transizione da codice nativo a codice gestito.  
  
 I thread che passano da codice nativo a codice gestito e viceversa devono eseguire una transizione ordinata. Alcuni punti di estendibilità di basso livello nel sistema operativo, ad esempio il gestore di eccezioni con vettori, consentono tuttavia il passaggio da codice gestito a codice nativo senza eseguire una transizione ordinata.  Questi passaggi avvengono sotto il controllo del sistema operativo, invece che di Common Language Runtime (CLR).  Il codice nativo eseguito in questi punti di estendibilità deve evitare il callback nel codice gestito.  
  
## <a name="cause"></a>Causa  
 Un punto di estendibilità di basso livello del sistema operativo, ad esempio il gestore di eccezioni con vettori, è stato attivato durante l'esecuzione di codice gestito.  Il codice dell'applicazione che viene richiamato tramite tale punto di estendibilità sta cercando di eseguire il callback nel codice gestito.  
  
 Questo problema è sempre causato dal codice dell'applicazione.  
  
## <a name="resolution"></a>Risoluzione  
 Esaminare l'analisi dello stack per il thread che ha attivato questo assistente al debug gestito.  Il thread sta cercando di eseguire una chiamata non valida nel codice gestito.  L'analisi dello stack indica il codice dell'applicazione che usa il punto di estendibilità, il codice del sistema operativo che fornisce il punto di estendibilità e il codice gestito interrotto dal punto di estendibilità.  
  
 Si noterà, ad esempio, che l'assistente al debug gestito viene attivato in un tentativo di chiamare il codice gestito da un gestore di eccezioni con vettori.  Nello stack sarà possibile vedere il codice di gestione delle eccezioni del sistema operativo e il codice gestito che genera un'eccezione come <xref:System.DivideByZeroException> o <xref:System.AccessViolationException>.  
  
 In questo esempio la risoluzione corretta consiste nell'implementare il gestore di eccezioni con vettori completamente nel codice non gestito.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR.  
  
## <a name="output"></a>Output  
 L'assistente al debug gestito indica il tentativo di reentrancy non valida.  Esaminare lo stack del thread per determinare il motivo per cui ciò si verifica e come risolvere il problema. Di seguito è riportato l'output di esempio.  
  
```output
Additional Information: Attempting to call into managed code without   
transitioning out first.  Do not attempt to run managed code inside   
low-level native extensibility points. Managed Debugging Assistant   
'Reentrancy' has detected a problem in 'D:\ConsoleApplication1\  
ConsoleApplication1\bin\Debug\ConsoleApplication1.vshost.exe'.  
```  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reentrancy />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Esempio  
 Il codice seguente causa la generazione di un'eccezione <xref:System.AccessViolationException>.  Nelle versioni di Windows che supportano la gestione delle eccezioni con vettori, ciò causa la chiamata del gestore di eccezioni con vettori gestito.  Se l'assistente al debug gestito `reentrancy` è abilitato, verrà attivato durante il tentativo di chiamata a `MyHandler` dal codice di supporto di gestione delle eccezioni con vettori del sistema operativo.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
