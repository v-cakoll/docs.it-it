---
title: Esecuzione di query su XDocument e su XElement (C#)
ms.date: 07/20/2015
ms.assetid: 46221ff5-62ee-4de8-93ba-66465facb5c1
ms.openlocfilehash: 991cbf14fde1c2e3e1e76ef10066db3408ca51c5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/09/2018
ms.locfileid: "44200828"
---
# <a name="querying-an-xdocument-vs-querying-an-xelement-c"></a><span data-ttu-id="ae32e-102">Esecuzione di query su XDocument e su XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="ae32e-102">Querying an XDocument vs. Querying an XElement (C#)</span></span>
<span data-ttu-id="ae32e-103">Quando si carica un documento tramite <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, si noterà che è necessario scrivere le query in modo leggermente diverso rispetto a quando si carica un documento tramite <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ae32e-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="ae32e-104">Confronto tra XDocument.Load e XElement.Load</span><span class="sxs-lookup"><span data-stu-id="ae32e-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="ae32e-105">Quando si carica un documento XML in un oggetto <xref:System.Xml.Linq.XElement> tramite <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, l'oggetto <xref:System.Xml.Linq.XElement> nella radice dell'albero XML contiene l'elemento radice del documento caricato.</span><span class="sxs-lookup"><span data-stu-id="ae32e-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="ae32e-106">Tuttavia, quando si carica lo stesso documento XML in un oggetto <xref:System.Xml.Linq.XDocument> tramite <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, la radice dell'albero è un nodo <xref:System.Xml.Linq.XDocument>, mentre l'elemento radice del documento caricato è l'unico nodo <xref:System.Xml.Linq.XElement> figlio consentito di <xref:System.Xml.Linq.XDocument>.</span><span class="sxs-lookup"><span data-stu-id="ae32e-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="ae32e-107">Gli assi di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eseguono operazioni in relazione al nodo radice.</span><span class="sxs-lookup"><span data-stu-id="ae32e-107">The [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="ae32e-108">Nel primo esempio viene caricato un albero XML usando <xref:System.Xml.Linq.XElement.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae32e-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="ae32e-109">Viene quindi eseguita una query per gli elementi figlio della radice dell'albero.</span><span class="sxs-lookup"><span data-stu-id="ae32e-109">It then queries for the child elements of the root of the tree.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XElement.Load");  
Console.WriteLine("----");  
XElement doc = XElement.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="ae32e-110">Come previsto, nell'esempio viene prodotto il seguente output:</span><span class="sxs-lookup"><span data-stu-id="ae32e-110">As expected, this example produces the following output:</span></span>  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="ae32e-111">L'esempio seguente è identico a quello precedente, con l'eccezione che l'albero XML viene caricato in un oggetto <xref:System.Xml.Linq.XDocument> anziché in <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ae32e-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="ae32e-112">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="ae32e-112">This example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="ae32e-113">Notare che la stessa query ha restituito l'unico nodo `Root` anziché i tre nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="ae32e-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="ae32e-114">Per gestire questa situazione, è possibile usare la proprietà <xref:System.Xml.Linq.XDocument.Root%2A> prima di accedere ai metodi degli assi, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ae32e-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```csharp  
// Create a simple document and write it to a file  
File.WriteAllText("Test.xml", @"<Root>  
    <Child1>1</Child1>  
    <Child2>2</Child2>  
    <Child3>3</Child3>  
</Root>");  
  
Console.WriteLine("Querying tree loaded with XDocument.Load");  
Console.WriteLine("----");  
XDocument doc = XDocument.Load("Test.xml");  
IEnumerable<XElement> childList =  
    from el in doc.Root.Elements()  
    select el;  
foreach (XElement e in childList)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="ae32e-115">Questa query viene ora eseguita in modo identico alla query sull'albero inserito nella radice di <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="ae32e-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="ae32e-116">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="ae32e-116">The example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae32e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae32e-117">See Also</span></span>

- [<span data-ttu-id="ae32e-118">Query di base (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ae32e-118">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
