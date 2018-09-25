---
title: Annidamento di oggetti DataRelation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9530f9c9-dd98-4b93-8cdb-40d7f1e8d0ab
ms.openlocfilehash: 9255615c7786773f1d4f453b910fdccdf191721f
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47076651"
---
# <a name="nesting-datarelations"></a><span data-ttu-id="7aae0-102">Annidamento di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="7aae0-102">Nesting DataRelations</span></span>
<span data-ttu-id="7aae0-103">In una rappresentazione relazionale dei dati, le singole tabelle contengono righe correlate tra loro tramite una colonna o un set di colonne.</span><span class="sxs-lookup"><span data-stu-id="7aae0-103">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="7aae0-104">Nel <xref:System.Data.DataSet> di ADO.NET la relazione tra le tabelle viene implementata mediante l'oggetto <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="7aae0-104">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="7aae0-105">Quando si crea una **DataRelation**, le relazioni padre-figlio tra le colonne vengono gestite solo tramite la relazione.</span><span class="sxs-lookup"><span data-stu-id="7aae0-105">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="7aae0-106">Le tabelle e le colonne sono entità separate.</span><span class="sxs-lookup"><span data-stu-id="7aae0-106">The tables and columns are separate entities.</span></span> <span data-ttu-id="7aae0-107">Nella rappresentazione gerarchica dei dati fornita dall'XML, le relazioni padre-figlio sono rappresentate da elementi padre contenenti elementi figlio annidati.</span><span class="sxs-lookup"><span data-stu-id="7aae0-107">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="7aae0-108">Per facilitare l'annidamento di oggetti figlio quando un **set di dati** è sincronizzato con un <xref:System.Xml.XmlDataDocument> o scrivere come dati XML mediante **WriteXml**, la **DataRelation** espone un **Nested** proprietà.</span><span class="sxs-lookup"><span data-stu-id="7aae0-108">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="7aae0-109">Impostando il **Nested** proprietà di un **DataRelation** al **true** fa sì che le righe della relazione annidata all'interno della colonna padre quando scritti come dati XML l'elemento figlio o sincronizzato con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="7aae0-109">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="7aae0-110">Il **Nested** proprietà delle **DataRelation** viene **false**, per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7aae0-110">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="7aae0-111">Ad esempio, tenere presente quanto segue **set di dati**.</span><span class="sxs-lookup"><span data-stu-id="7aae0-111">For example, consider the following **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="7aae0-112">Poiché il **Nested** proprietà delle **DataRelation** oggetto non è impostato su **true** per questo **set di dati**, gli oggetti figlio non sono annidati all'interno degli elementi padre quando ciò **set di dati** è rappresentato come dati XML.</span><span class="sxs-lookup"><span data-stu-id="7aae0-112">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="7aae0-113">Trasformare la rappresentazione XML di un **set di dati** che contiene correlato **set di dati**s con relazioni dati non annidate può causare un rallentamento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7aae0-113">Transforming the XML representation of a **DataSet** that contains related **DataSet**s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="7aae0-114">È consigliabile annidare le relazioni dati.</span><span class="sxs-lookup"><span data-stu-id="7aae0-114">We recommend that you nest the data relations.</span></span> <span data-ttu-id="7aae0-115">A questo scopo, impostare il **Nested** proprietà **true**.</span><span class="sxs-lookup"><span data-stu-id="7aae0-115">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="7aae0-116">quindi scrivere codice nel foglio di stile XSLT che usa espressioni di query XPath gerarchiche basate su un approccio dall'alto verso il basso per individuare e trasformare i dati.</span><span class="sxs-lookup"><span data-stu-id="7aae0-116">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="7aae0-117">Esempio di codice seguente viene illustrato il risultato della chiamata **WriteXml** nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="7aae0-117">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="7aae0-118">Si noti che il **clienti** elemento e il **ordini** gli elementi vengono visualizzati come elementi di pari livello.</span><span class="sxs-lookup"><span data-stu-id="7aae0-118">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="7aae0-119">Se si desidera la **ordini** elementi visualizzati come elementi figlio dei rispettivi elementi padre, il **Nested** proprietà del **DataRelation** dovrà essere impostata su **true** e aggiungere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="7aae0-119">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="7aae0-120">Il codice seguente viene illustrato l'output risultante sarebbe aspetto, con la **ordini** elementi annidati all'interno dei rispettivi elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7aae0-120">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7aae0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7aae0-121">See Also</span></span>  
 [<span data-ttu-id="7aae0-122">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="7aae0-122">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="7aae0-123">Aggiunta di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="7aae0-123">Adding DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md)  
 [<span data-ttu-id="7aae0-124">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="7aae0-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="7aae0-125">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="7aae0-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
