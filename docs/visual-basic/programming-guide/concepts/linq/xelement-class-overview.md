---
title: Cenni preliminari sulla classe XElement (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 78a72effa021408943b9248546106c6fd655ac0b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="xelement-class-overview-visual-basic"></a><span data-ttu-id="4bf0d-102">Cenni preliminari sulla classe XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bf0d-102">XElement Class Overview (Visual Basic)</span></span>
<span data-ttu-id="4bf0d-103">Il <xref:System.Xml.Linq.XElement>è una delle classi fondamentali di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="4bf0d-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span> <span data-ttu-id="4bf0d-104">Rappresenta un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="4bf0d-104">It represents an XML element.</span></span> <span data-ttu-id="4bf0d-105">Può essere usata per creare elementi, modificare il contenuto dell'elemento, aggiungere, modificare o eliminare elementi figlio, aggiungere attributi a un elemento oppure serializzare il contenuto di un elemento in formato testo.</span><span class="sxs-lookup"><span data-stu-id="4bf0d-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="4bf0d-106">È possibile anche interagire con altre classi di <xref:System.Xml?displayProperty=fullName>, ad esempio <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>e <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> </xref:System.Xml?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4bf0d-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=fullName>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="xelement-functionality"></a><span data-ttu-id="4bf0d-107">Funzionalità di XElement</span><span class="sxs-lookup"><span data-stu-id="4bf0d-107">XElement Functionality</span></span>  
 <span data-ttu-id="4bf0d-108">In questo argomento viene descritta la funzionalità fornita dalla <xref:System.Xml.Linq.XElement>classe.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="4bf0d-108">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
### <a name="constructing-xml-trees"></a><span data-ttu-id="4bf0d-109">Costruzione di alberi XML</span><span class="sxs-lookup"><span data-stu-id="4bf0d-109">Constructing XML Trees</span></span>  
 <span data-ttu-id="4bf0d-110">È possibile costruire alberi XML in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="4bf0d-110">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
-   <span data-ttu-id="4bf0d-111">È possibile costruire un albero XML nel codice.</span><span class="sxs-lookup"><span data-stu-id="4bf0d-111">You can construct an XML tree in code.</span></span> <span data-ttu-id="4bf0d-112">Per ulteriori informazioni, vedere [la creazione di strutture ad albero XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="4bf0d-112">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
-   <span data-ttu-id="4bf0d-113">È possibile analizzare il codice XML da origini diverse, incluso un <xref:System.IO.TextReader>, file di testo o un indirizzo Web (URL).</xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="4bf0d-113">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="4bf0d-114">Per ulteriori informazioni, vedere [l'analisi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4bf0d-114">For more information, see [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).</span></span>  
  
-   <span data-ttu-id="4bf0d-115">È possibile utilizzare un <xref:System.Xml.XmlReader>per popolare l'albero.</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="4bf0d-115">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="4bf0d-116">Per ulteriori informazioni, vedere <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</xref:System.Xml.Linq.XNode.ReadFrom%2A></span><span class="sxs-lookup"><span data-stu-id="4bf0d-116">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
-   <span data-ttu-id="4bf0d-117">Se si dispone di un modulo può scrivere contenuto in un <xref:System.Xml.XmlWriter>, è possibile utilizzare il <xref:System.Xml.Linq.XContainer.CreateWriter%2A>per creare un writer, passare il writer al modulo e quindi usare il contenuto che viene scritto il <xref:System.Xml.XmlWriter>per popolare l'albero XML.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A> </xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="4bf0d-117">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="4bf0d-118">Tuttavia, il modo più comune per creare un albero XML è il seguente:</span><span class="sxs-lookup"><span data-stu-id="4bf0d-118">However, the most common way to create an XML tree is as follows:</span></span>  
  
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
  
 <span data-ttu-id="4bf0d-119">Un'altra tecnica molto comune per la creazione di una struttura ad albero XML implica l'utilizzo dei risultati di una [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query per popolare una struttura ad albero XML, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4bf0d-119">Another very common technique for creating an XML tree involves using the results of a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query to populate an XML tree, as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="4bf0d-120">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4bf0d-120">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a><span data-ttu-id="4bf0d-121">Serializzazione di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="4bf0d-121">Serializing XML Trees</span></span>  
 <span data-ttu-id="4bf0d-122">È possibile serializzare l'albero XML in un <xref:System.IO.File>, <xref:System.IO.TextWriter>, o un <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File></span><span class="sxs-lookup"><span data-stu-id="4bf0d-122">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="4bf0d-123">Per ulteriori informazioni, vedere [la serializzazione di strutture ad albero XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="4bf0d-123">For more information, see [Serializing XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).</span></span>  
  
### <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="4bf0d-124">Recupero di dati XML tramite metodi dell'asse</span><span class="sxs-lookup"><span data-stu-id="4bf0d-124">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="4bf0d-125">È possibile usare metodi dell'asse per recuperare attributi, elementi figlio, elementi discendenti ed elementi predecessori.</span><span class="sxs-lookup"><span data-stu-id="4bf0d-125">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="4bf0d-126">Le query [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] vengono eseguite sui metodi dell'asse e forniscono numerose funzionalità flessibili e potenti per spostarsi in un albero XML ed elaborarla.</span><span class="sxs-lookup"><span data-stu-id="4bf0d-126">[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="4bf0d-127">Per ulteriori informazioni, vedere [assi LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span><span class="sxs-lookup"><span data-stu-id="4bf0d-127">For more information, see [LINQ to XML Axes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).</span></span>  
  
### <a name="querying-xml-trees"></a><span data-ttu-id="4bf0d-128">Esecuzione di query su strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="4bf0d-128">Querying XML Trees</span></span>  
 <span data-ttu-id="4bf0d-129">È possibile scrivere [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query che consentono di estrarre dati da un albero XML.</span><span class="sxs-lookup"><span data-stu-id="4bf0d-129">You can write [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="4bf0d-130">Per ulteriori informazioni, vedere [query su strutture ad albero XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="4bf0d-130">For more information, see [Querying XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).</span></span>  
  
### <a name="modifying-xml-trees"></a><span data-ttu-id="4bf0d-131">Modifica di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="4bf0d-131">Modifying XML Trees</span></span>  
 <span data-ttu-id="4bf0d-132">È possibile modificare un elemento in modi diversi, ad esempio modificandone il contenuto o gli attributi.</span><span class="sxs-lookup"><span data-stu-id="4bf0d-132">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="4bf0d-133">È inoltre possibile rimuovere un elemento dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="4bf0d-133">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="4bf0d-134">Per ulteriori informazioni, vedere [la modifica di strutture ad albero XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4bf0d-134">For more information, see [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf0d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bf0d-135">See Also</span></span>  
 [<span data-ttu-id="4bf0d-136">LINQ to Cenni preliminari sulla programmazione XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bf0d-136">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
