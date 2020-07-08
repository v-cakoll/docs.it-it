---
title: MDA illegalPrepareConstrainedRegion
description: Esaminare l'assistente al debug gestito illegalPrepareConstrainedRegion, che viene richiamato se una chiamata PrepareConstrainedRegions non è seguita da un'istruzione try.
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
ms.openlocfilehash: d6a0d1d95840ebd735806c5547730ae9e0b2aace
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051285"
---
# <a name="illegalprepareconstrainedregion-mda"></a>MDA illegalPrepareConstrainedRegion
L'assistente al debug gestito `illegalPrepareConstrainedRegion` viene attivato quando una chiamata al metodo <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> non precede immediatamente l'istruzione `try` del gestore di eccezioni. Poiché questa restrizione è a livello MSIL, è consentita la presenza di un'origine che non genera codice tra la chiamata e l'istruzione `try`, ad esempio commenti.  
  
## <a name="symptoms"></a>Sintomi  
 Area a esecuzione vincolata che non viene mai considerata come tale, ma come semplice blocco di gestione delle eccezioni (`finally` o `catch`). Di conseguenza, l'area non viene eseguita nel caso di una condizione di memoria insufficiente o di interruzione del thread.  
  
## <a name="cause"></a>Causa  
 Il modello di preparazione per un'area a esecuzione vincolata non è stato applicato correttamente.  Si tratta di un evento di errore. La <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> chiamata al metodo utilizzata per contrassegnare i gestori di eccezioni come introduzione a una CER nei `catch` / `finally` / `fault` / `filter` blocchi deve essere utilizzata immediatamente prima dell' `try` istruzione.  
  
## <a name="resolution"></a>Soluzione  
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
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshalling di interoperabilità](../interop/interop-marshaling.md)
