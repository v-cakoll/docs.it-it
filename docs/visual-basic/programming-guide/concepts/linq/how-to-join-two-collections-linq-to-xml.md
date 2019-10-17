---
title: 'Procedura: unire due raccolte (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5a5758d4-906b-4285-908d-5b930db192e6
ms.openlocfilehash: cb39895ec5916eb417fb2a161e7c1307087c09c5
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320570"
---
# <a name="how-to-join-two-collections-linq-to-xml-visual-basic"></a><span data-ttu-id="f63df-102">Procedura: unire due raccolte (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f63df-102">How to: Join Two Collections (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f63df-103">Un elemento o un attributo di un documento XML può talvolta fare riferimento a un altro elemento o attributo.</span><span class="sxs-lookup"><span data-stu-id="f63df-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="f63df-104">Ad esempio, il documento XML [File XML di esempio: Customers e Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) contiene un elenco di clienti e un elenco di ordini.</span><span class="sxs-lookup"><span data-stu-id="f63df-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="f63df-105">Ogni elemento `Customer` contiene un attributo `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="f63df-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="f63df-106">Ogni elemento `Order` contiene un elemento `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="f63df-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="f63df-107">L'elemento `CustomerID` di ciascun ordine si riferisce all'attributo `CustomerID` di un cliente.</span><span class="sxs-lookup"><span data-stu-id="f63df-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>  
  
 <span data-ttu-id="f63df-108">L'argomento [File XSD di esempio: Customers e Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md) contiene uno schema XSD che può essere usato per convalidare questo documento.</span><span class="sxs-lookup"><span data-stu-id="f63df-108">The topic [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="f63df-109">Lo schema usa le funzionalità `xs:key` e `xs:keyref` di XSD per stabilire che l'attributo `CustomerID` dell'elemento `Customer` è una chiave e per stabilire una relazione tra l'elemento `CustomerID` in ogni elemento `Order` e l'attributo `CustomerID` in ogni elemento `Customer`.</span><span class="sxs-lookup"><span data-stu-id="f63df-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="f63df-110">Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile sfruttare questa relazione usando la clausola `Join`.</span><span class="sxs-lookup"><span data-stu-id="f63df-110">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `Join` clause.</span></span>  
  
 <span data-ttu-id="f63df-111">Notare che, poiché non è disponibile nessun indice, una tale operazione di join sarà caratterizzata da prestazioni ridotte in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f63df-111">Note that because there is no index available, such joining will have poor runtime performance.</span></span>  
  
 <span data-ttu-id="f63df-112">Per informazioni più dettagliate sui `Join`, vedere [operazioni di join (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="f63df-112">For more detailed information about `Join`, see [Join Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/join-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f63df-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="f63df-113">Example</span></span>  
 <span data-ttu-id="f63df-114">Nell'esempio seguente gli elementi `Customer` vengono uniti agli elementi `Order` tramite join e viene generato un nuovo documento XML che include l'elemento `CompanyName` negli ordini.</span><span class="sxs-lookup"><span data-stu-id="f63df-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>  
  
 <span data-ttu-id="f63df-115">Prima di eseguire la query, l'esempio convalida la conformità del documento allo schema descritto in [File XSD di esempio: Customers e Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="f63df-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="f63df-116">Tale convalida assicura la corretta esecuzione della clausola di join.</span><span class="sxs-lookup"><span data-stu-id="f63df-116">This ensures that the join clause will always work.</span></span>  
  
 <span data-ttu-id="f63df-117">La query recupera prima tutti gli elementi `Customer` e quindi li unisce agli elementi `Order` tramite join.</span><span class="sxs-lookup"><span data-stu-id="f63df-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="f63df-118">Vengono selezionati solo gli ordini relativi ai clienti il cui valore di `CustomerID` è maggiore di "K".</span><span class="sxs-lookup"><span data-stu-id="f63df-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="f63df-119">Viene quindi proiettato un nuovo elemento `Order` che contiene le informazioni del cliente all'interno di ciascun ordine.</span><span class="sxs-lookup"><span data-stu-id="f63df-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>  
  
 <span data-ttu-id="f63df-120">Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f63df-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="f63df-121">Questo esempio usa lo schema XSD seguente: [File XSD di esempio: Customers e Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="f63df-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span>  
  
 <span data-ttu-id="f63df-122">Notare che le unioni tramite join eseguite in questo modo comportano problemi.</span><span class="sxs-lookup"><span data-stu-id="f63df-122">Note that joining in this fashion will not perform very well.</span></span> <span data-ttu-id="f63df-123">I join vengono eseguiti tramite una ricerca lineare,</span><span class="sxs-lookup"><span data-stu-id="f63df-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="f63df-124">pertanto l'assenza di tabelle hash o indici influisce negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="f63df-124">There are no hash tables or indexes to help with performance.</span></span>  
  
```vb  
Public Class Program  
    Public Shared errors As Boolean = False  
  
    Public Shared Function LamValidEvent(ByVal o As Object, _  
                 ByVal e As ValidationEventArgs) As Boolean  
        Console.WriteLine("{0}", e.Message)  
        errors = True  
    End Function  
  
    Shared Sub Main()  
        Dim schemas As New XmlSchemaSet()  
        schemas.Add("", "CustomersOrders.xsd")  
  
        Console.Write("Attempting to validate, ")  
        Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
  
        custOrdDoc.Validate(schemas, Function(o, e) LamValidEvent(0, e))  
        If errors Then  
            Console.WriteLine("custOrdDoc did not validate")  
        Else  
            Console.WriteLine("custOrdDoc validated")  
        End If  
  
        If Not errors Then  
            'Join customers and orders, and create a new XML document with  
            ' a different shape.  
            'The new document contains orders only for customers with a  
            ' CustomerID > 'K'.  
            Dim custOrd As XElement = custOrdDoc.<Root>.FirstOrDefault  
            Dim newCustOrd As XElement = _  
                <Root>  
                    <%= From c In custOrd.<Customers>.<Customer> _  
                        Join o In custOrd.<Orders>.<Order> _  
                        On c.@CustomerID Equals o.<CustomerID>.Value _  
                        Where c.@CustomerID.CompareTo("K") > 0 _  
                        Select _  
                        <Order>  
                            <CustomerID><%= c.@CustomerID %></CustomerID>  
                            <%= c.<CompanyName> %>  
                            <%= c.<ContactName> %>  
                            <%= o.<EmployeeID> %>  
                            <%= o.<OrderDate> %>  
                        </Order> _  
                    %>  
                </Root>  
            Console.WriteLine(newCustOrd)  
        End If  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="f63df-125">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f63df-125">This code produces the following output:</span></span>  
  
```console
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
  
## <a name="see-also"></a><span data-ttu-id="f63df-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f63df-126">See also</span></span>

- [<span data-ttu-id="f63df-127">Tecniche di query avanzate (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f63df-127">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
