---
title: MDA asynchronousThreadAbort
description: Verificare il modo in cui viene attivato l'assistente al debug gestito asynchronousThreadAbort quando un thread tenta di inserire un'interruzione asincrona in un altro thread.
ms.date: 03/30/2017
helpviewer_keywords:
- asynchronous thread aborts
- AsynchronousThreadAbort MDA
- managed debugging assistants (MDAs), asynchronous thread aborts
- threading [.NET Framework], managed debugging assistants
- MDAs (managed debugging assistants), asynchronous thread aborts
ms.assetid: 9ebe40b2-d703-421e-8660-984acc42bfe0
ms.openlocfilehash: 469372d57d9c21198353d171fec16458691eb25d
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415667"
---
# <a name="asynchronousthreadabort-mda"></a>MDA asynchronousThreadAbort
L'assistente al debug gestito `asynchronousThreadAbort` viene attivato quando un thread tenta di introdurre un'interruzione asincrona in un altro thread. `asynchronousThreadAbort` non viene invece attivato da interruzioni sincrone dei thread.

## <a name="symptoms"></a>Sintomi
 Quando il thread principale di un'applicazione viene interrotto, l'applicazione si arresta in modo anomalo e viene generata un'eccezione <xref:System.Threading.ThreadAbortException> non gestita. Se l'esecuzione dell'applicazione dovesse continuare, le conseguenze potrebbero essere peggiori di un arresto anomalo. Si potrebbe infatti verificare un ulteriore danneggiamento dei dati.

 Con molta probabilità operazioni che dovevano essere atomiche sono state interrotte dopo il completamento parziale, lasciando i dati dell'applicazione in uno stato imprevedibile. È possibile che venga generata un'eccezione <xref:System.Threading.ThreadAbortException> da punti apparentemente casuali nell'esecuzione del codice, spesso in posizioni in cui non è prevista la generazione di un'eccezione. Il codice può non essere in grado di gestire questo tipo di eccezioni, generando così uno stato danneggiato.

 I sintomi possono variare ampiamente a causa della casualità implicita nel problema.

## <a name="cause"></a>Causa
 Il codice di un thread ha chiamato il metodo <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> su un thread di destinazione per introdurre un'interruzione di thread asincrona. L'interruzione è asincrona perché il codice che effettua la chiamata a <xref:System.Threading.Thread.Abort%2A> è in esecuzione su un thread diverso da quello di destinazione dell'operazione di interruzione. In genere, le interruzioni sincrone dei thread non causano problemi in quanto il thread che esegue il metodo <xref:System.Threading.Thread.Abort%2A> effettua questa operazione solo in un checkpoint sicuro in cui lo stato dell'applicazione è coerente.

 Le interruzioni asincrone dei thread generano invece un problema poiché vengono elaborate in punti imprevisti nell'esecuzione del thread di destinazione. Per evitare questo problema, il codice scritto per essere eseguito su un thread che può essere interrotto in questo modo deve poter gestire un'eccezione <xref:System.Threading.ThreadAbortException> pressoché in corrispondenza di ogni riga di codice, prestando attenzione a ripristinare lo stato di coerenza dei dati dell'applicazione. Non è realistico, tuttavia, prevedere la scrittura di codice tenendo presente questo problema o la protezione da tutti possibili rischi.

 Le chiamate a codice non gestito e a blocchi `finally` non vengono interrotte in modo asincrono, ma all'uscita da una di queste categorie.

 È possibile che la causa sia difficile da determinare a causa della casualità implicita nel problema.

## <a name="resolution"></a>Risoluzione
 Evitare la progettazione di codice che richieda l'utilizzo di interruzioni asincrone dei thread. Per l'interruzione di un thread di destinazione esistono vari approcci più appropriati che non richiedono una chiamata al metodo <xref:System.Threading.Thread.Abort%2A>. L'approccio più sicuro prevede l'introduzione di un meccanismo, ad esempio una proprietà comune, che segnali al thread di destinazione di richiedere un'interruzione. Il thread di destinazione verifica il segnale in determinati checkpoint sicuri e, se rileva una richiesta di interruzione, viene chiuso correttamente.

## <a name="effect-on-the-runtime"></a>Effetto sull'ambiente di esecuzione
 L'assistente al debug gestito non ha alcun effetto su CLR. Si limita a generare un report dei dati relativi alle interruzioni asincrone dei thread.

## <a name="output"></a>Output
 L'assistente al debug gestito segnala l'ID del thread che esegue l'interruzione e l'ID del thread di destinazione dell'interruzione. I due ID non coincideranno mai perché questo tipo di output viene generato solo per le interruzioni asincrone.

## <a name="configuration"></a>Configurazione

```xml
<mdaConfig>
  <assistants>
    <asynchronousThreadAbort />
  </assistants>
</mdaConfig>
```

## <a name="example"></a>Esempio
 L'attivazione dell'assistente al debug gestito `asynchronousThreadAbort` richiede solo una chiamata al metodo <xref:System.Threading.Thread.Abort%2A> su un altro thread in esecuzione. Considerare le conseguenze nel caso in cui il contenuto della funzione di avvio del thread corrispondesse a un insieme di operazioni più complesse che potrebbero essere interrotte in modo anomalo in un qualsiasi punto arbitrario.

```csharp
using System.Threading;
void FireMda()
{
    Thread t = new Thread(delegate() { Thread.Sleep(1000); });
    t.Start();
    // The following line activates the MDA.
    t.Abort();
    t.Join();
}
```

## <a name="see-also"></a>Vedi anche

- <xref:System.Threading.Thread>
- [Diagnostica degli errori tramite gli assistenti al debug gestito](diagnosing-errors-with-managed-debugging-assistants.md)
