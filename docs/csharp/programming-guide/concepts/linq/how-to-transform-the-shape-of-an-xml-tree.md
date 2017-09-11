---
title: 'Procedura: trasformare la forma di una struttura ad albero XML (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 93c5d426-dea2-4709-a991-60204de42e8f
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3558cb7592641d784f0150ce7016563ad9c81c46
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-transform-the-shape-of-an-xml-tree-c"></a><span data-ttu-id="984f7-102">Procedura: trasformare la forma di una struttura ad albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="984f7-102">How to: Transform the Shape of an XML Tree (C#)</span></span>
<span data-ttu-id="984f7-103">Per *forma* di un documento XML si intendono i relativi nomi di elemento, nomi di attributi, nonché le caratteristiche della relativa gerarchia.</span><span class="sxs-lookup"><span data-stu-id="984f7-103">The *shape* of an XML document refers to its element names, attribute names, and the characteristics of its hierarchy.</span></span>  
  
 <span data-ttu-id="984f7-104">In alcuni casi è necessario modificare la forma di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="984f7-104">Sometimes you will have to change the shape of an XML document.</span></span> <span data-ttu-id="984f7-105">Ad esempio, può essere necessario inviare un documento XML esistente a un altro sistema che richiede nomi di elemento e di attributo diversi.</span><span class="sxs-lookup"><span data-stu-id="984f7-105">For example, you might have to send an existing XML document to another system that requires different element and attribute names.</span></span> <span data-ttu-id="984f7-106">In tal caso, è possibile scorrere il documento, eliminando e rinominando gli elementi a seconda dei casi, tuttavia l'uso della costruzione funzionale consente di ottenere codice più leggibile e conservabile.</span><span class="sxs-lookup"><span data-stu-id="984f7-106">You could go through the document, deleting and renaming elements as required, but using functional construction results in more readable and maintainable code.</span></span> <span data-ttu-id="984f7-107">Per altre informazioni sulla costruzione funzionale, vedere [Costruzione funzionale (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="984f7-107">For more information about functional construction, see [Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="984f7-108">Nel primo esempio viene modificata l'organizzazione del documento XML.</span><span class="sxs-lookup"><span data-stu-id="984f7-108">The first example changes the organization of the XML document.</span></span> <span data-ttu-id="984f7-109">Gli elementi complessi vengono spostati da un punto all'altro dell'albero.</span><span class="sxs-lookup"><span data-stu-id="984f7-109">It moves complex elements from one location in the tree to another.</span></span>  
  
 <span data-ttu-id="984f7-110">Nel secondo esempio di questo argomento viene creato un documento XML con una forma diversa rispetto al documento di origine.</span><span class="sxs-lookup"><span data-stu-id="984f7-110">The second example in this topic creates an XML document with a different shape than the source document.</span></span> <span data-ttu-id="984f7-111">Viene modificato l'uso di maiuscole e minuscole nei nomi di elemento, alcuni elementi vengono rinominati e alcuni elementi dell'albero di origine vengono esclusi dall'albero trasformato.</span><span class="sxs-lookup"><span data-stu-id="984f7-111">It changes the casing of the element names, renames some elements, and leaves some elements from the source tree out of the transformed tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="984f7-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="984f7-112">Example</span></span>  
 <span data-ttu-id="984f7-113">Il codice seguente consente di modificare la forma di un file XML usando espressioni di query incorporate.</span><span class="sxs-lookup"><span data-stu-id="984f7-113">The following code changes the shape of an XML file using embedded query expressions.</span></span>  
  
 <span data-ttu-id="984f7-114">Il documento XML di origine di questo esempio include un elemento `Customers` sotto l'elemento `Root` che contiene tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="984f7-114">The source XML document in this example contains a `Customers` element under the `Root` element that contains all customers.</span></span> <span data-ttu-id="984f7-115">Include inoltre un elemento `Orders` sotto l'elemento `Root` che contiene tutti gli ordini.</span><span class="sxs-lookup"><span data-stu-id="984f7-115">It also contains an `Orders` element under the `Root` element that contains all orders.</span></span> <span data-ttu-id="984f7-116">In questo esempio viene creata un nuovo albero XML in cui gli ordini relativi a ciascun cliente sono contenuti in un elemento `Orders` all'interno dell'elemento `Customer`.</span><span class="sxs-lookup"><span data-stu-id="984f7-116">This example creates a new XML tree in which the orders for each customer are contained in an `Orders` element within the `Customer` element.</span></span> <span data-ttu-id="984f7-117">Il documento originale include inoltre nell'elemento `CustomerID` un elemento `Order` che verrà rimosso dal documento modificato.</span><span class="sxs-lookup"><span data-stu-id="984f7-117">The original document also contains a `CustomerID` element in the `Order` element; this element will be removed from the re-shaped document.</span></span>  
  
 <span data-ttu-id="984f7-118">Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="984f7-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
