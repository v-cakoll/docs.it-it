---
title: Programmazione con nodi
ms.date: 07/20/2015
ms.assetid: d8422a9b-dd37-44a3-8aac-2237ed9561e0
ms.openlocfilehash: 4cae85d99e7e28506faad8ca39347cf8f271718e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396376"
---
# <a name="programming-with-nodes-visual-basic"></a><span data-ttu-id="750fe-102">Programmazione con nodi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="750fe-102">Programming with Nodes (Visual Basic)</span></span>
<span data-ttu-id="750fe-103">Gli sviluppatori di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] che hanno la necessità di scrivere programmi come un editor XML, un sistema di trasformazioni o un writer di rapporti, spesso devono scrivere programmi che funzionano a un livello di granularità maggiore rispetto a elementi e attributi.</span><span class="sxs-lookup"><span data-stu-id="750fe-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] developers who need to write programs such as an XML editor, a transform system, or a report writer often need to write programs that work at a finer level of granularity than elements and attributes.</span></span> <span data-ttu-id="750fe-104">Devono spesso operare a livello di nodo, modificando i nodi di testo, elaborando istruzioni e commenti.</span><span class="sxs-lookup"><span data-stu-id="750fe-104">They often need to work at the node level, manipulating text nodes, processing instructions, and comments.</span></span> <span data-ttu-id="750fe-105">In questo argomento vengono forniti dettagli sulla programmazione a livello di nodo.</span><span class="sxs-lookup"><span data-stu-id="750fe-105">This topic provides some details about programming at the node level.</span></span>  
  
## <a name="node-details"></a><span data-ttu-id="750fe-106">Dettagli sui nodi</span><span class="sxs-lookup"><span data-stu-id="750fe-106">Node Details</span></span>  
 <span data-ttu-id="750fe-107">I programmatori che operano a livello di nodo devono conoscere diversi dettagli di programmazione.</span><span class="sxs-lookup"><span data-stu-id="750fe-107">There are a number of details of programming that a programmer working at the node level should know.</span></span>  
  
### <a name="parent-property-of-children-nodes-of-xdocument-is-set-to-null"></a><span data-ttu-id="750fe-108">La proprietà padre dei nodi figlio di XDocument è impostata su Null</span><span class="sxs-lookup"><span data-stu-id="750fe-108">Parent Property of Children Nodes of XDocument is Set to Null</span></span>  
 <span data-ttu-id="750fe-109">La proprietà <xref:System.Xml.Linq.XObject.Parent%2A> contiene l'elemento padre <xref:System.Xml.Linq.XElement>, non il nodo padre.</span><span class="sxs-lookup"><span data-stu-id="750fe-109">The <xref:System.Xml.Linq.XObject.Parent%2A> property contains the parent <xref:System.Xml.Linq.XElement>, not the parent node.</span></span> <span data-ttu-id="750fe-110">I nodi figlio di <xref:System.Xml.Linq.XDocument> non hanno un elemento <xref:System.Xml.Linq.XElement> padre.</span><span class="sxs-lookup"><span data-stu-id="750fe-110">Child nodes of <xref:System.Xml.Linq.XDocument> have no parent <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="750fe-111">L'elemento padre è il documento, pertanto la proprietà <xref:System.Xml.Linq.XObject.Parent%2A> per tali nodi è impostata su Null.</span><span class="sxs-lookup"><span data-stu-id="750fe-111">Their parent is the document, so the <xref:System.Xml.Linq.XObject.Parent%2A> property for those nodes is set to null.</span></span>  
  
 <span data-ttu-id="750fe-112">Questo concetto è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="750fe-112">The following example demonstrates this:</span></span>  
  
```vb  
Dim doc As XDocument = XDocument.Parse("<!-- a comment --><Root/>")  
Console.WriteLine(doc.Nodes().OfType(Of XComment).First().Parent Is Nothing)  
Console.WriteLine(doc.Root.Parent Is Nothing)  
```  
  
 <span data-ttu-id="750fe-113">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="750fe-113">This example produces the following output:</span></span>  
  
```console  
True  
True  
```  
  
### <a name="adjacent-text-nodes-are-possible"></a><span data-ttu-id="750fe-114">I nodi di testo adiacenti sono possibili</span><span class="sxs-lookup"><span data-stu-id="750fe-114">Adjacent Text Nodes are Possible</span></span>  
 <span data-ttu-id="750fe-115">In diversi modelli di programmazione XML i nodi di testo adiacenti vengono sempre uniti.</span><span class="sxs-lookup"><span data-stu-id="750fe-115">In a number of XML programming models, adjacent text nodes are always merged.</span></span> <span data-ttu-id="750fe-116">Questa operazione è denominata normalizzazione dei nodi di testo.</span><span class="sxs-lookup"><span data-stu-id="750fe-116">This is sometimes called normalization of text nodes.</span></span> <span data-ttu-id="750fe-117">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] i nodi di testo non vengono normalizzati.</span><span class="sxs-lookup"><span data-stu-id="750fe-117">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] does not normalize text nodes.</span></span> <span data-ttu-id="750fe-118">Se si aggiungono due nodi di testo allo stesso elemento, si otterranno nodi di testo adiacenti.</span><span class="sxs-lookup"><span data-stu-id="750fe-118">If you add two text nodes to the same element, it will result in adjacent text nodes.</span></span> <span data-ttu-id="750fe-119">Se, tuttavia, si aggiunge contenuto specificato come stringa anziché come nodo <xref:System.Xml.Linq.XText>, è possibile che in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] la stringa venga unita con un nodo di testo adiacente.</span><span class="sxs-lookup"><span data-stu-id="750fe-119">However, if you add content specified as a string rather than as an <xref:System.Xml.Linq.XText> node, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] might merge the string with an adjacent text node.</span></span>  
  
 <span data-ttu-id="750fe-120">Questo concetto è illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="750fe-120">The following example demonstrates this:</span></span>  
  
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
  
 <span data-ttu-id="750fe-121">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="750fe-121">This example produces the following output:</span></span>  
  
