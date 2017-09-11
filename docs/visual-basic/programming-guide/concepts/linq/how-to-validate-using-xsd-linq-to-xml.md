---
title: 'Procedura: eseguire la convalida tramite XSD (LINQ to XML) (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: a0fe88d4-4e77-49e7-90de-8953feeccc21
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d791bcb47243f1b9b2580617c7881d77b11aef1d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-validate-using-xsd-linq-to-xml-visual-basic"></a><span data-ttu-id="8a59f-102">Procedura: eseguire la convalida tramite XSD (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a59f-102">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="8a59f-103">Il <xref:System.Xml.Schema>dello spazio dei nomi contiene metodi di estensione che semplificano la convalida di un albero XML rispetto a un file XML Schema Definition Language (XSD).</xref:System.Xml.Schema></span><span class="sxs-lookup"><span data-stu-id="8a59f-103">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="8a59f-104">Per ulteriori informazioni, vedere il <xref:System.Xml.Schema.Extensions.Validate%2A>documentazione relativa al metodo.</xref:System.Xml.Schema.Extensions.Validate%2A></span><span class="sxs-lookup"><span data-stu-id="8a59f-104">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a59f-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a59f-105">Example</span></span>  
 <span data-ttu-id="8a59f-106">Nell'esempio seguente viene creato un <xref:System.Xml.Schema.XmlSchemaSet>, quindi vengono convalidati due <xref:System.Xml.Linq.XDocument>oggetti rispetto allo schema.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Schema.XmlSchemaSet></span><span class="sxs-lookup"><span data-stu-id="8a59f-106">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="8a59f-107">Uno dei documenti è valido, l'altro non lo è.</span><span class="sxs-lookup"><span data-stu-id="8a59f-107">One of the documents is valid, the other is not.</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim xsdMarkup As XElement = _  
        <xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>  
            <xsd:element name='Root'>  
                <xsd:complexType>  
                    <xsd:sequence>  
                        <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>  
                        <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>  
                    </xsd:sequence>  
                </xsd:complexType>  
            </xsd:element>  
        </xsd:schema>  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", xsdMarkup.CreateReader)  
  
    Dim doc1 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child2>content1</Child2>  
        </Root>  
  
    Dim doc2 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child3>content1</Child3>  
        </Root>  
  
    Console.WriteLine("Validating doc1")  
    errors = False  
    doc1.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc1 {0}", IIf(errors = True, "did not validate", "validated"))  
  
    Console.WriteLine()  
    Console.WriteLine("Validating doc2")  
    errors = False  
    doc2.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc2 {0}", IIf(errors = True, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="8a59f-108">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8a59f-108">This example produces the following output:</span></span>  
  
```  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="8a59f-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="8a59f-109">Example</span></span>  
 <span data-ttu-id="8a59f-110">Nell'esempio seguente verifica che il documento XML da [File XML di esempio: Customers e Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) è valido per lo schema di [File XSD di esempio: Customers e Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="8a59f-110">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) is valid per the schema from [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="8a59f-111">Viene quindi modificato il documento XML di origine.</span><span class="sxs-lookup"><span data-stu-id="8a59f-111">It then modifies the source XML document.</span></span> <span data-ttu-id="8a59f-112">Viene cambiato l'attributo `CustomerID` sul primo cliente.</span><span class="sxs-lookup"><span data-stu-id="8a59f-112">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="8a59f-113">Dopo la modifica, gli ordini faranno riferimento a un cliente che non esiste, quindi il documento XML non verrà più convalidato.</span><span class="sxs-lookup"><span data-stu-id="8a59f-113">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="8a59f-114">In questo esempio viene utilizzato il documento XML seguente: [File XML di esempio: Customers e Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8a59f-114">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="8a59f-115">Questo esempio viene utilizzato lo schema XSD seguente: [File XSD di esempio: Customers e Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="8a59f-115">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", "CustomersOrders.xsd")  
  
    Console.WriteLine("Attempting to validate")  
    Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
  
    Console.WriteLine()  
    ' Modify the source document so that it will not validate.  
    custOrdDoc.<Root>.<Orders>.<Order>.<CustomerID>(0).Value = "AAAAA"  
    Console.WriteLine("Attempting to validate after modification")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="8a59f-116">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8a59f-116">This example produces the following output:</span></span>  
  
```  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a59f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a59f-117">See Also</span></span>  
 <span data-ttu-id="8a59f-118"><xref:System.Xml.Schema.Extensions.Validate%2A></xref:System.Xml.Schema.Extensions.Validate%2A></span><span class="sxs-lookup"><span data-stu-id="8a59f-118"><xref:System.Xml.Schema.Extensions.Validate%2A></span></span>   
<span data-ttu-id="8a59f-119"> [Creazione di strutture ad albero XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)</span><span class="sxs-lookup"><span data-stu-id="8a59f-119"> [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)</span></span>
