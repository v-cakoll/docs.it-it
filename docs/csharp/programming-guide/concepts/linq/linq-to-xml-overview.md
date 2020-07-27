---
title: Panoramica di LINQ to XML (C#)
description: LINQ to XML sfrutta il Framework .NET LINQ per fornire funzionalità di modifica dei documenti in memoria ed espressioni di query con funzionalità come XPath.
ms.date: 10/30/2018
ms.assetid: 716b94d3-0091-4de1-8e05-41bc069fa9dd
ms.openlocfilehash: d2e4cf4e63d1a6ed7c1f0c163c12bb422b55ba11
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165354"
---
# <a name="linq-to-xml-overview-c"></a><span data-ttu-id="cf653-103">Panoramica di LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="cf653-103">LINQ to XML Overview (C#)</span></span>

<span data-ttu-id="cf653-104">LINQ to XML offre un'interfaccia di programmazione XML in memoria che usa .NET Language-Integrated Query (LINQ) Framework.</span><span class="sxs-lookup"><span data-stu-id="cf653-104">LINQ to XML provides an in-memory XML programming interface that leverages the .NET Language-Integrated Query (LINQ) Framework.</span></span> <span data-ttu-id="cf653-105">LINQ to XML usa le funzionalità .NET e può essere paragonato a un'interfaccia di programmazione XML DOM aggiornata e riprogettata.</span><span class="sxs-lookup"><span data-stu-id="cf653-105">LINQ to XML uses .NET capabilities and is comparable to an updated, redesigned Document Object Model (DOM) XML programming interface.</span></span>

<span data-ttu-id="cf653-106">XML è stato ampiamente adottato per la formattazione dei dati in una vasta gamma di contesti.</span><span class="sxs-lookup"><span data-stu-id="cf653-106">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="cf653-107">Viene ad esempio usato in applicazioni Web, file di configurazione, file di Microsoft Office Word e in database.</span><span class="sxs-lookup"><span data-stu-id="cf653-107">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="cf653-108">costituisce un approccio aggiornato e ridisegnato alla programmazione con XML.</span><span class="sxs-lookup"><span data-stu-id="cf653-108">is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="cf653-109">Fornisce le funzionalità di modifica dei documenti in memoria del Document Object Model (DOM) e supporta le espressioni di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="cf653-109">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports LINQ query expressions.</span></span> <span data-ttu-id="cf653-110">Sebbene sintatticamente diverse da XPath, queste espressioni di query offrono funzionalità simili.</span><span class="sxs-lookup"><span data-stu-id="cf653-110">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>

## <a name="linq-to-xml-developers"></a><span data-ttu-id="cf653-111">Sviluppatori LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="cf653-111">LINQ to XML Developers</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="cf653-112">è destinato a diversi tipi di sviluppatori.</span><span class="sxs-lookup"><span data-stu-id="cf653-112">targets a variety of developers.</span></span> <span data-ttu-id="cf653-113">Per un sviluppatore medio che desidera solo poter eseguire una determinata operazione, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] semplifica il codice XML e consente di eseguire query in modo simile a SQL.</span><span class="sxs-lookup"><span data-stu-id="cf653-113">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="cf653-114">Sono poi sufficienti competenze minime per consentire a un programmatore di imparare a scrivere query potenti e meno estese nel linguaggio di programmazione desiderato.</span><span class="sxs-lookup"><span data-stu-id="cf653-114">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>

<span data-ttu-id="cf653-115">Gli sviluppatori professionisti possono usare [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per incrementare notevolmente la propria produttività.</span><span class="sxs-lookup"><span data-stu-id="cf653-115">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="cf653-116">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consente di scrivere una minor quantità di codice, che tuttavia risulta più espressivo, compatto e potente.</span><span class="sxs-lookup"><span data-stu-id="cf653-116">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="cf653-117">È inoltre possibile usare espressioni di query da più domini di dati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="cf653-117">They can use query expressions from multiple data domains at the same time.</span></span>

## <a name="what-is-linq-to-xml"></a><span data-ttu-id="cf653-118">Informazioni su LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="cf653-118">What Is LINQ to XML?</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="cf653-119">è un'interfaccia di programmazione XML in memoria abilitata per LINQ che consente di usare codice XML dall'interno dei linguaggi di programmazione .NET.</span><span class="sxs-lookup"><span data-stu-id="cf653-119">is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the .NET programming languages.</span></span>

[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="cf653-120">è simile al modello DOM (Document Object Model) in quanto porta in memoria il documento XML.</span><span class="sxs-lookup"><span data-stu-id="cf653-120">is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="cf653-121">È quindi possibile eseguire query e modificare il documento e dopo averlo modificato salvarlo in un file o serializzarlo e inviarlo tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="cf653-121">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="cf653-122">Tuttavia, a differenza di DOM, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] offre un nuovo modello a oggetti più leggero e facile da usare che sfrutta le funzionalità del linguaggio in C#.</span><span class="sxs-lookup"><span data-stu-id="cf653-122">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in C#.</span></span>

<span data-ttu-id="cf653-123">Il vantaggio più importante di è costituito dall' [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] integrazione con LINQ (Language-Integrated Query).</span><span class="sxs-lookup"><span data-stu-id="cf653-123">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with Language-Integrated Query (LINQ).</span></span> <span data-ttu-id="cf653-124">Grazie a tale integrazione è possibile scrivere query sul documento XML in memoria per recuperare raccolte di elementi e di attributi.</span><span class="sxs-lookup"><span data-stu-id="cf653-124">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="cf653-125">La funzionalità di query di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è paragonabile a XPath e XQuery, dal punto di vista funzionale ma non sintattico.</span><span class="sxs-lookup"><span data-stu-id="cf653-125">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="cf653-126">L'integrazione di LINQ in C# fornisce una tipizzazione più forte, il controllo in fase di compilazione e il supporto migliorato del debugger.</span><span class="sxs-lookup"><span data-stu-id="cf653-126">The integration of LINQ in C# provides stronger typing, compile-time checking, and improved debugger support.</span></span>

<span data-ttu-id="cf653-127">Un altre vantaggio di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], costituito dalla possibilità di usare risultati di query come parametri di costruttori di oggetti <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute>, consente di disporre di un approccio potente per la creazione di alberi XML.</span><span class="sxs-lookup"><span data-stu-id="cf653-127">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="cf653-128">Questo approccio, chiamato *costruzione funzionale* consente agli sviluppatori di trasformare facilmente gli alberi XML da una forma all'altra.</span><span class="sxs-lookup"><span data-stu-id="cf653-128">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>

<span data-ttu-id="cf653-129">Ad esempio, è possibile avere un ordine d'acquisto XML tipico come descritto in [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md) (File XML di esempio: ordine d'acquisto tipico (LINQ to XML).</span><span class="sxs-lookup"><span data-stu-id="cf653-129">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span> <span data-ttu-id="cf653-130">Usando [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], è possibile eseguire la query seguente per ottenere il valore dell'attributo relativo al numero di parte di ciascun articolo incluso dell'ordine di acquisto:</span><span class="sxs-lookup"><span data-stu-id="cf653-130">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<string> partNos =  from item in purchaseOrder.Descendants("Item")
                               select (string) item.Attribute("PartNumber");
```

<span data-ttu-id="cf653-131">Ciò può essere riscritto nel modulo di sintassi del metodo:</span><span class="sxs-lookup"><span data-stu-id="cf653-131">This can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<string> partNos = purchaseOrder.Descendants("Item").Select(x => (string) x.Attribute("PartNumber"));
```

<span data-ttu-id="cf653-132">Si supponga ancora, ad esempio, di voler creare un elenco, ordinato in base al numero di parte, degli articoli il cui valore è maggiore di 100 dollari.</span><span class="sxs-lookup"><span data-stu-id="cf653-132">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="cf653-133">Per ottenere queste informazioni, è possibile eseguire la query seguente:</span><span class="sxs-lookup"><span data-stu-id="cf653-133">To obtain this information, you could run the following query:</span></span>

```csharp
// Load the XML file from our project directory containing the purchase orders
var filename = "PurchaseOrder.xml";
var currentDirectory = Directory.GetCurrentDirectory();
var purchaseOrderFilepath = Path.Combine(currentDirectory, filename);

XElement purchaseOrder = XElement.Load(purchaseOrderFilepath);

IEnumerable<XElement> pricesByPartNos =  from item in purchaseOrder.Descendants("Item")
                                 where (int) item.Element("Quantity") * (decimal) item.Element("USPrice") > 100
                                 orderby (string)item.Element("PartNumber")
                                 select item;
```

<span data-ttu-id="cf653-134">Ciò può essere riscritto nel modulo di sintassi del metodo:</span><span class="sxs-lookup"><span data-stu-id="cf653-134">Again, this can be rewritten in method syntax form:</span></span>

```csharp
IEnumerable<XElement> pricesByPartNos = purchaseOrder.Descendants("Item")
                                        .Where(item => (int)item.Element("Quantity") * (decimal)item.Element("USPrice") > 100)
                                        .OrderBy(order => order.Element("PartNumber"));
```

<span data-ttu-id="cf653-135">Oltre a queste funzionalità LINQ, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] fornisce un'interfaccia di programmazione XML migliorata.</span><span class="sxs-lookup"><span data-stu-id="cf653-135">In addition to these LINQ capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="cf653-136">Usando [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è possibile:</span><span class="sxs-lookup"><span data-stu-id="cf653-136">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>

