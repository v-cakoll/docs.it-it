---
title: Thread e threading
ms.date: 11/08/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET]
- threading [.NET], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
ms.openlocfilehash: e29c131f8459179d0641ac9a0cb8234fbba0e7d0
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588436"
---
# <a name="threads-and-threading"></a>Thread e threading

Il multithreading consente di aumentare la velocità di risposta dell'applicazione e, se l'applicazione viene eseguita in un sistema multiprocessore o multicore, aumentare la velocità effettiva.

## <a name="processes-and-threads"></a>Processi e thread

Un *processo* è un programma in esecuzione. Un sistema operativo usa i processi per separare le applicazioni che vengono eseguite. Un *thread* è l'unità di base in cui un sistema operativo alloca il tempo del processore. Ogni thread ha una [priorità di pianificazione](scheduling-threads.md) e un insieme di strutture usate dal sistema per salvare il contesto del thread quando viene sospesa l'esecuzione del thread. Nel contesto del thread sono presenti tutte le informazioni necessarie per riprendere senza problemi l'esecuzione, incluso il set di registri della CPU del thread e lo stack. Nel contesto di un processo possono essere eseguiti più thread. Tutti i thread di un processo ne condividono lo spazio degli indirizzi virtuali. Un thread può eseguire qualsiasi parte del codice del programma, comprese le parti attualmente eseguite da un altro thread.

> [!NOTE]
> .NET Framework offre un modo per isolare le applicazioni all'interno di un processo con l'uso dei *domini dell'applicazione*. I domini applicazione non sono disponibili in .NET Core. Per altre informazioni, vedere la sezione [Domini e thread applicazione](../../framework/app-domains/application-domains.md#application-domains-and-threads) dell'articolo Domini [applicazione.](../../framework/app-domains/application-domains.md)

Per impostazione predefinita, viene avviato un programma .NET con un thread singolo, spesso chiamato *thread primario*. Tuttavia, è possibile creare thread aggiuntivi per eseguire il codice in parallelo o contemporaneamente al thread primario. Questi thread sono spesso chiamati thread di *lavoro.*

## <a name="when-to-use-multiple-threads"></a>Uso di più thread

L'uso di più thread consente di aumentare la velocità di risposta dell'applicazione e di usare un sistema multiprocessore o multicore per aumentare la velocità effettiva dell'applicazione.

Si consideri un'applicazione desktop in cui il thread primario è responsabile degli elementi dell'interfaccia utente e risponde alle azioni dell'utente. Usare i thread di lavoro per eseguire operazioni che richiedono molto tempo e che altrimenti occuperebbero il thread primario e impedirebbero all'interfaccia utente di rispondere. È anche possibile usare un thread dedicato per fare in modo che la comunicazione di rete o del dispositivo sia maggiormente reattiva ai messaggi in ingresso o agli eventi.

Se il programma esegue operazioni che possono essere eseguite in parallelo, il tempo di esecuzione totale può essere ridotto eseguendo queste operazioni in thread separati ed eseguendo il programma in un sistema multiprocessore o multicore. In un sistema di questo tipo, l'uso del multithreading potrebbe aumentare la velocità effettiva e la velocità di risposta.

## <a name="how-to-use-multithreading-in-net"></a>Come usare il multithreading in .NET

A partire da .NET Framework 4, per il multithreading è consigliabile usare [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) e [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md). Per altre informazioni, vedere [Programmazione parallela](../parallel-programming/index.md).

TPL e PLINQ sono entrambi basati su thread <xref:System.Threading.ThreadPool>. La classe <xref:System.Threading.ThreadPool?displayProperty=nameWithType> offre un'applicazione .NET con un pool di thread di lavoro. È possibile usare i thread del pool di thread. Per altre informazioni, vedere [Pool di thread gestiti](the-managed-thread-pool.md).

Infine, è possibile usare la classe <xref:System.Threading.Thread?displayProperty=nameWithType> che rappresenta un thread gestito. Per altre informazioni, vedere [Uso di thread e threading](using-threads-and-threading.md).

È possibile che più thread richiedano l'accesso a una risorsa condivisa. Per mantenere la risorsa in uno stato non danneggiato ed evitare race condition, è necessario sincronizzare l'accesso thread a esso. È anche possibile coordinare l'interazione di più thread. .NET offre una gamma di tipi che è possibile usare per sincronizzare l'accesso a una risorsa condivisa o coordinare l'interazione tra thread. Per altre informazioni, vedere [Panoramica delle primitive di sincronizzazione](overview-of-synchronization-primitives.md).

Gestire le eccezioni nei thread. In genere le eccezioni non gestite nei thread terminano il processo. Per ulteriori informazioni, vedere [Eccezioni nei thread gestiti](exceptions-in-managed-threads.md).

## <a name="see-also"></a>Vedere anche

- [Oggetti e funzionalità del threading](threading-objects-and-features.md)
- [Suggerimenti per l'uso del threading gestito](managed-threading-best-practices.md)
- [Elaborazione parallela, concorrenza e programmazione asincrona in .NET](../parallel-processing-and-concurrency.md)
- [Informazioni su processi e thread](/windows/desktop/procthread/about-processes-and-threads)
