---
title: 'Procedura: scorrere le directory dei file con PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
ms.openlocfilehash: 90afc767e422515c6122b8a6ef0e63ffc07caf3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091373"
---
# <a name="how-to-iterate-file-directories-with-plinq"></a>Procedura: scorrere le directory dei file con PLINQ
Questo esempio mostra due semplici modi per parallelizzare le operazioni su directory di file. La prima query usa il metodo <xref:System.IO.Directory.GetFiles%2A> per popolare una matrice di nomi di file in una directory e in tutte le sottodirectory. Questo metodo non restituisce alcun risultato finché non viene popolata l'intera matrice e di conseguenza può introdurre latenza all'inizio dell'operazione. Tuttavia, dopo che la matrice viene popolata, PLINQ può elaborarla in parallelo molto rapidamente.  
  
 La seconda query usa i metodi statici <xref:System.IO.Directory.EnumerateDirectories%2A> e <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, che iniziano a restituire risultati immediatamente. Questo approccio può rivelarsi più veloce quando si esegue l'iterazione di alberi di directory di grandi dimensioni, anche se i tempi di elaborazione rispetto al primo esempio possono dipendere da molti fattori.  
  
> [!WARNING]
> Lo scopo di questi esempi è mostrare l'utilizzo e la loro esecuzione potrebbe non essere più rapida della query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come eseguire l'iterazione di directory di file in semplici scenari quando si ha accesso a tutte le directory nell'albero, le dimensioni dei file non sono molto grandi e i tempi di accesso non sono significativi. Questo approccio comporta un periodo di latenza all'inizio, durante la creazione della matrice di nomi di file.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra come eseguire l'iterazione di directory di file in semplici scenari quando si ha accesso a tutte le directory nell'albero, le dimensioni dei file non sono molto grandi e i tempi di accesso non sono significativi. Questo approccio inizia a restituire risultati più rapidamente rispetto all'esempio precedente.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 Quando si usa <xref:System.IO.Directory.GetFiles%2A>, assicurarsi di avere autorizzazioni sufficienti per tutte le directory nell'albero. In caso contrario, verrà generata un'eccezione e non verrà restituito alcun risultato. Quando si usa <xref:System.IO.Directory.EnumerateDirectories%2A> in una query PLINQ, risulta problematico gestire le eccezioni di I/O in un modo appropriato che permetta di proseguire con l'iterazione. Se il codice deve gestire eccezioni di I/O o di accesso non autorizzato, è consigliabile provare l'approccio descritto in [Procedura: Eseguire l'iterazione di file di directory con la classe Parallel](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).  
  
 Se la latenza di I/O costituisce un problema, ad esempio con I/O di file in una rete, provare a usare una delle tecniche di I/O asincrono descritte in [Task Parallel Library e programmazione asincrona .NET Framework tradizionale](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) e in questo [post di blog](https://devblogs.microsoft.com/pfxteam/parallel-extensions-and-io/).  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