- <span data-ttu-id="cf653-137">Caricare XML da [file](how-to-load-xml-from-a-file.md) o [flussi](how-to-stream-xml-fragments-from-an-xmlreader.md).</span><span class="sxs-lookup"><span data-stu-id="cf653-137">Load XML from [files](how-to-load-xml-from-a-file.md) or [streams](how-to-stream-xml-fragments-from-an-xmlreader.md).</span></span>

- <span data-ttu-id="cf653-138">Serializzare codice XML in file o flussi.</span><span class="sxs-lookup"><span data-stu-id="cf653-138">Serialize XML to files or streams.</span></span>

- <span data-ttu-id="cf653-139">Creare codice XML nuovo usando la costruzione funzionale.</span><span class="sxs-lookup"><span data-stu-id="cf653-139">Create XML from scratch by using functional construction.</span></span>

- <span data-ttu-id="cf653-140">Eseguire una query su codice XML usando assi simili a XPath.</span><span class="sxs-lookup"><span data-stu-id="cf653-140">Query XML using XPath-like axes.</span></span>

- <span data-ttu-id="cf653-141">Modificare l'albero XML in memoria usando metodi quali esempio <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>e <xref:System.Xml.Linq.XElement.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf653-141">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>

- <span data-ttu-id="cf653-142">Convalidare alberi XML usando lo schema XSD.</span><span class="sxs-lookup"><span data-stu-id="cf653-142">Validate XML trees using XSD.</span></span>

