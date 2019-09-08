---
title: Annidamento di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 971a1bddc40521dc7381ecb2e39709c0fed282ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785980"
---
# <a name="nesting-datarelations"></a>Annidamento di oggetti DataRelation
In una rappresentazione relazionale dei dati, le singole tabelle contengono righe correlate tra loro tramite una colonna o un set di colonne. Nel <xref:System.Data.DataSet> di ADO.NET la relazione tra le tabelle viene implementata mediante l'oggetto <xref:System.Data.DataRelation>. Quando si crea un oggetto **DataRelation**, le relazioni padre-figlio delle colonne vengono gestite solo tramite la relazione. Le tabelle e le colonne sono entità separate. Nella rappresentazione gerarchica dei dati fornita dall'XML, le relazioni padre-figlio sono rappresentate da elementi padre contenenti elementi figlio annidati.  
  
 Per semplificare l'annidamento di oggetti figlio quando un **set** di dati viene <xref:System.Xml.XmlDataDocument> sincronizzato con o scritto come dati XML tramite **WriteXml**, **DataRelation** espone una proprietà **nidificata** . Se si imposta la proprietà **Nested** di un oggetto **DataRelation** su **true** , le righe figlio della relazione verranno annidate all'interno della colonna padre quando vengono scritte come dati XML o sincronizzate con un **XmlDataDocument**. Per impostazione predefinita, la proprietà **Nested** di **DataRelation** è **false**.  
  
 Si consideri, ad esempio, il **set di dati**seguente.  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection)  
  
connection.Open()  
  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
customerAdapter.Fill(dataSet, "Customers")  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
Dim customerOrders As DataRelation = dataSet.Relations.Add( _  
  "CustOrders", dataSet.Tables("Customers").Columns("CustomerID"), _  
  dataSet.Tables("Orders").Columns("CustomerID"))  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID, OrderDate FROM Orders", connection);  
  
connection.Open();  
  
DataSet dataSet = new DataSet("CustomerOrders");  
customerAdapter.Fill(dataSet, "Customers");  
orderAdapter.Fill(dataSet, "Orders");  
  
connection.Close();  
  
DataRelation customerOrders = dataSet.Relations.Add(  
  "CustOrders", dataSet.Tables["Customers"].Columns["CustomerID"],  
  dataSet.Tables["Orders"].Columns["CustomerID"]);  
```  
  
 Poiché la **proprietà Nested** dell' **oggetto DataRelation** non è impostata su **true** per questo **DataSet**, gli oggetti figlio non vengono annidati all'interno degli elementi padre quando questo **set** di dati è rappresentato come dati XML. La trasformazione della rappresentazione XML di un **set** di dati che contiene **set**di dati correlati con relazioni dati non annidate può causare un rallentamento delle prestazioni. È consigliabile annidare le relazioni dati. A tale scopo, impostare la proprietà **Nested** su **true**. quindi scrivere codice nel foglio di stile XSLT che usa espressioni di query XPath gerarchiche basate su un approccio dall'alto verso il basso per individuare e trasformare i dati.  
  
 Nell'esempio di codice seguente viene illustrato il risultato della chiamata a **WriteXml** nel **DataSet**.  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
  <Orders>  
    <OrderID>10643</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-08-25T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10692</OrderID>  
    <CustomerID>ALFKI</CustomerID>  
    <OrderDate>1997-10-03T00:00:00</OrderDate>  
  </Orders>  
  <Orders>  
    <OrderID>10308</OrderID>  
    <CustomerID>ANATR</CustomerID>  
    <OrderDate>1996-09-18T00:00:00</OrderDate>  
  </Orders>  
</CustomerOrders>  
```  
  
 Si noti che l'elemento **Customers** e gli elementi **Orders** vengono visualizzati come elementi di pari livello. Se si desidera che gli elementi **Orders** vengano visualizzati come elementi figlio dei rispettivi elementi padre, è necessario impostare la proprietà **Nested** di **DataRelation** su **true** e aggiungere quanto segue:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 Il codice seguente illustra l'aspetto dell'output risultante, con gli elementi **Orders** annidati all'interno dei rispettivi elementi padre.  
  
```xml  
<CustomerOrders>  
  <Customers>  
    <CustomerID>ALFKI</CustomerID>  
    <Orders>  
      <OrderID>10643</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-08-25T00:00:00</OrderDate>  
    </Orders>  
    <Orders>  
      <OrderID>10692</OrderID>  
      <CustomerID>ALFKI</CustomerID>  
      <OrderDate>1997-10-03T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Alfreds Futterkiste</CompanyName>  
  </Customers>  
  <Customers>  
    <CustomerID>ANATR</CustomerID>  
    <Orders>  
      <OrderID>10308</OrderID>  
      <CustomerID>ANATR</CustomerID>  
      <OrderDate>1996-09-18T00:00:00</OrderDate>  
    </Orders>  
    <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
  </Customers>  
</CustomerOrders>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Uso di XML in un set di dati](using-xml-in-a-dataset.md)
- [Aggiunta di oggetti DataRelation](adding-datarelations.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
