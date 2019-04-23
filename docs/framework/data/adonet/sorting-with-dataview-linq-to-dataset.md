---
title: Ordinamento con DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885b3b7b-51c1-42b3-bb29-b925f4f69a6f
ms.openlocfilehash: 01fb70a7b37d6c9c119fff16a9d680d4139421cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109811"
---
# <a name="sorting-with-dataview-linq-to-dataset"></a>Ordinamento con DataView (LINQ to DataSet)
La possibilità di ordinare i dati in base a criteri specifici e quindi di presentarli a un client tramite un controllo dell'interfaccia utente rappresenta un aspetto importante dell'associazione dati. Con <xref:System.Data.DataView> è possibile ordinare i dati e restituire righe di dati ordinate in base a criteri specifici in diversi modi. Oltre a basate su stringa, funzionalità di ordinamento <xref:System.Data.DataView> consente inoltre di usare [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] espressioni per i criteri di ordinamento. [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] le espressioni consentono le operazioni di ordinamento più complesse e potenti rispetto a ordinamento basato su stringa. In questo argomento vengono descritti entrambi gli approcci all'ordinamento tramite <xref:System.Data.DataView>.  
  
## <a name="creating-dataview-from-a-query-with-sorting-information"></a>Creazione di DataView da una query con informazioni di ordinamento  
 È possibile creare un oggetto <xref:System.Data.DataView> da una query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Se la query contiene un' <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.ThenBy%2A>, o <xref:System.Linq.Enumerable.ThenByDescending%2A> le espressioni in tale clausola vengono usate come base per l'ordinamento dei dati nella clausola di <xref:System.Data.DataView>. Ad esempio, se la query contiene il `Order By…`e `Then By…` clausole, risultante <xref:System.Data.DataView> Ordina i dati da entrambe le colonne specificate.  
  
 L'ordinamento basato su espressione è più potente e complesso rispetto a quello più semplice basato su stringa. Notare che l'ordinamento basato su stringa e l'ordinamento basato su espressione si escludono a vicenda. Se si imposta un oggetto <xref:System.Data.DataView.Sort%2A> basato su stringa dopo la creazione di un oggetto <xref:System.Data.DataView> da una query, il filtro basato sull'espressione dedotto dalla query viene cancellato e non può essere ripristinato.  
  
 L'indice relativo a un oggetto <xref:System.Data.DataView> viene compilato sia quando si crea <xref:System.Data.DataView> che quando si modifica una qualsiasi delle informazioni relative all'ordinamento o al filtraggio. Per prestazioni ottimali è preferibile fornire i criteri di ordinamento nella query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] da cui viene creato l'oggetto <xref:System.Data.DataView> ed evitare di modificare le informazioni sull'ordinamento in un secondo momento. Per altre informazioni, vedere [prestazioni di DataView](../../../../docs/framework/data/adonet/dataview-performance.md).  
  
> [!NOTE]
>  Nella maggior parte dei casi le espressioni usate per l'ordinamento non devono presentare effetti collaterali e devono essere deterministiche. Le espressioni non devono inoltre contenere eventuale codice che dipende da un numero impostato di esecuzioni perché è possibile che le operazioni di ordinamento vengano eseguite un numero qualsiasi di volte.  
  
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
 La funzionalità di ordinamento basato su stringa di <xref:System.Data.DataView> è ancora disponibile in [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]. Dopo aver creato un oggetto <xref:System.Data.DataView> da una query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], è possibile usare la proprietà <xref:System.Data.DataView.Sort%2A> per impostare l'ordinamento su <xref:System.Data.DataView>.  
  
 Le funzionalità di ordinamento basato su stringa e di ordinamento basato su espressione si escludono a vicenda. L'impostazione della proprietà <xref:System.Data.DataView.Sort%2A> implica la cancellazione dell'ordinamento basato su espressione ereditato dalla query da cui è stato creato l'oggetto <xref:System.Data.DataView>.  
  
 Per altre informazioni sulla stringa basata <xref:System.Data.DataView.Sort%2A> applicazione di filtri, vedere [ordinamento e filtro dei dati](../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
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
  
-   Impostare la proprietà <xref:System.Data.DataView.Sort%2A> su `null`.  
  
-   Impostare la proprietà <xref:System.Data.DataView.Sort%2A> su una stringa vuota.  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un oggetto <xref:System.Data.DataView> da una query e viene quindi cancellato l'ordinamento impostando la proprietà <xref:System.Data.DataView.Sort%2A> su una stringa vuota:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort)]
 [!code-vb[DP DataView Samples#LDVClearSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort)]  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un oggetto <xref:System.Data.DataView> dalla tabella Contact e viene impostata la proprietà <xref:System.Data.DataView.Sort%2A> per ordinare le righe in base al cognome in ordine decrescente. Le informazioni sull'ordinamento vengono quindi cancellate impostando la proprietà <xref:System.Data.DataView.Sort%2A> su `null`:  
  
 [!code-csharp[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearsort2)]
 [!code-vb[DP DataView Samples#LDVClearSort2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearsort2)]  
  
## <a name="see-also"></a>Vedere anche

- [Data binding e LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
- [Filtro con DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)
- [Ordinamento dei dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546145(v=vs.120))
