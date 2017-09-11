---
title: Programmazione con nodi (Visual Basic) | Documenti di Microsoft
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
ms.assetid: d8422a9b-dd37-44a3-8aac-2237ed9561e0
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 967e207aa4d1a4afb21f82b7b1767a5c6dc088c6
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017

---
# <a name="programming-with-nodes-visual-basic"></a><span data-ttu-id="4db6c-102">Programmazione con nodi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4db6c-102">Programming with Nodes (Visual Basic)</span></span>
<span data-ttu-id="4db6c-103">Gli sviluppatori di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] che hanno la necessità di scrivere programmi come un editor XML, un sistema di trasformazioni o un writer di rapporti, spesso devono scrivere programmi che funzionano a un livello di granularità maggiore rispetto a elementi e attributi.</span><span class="sxs-lookup"><span data-stu-id="4db6c-103">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] developers who need to write programs such as an XML editor, a transform system, or a report writer often need to write programs that work at a finer level of granularity than elements and attributes.</span></span> <span data-ttu-id="4db6c-104">Devono spesso operare a livello di nodo, modificando i nodi di testo, elaborando istruzioni e commenti.</span><span class="sxs-lookup"><span data-stu-id="4db6c-104">They often need to work at the node level, manipulating text nodes, processing instructions, and comments.</span></span> <span data-ttu-id="4db6c-105">In questo argomento vengono forniti dettagli sulla programmazione a livello di nodo.</span><span class="sxs-lookup"><span data-stu-id="4db6c-105">This topic provides some details about programming at the node level.</span></span>  
  
## <a name="node-details"></a><span data-ttu-id="4db6c-106">Dettagli sui nodi</span><span class="sxs-lookup"><span data-stu-id="4db6c-106">Node Details</span></span>  
 <span data-ttu-id="4db6c-107">I programmatori che operano a livello di nodo devono conoscere diversi dettagli di programmazione.</span><span class="sxs-lookup"><span data-stu-id="4db6c-107">There are a number of details of programming that a programmer working at the node level should know.</span></span>  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a><span data-ttu-id="4db6c-108">La proprietà padre dei nodi figlio di XDocument è impostata su Null</span><span class="sxs-lookup"><span data-stu-id="4db6c-108">Parent Property of Children Nodes of XDocument is Set to Null</span></span>  
 <span data-ttu-id="4db6c-109">Il <xref:System.Xml.Linq.XObject.Parent%2A>proprietà contiene l'elemento padre <xref:System.Xml.Linq.XElement>, non il nodo padre.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XObject.Parent%2A></span><span class="sxs-lookup"><span data-stu-id="4db6c-109">The <xref:System.Xml.Linq.XObject.Parent%2A> property contains the parent <xref:System.Xml.Linq.XElement>, not the parent node.</span></span> <span data-ttu-id="4db6c-110">Nodi figlio di <xref:System.Xml.Linq.XDocument>alcun elemento padre <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="4db6c-110">Child nodes of <xref:System.Xml.Linq.XDocument> have no parent <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="4db6c-111">L'elemento padre è il documento, in modo che il <xref:System.Xml.Linq.XObject.Parent%2A>per questi nodi è impostata su null.</xref:System.Xml.Linq.XObject.Parent%2A></span><span class="sxs-lookup"><span data-stu-id="4db6c-111">Their parent is the document, so the <xref:System.Xml.Linq.XObject.Parent%2A> property for those nodes is set to null.</span></span>  
  
 <span data-ttu-id="4db6c-112">Questo concetto è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4db6c-112">The following example demonstrates this:</span></span>  
  
```vb  
Dim doc As XDocument = XDocument.Parse("<!-- a comment --><Root/>")  
Console.WriteLine(doc.Nodes().OfType(Of XComment).First().Parent Is Nothing)  
Console.WriteLine(doc.Root.Parent Is Nothing)  
```  
  
 <span data-ttu-id="4db6c-113">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4db6c-113">This example produces the following output:</span></span>  
  
```  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a><span data-ttu-id="4db6c-114">I nodi di testo adiacenti sono possibili</span><span class="sxs-lookup"><span data-stu-id="4db6c-114">Adjacent Text Nodes are Possible</span></span>  
 <span data-ttu-id="4db6c-115">In diversi modelli di programmazione XML i nodi di testo adiacenti vengono sempre uniti.</span><span class="sxs-lookup"><span data-stu-id="4db6c-115">In a number of XML programming models, adjacent text nodes are always merged.</span></span> <span data-ttu-id="4db6c-116">Questa operazione è denominata normalizzazione dei nodi di testo.</span><span class="sxs-lookup"><span data-stu-id="4db6c-116">This is sometimes called normalization of text nodes.</span></span> <span data-ttu-id="4db6c-117">In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] i nodi di testo non vengono normalizzati.</span><span class="sxs-lookup"><span data-stu-id="4db6c-117">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] does not normalize text nodes.</span></span> <span data-ttu-id="4db6c-118">Se si aggiungono due nodi di testo allo stesso elemento, si otterranno nodi di testo adiacenti.</span><span class="sxs-lookup"><span data-stu-id="4db6c-118">If you add two text nodes to the same element, it will result in adjacent text nodes.</span></span> <span data-ttu-id="4db6c-119">Tuttavia, se si aggiunge contenuto specificato come stringa anziché come un <xref:System.Xml.Linq.XText>nodo [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] potrebbe essere di tipo merge la stringa con un nodo di testo adiacente.</xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="4db6c-119">However, if you add content specified as a string rather than as an <xref:System.Xml.Linq.XText> node, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] might merge the string with an adjacent text node.</span></span>  
  
 <span data-ttu-id="4db6c-120">Questo concetto è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4db6c-120">The following example demonstrates this:</span></span>  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
  
' This does not add a new text node.  
xmlTree.Add("new content")  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
  
'// This does add a new, adjacent text node.  
xmlTree.Add(New XText("more text"))  
Console.WriteLine(xmlTree.Nodes().OfType(Of XText)().Count())  
```  
  
 <span data-ttu-id="4db6c-121">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4db6c-121">This example produces the following output:</span></span>  
  
