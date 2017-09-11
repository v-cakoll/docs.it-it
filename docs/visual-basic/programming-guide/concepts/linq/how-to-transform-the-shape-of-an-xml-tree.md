---
title: 'Procedura: trasformare la forma di una struttura ad albero XML (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 84b60854-48b2-452c-87f2-77d53e1d653a
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 9c535a06e70ebd299d7f6646576e703d7a0dda84
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-transform-the-shape-of-an-xml-tree-visual-basic"></a><span data-ttu-id="be4ac-102">Procedura: trasformare la forma di una struttura ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be4ac-102">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="be4ac-103">Il *forma* di un file XML documento si intende i relativi nomi di elemento, i nomi degli attributi e le caratteristiche della relativa gerarchia.</span><span class="sxs-lookup"><span data-stu-id="be4ac-103">The *shape* of an XML document refers to its element names, attribute names, and the characteristics of its hierarchy.</span></span>  
  
 <span data-ttu-id="be4ac-104">In alcuni casi è necessario modificare la forma di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="be4ac-104">Sometimes you will have to change the shape of an XML document.</span></span> <span data-ttu-id="be4ac-105">Ad esempio, può essere necessario inviare un documento XML esistente a un altro sistema che richiede nomi di elemento e di attributo diversi.</span><span class="sxs-lookup"><span data-stu-id="be4ac-105">For example, you might have to send an existing XML document to another system that requires different element and attribute names.</span></span> <span data-ttu-id="be4ac-106">In tal caso, è possibile scorrere il documento, eliminando e rinominando gli elementi a seconda dei casi, tuttavia l'uso della costruzione funzionale consente di ottenere codice più leggibile e conservabile.</span><span class="sxs-lookup"><span data-stu-id="be4ac-106">You could go through the document, deleting and renaming elements as required, but using functional construction results in more readable and maintainable code.</span></span> <span data-ttu-id="be4ac-107">Per ulteriori informazioni sulla costruzione funzionale, vedere [costruzione funzionale (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="be4ac-107">For more information about functional construction, see [Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="be4ac-108">Nel primo esempio viene modificata l'organizzazione del documento XML.</span><span class="sxs-lookup"><span data-stu-id="be4ac-108">The first example changes the organization of the XML document.</span></span> <span data-ttu-id="be4ac-109">Gli elementi complessi vengono spostati da un punto all'altro dell'albero.</span><span class="sxs-lookup"><span data-stu-id="be4ac-109">It moves complex elements from one location in the tree to another.</span></span>  
  
 <span data-ttu-id="be4ac-110">Nel secondo esempio di questo argomento viene creato un documento XML con una forma diversa rispetto al documento di origine.</span><span class="sxs-lookup"><span data-stu-id="be4ac-110">The second example in this topic creates an XML document with a different shape than the source document.</span></span> <span data-ttu-id="be4ac-111">Viene modificato l'uso di maiuscole e minuscole nei nomi di elemento, alcuni elementi vengono rinominati e alcuni elementi dell'albero di origine vengono esclusi dall'albero trasformato.</span><span class="sxs-lookup"><span data-stu-id="be4ac-111">It changes the casing of the element names, renames some elements, and leaves some elements from the source tree out of the transformed tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be4ac-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="be4ac-112">Example</span></span>  
 <span data-ttu-id="be4ac-113">Il codice seguente consente di modificare la forma di un file XML usando espressioni di query incorporate.</span><span class="sxs-lookup"><span data-stu-id="be4ac-113">The following code changes the shape of an XML file using embedded query expressions.</span></span>  
  
 <span data-ttu-id="be4ac-114">Il documento XML di origine di questo esempio include un elemento `Customers` sotto l'elemento `Root` che contiene tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="be4ac-114">The source XML document in this example contains a `Customers` element under the `Root` element that contains all customers.</span></span> <span data-ttu-id="be4ac-115">Include inoltre un elemento `Orders` sotto l'elemento `Root` che contiene tutti gli ordini.</span><span class="sxs-lookup"><span data-stu-id="be4ac-115">It also contains an `Orders` element under the `Root` element that contains all orders.</span></span> <span data-ttu-id="be4ac-116">In questo esempio viene creata un nuovo albero XML in cui gli ordini relativi a ciascun cliente sono contenuti in un elemento `Orders` all'interno dell'elemento `Customer`.</span><span class="sxs-lookup"><span data-stu-id="be4ac-116">This example creates a new XML tree in which the orders for each customer are contained in an `Orders` element within the `Customer` element.</span></span> <span data-ttu-id="be4ac-117">Il documento originale include inoltre nell'elemento `CustomerID` un elemento `Order` che verrà rimosso dal documento modificato.</span><span class="sxs-lookup"><span data-stu-id="be4ac-117">The original document also contains a `CustomerID` element in the `Order` element; this element will be removed from the re-shaped document.</span></span>  
  
 <span data-ttu-id="be4ac-118">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: Customers e Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="be4ac-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim co As XElement = XElement.Load("CustomersOrders.xml")  
