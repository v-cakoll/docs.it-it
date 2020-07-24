---
title: Come unire due raccolte (LINQ to XML) (C#)
description: Questo esempio C# unisce gli elementi in LINQ to XML ad altri elementi e genera un nuovo documento XML.
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
ms.openlocfilehash: 10792ed4907e778b41821c9b32574bd8fc0ab35f
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104989"
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a><span data-ttu-id="0d743-103">Come unire due raccolte (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0d743-103">How to join two collections (LINQ to XML) (C#)</span></span>

<span data-ttu-id="0d743-104">Un elemento o un attributo di un documento XML può talvolta fare riferimento a un altro elemento o attributo.</span><span class="sxs-lookup"><span data-stu-id="0d743-104">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="0d743-105">Ad esempio, il documento XML [File XML di esempio: Customers e Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) contiene un elenco di clienti e un elenco di ordini.</span><span class="sxs-lookup"><span data-stu-id="0d743-105">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="0d743-106">Ogni elemento `Customer` contiene un attributo `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="0d743-106">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="0d743-107">Ogni elemento `Order` contiene un elemento `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="0d743-107">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="0d743-108">L'elemento `CustomerID` di ciascun ordine si riferisce all'attributo `CustomerID` di un cliente.</span><span class="sxs-lookup"><span data-stu-id="0d743-108">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>

<span data-ttu-id="0d743-109">L'argomento [File XSD di esempio: Customers e Orders](./sample-xsd-file-customers-and-orders1.md) contiene uno schema XSD che può essere usato per convalidare questo documento.</span><span class="sxs-lookup"><span data-stu-id="0d743-109">The topic [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="0d743-110">Lo schema usa le funzionalità `xs:key` e `xs:keyref` di XSD per stabilire che l'attributo `CustomerID` dell'elemento `Customer` è una chiave e per stabilire una relazione tra l'elemento `CustomerID` in ogni elemento `Order` e l'attributo `CustomerID` in ogni elemento `Customer`.</span><span class="sxs-lookup"><span data-stu-id="0d743-110">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>

<span data-ttu-id="0d743-111">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile sfruttare questa relazione usando la clausola `join`.</span><span class="sxs-lookup"><span data-stu-id="0d743-111">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `join` clause.</span></span>

<span data-ttu-id="0d743-112">Poiché non è disponibile alcun indice, tale Unione avrà prestazioni di run-time insufficienti.</span><span class="sxs-lookup"><span data-stu-id="0d743-112">Because there is no index available, such joining will have poor run-time performance.</span></span>

<span data-ttu-id="0d743-113">Per altre informazioni su `join`, vedere [Operazioni Join (C#)](./join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="0d743-113">For more detailed information about `join`, see [Join Operations (C#)](./join-operations.md).</span></span>

## <a name="example"></a><span data-ttu-id="0d743-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d743-114">Example</span></span>

<span data-ttu-id="0d743-115">Nell'esempio seguente gli elementi `Customer` vengono uniti agli elementi `Order` tramite join e viene generato un nuovo documento XML che include l'elemento `CompanyName` negli ordini.</span><span class="sxs-lookup"><span data-stu-id="0d743-115">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>

<span data-ttu-id="0d743-116">Prima di eseguire la query, l'esempio convalida la conformità del documento allo schema descritto in [File XSD di esempio: Customers e Orders](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="0d743-116">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="0d743-117">Tale convalida assicura la corretta esecuzione della clausola di join.</span><span class="sxs-lookup"><span data-stu-id="0d743-117">This ensures that the join clause will always work.</span></span>

<span data-ttu-id="0d743-118">La query recupera prima tutti gli elementi `Customer` e quindi li unisce agli elementi `Order` tramite join.</span><span class="sxs-lookup"><span data-stu-id="0d743-118">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="0d743-119">Vengono selezionati solo gli ordini relativi ai clienti il cui valore di `CustomerID` è maggiore di "K".</span><span class="sxs-lookup"><span data-stu-id="0d743-119">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="0d743-120">Viene quindi proiettato un nuovo elemento `Order` che contiene le informazioni del cliente all'interno di ciascun ordine.</span><span class="sxs-lookup"><span data-stu-id="0d743-120">It then projects a new `Order` element that contains the customer information within each order.</span></span>

<span data-ttu-id="0d743-121">Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="0d743-121">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>

<span data-ttu-id="0d743-122">Questo esempio usa lo schema XSD seguente: [File XSD di esempio: Customers e Orders](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="0d743-122">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span>

<span data-ttu-id="0d743-123">L'Unione in questo modo non verrà eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="0d743-123">Joining in this fashion will not perform well.</span></span> <span data-ttu-id="0d743-124">I join vengono eseguiti tramite una ricerca lineare,</span><span class="sxs-lookup"><span data-stu-id="0d743-124">Joins are performed via a linear search.</span></span> <span data-ttu-id="0d743-125">pertanto l'assenza di tabelle hash o indici influisce negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="0d743-125">There are no hash tables or indexes to help with performance.</span></span>

```csharp
XmlSchemaSet schemas = new XmlSchemaSet();
schemas.Add("", "CustomersOrders.xsd");

Console.Write("Attempting to validate, ");
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");

bool errors = false;
custOrdDoc.Validate(schemas, (o, e) =>
                     {
                         Console.WriteLine("{0}", e.Message);
                         errors = true;
                     });
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");

if (!errors)
{
    // Join customers and orders, and create a new XML document with
    // a different shape.

    // The new document contains orders only for customers with a
    // CustomerID > 'K'
    XElement custOrd = custOrdDoc.Element("Root");
    XElement newCustOrd = new XElement("Root",
        from c in custOrd.Element("Customers").Elements("Customer")
        join o in custOrd.Element("Orders").Elements("Order")
                   on (string)c.Attribute("CustomerID") equals
                      (string)o.Element("CustomerID")
        where ((string)c.Attribute("CustomerID")).CompareTo("K") > 0
        select new XElement("Order",
            new XElement("CustomerID", (string)c.Attribute("CustomerID")),
            new XElement("CompanyName", (string)c.Element("CompanyName")),
            new XElement("ContactName", (string)c.Element("ContactName")),
            new XElement("EmployeeID", (string)o.Element("EmployeeID")),
            new XElement("OrderDate", (DateTime)o.Element("OrderDate"))
        )
    );
    Console.WriteLine(newCustOrd);
}
```

<span data-ttu-id="0d743-126">Questo codice genera l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="0d743-126">This code produces the following output:</span></span>

```output
Attempting to validate, custOrdDoc validated
<Root>
  <Order>
    <CustomerID>LAZYK</CustomerID>
    <CompanyName>Lazy K Kountry Store</CompanyName>
    <ContactName>John Steel</ContactName>
    <EmployeeID>1</EmployeeID>
    <OrderDate>1997-03-21T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LAZYK</CustomerID>
    <CompanyName>Lazy K Kountry Store</CompanyName>
    <ContactName>John Steel</ContactName>
    <EmployeeID>8</EmployeeID>
    <OrderDate>1997-05-22T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>1</EmployeeID>
    <OrderDate>1997-06-25T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>8</EmployeeID>
    <OrderDate>1997-10-27T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>6</EmployeeID>
    <OrderDate>1997-11-10T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>4</EmployeeID>
    <OrderDate>1998-02-12T00:00:00</OrderDate>
  </Order>
</Root>
```
