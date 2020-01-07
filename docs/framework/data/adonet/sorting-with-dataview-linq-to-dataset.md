---
title: Ordinamento con DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
ms.openlocfilehash: 2998de7dee34f9b5410bfe53988e0b7cfa797784
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634755"
---
# <a name="sorting-with-dataview-linq-to-dataset"></a>Ordinamento con DataView (LINQ to DataSet)
La possibilità di ordinare i dati in base a criteri specifici e quindi di presentarli a un client tramite un controllo dell'interfaccia utente rappresenta un aspetto importante dell'associazione dati. Con <xref:System.Data.DataView> è possibile ordinare i dati e restituire righe di dati ordinate in base a criteri specifici in diversi modi. Oltre alle funzionalità di ordinamento basate su stringa, <xref:System.Data.DataView> consente inoltre di utilizzare espressioni LINQ (Language Integrated Query) per i criteri di ordinamento. Le espressioni LINQ consentono operazioni di ordinamento molto più complesse e potenti rispetto all'ordinamento basato su stringa. In questo argomento vengono descritti entrambi gli approcci all'ordinamento tramite <xref:System.Data.DataView>.  
  
## <a name="creating-dataview-from-a-query-with-sorting-information"></a>Creazione di DataView da una query con informazioni di ordinamento  
 Un oggetto <xref:System.Data.DataView> può essere creato da una query LINQ to DataSet. Se la query contiene una clausola <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.ThenBy%2A>o <xref:System.Linq.Enumerable.ThenByDescending%2A> le espressioni in queste clausole vengono utilizzate come base per l'ordinamento dei dati nella <xref:System.Data.DataView>. Se ad esempio la query contiene le clausole `Order By…`e `Then By…`, il <xref:System.Data.DataView> risultante Ordina i dati in base a entrambe le colonne specificate.  
  
 L'ordinamento basato su espressione è più potente e complesso rispetto a quello più semplice basato su stringa. Notare che l'ordinamento basato su stringa e l'ordinamento basato su espressione si escludono a vicenda. Se si imposta un oggetto <xref:System.Data.DataView.Sort%2A> basato su stringa dopo la creazione di un oggetto <xref:System.Data.DataView> da una query, il filtro basato sull'espressione dedotto dalla query viene cancellato e non può essere ripristinato.  
  
 L'indice relativo a un oggetto <xref:System.Data.DataView> viene compilato sia quando si crea <xref:System.Data.DataView> che quando si modifica una qualsiasi delle informazioni relative all'ordinamento o al filtraggio. Per ottenere prestazioni ottimali, è possibile specificare criteri di ordinamento nella query LINQ to DataSet dalla quale viene creata la <xref:System.Data.DataView> e non modificare le informazioni di ordinamento in un secondo momento. Per altre informazioni, vedere [prestazioni di DataView](dataview-performance.md).  
  
> [!NOTE]
> Nella maggior parte dei casi le espressioni usate per l'ordinamento non devono presentare effetti collaterali e devono essere deterministiche. Le espressioni non devono inoltre contenere eventuale codice che dipende da un numero impostato di esecuzioni perché è possibile che le operazioni di ordinamento vengano eseguite un numero qualsiasi di volte.  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita una query sulla tabella SalesOrderHeader e le righe restituite vengono ordinate in base alla data dell'ordine. Viene quindi creato un oggetto <xref:System.Data.DataView> dalla query e l'oggetto <xref:System.Data.DataView> viene infine associato a <xref:System.Windows.Forms.BindingSource>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby)]  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita una query sulla tabella SalesOrderHeader e le righe restituite vengono ordinate in base all'importo totale dovuto. Viene quindi creato un oggetto <xref:System.Data.DataView> dalla query e l'oggetto <xref:System.Data.DataView> viene infine associato a <xref:System.Windows.Forms.BindingSource>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderby2)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderBy2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderby2)]  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita una query sulla tabella SalesOrderDetail e le righe restituite vengono ordinate prima in base alla quantità dell'ordine e quindi in base all'ID dell'ordine di vendita. Viene quindi creato un oggetto <xref:System.Data.DataView> dalla query e l'oggetto <xref:System.Data.DataView> viene infine associato a <xref:System.Windows.Forms.BindingSource>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromqueryorderbythenby)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromqueryorderbythenby)]  
  
## <a name="using-the-string-based-sort-property"></a>Utilizzo della proprietà per l'ordinamento basato su stringa  
 La funzionalità di ordinamento basata su stringa di <xref:System.Data.DataView> continua a funzionare con LINQ to DataSet. Dopo la creazione di un <xref:System.Data.DataView> da una query di LINQ to DataSet, è possibile utilizzare la proprietà <xref:System.Data.DataView.Sort%2A> per impostare l'ordinamento sul <xref:System.Data.DataView>.  
  
 Le funzionalità di ordinamento basato su stringa e di ordinamento basato su espressione si escludono a vicenda. L'impostazione della proprietà <xref:System.Data.DataView.Sort%2A> implica la cancellazione dell'ordinamento basato su espressione ereditato dalla query da cui è stato creato l'oggetto <xref:System.Data.DataView>.  
  
 Per ulteriori informazioni sul filtro <xref:System.Data.DataView.Sort%2A> basato su stringa, vedere [ordinamento e filtro dei dati](./dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un oggetto <xref:System.Data.DataView> dalla tabella Contact e le righe vengono ordinate prima in base al cognome in ordine decrescente e quindi in base al nome in ordine crescente:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene eseguita una query sulla tabella Contact per individuare i cognomi che iniziano per la lettera "S".  Da tale query viene creato un oggetto <xref:System.Data.DataView> che viene associato a un oggetto <xref:System.Windows.Forms.BindingSource>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="clearing-the-sort"></a>Cancellazione dell'ordinamento  
 È possibile cancellare le informazioni sull'ordinamento relative a un oggetto <xref:System.Data.DataView>, impostate tramite la proprietà <xref:System.Data.DataView.Sort%2A>. È possibile cancellare le informazioni sull'ordinamento in <xref:System.Data.DataView> in due modi diversi:  
  
- Impostare la proprietà <xref:System.Data.DataView.Sort%2A> su `null`.  
  
- Impostare la proprietà <xref:System.Data.DataView.Sort%2A> su una stringa vuota.  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un oggetto <xref:System.Data.DataView> da una query e viene quindi cancellato l'ordinamento impostando la proprietà <xref:System.Data.DataView.Sort%2A> su una stringa vuota:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un oggetto <xref:System.Data.DataView> dalla tabella Contact e viene impostata la proprietà <xref:System.Data.DataView.Sort%2A> per ordinare le righe in base al cognome in ordine decrescente. Le informazioni sull'ordinamento vengono quindi cancellate impostando la proprietà <xref:System.Data.DataView.Sort%2A> su `null`:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## <a name="see-also"></a>Vedere anche

- [Data binding e LINQ to DataSet](data-binding-and-linq-to-dataset.md)
- [Filtro con DataView](filtering-with-dataview-linq-to-dataset.md)
- [Ordinamento dei dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546145(v=vs.120))
