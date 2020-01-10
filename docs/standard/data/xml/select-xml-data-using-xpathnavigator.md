---
title: Selezione di dati XML con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: c268c49e-32b9-4171-b782-dcb7b065fa73
ms.openlocfilehash: 99b6b3b6959abf4c8adc313364ad641249bd9bc3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710167"
---
# <a name="select-xml-data-using-xpathnavigator"></a><span data-ttu-id="ac187-102">Selezione di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ac187-102">Select XML Data Using XPathNavigator</span></span>
<span data-ttu-id="ac187-103">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce un set di metodi usato per selezionare un set di nodi in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> usando un'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="ac187-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span> <span data-ttu-id="ac187-104">È possibile scorrere il set di nodi dopo averlo selezionato.</span><span class="sxs-lookup"><span data-stu-id="ac187-104">Once selected, you can iterate over the selected set of nodes.</span></span>  
  
## <a name="xpathnavigator-selection-methods"></a><span data-ttu-id="ac187-105">Metodi di selezione di XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ac187-105">XPathNavigator Selection Methods</span></span>  
 <span data-ttu-id="ac187-106">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce un set di metodi usato per selezionare un set di nodi in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> usando un'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="ac187-106">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span> <span data-ttu-id="ac187-107">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce inoltre un set di metodi ottimizzati per selezionare più velocemente i nodi progenitore, figlio e discendente anziché usare un'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="ac187-107">The <xref:System.Xml.XPath.XPathNavigator> class also provides a set of optimized methods for selecting ancestor, child and descendant nodes faster than using an XPath expression.</span></span> <span data-ttu-id="ac187-108">Nel caso di un singolo nodo selezionato, il set di nodi selezionato viene restituito in un oggetto <xref:System.Xml.XPath.XPathNodeIterator> o <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="ac187-108">The selected set of nodes is returned in an <xref:System.Xml.XPath.XPathNodeIterator> object or an <xref:System.Xml.XPath.XPathNavigator> object in the case of a single selected node.</span></span>  
  
### <a name="selecting-nodes-using-xpath-expressions"></a><span data-ttu-id="ac187-109">Selezione di nodi con le espressioni XPath</span><span class="sxs-lookup"><span data-stu-id="ac187-109">Selecting Nodes Using XPath Expressions</span></span>  
 <span data-ttu-id="ac187-110">Per selezionare un set di nodi usando un'espressione XPath, usare uno dei seguenti metodi di selezione.</span><span class="sxs-lookup"><span data-stu-id="ac187-110">To select a set of nodes using an XPath expression, use one of the following selection methods.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 <span data-ttu-id="ac187-111">Nel caso di un singolo nodo selezionato, se chiamati, questi metodi restituiscono un set di nodi che può essere esplorato liberamente usando un oggetto <xref:System.Xml.XPath.XPathNodeIterator> o <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="ac187-111">When called, these methods return a set of nodes that you can navigate freely using an <xref:System.Xml.XPath.XPathNodeIterator> object or an <xref:System.Xml.XPath.XPathNavigator> object in the case of a single selected node.</span></span>  
  
 <span data-ttu-id="ac187-112">L'esplorazione di un oggetto <xref:System.Xml.XPath.XPathNodeIterator> non influisce sulla posizione dell'oggetto <xref:System.Xml.XPath.XPathNavigator> usato per crearlo.</span><span class="sxs-lookup"><span data-stu-id="ac187-112">Navigating with an <xref:System.Xml.XPath.XPathNodeIterator> object does not affect the position of the <xref:System.Xml.XPath.XPathNavigator> object used to create it.</span></span> <span data-ttu-id="ac187-113">L'oggetto <xref:System.Xml.XPath.XPathNavigator> restituito dai metodi <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> è posizionato nel singolo nodo restituito e non influisce sulla posizione dell'oggetto <xref:System.Xml.XPath.XPathNavigator> usato per crearlo.</span><span class="sxs-lookup"><span data-stu-id="ac187-113">The <xref:System.Xml.XPath.XPathNavigator> object returned from the <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> methods is positioned on the single returned node and also does not affect the position of the <xref:System.Xml.XPath.XPathNavigator> object used to create it.</span></span>  
  
 <span data-ttu-id="ac187-114">Nell'esempio seguente viene illustrata la creazione di un oggetto <xref:System.Xml.XPath.XPathNavigator> da un oggetto <xref:System.Xml.XPath.XPathDocument>, l'uso del metodo <xref:System.Xml.XPath.XPathNavigator.Select%2A> per selezionare nodi nell'oggetto <xref:System.Xml.XPath.XPathDocument> e l'uso dell'oggetto <xref:System.Xml.XPath.XPathNodeIterator> per scorrere i nodi selezionati.</span><span class="sxs-lookup"><span data-stu-id="ac187-114">The following example shows the creation of an <xref:System.Xml.XPath.XPathNavigator> object from an <xref:System.Xml.XPath.XPathDocument> object, the use of the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method to select nodes in the <xref:System.Xml.XPath.XPathDocument> object, and the use of the <xref:System.Xml.XPath.XPathNodeIterator> object to iterate over the selected nodes.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim nodes As XPathNodeIterator = navigator.Select("/bookstore/book")  
  
