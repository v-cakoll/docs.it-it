---
title: Query in LINQ to DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c1a78fa8-9f0c-40bc-a372-5575a48708fe
ms.openlocfilehash: 092dbb5227e5f9e0ae2a62656a300d2367bcf16b
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634794"
---
# <a name="queries-in-linq-to-dataset"></a>Query in LINQ to DataSet
Una query è un'espressione che recupera dati da un'origine dati. Le query sono in genere espresse in un linguaggio di query specializzato, ad esempio SQL per i database relazionali e XQuery per XML. Gli sviluppatori hanno dovuto pertanto imparare un nuovo linguaggio di query per ogni tipo di origine dati o formato dati usato per le query. LINQ (Language-Integrated Query) offre un modello più semplice e coerente per l'uso di dati in diversi tipi di origini dati e formati di dati. In una query LINQ vengono sempre usati oggetti di programmazione.  
  
 Un'operazione di query LINQ comporta tre azioni: il recupero di una o più origini dati, la creazione della query e l'esecuzione della query.  
  
 È possibile eseguire query su origini dati che implementano l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601> tramite LINQ. La chiamata di <xref:System.Data.DataTableExtensions.AsEnumerable%2A> su un <xref:System.Data.DataTable> restituisce un oggetto che implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>, che funge da origine dati per le query LINQ to DataSet.  
  
 Nella query è necessario specificare esattamente le informazioni che si desidera recuperare dall'origine dati. Una query può inoltre specificare in che modo ordinare, raggruppare e formattare le informazioni prima che vengano restituite. In LINQ una query viene archiviata in una variabile. Se la query è progettata per restituire una sequenza di valori, la variabile di query stessa deve essere un tipo enumerabile. La variabile di query non esegue azioni né restituisce dati. Viene solo usata per archiviare le informazioni sulla query. Dopo aver creato una query è necessario eseguirla per recuperare eventuali dati.  
  
 In una query che restituisce una sequenza di valori, la variabile di query stessa non contiene mai i risultati della query ma viene usata solo per l'archiviazione dei comandi della query. L'esecuzione della query viene posticipata finché non viene eseguita un'iterazione della variabile di query in un ciclo `foreach` o `For Each`. Questa operazione è denominata *esecuzione posticipata*; in altre termini, l'esecuzione della query viene eseguita un po' di tempo dopo la costruzione della query. È quindi possibile eseguire una query il numero di volte desiderato. Tale caratteristica è utile, ad esempio, quando si dispone di un database che viene aggiornato da altre applicazioni. Nell'applicazione è possibile creare una query per recuperare le informazioni più recenti ed eseguire ripetutamente la query che restituisce ogni volta le informazioni aggiornate.  
  
 A differenza delle query posticipate che restituiscono una sequenza di valori, le query che restituiscono un valore singleton vengono eseguite immediatamente. Alcuni esempi di query singleton sono <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Average%2A> e <xref:System.Linq.Enumerable.First%2A>. Tali query vengono eseguite immediatamente perché i risultati restituiti sono necessari per calcolare il risultato singleton. Ad esempio, per individuare la media dei risultati della query, è necessario eseguire la query in modo che per la funzione di calcolo della media siano disponibili i dati di input. È inoltre possibile usare i metodi <xref:System.Linq.Enumerable.ToList%2A> o <xref:System.Linq.Enumerable.ToArray%2A> su una query per forzare l'esecuzione immediata di una query che non restituisce un valore singleton. Queste tecniche per forzare l'esecuzione immediata possono essere utili quando si desidera memorizzare nella cache i risultati di una query.
  
## <a name="queries"></a>Query  
 LINQ to DataSet le query possono essere formulate in due diverse sintassi: la sintassi delle espressioni di query e la sintassi delle query basate su metodo.  
  
### <a name="query-expression-syntax"></a>Sintassi di espressione della query  
 Le espressioni di query vengono scritte in una sintassi di query dichiarativa. Questa sintassi consente a un sviluppatore di scrivere query in C# o Visual Basic in un formato simile a quello di SQL. Tramite la sintassi delle espressioni di query è possibile eseguire anche complesse operazioni di filtro, ordinamento e raggruppamento sulle origini dati usando una quantità minima di codice. Per altre informazioni, vedere [espressioni di query LINQ](../../../csharp/linq/index.md#query-expression-overview) e [operazioni di query di base (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).
  
 Il .NET Framework Common Language Runtime (CLR) non è in grado di leggere la sintassi delle espressioni di query. Pertanto, in fase di compilazione, le espressioni di query vengono convertite in chiamate al metodo in modo da poter essere usate da CLR. Questi metodi sono detti *operatori di query standard*. Gli sviluppatori possono scegliere di chiamare direttamente questi metodi usando la relativa sintassi, anziché usare la sintassi delle query. Per altre informazioni, vedere [Sintassi di query e sintassi di metodi in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md). Per ulteriori informazioni sugli operatori di query standard, vedere [Cenni preliminari sugli operatori di query standard](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
 Nell'esempio seguente viene usato <xref:System.Linq.Enumerable.Select%2A> per restituire tutte le righe della tabella `Product` e visualizzare i nomi di prodotto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="method-based-query-syntax"></a>Sintassi delle query basate su metodo  
 L'altro modo per formulare query LINQ to DataSet consiste nell'usare query basate su metodo. La sintassi delle query basate su metodo è una sequenza di chiamate dirette ai metodi degli operatori LINQ, che passano espressioni lambda come parametri. Per altre informazioni, vedere [Espressioni lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 In questo esempio viene usato <xref:System.Linq.Enumerable.Select%2A> per restituire tutte le righe di `Product` e visualizzare i nomi di prodotto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="composing-queries"></a>Composizione di query  
 Come già detto in precedenza in questo argomento, la variabile di query viene usata solo per archiviare i comandi della query quando questa viene progettata in modo da restituire una sequenza di valori. Se la query non contiene un metodo che causa l'esecuzione immediata, l'esecuzione effettiva della query viene posticipata finché non si esegue un'iterazione sulla variabile di query in un ciclo `foreach` o `For Each`. L'esecuzione posticipata consente di combinare più query o di estendere una query. Una query estesa viene modificata in modo da includere nuove operazioni. Le modifiche verranno quindi riflesse nell'eventuale esecuzione. Nell'esempio seguente la prima query restituisce tutti i prodotti. La seconda query estende la prima usando `Where` per restituire tutti i prodotti di taglia "L":  
  
 [!code-csharp[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#composing)]
 [!code-vb[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#composing)]  
  
 Dopo l'esecuzione di una query, non è possibile comporre altre query e tutte le query successive utilizzeranno gli operatori LINQ in memoria. L'esecuzione della query verrà eseguita quando si scorre la variabile di query in un'istruzione `foreach` o `For Each` oppure mediante una chiamata a uno degli operatori di conversione LINQ che provocano l'esecuzione immediata. Tali operatori includono: <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToLookup%2A> e <xref:System.Linq.Enumerable.ToDictionary%2A>.  
  
 Nell'esempio seguente la prima query restituisce tutti i prodotti ordinati in base al prezzo di listino. Viene usato il metodo <xref:System.Linq.Enumerable.ToArray%2A> per forzare l'esecuzione immediata della query:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray2)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray2)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori](programming-guide-linq-to-dataset.md)
- [Esecuzione di query su oggetti DataSet](querying-datasets-linq-to-dataset.md)
- [Nozioni di base su LINQ in C#](../../../csharp/programming-guide/concepts/linq/index.md)
- [Introduzione a LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
