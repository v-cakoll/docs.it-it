---
title: Tipi di nodo riconosciuti con le query XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
ms.openlocfilehash: cc1aa668ccf6fc7f210f48a28cf76b364459c784
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710544"
---
# <a name="node-types-recognized-with-xpath-queries"></a><span data-ttu-id="7b89c-102">Tipi di nodo riconosciuti con le query XPath</span><span class="sxs-lookup"><span data-stu-id="7b89c-102">Node Types Recognized with XPath Queries</span></span>
<span data-ttu-id="7b89c-103">I tipi di nodi riconosciuti in una query XPath non corrispondono a quelli del DOM (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="7b89c-103">The types of nodes recognized in an XPath query are not the same node types found in the Document Object Model (DOM).</span></span>  
  
## <a name="w3c-xpath-node-types"></a><span data-ttu-id="7b89c-104">Tipi di nodo XPath W3C</span><span class="sxs-lookup"><span data-stu-id="7b89c-104">W3C XPath Node Types</span></span>  
 <span data-ttu-id="7b89c-105">I tipi di nodo riconosciuti in una query XPath non corrispondono a quelli del DOM (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="7b89c-105">The types of nodes recognized in an XPath query are not the types of nodes found in the Document Object Model (DOM).</span></span> <span data-ttu-id="7b89c-106">Di seguito sono riportati i tipi di nodo XPath rappresentati dall'enumerazione <xref:System.Xml.XPath.XPathNodeType>.</span><span class="sxs-lookup"><span data-stu-id="7b89c-106">The following are the XPath node types represented by the <xref:System.Xml.XPath.XPathNodeType> enumeration.</span></span>  
  
- <xref:System.Xml.XPath.XPathNodeType.All>  
  
- <xref:System.Xml.XPath.XPathNodeType.Attribute>  
  
- <xref:System.Xml.XPath.XPathNodeType.Comment>  
  
- <xref:System.Xml.XPath.XPathNodeType.Element>  
  
- <xref:System.Xml.XPath.XPathNodeType.Namespace>  
  
- <xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>  
  
- <xref:System.Xml.XPath.XPathNodeType.Root>  
  
- <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>  
  
- <xref:System.Xml.XPath.XPathNodeType.Text>  
  
- <xref:System.Xml.XPath.XPathNodeType.Whitespace>  
  
 <span data-ttu-id="7b89c-107">Questi tipi di nodo sono basati sul modello dati XPath, dove i nodi derivano dal set di informazioni XML.</span><span class="sxs-lookup"><span data-stu-id="7b89c-107">These node types are based on the XPath data model, where the nodes are derived from the XML Information Set.</span></span> <span data-ttu-id="7b89c-108">I tipi di nodo <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> e <xref:System.Xml.XPath.XPathNodeType.Whitespace> sono estensioni Microsoft .NET Framework dei tipi di nodi di base descritti nel modello dati XPath.</span><span class="sxs-lookup"><span data-stu-id="7b89c-108">The <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> and <xref:System.Xml.XPath.XPathNodeType.Whitespace> node types are Microsoft .NET Framework extensions to the base node types described in the XPath data model.</span></span>  
  
 <span data-ttu-id="7b89c-109">Il tipo di nodo Attribute viene usato in modo diverso nel modello dati XPath rispetto al DOM.</span><span class="sxs-lookup"><span data-stu-id="7b89c-109">The attribute node type is used differently in the XPath data model than it is in the DOM.</span></span> <span data-ttu-id="7b89c-110">Nel modello dati XPath il nodo di tipo element è composto da un set di nodi Attribute a esso correlati e il nodo di tipo element è il padre di ogni nodo Attribute.</span><span class="sxs-lookup"><span data-stu-id="7b89c-110">In the XPath data model, the element node has a set of attribute nodes related to it and the element node is the parent of each attribute node.</span></span> <span data-ttu-id="7b89c-111">Nel DOM, tuttavia, il nodo di tipo element è il proprietario e non il padre.</span><span class="sxs-lookup"><span data-stu-id="7b89c-111">However, in the DOM, the element node is the owner and not the parent.</span></span> <span data-ttu-id="7b89c-112">In entrambi i modelli, i nodi Attribute e Namespace non sono considerati nodi figlio del nodo di tipo element.</span><span class="sxs-lookup"><span data-stu-id="7b89c-112">In both models, attribute and namespace nodes are not considered child nodes of the element node.</span></span>  
  
 <span data-ttu-id="7b89c-113">Il tipo di nodo Namespace è un'aggiunta al modello dati XPath e non è un tipo di nodo DOM riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7b89c-113">The namespace node type is an addition to the XPath data model and is not a recognized DOM node type.</span></span>  
  
 <span data-ttu-id="7b89c-114">Per altre informazioni sulla navigazione dei nodi di elementi, attributi e spazi dei nomi, vedere gli argomenti [Navigazione del set di nodi con XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) e [Navigazione dei nodi di attributi e dello spazio dei nomi con XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="7b89c-114">For more information about navigating element, attribute, and namespace nodes, see the [Node Set Navigation Using XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) and [Attribute and Namespace Node Navigation Using XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md) topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b89c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b89c-115">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="7b89c-116">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="7b89c-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="7b89c-117">Selezionare dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7b89c-117">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="7b89c-118">Valutare espressioni XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7b89c-118">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="7b89c-119">Corrispondenza di nodi con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="7b89c-119">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="7b89c-120">Query e spazi dei nomi XPath</span><span class="sxs-lookup"><span data-stu-id="7b89c-120">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [<span data-ttu-id="7b89c-121">Espressioni XPath compilate</span><span class="sxs-lookup"><span data-stu-id="7b89c-121">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