```  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a><span data-ttu-id="4db6c-122">I nodi di testo vuoti sono possibili</span><span class="sxs-lookup"><span data-stu-id="4db6c-122">Empty Text Nodes are Possible</span></span>  
 <span data-ttu-id="4db6c-123">In alcuni modelli di programmazione di XML è garantito che i nodi di testo non contengono la stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="4db6c-123">In some XML programming models, text nodes are guaranteed to not contain the empty string.</span></span> <span data-ttu-id="4db6c-124">Il concetto di base è che un nodo di testo di questo tipo non ha impatto sulla serializzazione dell'XML.</span><span class="sxs-lookup"><span data-stu-id="4db6c-124">The reasoning is that such a text node has no impact on serialization of the XML.</span></span> <span data-ttu-id="4db6c-125">Tuttavia, per lo stesso motivo per cui i nodi di testo sono possibili, la rimozione di testo da un nodo di testo impostandone il valore sulla stringa vuota non comporta l'eliminazione del nodo di testo stesso.</span><span class="sxs-lookup"><span data-stu-id="4db6c-125">However, for the same reason that adjacent text nodes are possible, if you remove the text from a text node by setting its value to the empty string, the text node itself will not be deleted.</span></span>  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Dim textNode As XText = xmlTree.Nodes().OfType(Of XText)().First()  
  
' The following line does not cause the removal of the text node.  
textNode.Value = ""  
  
Dim textNode2 As XText = xmlTree.Nodes().OfType(Of XText)().First()  
Console.WriteLine(">>{0}<<", textNode2)  
```  
  
 <span data-ttu-id="4db6c-126">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4db6c-126">This example produces the following output:</span></span>  
  
```  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a><span data-ttu-id="4db6c-127">Un nodo di testo vuoto ha effetto sulla serializzazione</span><span class="sxs-lookup"><span data-stu-id="4db6c-127">An Empty Text Node Impacts Serialization</span></span>  
 <span data-ttu-id="4db6c-128">Se un elemento contiene solo un nodo di testo figlio vuoto, verrà serializzato con la sintassi lunga dei tag: `<Child></Child>`.</span><span class="sxs-lookup"><span data-stu-id="4db6c-128">If an element contains only a child text node that is empty, it is serialized with the long tag syntax: `<Child></Child>`.</span></span> <span data-ttu-id="4db6c-129">Se un elemento non contiene alcun tipo di nodo figlio, verrà serializzato con la sintassi breve dei tag: `<Child />`.</span><span class="sxs-lookup"><span data-stu-id="4db6c-129">If an element contains no child nodes whatsoever, it is serialized with the short tag syntax: `<Child />`.</span></span>  
  
```vb  
Dim child1 As XElement = New XElement("Child1", _  
    New XText("") _  
)  
Dim child2 As XElement = New XElement("Child2")  
Console.WriteLine(child1)  
Console.WriteLine(child2)  
```  
  
 <span data-ttu-id="4db6c-130">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4db6c-130">This example produces the following output:</span></span>  
  
```  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a><span data-ttu-id="4db6c-131">Gli spazi dei nomi sono attributi nell'albero LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="4db6c-131">Namespaces are Attributes in the LINQ to XML Tree</span></span>  
 <span data-ttu-id="4db6c-132">Anche se la sintassi delle dichiarazioni di spazi dei nomi è identica a quella degli attributi, in alcune interfacce di programmazione, ad esempio XSLT e XPath, le dichiarazioni di spazi dei nomi non sono considerati attributi.</span><span class="sxs-lookup"><span data-stu-id="4db6c-132">Even though namespace declarations have identical syntax to attributes, in some programming interfaces, such as XSLT and XPath, namespace declarations are not considered to be attributes.</span></span> <span data-ttu-id="4db6c-133">Tuttavia, in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], gli spazi dei nomi vengono archiviati come <xref:System.Xml.Linq.XAttribute>oggetti nell'albero XML.</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="4db6c-133">However, in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], namespaces are stored as <xref:System.Xml.Linq.XAttribute> objects in the XML tree.</span></span> <span data-ttu-id="4db6c-134">Se si scorrono gli attributi per un elemento che contiene una dichiarazione di spazio dei nomi, le dichiarazioni di spazi dei nomi verranno visualizzate come uno degli elementi nella raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="4db6c-134">If you iterate through the attributes for an element that contains a namespace declaration, you will see the namespace declaration as one of the items in the returned collection.</span></span>  
  
 <span data-ttu-id="4db6c-135">Il <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A>proprietà indica se un attributo è una dichiarazione dello spazio dei nomi.</xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A></span><span class="sxs-lookup"><span data-stu-id="4db6c-135">The <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> property indicates whether an attribute is a namespace declaration.</span></span>  
  
