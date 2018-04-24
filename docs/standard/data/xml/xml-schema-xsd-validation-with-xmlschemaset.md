---
title: Convalida di XML Schema (XSD) con XmlSchemaSet
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
caps.latest.revision: 3
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f18852411d733d12bcbbdba2b64bc2f134ea061c
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="ec85b-102">Convalida di XML Schema (XSD) con XmlSchemaSet</span><span class="sxs-lookup"><span data-stu-id="ec85b-102">XML Schema (XSD) Validation with XmlSchemaSet</span></span>
<span data-ttu-id="ec85b-103">È possibile eseguire la convalida di documenti XML rispetto a uno schema XSD (XML Schema Definition Language) usando un tipo <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="ec85b-103">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validating-xml-documents"></a><span data-ttu-id="ec85b-104">Convalida di documenti XML</span><span class="sxs-lookup"><span data-stu-id="ec85b-104">Validating XML Documents</span></span>  
 <span data-ttu-id="ec85b-105">I documenti XML vengono convalidati mediante il metodo <xref:System.Xml.XmlReader.Create%2A> della classe <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="ec85b-105">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="ec85b-106">Per convalidare un documento XML è necessario costruire un oggetto <xref:System.Xml.XmlReaderSettings> che contenga uno schema XSD (XML Schema Definition Language) con il quale convalidare il documento XML.</span><span class="sxs-lookup"><span data-stu-id="ec85b-106">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec85b-107">Lo spazio dei nomi <xref:System.Xml.Schema> contiene metodi di estensione che semplificano la convalida di un albero XML rispetto a un file XSD quando si usa [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="ec85b-107">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span> <span data-ttu-id="ec85b-108">Per altre informazioni sulla convalida di documenti XML con LINQ to XML, vedere [Procedura: Eseguire la convalida tramite XSD](https://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b).</span><span class="sxs-lookup"><span data-stu-id="ec85b-108">For more information on validating XML documents with LINQ to XML, see [How to: Validate Using XSD](https://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b).</span></span>  
  
 <span data-ttu-id="ec85b-109">È possibile aggiungere un singolo schema o un set di schemi (ad esempio <xref:System.Xml.Schema.XmlSchemaSet>) a un <xref:System.Xml.Schema.XmlSchemaSet> passandone uno come parametro al metodo <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> di <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="ec85b-109">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="ec85b-110">Durante la convalida di un documento lo spazio dei nomi di destinazione del documento deve corrispondere allo spazio dei nomi di destinazione dello schema del set di schemi.</span><span class="sxs-lookup"><span data-stu-id="ec85b-110">Note that when validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="ec85b-111">Di seguito viene riportato un esempio di documento XML.</span><span class="sxs-lookup"><span data-stu-id="ec85b-111">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="ec85b-112">Lo schema seguente convalida il documento XML di esempio.</span><span class="sxs-lookup"><span data-stu-id="ec85b-112">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="ec85b-113">Nell'esempio di codice seguente lo schema precedente viene aggiunto alla proprietà <xref:System.Xml.Schema.XmlSchemaSet> di <xref:System.Xml.XmlReaderSettings.Schemas%2A> dell'oggetto <xref:System.Xml.XmlReaderSettings>.</span><span class="sxs-lookup"><span data-stu-id="ec85b-113">In the code example that follows, the schema above is added to the <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="ec85b-114">L'oggetto <xref:System.Xml.XmlReaderSettings> viene passato come parametro al metodo <xref:System.Xml.XmlReader.Create%2A> dell'oggetto <xref:System.Xml.XmlReader> che convalida il documento XML precedente.</span><span class="sxs-lookup"><span data-stu-id="ec85b-114">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="ec85b-115">La proprietà <xref:System.Xml.XmlReaderSettings.ValidationType%2A> dell'oggetto <xref:System.Xml.XmlReaderSettings> è impostata su `Schema` per imporre la convalida del documento XML mediante il metodo <xref:System.Xml.XmlReader.Create%2A> dell'oggetto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="ec85b-115">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="ec85b-116">Un tipo <xref:System.Xml.Schema.ValidationEventHandler> viene aggiunto all'oggetto <xref:System.Xml.XmlReaderSettings> per gestire qualunque evento <xref:System.Xml.Schema.XmlSeverityType.Warning> o <xref:System.Xml.Schema.XmlSeverityType.Error> generato da errori rilevati durante il processo di convalida del documento XML e dello schema.</span><span class="sxs-lookup"><span data-stu-id="ec85b-116">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ec85b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec85b-117">See Also</span></span>  
 [<span data-ttu-id="ec85b-118">XmlSchemaSet per la compilazione di schemi</span><span class="sxs-lookup"><span data-stu-id="ec85b-118">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [<span data-ttu-id="ec85b-119">Uso di schemi XML</span><span class="sxs-lookup"><span data-stu-id="ec85b-119">Working with XML Schemas</span></span>](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
