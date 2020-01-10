---
title: Convalida di XML Schema (XSD) con XmlSchemaSet
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
ms.openlocfilehash: 6bd7525b77d4154193b57f8e6589cb865ace5fd6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709881"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="f1ac5-102">Convalida di XML Schema (XSD) con XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="f1ac5-102">XML Schema (XSD) Validation with XmlSchemaSet</span></span>
<span data-ttu-id="f1ac5-103">È possibile eseguire la convalida di documenti XML rispetto a uno schema XSD (XML Schema Definition Language) usando un tipo <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-103">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validating-xml-documents"></a><span data-ttu-id="f1ac5-104">Convalida di documenti XML</span><span class="sxs-lookup"><span data-stu-id="f1ac5-104">Validating XML Documents</span></span>  
 <span data-ttu-id="f1ac5-105">I documenti XML vengono convalidati mediante il metodo <xref:System.Xml.XmlReader.Create%2A> della classe <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-105">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="f1ac5-106">Per convalidare un documento XML è necessario costruire un oggetto <xref:System.Xml.XmlReaderSettings> che contenga uno schema XSD (XML Schema Definition Language) con il quale convalidare il documento XML.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-106">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1ac5-107">Lo spazio dei nomi <xref:System.Xml.Schema> contiene metodi di estensione che semplificano la convalida di un albero XML rispetto a un file XSD quando si usano [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) e [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f1ac5-107">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span> <span data-ttu-id="f1ac5-108">Per ulteriori informazioni sulla convalida di documenti XML con LINQ to XML, vedere [How to Validate Using XSD (LINQ to XML)C#()](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) e [How to: Validate Using XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f1ac5-108">For more information on validating XML documents with LINQ to XML, see [How to validate using XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) and [How to: Validate Using XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span></span>
  
 <span data-ttu-id="f1ac5-109">È possibile aggiungere un singolo schema o un set di schemi (ad esempio <xref:System.Xml.Schema.XmlSchemaSet>) a un <xref:System.Xml.Schema.XmlSchemaSet> passandone uno come parametro al metodo <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> di <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-109">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="f1ac5-110">Durante la convalida di un documento lo spazio dei nomi di destinazione del documento deve corrispondere allo spazio dei nomi di destinazione dello schema del set di schemi.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-110">Note that when validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="f1ac5-111">Di seguito viene riportato un esempio di documento XML.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-111">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="f1ac5-112">Lo schema seguente convalida il documento XML di esempio.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-112">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="f1ac5-113">Nell'esempio di codice seguente lo schema precedente viene aggiunto alla proprietà <xref:System.Xml.Schema.XmlSchemaSet> di <xref:System.Xml.XmlReaderSettings.Schemas%2A> dell'oggetto <xref:System.Xml.XmlReaderSettings>.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-113">In the code example that follows, the schema above is added to the <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="f1ac5-114">L'oggetto <xref:System.Xml.XmlReaderSettings> viene passato come parametro al metodo <xref:System.Xml.XmlReader.Create%2A> dell'oggetto <xref:System.Xml.XmlReader> che convalida il documento XML precedente.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-114">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="f1ac5-115">La proprietà <xref:System.Xml.XmlReaderSettings.ValidationType%2A> dell'oggetto <xref:System.Xml.XmlReaderSettings> è impostata su `Schema` per imporre la convalida del documento XML mediante il metodo <xref:System.Xml.XmlReader.Create%2A> dell'oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-115">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="f1ac5-116">Un tipo <xref:System.Xml.Schema.ValidationEventHandler> viene aggiunto all'oggetto <xref:System.Xml.XmlReaderSettings> per gestire qualunque evento <xref:System.Xml.Schema.XmlSeverityType.Warning> o <xref:System.Xml.Schema.XmlSeverityType.Error> generato da errori rilevati durante il processo di convalida del documento XML e dello schema.</span><span class="sxs-lookup"><span data-stu-id="f1ac5-116">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f1ac5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1ac5-117">See also</span></span>

- [<span data-ttu-id="f1ac5-118">XmlSchemaSet per la compilazione di schemi</span><span class="sxs-lookup"><span data-stu-id="f1ac5-118">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="f1ac5-119">Uso di schemi XML</span><span class="sxs-lookup"><span data-stu-id="f1ac5-119">Working with XML Schemas</span></span>](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
