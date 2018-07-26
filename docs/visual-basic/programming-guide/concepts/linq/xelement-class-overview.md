---
title: Panoramica della classe XElement (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
ms.openlocfilehash: 321f812176fc129e0922878c1d071621c32ccf57
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199342"
---
# <a name="xelement-class-overview-visual-basic"></a><span data-ttu-id="a7a6a-102">Panoramica della classe XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7a6a-102">XElement Class Overview (Visual Basic)</span></span>
<span data-ttu-id="a7a6a-103"><xref:System.Xml.Linq.XElement> è una delle classi fondamentali di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7a6a-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="a7a6a-104">Rappresenta un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-104">It represents an XML element.</span></span> <span data-ttu-id="a7a6a-105">Può essere usata per creare elementi, modificare il contenuto dell'elemento, aggiungere, modificare o eliminare elementi figlio, aggiungere attributi a un elemento oppure serializzare il contenuto di un elemento in formato testo.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="a7a6a-106">È inoltre possibile definire l'interoperabilità con altre classi di <xref:System.Xml?displayProperty=nameWithType>, ad esempio <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> e <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="xelement-functionality"></a><span data-ttu-id="a7a6a-107">Funzionalità di XElement</span><span class="sxs-lookup"><span data-stu-id="a7a6a-107">XElement Functionality</span></span>  
 <span data-ttu-id="a7a6a-108">In questo argomento viene descritta la funzionalità fornita dalla classe <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-108">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
### <a name="constructing-xml-trees"></a><span data-ttu-id="a7a6a-109">Costruzione di alberi XML</span><span class="sxs-lookup"><span data-stu-id="a7a6a-109">Constructing XML Trees</span></span>  
 <span data-ttu-id="a7a6a-110">È possibile costruire alberi XML in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="a7a6a-110">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
-   <span data-ttu-id="a7a6a-111">È possibile costruire un albero XML nel codice.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-111">You can construct an XML tree in code.</span></span> <span data-ttu-id="a7a6a-112">Per altre informazioni, vedere [creazione di alberi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="a7a6a-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
-   <span data-ttu-id="a7a6a-113">È possibile analizzare codice XML di origini diverse, incluso un oggetto <xref:System.IO.TextReader>, file di testo o un indirizzo Web (URL).</span><span class="sxs-lookup"><span data-stu-id="a7a6a-113">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="a7a6a-114">Per altre informazioni, vedere [analisi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a7a6a-114">For more information, see [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span></span>  
  
-   <span data-ttu-id="a7a6a-115">È possibile usare un oggetto <xref:System.Xml.XmlReader> per popolare l'albero.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-115">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="a7a6a-116">Per altre informazioni, vedere <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-116">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
-   <span data-ttu-id="a7a6a-117">Se si dispone di un modulo in grado di scrivere contenuto in un oggetto <xref:System.Xml.XmlWriter>, è possibile usare il metodo <xref:System.Xml.Linq.XContainer.CreateWriter%2A> per creare un writer, passare il writer al modulo e quindi usare il contenuto scritto in <xref:System.Xml.XmlWriter> per popolare l'albero XML.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-117">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="a7a6a-118">Tuttavia, il modo più comune per creare un albero XML è il seguente:</span><span class="sxs-lookup"><span data-stu-id="a7a6a-118">However, the most common way to create an XML tree is as follows:</span></span>  
  
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
  
 <span data-ttu-id="a7a6a-119">Un'altra tecnica molto comune per la creazione di un albero XML implica l'uso dei risultati di una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] per popolare un albero XML, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="a7a6a-119">Another very common technique for creating an XML tree involves using the results of a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to populate an XML tree, as shown in the following example:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="a7a6a-120">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="a7a6a-120">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a><span data-ttu-id="a7a6a-121">Serializzazione di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="a7a6a-121">Serializing XML Trees</span></span>  
 <span data-ttu-id="a7a6a-122">È possibile serializzare l'albero XML in un oggetto <xref:System.IO.File>, <xref:System.IO.TextWriter> o <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-122">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="a7a6a-123">Per altre informazioni, vedere [serializzazione di alberi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="a7a6a-123">For more information, see [Serializing XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span></span>  
  
### <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="a7a6a-124">Recupero di dati XML tramite metodi dell'asse</span><span class="sxs-lookup"><span data-stu-id="a7a6a-124">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="a7a6a-125">È possibile usare metodi dell'asse per recuperare attributi, elementi figlio, elementi discendenti ed elementi predecessori.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-125">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="a7a6a-126">Le query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] vengono eseguite sui metodi dell'asse e forniscono numerose funzionalità flessibili e potenti per spostarsi in un albero XML ed elaborarla.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-126">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="a7a6a-127">Per altre informazioni, vedere [assi LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span><span class="sxs-lookup"><span data-stu-id="a7a6a-127">For more information, see [LINQ to XML Axes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span></span>  
  
### <a name="querying-xml-trees"></a><span data-ttu-id="a7a6a-128">Esecuzione di query su strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="a7a6a-128">Querying XML Trees</span></span>  
 <span data-ttu-id="a7a6a-129">È possibile scrivere query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] per estrarre dati da un albero XML.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-129">You can write [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="a7a6a-130">Per altre informazioni, vedere [esecuzione di query su strutture ad albero XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="a7a6a-130">For more information, see [Querying XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span></span>  
  
### <a name="modifying-xml-trees"></a><span data-ttu-id="a7a6a-131">Modifica di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="a7a6a-131">Modifying XML Trees</span></span>  
 <span data-ttu-id="a7a6a-132">È possibile modificare un elemento in modi diversi, ad esempio modificandone il contenuto o gli attributi.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-132">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="a7a6a-133">È inoltre possibile rimuovere un elemento dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="a7a6a-133">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="a7a6a-134">Per altre informazioni, vedere [modifica di alberi XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a7a6a-134">For more information, see [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a6a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7a6a-135">See Also</span></span>  
 [<span data-ttu-id="a7a6a-136">LINQ to XML Panoramica della programmazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7a6a-136">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