Dim newCustOrd = _  
    <Root>  
        <%= From cust In co.<Customers>.<Customer> _  
            Select _  
            <Customer>  
                <%= cust.Attributes() %>  
                <%= cust.Elements() %>  
                <Orders>  
                    <%= From ord In co.<Orders>.<Order> _  
                        Where ord.<CustomerID>.Value = cust.@CustomerID _  
                        Select _  
                        <Order>  
                            <%= ord.Attributes() %>  
                            <%= ord.<EmployeeID> %>  
                            <%= ord.<OrderDate> %>  
                            <%= ord.<RequiredDate> %>  
                            <%= ord.<ShipInfo> %>  
                        </Order> _  
                    %>  
                </Orders>  
            </Customer> _  
        %>  
    </Root>  
Console.WriteLine(newCustOrd)  
```  
  
 <span data-ttu-id="be4ac-119">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="be4ac-119">This code produces the following output:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="be4ac-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="be4ac-120">Example</span></span>  
 <span data-ttu-id="be4ac-121">In questo esempio vengono rinominati alcuni elementi e convertiti alcuni attributi in elementi.</span><span class="sxs-lookup"><span data-stu-id="be4ac-121">This example renames some elements and converts some attributes to elements.</span></span>  
  
 <span data-ttu-id="be4ac-122">Il codice chiama `ConvertAddress`, che restituisce un elenco di <xref:System.Xml.Linq.XElement>oggetti.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="be4ac-122">The code calls `ConvertAddress`, which returns a list of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="be4ac-123">L'argomento del metodo è una query che determina l'elemento complesso `Address` in cui il valore dell'attributo `Type` è `"Shipping"`.</span><span class="sxs-lookup"><span data-stu-id="be4ac-123">The argument to the method is a query that determines the `Address` complex element where the `Type` attribute has a value of `"Shipping"`.</span></span>  
  
 <span data-ttu-id="be4ac-124">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="be4ac-124">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Function ConvertAddress(ByVal add As XElement) As IEnumerable(Of XElement)  
    Dim fragment = New List(Of XElement)  
    fragment.Add(<NAME><%= add.<Name>.Value %></NAME>)  
    fragment.Add(<STREET><%= add.<Street>.Value %></STREET>)  
    fragment.Add(<CITY><%= add.<City>.Value %></CITY>)  
    fragment.Add(<ST><%= add.<State>.Value %></ST>)  
    fragment.Add(<POSTALCODE><%= add.<Zip>.Value %></POSTALCODE>)  
    fragment.Add(<COUNTRY><%= add.<Country>.Value %></COUNTRY>)  
    Return fragment  
End Function  
  
Sub Main()  
    Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
    Dim newPo As XElement = _  
        <PO>  
            <ID><%= po.@PurchaseOrderNumber %></ID>  
            <DATE><%= CDate(po.@OrderDate) %></DATE>  
            <%= _  
                ConvertAddress( _  
                (From el In po.<Address> _  
                Where el.@Type = "Shipping" _  
                Select el) _  
                .First() _  
                ) _  
            %>  
        </PO>  
    Console.WriteLine(newPo)  
End Sub  
```  
  
 <span data-ttu-id="be4ac-125">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="be4ac-125">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="be4ac-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be4ac-126">See Also</span></span>  
 [<span data-ttu-id="be4ac-127">Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be4ac-127">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)

