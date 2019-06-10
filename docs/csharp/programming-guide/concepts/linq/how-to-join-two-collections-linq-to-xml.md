---
title: 'Procedura: Unire due raccolte (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
ms.openlocfilehash: 893966f3b803b92efbc89a65870623f10195c85f
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485374"
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a><span data-ttu-id="b495b-102">Procedura: Unire due raccolte (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b495b-102">How to: Join Two Collections (LINQ to XML) (C#)</span></span>
<span data-ttu-id="b495b-103">Un elemento o un attributo di un documento XML può talvolta fare riferimento a un altro elemento o attributo.</span><span class="sxs-lookup"><span data-stu-id="b495b-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="b495b-104">Ad esempio, il documento XML [File XML di esempio: Customers e Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) contiene un elenco di clienti e un elenco di ordini.</span><span class="sxs-lookup"><span data-stu-id="b495b-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="b495b-105">Ogni elemento `Customer` contiene un attributo `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="b495b-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="b495b-106">Ogni elemento `Order` contiene un elemento `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="b495b-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="b495b-107">L'elemento `CustomerID` di ciascun ordine si riferisce all'attributo `CustomerID` di un cliente.</span><span class="sxs-lookup"><span data-stu-id="b495b-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>  
  
 <span data-ttu-id="b495b-108">L'argomento [File XSD di esempio: Customers and Orders ](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md) contiene uno schema XSD che può essere usato per convalidare questo documento.</span><span class="sxs-lookup"><span data-stu-id="b495b-108">The topic [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="b495b-109">Lo schema usa le funzionalità `xs:key` e `xs:keyref` di XSD per stabilire che l'attributo `CustomerID` dell'elemento `Customer` è una chiave e per stabilire una relazione tra l'elemento `CustomerID` in ogni elemento `Order` e l'attributo `CustomerID` in ogni elemento `Customer`.</span><span class="sxs-lookup"><span data-stu-id="b495b-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="b495b-110">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile sfruttare questa relazione usando la clausola `join`.</span><span class="sxs-lookup"><span data-stu-id="b495b-110">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `join` clause.</span></span>  
  
 <span data-ttu-id="b495b-111">Notare che, poiché non è disponibile nessun indice, una tale operazione di join sarà caratterizzata da prestazioni ridotte in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b495b-111">Note that because there is no index available, such joining will have poor runtime performance.</span></span>  
  
 <span data-ttu-id="b495b-112">Per altre informazioni su `join`, vedere [Operazioni Join (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b495b-112">For more detailed information about `join`, see [Join Operations (C#)](../../../../csharp/programming-guide/concepts/linq/join-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b495b-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="b495b-113">Example</span></span>  
 <span data-ttu-id="b495b-114">Nell'esempio seguente gli elementi `Customer` vengono uniti agli elementi `Order` tramite join e viene generato un nuovo documento XML che include l'elemento `CompanyName` negli ordini.</span><span class="sxs-lookup"><span data-stu-id="b495b-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>  
  
 <span data-ttu-id="b495b-115">Prima di eseguire la query, l'esempio convalida la conformità del documento allo schema descritto in [File XSD di esempio: Customers e Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="b495b-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="b495b-116">Tale convalida assicura la corretta esecuzione della clausola di join.</span><span class="sxs-lookup"><span data-stu-id="b495b-116">This ensures that the join clause will always work.</span></span>  
  
 <span data-ttu-id="b495b-117">La query recupera prima tutti gli elementi `Customer` e quindi li unisce agli elementi `Order` tramite join.</span><span class="sxs-lookup"><span data-stu-id="b495b-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="b495b-118">Vengono selezionati solo gli ordini relativi ai clienti il cui valore di `CustomerID` è maggiore di "K".</span><span class="sxs-lookup"><span data-stu-id="b495b-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="b495b-119">Viene quindi proiettato un nuovo elemento `Order` che contiene le informazioni del cliente all'interno di ciascun ordine.</span><span class="sxs-lookup"><span data-stu-id="b495b-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>  
  
 <span data-ttu-id="b495b-120">Nell'esempio viene usato il documento XML seguente: [File XML di esempio: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="b495b-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
 <span data-ttu-id="b495b-121">L'esempio usa lo schema XSD seguente: [File XSD di esempio: Customers e Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="b495b-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../csharp/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders1.md).</span></span>  
  
 <span data-ttu-id="b495b-122">Notare che le unioni tramite join eseguite in questo modo comportano problemi.</span><span class="sxs-lookup"><span data-stu-id="b495b-122">Note that joining in this fashion will not perform very well.</span></span> <span data-ttu-id="b495b-123">I join vengono eseguiti tramite una ricerca lineare,</span><span class="sxs-lookup"><span data-stu-id="b495b-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="b495b-124">pertanto l'assenza di tabelle hash o indici influisce negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b495b-124">There are no hash tables or indexes to help with performance.</span></span>  
  
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
  
 <span data-ttu-id="b495b-125">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b495b-125">This code produces the following output:</span></span>  
  
```  
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
