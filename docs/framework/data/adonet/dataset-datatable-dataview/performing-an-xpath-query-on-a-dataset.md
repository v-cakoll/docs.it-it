---
title: Esecuzione di una query XPath in un dataset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e828566-fffe-4d38-abb2-4d68fd73f663
ms.openlocfilehash: 5e9a00ab78a57c3c1686d7c87ed8b45d9b2649af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150831"
---
# <a name="performing-an-xpath-query-on-a-dataset"></a>Esecuzione di una query XPath in un dataset
La relazione tra <xref:System.Data.DataSet> un <xref:System.Xml.XmlDataDocument> sincronizzato e consente di utilizzare i servizi XML, ad esempio la query XPath (XML Path Language), che accedono a **XmlDataDocument** e possono eseguire determinate funzionalità in modo più pratico rispetto all'accesso diretto al **DataSet.** Ad esempio, anziché **Select** utilizzare il <xref:System.Data.DataTable> metodo Select di un per spostarsi tra le relazioni con altre tabelle in un **DataSet**, è possibile eseguire una query <xref:System.Xml.XmlNodeList>XPath su un **XmlDataDocument** sincronizzato con il **DataSet**, per ottenere un elenco di elementi XML sotto forma di file . I nodi in **XmlNodeList**, eseguito il <xref:System.Xml.XmlElement> cast come nodi , possono quindi essere passati al metodo **GetRowFromElement** di **XmlDataDocument**, per restituire riferimenti corrispondenti <xref:System.Data.DataRow> alle righe della tabella nel **DataSet**sincronizzato.  
  
 Nell'esempio di codice seguente viene eseguita una query XPath "nipote". Il **DataSet** viene compilato con tre tabelle: **Customers**, **Orders**e **OrderDetails**. Nell'esempio viene innanzitutto creata una relazione padre-figlio tra le tabelle **Customers** e **Orders** e tra le tabelle **Orders** e **OrderDetails.** Viene quindi eseguita una query XPath per restituire un **XmlNodeList** di **Customers** nodi in cui un nipote **OrderDetails** nodo dispone di un **ProductID** nodo con il valore di 43. In sostanza, l'esempio utilizza la query XPath per determinare quali clienti hanno ordinato il prodotto con **ProductID** pari a 43.  
  
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
- [Panoramica di ADO.NET](../ado-net-overview.md)
