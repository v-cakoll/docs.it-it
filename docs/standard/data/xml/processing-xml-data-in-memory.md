---
title: Elaborazione di dati XML in memoria
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ec4ccbff095071b279e07cee6a1aab3ca830423f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="0ae4d-102">Elaborazione di dati XML in memoria</span><span class="sxs-lookup"><span data-stu-id="0ae4d-102">Processing XML Data In-Memory</span></span>
<span data-ttu-id="0ae4d-103">Microsoft .NET Framework include tre modelli per l'elaborazione dati XML: il <xref:System.Xml.XmlDocument> (classe), il <xref:System.Xml.XPath.XPathDocument> (classe), e [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="0ae4d-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span>  
  
 <span data-ttu-id="0ae4d-104">La classe <xref:System.Xml.XmlDocument> consente l'implementazione delle raccomandazioni di base di livello 1 e 2 del modello DOM W3C.</span><span class="sxs-lookup"><span data-stu-id="0ae4d-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="0ae4d-105">Il modello DOM è una rappresentazione in memoria (cache) dell'albero di un documento XML.</span><span class="sxs-lookup"><span data-stu-id="0ae4d-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="0ae4d-106">Usando la classe <xref:System.Xml.XmlDocument> e le classi correlate è possibile costruire documenti XML, caricare e accedere ai dati, modificare i dati e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="0ae4d-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="0ae4d-107">La classe <xref:System.Xml.XPath.XPathDocument> è un archivio dati in memoria, di sola lettura, basato sul modello dati XPath.</span><span class="sxs-lookup"><span data-stu-id="0ae4d-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="0ae4d-108">La classe <xref:System.Xml.XPath.XPathNavigator> offre diverse opzioni di modifica e funzionalità di navigazione usando un modello di cursore sui documenti XML contenuti nella classe <xref:System.Xml.XPath.XPathDocument> di sola lettura, nonché nella classe <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="0ae4d-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="0ae4d-109">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) è il nuovo modello di .NET Framework versione 3.5 per l'elaborazione dati XML.</span><span class="sxs-lookup"><span data-stu-id="0ae4d-109">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="0ae4d-110">Si tratta di un modello in memoria che sfrutta [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span><span class="sxs-lookup"><span data-stu-id="0ae4d-110">It is an in-memory model that leverages [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span></span> <span data-ttu-id="0ae4d-111">LINQ estende la sintassi dei linguaggi C# e Visual Basic offrendo nuove funzionalità di query.</span><span class="sxs-lookup"><span data-stu-id="0ae4d-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ae4d-112">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0ae4d-112">In This Section</span></span>  
 [<span data-ttu-id="0ae4d-113">Elaborazione di dati XML con il modello DOM</span><span class="sxs-lookup"><span data-stu-id="0ae4d-113">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="0ae4d-114">Viene illustrato l'uso della classe <xref:System.Xml.XmlDocument> e delle classi correlate per l'elaborazione dei dati XML.</span><span class="sxs-lookup"><span data-stu-id="0ae4d-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="0ae4d-115">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="0ae4d-115">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="0ae4d-116">Viene illustrato l'uso delle classi <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument> e <xref:System.Xml.XPath.XPathNavigator> e delle classi correlate per l'elaborazione dei dati XML.</span><span class="sxs-lookup"><span data-stu-id="0ae4d-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="0ae4d-117">Elaborazione di dati XML utilizzando LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="0ae4d-117">Process XML Data Using LINQ to XML</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="0ae4d-118">Viene fornita una breve panoramica di LINQ to XML e sono elencati i collegamenti alla relativa documentazione.</span><span class="sxs-lookup"><span data-stu-id="0ae4d-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="0ae4d-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="0ae4d-119">Related Sections</span></span>  
 [<span data-ttu-id="0ae4d-120">Documenti e dati XML</span><span class="sxs-lookup"><span data-stu-id="0ae4d-120">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
