---
title: Valutazione di espressioni XPath con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2913ccf3-f932-4363-8028-9e2d22ce6093
ms.openlocfilehash: b6e18fe02a828ae307ac7ade15650d3303f2600c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287805"
---
# <a name="evaluate-xpath-expressions-using-xpathnavigator"></a><span data-ttu-id="8528a-102">Valutazione di espressioni XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8528a-102">Evaluate XPath Expressions using XPathNavigator</span></span>
<span data-ttu-id="8528a-103">La classe <xref:System.Xml.XPath.XPathNavigator> fornisce il metodo <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> per valutare un'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="8528a-103">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method to evaluate an XPath expression.</span></span> <span data-ttu-id="8528a-104">Il metodo <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> rileva un'espressione XPath, la valuta e restituisce un W3C XPath di tipo booleano, numero, stringa o set di nodi, in base al risultato dell'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="8528a-104">The <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method takes an XPath expression, evaluates it and returns a W3C XPath type of Boolean, Number, String, or Node Set based on the result of the XPath expression.</span></span>  
  
## <a name="the-evaluate-method"></a><span data-ttu-id="8528a-105">Metodo Evaluate</span><span class="sxs-lookup"><span data-stu-id="8528a-105">The Evaluate Method</span></span>  
 <span data-ttu-id="8528a-106">Il metodo <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> rileva un'espressione XPath, la valuta e restituisce un risultato di tipo booleano(<xref:System.Boolean>), numero (<xref:System.Double>), stringa (<xref:System.String>) o set di nodi (<xref:System.Xml.XPath.XPathNodeIterator>).</span><span class="sxs-lookup"><span data-stu-id="8528a-106">The <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method takes an XPath expression, evaluates it, and returns a typed result of Boolean (<xref:System.Boolean>), Number (<xref:System.Double>), String (<xref:System.String>), or Node Set (<xref:System.Xml.XPath.XPathNodeIterator>).</span></span> <span data-ttu-id="8528a-107">È possibile ad esempio usare il metodo <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> in un metodo matematico.</span><span class="sxs-lookup"><span data-stu-id="8528a-107">For example, the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method could be used in a mathematical method.</span></span> <span data-ttu-id="8528a-108">Nell'esempio di codice seguente viene calcolato il prezzo totale di tutti i libri nel file `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="8528a-108">The following example code calculates the total price of all the books in the `books.xml` file.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Dim query As XPathExpression = navigator.Compile("sum(//price/text())")  
Dim total As Double = CType(navigator.Evaluate(query), Double)  
Console.WriteLine(total)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
XPathExpression query = navigator.Compile("sum(//price/text())");  
Double total = (Double)navigator.Evaluate(query);  
Console.WriteLine(total);  
```  
  
 <span data-ttu-id="8528a-109">Nell'esempio il file `books.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="8528a-109">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="position-and-last-functions"></a><span data-ttu-id="8528a-110">Funzioni position e last</span><span class="sxs-lookup"><span data-stu-id="8528a-110">position and last Functions</span></span>  
 <span data-ttu-id="8528a-111">Il metodo <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> è un metodo di overload.</span><span class="sxs-lookup"><span data-stu-id="8528a-111">The <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method is overloaded.</span></span> <span data-ttu-id="8528a-112">Uno dei metodi <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> accetta come parametro un oggetto <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="8528a-112">One of the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> methods takes an <xref:System.Xml.XPath.XPathNodeIterator> object as a parameter.</span></span> <span data-ttu-id="8528a-113">Questo specifico metodo <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> è identico al metodo <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> che accetta solo un oggetto <xref:System.Xml.XPath.XPathExpression> come parametro, ad eccezione del fatto che consente a un argomento set di nodi di specificare il contesto corrente in base al quale eseguire la valutazione.</span><span class="sxs-lookup"><span data-stu-id="8528a-113">This particular <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method is identical to the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method that takes only an <xref:System.Xml.XPath.XPathExpression> object as a parameter, except that it allows a node set argument to specify the current context to perform the evaluation on.</span></span> <span data-ttu-id="8528a-114">Questo contesto è necessario per le funzioni `position()` e `last()` di XPath in quanto sono relative al nodo di contesto corrente.</span><span class="sxs-lookup"><span data-stu-id="8528a-114">This context is required for the XPath `position()` and `last()` functions as they are relative to the current context node.</span></span> <span data-ttu-id="8528a-115">A meno che non vengano usate come predicato in una fase di posizione, per la valutazione delle funzioni `position()` e `last()` è necessario specificare un riferimento a un set di nodi, altrimenti le funzioni `position` e `last` restituiscono `0`.</span><span class="sxs-lookup"><span data-stu-id="8528a-115">Unless used as a predicate in a location step, the `position()` and `last()` functions require a reference to a node set in order to be evaluated otherwise, the `position` and `last` functions return `0`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8528a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8528a-116">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="8528a-117">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="8528a-117">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="8528a-118">Selezione di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8528a-118">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="8528a-119">Corrispondenza di nodi utilizzando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8528a-119">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="8528a-120">Tipi di nodo riconosciuti con le query XPath</span><span class="sxs-lookup"><span data-stu-id="8528a-120">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="8528a-121">Query e spazi dei nomi XPath</span><span class="sxs-lookup"><span data-stu-id="8528a-121">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)
- [<span data-ttu-id="8528a-122">Espressioni XPath compilate</span><span class="sxs-lookup"><span data-stu-id="8528a-122">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)
