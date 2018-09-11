---
title: Esecuzione di una query XPath in un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: a1718429360d79c4628e9948eb1b052c3ac01964
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2018
ms.locfileid: "44360752"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>Esecuzione di una query XPath in un dataset
La relazione tra un oggetto sincronizzato <xref:System.Data.DataSet> e <xref:System.Xml.XmlDataDocument> consente di utilizzare XML servizi che accedono, ad esempio la query XML Path Language (XPath), il **XmlDataDocument** e possono eseguire determinate funzionalità in modo più semplice rispetto all'accesso ai **set di dati** direttamente. Ad esempio, invece di usare la **selezionare** metodo di un <xref:System.Data.DataTable> spostarsi nelle relazioni ad altre tabelle in una **set di dati**, è possibile eseguire una query XPath in un **XmlDataDocument**  sincronizzato con il **set di dati**, per ottenere un elenco di elementi XML sotto forma di un <xref:System.Xml.XmlNodeList>. I nodi il **XmlNodeList**, eseguire il cast come <xref:System.Xml.XmlElement> nodi, può quindi essere passato al **GetRowFromElement** metodo del **XmlDataDocument**, per restituire una corrispondenza <xref:System.Data.DataRow> riferimenti alle righe della tabella in sincronizzato **set di dati**.  
  
 Nell'esempio di codice seguente viene eseguita una query XPath "nipote". Il **set di dati** sono presenti tre tabelle: **clienti**, **ordini**, e **OrderDetails**. Nell'esempio, è prima di tutto viene creata una relazione padre-figlio tra il **clienti** e **ordini** tabelle così come tra la **ordini** e **OrderDetails** tabelle. Viene quindi eseguita una query XPath per restituire un **XmlNodeList** dei **clienti** nodi in cui un nipote **OrderDetails** nodo dispone di un **ProductID**nodi con valore 43. In sostanza, l'esempio Usa la query XPath per determinare quali clienti hanno ordinato il prodotto che ha il **ProductID** 43.  
  
```vb  
' Assumes that connection is a valid SqlConnection.  
connection.Open()  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
Dim detailAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM [Order Details]", connection)  
detailAdapter.Fill(dataSet, "OrderDetails")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
dataSet.Relations.Add("OrderDetail", _  
  dataSet.Tables("Orders").Columns("OrderID"), _  
dataSet.Tables("OrderDetails").Columns("OrderID"), false).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim nodeList As XmlNodeList = xmlDoc.DocumentElement.SelectNodes( _  
  "descendant::Customers[*/OrderDetails/ProductID=43]")  
  
Dim dataRow As DataRow  
Dim xmlNode As XmlNode  
  
For Each xmlNode In nodeList  
  dataRow = xmlDoc.GetRowFromElement(CType(xmlNode, XmlElement))  
  
  If Not dataRow Is Nothing then Console.WriteLine(xmlRow(0).ToString())  
Next  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection.  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(dataSet, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(dataSet, "Orders");  
  
SqlDataAdapter detailAdapter = new SqlDataAdapter(  
  "SELECT * FROM [Order Details]", connection);  
detailAdapter.Fill(dataSet, "OrderDetails");  
  
connection.Close();  
  
dataSet.Relations.Add("CustOrders",  
  dataSet.Tables["Customers"].Columns["CustomerID"],  
 dataSet.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
dataSet.Relations.Add("OrderDetail",  
  dataSet.Tables["Orders"].Columns["OrderID"],  
  dataSet.Tables["OrderDetails"].Columns["OrderID"],   
  false).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(dataSet);   
  
XmlNodeList nodeList = xmlDoc.DocumentElement.SelectNodes(  
  "descendant::Customers[*/OrderDetails/ProductID=43]");  
  
DataRow dataRow;  
foreach (XmlNode xmlNode in nodeList)  
{  
  dataRow = xmlDoc.GetRowFromElement((XmlElement)xmlNode);  
  if (dataRow != null)  
    Console.WriteLine(dataRow[0]);  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Sincronizzazione di DataSet e XmlDataDocument](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
