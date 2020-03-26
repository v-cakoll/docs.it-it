---
title: Metodi generici Field e SetField (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1883365f-9d6c-4ccb-9187-df309f47706d
ms.openlocfilehash: d7ddee775e91c6be6166a091997afd58113cfe6b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249103"
---
# <a name="generic-field-and-setfield-methods-linq-to-dataset"></a>Metodi generici Field e SetField (LINQ to DataSet)
LINQ to DataSet LINQ <xref:System.Data.DataRow> to DataSet fornisce metodi <xref:System.Data.DataRowExtensions.Field%2A> di <xref:System.Data.DataRowExtensions.SetField%2A> estensione alla classe per l'accesso ai valori di colonna: il metodo e il metodo. Questi metodi semplificano l'accesso ai valori di colonna per gli sviluppatori, in particolare per quanto riguarda i valori Null. Utilizza <xref:System.Data.DataSet> <xref:System.DBNull.Value?displayProperty=nameWithType> per rappresentare valori null, <xref:System.Nullable> <xref:System.Nullable%601> mentre LINQ usa i tipi e . L'utilizzo della funzione di <xref:System.Data.DataRow> accesso di colonna preesistente in richiede il cast dell'oggetto restituito al tipo appropriato. Se un determinato <xref:System.Data.DataRow> campo in un oggetto può essere null, <xref:System.DBNull.Value?displayProperty=nameWithType> è necessario verificare in modo <xref:System.InvalidCastException>esplicito la presenza di un valore null perché la restituzione e il cast implicito a un altro tipo genera un'eccezione . Nell'esempio seguente, <xref:System.Data.DataRow.IsNull%2A?displayProperty=nameWithType> se il metodo non è stato utilizzato per verificare la presenza <xref:System.DBNull.Value?displayProperty=nameWithType> di un valore <xref:System.String>null, verrebbe generata un'eccezione se l'indicizzatore restituisse e tentasse di eseguire il cast a un oggetto .  
  
 [!code-csharp[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#whereisnull)]
 [!code-vb[DP LINQ to DataSet Examples#WhereIsNull](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#whereisnull)]  
  
 Il metodo <xref:System.Data.DataRowExtensions.Field%2A> fornisce l'accesso ai valori di colonna di <xref:System.Data.DataRow> e <xref:System.Data.DataRowExtensions.SetField%2A> imposta i valori di colonna in <xref:System.Data.DataRow>. Sia <xref:System.Data.DataRowExtensions.Field%2A> il <xref:System.Data.DataRowExtensions.SetField%2A> metodo che il metodo gestiscono i tipi di valore nullable, pertanto non è necessario controllare in modo esplicito i valori null come nell'esempio precedente. Entrambi metodi sono inoltre generici, quindi non è necessario eseguire i cast del tipo restituito.  
  
 Nell'esempio seguente viene usato il metodo <xref:System.Data.DataRowExtensions.Field%2A>:  
  
 [!code-csharp[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#where3)]
 [!code-vb[DP LINQ to DataSet Examples#Where3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#where3)]  
  
 Si noti che il tipo di dati specificato nel parametro `T` generico del metodo <xref:System.Data.DataRowExtensions.Field%2A> e del metodo <xref:System.Data.DataRowExtensions.SetField%2A> deve corrispondere al tipo del valore sottostante. In caso contrario, verrà generata un'eccezione <xref:System.InvalidCastException>. Il nome di colonna specificato deve inoltre corrispondere al nome di una colonna presente in <xref:System.Data.DataSet>; in caso contrario, verrà generata un'eccezione <xref:System.ArgumentException>. In entrambi casi, l'eccezione viene generata in fase di esecuzione durante l'enumerazione dei dati quando viene eseguita la query.  
  
 Il metodo <xref:System.Data.DataRowExtensions.SetField%2A> non esegue alcun tipo di conversione. Tuttavia, ciò non significa che non verrà eseguita una conversione del tipo. Il <xref:System.Data.DataRowExtensions.SetField%2A> metodo espone il ADO.NET <xref:System.Data.DataRow> comportamento della classe. Una conversione del tipo <xref:System.Data.DataRow> può essere eseguita dall'oggetto <xref:System.Data.DataRow> e il valore convertito viene quindi salvato nell'oggetto.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataRowExtensions>
