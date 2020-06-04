---
title: Panoramica della classe XElement
ms.date: 07/20/2015
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
ms.openlocfilehash: a0e50c8a5a14150ee09a328f4dcdd5bc88363621
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413219"
---
# <a name="xelement-class-overview-visual-basic"></a><span data-ttu-id="4df59-102">Cenni preliminari sulla classe XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4df59-102">XElement Class Overview (Visual Basic)</span></span>
<span data-ttu-id="4df59-103"><xref:System.Xml.Linq.XElement> è una delle classi fondamentali di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4df59-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="4df59-104">Rappresenta un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="4df59-104">It represents an XML element.</span></span> <span data-ttu-id="4df59-105">Può essere usata per creare elementi, modificare il contenuto dell'elemento, aggiungere, modificare o eliminare elementi figlio, aggiungere attributi a un elemento oppure serializzare il contenuto di un elemento in formato testo.</span><span class="sxs-lookup"><span data-stu-id="4df59-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="4df59-106">È inoltre possibile definire l'interoperabilità con altre classi di <xref:System.Xml?displayProperty=nameWithType>, ad esempio <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> e <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="4df59-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="xelement-functionality"></a><span data-ttu-id="4df59-107">Funzionalità di XElement</span><span class="sxs-lookup"><span data-stu-id="4df59-107">XElement Functionality</span></span>  
 <span data-ttu-id="4df59-108">In questo argomento viene descritta la funzionalità fornita dalla classe <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="4df59-108">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
### <a name="constructing-xml-trees"></a><span data-ttu-id="4df59-109">Costruzione di alberi XML</span><span class="sxs-lookup"><span data-stu-id="4df59-109">Constructing XML Trees</span></span>  
 <span data-ttu-id="4df59-110">È possibile costruire alberi XML in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="4df59-110">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
- <span data-ttu-id="4df59-111">È possibile costruire un albero XML nel codice.</span><span class="sxs-lookup"><span data-stu-id="4df59-111">You can construct an XML tree in code.</span></span> <span data-ttu-id="4df59-112">Per ulteriori informazioni, vedere [creazione di alberi XML (Visual Basic)](creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="4df59-112">For more information, see [Creating XML Trees (Visual Basic)](creating-xml-trees.md).</span></span>  
  
- <span data-ttu-id="4df59-113">È possibile analizzare codice XML di origini diverse, incluso un oggetto <xref:System.IO.TextReader>, file di testo o un indirizzo Web (URL).</span><span class="sxs-lookup"><span data-stu-id="4df59-113">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="4df59-114">Per ulteriori informazioni, vedere [analisi di XML (Visual Basic)](parsing-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4df59-114">For more information, see [Parsing XML (Visual Basic)](parsing-xml.md).</span></span>  
  
- <span data-ttu-id="4df59-115">È possibile usare un oggetto <xref:System.Xml.XmlReader> per popolare l'albero.</span><span class="sxs-lookup"><span data-stu-id="4df59-115">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="4df59-116">Per altre informazioni, vedere <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="4df59-116">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
- <span data-ttu-id="4df59-117">Se si dispone di un modulo in grado di scrivere contenuto in un oggetto <xref:System.Xml.XmlWriter>, è possibile usare il metodo <xref:System.Xml.Linq.XContainer.CreateWriter%2A> per creare un writer, passare il writer al modulo e quindi usare il contenuto scritto in <xref:System.Xml.XmlWriter> per popolare l'albero XML.</span><span class="sxs-lookup"><span data-stu-id="4df59-117">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="4df59-118">Tuttavia, il modo più comune per creare un albero XML è il seguente:</span><span class="sxs-lookup"><span data-stu-id="4df59-118">However, the most common way to create an XML tree is as follows:</span></span>  
  
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
  
 <span data-ttu-id="4df59-119">Un'altra tecnica molto comune per la creazione di un albero XML prevede l'uso dei risultati di una query LINQ per popolare un albero XML, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4df59-119">Another very common technique for creating an XML tree involves using the results of a LINQ query to populate an XML tree, as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="4df59-120">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="4df59-120">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a><span data-ttu-id="4df59-121">Serializzazione di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="4df59-121">Serializing XML Trees</span></span>  
 <span data-ttu-id="4df59-122">È possibile serializzare l'albero XML in un oggetto <xref:System.IO.File>, <xref:System.IO.TextWriter> o <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="4df59-122">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="4df59-123">Per ulteriori informazioni, vedere [serializzazione di strutture ad albero XML (Visual Basic)](serializing-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="4df59-123">For more information, see [Serializing XML Trees (Visual Basic)](serializing-xml-trees.md).</span></span>  
  
### <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="4df59-124">Recupero di dati XML tramite metodi dell'asse</span><span class="sxs-lookup"><span data-stu-id="4df59-124">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="4df59-125">È possibile usare metodi dell'asse per recuperare attributi, elementi figlio, elementi discendenti ed elementi predecessori.</span><span class="sxs-lookup"><span data-stu-id="4df59-125">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="4df59-126">Le query LINQ operano sui metodi dell'asse e forniscono diversi modi flessibili e potenti per spostarsi ed elaborare un albero XML.</span><span class="sxs-lookup"><span data-stu-id="4df59-126">LINQ queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="4df59-127">Per ulteriori informazioni, vedere [LINQ to XML assi (Visual Basic)](linq-to-xml-axes.md).</span><span class="sxs-lookup"><span data-stu-id="4df59-127">For more information, see [LINQ to XML Axes (Visual Basic)](linq-to-xml-axes.md).</span></span>  
  
### <a name="querying-xml-trees"></a><span data-ttu-id="4df59-128">Esecuzione di query su strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="4df59-128">Querying XML Trees</span></span>  
 <span data-ttu-id="4df59-129">È possibile scrivere query LINQ che consentono di estrarre dati da un albero XML.</span><span class="sxs-lookup"><span data-stu-id="4df59-129">You can write LINQ queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="4df59-130">Per ulteriori informazioni, vedere [esecuzione di query su strutture ad albero XML (Visual Basic)](querying-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="4df59-130">For more information, see [Querying XML Trees (Visual Basic)](querying-xml-trees.md).</span></span>  
  
### <a name="modifying-xml-trees"></a><span data-ttu-id="4df59-131">Modifica di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="4df59-131">Modifying XML Trees</span></span>  
 <span data-ttu-id="4df59-132">È possibile modificare un elemento in modi diversi, ad esempio modificandone il contenuto o gli attributi.</span><span class="sxs-lookup"><span data-stu-id="4df59-132">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="4df59-133">È inoltre possibile rimuovere un elemento dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="4df59-133">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="4df59-134">Per ulteriori informazioni, vedere [modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4df59-134">For more information, see [Modifying XML Trees (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4df59-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4df59-135">See also</span></span>

- [<span data-ttu-id="4df59-136">Panoramica della programmazione LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4df59-136">LINQ to XML Programming Overview (Visual Basic)</span></span>](linq-to-xml-programming-overview.md)
