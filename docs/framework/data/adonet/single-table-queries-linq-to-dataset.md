---
title: Query su singola tabella (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b74bcf8-3f87-449f-bff7-6bcb0d69d212
ms.openlocfilehash: 00b0773ba66ad8e0acfdccb37964030a9cacff52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61664168"
---
# <a name="single-table-queries-linq-to-dataset"></a>Query su singola tabella (LINQ to DataSet)
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] le query funzionano sulle origini dati che implementano il <xref:System.Collections.Generic.IEnumerable%601> interfaccia o <xref:System.Linq.IQueryable%601> interfaccia. Il <xref:System.Data.DataTable> classe non implementa entrambe le interfacce, è necessario chiamare il <xref:System.Data.DataTableExtensions.AsEnumerable%2A> metodo, se si desidera utilizzare il <xref:System.Data.DataTable> come origine nel `From` clausola di un [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] query.  
  
 Nell'esempio seguente vengono ottenuti tutti gli ordini online della tabella SalesOrderHeader e l'output costituito da ID ordine, data dell'ordine e numero di ordine viene inviato alla console.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)] 
  
 La query con variabili locale viene inizializzata con un'espressione di query, che opera su uno o più fonti di informazione applicando uno o più operatori di query da entrambi gli operatori query standard o, nel caso di [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], gli operatori specifici per il <xref:System.Data.DataSet>classe. Nell'espressione di query dell'esempio precedente vengono usati due operatori di query standard: `Where` e `Select`.  
  
 La clausola `Where` filtra la sequenza in base a una condizione, in questo caso che `OnlineOrderFlag` sia impostato su `true`. L'operatore `Select` alloca e restituisce un oggetto enumerabile che acquisisce gli argomenti passati all'operatore. Nell'esempio precedente viene creato un tipo anonimo con tre proprietà: `SalesOrderID`, `OrderDate` e `SalesOrderNumber`. I valori di queste tre proprietà vengono impostati sui valori delle colonne `SalesOrderID`, `OrderDate` e `SalesOrderNumber` della tabella `SalesOrderHeader`.  
  
 Il ciclo `foreach` enumera quindi gli oggetti enumerabili restituiti da `Select` e produce i risultati della query. Poiché la query è un tipo <xref:System.Linq.Enumerable>, che implementa <xref:System.Collections.Generic.IEnumerable%601>, la valutazione della query viene posticipata finché non viene eseguita un'iterazione della variabile di query in un ciclo `foreach`. La valutazione posticipata della query consente di mantenere le query come valori che è possibile valutare più volte, ogni volta con un risultato potenzialmente diverso.  
  
 Il metodo <xref:System.Data.DataRowExtensions.Field%2A> fornisce l'accesso ai valori di colonna di un oggetto <xref:System.Data.DataRow> e <xref:System.Data.DataRowExtensions.SetField%2A> (non illustrato nell'esempio precedente) imposta i valori di colonna in <xref:System.Data.DataRow>. Poiché i metodi <xref:System.Data.DataRowExtensions.Field%2A> e <xref:System.Data.DataRowExtensions.SetField%2A> gestiscono tipi nullable, non è necessario verificare in modo esplicito la presenza di valori Null. Entrambi metodi sono inoltre generici, quindi non è necessario eseguire i cast del tipo restituito. È possibile usare la funzione di accesso della colonna preesistente in <xref:System.Data.DataRow> (ad esempio, `o["OrderDate"]`), ma in questo caso è necessario eseguire il cast dell'oggetto restituito nel tipo appropriato.  Se la colonna è nullable, è necessario verificare se il valore è Null usando il metodo <xref:System.Data.DataRow.IsNull%2A>. Per altre informazioni, vedere [metodi generici Field e SetField](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md).  
  
 Si noti che il tipo di dati specificato nel parametro `T` generico del metodo <xref:System.Data.DataRowExtensions.Field%2A> e del metodo <xref:System.Data.DataRowExtensions.SetField%2A> deve corrispondere al tipo del valore sottostante; in caso contrario, verrà generata un'eccezione <xref:System.InvalidCastException>. Il nome di colonna specificato deve inoltre corrispondere al nome di una colonna presente in <xref:System.Data.DataSet>; in caso contrario, verrà generata un'eccezione <xref:System.ArgumentException>. In entrambi casi, l'eccezione viene generata in fase di esecuzione durante l'enumerazione dei dati quando viene eseguita la query.  
  
## <a name="see-also"></a>Vedere anche

- [Query su tabella incrociata](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [Esecuzione di query su oggetti DataSet tipizzati](../../../../docs/framework/data/adonet/querying-typed-datasets.md)
- [Metodi generici Field e SetField](../../../../docs/framework/data/adonet/generic-field-and-setfield-methods-linq-to-dataset.md)