```console  
1  
1  
2  
```  
  
### <a name="empty-text-nodes-are-possible"></a><span data-ttu-id="750fe-122">I nodi di testo vuoti sono possibili</span><span class="sxs-lookup"><span data-stu-id="750fe-122">Empty Text Nodes are Possible</span></span>  
 <span data-ttu-id="750fe-123">In alcuni modelli di programmazione di XML è garantito che i nodi di testo non contengono la stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="750fe-123">In some XML programming models, text nodes are guaranteed to not contain the empty string.</span></span> <span data-ttu-id="750fe-124">Il concetto di base è che un nodo di testo di questo tipo non ha impatto sulla serializzazione dell'XML.</span><span class="sxs-lookup"><span data-stu-id="750fe-124">The reasoning is that such a text node has no impact on serialization of the XML.</span></span> <span data-ttu-id="750fe-125">Tuttavia, per lo stesso motivo per cui i nodi di testo sono possibili, la rimozione di testo da un nodo di testo impostandone il valore sulla stringa vuota non comporta l'eliminazione del nodo di testo stesso.</span><span class="sxs-lookup"><span data-stu-id="750fe-125">However, for the same reason that adjacent text nodes are possible, if you remove the text from a text node by setting its value to the empty string, the text node itself will not be deleted.</span></span>  
  
```vb  
Dim xmlTree As XElement = <Root>Content</Root>  
Dim textNode As XText = xmlTree.Nodes().OfType(Of XText)().First()  
  
' The following line does not cause the removal of the text node.  
textNode.Value = ""  
  
Dim textNode2 As XText = xmlTree.Nodes().OfType(Of XText)().First()  
Console.WriteLine(">>{0}<<", textNode2)  
```  
  
 <span data-ttu-id="750fe-126">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="750fe-126">This example produces the following output:</span></span>  
  
```console  
>><<  
```  
  
### <a name="an-empty-text-node-impacts-serialization"></a><span data-ttu-id="750fe-127">Un nodo di testo vuoto ha effetto sulla serializzazione</span><span class="sxs-lookup"><span data-stu-id="750fe-127">An Empty Text Node Impacts Serialization</span></span>  
 <span data-ttu-id="750fe-128">Se un elemento contiene solo un nodo di testo figlio vuoto, verrà serializzato con la sintassi lunga dei tag: `<Child></Child>`.</span><span class="sxs-lookup"><span data-stu-id="750fe-128">If an element contains only a child text node that is empty, it is serialized with the long tag syntax: `<Child></Child>`.</span></span> <span data-ttu-id="750fe-129">Se un elemento non contiene alcun tipo di nodo figlio, verrà serializzato con la sintassi breve dei tag: `<Child />`.</span><span class="sxs-lookup"><span data-stu-id="750fe-129">If an element contains no child nodes whatsoever, it is serialized with the short tag syntax: `<Child />`.</span></span>  
  
```vb  
Dim child1 As XElement = New XElement("Child1", _  
    New XText("") _  
)  
Dim child2 As XElement = New XElement("Child2")  
Console.WriteLine(child1)  
Console.WriteLine(child2)  
```  
  
 <span data-ttu-id="750fe-130">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="750fe-130">This example produces the following output:</span></span>  
  
```xml  
<Child1></Child1>  
<Child2 />  
```  
  
