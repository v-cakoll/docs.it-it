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
# <a name="nesting-datarelations"></a><span data-ttu-id="c8c60-102">Annidamento di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="c8c60-102">Nesting DataRelations</span></span>
<span data-ttu-id="c8c60-103">In una rappresentazione relazionale dei dati, le singole tabelle contengono righe correlate tra loro tramite una colonna o un set di colonne.</span><span class="sxs-lookup"><span data-stu-id="c8c60-103">In a relational representation of data, individual tables contain rows that are related to one another using a column or set of columns.</span></span> <span data-ttu-id="c8c60-104">Nel <xref:System.Data.DataSet> di ADO.NET la relazione tra le tabelle viene implementata mediante l'oggetto <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="c8c60-104">In the ADO.NET <xref:System.Data.DataSet>, the relationship between tables is implemented using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="c8c60-105">Quando si crea un oggetto **DataRelation**, le relazioni padre-figlio delle colonne vengono gestite solo tramite la relazione.</span><span class="sxs-lookup"><span data-stu-id="c8c60-105">When you create a **DataRelation**, the parent-child relationships of the columns are managed only through the relation.</span></span> <span data-ttu-id="c8c60-106">Le tabelle e le colonne sono entità separate.</span><span class="sxs-lookup"><span data-stu-id="c8c60-106">The tables and columns are separate entities.</span></span> <span data-ttu-id="c8c60-107">Nella rappresentazione gerarchica dei dati fornita dall'XML, le relazioni padre-figlio sono rappresentate da elementi padre contenenti elementi figlio annidati.</span><span class="sxs-lookup"><span data-stu-id="c8c60-107">In the hierarchical representation of data that XML provides, the parent-child relationships are represented by parent elements that contain nested child elements.</span></span>  
  
 <span data-ttu-id="c8c60-108">Per semplificare l'annidamento di oggetti figlio quando un **set** di dati viene <xref:System.Xml.XmlDataDocument> sincronizzato con o scritto come dati XML tramite **WriteXml**, **DataRelation** espone una proprietà **nidificata** .</span><span class="sxs-lookup"><span data-stu-id="c8c60-108">To facilitate the nesting of child objects when a **DataSet** is synchronized with an <xref:System.Xml.XmlDataDocument> or written as XML data using **WriteXml**, the **DataRelation** exposes a **Nested** property.</span></span> <span data-ttu-id="c8c60-109">Se si imposta la proprietà **Nested** di un oggetto **DataRelation** su **true** , le righe figlio della relazione verranno annidate all'interno della colonna padre quando vengono scritte come dati XML o sincronizzate con un **XmlDataDocument**.</span><span class="sxs-lookup"><span data-stu-id="c8c60-109">Setting the **Nested** property of a **DataRelation** to **true** causes the child rows of the relation to be nested within the parent column when written as XML data or synchronized with an **XmlDataDocument**.</span></span> <span data-ttu-id="c8c60-110">Per impostazione predefinita, la proprietà **Nested** di **DataRelation** è **false**.</span><span class="sxs-lookup"><span data-stu-id="c8c60-110">The **Nested** property of the **DataRelation** is **false**, by default.</span></span>  
  
 <span data-ttu-id="c8c60-111">Si consideri, ad esempio, il **set di dati**seguente.</span><span class="sxs-lookup"><span data-stu-id="c8c60-111">For example, consider the following **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="c8c60-112">Poiché la **proprietà Nested** dell' **oggetto DataRelation** non è impostata su **true** per questo **DataSet**, gli oggetti figlio non vengono annidati all'interno degli elementi padre quando questo **set** di dati è rappresentato come dati XML.</span><span class="sxs-lookup"><span data-stu-id="c8c60-112">Because the **Nested** property of the **DataRelation** object is not set to **true** for this **DataSet**, the child objects are not nested within the parent elements when this **DataSet** is represented as XML data.</span></span> <span data-ttu-id="c8c60-113">La trasformazione della rappresentazione XML di un **set** di dati che contiene **set**di dati correlati con relazioni dati non annidate può causare un rallentamento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c8c60-113">Transforming the XML representation of a **DataSet** that contains related **DataSet**s with non-nested data relations can cause slow performance.</span></span> <span data-ttu-id="c8c60-114">È consigliabile annidare le relazioni dati.</span><span class="sxs-lookup"><span data-stu-id="c8c60-114">We recommend that you nest the data relations.</span></span> <span data-ttu-id="c8c60-115">A tale scopo, impostare la proprietà **Nested** su **true**.</span><span class="sxs-lookup"><span data-stu-id="c8c60-115">To do this, set the **Nested** property to **true**.</span></span> <span data-ttu-id="c8c60-116">quindi scrivere codice nel foglio di stile XSLT che usa espressioni di query XPath gerarchiche basate su un approccio dall'alto verso il basso per individuare e trasformare i dati.</span><span class="sxs-lookup"><span data-stu-id="c8c60-116">Then write code in the XSLT style sheet that uses top-down hierarchical XPath query expressions to locate and transform the data.</span></span>  
  
 <span data-ttu-id="c8c60-117">Nell'esempio di codice seguente viene illustrato il risultato della chiamata a **WriteXml** nel **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="c8c60-117">The following code example shows the result from calling **WriteXml** on the **DataSet**.</span></span>  
  
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
  
 <span data-ttu-id="c8c60-118">Si noti che l'elemento **Customers** e gli elementi **Orders** vengono visualizzati come elementi di pari livello.</span><span class="sxs-lookup"><span data-stu-id="c8c60-118">Note that the **Customers** element and the **Orders** elements are shown as sibling elements.</span></span> <span data-ttu-id="c8c60-119">Se si desidera che gli elementi **Orders** vengano visualizzati come elementi figlio dei rispettivi elementi padre, è necessario impostare la proprietà **Nested** di **DataRelation** su **true** e aggiungere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c8c60-119">If you wanted the **Orders** elements to show up as children of their respective parent elements, the **Nested** property of the **DataRelation** would need to be set to **true** and you would add the following:</span></span>  
  
```vb  
customerOrders.Nested = True  
```  
  
```csharp  
customerOrders.Nested = true;  
```  
  
 <span data-ttu-id="c8c60-120">Il codice seguente illustra l'aspetto dell'output risultante, con gli elementi **Orders** annidati all'interno dei rispettivi elementi padre.</span><span class="sxs-lookup"><span data-stu-id="c8c60-120">The following code shows what the resulting output would look like, with the **Orders** elements nested within their respective parent elements.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c8c60-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8c60-121">See also</span></span>

- [<span data-ttu-id="c8c60-122">Uso di XML in un set di dati</span><span class="sxs-lookup"><span data-stu-id="c8c60-122">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="c8c60-123">Aggiunta di oggetti DataRelation</span><span class="sxs-lookup"><span data-stu-id="c8c60-123">Adding DataRelations</span></span>](adding-datarelations.md)
- [<span data-ttu-id="c8c60-124">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="c8c60-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c8c60-125">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c8c60-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
