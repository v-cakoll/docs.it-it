---
title: Introduzione ai valori letterali XML in Visual Basic2
ms.date: 07/20/2015
ms.assetid: 94fc0e03-978e-4c08-ab6c-0dc3c1e64f10
ms.openlocfilehash: 8b92d22727c50274d57a5e407a0ca42807de3a94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397584"
---
# <a name="introduction-to-xml-literals-in-visual-basic"></a><span data-ttu-id="74853-102">Introduzione ai valori letterali XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="74853-102">Introduction to XML Literals in Visual Basic</span></span>
<span data-ttu-id="74853-103">In questa sezione vengono fornite informazioni sulla creazione di alberi XML in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="74853-103">This section provides information about creating XML trees in Visual Basic.</span></span>  
  
 <span data-ttu-id="74853-104">Per informazioni sull'utilizzo dei risultati delle query LINQ come contenuto di un albero XML, vedere la pagina relativa alla [costruzione funzionale (LINQ to XML) (Visual Basic)](functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="74853-104">For information about using the results of LINQ queries as the content for an XML tree, see [Functional Construction (LINQ to XML) (Visual Basic)](functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="74853-105">Per ulteriori informazioni sui valori letterali XML in Visual Basic, vedere [Panoramica di LINQ to XML in Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="74853-105">For more information on XML literals in Visual Basic, see [Overview of LINQ to XML in Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md).</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="74853-106">Creazione di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="74853-106">Creating XML Trees</span></span>  
 <span data-ttu-id="74853-107">Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Xml.Linq.XElement>, in questo caso `contacts`.</span><span class="sxs-lookup"><span data-stu-id="74853-107">The following example shows how to create an <xref:System.Xml.Linq.XElement>, in this case `contacts`:</span></span>  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
### <a name="creating-an-xelement-with-simple-content"></a><span data-ttu-id="74853-108">Creazione di un XElement con contenuto semplice</span><span class="sxs-lookup"><span data-stu-id="74853-108">Creating an XElement with Simple Content</span></span>  
 <span data-ttu-id="74853-109">È possibile creare un oggetto <xref:System.Xml.Linq.XElement> con contenuto semplice, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="74853-109">You can create an <xref:System.Xml.Linq.XElement> that contains simple content, as follows:</span></span>  
  
```vb  
Dim n as XElement = <Customer>Adventure Works</Customer>  
Console.WriteLine(n)
```  
  
 <span data-ttu-id="74853-110">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="74853-110">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
### <a name="creating-an-empty-element"></a><span data-ttu-id="74853-111">Creazione di un elemento vuoto</span><span class="sxs-lookup"><span data-stu-id="74853-111">Creating an Empty Element</span></span>  
 <span data-ttu-id="74853-112">È possibile creare un oggetto <xref:System.Xml.Linq.XElement> vuoto, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="74853-112">You can create an empty <xref:System.Xml.Linq.XElement>, as follows:</span></span>  
  
```vb  
Dim n As XElement = <Customer/>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="74853-113">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="74853-113">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="using-embedded-expressions"></a><span data-ttu-id="74853-114">Uso di espressioni incorporate</span><span class="sxs-lookup"><span data-stu-id="74853-114">Using Embedded Expressions</span></span>  
 <span data-ttu-id="74853-115">Un'importante funzionalità dei valori letterali XML è che consentono di usare espressioni incorporate.</span><span class="sxs-lookup"><span data-stu-id="74853-115">An important feature of XML literals is that they allow embedded expressions.</span></span> <span data-ttu-id="74853-116">Con le espressioni incorporate è possibile valutare un'espressione e inserirne i risultati nell'albero XML.</span><span class="sxs-lookup"><span data-stu-id="74853-116">Embedded expressions enable you to evaluate an expression and insert the results of the expression into the XML tree.</span></span> <span data-ttu-id="74853-117">Se l'espressione restituisce un tipo di <xref:System.Xml.Linq.XElement>, nell'albero viene inserito un elemento.</span><span class="sxs-lookup"><span data-stu-id="74853-117">If the expression evaluates to a type of <xref:System.Xml.Linq.XElement>, an element is inserted into the tree.</span></span> <span data-ttu-id="74853-118">Se l'espressione restituisce un tipo di <xref:System.Xml.Linq.XAttribute>, nell'albero viene inserito un attributo.</span><span class="sxs-lookup"><span data-stu-id="74853-118">If the expression evaluates to a type of <xref:System.Xml.Linq.XAttribute>, an attribute is inserted into the tree.</span></span> <span data-ttu-id="74853-119">È possibile inserire elementi e attributi nell'albero solo nei casi in cui sono validi.</span><span class="sxs-lookup"><span data-stu-id="74853-119">You can insert elements and attributes into the tree only where they are valid.</span></span>  
  
 <span data-ttu-id="74853-120">È importante notare che un'espressione incorporata può includere una sola espressione.</span><span class="sxs-lookup"><span data-stu-id="74853-120">It is important to note that only a single expression can go into an embedded expression.</span></span> <span data-ttu-id="74853-121">Non è possibile incorporare più istruzioni.</span><span class="sxs-lookup"><span data-stu-id="74853-121">You cannot embed multiple statements.</span></span> <span data-ttu-id="74853-122">Se un'espressione si estende oltre una singola riga, è necessario usare il carattere di continuazione di riga.</span><span class="sxs-lookup"><span data-stu-id="74853-122">If an expression extends beyond a single line, you must use the line continuation character.</span></span>  
  
 <span data-ttu-id="74853-123">Se si usa un'espressione incorporata per aggiungere nodi (inclusi elementi) e attributi esistenti a un nuovo albero XML e se per i nodi esistenti è già presente un elemento padre, i nodi vengono duplicati.</span><span class="sxs-lookup"><span data-stu-id="74853-123">If you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree and if the existing nodes are already parented, the nodes are cloned.</span></span> <span data-ttu-id="74853-124">I nuovi nodi duplicati vengono collegati al nuovo albero XML.</span><span class="sxs-lookup"><span data-stu-id="74853-124">The newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="74853-125">Se per i nodi esistenti non è presente un elemento padre, i nodi vengono semplicemente collegati al nuovo albero XML.</span><span class="sxs-lookup"><span data-stu-id="74853-125">If the existing nodes are not parented, the nodes are simply attached to the new XML tree.</span></span> <span data-ttu-id="74853-126">Tale comportamento è illustrato nell'ultimo esempio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="74853-126">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="74853-127">Nell'esempio seguente viene usata un'espressione incorporata per inserire un elemento nell'albero.</span><span class="sxs-lookup"><span data-stu-id="74853-127">The following example uses an embedded expression to insert an element into the tree:</span></span>  
  
```vb  
xmlTree1 As XElement = _  
    <Root>  
        <Child>Contents</Child>  
    </Root>  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child> %>  
    </Root>  
