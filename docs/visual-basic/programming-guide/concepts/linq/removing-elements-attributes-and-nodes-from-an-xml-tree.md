---
title: Rimozione di elementi, attributi e nodi da un albero XML
ms.date: 07/20/2015
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
ms.openlocfilehash: f8be7fe521fb3c2662b105e34fd96fea1d1ac6e7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413407"
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a><span data-ttu-id="aa064-102">Rimozione di elementi, attributi e nodi da un albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa064-102">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="aa064-103">È possibile modificare un albero XML, rimuovendo elementi, attributi e altri tipi di nodi.</span><span class="sxs-lookup"><span data-stu-id="aa064-103">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>  
  
 <span data-ttu-id="aa064-104">La rimozione di un singolo elemento o di un singolo attributo da un documento XML è un processo semplice.</span><span class="sxs-lookup"><span data-stu-id="aa064-104">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="aa064-105">Tuttavia, quando si rimuovono raccolte di elementi o attributi, è necessario innanzitutto materializzare una raccolta in un elenco e quindi eliminare gli elementi o gli attributi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="aa064-105">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="aa064-106">L'approccio più efficace prevede l'uso del metodo di estensione <xref:System.Xml.Linq.Extensions.Remove%2A>, che consente di ottenere questi risultati.</span><span class="sxs-lookup"><span data-stu-id="aa064-106">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method, which will do this for you.</span></span>  
  
 <span data-ttu-id="aa064-107">Il motivo principale per cui scegliere questo approccio è che la maggior parte delle raccolte recuperate da un albero XML viene restituita tramite esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="aa064-107">The main reason for doing this is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="aa064-108">Se le raccolte non vengono dapprima materializzate in un elenco o se non vengono usati i metodi di estensione, è possibile riscontrare una determinata categoria di bug.</span><span class="sxs-lookup"><span data-stu-id="aa064-108">If you do not first materialize them into a list, or if you do not use the extension methods, it is possible to encounter a certain class of bugs.</span></span> <span data-ttu-id="aa064-109">Per ulteriori informazioni, vedere [bug del codice dichiarativo/imperativo misto (LINQ to XML) (Visual Basic)](mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="aa064-109">For more information, see [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)](mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="aa064-110">I metodi seguenti consentono di rimuovere nodi e attributi da un albero XML.</span><span class="sxs-lookup"><span data-stu-id="aa064-110">The following methods remove nodes and attributes from an XML tree.</span></span>  
  
|<span data-ttu-id="aa064-111">Metodo</span><span class="sxs-lookup"><span data-stu-id="aa064-111">Method</span></span>|<span data-ttu-id="aa064-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa064-112">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="aa064-113">Rimuove un oggetto <xref:System.Xml.Linq.XAttribute> dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="aa064-113">Removes an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|  
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="aa064-114">Rimuove i nodi figlio da un oggetto <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="aa064-114">Removes the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="aa064-115">Rimuove il contenuto e gli attributi da un oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="aa064-115">Removes content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="aa064-116">Rimuove gli attributi di un oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="aa064-116">Removes the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="aa064-117">Se viene passato `null` come valore, rimuove l'attributo.</span><span class="sxs-lookup"><span data-stu-id="aa064-117">If you pass `null` for value, then removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="aa064-118">Se viene passato `null` come valore, rimuove l'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="aa064-118">If you pass `null` for value, then removes the child element.</span></span>|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="aa064-119">Rimuove un oggetto <xref:System.Xml.Linq.XNode> dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="aa064-119">Removes an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="aa064-120">Rimuove ogni attributo o elemento nella raccolta di origine dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="aa064-120">Removes every attribute or element in the source collection from its parent element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="aa064-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="aa064-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="aa064-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aa064-122">Description</span></span>  
 <span data-ttu-id="aa064-123">In questo esempio sono illustrati tre approcci per la rimozione di elementi.</span><span class="sxs-lookup"><span data-stu-id="aa064-123">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="aa064-124">Con il primo viene rimosso un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="aa064-124">First, it removes a single element.</span></span> <span data-ttu-id="aa064-125">Con il secondo viene recuperata una raccolta di elementi, che viene materializzata tramite l'operatore <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> e quindi viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="aa064-125">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> operator, and removes the collection.</span></span> <span data-ttu-id="aa064-126">Infine, viene recuperata una raccolta di elementi che viene rimossa tramite il metodo di estensione <xref:System.Xml.Linq.Extensions.Remove%2A>.</span><span class="sxs-lookup"><span data-stu-id="aa064-126">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>  
  
 <span data-ttu-id="aa064-127">Per ulteriori informazioni sull' <xref:System.Linq.Enumerable.ToList%2A> operatore, vedere [conversione di tipi di dati (Visual Basic)](converting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="aa064-127">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (Visual Basic)](converting-data-types.md).</span></span>  
  
### <a name="code"></a><span data-ttu-id="aa064-128">Codice</span><span class="sxs-lookup"><span data-stu-id="aa064-128">Code</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1/>  
            <GrandChild2/>  
            <GrandChild3/>  
        </Child1>  
        <Child2>  
            <GrandChild4/>  
            <GrandChild5/>  
            <GrandChild6/>  
        </Child2>  
        <Child3>  
            <GrandChild7/>  
            <GrandChild8/>  
            <GrandChild9/>  
        </Child3>  
    </Root>  
root.<Child1>.<GrandChild1>.Remove()  
root.<Child2>.Elements().ToList().Remove()  
root.<Child3>.Elements().Remove()  
Console.WriteLine(root)  
```  
  
### <a name="comments"></a><span data-ttu-id="aa064-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="aa064-129">Comments</span></span>  
 <span data-ttu-id="aa064-130">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="aa064-130">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>  
    <GrandChild2 />  
    <GrandChild3 />  
  </Child1>  
  <Child2 />  
  <Child3 />  
</Root>  
```  
  
 <span data-ttu-id="aa064-131">Si noti che il primo elemento nipote è stato rimosso da `Child1`.</span><span class="sxs-lookup"><span data-stu-id="aa064-131">Notice that the first grandchild element has been removed from `Child1`.</span></span> <span data-ttu-id="aa064-132">Tutti gli elementi nipote sono stati rimossi da `Child2` e da `Child3`.</span><span class="sxs-lookup"><span data-stu-id="aa064-132">All grandchildren elements have been removed from `Child2` and from `Child3`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa064-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aa064-133">See also</span></span>

- [<span data-ttu-id="aa064-134">Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa064-134">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](modifying-xml-trees-linq-to-xml.md)
