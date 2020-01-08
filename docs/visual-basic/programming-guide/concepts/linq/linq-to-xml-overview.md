---
title: Panoramica di LINQ to XML
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: a30340e06a3f8eac9fe2b7718b14ba20363d682f
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636471"
---
# <a name="linq-to-xml-overview-visual-basic"></a><span data-ttu-id="0c11e-102">Panoramica di LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c11e-102">LINQ to XML Overview (Visual Basic)</span></span>
<span data-ttu-id="0c11e-103">XML è stato ampiamente adottato per la formattazione dei dati in una vasta gamma di contesti.</span><span class="sxs-lookup"><span data-stu-id="0c11e-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="0c11e-104">Viene ad esempio usato in applicazioni Web, file di configurazione, file di Microsoft Office Word e in database.</span><span class="sxs-lookup"><span data-stu-id="0c11e-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="0c11e-105">costituisce un approccio aggiornato e ridisegnato alla programmazione con XML.</span><span class="sxs-lookup"><span data-stu-id="0c11e-105">is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="0c11e-106">Fornisce le funzionalità di modifica dei documenti in memoria del Document Object Model (DOM) e supporta le espressioni di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="0c11e-106">It provides the in-memory document-modification capabilities of the Document Object Model (DOM) and supports LINQ query expressions.</span></span> <span data-ttu-id="0c11e-107">Sebbene sintatticamente diverse da XPath, queste espressioni di query offrono funzionalità simili.</span><span class="sxs-lookup"><span data-stu-id="0c11e-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="0c11e-108">Sviluppatori LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="0c11e-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="0c11e-109">è destinato a diversi tipi di sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="0c11e-109">targets a variety of developers.</span></span> <span data-ttu-id="0c11e-110">Per un sviluppatore medio che desidera solo poter eseguire una determinata operazione, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] semplifica il codice XML e consente di eseguire query in modo simile a SQL.</span><span class="sxs-lookup"><span data-stu-id="0c11e-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="0c11e-111">Sono poi sufficienti competenze minime per consentire a un programmatore di imparare a scrivere query potenti e meno estese nel linguaggio di programmazione desiderato.</span><span class="sxs-lookup"><span data-stu-id="0c11e-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="0c11e-112">Gli sviluppatori professionisti possono usare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per incrementare notevolmente la propria produttività.</span><span class="sxs-lookup"><span data-stu-id="0c11e-112">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="0c11e-113">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consente di scrivere una minor quantità di codice, che tuttavia risulta più espressivo, compatto e potente.</span><span class="sxs-lookup"><span data-stu-id="0c11e-113">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="0c11e-114">È inoltre possibile usare espressioni di query da più domini di dati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0c11e-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="0c11e-115">Informazioni su LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="0c11e-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="0c11e-116">è un'interfaccia di programmazione XML in memoria con supporto LINQ che consente di usare codice XML dall'interno dei linguaggi di programmazione .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0c11e-116">is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the .NET Framework programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="0c11e-117">è simile al modello DOM (Document Object Model) in quanto porta in memoria il documento XML.</span><span class="sxs-lookup"><span data-stu-id="0c11e-117">is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="0c11e-118">È quindi possibile eseguire query e modificare il documento e dopo averlo modificato salvarlo in un file o serializzarlo e inviarlo tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="0c11e-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="0c11e-119">Tuttavia, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differisce da DOM: fornisce un nuovo modello a oggetti più leggero e facile da usare e che sfrutta le funzionalità del linguaggio in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0c11e-119">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.</span></span>  
  
 <span data-ttu-id="0c11e-120">Il vantaggio più importante della [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è l'integrazione con LINQ (Language-Integrated Query).</span><span class="sxs-lookup"><span data-stu-id="0c11e-120">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="0c11e-121">Grazie a tale integrazione è possibile scrivere query sul documento XML in memoria per recuperare raccolte di elementi e di attributi.</span><span class="sxs-lookup"><span data-stu-id="0c11e-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="0c11e-122">La funzionalità di query di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è paragonabile a XPath e XQuery, dal punto di vista funzionale ma non sintattico.</span><span class="sxs-lookup"><span data-stu-id="0c11e-122">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="0c11e-123">L'integrazione di LINQ in Visual Basic offre una tipizzazione più forte, il controllo in fase di compilazione e il supporto migliorato del debugger.</span><span class="sxs-lookup"><span data-stu-id="0c11e-123">The integration of LINQ in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="0c11e-124">Un altre vantaggio di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], costituito dalla possibilità di usare risultati di query come parametri di costruttori di oggetti <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute>, consente di disporre di un approccio potente per la creazione di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="0c11e-124">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="0c11e-125">Questo approccio, chiamato *costruzione funzionale* consente agli sviluppatori di trasformare facilmente gli alberi XML da una forma all'altra.</span><span class="sxs-lookup"><span data-stu-id="0c11e-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="0c11e-126">Ad esempio, è possibile avere un ordine d'acquisto XML tipico come descritto in [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md) (File XML di esempio: ordine d'acquisto tipico (LINQ to XML).</span><span class="sxs-lookup"><span data-stu-id="0c11e-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span> <span data-ttu-id="0c11e-127">Usando [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], è possibile eseguire la query seguente per ottenere il valore dell'attributo relativo al numero di parte di ciascun articolo incluso dell'ordine di acquisto:</span><span class="sxs-lookup"><span data-stu-id="0c11e-127">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 <span data-ttu-id="0c11e-128">Si supponga ancora, ad esempio, di voler creare un elenco, ordinato in base al numero di parte, degli articoli il cui valore è maggiore di 100 dollari.</span><span class="sxs-lookup"><span data-stu-id="0c11e-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="0c11e-129">Per ottenere queste informazioni, è possibile eseguire la query seguente:</span><span class="sxs-lookup"><span data-stu-id="0c11e-129">To obtain this information, you could run the following query:</span></span>  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 <span data-ttu-id="0c11e-130">Oltre a queste funzionalità LINQ, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] fornisce un'interfaccia di programmazione XML migliorata.</span><span class="sxs-lookup"><span data-stu-id="0c11e-130">In addition to these LINQ capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="0c11e-131">Tramite [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile:</span><span class="sxs-lookup"><span data-stu-id="0c11e-131">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>  
  
- <span data-ttu-id="0c11e-132">Caricare codice XML da file o flussi.</span><span class="sxs-lookup"><span data-stu-id="0c11e-132">Load XML from files or streams.</span></span>  
  
- <span data-ttu-id="0c11e-133">Serializzare codice XML in file o flussi.</span><span class="sxs-lookup"><span data-stu-id="0c11e-133">Serialize XML to files or streams.</span></span>  
  
- <span data-ttu-id="0c11e-134">Creare codice XML nuovo usando la costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="0c11e-134">Create XML from scratch by using functional construction.</span></span>  
  
- <span data-ttu-id="0c11e-135">Eseguire una query su codice XML usando assi simili a XPath.</span><span class="sxs-lookup"><span data-stu-id="0c11e-135">Query XML using XPath-like axes.</span></span>  
  
- <span data-ttu-id="0c11e-136">Modificare l'albero XML in memoria usando metodi quali esempio <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>e <xref:System.Xml.Linq.XElement.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="0c11e-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
- <span data-ttu-id="0c11e-137">Convalidare alberi XML usando lo schema XSD.</span><span class="sxs-lookup"><span data-stu-id="0c11e-137">Validate XML trees using XSD.</span></span>  
  
- <span data-ttu-id="0c11e-138">Usare una combinazione di queste funzionalità per trasformare strutture ad albero XML da una forma in un altra.</span><span class="sxs-lookup"><span data-stu-id="0c11e-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="0c11e-139">Creazione di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="0c11e-139">Creating XML Trees</span></span>  
 <span data-ttu-id="0c11e-140">Uno dei vantaggi più significativi della programmazione con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è rappresentato dalla facilità con cui è possibile creare alberi XML.</span><span class="sxs-lookup"><span data-stu-id="0c11e-140">IOne of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="0c11e-141">Ad esempio, per creare un piccolo albero XML, è possibile scrivere il codice nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="0c11e-141">For example, to create a small XML tree, you can write  code as follows:</span></span>  
  
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
  
 <span data-ttu-id="0c11e-142">Il compilatore Visual Basic converte i valori letterali XML in chiamate al metodo [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c11e-142">The Visual Basic compiler translates XML literals into [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] method calls.</span></span>  
  
 <span data-ttu-id="0c11e-143">Per ulteriori informazioni, vedere [creazione di alberi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="0c11e-143">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c11e-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c11e-144">See also</span></span>

- <xref:System.Xml.Linq>
- [<span data-ttu-id="0c11e-145">Introduzione (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="0c11e-145">Getting Started (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
- [<span data-ttu-id="0c11e-146">Cenni preliminari su LINQ to XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c11e-146">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)
- [<span data-ttu-id="0c11e-147">XML</span><span class="sxs-lookup"><span data-stu-id="0c11e-147">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
