---
title: Stati dei thread gestiti
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], states
ms.assetid: 63890d5e-6025-4a7c-aaf0-d8bfd54b455f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a55409cd2c3bed2bc09db10622de1cceab934112
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "46711148"
---
# <a name="managed-thread-states"></a>Stati dei thread gestiti
La proprietà <xref:System.Threading.Thread.ThreadState%2A?displayProperty=nameWithType> fornisce una maschera di bit che indica lo stato corrente del thread. Un thread si trova sempre in almeno uno degli stati possibili nell'enumerazione <xref:System.Threading.ThreadState> e può essere contemporaneamente in più stati.  
  
> [!IMPORTANT]
>  Lo stato del thread è importante solo in alcuni scenari di debug. Il codice non deve mai usare lo stato del thread per sincronizzare le attività dei thread.  
  
 Quando si crea un thread gestito, viene visualizzato in stato <xref:System.Threading.ThreadState.Unstarted> . Il thread rimane in stato <xref:System.Threading.ThreadState.Unstarted> fino a quando il sistema operativo non lo sposta in stato avviato. La chiamata <xref:System.Threading.Thread.Start%2A> informa il sistema operativo che può essere avviato il thread. Lo stato del thread non viene modificato.  
  
 I thread non gestiti che accedono all'ambiente gestito si trovano già in stato avviato. Quando un thread è in stato avviato, diverse azioni possono modificarne lo stato. La tabella seguente elenca le azioni che causano una modifica di stato e il nuovo stato corrispondente.  
  
|Operazione|Nuovo stato risultante|  
|------------|-------------------------|  
|Viene chiamato il costruttore per la classe <xref:System.Threading.Thread> .|<xref:System.Threading.ThreadState.Unstarted>|  
|Un altro thread chiama <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Unstarted>|  
|Il thread risponde a <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> e avvia l'esecuzione.|<xref:System.Threading.ThreadState.Running>|  
|Il thread chiama <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|Il thread chiama <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> su un altro oggetto.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|Il thread chiama <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> su un altro thread.|<xref:System.Threading.ThreadState.WaitSleepJoin>|  
|Un altro thread chiama <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.SuspendRequested>|  
|Il thread risponde a una richiesta <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Suspended>|  
|Un altro thread chiama <xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Running>|  
|Un altro thread chiama <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.AbortRequested>|  
|Il thread risponde ad <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.|<xref:System.Threading.ThreadState.Aborted>, quindi <xref:System.Threading.ThreadState.Stopped>|  
  
 Poiché lo stato <xref:System.Threading.ThreadState.Running> ha un valore 0, non è possibile eseguire un test dei bit per individuare lo stato. Al suo posto, usare il test seguente (in pseudocodice):  
  
```  
if ((state & (Unstarted | Stopped)) == 0)   // implies Running     
```  
  
 In uno specifico momento, i thread spesso sono in più di uno stato. Se ad esempio un thread è bloccato in una chiamata a <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> e un altro thread chiama <xref:System.Threading.Thread.Abort%2A> nello stesso thread, il thread sarà contemporaneamente nello stato <xref:System.Threading.ThreadState.WaitSleepJoin> e <xref:System.Threading.ThreadState.AbortRequested>. In tal caso, non appena il thread viene restituito dalla chiamata a <xref:System.Threading.Monitor.Wait%2A> o viene interrotto, riceve <xref:System.Threading.ThreadAbortException>.  
  
 Quando un thread lascia lo stato <xref:System.Threading.ThreadState.Unstarted> in seguito a una chiamata a <xref:System.Threading.Thread.Start%2A>, non può più tornare allo stato <xref:System.Threading.ThreadState.Unstarted> . Un thread non può mai lasciare lo stato <xref:System.Threading.ThreadState.Stopped> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.ThreadAbortException>  
- <xref:System.Threading.Thread>  
- <xref:System.Threading.ThreadState>  
- [Threading](../../../docs/standard/threading/index.md)
