---
title: Elaborazione di dati XML con il modello DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 56b6e9c7-ed82-4a65-a647-7be32c83bcc8
ms.openlocfilehash: 01ef4bef57b8a2e3e13f28a98adb21b111f3f4ed
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710453"
---
# <a name="process-xml-data-using-the-dom-model"></a><span data-ttu-id="4dfb3-102">Elaborazione di dati XML con il modello DOM</span><span class="sxs-lookup"><span data-stu-id="4dfb3-102">Process XML Data Using the DOM Model</span></span>
<span data-ttu-id="4dfb3-103">Il DOM (Document Object Model) XML considera i dati XML come un set standard di oggetti e viene usato per elaborare i dati XML in memoria.</span><span class="sxs-lookup"><span data-stu-id="4dfb3-103">The XML Document Object Model (DOM) treats XML data as a standard set of objects and is used to process XML data in memory.</span></span> <span data-ttu-id="4dfb3-104">Lo spazio dei nomi `System.Xml` fornisce una rappresentazione programmatica di documenti, frammenti, nodi o set di nodi XML.</span><span class="sxs-lookup"><span data-stu-id="4dfb3-104">The `System.Xml` namespace provides a programmatic representation of XML documents, fragments, nodes, or node-sets.</span></span> <span data-ttu-id="4dfb3-105">Si basa sulle raccomandazioni principali del World Wide Web Consortium (W3C) DOM Level 1 e DOM Level 2.</span><span class="sxs-lookup"><span data-stu-id="4dfb3-105">It is based on the World Wide Web Consortium (W3C) DOM Level 1 Core and the DOM Level 2 Core recommendations.</span></span>  
  
 <span data-ttu-id="4dfb3-106">La classe <xref:System.Xml.XmlDocument> rappresenta un documento XML.</span><span class="sxs-lookup"><span data-stu-id="4dfb3-106">The <xref:System.Xml.XmlDocument> class represents an XML document.</span></span> <span data-ttu-id="4dfb3-107">Include membri per il recupero e la creazione di tutti gli altri oggetti XML.</span><span class="sxs-lookup"><span data-stu-id="4dfb3-107">It includes members for retrieving and creating all other XML objects.</span></span> <span data-ttu-id="4dfb3-108">Usando la classe <xref:System.Xml.XmlDocument> e le classi correlate è possibile costruire documenti XML, caricare e accedere ai dati, modificare i dati e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="4dfb3-108">Using the <xref:System.Xml.XmlDocument>, and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4dfb3-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="4dfb3-109">In This Section</span></span>  
  
- [<span data-ttu-id="4dfb3-110">XML DOM (Document Object Model)</span><span class="sxs-lookup"><span data-stu-id="4dfb3-110">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)  
  
- [<span data-ttu-id="4dfb3-111">Tipi di nodi XML</span><span class="sxs-lookup"><span data-stu-id="4dfb3-111">Types of XML Nodes</span></span>](../../../../docs/standard/data/xml/types-of-xml-nodes.md)  
  
- [<span data-ttu-id="4dfb3-112">Gerarchia del modello a oggetti di documenti XML (Document Object Model, DOM)</span><span class="sxs-lookup"><span data-stu-id="4dfb3-112">XML Document Object Model (DOM) Hierarchy</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md)  
  
- [<span data-ttu-id="4dfb3-113">Mapping della gerarchia di oggetti in dati XML</span><span class="sxs-lookup"><span data-stu-id="4dfb3-113">Mapping the Object Hierarchy to XML Data</span></span>](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)  
  
- [<span data-ttu-id="4dfb3-114">Creazione di documenti XML</span><span class="sxs-lookup"><span data-stu-id="4dfb3-114">XML Document Creation</span></span>](../../../../docs/standard/data/xml/xml-document-creation.md)  
  
- [<span data-ttu-id="4dfb3-115">Lettura di un documento XML nel DOM</span><span class="sxs-lookup"><span data-stu-id="4dfb3-115">Reading an XML Document into the DOM</span></span>](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)  
  
