---
title: Panoramica LINQ to XML (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
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
ms.openlocfilehash: 4732aaa64119ba98ab11205e8c93dd8d3eb62d4b
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-overview-visual-basic"></a><span data-ttu-id="a7c03-102">Panoramica LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7c03-102">LINQ to XML Overview (Visual Basic)</span></span>
<span data-ttu-id="a7c03-103">XML è stato ampiamente adottato per la formattazione dei dati in una vasta gamma di contesti.</span><span class="sxs-lookup"><span data-stu-id="a7c03-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="a7c03-104">Viene ad esempio usato in applicazioni Web, file di configurazione, file di Microsoft Office Word e in database.</span><span class="sxs-lookup"><span data-stu-id="a7c03-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="a7c03-105"> costituisce un approccio aggiornato e ridisegnato alla programmazione con XML.</span><span class="sxs-lookup"><span data-stu-id="a7c03-105"> is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="a7c03-106">Fornisce funzionalità di modifica dei documenti in memoria di Document Object Model (DOM) e supporta espressioni di query [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7c03-106">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query expressions.</span></span> <span data-ttu-id="a7c03-107">Sebbene sintatticamente diverse da XPath, queste espressioni di query offrono funzionalità simili.</span><span class="sxs-lookup"><span data-stu-id="a7c03-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="a7c03-108">Sviluppatori LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="a7c03-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="a7c03-109"> è destinato a diversi tipi di sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="a7c03-109"> targets a variety of developers.</span></span> <span data-ttu-id="a7c03-110">Per un sviluppatore medio che desidera solo poter eseguire una determinata operazione, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] semplifica il codice XML e consente di eseguire query in modo simile a SQL.</span><span class="sxs-lookup"><span data-stu-id="a7c03-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="a7c03-111">Sono poi sufficienti competenze minime per consentire a un programmatore di imparare a scrivere query potenti e meno estese nel linguaggio di programmazione desiderato.</span><span class="sxs-lookup"><span data-stu-id="a7c03-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="a7c03-112">Gli sviluppatori professionisti possono usare [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] per incrementare notevolmente la propria produttività.</span><span class="sxs-lookup"><span data-stu-id="a7c03-112">Professional developers can use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="a7c03-113">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] consente di scrivere una minor quantità di codice, che tuttavia risulta più espressivo, compatto e potente.</span><span class="sxs-lookup"><span data-stu-id="a7c03-113">With [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="a7c03-114">È inoltre possibile usare espressioni di query da più domini di dati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="a7c03-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="a7c03-115">Informazioni su LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="a7c03-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="a7c03-116"> è un'interfaccia di programmazione XML in memoria con supporto LINQ che consente di usare codice XML dall'interno dei linguaggi di programmazione di [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7c03-116"> is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="a7c03-117">è ad esempio il modello DOM (Document Object) in quanto porta in memoria il documento XML.</span><span class="sxs-lookup"><span data-stu-id="a7c03-117"> is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="a7c03-118">È quindi possibile eseguire query e modificare il documento e dopo averlo modificato salvarlo in un file o serializzarlo e inviarlo tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="a7c03-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="a7c03-119">Tuttavia, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] diverso da DOM: fornisce un nuovo modello a oggetti più leggero e facile da usare con, e che si avvale delle funzionalità del linguaggio Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a7c03-119">However, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.</span></span>  
  
 <span data-ttu-id="a7c03-120">Il principale vantaggio di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] è costituito dall'integrazione con [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7c03-120">The most important advantage of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is its integration with [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)].</span></span> <span data-ttu-id="a7c03-121">Grazie a tale integrazione è possibile scrivere query sul documento XML in memoria per recuperare raccolte di elementi e di attributi.</span><span class="sxs-lookup"><span data-stu-id="a7c03-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="a7c03-122">La funzionalità di query di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] è paragonabile a XPath e XQuery, dal punto di vista funzionale ma non sintattico.</span><span class="sxs-lookup"><span data-stu-id="a7c03-122">The query capability of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="a7c03-123">L'integrazione di [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] in Visual Basic fornisce più forte tipizzazione, in fase di compilazione, controllo e supporto migliorato del debugger.</span><span class="sxs-lookup"><span data-stu-id="a7c03-123">The integration of [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="a7c03-124">Un altro vantaggio di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] è la possibilità di usare i risultati della query come parametri <xref:System.Xml.Linq.XElement>e <xref:System.Xml.Linq.XAttribute>costruttori di oggetti consente un approccio potente per la creazione di strutture ad albero XML.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a7c03-124">Another advantage of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="a7c03-125">Questo approccio, denominato *costruzione funzionale*, consente agli sviluppatori di trasformare facilmente alberi XML da una forma a un'altra.</span><span class="sxs-lookup"><span data-stu-id="a7c03-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="a7c03-126">Ad esempio, potrebbe essere un file XML tipico ordine di acquisto come descritto in [File XML di esempio: tipico ordine di acquisto (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348).</span><span class="sxs-lookup"><span data-stu-id="a7c03-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348).</span></span> <span data-ttu-id="a7c03-127">Usando [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], è possibile eseguire la query seguente per ottenere il valore dell'attributo relativo al numero di parte di ciascun articolo incluso dell'ordine di acquisto:</span><span class="sxs-lookup"><span data-stu-id="a7c03-127">By using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 <span data-ttu-id="a7c03-128">Si supponga ancora, ad esempio, di voler creare un elenco, ordinato in base al numero di parte, degli articoli il cui valore è maggiore di&100; dollari.</span><span class="sxs-lookup"><span data-stu-id="a7c03-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="a7c03-129">Per ottenere queste informazioni, è possibile eseguire la query seguente:</span><span class="sxs-lookup"><span data-stu-id="a7c03-129">To obtain this information, you could run the following query:</span></span>  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 <span data-ttu-id="a7c03-130">Oltre a queste [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] funzionalità, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] fornisce un'interfaccia di programmazione XML migliorata.</span><span class="sxs-lookup"><span data-stu-id="a7c03-130">In addition to these [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] capabilities, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="a7c03-131">Usando [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] è possibile:</span><span class="sxs-lookup"><span data-stu-id="a7c03-131">Using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you can:</span></span>  
  
-   <span data-ttu-id="a7c03-132">Caricare codice XML da file o flussi.</span><span class="sxs-lookup"><span data-stu-id="a7c03-132">Load XML from files or streams.</span></span>  
  
-   <span data-ttu-id="a7c03-133">Serializzare codice XML in file o flussi.</span><span class="sxs-lookup"><span data-stu-id="a7c03-133">Serialize XML to files or streams.</span></span>  
  
-   <span data-ttu-id="a7c03-134">Creare codice XML nuovo usando la costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="a7c03-134">Create XML from scratch by using functional construction.</span></span>  
  
-   <span data-ttu-id="a7c03-135">Eseguire una query su codice XML usando assi simili a XPath.</span><span class="sxs-lookup"><span data-stu-id="a7c03-135">Query XML using XPath-like axes.</span></span>  
  
-   <span data-ttu-id="a7c03-136">Modificare la struttura ad albero XML in memoria usando metodi, ad esempio <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>e <xref:System.Xml.Linq.XElement.SetValue%2A>.</xref:System.Xml.Linq.XElement.SetValue%2A> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XNode.Remove%2A> </xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="a7c03-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
-   <span data-ttu-id="a7c03-137">Convalidare alberi XML usando lo schema XSD.</span><span class="sxs-lookup"><span data-stu-id="a7c03-137">Validate XML trees using XSD.</span></span>  
  
-   <span data-ttu-id="a7c03-138">Usare una combinazione di queste funzionalità per trasformare strutture ad albero XML da una forma in un altra.</span><span class="sxs-lookup"><span data-stu-id="a7c03-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="a7c03-139">Creazione di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="a7c03-139">Creating XML Trees</span></span>  
 <span data-ttu-id="a7c03-140">Uno dei vantaggi più significativi della programmazione con [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] è rappresentato dalla facilità con cui è possibile creare alberi XML.</span><span class="sxs-lookup"><span data-stu-id="a7c03-140">IOne of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="a7c03-141">Ad esempio, per creare un piccolo albero XML, è possibile scrivere codice come segue:</span><span class="sxs-lookup"><span data-stu-id="a7c03-141">For example, to create a small XML tree, you can write  code as follows:</span></span>  
  
```vb  
Dim contacts = _  
<Contacts>  
    <Contact>  
        <Name>Patrick Hines</Name>  
        <Phone Type="Home">206-555-0144</Phone>  
        <Phone Type="Work">425-555-0145</Phone>  
        <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
        </Address>  
    </Contact>  
</Contacts>  
```  
  
 <span data-ttu-id="a7c03-142">Il [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilatore converte i valori letterali XML in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="a7c03-142">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler translates XML literals into [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] method calls.</span></span>  
  
 <span data-ttu-id="a7c03-143">Per ulteriori informazioni, vedere [la creazione di strutture ad albero XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="a7c03-143">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c03-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7c03-144">See Also</span></span>  
 <span data-ttu-id="a7c03-145"><xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="a7c03-145"><xref:System.Xml.Linq></span></span>   
<span data-ttu-id="a7c03-146"> [Guida introduttiva (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a7c03-146"> [Getting Started (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md) </span></span>  
<span data-ttu-id="a7c03-147"> [Panoramica di LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a7c03-147"> [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md) </span></span>  
<span data-ttu-id="a7c03-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="a7c03-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
