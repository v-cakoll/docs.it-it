---
title: Metodi generici Field e SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: 310eb3ccecc3159234ed362ed044be7ad704dde4
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634833"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Metodi generici Field e SetField (LINQ to DataSet)
LINQ to DataSet fornisce metodi di estensione alla classe <xref:System.Data.DataRow> per l'accesso ai valori di colonna: il metodo <xref:System.Data.DataRowExtensions.Field%2A> e il metodo <xref:System.Data.DataRowExtensions.SetField%2A>. Questi metodi semplificano l'accesso ai valori di colonna per gli sviluppatori, in particolare per quanto riguarda i valori Null. Il <xref:System.Data.DataSet> utilizza <xref:System.DBNull.Value?displayProperty=nameWithType> per rappresentare i valori null, mentre LINQ utilizza i tipi di <xref:System.Nullable> e <xref:System.Nullable%601>. Per utilizzare la funzione di accesso di colonna preesistente in <xref:System.Data.DataRow>, è necessario eseguire il cast dell'oggetto restituito al tipo appropriato. Se un campo specifico in un <xref:System.Data.DataRow> può essere null, è necessario verificare in modo esplicito la presenza di un valore null perché la restituzione di <xref:System.DBNull.Value?displayProperty=nameWithType> e il cast implicito a un altro tipo genera un <xref:System.InvalidCastException>. Nell'esempio seguente, se il metodo <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> non è stato usato per verificare la presenza di un valore null, viene generata un'eccezione se l'indicizzatore ha restituito <xref:System.DBNull.Value?displayProperty=nameWithType> e ha tentato di eseguirne il cast a un <xref:System.String>.  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Il metodo <xref:System.Data.DataRowExtensions.Field%2A> fornisce l'accesso ai valori di colonna di <xref:System.Data.DataRow> e <xref:System.Data.DataRowExtensions.SetField%2A> imposta i valori di colonna in <xref:System.Data.DataRow>. Poiché i metodi <xref:System.Data.DataRowExtensions.Field%2A> e <xref:System.Data.DataRowExtensions.SetField%2A> gestiscono tipi nullable, non è necessario verificare in modo esplicito la presenza di valori Null, a differenza dell'esempio precedente. Entrambi metodi sono inoltre generici, quindi non è necessario eseguire i cast del tipo restituito.  
  
 Nell'esempio seguente viene usato il metodo <xref:System.Data.DataRowExtensions.Field%2A>:  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Si noti che il tipo di dati specificato nel parametro `T` generico del metodo <xref:System.Data.DataRowExtensions.Field%2A> e del metodo <xref:System.Data.DataRowExtensions.SetField%2A> deve corrispondere al tipo del valore sottostante. In caso contrario, verrà generata un'eccezione <xref:System.InvalidCastException>. Il nome di colonna specificato deve inoltre corrispondere al nome di una colonna presente in <xref:System.Data.DataSet>; in caso contrario, verrà generata un'eccezione <xref:System.ArgumentException>. In entrambi casi, l'eccezione viene generata in fase di esecuzione durante l'enumerazione dei dati quando viene eseguita la query.  
  
 Il metodo <xref:System.Data.DataRowExtensions.SetField%2A> non esegue alcun tipo di conversione. Tuttavia, ciò non significa che non verrà eseguita una conversione del tipo. Il metodo <xref:System.Data.DataRowExtensions.SetField%2A> espone il comportamento ADO.NET della classe <xref:System.Data.DataRow>. Una conversione di tipo può essere eseguita dall'oggetto <xref:System.Data.DataRow> e il valore convertito verrebbe quindi salvato nell'oggetto <xref:System.Data.DataRow>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataRowExtensions>