- <span data-ttu-id="cf653-143">Usare una combinazione di queste funzionalità per trasformare strutture ad albero XML da una forma in un altra.</span><span class="sxs-lookup"><span data-stu-id="cf653-143">Use a combination of these features to transform XML trees from one shape into another.</span></span>

## <a name="creating-xml-trees"></a><span data-ttu-id="cf653-144">Creazione di strutture ad albero XML</span><span class="sxs-lookup"><span data-stu-id="cf653-144">Creating XML Trees</span></span>

<span data-ttu-id="cf653-145">Uno dei vantaggi più significativi della programmazione con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] è rappresentato dalla facilità con cui è possibile creare alberi XML.</span><span class="sxs-lookup"><span data-stu-id="cf653-145">One of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="cf653-146">Ad esempio, per creare un piccolo albero XML, è possibile scrivere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="cf653-146">For example, to create a small XML tree, you can write code as follows:</span></span>

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

<span data-ttu-id="cf653-147">Per altre informazioni, vedere [Creazione di alberi XML (C#)](./creating-xml-trees-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="cf653-147">For more information, see [Creating XML Trees (C#)](./creating-xml-trees-linq-to-xml-2.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf653-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf653-148">See also</span></span>

- [<span data-ttu-id="cf653-149">Riferimenti (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="cf653-149">Reference (LINQ to XML)</span></span>](./reference-linq-to-xml.md)
- [<span data-ttu-id="cf653-150">LINQ to XML rispetto a DOM (C#)</span><span class="sxs-lookup"><span data-stu-id="cf653-150">LINQ to XML vs. DOM (C#)</span></span>](./linq-to-xml-vs-dom.md)
- [<span data-ttu-id="cf653-151">LINQ to XML e altre tecnologie XML</span><span class="sxs-lookup"><span data-stu-id="cf653-151">LINQ to XML vs. Other XML Technologies</span></span>](./linq-to-xml-vs-other-xml-technologies.md)
- <xref:System.Xml.Linq>
