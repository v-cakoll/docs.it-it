---
title: Esecuzione di una query XPath in un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 56d1d11240934036994a14e454cf1a1d8b95226a
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204531"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>Esecuzione di una query XPath in un dataset
La relazione tra un <xref:System.Data.DataSet> sincronizzato <xref:System.Xml.XmlDataDocument> e consente di utilizzare i servizi XML, ad esempio la query XPath (XML Path Language), che accedono a **XmlDataDocument** e possono eseguire determinate funzionalità in modo più semplice rispetto a accesso diretto al **set di dati** . Ad esempio, anziché usare il metodo **Select** di <xref:System.Data.DataTable> un oggetto per spostarsi tra le relazioni con altre tabelle in un **set di dati**, è possibile eseguire una query XPath su un **XmlDataDocument** sincronizzato con il set di **dati**, per ottenere un oggetto elenco di elementi XML nel formato di un oggetto <xref:System.Xml.XmlNodeList>. I nodi del **nodo XmlNodeList**, di cui è stato <xref:System.Xml.XmlElement> eseguito il cast come nodi, possono quindi essere passati al metodo **GetRowFromElement** di **XmlDataDocument**per restituire <xref:System.Data.DataRow> riferimenti corrispondenti alle righe della tabella nell'oggetto Synchronized  **Set di dati**.  
  
 Nell'esempio di codice seguente viene eseguita una query XPath "nipote". Il **set di dati** viene compilato con tre tabelle: **Customers**, **Orders**e **OrderDetails**. Nell'esempio viene innanzitutto creata una relazione padre-figlio tra le tabelle **Customers** e **Orders** e tra le tabelle **Orders** e **OrderDetails** . Viene quindi eseguita una query XPath per restituire un XmlNodeList di nodi **Customers** in cui un nodo nipote **OrderDetails** ha un nodo **ProductID** con valore 43. In sostanza, nell'esempio viene utilizzata la query XPath per determinare quali clienti hanno ordinato il prodotto con **ProductID** 43.  
  
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

- [Sincronizzazione di DataSet e XmlDataDocument](dataset-and-xmldatadocument-synchronization.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
