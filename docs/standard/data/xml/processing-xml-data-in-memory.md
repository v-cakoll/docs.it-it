---
title: Elaborazione di dati XML in memoria
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: 2
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 1c451e4015e37c118f475ec1e7c099566e28767f
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="7514c-102">Elaborazione di dati XML in memoria</span><span class="sxs-lookup"><span data-stu-id="7514c-102">Processing XML Data In-Memory</span></span>
<span data-ttu-id="7514c-103">Microsoft .NET Framework include tre modelli per l'elaborazione dei dati XML: la classe <xref:System.Xml.XmlDocument>, la classe <xref:System.Xml.XPath.XPathDocument> e [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="7514c-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span>  
  
 <span data-ttu-id="7514c-104">La classe <xref:System.Xml.XmlDocument> consente l'implementazione delle raccomandazioni di base di livello 1 e 2 del modello DOM W3C.</span><span class="sxs-lookup"><span data-stu-id="7514c-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="7514c-105">Il modello DOM è una rappresentazione in memoria (cache) dell'albero di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="7514c-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="7514c-106">Usando la classe <xref:System.Xml.XmlDocument> e le classi correlate è possibile costruire documenti XML, caricare e accedere ai dati, modificare i dati e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7514c-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="7514c-107">La classe <xref:System.Xml.XPath.XPathDocument> è un archivio dati in memoria, di sola lettura, basato sul modello dati XPath.</span><span class="sxs-lookup"><span data-stu-id="7514c-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="7514c-108">La classe <xref:System.Xml.XPath.XPathNavigator> offre diverse opzioni di modifica e funzionalità di navigazione usando un modello di cursore sui documenti XML contenuti nella classe <xref:System.Xml.XPath.XPathDocument> di sola lettura, nonché nella classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="7514c-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="7514c-109">[LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) è il nuovo modello di elaborazione dei dati XML incluso in .NET Framework versione 3.5.</span><span class="sxs-lookup"><span data-stu-id="7514c-109">[LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="7514c-110">Si tratta di un modello di memoria che usa [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span><span class="sxs-lookup"><span data-stu-id="7514c-110">It is an in-memory model that leverages [LINQ (Language-Integrated Query)](https://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span></span> <span data-ttu-id="7514c-111">LINQ estende la sintassi dei linguaggi C# e Visual Basic offrendo nuove funzionalità di query.</span><span class="sxs-lookup"><span data-stu-id="7514c-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7514c-112">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="7514c-112">In This Section</span></span>  
 [<span data-ttu-id="7514c-113">Elaborare dati XML con il modello DOM</span><span class="sxs-lookup"><span data-stu-id="7514c-113">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="7514c-114">Viene illustrato l'uso della classe <xref:System.Xml.XmlDocument> e delle classi correlate per l'elaborazione dei dati XML.</span><span class="sxs-lookup"><span data-stu-id="7514c-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="7514c-115">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="7514c-115">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="7514c-116">Viene illustrato l'uso delle classi <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> e <xref:System.Xml.XPath.XPathNavigator> e delle classi correlate per l'elaborazione dei dati XML.</span><span class="sxs-lookup"><span data-stu-id="7514c-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="7514c-117">Elaborare dati XML con LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="7514c-117">Process XML Data Using LINQ to XML</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="7514c-118">Viene fornita una breve panoramica di LINQ to XML e sono elencati i collegamenti alla relativa documentazione.</span><span class="sxs-lookup"><span data-stu-id="7514c-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7514c-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="7514c-119">Related Sections</span></span>  
 [<span data-ttu-id="7514c-120">Documenti e dati XML</span><span class="sxs-lookup"><span data-stu-id="7514c-120">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
