---
title: Panoramica di LINQ to XML (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e85e61b29b9a97469c84abba4e4149b1967e601f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-xml-overview-c"></a><span data-ttu-id="2bbbd-102">Panoramica di LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2bbbd-102">LINQ to XML Overview (C#)</span></span>
<span data-ttu-id="2bbbd-103">XML è stato ampiamente adottato per la formattazione dei dati in una vasta gamma di contesti.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="2bbbd-104">Viene ad esempio usato in applicazioni Web, file di configurazione, file di Microsoft Office Word e in database.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="2bbbd-105"> costituisce un approccio aggiornato e ridisegnato alla programmazione con XML.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-105"> is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="2bbbd-106">Fornisce funzionalità di modifica dei documenti in memoria di Document Object Model (DOM) e supporta espressioni di query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bbbd-106">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="2bbbd-107">Sebbene sintatticamente diverse da XPath, queste espressioni di query offrono funzionalità simili.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="2bbbd-108">Sviluppatori LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="2bbbd-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="2bbbd-109"> è destinato a diversi tipi di sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-109"> targets a variety of developers.</span></span> <span data-ttu-id="2bbbd-110">Per un sviluppatore medio che desidera solo poter eseguire una determinata operazione, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] semplifica il codice XML e consente di eseguire query in modo simile a SQL.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="2bbbd-111">Sono poi sufficienti competenze minime per consentire a un programmatore di imparare a scrivere query potenti e meno estese nel linguaggio di programmazione desiderato.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="2bbbd-112">Gli sviluppatori professionisti possono usare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per incrementare notevolmente la propria produttività.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-112">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="2bbbd-113">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consente di scrivere una minor quantità di codice, che tuttavia risulta più espressivo, compatto e potente.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-113">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="2bbbd-114">È inoltre possibile usare espressioni di query da più domini di dati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="2bbbd-115">Informazioni su LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="2bbbd-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="2bbbd-116"> è un'interfaccia di programmazione XML in memoria con supporto LINQ che consente di usare codice XML dall'interno dei linguaggi di programmazione di [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bbbd-116"> is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="2bbbd-117"> è simile al modello DOM (Document Object Model) in quanto porta in memoria il documento XML.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-117"> is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="2bbbd-118">È quindi possibile eseguire query e modificare il documento e dopo averlo modificato salvarlo in un file o serializzarlo e inviarlo tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="2bbbd-119">Tuttavia, a differenza di DOM, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] offre un nuovo modello a oggetti più leggero e facile da usare che sfrutta le funzionalità del linguaggio in C#.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-119">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in C#.</span></span>  
  
 <span data-ttu-id="2bbbd-120">Il principale vantaggio di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è costituito dall'integrazione con [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bbbd-120">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span></span> <span data-ttu-id="2bbbd-121">Grazie a tale integrazione è possibile scrivere query sul documento XML in memoria per recuperare raccolte di elementi e di attributi.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="2bbbd-122">La funzionalità di query di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è paragonabile a XPath e XQuery, dal punto di vista funzionale ma non sintattico.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-122">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="2bbbd-123">L'integrazione di [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in C# offre una tipizzazione più forte, il controllo in fase di compilazione e il supporto migliorato del debugger.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-123">The integration of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in C# provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="2bbbd-124">Un altre vantaggio di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], costituito dalla possibilità di usare risultati di query come parametri di costruttori di oggetti <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute>, consente di disporre di un approccio potente per la creazione di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-124">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="2bbbd-125">Questo approccio, chiamato *costruzione funzionale* consente agli sviluppatori di trasformare facilmente gli alberi XML da una forma all'altra.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="2bbbd-126">Ad esempio, è possibile avere un ordine d'acquisto XML tipico come descritto in [Sample XML File: Typical Purchase Order (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348) (File XML di esempio: ordine d'acquisto tipico (LINQ to XML).</span><span class="sxs-lookup"><span data-stu-id="2bbbd-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348).</span></span> <span data-ttu-id="2bbbd-127">Usando [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], è possibile eseguire la query seguente per ottenere il valore dell'attributo relativo al numero di parte di ciascun articolo incluso dell'ordine di acquisto:</span><span class="sxs-lookup"><span data-stu-id="2bbbd-127">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```csharp  
IEnumerable<string> partNos =  
from item in purchaseOrder.Descendants("Item")  
select (string) item.Attribute("PartNumber");  
```  
  
 <span data-ttu-id="2bbbd-128">Si supponga ancora, ad esempio, di voler creare un elenco, ordinato in base al numero di parte, degli articoli il cui valore è maggiore di 100 dollari.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="2bbbd-129">Per ottenere queste informazioni, è possibile eseguire la query seguente:</span><span class="sxs-lookup"><span data-stu-id="2bbbd-129">To obtain this information, you could run the following query:</span></span>  
  
```csharp  
IEnumerable<XElement> partNos =  
from item in purchaseOrder.Descendants("Item")  
where (int) item.Element("Quantity") *  
    (decimal) item.Element("USPrice") > 100  
orderby (string)item.Element("PartNumber")  
select item;  
```  
  
 <span data-ttu-id="2bbbd-130">Oltre alle funzionalità [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] include un'interfaccia di programmazione XML migliorata.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-130">In addition to these [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="2bbbd-131">Usando [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile:</span><span class="sxs-lookup"><span data-stu-id="2bbbd-131">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>  
  
-   <span data-ttu-id="2bbbd-132">Caricare codice XML da file o flussi.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-132">Load XML from files or streams.</span></span>  
  
-   <span data-ttu-id="2bbbd-133">Serializzare codice XML in file o flussi.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-133">Serialize XML to files or streams.</span></span>  
  
-   <span data-ttu-id="2bbbd-134">Creare codice XML nuovo usando la costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-134">Create XML from scratch by using functional construction.</span></span>  
  
-   <span data-ttu-id="2bbbd-135">Eseguire una query su codice XML usando assi simili a XPath.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-135">Query XML using XPath-like axes.</span></span>  
  
-   <span data-ttu-id="2bbbd-136">Modificare l'albero XML in memoria usando metodi quali esempio <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>e <xref:System.Xml.Linq.XElement.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
-   <span data-ttu-id="2bbbd-137">Convalidare alberi XML usando lo schema XSD.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-137">Validate XML trees using XSD.</span></span>  
  
-   <span data-ttu-id="2bbbd-138">Usare una combinazione di queste funzionalità per trasformare strutture ad albero XML da una forma in un altra.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="2bbbd-139">Creazione di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="2bbbd-139">Creating XML Trees</span></span>  
 <span data-ttu-id="2bbbd-140">Uno dei vantaggi più significativi della programmazione con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è rappresentato dalla facilità con cui è possibile creare alberi XML.</span><span class="sxs-lookup"><span data-stu-id="2bbbd-140">IOne of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="2bbbd-141">Ad esempio, per creare un piccolo albero XML, è possibile scrivere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2bbbd-141">For example, to create a small XML tree, you can write code as follows:</span></span>  
  
```csharp  
XElement contacts =  
new XElement("Contacts",  
    new XElement("Contact",  
        new XElement("Name", "Patrick Hines"),  
        new XElement("Phone", "206-555-0144",   
            new XAttribute("Type", "Home")),  
        new XElement("phone", "425-555-0145",  
            new XAttribute("Type", "Work")),  
        new XElement("Address",  
            new XElement("Street1", "123 Main St"),  
            new XElement("City", "Mercer Island"),  
            new XElement("State", "WA"),  
            new XElement("Postal", "68042")  
        )  
    )  
);  
```  
  
 <span data-ttu-id="2bbbd-142">Per altre informazioni, vedere [Creazione di alberi XML (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).</span><span class="sxs-lookup"><span data-stu-id="2bbbd-142">For more information, see [Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bbbd-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2bbbd-143">See Also</span></span>  
 <span data-ttu-id="2bbbd-144"><xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="2bbbd-144"><xref:System.Xml.Linq></span></span>   
 [<span data-ttu-id="2bbbd-145">Introduzione (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="2bbbd-145">Getting Started (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)

