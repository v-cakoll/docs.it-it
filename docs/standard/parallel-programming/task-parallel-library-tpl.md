---
title: Task Parallel Library (TPL)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, concurrency in
- .NET, parallel programming in
- Parallel Programming
ms.assetid: b8f99f43-9104-45fd-9bff-385a20488a23
ms.openlocfilehash: 45c9f43e67b66b00758afa0659897971aef317c2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284975"
---
# <a name="task-parallel-library-tpl"></a>Task Parallel Library (TPL)
La libreria Task Parallel Library (TPL) è un set di tipi e API pubblici negli spazi dei nomi <xref:System.Threading?displayProperty=nameWithType> e <xref:System.Threading.Tasks?displayProperty=nameWithType>. Lo scopo di TPL è di rendere gli sviluppatori più produttivi mediante la semplificazione del processo di aggiunta di parallelismo e concorrenza alle applicazioni. La libreria TPL ridimensiona il grado di concorrenza dinamicamente per utilizzare in modo efficace tutti i processori disponibili. La libreria TPL gestisce inoltre il partizionamento del lavoro, la pianificazione dei thread in <xref:System.Threading.ThreadPool>, il supporto per l'annullamento, la gestione dello stato e altri dettagli di basso livello. Quando si utilizza TPL, è possibile ottimizzare le prestazioni del codice concentrandosi sulle operazioni per cui il programma è stato progettato.  
  
 A partire da .NET Framework 4, TPL è la soluzione più adatta per scrivere codice multithreading e parallelo. Tuttavia, non tutto il codice è adatto per la parallelizzazione; ad esempio, se un ciclo esegue solo una piccola parte di lavoro in ciascuna iterazione o non viene eseguito per molte iterazioni, il sovraccarico della parallelizzazione potrebbe provocare un rallentamento dell'esecuzione del codice. Inoltre, la parallelizzazione come qualsiasi codice multithreading, aggiunge complessità all'esecuzione del programma. Benché la libreria TPL semplifichi gli scenari multithreading, è consigliabile avere una conoscenza di base dei concetti relativi all'utilizzo dei thread, ad esempio blocchi, deadlock e race condition. Infatti, ciò consentirà di utilizzare la libreria TPL in modo più efficace.  
  
## <a name="related-topics"></a>Argomenti correlati  
  
|Titolo|Descrizione|  
|-|-|  
|[Parallelismo dei dati](data-parallelism-task-parallel-library.md)|Viene descritto come creare cicli `for` e `foreach` paralleli (`For` e `For Each` in Visual Basic).|  
|[Programmazione asincrona basata su attività](task-based-asynchronous-programming.md)|Viene descritto come creare ed eseguire attività tramite <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> in modo implicito o direttamente tramite oggetti <xref:System.Threading.Tasks.Task> in modo esplicito.|  
|[Flusso di dati](dataflow-task-parallel-library.md)|Viene descritto come utilizzare i componenti del flusso di dati nella libreria del flusso di dati TPL per gestire più operazioni che devono comunicare tra loro o elaborare dati man mano che diventano disponibili.|  
|[Uso di TPL con altri modelli asincroni](using-tpl-with-other-asynchronous-patterns.md)|Viene descritto come usare TPL con altri modelli asincroni in .NET|  
|[Problemi potenziali nel parallelismo di dati e attività](potential-pitfalls-in-data-and-task-parallelism.md)|Vengono descritti alcuni problemi comuni e il modo per evitarli.|  
|[Parallel LINQ (PLINQ)](introduction-to-plinq.md)|Viene descritto come realizzare il parallelismo dei dati con le query LINQ.|  
|[Programmazione parallela](index.md)|Nodo di livello superiore per la programmazione parallela di .NET.|  
  
## <a name="see-also"></a>Vedere anche

- [Esempi per la programmazione parallela con .NET Core & .NET Standard](/samples/browse/?products=dotnet-core%2Cdotnet-standard&term=parallel)
