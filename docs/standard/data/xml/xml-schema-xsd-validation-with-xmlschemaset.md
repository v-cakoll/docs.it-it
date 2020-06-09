---
title: Convalida di XML Schema (XSD) con XmlSchemaSet
description: Informazioni su come convalidare i documenti XML rispetto a uno schema di XML Schema Definition Language (XSD), usando una classe XmlSchemaSet in .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
ms.openlocfilehash: 995323d1882da13d45cdac516518d5b67845715a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594504"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="8446b-103">Convalida di XML Schema (XSD) con XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="8446b-103">XML schema (XSD) validation with XmlSchemaSet</span></span>

<span data-ttu-id="8446b-104">È possibile eseguire la convalida di documenti XML rispetto a uno schema XSD (XML Schema Definition Language) usando un tipo <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="8446b-104">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validate-xml-documents"></a><span data-ttu-id="8446b-105">Convalida di documenti XML</span><span class="sxs-lookup"><span data-stu-id="8446b-105">Validate XML documents</span></span>  
 <span data-ttu-id="8446b-106">I documenti XML vengono convalidati mediante il metodo <xref:System.Xml.XmlReader.Create%2A> della classe <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="8446b-106">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="8446b-107">Per convalidare un documento XML è necessario costruire un oggetto <xref:System.Xml.XmlReaderSettings> che contenga uno schema XSD (XML Schema Definition Language) con il quale convalidare il documento XML.</span><span class="sxs-lookup"><span data-stu-id="8446b-107">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8446b-108">Lo spazio dei nomi <xref:System.Xml.Schema> contiene metodi di estensione che semplificano la convalida di un albero XML rispetto a un file XSD quando si usano [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) e [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8446b-108">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span> <span data-ttu-id="8446b-109">Per ulteriori informazioni sulla convalida di documenti XML con LINQ to XML, vedere [How to Validate Using XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) e [How to: Validate using XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8446b-109">For more information on validating XML documents with LINQ to XML, see [How to validate using XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) and [How to: Validate Using XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span></span>
  
 <span data-ttu-id="8446b-110">È possibile aggiungere un singolo schema o un set di schemi (ad esempio <xref:System.Xml.Schema.XmlSchemaSet>) a un <xref:System.Xml.Schema.XmlSchemaSet> passandone uno come parametro al metodo <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> di <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="8446b-110">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="8446b-111">Quando si convalida un documento, lo spazio dei nomi di destinazione del documento deve corrispondere allo spazio dei nomi di destinazione dello schema nel set di schemi.</span><span class="sxs-lookup"><span data-stu-id="8446b-111">When validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="8446b-112">Di seguito viene riportato un esempio di documento XML.</span><span class="sxs-lookup"><span data-stu-id="8446b-112">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples #5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="8446b-113">Lo schema seguente convalida il documento XML di esempio.</span><span class="sxs-lookup"><span data-stu-id="8446b-113">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples #6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="8446b-114">Nell'esempio di codice seguente lo schema precedente viene aggiunto alla proprietà <xref:System.Xml.XmlReaderSettings.Schemas%2A> di  dell'oggetto <xref:System.Xml.XmlReaderSettings>.</span><span class="sxs-lookup"><span data-stu-id="8446b-114">In the code example that follows, the schema above is added to the <xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="8446b-115">L'oggetto <xref:System.Xml.XmlReaderSettings> viene passato come parametro al metodo <xref:System.Xml.XmlReader.Create%2A> dell'oggetto <xref:System.Xml.XmlReader> che convalida il documento XML precedente.</span><span class="sxs-lookup"><span data-stu-id="8446b-115">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="8446b-116">La proprietà <xref:System.Xml.XmlReaderSettings.ValidationType%2A> dell'oggetto <xref:System.Xml.XmlReaderSettings> è impostata su `Schema` per imporre la convalida del documento XML mediante il metodo <xref:System.Xml.XmlReader.Create%2A> dell'oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="8446b-116">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="8446b-117">Un tipo <xref:System.Xml.Schema.ValidationEventHandler> viene aggiunto all'oggetto <xref:System.Xml.XmlReaderSettings> per gestire qualunque evento <xref:System.Xml.Schema.XmlSeverityType.Warning> o <xref:System.Xml.Schema.XmlSeverityType.Error> generato da errori rilevati durante il processo di convalida del documento XML e dello schema.</span><span class="sxs-lookup"><span data-stu-id="8446b-117">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example #1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8446b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8446b-118">See also</span></span>

- [<span data-ttu-id="8446b-119">XmlSchemaSet per la compilazione di schemi</span><span class="sxs-lookup"><span data-stu-id="8446b-119">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="8446b-120">Utilizzo di schemi XML</span><span class="sxs-lookup"><span data-stu-id="8446b-120">Working with XML Schemas</span></span>](working-with-xml-schemas.md)
