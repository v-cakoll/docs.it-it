---
title: Utilizzo di thread e threading
ms.date: 08/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
ms.openlocfilehash: 1d487edff2cdc2e63f81963bfaa1f68a06e5b36e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "75936852"
---
# <a name="using-threads-and-threading"></a>Utilizzo di thread e threading

Con .NET è possibile scrivere applicazioni in grado di eseguire più operazioni contemporaneamente. Le operazioni potenzialmente in grado di compromettere altre operazioni possono essere eseguite su thread separati, un processo noto con il nome di *multithreading* o *threading Free*.  
  
Le applicazioni che usano il multithreading sono più reattive all'input dell'utente poiché l'interfaccia utente rimane attiva mentre le attività che richiedono un uso intensivo del processore vengono eseguite su thread separati. Il multithreading è utile anche durante la creazione di applicazioni scalabili poiché consente di aggiungere thread man mano che aumenta il carico di lavoro.

> [!NOTE]
> Nel caso sia necessario un maggiore controllo sul comportamento dei thread dell'applicazione, è possibile gestirli personalmente. Tuttavia, a partire da .NET Framework 4, la programmazione multithreading è notevolmente semplificata con le classi <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> e <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, [Parallel LINQ (PLINQ)](../parallel-programming/parallel-linq-plinq.md), le nuove classi di raccolta simultanee nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType> e un nuovo modello di programmazione che si basa sul concetto di attività anziché di thread. Per altre informazioni, vedere [Programmazione parallela](../parallel-programming/index.md) e [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md).

## <a name="how-to-create-and-start-a-new-thread"></a>Procedura: Creare e avviare un nuovo thread

Per creare un nuovo thread, creare una nuova istanza della classe <xref:System.Threading.Thread?displayProperty=nameWithType> e fornire al costruttore il nome del metodo che si vuole eseguire in un nuovo thread. Per avviare un thread creato, chiamare il metodo <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>. Per altre informazioni ed esempi, vedere l'articolo [Creazione di thread e passaggio di dati all'avvio](creating-threads-and-passing-data-at-start-time.md) e il riferimento API <xref:System.Threading.Thread>.

## <a name="how-to-stop-a-thread"></a>Procedura: Arrestare un thread

Per terminare l'esecuzione di <xref:System.Threading.CancellationToken?displayProperty=nameWithType>un thread, utilizzare il metodo . Fornisce un modo unificato per arrestare i thread in modo cooperativo. Per altre informazioni, vedere [Annullamento in thread gestiti](cancellation-in-managed-threads.md).

A volte non è possibile arrestare un thread in modo cooperativo, perché esegue codice di terze parti non progettato per l'annullamento cooperativo. In questo caso, è possibile terminarne l'esecuzione forzatamente. Per terminare l'esecuzione di un thread con la coattività, in .NET Framework è possibile utilizzare il <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> metodo . Questo metodo genera un oggetto <xref:System.Threading.ThreadAbortException> nel thread in cui viene richiamato. Per altre informazioni, vedere [Eliminazione definitiva di thread](destroying-threads.md). Il <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> metodo non è supportato in .NET Core.The method is not supported in .NET Core. Se è necessario terminare l'esecuzione di codice di terze parti con la coattività <xref:System.Diagnostics.Process.Kill%2A?displayProperty=nameWithType>in .NET Core, eseguirlo nel processo separato e utilizzare .

Il <xref:System.Threading.CancellationToken?displayProperty=nameWithType> non è disponibile prima di .NET Framework 4. Per arrestare un thread nelle versioni precedenti di .NET Framework, è necessario implementare manualmente l'annullamento cooperativo utilizzando le tecniche di sincronizzazione dei thread. Ad esempio, è possibile creare `shouldStop` il campo booleano volatile e utilizzarlo per richiedere il codice eseguito dal thread per interrompere. Per ulteriori informazioni, vedere [volatile](../../csharp/language-reference/keywords/volatile.md) <xref:System.Threading.Volatile?displayProperty=nameWithType>in Riferimenti per Il linguaggio Visual Basic e .

Utilizzare <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType> il metodo per fare in modo che il thread chiamante attenda la terminazione del thread arrestato.

## <a name="how-to-pause-or-interrupt-a-thread"></a>Procedura: Sospendere o interrompere un thread

È possibile usare il metodo <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> per sospendere il thread corrente per un periodo di tempo specificato. È possibile interrompere un thread bloccato chiamando il metodo <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType>. Per altre informazioni, vedere [Sospensione e interruzione di thread](pausing-and-resuming-threads.md).

## <a name="thread-properties"></a>Proprietà del thread

La tabella seguente illustra alcune delle proprietà dell'oggetto <xref:System.Threading.Thread>:  
  
|Proprietà|Descrizione|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|Restituisce `true` se il thread è stato avviato, ma non è stato ancora terminato normalmente o è stato interrotto.|  
|<xref:System.Threading.Thread.IsBackground%2A>|Ottiene o imposta un valore booleano che indica se un thread è un thread in background. I thread in background sono simili ai thread in primo piano, ma un thread in background non impedisce l'arresto di un processo. Dopo l'arresto di tutti i thread in primo piano che appartengono a un processo, Common Language Runtime termina il processo chiamando il metodo <xref:System.Threading.Thread.Abort%2A> nei thread in background ancora attivi. Per altre informazioni, vedere [Thread in primo piano e in background](foreground-and-background-threads.md).|  
|<xref:System.Threading.Thread.Name%2A>|Ottiene o imposta il nome del thread. Usato in genere per individuare i singoli thread durante il debug.|  
|<xref:System.Threading.Thread.Priority%2A>|Ottiene o imposta un valore <xref:System.Threading.ThreadPriority> che viene usato dal sistema operativo per definire le priorità di pianificazione dei thread. Per altre informazioni, vedere [Pianificazione di thread](scheduling-threads.md) e il riferimento <xref:System.Threading.ThreadPriority>.|  
|<xref:System.Threading.Thread.ThreadState%2A>|Ottiene un valore <xref:System.Threading.ThreadState> contenente gli stati correnti di un thread.|  

## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Thread?displayProperty=nameWithType>
- [Thread e threading](threads-and-threading.md)
- [Programmazione parallela](../parallel-programming/index.md)
