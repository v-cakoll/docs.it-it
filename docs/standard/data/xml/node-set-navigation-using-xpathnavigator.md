---
title: Navigazione del set di nodi con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1a954b41-7173-40bc-8544-d430f209b1e5
ms.openlocfilehash: 132154afdfd3e5bd6769bfcce338e598136e7515
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288758"
---
# <a name="node-set-navigation-using-xpathnavigator"></a><span data-ttu-id="72c82-102">Navigazione del set di nodi con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="72c82-102">Node Set Navigation Using XPathNavigator</span></span>
<span data-ttu-id="72c82-103">È possibile navigare nei nodi in un oggetto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> usando i metodi di navigazione del set di nodi della classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="72c82-103">You can navigate over nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="72c82-104">È possibile navigare in tutti i nodi o un set di nodi selezionato restituito da uno dei metodi di selezione della classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="72c82-104">You can navigate over all the nodes or over a selected set of nodes returned by one of the selection methods of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="element-node-set-navigation"></a><span data-ttu-id="72c82-105">Navigazione del set di nodi di tipo element</span><span class="sxs-lookup"><span data-stu-id="72c82-105">Element Node Set Navigation</span></span>  
 <span data-ttu-id="72c82-106">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce diversi metodi usati per navigare nei nodi di tipo element.</span><span class="sxs-lookup"><span data-stu-id="72c82-106">The <xref:System.Xml.XPath.XPathNavigator> class provides several methods used to navigate element nodes.</span></span> <span data-ttu-id="72c82-107">Nella tabella seguente vengono illustrati i metodi di navigazione disponibili e viene fornita una descrizione delle modalità di spostamento. Non sono inclusi i metodi usati per esplorare i nodi Attribute e Namespace.</span><span class="sxs-lookup"><span data-stu-id="72c82-107">The following table shows the navigation methods available and a description of how they move; this does not include methods used to navigate attribute and namespace nodes.</span></span>  
  
 <span data-ttu-id="72c82-108">Per altre informazioni sulla selezione dei nodi in un oggetto <xref:System.Xml.XPath.XPathNavigator>, vedere [Selezione, valutazione e corrispondenza di dati XML con XPathNavigator](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="72c82-108">For more information about selecting nodes in an <xref:System.Xml.XPath.XPathNavigator> object, see [Selecting, Evaluating and Matching XML Data using XPathNavigator](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md).</span></span> <span data-ttu-id="72c82-109">Per altre informazioni sulla navigazione dei nodi di attributi e spazi dei nomi, vedere [Navigazione dei nodi di attributi e dello spazio dei nomi con XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="72c82-109">For more information about navigating attribute and namespace nodes, see [Attribute and Namespace Node Navigation Using XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md).</span></span>  
  
|<span data-ttu-id="72c82-110">Metodo</span><span class="sxs-lookup"><span data-stu-id="72c82-110">Method</span></span>|<span data-ttu-id="72c82-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72c82-111">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>|<span data-ttu-id="72c82-112">Sposta il tipo <xref:System.Xml.XPath.XPathNavigator> nella stessa posizione dell'oggetto <xref:System.Xml.XPath.XPathNavigator> specificato.</span><span class="sxs-lookup"><span data-stu-id="72c82-112">Moves the <xref:System.Xml.XPath.XPathNavigator> to the same position of the <xref:System.Xml.XPath.XPathNavigator> specified.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>|<span data-ttu-id="72c82-113">Sposta il tipo <xref:System.Xml.XPath.XPathNavigator> su un nodo figlio del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="72c82-113">Moves the <xref:System.Xml.XPath.XPathNavigator> to a child node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>|<span data-ttu-id="72c82-114">Sposta il tipo <xref:System.Xml.XPath.XPathNavigator> sul primo nodo di pari livello del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="72c82-114">Moves the <xref:System.Xml.XPath.XPathNavigator> to the first sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>|<span data-ttu-id="72c82-115">Sposta il tipo <xref:System.Xml.XPath.XPathNavigator> sul primo nodo figlio del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="72c82-115">Moves the <xref:System.Xml.XPath.XPathNavigator> to the first child node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>|<span data-ttu-id="72c82-116">Sposta il tipo <xref:System.Xml.XPath.XPathNavigator> sull'elemento specificato in base all'ordine con cui è riportato nel documento.</span><span class="sxs-lookup"><span data-stu-id="72c82-116">Moves the <xref:System.Xml.XPath.XPathNavigator> to the specified element in document order.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>|<span data-ttu-id="72c82-117">Sposta il tipo <xref:System.Xml.XPath.XPathNavigator> sul nodo che dispone di un attributo di tipo `ID`, il cui valore corrisponde alla stringa <xref:System.String> indicata.</span><span class="sxs-lookup"><span data-stu-id="72c82-117">Moves the <xref:System.Xml.XPath.XPathNavigator> to the node that has an attribute of type `ID` with a value that matches the given <xref:System.String>.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>|<span data-ttu-id="72c82-118">Sposta il tipo <xref:System.Xml.XPath.XPathNavigator> sul successivo nodo di pari livello del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="72c82-118">Moves the <xref:System.Xml.XPath.XPathNavigator> to the next sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>|<span data-ttu-id="72c82-119">Sposta il tipo <xref:System.Xml.XPath.XPathNavigator> sul nodo padre del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="72c82-119">Moves the <xref:System.Xml.XPath.XPathNavigator> to the parent node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>|<span data-ttu-id="72c82-120">Sposta il tipo <xref:System.Xml.XPath.XPathNavigator> sul precedente nodo di pari livello del nodo corrente.</span><span class="sxs-lookup"><span data-stu-id="72c82-120">Moves the <xref:System.Xml.XPath.XPathNavigator> to the previous sibling node of the current node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>|<span data-ttu-id="72c82-121">Sposta il tipo <xref:System.Xml.XPath.XPathNavigator> sul nodo radice del documento XML.</span><span class="sxs-lookup"><span data-stu-id="72c82-121">Moves the <xref:System.Xml.XPath.XPathNavigator> to the root node of the XML document.</span></span>|  
  
## <a name="comments-and-processing-instruction-node-navigation"></a><span data-ttu-id="72c82-122">Navigazione dei nodi di tipo Comment e Processing Instruction</span><span class="sxs-lookup"><span data-stu-id="72c82-122">Comments and Processing Instruction Node Navigation</span></span>  
 <span data-ttu-id="72c82-123">I seguenti metodi della classe <xref:System.Xml.XPath.XPathNavigator> sono validi per passare ai commenti o alle istruzioni di elaborazione da altri nodi all'interno un documento XML.</span><span class="sxs-lookup"><span data-stu-id="72c82-123">The following <xref:System.Xml.XPath.XPathNavigator> class methods are valid for moving to comments or processing instructions from other nodes in an XML document.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>  
  
## <a name="see-also"></a><span data-ttu-id="72c82-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72c82-124">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="72c82-125">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="72c82-125">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="72c82-126">Navigazione dei nodi di attributi e dello spazio dei nomi con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="72c82-126">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="72c82-127">Estrazione di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="72c82-127">Extract XML Data Using XPathNavigator</span></span>](extract-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="72c82-128">Accesso a dati XML fortemente tipizzati con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="72c82-128">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>](accessing-strongly-typed-xml-data-using-xpathnavigator.md)