- [<span data-ttu-id="4dfb3-116">Inserimento di nodi in un documento XML</span><span class="sxs-lookup"><span data-stu-id="4dfb3-116">Inserting Nodes into an XML Document</span></span>](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md)  
  
- [<span data-ttu-id="4dfb3-117">Rimozione di nodi, contenuto e valori da un documento XML</span><span class="sxs-lookup"><span data-stu-id="4dfb3-117">Removing Nodes, Content, and Values from an XML Document</span></span>](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md)  
  
- [<span data-ttu-id="4dfb3-118">Modifica di nodi, contenuto e valori in un documento XML</span><span class="sxs-lookup"><span data-stu-id="4dfb3-118">Modifying Nodes, Content, and Values in an XML Document</span></span>](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)  
  
- [<span data-ttu-id="4dfb3-119">Convalida di un documento XML nel DOM</span><span class="sxs-lookup"><span data-stu-id="4dfb3-119">Validating an XML Document in the DOM</span></span>](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
  
- [<span data-ttu-id="4dfb3-120">Salvataggio e scrittura di un documento</span><span class="sxs-lookup"><span data-stu-id="4dfb3-120">Saving and Writing a Document</span></span>](../../../../docs/standard/data/xml/saving-and-writing-a-document.md)  
  
- [<span data-ttu-id="4dfb3-121">Selezione di nodi utilizzando la navigazione XPath</span><span class="sxs-lookup"><span data-stu-id="4dfb3-121">Select Nodes Using XPath Navigation</span></span>](../../../../docs/standard/data/xml/select-nodes-using-xpath-navigation.md)  
  
- [<span data-ttu-id="4dfb3-122">Risoluzione di risorse esterne</span><span class="sxs-lookup"><span data-stu-id="4dfb3-122">Resolving External Resources</span></span>](../../../../docs/standard/data/xml/resolving-external-resources.md)  
  
- [<span data-ttu-id="4dfb3-123">Confronto di oggetti con XmlNameTable</span><span class="sxs-lookup"><span data-stu-id="4dfb3-123">Object Comparison Using XmlNameTable</span></span>](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)  
  
- [<span data-ttu-id="4dfb3-124">Raccolte di nodi in NamedNodeMaps e NodeLists</span><span class="sxs-lookup"><span data-stu-id="4dfb3-124">Node Collections in NamedNodeMaps and NodeLists</span></span>](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)  
  
- [<span data-ttu-id="4dfb3-125">Aggiornamenti dinamici di NodeLists e NamedNodeMaps</span><span class="sxs-lookup"><span data-stu-id="4dfb3-125">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>](../../../../docs/standard/data/xml/dynamic-updates-to-nodelists-and-namednodemaps.md)  
  
- [<span data-ttu-id="4dfb3-126">Supporto dello spazio dei nomi nel DOM</span><span class="sxs-lookup"><span data-stu-id="4dfb3-126">Namespace Support in the DOM</span></span>](../../../../docs/standard/data/xml/namespace-support-in-the-dom.md)  
  
- [<span data-ttu-id="4dfb3-127">Gestione degli eventi in un documento XML con XmlNodeChangedEventArgs</span><span class="sxs-lookup"><span data-stu-id="4dfb3-127">Event Handling in an XML Document Using the XmlNodeChangedEventArgs</span></span>](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)  
  
- [<span data-ttu-id="4dfb3-128">Estensione del DOM</span><span class="sxs-lookup"><span data-stu-id="4dfb3-128">Extending the DOM</span></span>](../../../../docs/standard/data/xml/extending-the-dom.md)  
  
## <a name="related-sections"></a><span data-ttu-id="4dfb3-129">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="4dfb3-129">Related Sections</span></span>  
 [<span data-ttu-id="4dfb3-130">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="4dfb3-130">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="4dfb3-131">Viene illustrata l'elaborazione XML usando la classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="4dfb3-131">Discusses XML processing using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
