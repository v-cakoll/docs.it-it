---
title: Prestazioni di DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 90820e49-9d46-41f6-9a3d-6c0741bbd8eb
ms.openlocfilehash: 7c81619bf4ac6ed084ea63349345dbf3b7f139b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150688"
---
# <a name="dataview-performance"></a>Prestazioni di DataView
In questo argomento vengono illustrati i vantaggi, in termini di prestazioni, associati all'utilizzo dei metodi <xref:System.Data.DataView.Find%2A> e <xref:System.Data.DataView.FindRows%2A> della classe <xref:System.Data.DataView> e della memorizzazione nella cache di un oggetto <xref:System.Data.DataView> in un'applicazione Web.  
  
## <a name="find-and-findrows"></a>Find e FindRows  
 <xref:System.Data.DataView> costruisce un indice L'indice contiene chiavi costituite da una o più colonne della tabella o della vista. Tali chiavi sono archiviate in una struttura che consente a <xref:System.Data.DataView> di individuare con rapidità ed efficienza la riga o le righe associate ai valori di chiave. Le operazioni che utilizzano l'indice, ad esempio il filtro e l'ordinamento, vedono un aumento significativo delle prestazioni. L'indice relativo a un oggetto <xref:System.Data.DataView> viene compilato sia quando si crea <xref:System.Data.DataView> che quando si modifica una qualsiasi delle informazioni relative all'ordinamento o al filtraggio. Se si crea un oggetto <xref:System.Data.DataView> e quindi si impostano le impostazioni sull'ordinamento o il filtraggio in un secondo momento, l'indice verrà compilato almeno due volte, ovvero una volta durante la creazione di <xref:System.Data.DataView> e una seconda volta quando viene modificata una qualsiasi delle proprietà di ordinamento o filtro. Per ulteriori informazioni sul <xref:System.Data.DataView>filtro e l'ordinamento con , vedere [Filtro con DataView](filtering-with-dataview-linq-to-dataset.md) e [Ordinamento con DataView](sorting-with-dataview-linq-to-dataset.md).  
  
 Per restituire i risultati di una particolare query sui dati anziché fornire una visualizzazione dinamica di un subset di dati, è possibile usare i metodi <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> di <xref:System.Data.DataView> anziché impostare la proprietà <xref:System.Data.DataView.RowFilter%2A>. L'utilizzo della proprietà <xref:System.Data.DataView.RowFilter%2A> è consigliato in applicazioni con associazioni a dati, in cui i risultati filtrati vengono visualizzati da un controllo associato. L'impostazione della proprietà <xref:System.Data.DataView.RowFilter%2A> provoca una ricompilazione dell'indice dei dati, aggiungendo un sovraccarico all'applicazione e riducendo le prestazioni. I metodi <xref:System.Data.DataView.Find%2A> e <xref:System.Data.DataView.FindRows%2A> si avvalgono dell'indice corrente, senza che sia necessario ricompilarlo. Se si intende chiamare <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> solo una volta, è opportuno usare l'oggetto <xref:System.Data.DataView> esistente. Se invece si intende chiamare <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A> più volte, è opportuno creare un nuovo oggetto <xref:System.Data.DataView> per ricompilare l'indice sulla colonna da usare per la ricerca e quindi chiamare il metodo <xref:System.Data.DataView.Find%2A> o <xref:System.Data.DataView.FindRows%2A>. Per ulteriori informazioni <xref:System.Data.DataView.Find%2A> <xref:System.Data.DataView.FindRows%2A> sui metodi e , vedere [Ricerca di righe](./dataset-datatable-dataview/finding-rows.md).  
  
 Nell'esempio seguente viene usato il metodo <xref:System.Data.DataView.Find%2A> per individuare un contatto il cui cognome è "Zhu".  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryorderbyfind)]
 [!code-vb[DP DataView Samples#LDVFromQueryOrderByFind](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryorderbyfind)]  
  
 Nell'esempio seguente viene usato il metodo <xref:System.Data.DataView.FindRows%2A> per individuare tutti i prodotti di colore rosso.  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromqueryfindrows)]
 [!code-vb[DP DataView Samples#LDVFromQueryFindRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromqueryfindrows)]  
  
## <a name="aspnet"></a>ASP.NET  
 In ASP.NET è disponibile un meccanismo di memorizzazione nella cache, che consente di archiviare in memoria oggetti la cui creazione richiede una notevole quantità di risorse del server. La memorizzazione di questi tipi di risorse nella cache può migliorare in modo significativo le prestazioni dell'applicazione. Questo meccanismo viene implementato dalla classe <xref:System.Web.Caching.Cache>, con istanze cache private per ogni applicazione. Poiché la creazione di un nuovo oggetto <xref:System.Data.DataView> può richiedere una notevole quantità di risorse, è opportuno usare la funzionalità di memorizzazione nella cache nelle applicazioni Web in modo da evitare di ricompilare <xref:System.Data.DataView> ogni volta che la pagina Web viene aggiornata.  
  
 Nell'esempio seguente l'oggetto <xref:System.Data.DataView> viene memorizzato nella cache per evitare di ordinare nuovamente i dati quando la pagina viene aggiornata.  
  
```vb  
If (Cache("ordersView") = Nothing) Then  
  
Dim dataSet As New DataSet()  
  
   FillDataSet(dataSet)  
  
   Dim orders As DataTable = dataSet.Tables("SalesOrderHeader")  
  
   Dim query = _  
                    From order In orders.AsEnumerable() _  
                    Where order.Field(Of Boolean)("OnlineOrderFlag") = True _  
                    Order By order.Field(Of Decimal)("TotalDue") _  
                    Select order  
  
   Dim view As DataView = query.AsDataView()  
  
   Cache.Insert("ordersView", view)  
  
End If  
  
Dim ordersView = CType(Cache("ordersView"), DataView)  
  
GridView1.DataSource = ordersView  
GridView1.DataBind()  
```  
  
```csharp  
if (Cache["ordersView"] == null)  
{  
   // Fill the DataSet.
   DataSet dataSet = FillDataSet();  
  
   DataTable orders = dataSet.Tables["SalesOrderHeader"];  
  
   EnumerableRowCollection<DataRow> query =  
                        from order in orders.AsEnumerable()  
                        where order.Field<bool>("OnlineOrderFlag") == true  
                        orderby order.Field<decimal>("TotalDue")  
                        select order;  
  
   DataView view = query.AsDataView();  
   Cache.Insert("ordersView", view);  
}  
  
DataView ordersView = (DataView)Cache["ordersView"];  
  
GridView1.DataSource = ordersView;  
GridView1.DataBind();  
```  
  
## <a name="see-also"></a>Vedere anche

- [Data binding e LINQ to DataSet](data-binding-and-linq-to-dataset.md)
