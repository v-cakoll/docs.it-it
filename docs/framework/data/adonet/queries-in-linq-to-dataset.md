---
title: Query in LINQ to DataSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c1a78fa8-9f0c-40bc-a372-5575a48708fe
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f41a55cce6834b58526c84d9a82fb38e10f46b42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="queries-in-linq-to-dataset"></a>Query in LINQ to DataSet
Una query è un'espressione che recupera dati da un'origine dati. Le query sono in genere espresse in un linguaggio di query specializzato, ad esempio SQL per i database relazionali e XQuery per XML. Gli sviluppatori hanno dovuto pertanto imparare un nuovo linguaggio di query per ogni tipo di origine dati o formato dati usato per le query. [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] offre un modello più semplice e coerente per l'uso dei dati con tutti i vari tipi di origini e formati dati. In una query [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] vengono sempre usati oggetti di programmazione.  
  
 Un'operazione di query [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] comporta tre azioni: recupero dell'origine o delle origini dati, creazione della query ed esecuzione della query.  
  
 Per eseguire query su origini dati che implementano l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601> è possibile usare [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)]. La chiamata <xref:System.Data.DataTableExtensions.AsEnumerable%2A> su un <xref:System.Data.DataTable> restituisce un oggetto che implementa l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601> interfaccia, che funge da origine dati per [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query.  
  
 Nella query è necessario specificare esattamente le informazioni che si desidera recuperare dall'origine dati. Una query può inoltre specificare in che modo ordinare, raggruppare e formattare le informazioni prima che vengano restituite. In [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] le query vengono archiviate nelle variabili. Se la query è progettata per restituire una sequenza di valori, la variabile di query stessa deve essere un tipo enumerabile. La variabile di query non esegue azioni né restituisce dati. Viene solo usata per archiviare le informazioni sulla query. Dopo aver creato una query è necessario eseguirla per recuperare eventuali dati.  
  
 In una query che restituisce una sequenza di valori, la variabile di query stessa non contiene mai i risultati della query ma viene usata solo per l'archiviazione dei comandi della query. L'esecuzione della query viene posticipata finché non viene eseguita un'iterazione della variabile di query in un ciclo `foreach` o `For Each`. Si tratta di *esecuzione posticipata*; ovvero, query viene eseguita qualche tempo dopo la query viene costruita. È quindi possibile eseguire una query il numero di volte desiderato. Tale caratteristica è utile, ad esempio, quando si dispone di un database che viene aggiornato da altre applicazioni. Nell'applicazione è possibile creare una query per recuperare le informazioni più recenti ed eseguire ripetutamente la query che restituisce ogni volta le informazioni aggiornate.  
  
 A differenza delle query posticipate che restituiscono una sequenza di valori, le query che restituiscono un valore singleton vengono eseguite immediatamente. Alcuni esempi di query singleton sono <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Average%2A> e <xref:System.Linq.Enumerable.First%2A>. Tali query vengono eseguite immediatamente perché i risultati restituiti sono necessari per calcolare il risultato singleton. Ad esempio, per individuare la media dei risultati della query, è necessario eseguire la query in modo che per la funzione di calcolo della media siano disponibili i dati di input. È inoltre possibile usare i metodi <xref:System.Linq.Enumerable.ToList%2A> o <xref:System.Linq.Enumerable.ToArray%2A> su una query per forzare l'esecuzione immediata di una query che non restituisce un valore singleton. Queste tecniche per forzare l'esecuzione immediata possono essere utili quando si desidera memorizzare nella cache i risultati di una query. Per ulteriori informazioni sull'esecuzione di query posticipata e immediata, vedere [Introduzione a LINQ](http://msdn.microsoft.com/en-us/6cc9af04-950a-4cc3-83d4-2aeb4abe4de9).  
  
## <a name="queries"></a>Query  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]è possibile formulare query in due diverse sintassi: espressione sintassi delle query e sintassi di query basate su metodo.  
  
### <a name="query-expression-syntax"></a>Sintassi delle espressioni di query  
 Le espressioni di query vengono scritte in una sintassi di query dichiarativa. Questa sintassi consente a un sviluppatore di scrivere query in C# o Visual Basic in un formato simile a quello di SQL. Tramite la sintassi delle espressioni di query è possibile eseguire anche complesse operazioni di filtro, ordinamento e raggruppamento sulle origini dati usando una quantità minima di codice. Per ulteriori informazioni, vedere [espressioni di Query LINQ](http://msdn.microsoft.com/library/40638f19-fb46-4d26-a2d9-a383b48f5ed4) e [operazioni di Query di base (Visual Basic)](~/docs/visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 La sintassi delle espressioni di query rappresenta una novità di C# 3.0 e [!INCLUDE[vb_orcas_long](../../../../includes/vb-orcas-long-md.md)]. Tuttavia, [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR) non è in grado di leggere da solo la sintassi delle espressioni di query. Pertanto, in fase di compilazione, le espressioni di query vengono convertite in chiamate al metodo in modo da poter essere usate da CLR. Questi metodi vengono definiti il *operatori di query standard*. Gli sviluppatori possono scegliere di chiamare direttamente questi metodi usando la relativa sintassi, anziché usare la sintassi delle query. Per altre informazioni, vedere [Sintassi di query e sintassi di metodi in LINQ](~/docs/csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md). Per ulteriori informazioni su come usare gli operatori query standard, vedere [NOT IN BUILD: Guida per programmatori LINQ generale](http://msdn.microsoft.com/en-us/609c7a6b-cbdd-429d-99f3-78d13d3bc049).  
  
 Nell'esempio seguente viene usato <xref:System.Linq.Enumerable.Select%2A> per restituire tutte le righe della tabella `Product` e visualizzare i nomi di prodotto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="method-based-query-syntax"></a>Sintassi delle query basate su metodo  
 Per formulare query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], è inoltre possibile usare query basate su metodo. La sintassi delle query basate su metodo è costituita da una sequenza di chiamate dirette del metodo ai metodi dell'operatore [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], in cui come parametri vengono passate espressioni lambda. Per altre informazioni, vedere [Espressioni lambda](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 In questo esempio viene usato <xref:System.Linq.Enumerable.Select%2A> per restituire tutte le righe di `Product` e visualizzare i nomi di prodotto.  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="composing-queries"></a>Composizione di query  
 Come già detto in precedenza in questo argomento, la variabile di query viene usata solo per archiviare i comandi della query quando questa viene progettata in modo da restituire una sequenza di valori. Se la query non contiene un metodo che causa l'esecuzione immediata, l'esecuzione effettiva della query viene posticipata finché non si esegue un'iterazione sulla variabile di query in un ciclo `foreach` o `For Each`. L'esecuzione posticipata consente di combinare più query o di estendere una query. Una query estesa viene modificata in modo da includere nuove operazioni. Le modifiche verranno quindi riflesse nell'eventuale esecuzione. Nell'esempio seguente la prima query restituisce tutti i prodotti. La seconda query estende la prima usando `Where` per restituire tutti i prodotti di taglia "L":  
  
 [!code-csharp[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#composing)]
 [!code-vb[DP LINQ to DataSet Examples#Composing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#composing)]  
  
 Dopo aver eseguito una query, non è possibile comporre query aggiuntive e per tutte le query successive verranno usati gli operatori [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] in memoria. La query verrà eseguita quando esegue un'iterazione sulla variabile di query in un `foreach` o `For Each` istruzione, o da una chiamata a uno del [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] gli operatori di conversione che causano l'esecuzione immediata. Tali operatori includono: <xref:System.Linq.Enumerable.ToList%2A>, <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToLookup%2A> e <xref:System.Linq.Enumerable.ToDictionary%2A>.  
  
 Nell'esempio seguente la prima query restituisce tutti i prodotti ordinati in base al prezzo di listino. Viene usato il metodo <xref:System.Linq.Enumerable.ToArray%2A> per forzare l'esecuzione immediata della query:  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray2)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)  
 [Esecuzione di query su oggetti DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [Nozioni di base su LINQ in C#](~/docs/csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Introduzione a LINQ in Visual Basic](~/docs/visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
