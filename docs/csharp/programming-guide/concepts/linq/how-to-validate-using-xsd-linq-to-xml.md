---
title: Come eseguire la convalida utilizzando XSD (LINQ to XML)C#()
ms.date: 07/20/2015
ms.assetid: 6a7f83a9-2d74-4c2b-8417-0a8595879516
ms.openlocfilehash: 29830457b63f36dd401a412364060339344f35cb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347249"
---
# <a name="how-to-validate-using-xsd-linq-to-xml-c"></a><span data-ttu-id="c5147-102">Come eseguire la convalida utilizzando XSD (LINQ to XML)C#()</span><span class="sxs-lookup"><span data-stu-id="c5147-102">How to validate using XSD (LINQ to XML) (C#)</span></span>
<span data-ttu-id="c5147-103">Lo spazio dei nomi <xref:System.Xml.Schema> contiene metodi di estensione che semplificano la convalida di un albero XML rispetto a un file XSD (Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="c5147-103">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="c5147-104">Per altre informazioni, vedere la documentazione del metodo <xref:System.Xml.Schema.Extensions.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5147-104">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5147-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5147-105">Example</span></span>  
 <span data-ttu-id="c5147-106">Nell'esempio seguente viene creato un oggetto <xref:System.Xml.Schema.XmlSchemaSet>, quindi vengono convalidati due oggetti <xref:System.Xml.Linq.XDocument> rispetto al set di schemi.</span><span class="sxs-lookup"><span data-stu-id="c5147-106">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="c5147-107">Uno dei documenti è valido, l'altro non lo è.</span><span class="sxs-lookup"><span data-stu-id="c5147-107">One of the documents is valid, the other is not.</span></span>  
  
```csharp  
string xsdMarkup =  
    @"<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>  
       <xsd:element name='Root'>  
        <xsd:complexType>  
         <xsd:sequence>  
          <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>  
          <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>  
         </xsd:sequence>  
        </xsd:complexType>  
       </xsd:element>  
      </xsd:schema>";  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", XmlReader.Create(new StringReader(xsdMarkup)));  
  
XDocument doc1 = new XDocument(  
    new XElement("Root",  
        new XElement("Child1", "content1"),  
        new XElement("Child2", "content1")  
    )  
);  
  
XDocument doc2 = new XDocument(  
    new XElement("Root",  
        new XElement("Child1", "content1"),  
        new XElement("Child3", "content1")  
    )  
);  
  
Console.WriteLine("Validating doc1");  
bool errors = false;  
doc1.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("doc1 {0}", errors ? "did not validate" : "validated");  
  
Console.WriteLine();  
Console.WriteLine("Validating doc2");  
errors = false;  
doc2.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("doc2 {0}", errors ? "did not validate" : "validated");  
```  
  
 <span data-ttu-id="c5147-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c5147-108">This example produces the following output:</span></span>  
  
```output  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="c5147-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5147-109">Example</span></span>  
 <span data-ttu-id="c5147-110">L'esempio seguente verifica che il documento XML di [File XML di esempio: Customers e Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) sia valido per lo schema di [File XSD di esempio: Customers e Orders](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="c5147-110">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) is valid per the schema from [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="c5147-111">Viene quindi modificato il documento XML di origine.</span><span class="sxs-lookup"><span data-stu-id="c5147-111">It then modifies the source XML document.</span></span> <span data-ttu-id="c5147-112">Viene cambiato l'attributo `CustomerID` sul primo cliente.</span><span class="sxs-lookup"><span data-stu-id="c5147-112">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="c5147-113">Dopo la modifica, gli ordini faranno riferimento a un cliente che non esiste, quindi il documento XML non verrà più convalidato.</span><span class="sxs-lookup"><span data-stu-id="c5147-113">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="c5147-114">Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="c5147-114">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
 <span data-ttu-id="c5147-115">Questo esempio usa lo schema XSD seguente: [File XSD di esempio: Customers e Orders](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="c5147-115">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span>  
  
```csharp  
XmlSchemaSet schemas = new XmlSchemaSet();  
schemas.Add("", "CustomersOrders.xsd");  
  
Console.WriteLine("Attempting to validate");  
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");  
bool errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
  
Console.WriteLine();  
// Modify the source document so that it will not validate.  
custOrdDoc.Root.Element("Orders").Element("Order").Element("CustomerID").Value = "AAAAA";  
Console.WriteLine("Attempting to validate after modification");  
errors = false;  
custOrdDoc.Validate(schemas, (o, e) =>  
                     {  
                         Console.WriteLine("{0}", e.Message);  
                         errors = true;  
                     });  
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");  
```  
  
 <span data-ttu-id="c5147-116">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c5147-116">This example produces the following output:</span></span>  
  
```output  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5147-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5147-117">See also</span></span>

- <xref:System.Xml.Schema.Extensions.Validate%2A>
- [<span data-ttu-id="c5147-118">Creazione di alberi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="c5147-118">Creating XML Trees (C#)</span></span>](creating-xml-trees-linq-to-xml-2.md)
