---
title: MDA invalidCERCall
ms.date: 03/30/2017
helpviewer_keywords:
- invalid CER calls
- InvalidCERCall MDA
- MDAs (managed debugging assistants), CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
ms.openlocfilehash: f8e467401f7c50898613c7cf6eca68a8a705431a
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217388"
---
# <a name="invalidcercall-mda"></a>MDA invalidCERCall
L'assistente al debug gestito `invalidCERCall` viene attivato quando all'interno del grafico delle aree a esecuzione vincolata è presente una chiamata a un metodo che non include alcun contratto di affidabilità o che include un contratto eccessivamente debole. Un contratto debole è un contratto che dichiara che il peggior stato di danneggiamento ha un ambito più vasto rispetto all'istanza passata alla chiamata, ovvero lo stato di <xref:System.AppDomain> o del processo può risultare danneggiato o il risultato non è sempre calcolabile in modo deterministico quando la chiamata avviene all'interno di un'area a esecuzione vincolata.  
  
## <a name="symptoms"></a>Sintomi  
 Risultati imprevisti durante l'esecuzione di codice in un'area a esecuzione vincolata. I sintomi non sono specifici. Potrebbero comprendere un'eccezione <xref:System.OutOfMemoryException> non prevista, un'eccezione <xref:System.Threading.ThreadAbortException> o altre eccezioni nella chiamata nel metodo non affidabile, che non è stato preparato in anticipo o protetto da eccezioni <xref:System.Threading.ThreadAbortException> in fase di esecuzione dal runtime. Una minaccia maggiore è costituita dal fatto che qualsiasi eccezione risultante dal metodo in fase di esecuzione può lasciare <xref:System.AppDomain> o il processo in uno stato instabile, che è un comportamento opposto agli obiettivi di un'area a esecuzione vincolata. Il motivo della creazione di un'area a esecuzione vincolata è evitare danneggiamenti dello stato come questo. I sintomi di uno stato danneggiato sono specifici dell'applicazione, perché la definizione di stato coerente varia a seconda dell'applicazione.  
  
## <a name="cause"></a>Causa  
 Il codice all'interno di un'area a esecuzione vincolata chiama una funzione senza <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> o con un oggetto <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> debole, che non è compatibile con l'esecuzione in un'area a esecuzione vincolata.  
  
 In termini di sintassi del contratto di affidabilità, un contratto debole è un contratto che non specifica un valore di enumerazione <xref:System.Runtime.ConstrainedExecution.Consistency> o che specifica il valore di <xref:System.Runtime.ConstrainedExecution.Consistency> come <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>, <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain> o <xref:System.Runtime.ConstrainedExecution.Cer.None>. Tutte queste condizioni indicano che il codice chiamato può impedire i tentativi di altro codice nell'area a esecuzione vincolata di mantenere uno stato coerente.  Le aree a esecuzione vincolata permettono al codice di gestire gli errori in modo molto deterministico, mantenendo le invarianti interne importanti per l'applicazione e consentendo l'esecuzione continua del codice anche in caso di errori temporanei come le eccezioni di memoria insufficiente.  
  
 L'attivazione di questo assistente al debug gestito indica la possibilità che il metodo chiamato nell'area a esecuzione vincolata possa non riuscire con un comportamento imprevisto per il chiamante o in modo da lasciare lo stato di <xref:System.AppDomain> o del processo danneggiato o non ripristinabile. Naturalmente, è possibile che il codice chiamato venga eseguito correttamente e che il problema sia semplicemente un contratto mancante. Tuttavia, i problemi correlati alla scrittura di codice affidabile sono impercettibili e l'assenza di un contratto è un buon indicatore del rischio che il codice non venga eseguito correttamente. I contratti sono indicatori del fatto che il programmatore ha creato il codice in modo affidabile e lasciano presupporre che queste garanzie resteranno immutate nelle versioni successive del codice.  Questo significa che i contratti sono dichiarazioni di intenti e non solo dettagli di implementazione.  
  
 Poiché qualsiasi metodo con un contratto debole o inesistente può non riuscire in molti modi imprevisti, il runtime non tenta di rimuovere alcuno degli errori imprevisti dal metodo, introdotti, ad esempio, da una compilazione JIT inefficace, dal popolamento di dizionari di generics o da interruzioni dei thread. Di conseguenza, quando questo assistente al debug gestito viene attivato, indica che il runtime non ha incluso il metodo chiamato nell'area a esecuzione vincolata definita. Il grafico chiamate è stato terminato in questo nodo perché se si continua a preparare il sottoalbero, si rischia di contribuire a nascondere il possibile errore.  
  
## <a name="resolution"></a>Risoluzione  
 Aggiungere un contratto di affidabilità valido alla funzione o evitare di usare questa chiamata di funzione.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 L'effetto della chiamata di un contratto debole da un'area a esecuzione vincolata può essere l'incapacità dell'area a esecuzione vincolata di completare le proprie operazioni. Questo problema può provocare il danneggiamento dello stato del processo e di <xref:System.AppDomain>.  
  
## <a name="output"></a>Output  
 Di seguito è riportato un esempio di output generato dall'assistente al debug gestito.  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## <a name="configuration"></a>Configurazione  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