Console.WriteLine(xmlTree2)  
```  
  
 <span data-ttu-id="74853-128">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="74853-128">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>Contents</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-content"></a><span data-ttu-id="74853-129">Uso di espressioni incorporate per il contenuto</span><span class="sxs-lookup"><span data-stu-id="74853-129">Using Embedded Expressions for Content</span></span>  
 <span data-ttu-id="74853-130">È possibile usare un'espressione incorporata per fornire il contenuto di un elemento:</span><span class="sxs-lookup"><span data-stu-id="74853-130">You can use an embedded expression to supply the content of an element:</span></span>  
  
```vb  
Dim str As String  
str = "Some content"  
Dim root As XElement = <Root><%= str %></Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="74853-131">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="74853-131">This example produces the following output:</span></span>  
  
```xml  
<Root>Some content</Root>  
```  
  
### <a name="using-a-linq-query-in-an-embedded-expression"></a><span data-ttu-id="74853-132">Uso di una query LINQ in un'espressione incorporata</span><span class="sxs-lookup"><span data-stu-id="74853-132">Using a LINQ Query in an Embedded Expression</span></span>  
 <span data-ttu-id="74853-133">È possibile usare i risultati di una query LINQ per il contenuto di un elemento:</span><span class="sxs-lookup"><span data-stu-id="74853-133">You can use the results of a LINQ query for the content of an element:</span></span>  
  
```vb  
Dim arr As Integer() = {1, 2, 3}  
  
Dim n As XElement = _  
    <Root>  
        <%= From i In arr Select <Child><%= i %></Child> %>  
    </Root>  
  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="74853-134">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="74853-134">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Child>3</Child>  
</Root>  
```  
  
### <a name="using-embedded-expressions-for-node-names"></a><span data-ttu-id="74853-135">Uso di espressioni incorporate per i nomi di nodo</span><span class="sxs-lookup"><span data-stu-id="74853-135">Using Embedded Expressions for Node Names</span></span>  
 <span data-ttu-id="74853-136">È inoltre possibile usare espressioni incorporate per calcolare nomi e valori di attributi ed elementi:</span><span class="sxs-lookup"><span data-stu-id="74853-136">You can also use embedded expressions to calculate attribute names, attribute values, element names, and element values:</span></span>  
  
```vb  
Dim eleName As String = "ele"  
Dim attName As String = "att"  
Dim attValue As String = "aValue"  
Dim eleValue As String = "eValue"  
Dim n As XElement = _  
    <Root <%= attName %>=<%= attValue %>>  
        <<%= eleName %>>  
            <%= eleValue %>  
        </>  
    </Root>  
Console.WriteLine(n)  
```  
  
 <span data-ttu-id="74853-137">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="74853-137">This example produces the following output:</span></span>  
  
```xml  
<Root att="aValue">  
  <ele>eValue</ele>  
</Root>  
```  
  
### <a name="cloning-vs-attaching"></a><span data-ttu-id="74853-138">Clonazione e collegamento</span><span class="sxs-lookup"><span data-stu-id="74853-138">Cloning vs. Attaching</span></span>  
 <span data-ttu-id="74853-139">Come accennato in precedenza, se si usa un'espressione incorporata per aggiungere nodi (inclusi elementi) e attributi esistenti a un nuovo albero XML e se per i nodi esistenti è già presente un elemento padre, i nodi vengono duplicati. I nodi appena duplicati vengono quindi collegati al nuovo albero.</span><span class="sxs-lookup"><span data-stu-id="74853-139">As mentioned earlier, if you use an embedded expression to add existing nodes (including elements) and attributes to a new XML tree, if the existing nodes are already parented, the nodes are cloned and the newly cloned nodes are attached to the new XML tree.</span></span> <span data-ttu-id="74853-140">Se per i nodi esistenti non è presente un elemento padre, i nodi vengono semplicemente collegati al nuovo albero XML.</span><span class="sxs-lookup"><span data-stu-id="74853-140">If the existing nodes are not parented, they are simply attached to the new XML tree.</span></span>  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 <span data-ttu-id="74853-141">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="74853-141">This example produces the following output:</span></span>  
  
```console  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="74853-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74853-142">See also</span></span>

- [<span data-ttu-id="74853-143">Creazione di strutture ad albero XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74853-143">Creating XML Trees (Visual Basic)</span></span>](creating-xml-trees.md)
