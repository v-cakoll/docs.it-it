---
title: Aggiunta di elementi, attributi e nodi a una struttura ad albero XML (Visual Basic) | Documenti di Microsoft
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
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f8ee26aef896a2f404e815823ade83e204270613
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a><span data-ttu-id="1ffd2-102">Aggiunta di elementi, attributi e nodi a una struttura ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ffd2-102">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="1ffd2-103">È possibile aggiungere contenuto (elementi, attributi, commenti, istruzioni di elaborazione, testo e CDATA) a un albero XML esistente.</span><span class="sxs-lookup"><span data-stu-id="1ffd2-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="1ffd2-104">Metodi per l'aggiunta di contenuto</span><span class="sxs-lookup"><span data-stu-id="1ffd2-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="1ffd2-105">I metodi seguenti aggiungono contenuto figlio a un <xref:System.Xml.Linq.XElement>o un <xref:System.Xml.Linq.XDocument>:</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1ffd2-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="1ffd2-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="1ffd2-106">Method</span></span>|<span data-ttu-id="1ffd2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ffd2-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1ffd2-108"><xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="1ffd2-108"><xref:System.Xml.Linq.XContainer.Add%2A></span></span>|<span data-ttu-id="1ffd2-109">Consente di aggiungere contenuto alla fine del contenuto figlio dell'elemento <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="1ffd2-109">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="1ffd2-110"><xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A></span><span class="sxs-lookup"><span data-stu-id="1ffd2-110"><xref:System.Xml.Linq.XContainer.AddFirst%2A></span></span>|<span data-ttu-id="1ffd2-111">Aggiunge contenuto all'inizio del contenuto figlio dell'elemento <xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="1ffd2-111">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="1ffd2-112">I seguenti metodi di aggiungere contenuto come nodi di pari livello di un <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="1ffd2-112">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="1ffd2-113">Il nodo più comune a cui aggiungere contenuto di pari livello è <xref:System.Xml.Linq.XElement>, anche se è possibile aggiungere contenuto di pari livello valido ad altri tipi di nodi, ad esempio <xref:System.Xml.Linq.XText>o <xref:System.Xml.Linq.XComment>.</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XText> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1ffd2-113">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="1ffd2-114">Metodo</span><span class="sxs-lookup"><span data-stu-id="1ffd2-114">Method</span></span>|<span data-ttu-id="1ffd2-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ffd2-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1ffd2-116"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="1ffd2-116"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span></span>|<span data-ttu-id="1ffd2-117">Aggiunge contenuto dopo la <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="1ffd2-117">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="1ffd2-118"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span><span class="sxs-lookup"><span data-stu-id="1ffd2-118"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span></span>|<span data-ttu-id="1ffd2-119">Aggiunge contenuto prima di <xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="1ffd2-119">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1ffd2-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="1ffd2-120">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="1ffd2-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1ffd2-121">Description</span></span>  
 <span data-ttu-id="1ffd2-122">Nell'esempio seguente vengono create due strutture ad albero XML e quindi ne viene modificata una.</span><span class="sxs-lookup"><span data-stu-id="1ffd2-122">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="1ffd2-123">Codice</span><span class="sxs-lookup"><span data-stu-id="1ffd2-123">Code</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element1>1</Element1>  
        <Element2>2</Element2>  
        <Element3>3</Element3>  
        <Element4>4</Element4>  
        <Element5>5</Element5>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child2>2</Child2>  
        <Child3>3</Child3>  
        <Child4>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
xmlTree.Add(<NewChild>new content</NewChild>)  
xmlTree.Add( _  
    From el In srcTree.Elements() _  
    Where CInt(el) > 3 _  
    Select el)  
  
' Even though Child9 does not exist in srcTree, the following statement  
' will not throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"))  
Console.WriteLine(xmlTree)  
  
```  
  
### <a name="comments"></a><span data-ttu-id="1ffd2-124">Commenti</span><span class="sxs-lookup"><span data-stu-id="1ffd2-124">Comments</span></span>  
 <span data-ttu-id="1ffd2-125">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="1ffd2-125">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ffd2-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ffd2-126">See Also</span></span>  
 [<span data-ttu-id="1ffd2-127">Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ffd2-127">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
