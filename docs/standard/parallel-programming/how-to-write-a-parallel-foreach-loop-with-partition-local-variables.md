---
title: 'Procedura: Scrivere un ciclo Parallel.ForEach con variabili partition-local'
ms.date: 06/26/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel foreach loop, how to use local state
ms.assetid: 24b10041-b30b-45cb-aa65-66cf568ca76d
ms.openlocfilehash: eff176f7c3ae5cae4c450047214d8e9e20a6e66d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290746"
---
# <a name="how-to-write-a-parallelforeach-loop-with-partition-local-variables"></a>Procedura: Scrivere un ciclo Parallel.ForEach con variabili partition-local

L'esempio seguente illustra come scrivere un metodo <xref:System.Threading.Tasks.Parallel.ForEach%2A> che usa variabili partition-local. Quando viene eseguito un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A>, la relativa raccolta di origine viene divisa in più partizioni. Ogni partizione ha la propria copia della variabile partition-local. Una variabile partition-local è simile a una [variabile thread-local](xref:System.Threading.ThreadLocal%601), tranne per il fatto che in un singolo thread possono essere eseguite più partizioni.

Il codice e i parametri riportati in questo esempio, somigliano molto al metodo <xref:System.Threading.Tasks.Parallel.For%2A> corrispondente. Per altre informazioni, vedere [Procedura: scrivere un ciclo Parallel.For con variabili di thread locali](how-to-write-a-parallel-for-loop-with-thread-local-variables.md).

Per usare una variabile partition-local in un ciclo <xref:System.Threading.Tasks.Parallel.ForEach%2A>, è necessario chiamare uno degli overload del metodo che accetta due parametri di tipo. Il primo parametro di tipo, `TSource`, specifica il tipo di elemento di origine, mentre il secondo parametro di tipo, `TLocal`, specifica il tipo di variabile partition-local.

## <a name="example"></a>Esempio

Nell'esempio seguente viene chiamato l'overload <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> per calcolare la somma di una matrice di un milione di elementi. L'overload ha quattro parametri:

- `source`, ovvero l'origine dati. Deve implementare <xref:System.Collections.Generic.IEnumerable%601>. L'origine dati nell'esempio è l'oggetto `IEnumerable<Int32>` da un milione di membri restituito dal metodo <xref:System.Linq.Enumerable.Range%2A?displayProperty=nameWithType>.

- `localInit`, ovvero la funzione che inizializza la variabile partition-local. Questa funzione viene chiamata una volta per ogni partizione in cui viene eseguita l'operazione <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>. Nell'esempio, la variabile partition-local viene inizializzata su zero.

- `body`, un delegato <xref:System.Func%604> che viene richiamato dal ciclo parallelo per ogni iterazione del ciclo. La firma è `Func\<TSource, ParallelLoopState, TLocal, TLocal>`. Si fornisce il codice per il delegato e il ciclo passa i parametri di input, che sono:

  - L'elemento corrente dell'oggetto <xref:System.Collections.Generic.IEnumerable%601>.

  - Una variabile <xref:System.Threading.Tasks.ParallelLoopState> che si può usare nel codice del delegato per esaminare lo stato del ciclo.

  - La variabile partition-local.

  Il delegato restituisce la variabile partition-local, che viene quindi passata all'iterazione successiva del ciclo che viene eseguito in quella partizione specifica. Ogni partizione del ciclo mantiene un'istanza separata di questa variabile.

  Nell'esempio il delegato aggiunge il valore di ogni valore integer alla variabile partition-local, che mantiene un totale corrente dei valori degli elementi integer in quella partizione.

- `localFinally`, un delegato `Action<TLocal>` che viene richiamato da <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> al termine delle operazioni di riproduzione del ciclo in ogni partizione. Il metodo <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> passa al delegato `Action<TLocal>` il valore finale della variabile partition-local per questa partizione del ciclo e l'utente fornisce il codice che esegue l'azione necessaria per la combinazione del risultato di questa partizione con i risultati delle altre partizioni. Questo delegato può essere chiamato simultaneamente da più attività. Per questo motivo, nell'esempio viene usato il metodo <xref:System.Threading.Interlocked.Add%28System.Int32%40%2CSystem.Int32%29?displayProperty=nameWithType> per sincronizzare l'accesso alla variabile `total`. Poiché il tipo del delegato è <xref:System.Action%601>, non viene restituito alcun valore.

[!code-csharp[TPL_Parallel#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/foreachthreadlocal.cs#04)]
[!code-vb[TPL_Parallel#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/foreachthreadlocal.vb#04)]

## <a name="see-also"></a>Vedere anche

- [Parallelismo dei dati](data-parallelism-task-parallel-library.md)
- [Procedura: Scrivere un ciclo Parallel.For con variabili di thread locali](how-to-write-a-parallel-for-loop-with-thread-local-variables.md)
- [Espressioni lambda in PLINQ e TPL](lambda-expressions-in-plinq-and-tpl.md)
