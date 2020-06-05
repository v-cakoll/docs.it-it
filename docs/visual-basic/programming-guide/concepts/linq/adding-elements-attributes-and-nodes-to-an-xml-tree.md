---
title: Aggiunta di elementi, attributi e nodi a un albero XML
ms.date: 07/20/2015
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
ms.openlocfilehash: 5b80a19c952388c2591536077f382df2f69fe80f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383897"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a><span data-ttu-id="8872d-102">Aggiunta di elementi, attributi e nodi a un albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8872d-102">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="8872d-103">È possibile aggiungere contenuto (elementi, attributi, commenti, istruzioni di elaborazione, testo e CDATA) a un albero XML esistente.</span><span class="sxs-lookup"><span data-stu-id="8872d-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="8872d-104">Metodi per l'aggiunta di contenuto</span><span class="sxs-lookup"><span data-stu-id="8872d-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="8872d-105">I metodi seguenti consentono di aggiungere contenuto figlio a un oggetto <xref:System.Xml.Linq.XElement> o <xref:System.Xml.Linq.XDocument>:</span><span class="sxs-lookup"><span data-stu-id="8872d-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="8872d-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="8872d-106">Method</span></span>|<span data-ttu-id="8872d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8872d-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="8872d-108">Consente di aggiungere il contenuto alla fine del contenuto figlio di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="8872d-108">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="8872d-109">Consente di aggiungere il contenuto all'inizio del contenuto figlio di <xref:System.Xml.Linq.XContainer>.</span><span class="sxs-lookup"><span data-stu-id="8872d-109">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="8872d-110">I seguenti metodi consentono di aggiungere contenuto come nodi di pari livello di un oggetto <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="8872d-110">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="8872d-111">Il nodo più comune al quale viene aggiunto contenuto di pari livello è <xref:System.Xml.Linq.XElement>, anche se è possibile aggiungere contenuto di pari livello valido ad altri tipi di nodi, tra cui <xref:System.Xml.Linq.XText> o <xref:System.Xml.Linq.XComment>.</span><span class="sxs-lookup"><span data-stu-id="8872d-111">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="8872d-112">Metodo</span><span class="sxs-lookup"><span data-stu-id="8872d-112">Method</span></span>|<span data-ttu-id="8872d-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8872d-113">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="8872d-114">Consente di aggiungere contenuto dopo <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="8872d-114">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="8872d-115">Aggiunge contenuto prima di <xref:System.Xml.Linq.XNode>.</span><span class="sxs-lookup"><span data-stu-id="8872d-115">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8872d-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="8872d-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="8872d-117">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8872d-117">Description</span></span>  
 <span data-ttu-id="8872d-118">Nell'esempio seguente vengono create due strutture ad albero XML e quindi ne viene modificata una.</span><span class="sxs-lookup"><span data-stu-id="8872d-118">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="8872d-119">Codice</span><span class="sxs-lookup"><span data-stu-id="8872d-119">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="8872d-120">Commenti</span><span class="sxs-lookup"><span data-stu-id="8872d-120">Comments</span></span>  
 <span data-ttu-id="8872d-121">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8872d-121">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8872d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8872d-122">See also</span></span>

- [<span data-ttu-id="8872d-123">Modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8872d-123">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](modifying-xml-trees-linq-to-xml.md)
