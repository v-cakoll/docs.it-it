---
title: Rimozione di elementi, attributi e nodi da una struttura ad albero XML (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8842858080ce1f27d997e6af61a8dd2301cdc2bc
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a><span data-ttu-id="0f6b6-102">Rimozione di elementi, attributi e nodi da una struttura ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f6b6-102">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="0f6b6-103">È possibile modificare un albero XML, rimuovendo elementi, attributi e altri tipi di nodi.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-103">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>  
  
 <span data-ttu-id="0f6b6-104">La rimozione di un singolo elemento o di un singolo attributo da un documento XML è un processo semplice.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-104">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="0f6b6-105">Tuttavia, quando si rimuovono raccolte di elementi o attributi, è necessario innanzitutto materializzare una raccolta in un elenco e quindi eliminare gli elementi o gli attributi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-105">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="0f6b6-106">L'approccio migliore consiste nell'utilizzare il <xref:System.Xml.Linq.Extensions.Remove%2A>metodo di estensione, questa operazione verrà eseguita automaticamente.</xref:System.Xml.Linq.Extensions.Remove%2A></span><span class="sxs-lookup"><span data-stu-id="0f6b6-106">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method, which will do this for you.</span></span>  
  
 <span data-ttu-id="0f6b6-107">Il motivo principale per cui scegliere questo approccio è che la maggior parte delle raccolte recuperate da un albero XML viene restituita tramite esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-107">The main reason for doing this is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="0f6b6-108">Se le raccolte non vengono dapprima materializzate in un elenco o se non vengono usati i metodi di estensione, è possibile riscontrare una determinata categoria di bug.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-108">If you do not first materialize them into a list, or if you do not use the extension methods, it is possible to encounter a certain class of bugs.</span></span> <span data-ttu-id="0f6b6-109">Per ulteriori informazioni, vedere [mista dichiarativa/bug nel codice imperativo (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0f6b6-109">For more information, see [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="0f6b6-110">I metodi seguenti consentono di rimuovere nodi e attributi da un albero XML.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-110">The following methods remove nodes and attributes from an XML tree.</span></span>  
  
|<span data-ttu-id="0f6b6-111">Metodo</span><span class="sxs-lookup"><span data-stu-id="0f6b6-111">Method</span></span>|<span data-ttu-id="0f6b6-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f6b6-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0f6b6-113">[XAttribute.Remove](https://msdn.microsoft.com/library/system.xml.linq.xattribute.remove\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f6b6-113">[XAttribute.Remove](https://msdn.microsoft.com/library/system.xml.linq.xattribute.remove\(v=vs.110\).aspx)</span></span>|<span data-ttu-id="0f6b6-114">Rimuove un <xref:System.Xml.Linq.XAttribute>dal relativo elemento padre.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="0f6b6-114">Removes an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|  
|<span data-ttu-id="0f6b6-115">[XContainer.RemoveNodes](https://msdn.microsoft.com/library/system.xml.linq.xcontainer.removenodes\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="0f6b6-115">[XContainer.RemoveNodes](https://msdn.microsoft.com/library/system.xml.linq.xcontainer.removenodes\(v=vs.110\).aspx)</span></span>|<span data-ttu-id="0f6b6-116">Rimuove i nodi figlio da un <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="0f6b6-116">Removes the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="0f6b6-117"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0f6b6-117"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="0f6b6-118">Rimuove il contenuto e gli attributi da un <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0f6b6-118">Removes content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="0f6b6-119"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0f6b6-119"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="0f6b6-120">Rimuove gli attributi di un <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="0f6b6-120">Removes the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="0f6b6-121"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0f6b6-121"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="0f6b6-122">Se viene passato `null` come valore, rimuove l'attributo.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-122">If you pass `null` for value, then removes the attribute.</span></span>|  
|<span data-ttu-id="0f6b6-123"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0f6b6-123"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="0f6b6-124">Se viene passato `null` come valore, rimuove l'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-124">If you pass `null` for value, then removes the child element.</span></span>|  
|<span data-ttu-id="0f6b6-125"><xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0f6b6-125"><xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></span></span>|<span data-ttu-id="0f6b6-126">Rimuove un <xref:System.Xml.Linq.XNode>dal relativo elemento padre.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="0f6b6-126">Removes an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|  
|<span data-ttu-id="0f6b6-127"><xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0f6b6-127"><xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></span></span>|<span data-ttu-id="0f6b6-128">Rimuove ogni attributo o elemento nella raccolta di origine dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-128">Removes every attribute or element in the source collection from its parent element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0f6b6-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="0f6b6-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0f6b6-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0f6b6-130">Description</span></span>  
 <span data-ttu-id="0f6b6-131">In questo esempio sono illustrati tre approcci per la rimozione di elementi.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-131">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="0f6b6-132">Con il primo viene rimosso un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-132">First, it removes a single element.</span></span> <span data-ttu-id="0f6b6-133">In secondo luogo, viene recuperata una raccolta di elementi, materializzata tramite il <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>operatore e rimuove la raccolta.</xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="0f6b6-133">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> operator, and removes the collection.</span></span> <span data-ttu-id="0f6b6-134">Infine, recupera una raccolta di elementi e di rimuoverli tramite il <xref:System.Xml.Linq.Extensions.Remove%2A>metodo di estensione.</xref:System.Xml.Linq.Extensions.Remove%2A></span><span class="sxs-lookup"><span data-stu-id="0f6b6-134">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>  
  
 <span data-ttu-id="0f6b6-135">Per ulteriori informazioni sui <xref:System.Linq.Enumerable.ToList%2A>operatore, vedere [la conversione di tipi di dati (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</xref:System.Linq.Enumerable.ToList%2A></span><span class="sxs-lookup"><span data-stu-id="0f6b6-135">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</span></span>  
  
### <a name="code"></a><span data-ttu-id="0f6b6-136">Codice</span><span class="sxs-lookup"><span data-stu-id="0f6b6-136">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="0f6b6-137">Commenti</span><span class="sxs-lookup"><span data-stu-id="0f6b6-137">Comments</span></span>  
 <span data-ttu-id="0f6b6-138">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="0f6b6-138">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="0f6b6-139">Si noti che il primo elemento nipote è stato rimosso da `Child1`.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-139">Notice that the first grandchild element has been removed from `Child1`.</span></span> <span data-ttu-id="0f6b6-140">Tutti gli elementi nipote sono stati rimossi da `Child2` e da `Child3`.</span><span class="sxs-lookup"><span data-stu-id="0f6b6-140">All grandchildren elements have been removed from `Child2` and from `Child3`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f6b6-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f6b6-141">See Also</span></span>  
 [<span data-ttu-id="0f6b6-142">Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f6b6-142">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
