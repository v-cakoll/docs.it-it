---
title: Creazione di un oggetto DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 76057508-e12d-4779-a707-06a4c2568acf
ms.openlocfilehash: 95bc9beed9965bad32118dfafa4a5aa76902ca10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121654"
---
# <a name="creating-a-dataview-object-linq-to-dataset"></a>Creazione di un oggetto DataView (LINQ to DataSet)
Per creare un oggetto <xref:System.Data.DataView> nel contesto [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], sono disponibili due modalità. È possibile creare un oggetto <xref:System.Data.DataView> da una query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] su <xref:System.Data.DataTable> oppure da un oggetto <xref:System.Data.DataTable> tipizzato o non tipizzato. In entrambi i casi, si crea il <xref:System.Data.DataView> usando uno del <xref:System.Data.DataTableExtensions.AsDataView%2A> i metodi di estensione; <xref:System.Data.DataView> non è direttamente costruibile nel [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] contesto.  
  
 Dopo aver creato <xref:System.Data.DataView>, è possibile associarlo a un controllo dell'interfaccia utente in un'applicazione Windows Forms o ASP.NET oppure modificare le impostazioni di filtro e ordinamento.  
  
 <xref:System.Data.DataView> Costruisce un indice, che aumenta in modo significativo le prestazioni delle operazioni che è possibile usare l'indice, ad esempio filtro e ordinamento. L'indice relativo a un oggetto <xref:System.Data.DataView> viene compilato sia quando si crea <xref:System.Data.DataView> che quando si modifica una qualsiasi delle informazioni relative all'ordinamento o al filtraggio. Se si crea un oggetto <xref:System.Data.DataView> e quindi si impostano le impostazioni sull'ordinamento o il filtraggio in un secondo momento, l'indice verrà compilato almeno due volte, ovvero una volta durante la creazione di <xref:System.Data.DataView> e una seconda volta quando viene modificata una qualsiasi delle proprietà di ordinamento o filtro.  
  
 Per altre informazioni sul filtro e ordinamento con <xref:System.Data.DataView>, vedere [filtro con DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md) e [ordinamento con DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md).  
  
## <a name="creating-dataview-from-a-linq-to-dataset-query"></a>Creazione di una DataView da una query LINQ to DataSet  
 Un oggetto <xref:System.Data.DataView> può essere creato dai risultati di una query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], in cui i risultati sono una proiezione di oggetti <xref:System.Data.DataRow>. Il nuovo oggetto <xref:System.Data.DataView> eredita le informazioni di filtro e ordinamento della query da cui è stato creato.  
  
> [!NOTE]
>  Nella maggior parte dei casi le espressioni usate per il filtro e l'ordinamento non devono presentare effetti collaterali e devono essere deterministiche. Le espressioni non devono inoltre contenere eventuale codice che dipende da un numero impostato di esecuzioni perché è possibile che le operazioni di ordinamento e filtro vengano eseguite un numero qualsiasi di volte.  
  
 La creazione di <xref:System.Data.DataView> da una query che restituisce tipi anonimi o da query che eseguono operazioni join non è supportata.  
  
 In una query usata per creare <xref:System.Data.DataView> sono supportati solo i seguenti operatori di query:  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Cast%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.OrderBy%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.OrderByDescending%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.ThenBy%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.ThenByDescending%2A>  
  
-   <xref:System.Data.EnumerableRowCollectionExtensions.Where%2A>  
  
 Si noti che quando viene creato un oggetto <xref:System.Data.DataView> da una query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], il metodo <xref:System.Data.EnumerableRowCollectionExtensions.Select%2A> deve essere il metodo finale chiamato nella query, Questa operazione è illustrata nell'esempio seguente, che crea un <xref:System.Data.DataView> di ordini online ordinati in base al totale dovuto:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquery1)]
 [!code-vb[DP DataView Samples#CreateLDVFromQuery1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquery1)]  
  
 È anche possibile usare la stringa basata <xref:System.Data.DataView.RowFilter%2A> e <xref:System.Data.DataView.Sort%2A> delle proprietà per filtrare e ordinare un <xref:System.Data.DataView> dopo che è stato creato da una query. Si noti che in questo caso le informazioni di ordinamento e di filtro ereditate dalla query verranno cancellate. Nell'esempio seguente viene creato un oggetto <xref:System.Data.DataView> da una query [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] che filtra i contatti in base ai cognomi che iniziano con 'S'. La proprietà <xref:System.Data.DataView.Sort%2A> basata su stringa è impostata per ordinare i cognomi in ordine crescente e quindi i nomi in ordine decrescente:  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromquerystringsort)]
 [!code-vb[DP DataView Samples#CreateLDVFromQueryStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromquerystringsort)]  
  
## <a name="creating-a-dataview-from-a-datatable"></a>Creazione di una DataView da una DataTable  
 Oltre che da un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query, una <xref:System.Data.DataView> oggetto può essere creato da un <xref:System.Data.DataTable> utilizzando il <xref:System.Data.DataTableExtensions.AsDataView%2A> (metodo).  
  
 Nell'esempio seguente viene creato un oggetto <xref:System.Data.DataView> dalla tabella SalesOrderDetail e viene impostato come origine dati di un oggetto <xref:System.Windows.Forms.BindingSource>. L'oggetto funge da proxy per un controllo <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#createldvfromtable)]
 [!code-vb[DP DataView Samples#CreateLDVFromTable](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#createldvfromtable)]  
  
 Dopo la creazione dell'oggetto <xref:System.Data.DataView> da <xref:System.Data.DataTable>, è possibile specificare le impostazioni di filtro e ordinamento. Nell'esempio seguente viene creato un oggetto <xref:System.Data.DataView> dalla tabella Contact e la proprietà <xref:System.Data.DataView.Sort%2A> viene impostata in modo da ordinare i cognomi in ordine crescente e quindi i nomi in ordine decrescente:  
  
 [!code-csharp[DP DataView Samples#LDVStringSort](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvstringsort)]
 [!code-vb[DP DataView Samples#LDVStringSort](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvstringsort)]  
  
 Se tuttavia la proprietà <xref:System.Data.DataView.RowFilter%2A> o <xref:System.Data.DataView.Sort%2A> viene impostata dopo la creazione di <xref:System.Data.DataView> da una query, si verifica un decremento delle prestazioni perché <xref:System.Data.DataView> costruisce un indice per supportare le operazioni di filtro e ordinamento. L'impostazione della proprietà <xref:System.Data.DataView.RowFilter%2A> o <xref:System.Data.DataView.Sort%2A> provoca una ricompilazione dell'indice dei dati, aggiungendo un sovraccarico all'applicazione e riducendo le prestazioni. Se possibile, è preferibile specificare le impostazioni di filtro e ordinamento la prima volta che viene creato l'oggetto <xref:System.Data.DataView> ed evitare di modificarle in seguito.  
  
## <a name="see-also"></a>Vedere anche

- [Data binding e LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
- [Filtro con DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)
- [Ordinamento con DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)
