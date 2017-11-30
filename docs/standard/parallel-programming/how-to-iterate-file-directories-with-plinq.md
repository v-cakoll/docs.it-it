---
title: 'Procedura: scorrere le directory dei file con PLINQ'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: PLINQ queries, how to iterate directories
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 40fd9f64b5702f5205b7817f3de1e0a8709c5a63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-iterate-file-directories-with-plinq"></a>Procedura: scorrere le directory dei file con PLINQ
Questo esempio mostra due semplici modi di parallelizzare le operazioni sulle directory di file. La prima query utilizza la <xref:System.IO.Directory.GetFiles%2A> metodo per inserire una matrice di nomi di file in una directory e tutte le sottodirectory. Questo metodo non restituisce fino a quando non viene popolata l'intera matrice e pertanto può introdurre latenza all'inizio dell'operazione. Tuttavia, dopo la matrice viene compilata, PLINQ possibile elaborarlo in parallelo molto rapidamente.  
  
 La seconda query utilizza il metodo statico <xref:System.IO.Directory.EnumerateDirectories%2A> e <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> metodi con cui iniziano a restituire immediatamente i risultati. Questo approccio può essere più veloce quando si scorrono le strutture di directory di grandi dimensioni, anche se il tempo di elaborazione rispetto al primo esempio può dipendere da molti fattori.  
  
> [!WARNING]
>  Questi esempi servono a illustrare l'utilizzo e potrebbero non essere eseguito più velocemente rispetto a LINQ sequenziali equivalenti alla query di oggetti. Per ulteriori informazioni sull'aumento di velocità, vedere [comprensione aumento di velocità in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come scorrere le directory di file in scenari semplici quando è possibile accedere a tutte le directory la struttura ad albero, le dimensioni dei file non sono molto grandi e i tempi di accesso non sono significativi. Questo approccio prevede un periodo di latenza all'inizio, mentre la matrice di nomi di file viene creata.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come scorrere le directory di file in scenari semplici quando è possibile accedere a tutte le directory la struttura ad albero, le dimensioni dei file non sono molto grandi e i tempi di accesso non sono significativi. Questo approccio inizia producono risultati più velocemente rispetto all'esempio precedente.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 Quando si utilizza <xref:System.IO.Directory.GetFiles%2A>, assicurarsi di disporre di autorizzazioni sufficienti per tutte le directory nella struttura. In caso contrario verrà generata un'eccezione e verrà restituito alcun risultato. Quando si utilizza il <xref:System.IO.Directory.EnumerateDirectories%2A> in una query PLINQ, risulta problematico per gestire le eccezioni dei / o in un modo che consente di continuare l'esecuzione di iterazioni. Se il codice deve gestire eccezioni di accesso non autorizzato o i/o, quindi è necessario considerare l'approccio descritto in [procedura: scorrere le directory di File con la classe Parallel](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).  
  
 Se la latenza dei / o è un problema, ad esempio con i/o file in una rete, è consigliabile utilizzare una delle tecniche dei / o asincrone descritti in [TPL e .NET Framework programmazione asincrona tradizionale](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) e in questo [post di blog ](http://go.microsoft.com/fwlink/?LinkID=186458).  
  
## <a name="see-also"></a>Vedere anche  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