XElement newCustOrd =  
    new XElement("Root",  
        from cust in co.Element("Customers").Elements("Customer")  
        select new XElement("Customer",  
            cust.Attributes(),  
            cust.Elements(),  
            new XElement("Orders",  
                from ord in co.Element("Orders").Elements("Order")  
                where (string)ord.Element("CustomerID") == (string)cust.Attribute("CustomerID")  
                select new XElement("Order",  
                    ord.Attributes(),  
                    ord.Element("EmployeeID"),  
                    ord.Element("OrderDate"),  
                    ord.Element("RequiredDate"),  
                    ord.Element("ShipInfo")  
                )  
            )  
        )  
    );  
Console.WriteLine(newCustOrd);  
```  
  
 <span data-ttu-id="984f7-119">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="984f7-119">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Customer CustomerID="GREAL">  
    <CompanyName>Great Lakes Food Market</CompanyName>  
    <ContactName>Howard Snyder</ContactName>  
    <ContactTitle>Marketing Manager</ContactTitle>  
    <Phone>(503) 555-7555</Phone>  
    <FullAddress>  
      <Address>2732 Baker Blvd.</Address>  
      <City>Eugene</City>  
      <Region>OR</Region>  
      <PostalCode>97403</PostalCode>  
      <Country>USA</Country>  
    </FullAddress>  
    <Orders />  
  </Customer>  
  <Customer CustomerID="HUNGC">  
    <CompanyName>Hungry Coyote Import Store</CompanyName>  
    <ContactName>Yoshi Latimer</ContactName>  
    <ContactTitle>Sales Representative</ContactTitle>  
    <Phone>(503) 555-6874</Phone>  
    <Fax>(503) 555-2376</Fax>  
    <FullAddress>  
      <Address>City Center Plaza 516 Main St.</Address>  
      <City>Elgin</City>  
      <Region>OR</Region>  
      <PostalCode>97827</PostalCode>  
      <Country>USA</Country>  
    </FullAddress>  
    <Orders />  
  </Customer>  
  . . .  
```  
  
## <a name="example"></a><span data-ttu-id="984f7-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="984f7-120">Example</span></span>  
 <span data-ttu-id="984f7-121">In questo esempio vengono rinominati alcuni elementi e convertiti alcuni attributi in elementi.</span><span class="sxs-lookup"><span data-stu-id="984f7-121">This example renames some elements and converts some attributes to elements.</span></span>  
  
 <span data-ttu-id="984f7-122">Il codice chiama `ConvertAddress` che restituisce un elenco di oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="984f7-122">The code calls `ConvertAddress`, which returns a list of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="984f7-123">L'argomento del metodo è una query che determina l'elemento complesso `Address` in cui il valore dell'attributo `Type` è `"Shipping"`.</span><span class="sxs-lookup"><span data-stu-id="984f7-123">The argument to the method is a query that determines the `Address` complex element where the `Type` attribute has a value of `"Shipping"`.</span></span>  
  
 <span data-ttu-id="984f7-124">Questo esempio usa il documento XML seguente: [File XML di esempio: ordine di acquisto tipico (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="984f7-124">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
static IEnumerable<XElement> ConvertAddress(XElement add)  
{  
    List<XElement> fragment = new List<XElement>() {  
        new XElement("NAME", (string)add.Element("Name")),  
        new XElement("STREET", (string)add.Element("Street")),  
        new XElement("CITY", (string)add.Element("City")),  
        new XElement("ST", (string)add.Element("State")),  
        new XElement("POSTALCODE", (string)add.Element("Zip")),  
        new XElement("COUNTRY", (string)add.Element("Country"))  
    };  
    return fragment;  
}  
  
static void Main(string[] args)  
{  
    XElement po = XElement.Load("PurchaseOrder.xml");  
    XElement newPo = new XElement("PO",  
        new XElement("ID", (string)po.Attribute("PurchaseOrderNumber")),  
        new XElement("DATE", (DateTime)po.Attribute("OrderDate")),  
        ConvertAddress(  
            (from el in po.Elements("Address")  
            where (string)el.Attribute("Type") == "Shipping"  
            select el)  
            .First()  
        )  
    );  
    Console.WriteLine(newPo);  
}  
```  
  
 <span data-ttu-id="984f7-125">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="984f7-125">This code produces the following output:</span></span>  
  
```xml  
<PO>  
  <ID>99503</ID>  
  <DATE>1999-10-20T00:00:00</DATE>  
  <NAME>Ellen Adams</NAME>  
  <STREET>123 Maple Street</STREET>  
  <CITY>Mill Valley</CITY>  
  <ST>CA</ST>  
  <POSTALCODE>10999</POSTALCODE>  
  <COUNTRY>USA</COUNTRY>  
</PO>  
```  
  
## <a name="see-also"></a><span data-ttu-id="984f7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="984f7-126">See Also</span></span>  
 [<span data-ttu-id="984f7-127">Proiezioni e trasformazioni (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="984f7-127">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)

