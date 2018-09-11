---
title: Esecuzione di query su dataset tipizzati
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2018
ms.locfileid: "44270642"
---
# <a name="query-typed-datasets"></a>Eseguire query sui set di dati tipizzati

Se lo schema del <xref:System.Data.DataSet> è noto in fase di progettazione dell'applicazione, è consigliabile usare un oggetto tipizzato <xref:System.Data.DataSet> quando si usa LINQ to DataSet. Un oggetto tipizzato <xref:System.Data.DataSet> è una classe che deriva da un <xref:System.Data.DataSet>. In quanto tale, tale oggetto eredita tutti i metodi, gli eventi e le proprietà di un <xref:System.Data.DataSet>. Inoltre, un oggetto tipizzato <xref:System.Data.DataSet> fornisce metodi fortemente tipizzati, proprietà ed eventi. È quindi possibile accedere a tabelle e colonne in base al nome, anziché usare metodi basati su raccolta. Le query risultano quindi più semplici e più leggibili. Per altre informazioni, vedere [dataset tipizzati](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).

LINQ to DataSet supporta anche l'esecuzione di query su un oggetto tipizzato <xref:System.Data.DataSet>. Con un oggetto tipizzato <xref:System.Data.DataSet>, non è necessario utilizzare il tipo generico <xref:System.Data.DataRowExtensions.Field%2A> metodo o <xref:System.Data.DataRowExtensions.SetField%2A> metodo per accedere ai dati di colonna. I nomi delle proprietà sono disponibili in fase di compilazione perché le informazioni sul tipo è incluso nel <xref:System.Data.DataSet>. LINQ to DataSet fornisce accesso ai valori di colonna con il tipo corretto, in modo che gli errori di mancata corrispondenza di tipo vengono intercettati durante la compilazione del codice anziché in fase di esecuzione.

Prima di iniziare l'esecuzione di query tipizzati <xref:System.Data.DataSet>, è necessario generare la classe usando il **Progettazione DataSet** in Visual Studio. Per altre informazioni, vedere [creare e configurare i set di dati](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).

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

- [Esecuzione di query su oggetti DataSet](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [Query su tabella incrociata](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [Query su singola tabella](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
