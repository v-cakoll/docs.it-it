---
title: MDA illegalPrepareConstrainedRegion
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23a36d1709f03583ce39af0e7c80bb1ecd7cf809
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754388"
---
# <a name="illegalprepareconstrainedregion-mda"></a>MDA illegalPrepareConstrainedRegion
L'assistente al debug gestito `illegalPrepareConstrainedRegion` viene attivato quando una chiamata al metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> non precede immediatamente l'istruzione `try` del gestore di eccezioni. Poiché questa restrizione è a livello MSIL, è consentita la presenza di un'origine che non genera codice tra la chiamata e l'istruzione `try`, ad esempio commenti.  
  
## <a name="symptoms"></a>Sintomi  
 Area a esecuzione vincolata che non viene mai considerata come tale, ma come semplice blocco di gestione delle eccezioni (`finally` o `catch`). Di conseguenza, l'area non viene eseguita nel caso di una condizione di memoria insufficiente o di interruzione del thread.  
  
## <a name="cause"></a>Causa  
 Il modello di preparazione per un'area a esecuzione vincolata non è stato applicato correttamente.  Si tratta di un evento di errore. Il <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> chiamata al metodo usato per contrassegnare i gestori di eccezioni come introduzione a un'area a esecuzione vincolata in loro `catch` / `finally` / `fault` / `filter` blocchi devono essere usati immediatamente prima di `try` istruzione.  
  
## <a name="resolution"></a>Risoluzione  
 Assicurarsi che la chiamata a <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> avvenga immediatamente prima dell'istruzione `try`.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'assistente al debug gestito non ha alcun effetto su CLR.  
  
## <a name="output"></a>Output  
 L'assistente al debug gestito visualizza il nome del metodo che chiama il metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, l'offset MSIL e un messaggio indicante che la chiamata non precede immediatamente l'inizio del blocco try.  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Esempio  
 Il codice di esempio seguente mostra il modello che causa l'attivazione di questo assistente al debug gestito.  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../../../docs/framework/interop/interop-marshaling.md)