While nodes.MoveNext()  
    Console.WriteLine(nodes.Current.Name)  
End While  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathNodeIterator nodes = navigator.Select("/bookstore/book");  
  
while(nodes.MoveNext())  
{  
    Console.WriteLine(nodes.Current.Name);  
}  
```  
  
 <span data-ttu-id="ac187-115">Nell'esempio il file `books.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="ac187-115">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="optimized-selection-methods"></a><span data-ttu-id="ac187-116">Metodi di selezione ottimizzati</span><span class="sxs-lookup"><span data-stu-id="ac187-116">Optimized Selection Methods</span></span>  
 <span data-ttu-id="ac187-117">I metodi <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> e <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> della classe <xref:System.Xml.XPath.XPathNavigator> rappresentano le espressioni XPath comunemente usate per recuperare nodi figlio, discendente e progenitore.</span><span class="sxs-lookup"><span data-stu-id="ac187-117">The <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, and <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class represent XPath expressions commonly used to retrieve child, descendant, and ancestor nodes.</span></span> <span data-ttu-id="ac187-118">Questi metodi consentono di ottimizzare le prestazioni e sono più veloci delle espressioni XPath corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="ac187-118">These methods are optimized for performance and are faster than their corresponding XPath expressions.</span></span> <span data-ttu-id="ac187-119">I metodi <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> e <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> consentono di selezionare i nodi progenitore, figlio e discendente in base a un valore <xref:System.Xml.XPath.XPathNodeType> o al nome locale e all'URI dello spazio dei nomi dei nodi da selezionare.</span><span class="sxs-lookup"><span data-stu-id="ac187-119">The <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A>, and <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> methods selects ancestor, child, and descendant nodes based on an <xref:System.Xml.XPath.XPathNodeType> value or the local name and namespace URI of the nodes to select.</span></span> <span data-ttu-id="ac187-120">I nodi progenitore, figlio e discendente vengono restituiti in un oggetto <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="ac187-120">The selected ancestor, child, and descendant nodes are returned in an <xref:System.Xml.XPath.XPathNodeIterator> object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac187-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac187-121">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="ac187-122">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="ac187-122">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="ac187-123">Valutare espressioni XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ac187-123">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="ac187-124">Corrispondenza di nodi con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="ac187-124">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="ac187-125">Tipi di nodo riconosciuti con le query XPath</span><span class="sxs-lookup"><span data-stu-id="ac187-125">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="ac187-126">Query e spazi dei nomi XPath</span><span class="sxs-lookup"><span data-stu-id="ac187-126">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [<span data-ttu-id="ac187-127">Espressioni XPath compilate</span><span class="sxs-lookup"><span data-stu-id="ac187-127">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
