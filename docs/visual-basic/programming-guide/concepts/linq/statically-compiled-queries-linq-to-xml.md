---
title: Query compilate in modo statico (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
ms.openlocfilehash: f020c1ed8627df8c8386a059f0cea372e8df363e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406768"
---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="77641-102">Query compilate in modo statico (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77641-102">Statically Compiled Queries (LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="77641-103">Uno dei più importanti vantaggi a livello di prestazioni di LINQ to XML, rispetto a <xref:System.Xml.XmlDocument>, consiste nel fatto che le query in LINQ to XML sono compilate in modo statico, mentre le query XPath devono essere interpretate in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="77641-103">One of the most important performance benefits LINQ to XML, as opposed to <xref:System.Xml.XmlDocument>, is that queries in LINQ to XML are statically compiled, whereas XPath queries must be interpreted at run time.</span></span> <span data-ttu-id="77641-104">Questa funzionalità è incorporata in LINQ to XML, pertanto non è necessario eseguire passaggi aggiuntivi per sfruttarla, ma è utile capire la distinzione per saper scegliere tra le due tecnologie.</span><span class="sxs-lookup"><span data-stu-id="77641-104">This feature is built in to LINQ to XML, so you do not have to perform extra steps to take advantage of it, but it is helpful to understand the distinction when choosing between the two technologies.</span></span> <span data-ttu-id="77641-105">In questo argomento viene illustrata la differenza</span><span class="sxs-lookup"><span data-stu-id="77641-105">This topic explains the difference.</span></span>

## <a name="statically-compiled-queries-vs-xpath"></a><span data-ttu-id="77641-106">Confronto tra query compilate in modo statico e XPath</span><span class="sxs-lookup"><span data-stu-id="77641-106">Statically Compiled Queries vs. XPath</span></span>

<span data-ttu-id="77641-107">Nell'esempio seguente viene illustrato come ottenere gli elementi discendenti con un nome specificato e con un attributo con un valore specificato.</span><span class="sxs-lookup"><span data-stu-id="77641-107">The following example shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>

<span data-ttu-id="77641-108">Di seguito è riportata l'espressione XPath equivalente:</span><span class="sxs-lookup"><span data-stu-id="77641-108">The following is the equivalent XPath expression:</span></span>

```vb
//Address[@Type='Shipping']
```

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = From el In po.Descendants("Address")
            Where el.@Type = "Shipping"

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="77641-109">L'espressione di query di questo esempio viene scritta di nuovo dal compilatore nella sintassi delle query basate su metodo.</span><span class="sxs-lookup"><span data-stu-id="77641-109">The query expression in this example is re-written by the compiler to method-based query syntax.</span></span> <span data-ttu-id="77641-110">L'esempio seguente, scritto nella sintassi delle query basate su metodo, produce gli stessi risultati del precedente:</span><span class="sxs-lookup"><span data-stu-id="77641-110">The following example, which is written in method-based query syntax, produces the same results as the previous one:</span></span>

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="77641-111">Il metodo <xref:System.Linq.Enumerable.Where%2A> è un metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="77641-111">The <xref:System.Linq.Enumerable.Where%2A> method is an extension method.</span></span> <span data-ttu-id="77641-112">Per altre informazioni, vedere [Metodi di estensione](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="77641-112">For more information, see [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span> <span data-ttu-id="77641-113">Poiché <xref:System.Linq.Enumerable.Where%2A> è un metodo di estensione, la query precedente è compilata come se fosse scritta come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="77641-113">Because <xref:System.Linq.Enumerable.Where%2A> is an extension method, the query above is compiled as though it were written as follows:</span></span>

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

<span data-ttu-id="77641-114">Questo esempio produce esattamente gli stessi risultati dei due esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="77641-114">This example produces exactly the same results as the previous two examples.</span></span> <span data-ttu-id="77641-115">Questo illustra il fatto che le query sono compilate efficacemente in chiamate ai metodi collegate in modo statico.</span><span class="sxs-lookup"><span data-stu-id="77641-115">This illustrates the fact that queries are effectively compiled into statically linked method calls.</span></span> <span data-ttu-id="77641-116">Questo fatto, insieme alla semantica di esecuzione posticipata degli iteratori, consente un miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="77641-116">This, combined with the deferred execution semantics of iterators, improves performance.</span></span> <span data-ttu-id="77641-117">Per ulteriori informazioni sulla semantica di esecuzione posticipata degli iteratori, vedere [esecuzione posticipata e valutazione lazy in LINQ to XML (Visual Basic)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="77641-117">For more information about the deferred execution semantics of iterators, see [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>

> [!NOTE]
> <span data-ttu-id="77641-118">Questi esempi rappresentano il codice che potrebbe venire scritto dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="77641-118">These examples are representative of the code that the compiler might write.</span></span> <span data-ttu-id="77641-119">L'implementazione effettiva potrebbe differire leggermente da questi esempi, ma le prestazioni saranno la stesse o simili.</span><span class="sxs-lookup"><span data-stu-id="77641-119">The actual implementation might differ slightly from these examples, but the performance will be the same or similar to these examples.</span></span>

## <a name="executing-xpath-expressions-with-xmldocument"></a><span data-ttu-id="77641-120">Esecuzione di espressioni XPath con XmlDocument</span><span class="sxs-lookup"><span data-stu-id="77641-120">Executing XPath Expressions with XmlDocument</span></span>

<span data-ttu-id="77641-121">Nell'esempio seguente viene usato <xref:System.Xml.XmlDocument> per ottenere gli stessi risultati degli esempi precedenti:</span><span class="sxs-lookup"><span data-stu-id="77641-121">The following example uses <xref:System.Xml.XmlDocument> to accomplish the same results as the previous examples:</span></span>

```vb
Dim reader = Xml.XmlReader.Create("PurchaseOrders.xml")
Dim doc As New Xml.XmlDocument()
doc.Load(reader)
Dim nl As Xml.XmlNodeList = doc.SelectNodes(".//Address[@Type='Shipping']")
For Each n As Xml.XmlNode In nl
    Console.WriteLine(n.OuterXml)
Next
reader.Close()
```

<span data-ttu-id="77641-122">Questa query restituisce lo stesso output degli esempi che usano LINQ to XML. L'unica differenza consiste nel fatto che in LINQ to XML viene applicato un rientro al codice XML stampato, mentre in <xref:System.Xml.XmlDocument> no.</span><span class="sxs-lookup"><span data-stu-id="77641-122">This query returns the same output as the examples that use LINQ to XML; the only difference is that LINQ to XML indents the printed XML, whereas <xref:System.Xml.XmlDocument> does not.</span></span>

<span data-ttu-id="77641-123">L'utilizzo di <xref:System.Xml.XmlDocument> non garantisce tuttavia lo stesso livello di prestazioni di LINQ to XML, in quanto il metodo <xref:System.Xml.XmlNode.SelectNodes%2A> deve eseguire internamente le operazioni seguenti ogni volta che viene chiamato:</span><span class="sxs-lookup"><span data-stu-id="77641-123">However, the <xref:System.Xml.XmlDocument> approach generally does not perform as well as LINQ to XML, because the <xref:System.Xml.XmlNode.SelectNodes%2A> method must do the following internally every time it is called:</span></span>

- <span data-ttu-id="77641-124">Analisi della stringa che contiene l'espressione XPath, suddividendo la stringa in token.</span><span class="sxs-lookup"><span data-stu-id="77641-124">It parses the string that contains the XPath expression, breaking the string into tokens.</span></span>

- <span data-ttu-id="77641-125">Convalida dei token per assicurarsi che l'espressione XPath sia valida.</span><span class="sxs-lookup"><span data-stu-id="77641-125">It validates the tokens to make sure that the XPath expression is valid.</span></span>

- <span data-ttu-id="77641-126">Conversione dell'espressione in un albero delle espressioni interno.</span><span class="sxs-lookup"><span data-stu-id="77641-126">It translates the expression into an internal expression tree.</span></span>

- <span data-ttu-id="77641-127">Iterazione nei nodi, selezionando in modo appropriato i nodi per il set di risultati in base alla valutazione dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="77641-127">It iterates through the nodes, appropriately selecting the nodes for the result set based on the evaluation of the expression.</span></span>

<span data-ttu-id="77641-128">Queste operazioni sono in numero significativamente maggiore rispetto a quelle eseguite dalla query LINQ to XML corrispondente.</span><span class="sxs-lookup"><span data-stu-id="77641-128">This is significantly more than the work done by the corresponding LINQ to XML query.</span></span> <span data-ttu-id="77641-129">La differenza di prestazioni specifica varia per tipi diversi di query, ma in generale le query LINQ to XML comportano un lavoro minore, e pertanto prestazioni migliori, rispetto alla valutazione di espressioni XPath tramite <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="77641-129">The specific performance difference varies for different types of queries, but in general LINQ to XML queries do less work, and therefore perform better, than evaluating XPath expressions using <xref:System.Xml.XmlDocument>.</span></span>

## <a name="see-also"></a><span data-ttu-id="77641-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77641-130">See also</span></span>

- [<span data-ttu-id="77641-131">Prestazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77641-131">Performance (LINQ to XML) (Visual Basic)</span></span>](performance-linq-to-xml.md)