```vb  
Dim root As XElement = _   
<Root  
    xmlns='http://www.adventure-works.com'  
    xmlns:fc='www.fourthcoffee.com'  
    AnAttribute='abc'/>  
For Each att As XAttribute In root.Attributes()  
    Console.WriteLine("{0}  IsNamespaceDeclaration:{1}", att, _  
                      att.IsNamespaceDeclaration)  
Next  
```  
  
 <span data-ttu-id="4db6c-136">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4db6c-136">This example produces the following output:</span></span>  
  
```  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a><span data-ttu-id="4db6c-137">I metodi dell'asse di XPath non restituiscono lo spazio vuoto figlio di XDocument</span><span class="sxs-lookup"><span data-stu-id="4db6c-137">XPath Axis Methods Do Not Return Child White Space of XDocument</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="4db6c-138">Consente di nodi di testo figlio di un <xref:System.Xml.Linq.XDocument>, purché i nodi di testo contengano solo spazio vuoto.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="4db6c-138"> allows for child text nodes of an <xref:System.Xml.Linq.XDocument>, as long as the text nodes contain only white space.</span></span> <span data-ttu-id="4db6c-139">Tuttavia, il modello a oggetti XPath non include gli spazi vuoti come nodi figlio di un documento, pertanto quando si scorrono gli elementi figlio di un <xref:System.Xml.Linq.XDocument>utilizzando il <xref:System.Xml.Linq.XContainer.Nodes%2A>asse, verranno restituiti nodi di testo di spazi vuoti.</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="4db6c-139">However, the XPath object model does not include white space as child nodes of a document, so when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the <xref:System.Xml.Linq.XContainer.Nodes%2A> axis, white space text nodes will be returned.</span></span> <span data-ttu-id="4db6c-140">Tuttavia, quando si scorrono gli elementi figlio di un <xref:System.Xml.Linq.XDocument>utilizzando i metodi dell'asse di XPath, nodi testo con spazi vuoti non verranno restituiti.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="4db6c-140">However, when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the XPath axis methods, white space text nodes will not be returned.</span></span>  
  
```vb  
' Create a document with some white space child nodes of the document.  
Dim root As XDocument = XDocument.Parse( _  
"<?xml version='1.0' encoding='utf-8' standalone='yes'?>" & _  
vbNewLine & "<Root/>" & vbNewLine & "<!--a comment-->" & vbNewLine, _  
LoadOptions.PreserveWhitespace)  
  
' Count the white space child nodes using LINQ to XML.  
Console.WriteLine(root.Nodes().OfType(Of XText)().Count())  
  
' Count the white space child nodes using XPathEvaluate.  
Dim nodes As IEnumerable = CType(root.XPathEvaluate("text()"), IEnumerable)  
Console.WriteLine(nodes.OfType(Of XText)().Count())  
```  
  
 <span data-ttu-id="4db6c-141">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4db6c-141">This example produces the following output:</span></span>  
  
```  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a><span data-ttu-id="4db6c-142">Gli oggetti XDeclaration non sono nodi</span><span class="sxs-lookup"><span data-stu-id="4db6c-142">XDeclaration Objects are not Nodes</span></span>  
 <span data-ttu-id="4db6c-143">Quando si scorrono i nodi figlio di un <xref:System.Xml.Linq.XDocument>, l'oggetto dichiarazione XML non verrà.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="4db6c-143">When you iterate through the children nodes of an <xref:System.Xml.Linq.XDocument>, you will not see the XML declaration object.</span></span> <span data-ttu-id="4db6c-144">Si tratta di una proprietà, non di un nodo figlio del documento.</span><span class="sxs-lookup"><span data-stu-id="4db6c-144">It is a property of the document, not a child node of it.</span></span>  
  
```vb  
Dim doc As XDocument = _  
<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
<Root/>  
  
doc.Save("Temp.xml")  
Console.WriteLine(File.ReadAllText("Temp.xml"))  
  
' This shows that there is only one child node of the document.  
Console.WriteLine(doc.Nodes().Count())  
```  
  
 <span data-ttu-id="4db6c-145">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4db6c-145">This example produces the following output:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />  
1  
```  
  
## <a name="see-also"></a><span data-ttu-id="4db6c-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4db6c-146">See Also</span></span>  
 [<span data-ttu-id="4db6c-147">LINQ to XML (Visual Basic) di programmazione avanzata</span><span class="sxs-lookup"><span data-stu-id="4db6c-147">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

