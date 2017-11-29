---
title: Panoramica della classe XElement (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: bd3ffed4f164ac9edc5e46719f516363220c8d63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="xelement-class-overview-c"></a><span data-ttu-id="968ed-102">Panoramica della classe XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="968ed-102">XElement Class Overview (C#)</span></span>
<span data-ttu-id="968ed-103"><xref:System.Xml.Linq.XElement> è una delle classi fondamentali di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="968ed-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="968ed-104">Rappresenta un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="968ed-104">It represents an XML element.</span></span> <span data-ttu-id="968ed-105">Può essere usata per creare elementi, modificare il contenuto dell'elemento, aggiungere, modificare o eliminare elementi figlio, aggiungere attributi a un elemento oppure serializzare il contenuto di un elemento in formato testo.</span><span class="sxs-lookup"><span data-stu-id="968ed-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="968ed-106">È inoltre possibile definire l'interoperabilità con altre classi di <xref:System.Xml?displayProperty=nameWithType>, ad esempio <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> e <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="968ed-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="xelement-functionality"></a><span data-ttu-id="968ed-107">Funzionalità di XElement</span><span class="sxs-lookup"><span data-stu-id="968ed-107">XElement Functionality</span></span>  
 <span data-ttu-id="968ed-108">In questo argomento viene descritta la funzionalità fornita dalla classe <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="968ed-108">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
### <a name="constructing-xml-trees"></a><span data-ttu-id="968ed-109">Costruzione di alberi XML</span><span class="sxs-lookup"><span data-stu-id="968ed-109">Constructing XML Trees</span></span>  
 <span data-ttu-id="968ed-110">È possibile costruire alberi XML in diversi modi:</span><span class="sxs-lookup"><span data-stu-id="968ed-110">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
-   <span data-ttu-id="968ed-111">È possibile costruire un albero XML nel codice.</span><span class="sxs-lookup"><span data-stu-id="968ed-111">You can construct an XML tree in code.</span></span> <span data-ttu-id="968ed-112">Per altre informazioni, vedere [Creazione di alberi XML (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="968ed-112">For more information, see [Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
-   <span data-ttu-id="968ed-113">È possibile analizzare codice XML di origini diverse, incluso un oggetto <xref:System.IO.TextReader>, file di testo o un indirizzo Web (URL).</span><span class="sxs-lookup"><span data-stu-id="968ed-113">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="968ed-114">Per altre informazioni, vedere [Analisi di codice XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md).</span><span class="sxs-lookup"><span data-stu-id="968ed-114">For more information, see [Parsing XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md).</span></span>  
  
-   <span data-ttu-id="968ed-115">È possibile usare un oggetto <xref:System.Xml.XmlReader> per popolare l'albero.</span><span class="sxs-lookup"><span data-stu-id="968ed-115">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="968ed-116">Per altre informazioni, vedere <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="968ed-116">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
-   <span data-ttu-id="968ed-117">Se si dispone di un modulo in grado di scrivere contenuto in un oggetto <xref:System.Xml.XmlWriter>, è possibile usare il metodo <xref:System.Xml.Linq.XContainer.CreateWriter%2A> per creare un writer, passare il writer al modulo e quindi usare il contenuto scritto in <xref:System.Xml.XmlWriter> per popolare l'albero XML.</span><span class="sxs-lookup"><span data-stu-id="968ed-117">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="968ed-118">Tuttavia, il modo più comune per creare un albero XML è il seguente:</span><span class="sxs-lookup"><span data-stu-id="968ed-118">However, the most common way to create an XML tree is as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="968ed-119">Un'altra tecnica molto comune per la creazione di un albero XML implica l'uso dei risultati di una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] per popolare un albero XML, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="968ed-119">Another very common technique for creating an XML tree involves using the results of a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to populate an XML tree, as shown in the following example:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="968ed-120">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="968ed-120">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a><span data-ttu-id="968ed-121">Serializzazione di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="968ed-121">Serializing XML Trees</span></span>  
 <span data-ttu-id="968ed-122">È possibile serializzare l'albero XML in un oggetto <xref:System.IO.File>, <xref:System.IO.TextWriter> o <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="968ed-122">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="968ed-123">Per altre informazioni, vedere l'articolo sulla [serializzazione delle strutture ad albero XML in C#](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="968ed-123">For more information, see [Serializing XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md).</span></span>  
  
### <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="968ed-124">Recupero di dati XML tramite metodi dell'asse</span><span class="sxs-lookup"><span data-stu-id="968ed-124">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="968ed-125">È possibile usare metodi dell'asse per recuperare attributi, elementi figlio, elementi discendenti ed elementi predecessori.</span><span class="sxs-lookup"><span data-stu-id="968ed-125">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="968ed-126">Le query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] vengono eseguite sui metodi dell'asse e forniscono numerose funzionalità flessibili e potenti per spostarsi in un albero XML ed elaborarla.</span><span class="sxs-lookup"><span data-stu-id="968ed-126">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="968ed-127">Per altre informazioni, vedere [Assi LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md).</span><span class="sxs-lookup"><span data-stu-id="968ed-127">For more information, see [LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md).</span></span>  
  
### <a name="querying-xml-trees"></a><span data-ttu-id="968ed-128">Esecuzione di query su strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="968ed-128">Querying XML Trees</span></span>  
 <span data-ttu-id="968ed-129">È possibile scrivere query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] per estrarre dati da un albero XML.</span><span class="sxs-lookup"><span data-stu-id="968ed-129">You can write [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="968ed-130">Per altre informazioni, vedere [Esecuzione di query su strutture ad albero XML (C#)](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="968ed-130">For more information, see [Querying XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md).</span></span>  
  
### <a name="modifying-xml-trees"></a><span data-ttu-id="968ed-131">Modifica di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="968ed-131">Modifying XML Trees</span></span>  
 <span data-ttu-id="968ed-132">È possibile modificare un elemento in modi diversi, ad esempio modificandone il contenuto o gli attributi.</span><span class="sxs-lookup"><span data-stu-id="968ed-132">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="968ed-133">È inoltre possibile rimuovere un elemento dal relativo elemento padre.</span><span class="sxs-lookup"><span data-stu-id="968ed-133">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="968ed-134">Per altre informazioni, vedere [Modifica degli alberi XML (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="968ed-134">For more information, see [Modifying XML Trees (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="968ed-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="968ed-135">See Also</span></span>  
 [<span data-ttu-id="968ed-136">Panoramica della programmazione con LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="968ed-136">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
