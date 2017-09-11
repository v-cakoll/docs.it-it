---
title: Esecuzione di query su XDocument e su Query di XElement (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 93f0f7f50ad305540a6afef2374d4b948de48705
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a><span data-ttu-id="f83f9-102">Esecuzione di query su XDocument e su Query di XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f83f9-102">Querying an XDocument vs. Querying an XElement (Visual Basic)</span></span>
<span data-ttu-id="f83f9-103">Quando si carica un documento tramite <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, si noterà che è necessario scrivere query in modo leggermente diverso rispetto a quando si carica tramite <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f83f9-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="f83f9-104">Confronto tra XDocument.Load e XElement.Load</span><span class="sxs-lookup"><span data-stu-id="f83f9-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="f83f9-105">Quando si carica un documento XML in un <xref:System.Xml.Linq.XElement>tramite <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement>nella radice del XML albero contiene l'elemento radice del documento caricato.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f83f9-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="f83f9-106">Tuttavia, quando si carica lo stesso documento XML in un <xref:System.Xml.Linq.XDocument>tramite <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, la radice dell'albero è un <xref:System.Xml.Linq.XDocument>nodo, mentre l'elemento radice del documento caricato è il figlio consentito un <xref:System.Xml.Linq.XElement>nodo <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="f83f9-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="f83f9-107">Gli assi di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] eseguono operazioni in relazione al nodo radice.</span><span class="sxs-lookup"><span data-stu-id="f83f9-107">The [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="f83f9-108">Questo primo esempio viene caricato un albero XML usando <xref:System.Xml.Linq.XElement.Load%2A>.</xref:System.Xml.Linq.XElement.Load%2A></span><span class="sxs-lookup"><span data-stu-id="f83f9-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="f83f9-109">Viene quindi eseguita una query per gli elementi figlio della radice dell'albero.</span><span class="sxs-lookup"><span data-stu-id="f83f9-109">It then queries for the child elements of the root of the tree.</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XElement.Load")  
Console.WriteLine("----")  
Dim doc As XElement = XElement.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="f83f9-110">Come previsto, nell'esempio viene prodotto il seguente output:</span><span class="sxs-lookup"><span data-stu-id="f83f9-110">As expected, this example produces the following output:</span></span>  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="f83f9-111">L'esempio seguente è lo stesso di quello precedente, con l'eccezione che la struttura ad albero XML viene caricato un <xref:System.Xml.Linq.XDocument>anziché un <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="f83f9-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="f83f9-112">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="f83f9-112">This example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="f83f9-113">Notare che la stessa query ha restituito l'unico nodo `Root` anziché i tre nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="f83f9-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="f83f9-114">Per gestire questa situazione consiste nell'utilizzare il <xref:System.Xml.Linq.XDocument.Root%2A>proprietà prima di accedere ai metodi degli assi, come indicato di seguito:</xref:System.Xml.Linq.XDocument.Root%2A></span><span class="sxs-lookup"><span data-stu-id="f83f9-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Root.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="f83f9-115">Questa query viene ora eseguita nello stesso modo della query sull'albero con radice in <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="f83f9-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="f83f9-116">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="f83f9-116">The example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f83f9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f83f9-117">See Also</span></span>  
 [<span data-ttu-id="f83f9-118">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f83f9-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
