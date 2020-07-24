---
title: Aggiunta di elementi, attributi e nodi a un albero XML (C#)
description: Informazioni sui metodi per aggiungere contenuto come elementi, attributi, commenti, istruzioni di elaborazione e testo a un albero XML esistente.
ms.date: 07/20/2015
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
ms.openlocfilehash: 78a84401494e2d4280799632fa42dc95574e3e10
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105552"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-c"></a><span data-ttu-id="583e6-103">Aggiunta di elementi, attributi e nodi a un albero XML (C#)</span><span class="sxs-lookup"><span data-stu-id="583e6-103">Adding Elements, Attributes, and Nodes to an XML Tree (C#)</span></span>
<span data-ttu-id="583e6-104">È possibile aggiungere contenuto (elementi, attributi, commenti, istruzioni di elaborazione, testo e CDATA) a un albero XML esistente.</span><span class="sxs-lookup"><span data-stu-id="583e6-104">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="583e6-105">Metodi per l'aggiunta di contenuto</span><span class="sxs-lookup"><span data-stu-id="583e6-105">Methods for Adding Content</span></span>  
 <span data-ttu-id="583e6-106">I metodi seguenti consentono di aggiungere contenuto figlio a un oggetto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>:</span><span class="sxs-lookup"><span data-stu-id="583e6-106">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="583e6-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="583e6-107">Method</span></span>|<span data-ttu-id="583e6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="583e6-108">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="583e6-109">Consente di aggiungere il contenuto alla fine del contenuto figlio di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="583e6-109">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="583e6-110">Consente di aggiungere il contenuto all'inizio del contenuto figlio di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="583e6-110">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="583e6-111">I seguenti metodi consentono di aggiungere contenuto come nodi di pari livello di un oggetto <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="583e6-111">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="583e6-112">Il nodo più comune al quale viene aggiunto contenuto di pari livello è <xref:System.Xml.Linq.XElement>, anche se è possibile aggiungere contenuto di pari livello valido ad altri tipi di nodi, tra cui <xref:System.Xml.Linq.XText> o <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="583e6-112">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="583e6-113">Metodo</span><span class="sxs-lookup"><span data-stu-id="583e6-113">Method</span></span>|<span data-ttu-id="583e6-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="583e6-114">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="583e6-115">Consente di aggiungere contenuto dopo <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="583e6-115">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="583e6-116">Aggiunge contenuto prima di <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="583e6-116">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="583e6-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="583e6-117">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="583e6-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="583e6-118">Description</span></span>  
 <span data-ttu-id="583e6-119">Nell'esempio seguente vengono create due strutture ad albero XML e quindi ne viene modificata una.</span><span class="sxs-lookup"><span data-stu-id="583e6-119">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="583e6-120">Codice</span><span class="sxs-lookup"><span data-stu-id="583e6-120">Code</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",
    new XElement("Element1", 1),  
    new XElement("Element2", 2),  
    new XElement("Element3", 3),  
    new XElement("Element4", 4),  
    new XElement("Element5", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child2", 2),  
    new XElement("Child3", 3),  
    new XElement("Child4", 4),  
    new XElement("Child5", 5)  
);  
xmlTree.Add(new XElement("NewChild", "new content"));  
xmlTree.Add(  
    from el in srcTree.Elements()  
    where (int)el > 3  
    select el  
);  
// Even though Child9 does not exist in srcTree, the following statement will not  
// throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"));  
Console.WriteLine(xmlTree);  
```  
  
### <a name="comments"></a><span data-ttu-id="583e6-121">Commenti</span><span class="sxs-lookup"><span data-stu-id="583e6-121">Comments</span></span>  
 <span data-ttu-id="583e6-122">Questo codice genera l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="583e6-122">This code produces the following output:</span></span>  
  
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
  