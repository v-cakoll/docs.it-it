---
title: Rimozione di elementi, attributi e nodi da un albero XML (C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 07dd06d6-1117-4077-bf98-9120cf51176e
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1745b1ce84b33a67d54f5e752da2ecf9bbfdbc17
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-c"></a><span data-ttu-id="2d38a-102">Rimozione di elementi, attributi e nodi da un albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2d38a-102">Removing Elements, Attributes, and Nodes from an XML Tree (C#)</span></span>
<span data-ttu-id="2d38a-103">È possibile modificare un albero XML, rimuovendo elementi, attributi e altri tipi di nodi.</span><span class="sxs-lookup"><span data-stu-id="2d38a-103">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>  
  
 <span data-ttu-id="2d38a-104">La rimozione di un singolo elemento o di un singolo attributo da un documento XML è un processo semplice.</span><span class="sxs-lookup"><span data-stu-id="2d38a-104">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="2d38a-105">Tuttavia, quando si rimuovono raccolte di elementi o attributi, è necessario innanzitutto materializzare una raccolta in un elenco e quindi eliminare gli elementi o gli attributi dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="2d38a-105">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="2d38a-106">L'approccio più efficace prevede l'uso del metodo di estensione <xref:System.Xml.Linq.Extensions.Remove%2A>, che consente di ottenere questi risultati.</span><span class="sxs-lookup"><span data-stu-id="2d38a-106">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method, which will do this for you.</span></span>  
  
 <span data-ttu-id="2d38a-107">Il motivo principale per cui scegliere questo approccio è che la maggior parte delle raccolte recuperate da un albero XML viene restituita tramite esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="2d38a-107">The main reason for doing this is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="2d38a-108">Se le raccolte non vengono dapprima materializzate in un elenco o se non vengono usati i metodi di estensione, è possibile riscontrare una determinata categoria di bug.</span><span class="sxs-lookup"><span data-stu-id="2d38a-108">If you do not first materialize them into a list, or if you do not use the extension methods, it is possible to encounter a certain class of bugs.</span></span> <span data-ttu-id="2d38a-109">Per altre informazioni, vedere [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md) (Bug nel codice dichiarativo/imperativo misto (LINQ to XML) (C#)).</span><span class="sxs-lookup"><span data-stu-id="2d38a-109">For more information, see [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="2d38a-110">I metodi seguenti consentono di rimuovere nodi e attributi da un albero XML.</span><span class="sxs-lookup"><span data-stu-id="2d38a-110">The following methods remove nodes and attributes from an XML tree.</span></span>  
  
|<span data-ttu-id="2d38a-111">Metodo</span><span class="sxs-lookup"><span data-stu-id="2d38a-111">Method</span></span>|<span data-ttu-id="2d38a-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d38a-112">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="2d38a-113">Rimuove un oggetto <xref:System.Xml.Linq.XAttribute> dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="2d38a-113">Removes an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|  
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|<span data-ttu-id="2d38a-114">Rimuove i nodi figlio da un oggetto <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="2d38a-114">Removes the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|<span data-ttu-id="2d38a-115">Rimuove il contenuto e gli attributi da un oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="2d38a-115">Removes content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|<span data-ttu-id="2d38a-116">Rimuove gli attributi di un oggetto <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="2d38a-116">Removes the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|<span data-ttu-id="2d38a-117">Se viene passato `null` come valore, rimuove l'attributo.</span><span class="sxs-lookup"><span data-stu-id="2d38a-117">If you pass `null` for value, then removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|<span data-ttu-id="2d38a-118">Se viene passato `null` come valore, rimuove l'elemento figlio.</span><span class="sxs-lookup"><span data-stu-id="2d38a-118">If you pass `null` for value, then removes the child element.</span></span>|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="2d38a-119">Rimuove un oggetto <xref:System.Xml.Linq.XNode> dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="2d38a-119">Removes an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|<span data-ttu-id="2d38a-120">Rimuove ogni attributo o elemento nella raccolta di origine dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="2d38a-120">Removes every attribute or element in the source collection from its parent element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2d38a-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="2d38a-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2d38a-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2d38a-122">Description</span></span>  
 <span data-ttu-id="2d38a-123">In questo esempio sono illustrati tre approcci per la rimozione di elementi.</span><span class="sxs-lookup"><span data-stu-id="2d38a-123">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="2d38a-124">Con il primo viene rimosso un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="2d38a-124">First, it removes a single element.</span></span> <span data-ttu-id="2d38a-125">Con il secondo viene recuperata una raccolta di elementi, che viene materializzata tramite l'operatore <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> e quindi viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="2d38a-125">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> operator, and removes the collection.</span></span> <span data-ttu-id="2d38a-126">Infine, viene recuperata una raccolta di elementi che viene rimossa tramite il metodo di estensione <xref:System.Xml.Linq.Extensions.Remove%2A>.</span><span class="sxs-lookup"><span data-stu-id="2d38a-126">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>  
  
 <span data-ttu-id="2d38a-127">Per altre informazioni sull'operatore <xref:System.Linq.Enumerable.ToList%2A>, vedere [Conversione di tipi di dati (C#)](../../../../csharp/programming-guide/concepts/linq/converting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="2d38a-127">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (C#)](../../../../csharp/programming-guide/concepts/linq/converting-data-types.md).</span></span>  
  
### <a name="code"></a><span data-ttu-id="2d38a-128">Codice</span><span class="sxs-lookup"><span data-stu-id="2d38a-128">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
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
</Root>");  
root.Element("Child1").Element("GrandChild1").Remove();  
root.Element("Child2").Elements().ToList().Remove();  
root.Element("Child3").Elements().Remove();  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a><span data-ttu-id="2d38a-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="2d38a-129">Comments</span></span>  
 <span data-ttu-id="2d38a-130">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="2d38a-130">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="2d38a-131">Si noti che il primo elemento nipote è stato rimosso da `Child1`.</span><span class="sxs-lookup"><span data-stu-id="2d38a-131">Notice that the first grandchild element has been removed from `Child1`.</span></span> <span data-ttu-id="2d38a-132">Tutti gli elementi nipote sono stati rimossi da `Child2` e da `Child3`.</span><span class="sxs-lookup"><span data-stu-id="2d38a-132">All grandchildren elements have been removed from `Child2` and from `Child3`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d38a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d38a-133">See Also</span></span>  
 [<span data-ttu-id="2d38a-134">Modifica degli alberi XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2d38a-134">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
