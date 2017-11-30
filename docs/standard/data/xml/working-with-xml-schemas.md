---
title: Utilizzo di schemi XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e21d402dce02ecb332d041f0cda651df911979ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-xml-schemas"></a><span data-ttu-id="395d9-102">Utilizzo di schemi XML</span><span class="sxs-lookup"><span data-stu-id="395d9-102">Working with XML Schemas</span></span>
<span data-ttu-id="395d9-103">Per definire la struttura di un documento XML, oltre alle relazioni dei suoi elementi, i tipi di dati e i vincoli di contenuto, si usa una DTD (Document Type Definition, definizione del tipo di documento) o uno schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="395d9-103">To define the structure of an XML document, as well as its element relationships, data types, and content constraints, you use a document type definition (DTD) or XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="395d9-104">Sebbene un documento XML venga considerato in formato corretto se soddisfa tutti i requisiti sintattici definiti dalla raccomandazione W3C (World Wide Web Consortium) Extensible Markup Language (XML) 1.0, non viene ritenuto valido a meno che non sia in formato corretto e conforme ai vincoli definiti dalla relativa DTD o dal relativo schema.</span><span class="sxs-lookup"><span data-stu-id="395d9-104">Although an XML document is considered to be well-formed if it meets all the syntactical requirements defined by the World Wide Web Consortium (W3C) Extensible Markup Language (XML) 1.0 Recommendation, it is not considered valid unless it is both well-formed and conforms to the constraints defined by its DTD or schema.</span></span> <span data-ttu-id="395d9-105">Pertanto, anche se tutti i documenti XML validi sono in formato corretto, non tutti i documenti XML in formato corretto sono validi.</span><span class="sxs-lookup"><span data-stu-id="395d9-105">Therefore, although all valid XML documents are well-formed, not all well-formed XML documents are valid.</span></span>  
  
 <span data-ttu-id="395d9-106">Per ulteriori informazioni su XML, vedere il [raccomandazione W3C XML 1.0](http://go.microsoft.com/fwlink/?linkid=7269).</span><span class="sxs-lookup"><span data-stu-id="395d9-106">For more information about XML, see the [W3C XML 1.0 Recommendation](http://go.microsoft.com/fwlink/?linkid=7269).</span></span> <span data-ttu-id="395d9-107">Per ulteriori informazioni sul XML Schema, vedere il [W3C XML Schema Part 1: Structures Recommendation](http://go.microsoft.com/fwlink/?linkid=48881) e [W3C XML Schema Part 2: Datatypes Recommendation](http://go.microsoft.com/fwlink/?linkid=17392) indicazioni.</span><span class="sxs-lookup"><span data-stu-id="395d9-107">For more information about XML Schema, see the [W3C XML Schema Part 1: Structures Recommendation](http://go.microsoft.com/fwlink/?linkid=48881) and the [W3C XML Schema Part 2: Datatypes Recommendation](http://go.microsoft.com/fwlink/?linkid=17392) recommendations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="395d9-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="395d9-108">In This Section</span></span>  
 [<span data-ttu-id="395d9-109">SOM (Schema Object Model) XML</span><span class="sxs-lookup"><span data-stu-id="395d9-109">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 <span data-ttu-id="395d9-110">Viene illustrato il modello SOM (Schema Object Model) nello spazio dei nomi <xref:System.Xml.Schema?displayProperty=nameWithType>, che fornisce un set di classi che consente di leggere lo schema XSD da un file oppure di creare a livello di codice uno schema in memoria.</span><span class="sxs-lookup"><span data-stu-id="395d9-110">Discusses the Schema Object Model (SOM) in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that provides a set of classes that allows you to read a Schema definition language (XSD) schema from a file or programmatically create a schema in-memory.</span></span>  
  
 [<span data-ttu-id="395d9-111">XmlSchemaSet per la compilazione dello Schema</span><span class="sxs-lookup"><span data-stu-id="395d9-111">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 <span data-ttu-id="395d9-112">Viene illustrata la classe <xref:System.Xml.Schema.XmlSchemaSet>, ovvero una cache in cui possono essere archiviati e convalidati gli schemi XSD.</span><span class="sxs-lookup"><span data-stu-id="395d9-112">Discusses the <xref:System.Xml.Schema.XmlSchemaSet> class that is a cache where XSD schemas can be stored and validated.</span></span>  
  
 [<span data-ttu-id="395d9-113">Convalida basata sul metodo Push di XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="395d9-113">XmlSchemaValidator Push-Based Validation</span></span>](../../../../docs/standard/data/xml/xmlschemavalidator-push-based-validation.md)  
 <span data-ttu-id="395d9-114">Viene illustrata la classe <xref:System.Xml.Schema.XmlSchemaValidator> che fornisce un meccanismo efficiente e a elevate prestazioni per la convalida basata sul metodo push di dati XML in base a schemi XSD.</span><span class="sxs-lookup"><span data-stu-id="395d9-114">Discusses the <xref:System.Xml.Schema.XmlSchemaValidator> class that provides an efficient, high-performance mechanism to validate XML data against XSD schemas in a push-based manner.</span></span>  
  
 [<span data-ttu-id="395d9-115">Deduzione di uno Schema XML</span><span class="sxs-lookup"><span data-stu-id="395d9-115">Inferring an XML Schema</span></span>](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 <span data-ttu-id="395d9-116">Viene illustrato come usare la classe <xref:System.Xml.Schema.XmlSchemaInference> per inferire uno schema XSD dalla struttura di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="395d9-116">Discusses how to use the <xref:System.Xml.Schema.XmlSchemaInference> class to infer an XSD schema from the structure of an XML document.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="395d9-117">Riferimento</span><span class="sxs-lookup"><span data-stu-id="395d9-117">Reference</span></span>  
 <span data-ttu-id="395d9-118"><xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="395d9-118"><xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader></span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="395d9-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="395d9-119">Related Sections</span></span>  
 [<span data-ttu-id="395d9-120">Convalida di un documento XML nel DOM</span><span class="sxs-lookup"><span data-stu-id="395d9-120">Validating an XML Document in the DOM</span></span>](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 <span data-ttu-id="395d9-121">Viene illustrato come convalidare il documento XML nel DOM (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="395d9-121">Discusses how to validate the XML in the Document Object Model (DOM).</span></span> <span data-ttu-id="395d9-122">È possibile convalidare il documento XML quando viene caricato nel DOM oppure convalidare un documento non convalidato in precedenza nel DOM.</span><span class="sxs-lookup"><span data-stu-id="395d9-122">You can validate the XML as it is loaded into the DOM, or validate a previously unvalidated XML document in the DOM.</span></span>  
  
 [<span data-ttu-id="395d9-123">Convalida dello schema con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="395d9-123">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 <span data-ttu-id="395d9-124">Viene illustrato come convalidare il documento XML esplorato e modificato usando la classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="395d9-124">Discusses how to validate XML being navigated and edited using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
