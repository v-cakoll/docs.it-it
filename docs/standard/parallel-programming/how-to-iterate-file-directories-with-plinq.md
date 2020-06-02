---
title: 'Procedura: Scorrere le directory dei file con PLINQ'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
ms.openlocfilehash: abf31ea69af6a85140efb783959a9a586ef6a59e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84277999"
---
# <a name="how-to-iterate-file-directories-with-plinq"></a>Procedura: Scorrere le directory dei file con PLINQ

Questo articolo illustra due modi per parallelizzare le operazioni sulle directory di file. La prima query usa il metodo <xref:System.IO.Directory.GetFiles%2A> per popolare una matrice di nomi di file in una directory e in tutte le sottodirectory. Questo metodo può introdurre una latenza all'inizio dell'operazione, perché non restituisce un risultato fino a quando non viene popolata l'intera matrice. Tuttavia, dopo che la matrice è stata popolata, PLINQ può elaborarla in parallelo in modo rapido.  
  
La seconda query usa i <xref:System.IO.Directory.EnumerateDirectories%2A> metodi statici e <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> , che iniziano a restituire immediatamente i risultati. Questo approccio può essere più veloce quando si esegue l'iterazione in alberi di directory di grandi dimensioni, ma il tempo di elaborazione rispetto al primo esempio dipende da molti fattori.  
  
> [!NOTE]
> Questi esempi hanno lo scopo di illustrare l'utilizzo e potrebbero non essere eseguiti più velocemente rispetto alla query LINQ to Objects sequenziale equivalente. Per altre informazioni sull'aumento di velocità, vedere [Informazioni sull'aumento di velocità in PLINQ](understanding-speedup-in-plinq.md).  
  
## <a name="getfiles-example"></a>Esempio di GetFiles

 Questo esempio illustra come eseguire l'iterazione su directory di file in semplici scenari quando si ha accesso a tutte le directory nell'albero, le dimensioni dei file non sono grandi e i tempi di accesso non sono significativi. Questo approccio comporta un periodo di latenza all'inizio, durante la creazione della matrice di nomi di file.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="enumeratefiles-example"></a>Esempio di EnumerateFiles

 Questo esempio illustra come eseguire l'iterazione su directory di file in semplici scenari quando si ha accesso a tutte le directory nell'albero, le dimensioni dei file non sono grandi e i tempi di accesso non sono significativi. Questo approccio inizia a restituire risultati più rapidamente rispetto all'esempio precedente.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 Quando si usa <xref:System.IO.Directory.GetFiles%2A>, assicurarsi di avere autorizzazioni sufficienti per tutte le directory nell'albero. In caso contrario, verrà generata un'eccezione e non verrà restituito alcun risultato. Quando si usa <xref:System.IO.Directory.EnumerateDirectories%2A> in una query PLINQ, risulta problematico gestire le eccezioni di I/O in un modo appropriato che permetta di proseguire con l'iterazione. Se il codice deve gestire eccezioni di I/O o di accesso non autorizzato, è consigliabile provare l'approccio descritto in [Procedura: Eseguire l'iterazione di file di directory con la classe Parallel](how-to-iterate-file-directories-with-the-parallel-class.md).  
  
 Se la latenza di I/O costituisce un problema, ad esempio con I/O di file in una rete, provare a usare una delle tecniche di I/O asincrono descritte in [Task Parallel Library e programmazione asincrona .NET Framework tradizionale](tpl-and-traditional-async-programming.md) e in questo [post di blog](https://devblogs.microsoft.com/pfxteam/parallel-extensions-and-io/).  
  
## <a name="see-also"></a>Vedere anche

- [Parallel LINQ (PLINQ)](introduction-to-plinq.md)
