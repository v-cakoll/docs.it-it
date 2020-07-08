---
title: moduloObjectHashcode (MDA)
description: Esaminare l'assistente al debug gestito moduloObjectHashcode, che modifica la classe dell'oggetto per ottenere un valore di resto in un risultato del metodo GetHashCode.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
ms.openlocfilehash: a929ec2b9196f1f6cad0528fdf7323839a86fa55
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052065"
---
# <a name="moduloobjecthashcode-mda"></a>moduloObjectHashcode (MDA)
L'assistente al debug gestito `moduloObjectHashcode` modifica il comportamento della classe <xref:System.Object> per eseguire un'operazione modulo sul codice hash restituito dal metodo <xref:System.Object.GetHashCode%2A>. Il modulo predefinito per questo assistente al debug gestito è 1, che fa sì che <xref:System.Object.GetHashCode%2A> restituisca 0 per tutti gli oggetti.  
  
## <a name="symptoms"></a>Sintomi  
 Dopo la migrazione a una nuova versione di Common Language Runtime (CLR), un programma non viene più eseguito correttamente:  
  
- Il programma ottiene un oggetto non corretto da una <xref:System.Collections.Hashtable>.  
  
- L'ordine di enumerazione da una <xref:System.Collections.Hashtable> include una modifica che compromette il funzionamento del programma.  
  
- Due oggetti che erano uguali non sono più uguali.  
  
- Due oggetti che erano diversi sono ora uguali.  
  
## <a name="cause"></a>Causa  
 È possibile che il programma ottenga l'oggetto non corretto da una <xref:System.Collections.Hashtable> perché l'implementazione del metodo <xref:System.Object.Equals%2A> nella classe per la chiave in <xref:System.Collections.Hashtable> verifica l'uguaglianza degli oggetti confrontando i risultati della chiamata al metodo <xref:System.Object.GetHashCode%2A>. Non è consigliabile usare i codici hash per verificare l'uguaglianza di oggetti perché due oggetti possono avere lo stesso codice hash, anche se i rispettivi campi hanno valori diversi. Queste collisioni di codici hash, anche se nella pratica si tratta di eventi rari, possono verificarsi. L'effetto su una ricerca <xref:System.Collections.Hashtable> è che due chiavi diverse risultano apparentemente uguali e <xref:System.Collections.Hashtable> restituisce un oggetto non corretto. Per motivi di prestazioni, l'implementazione di <xref:System.Object.GetHashCode%2A> può cambiare tra versioni di runtime diverse, quindi potrebbero verificarsi collisioni in una versione e non nelle versioni successive. Abilitare questo assistente al debug gestito per verificare se il codice include bug in caso di collisioni di codici hash. Quando questo assistente al debug gestito viene abilitato, il metodo <xref:System.Object.GetHashCode%2A> restituisce 0, quindi tutti i codici hash risultano in collisione. L'unico effetto dell'abilitazione di questo assistente al debug gestito sul programma è un rallentamento dell'esecuzione.  
  
 L'ordine di enumerazione da una <xref:System.Collections.Hashtable> può variare tra le diverse versioni di runtime se cambia l'algoritmo usato per calcolare i codici hash per la chiave. Per verificare se il programma ha una dipendenza dall'ordine di enumerazione delle chiavi o dei valori da una tabella hash, è possibile abilitare questo assistente al debug gestito.  
  
## <a name="resolution"></a>Soluzione  
 Non usare mai codici hash in sostituzione all'identità dell'oggetto. Implementare l'override del metodo <xref:System.Object.Equals%2A?displayProperty=nameWithType> per non confrontare i codici hash.  
  
 Non creare dipendenze dall'ordine di enumerazione delle chiavi o dei valori nelle tabelle hash.  
  
## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione  
 Le applicazioni vengono eseguite più lentamente quando si abilita questo assistente al debug gestito. Questo assistente al debug gestito accetta semplicemente il codice hash che sarebbe stato restituito e restituisce invece il resto della divisione di un modulo.  
  
## <a name="output"></a>Output  
 Non è previsto alcun output per questo assistente al debug gestito.  
  
## <a name="configuration"></a>Configurazione  
 L'attributo `modulus` specifica il modulo usato sul codice hash. Il valore predefinito è 1.  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
