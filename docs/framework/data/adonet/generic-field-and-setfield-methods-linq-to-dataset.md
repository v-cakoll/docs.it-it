---
title: Metodi generici Field e SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: 7c7f1fef5d1fa575cd6d3bfdb7e6cbbea79ade28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086013"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Metodi generici Field e SetField (LINQ to DataSet)
In [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] sono disponibili metodi di estensione della classe <xref:System.Data.DataRow> per l'accesso ai valori di colonna: il metodo <xref:System.Data.DataRowExtensions.Field%2A> e il metodo <xref:System.Data.DataRowExtensions.SetField%2A>. Questi metodi semplificano l'accesso ai valori di colonna per gli sviluppatori, in particolare per quanto riguarda i valori Null. <xref:System.Data.DataSet> utilizza <xref:System.DBNull.Value> per rappresentare valori Null, mentre in [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] viene utilizzato il supporto dei tipi nullable introdotto in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]. Usando la funzione di accesso colonna preesistente in <xref:System.Data.DataRow> è necessario eseguire il cast dell'oggetto restituito nel tipo appropriato. Se un campo specifico in un <xref:System.Data.DataRow> può essere null, è necessario controllare in modo esplicito per un valore null perché la restituzione <xref:System.DBNull.Value> e in modo implicito il cast in un altro tipo genera un <xref:System.InvalidCastException>. Nell'esempio seguente, se il <xref:System.Data.DataRow.IsNull%2A> metodo non è stato usato per verificare la presenza di un valore null, verrà generata un'eccezione se l'indicizzatore restituisca <xref:System.DBNull.Value> e ha provato a eseguire il cast a un <xref:System.String>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Il metodo <xref:System.Data.DataRowExtensions.Field%2A> fornisce l'accesso ai valori di colonna di <xref:System.Data.DataRow> e <xref:System.Data.DataRowExtensions.SetField%2A> imposta i valori di colonna in <xref:System.Data.DataRow>. Poiché i metodi <xref:System.Data.DataRowExtensions.Field%2A> e <xref:System.Data.DataRowExtensions.SetField%2A> gestiscono tipi nullable, non è necessario verificare in modo esplicito la presenza di valori Null, a differenza dell'esempio precedente. Entrambi metodi sono inoltre generici, quindi non è necessario eseguire i cast del tipo restituito.  
  
 Nell'esempio seguente viene usato il metodo <xref:System.Data.DataRowExtensions.Field%2A>:  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Si noti che il tipo di dati specificato nel parametro `T` generico del metodo <xref:System.Data.DataRowExtensions.Field%2A> e del metodo <xref:System.Data.DataRowExtensions.SetField%2A> deve corrispondere al tipo del valore sottostante. In caso contrario, verrà generata un'eccezione <xref:System.InvalidCastException>. Il nome di colonna specificato deve inoltre corrispondere al nome di una colonna presente in <xref:System.Data.DataSet>; in caso contrario, verrà generata un'eccezione <xref:System.ArgumentException>. In entrambi casi, l'eccezione viene generata in fase di esecuzione durante l'enumerazione dei dati quando viene eseguita la query.  
  
 Il metodo <xref:System.Data.DataRowExtensions.SetField%2A> non esegue alcun tipo di conversione. Tuttavia, ciò non significa che non verrà eseguita una conversione del tipo. Il <xref:System.Data.DataRowExtensions.SetField%2A> metodo espone il [!INCLUDE[ado_whidbey_long](../../../../includes/ado-whidbey-long-md.md)] comportamento del <xref:System.Data.DataRow> classe. È possibile eseguire una conversione del tipo tramite il <xref:System.Data.DataRow> oggetto e il valore convertito verrebbero quindi salvate nel <xref:System.Data.DataRow> oggetto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataRowExtensions>