### <a name="namespaces-are-attributes-in-the-linq-to-xml-tree"></a><span data-ttu-id="750fe-131">Gli spazi dei nomi sono attributi nell'albero LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="750fe-131">Namespaces are Attributes in the LINQ to XML Tree</span></span>  
 <span data-ttu-id="750fe-132">Anche se la sintassi delle dichiarazioni di spazi dei nomi è identica a quella degli attributi, in alcune interfacce di programmazione, ad esempio XSLT e XPath, le dichiarazioni di spazi dei nomi non sono considerati attributi.</span><span class="sxs-lookup"><span data-stu-id="750fe-132">Even though namespace declarations have identical syntax to attributes, in some programming interfaces, such as XSLT and XPath, namespace declarations are not considered to be attributes.</span></span> <span data-ttu-id="750fe-133">Tuttavia, in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] gli spazi dei nomi vengono archiviati come oggetti <xref:System.Xml.Linq.XAttribute> nell'albero XML.</span><span class="sxs-lookup"><span data-stu-id="750fe-133">However, in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], namespaces are stored as <xref:System.Xml.Linq.XAttribute> objects in the XML tree.</span></span> <span data-ttu-id="750fe-134">Se si scorrono gli attributi per un elemento che contiene una dichiarazione di spazio dei nomi, le dichiarazioni di spazi dei nomi verranno visualizzate come uno degli elementi nella raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="750fe-134">If you iterate through the attributes for an element that contains a namespace declaration, you will see the namespace declaration as one of the items in the returned collection.</span></span>  
  
 <span data-ttu-id="750fe-135">La proprietà <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> indica se un attributo è una dichiarazione di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="750fe-135">The <xref:System.Xml.Linq.XAttribute.IsNamespaceDeclaration%2A> property indicates whether an attribute is a namespace declaration.</span></span>  
  
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
  
 <span data-ttu-id="750fe-136">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="750fe-136">This example produces the following output:</span></span>  
  
```console  
xmlns="http://www.adventure-works.com"  IsNamespaceDeclaration:True  
xmlns:fc="www.fourthcoffee.com"  IsNamespaceDeclaration:True  
AnAttribute="abc"  IsNamespaceDeclaration:False  
```  
  
### <a name="xpath-axis-methods-do-not-return-child-white-space-of-xdocument"></a><span data-ttu-id="750fe-137">I metodi dell'asse di XPath non restituiscono lo spazio vuoto figlio di XDocument</span><span class="sxs-lookup"><span data-stu-id="750fe-137">XPath Axis Methods Do Not Return Child White Space of XDocument</span></span>  
 <span data-ttu-id="750fe-138">In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile usare nodi di testo figlio di un oggetto <xref:System.Xml.Linq.XDocument>, purché i nodi di testo contengano solo spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="750fe-138">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] allows for child text nodes of an <xref:System.Xml.Linq.XDocument>, as long as the text nodes contain only white space.</span></span> <span data-ttu-id="750fe-139">Tuttavia, il modello a oggetti di XPath non include lo spazio vuoto come nodi figlio di un documento, pertanto quando si scorrono gli elementi figlio di <xref:System.Xml.Linq.XDocument> usando l'asse <xref:System.Xml.Linq.XContainer.Nodes%2A>, verranno restituiti nodi di testo di tipo spazio vuoto.</span><span class="sxs-lookup"><span data-stu-id="750fe-139">However, the XPath object model does not include white space as child nodes of a document, so when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the <xref:System.Xml.Linq.XContainer.Nodes%2A> axis, white space text nodes will be returned.</span></span> <span data-ttu-id="750fe-140">Tuttavia, quando si scorrono gli elementi figlio di <xref:System.Xml.Linq.XDocument> usando i metodi dell'asse di XPath, i nodi di testo di tipo spazio vuoto non verranno restituiti.</span><span class="sxs-lookup"><span data-stu-id="750fe-140">However, when you iterate through the children of an <xref:System.Xml.Linq.XDocument> using the XPath axis methods, white space text nodes will not be returned.</span></span>  
  
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
  
 <span data-ttu-id="750fe-141">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="750fe-141">This example produces the following output:</span></span>  
  
```console  
3  
0  
```  
  
### <a name="xdeclaration-objects-are-not-nodes"></a><span data-ttu-id="750fe-142">Gli oggetti XDeclaration non sono nodi</span><span class="sxs-lookup"><span data-stu-id="750fe-142">XDeclaration Objects are not Nodes</span></span>  
 <span data-ttu-id="750fe-143">Quando si scorrono i nodi figlio di <xref:System.Xml.Linq.XDocument>, l'oggetto dichiarazione XML non verrà visualizzato.</span><span class="sxs-lookup"><span data-stu-id="750fe-143">When you iterate through the children nodes of an <xref:System.Xml.Linq.XDocument>, you will not see the XML declaration object.</span></span> <span data-ttu-id="750fe-144">Si tratta di una proprietà, non di un nodo figlio del documento.</span><span class="sxs-lookup"><span data-stu-id="750fe-144">It is a property of the document, not a child node of it.</span></span>  
  
```vb  
Dim doc As XDocument = _  
<?xml version='1.0' encoding='utf-8' standalone='yes'?>  
<Root/>  
  
doc.Save("Temp.xml")  
Console.WriteLine(File.ReadAllText("Temp.xml"))  
  
' This shows that there is only one child node of the document.  
Console.WriteLine(doc.Nodes().Count())  
```  
  
 <span data-ttu-id="750fe-145">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="750fe-145">This example produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<Root />
1
```  
  
## <a name="see-also"></a><span data-ttu-id="750fe-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="750fe-146">See also</span></span>

- [<span data-ttu-id="750fe-147">Programmazione LINQ to XML avanzata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="750fe-147">Advanced LINQ to XML Programming (Visual Basic)</span></span>](advanced-linq-to-xml-programming.md)
