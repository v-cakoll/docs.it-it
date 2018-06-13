---
title: Annidamento di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 3f17d81ac41c90e7f1c48523a4ced91bc788a962
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761896"
---
# <a name="nesting-datarelations"></a>Annidamento di oggetti DataRelation
In una rappresentazione relazionale dei dati, le singole tabelle contengono righe correlate tra loro tramite una colonna o un set di colonne. Nel <xref:System.Data.DataSet> di ADO.NET la relazione tra le tabelle viene implementata mediante l'oggetto <xref:System.Data.DataRelation>. Quando si crea un **DataRelation**, le relazioni padre-figlio tra le colonne vengono gestite solo tramite la relazione. Le tabelle e le colonne sono entità separate. Nella rappresentazione gerarchica dei dati fornita dall'XML, le relazioni padre-figlio sono rappresentate da elementi padre contenenti elementi figlio annidati.  
  
 Per facilitare l'annidamento di oggetti figlio quando un **DataSet** è sincronizzato con un <xref:System.Xml.XmlDataDocument> o scritti come dati XML mediante **WriteXml**, **DataRelation** espone un **Nested** proprietà. Impostazione di **Nested** proprietà di un **DataRelation** a **true** fa sì che le righe della relazione vengono annidate all'interno della colonna padre durante scritti come dati XML l'elemento figlio o sincronizzazione con un **XmlDataDocument**. Il **Nested** proprietà del **DataRelation** è **false**, per impostazione predefinita.  
  
 Ad esempio, tenere presente quanto segue **DataSet**.  
  
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
  
 Poiché il **Nested** proprietà del **DataRelation** oggetto non è impostato su **true** per questo **DataSet**, gli oggetti figlio non sono annidati all'interno degli elementi padre quando questo **set di dati** è rappresentato come dati XML. Trasformazione della rappresentazione XML di un **DataSet** contenente correlati **DataSet**con relazioni dati non annidate può causare un rallentamento delle prestazioni. È consigliabile annidare le relazioni dati. A tale scopo, impostare il **Nested** proprietà **true**. quindi scrivere codice nel foglio di stile XSLT che usa espressioni di query XPath gerarchiche basate su un approccio dall'alto verso il basso per individuare e trasformare i dati.  
  
 Esempio di codice seguente viene illustrato il risultato della chiamata **WriteXml** sul **DataSet**.  
  
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
  
 Si noti che il **clienti** elemento e **ordini** gli elementi vengono visualizzati come elementi di pari livello. Se si desidera utilizzare il **ordini** elementi vengano visualizzati come elementi figlio dei rispettivi elementi padre, il **Nested** proprietà del **DataRelation** dovrà essere impostata su **true** e aggiungere quanto segue:  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 Il codice seguente viene mostrato l'output risultante, con la **ordini** elementi annidati all'interno dei rispettivi elementi padre.  
  
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
 [Uso di XML in un set di dati](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Aggiunta di oggetti DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 [Oggetti DataSet, DataTable e DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
