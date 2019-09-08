---
title: Esecuzione di query su dataset tipizzati
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: 55714c4dae73cd17a849cc35681797dfa4266e3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782973"
---
# <a name="query-typed-datasets"></a>Eseguire query su DataSet tipizzati

Se lo schema di <xref:System.Data.DataSet> è noto in fase di progettazione dell'applicazione, è consigliabile usare un oggetto tipizzato <xref:System.Data.DataSet> quando si usa LINQ to DataSet. Un oggetto <xref:System.Data.DataSet> tipizzato è una classe che deriva da <xref:System.Data.DataSet>un oggetto. In quanto tale, tale oggetto eredita tutti i metodi, gli eventi e le proprietà di un <xref:System.Data.DataSet>. Un oggetto tipizzato <xref:System.Data.DataSet> fornisce inoltre metodi, eventi e proprietà fortemente tipizzati. È quindi possibile accedere a tabelle e colonne in base al nome, anziché usare metodi basati su raccolta. Le query risultano quindi più semplici e più leggibili. Per altre informazioni, vedere [DataSet tipizzati](./dataset-datatable-dataview/typed-datasets.md).

LINQ to DataSet supporta anche l'esecuzione di query su <xref:System.Data.DataSet>un oggetto tipizzato. Con un oggetto <xref:System.Data.DataSet>tipizzato, non è necessario usare il metodo <xref:System.Data.DataRowExtensions.Field%2A> o <xref:System.Data.DataRowExtensions.SetField%2A> il metodo generico per accedere ai dati della colonna. I nomi delle proprietà sono disponibili in fase di compilazione perché le informazioni sul tipo <xref:System.Data.DataSet>sono incluse in. LINQ to DataSet fornisce l'accesso ai valori di colonna come tipo corretto, in modo che vengano rilevati errori di mancata corrispondenza del tipo quando il codice viene compilato anziché in fase di esecuzione.

Prima di iniziare a eseguire query su un <xref:System.Data.DataSet>oggetto tipizzato, è necessario generare la classe usando **Progettazione DataSet** in Visual Studio. Per altre informazioni, vedere [creare e configurare set](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)di dati.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrata una query su un oggetto <xref:System.Data.DataSet> tipizzato.

```csharp
var query = from o in orders
            where o.OnlineOrderFlag == true
            select new { o.SalesOrderID,
                         o.OrderDate,
                         o.SalesOrderNumber };

foreach(var order in query)
{
    Console.WriteLine("{0}\t{1:d}\t{2}",
      order.SalesOrderID,
      order.OrderDate,
      order.SalesOrderNumber);
}
```

```vb
Dim orders = ds.Tables("SalesOrderHeader")

Dim query = _
       From o In orders _
       Where o.OnlineOrderFlag = True _
       Select New {SalesOrderID := o.SalesOrderID, _
                   OrderDate := o.OrderDate, _
                   SalesOrderNumber := o.SalesOrderNumber}

For Each Dim onlineOrder In query
 Console.WriteLine("{0}\t{1:d}\t{2}", _
 onlineOrder.SalesOrderID, _
 onlineOrder.OrderDate, _
 onlineOrder.SalesOrderNumber)
Next
```

## <a name="see-also"></a>Vedere anche

- [Esecuzione di query su oggetti DataSet](querying-datasets-linq-to-dataset.md)
- [Query su tabella incrociata](cross-table-queries-linq-to-dataset.md)
- [Query su singola tabella](single-table-queries-linq-to-dataset.md)
