---
title: Tipi di nodo riconosciuti con le query XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
ms.openlocfilehash: b9fc55b11455491406970af2a9232b277160875f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288732"
---
# <a name="node-types-recognized-with-xpath-queries"></a><span data-ttu-id="26a95-102">Tipi di nodo riconosciuti con le query XPath</span><span class="sxs-lookup"><span data-stu-id="26a95-102">Node Types Recognized with XPath Queries</span></span>
<span data-ttu-id="26a95-103">I tipi di nodi riconosciuti in una query XPath non corrispondono a quelli del DOM (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="26a95-103">The types of nodes recognized in an XPath query are not the same node types found in the Document Object Model (DOM).</span></span>  
  
## <a name="w3c-xpath-node-types"></a><span data-ttu-id="26a95-104">Tipi di nodo XPath W3C</span><span class="sxs-lookup"><span data-stu-id="26a95-104">W3C XPath Node Types</span></span>  
 <span data-ttu-id="26a95-105">I tipi di nodo riconosciuti in una query XPath non corrispondono a quelli del DOM (Document Object Model).</span><span class="sxs-lookup"><span data-stu-id="26a95-105">The types of nodes recognized in an XPath query are not the types of nodes found in the Document Object Model (DOM).</span></span> <span data-ttu-id="26a95-106">Di seguito sono riportati i tipi di nodo XPath rappresentati dall'enumerazione <xref:System.Xml.XPath.XPathNodeType>.</span><span class="sxs-lookup"><span data-stu-id="26a95-106">The following are the XPath node types represented by the <xref:System.Xml.XPath.XPathNodeType> enumeration.</span></span>  
  
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
  
 <span data-ttu-id="26a95-107">Questi tipi di nodo sono basati sul modello dati XPath, dove i nodi derivano dal set di informazioni XML.</span><span class="sxs-lookup"><span data-stu-id="26a95-107">These node types are based on the XPath data model, where the nodes are derived from the XML Information Set.</span></span> <span data-ttu-id="26a95-108">I tipi di nodo <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> e <xref:System.Xml.XPath.XPathNodeType.Whitespace> sono estensioni Microsoft .NET Framework dei tipi di nodi di base descritti nel modello dati XPath.</span><span class="sxs-lookup"><span data-stu-id="26a95-108">The <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> and <xref:System.Xml.XPath.XPathNodeType.Whitespace> node types are Microsoft .NET Framework extensions to the base node types described in the XPath data model.</span></span>  
  
 <span data-ttu-id="26a95-109">Il tipo di nodo Attribute viene usato in modo diverso nel modello dati XPath rispetto al DOM.</span><span class="sxs-lookup"><span data-stu-id="26a95-109">The attribute node type is used differently in the XPath data model than it is in the DOM.</span></span> <span data-ttu-id="26a95-110">Nel modello dati XPath il nodo di tipo element è composto da un set di nodi Attribute a esso correlati e il nodo di tipo element è il padre di ogni nodo Attribute.</span><span class="sxs-lookup"><span data-stu-id="26a95-110">In the XPath data model, the element node has a set of attribute nodes related to it and the element node is the parent of each attribute node.</span></span> <span data-ttu-id="26a95-111">Nel DOM, tuttavia, il nodo di tipo element è il proprietario e non il padre.</span><span class="sxs-lookup"><span data-stu-id="26a95-111">However, in the DOM, the element node is the owner and not the parent.</span></span> <span data-ttu-id="26a95-112">In entrambi i modelli, i nodi Attribute e Namespace non sono considerati nodi figlio del nodo di tipo element.</span><span class="sxs-lookup"><span data-stu-id="26a95-112">In both models, attribute and namespace nodes are not considered child nodes of the element node.</span></span>  
  
 <span data-ttu-id="26a95-113">Il tipo di nodo Namespace è un'aggiunta al modello dati XPath e non è un tipo di nodo DOM riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="26a95-113">The namespace node type is an addition to the XPath data model and is not a recognized DOM node type.</span></span>  
  
 <span data-ttu-id="26a95-114">Per altre informazioni sulla navigazione dei nodi di elementi, attributi e spazi dei nomi, vedere gli argomenti [Navigazione del set di nodi con XPathNavigator](node-set-navigation-using-xpathnavigator.md) e [Navigazione dei nodi di attributi e dello spazio dei nomi con XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="26a95-114">For more information about navigating element, attribute, and namespace nodes, see the [Node Set Navigation Using XPathNavigator](node-set-navigation-using-xpathnavigator.md) and [Attribute and Namespace Node Navigation Using XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md) topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26a95-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26a95-115">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="26a95-116">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="26a95-116">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="26a95-117">Selezione di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="26a95-117">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="26a95-118">Valutazione di espressioni XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="26a95-118">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="26a95-119">Corrispondenza di nodi utilizzando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="26a95-119">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="26a95-120">Query e spazi dei nomi XPath</span><span class="sxs-lookup"><span data-stu-id="26a95-120">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)
- [<span data-ttu-id="26a95-121">Espressioni XPath compilate</span><span class="sxs-lookup"><span data-stu-id="26a95-121">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)
