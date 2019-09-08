---
title: Query su singola tabella (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b74bcf8-3f87-449f-bff7-6bcb0d69d212
ms.openlocfilehash: 8807125bd61c71217ca96f3b5a38148ed100073b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794369"
---
# <a name="single-table-queries-linq-to-dataset"></a>Query su singola tabella (LINQ to DataSet)
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]le query funzionano su origini dati che implementano l' <xref:System.Collections.Generic.IEnumerable%601> interfaccia o l' <xref:System.Linq.IQueryable%601> interfaccia. La <xref:System.Data.DataTable> classe non implementa alcuna interfaccia, pertanto è necessario chiamare il <xref:System.Data.DataTableExtensions.AsEnumerable%2A> metodo se <xref:System.Data.DataTable> si desidera utilizzare come origine nella `From` clausola di una [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] query.  
  
 Nell'esempio seguente vengono ottenuti tutti gli ordini online della tabella SalesOrderHeader e l'output costituito da ID ordine, data dell'ordine e numero di ordine viene inviato alla console.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where1)]  
 [!code-vb[DP LINQ to DataSet Examples#Where1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where1)] 
  
 La query della variabile locale viene inizializzata con un'espressione di query che opera su una o più origini informazioni applicando uno o più operatori di query dagli operatori di query standard o, nel caso di LINQ to DataSet, operatori specifici del <xref:System.Data.DataSet>classe. Nell'espressione di query dell'esempio precedente vengono usati due operatori di query standard: `Where` e `Select`.  
  
 La clausola `Where` filtra la sequenza in base a una condizione, in questo caso che `OnlineOrderFlag` sia impostato su `true`. L'operatore `Select` alloca e restituisce un oggetto enumerabile che acquisisce gli argomenti passati all'operatore. Nell'esempio precedente viene creato un tipo anonimo con tre proprietà: `SalesOrderID`, `OrderDate` e `SalesOrderNumber`. I valori di queste tre proprietà vengono impostati sui valori delle colonne `SalesOrderID`, `OrderDate` e `SalesOrderNumber` della tabella `SalesOrderHeader`.  
  
 Il ciclo `foreach` enumera quindi gli oggetti enumerabili restituiti da `Select` e produce i risultati della query. Poiché la query è un tipo <xref:System.Linq.Enumerable>, che implementa <xref:System.Collections.Generic.IEnumerable%601>, la valutazione della query viene posticipata finché non viene eseguita un'iterazione della variabile di query in un ciclo `foreach`. La valutazione posticipata della query consente di mantenere le query come valori che è possibile valutare più volte, ogni volta con un risultato potenzialmente diverso.  
  
 Il metodo <xref:System.Data.DataRowExtensions.Field%2A> fornisce l'accesso ai valori di colonna di un oggetto <xref:System.Data.DataRow> e <xref:System.Data.DataRowExtensions.SetField%2A> (non illustrato nell'esempio precedente) imposta i valori di colonna in <xref:System.Data.DataRow>. Poiché i metodi <xref:System.Data.DataRowExtensions.Field%2A> e <xref:System.Data.DataRowExtensions.SetField%2A> gestiscono tipi nullable, non è necessario verificare in modo esplicito la presenza di valori Null. Entrambi metodi sono inoltre generici, quindi non è necessario eseguire i cast del tipo restituito. È possibile usare la funzione di accesso della colonna preesistente in <xref:System.Data.DataRow> (ad esempio, `o["OrderDate"]`), ma in questo caso è necessario eseguire il cast dell'oggetto restituito nel tipo appropriato.  Se la colonna è nullable, è necessario verificare se il valore è Null usando il metodo <xref:System.Data.DataRow.IsNull%2A>. Per altre informazioni, vedere [Metodi Field e Sefield generici](generic-field-and-setfield-methods-linq-to-dataset.md).  
  
 Si noti che il tipo di dati specificato nel parametro `T` generico del metodo <xref:System.Data.DataRowExtensions.Field%2A> e del metodo <xref:System.Data.DataRowExtensions.SetField%2A> deve corrispondere al tipo del valore sottostante; in caso contrario, verrà generata un'eccezione <xref:System.InvalidCastException>. Il nome di colonna specificato deve inoltre corrispondere al nome di una colonna presente in <xref:System.Data.DataSet>; in caso contrario, verrà generata un'eccezione <xref:System.ArgumentException>. In entrambi casi, l'eccezione viene generata in fase di esecuzione durante l'enumerazione dei dati quando viene eseguita la query.  
  
## <a name="see-also"></a>Vedere anche

- [Query su tabella incrociata](cross-table-queries-linq-to-dataset.md)
- [Esecuzione di query su oggetti DataSet tipizzati](querying-typed-datasets.md)
- [Metodi generici Field e SetField](generic-field-and-setfield-methods-linq-to-dataset.md)
