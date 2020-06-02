---
title: Espressioni XPath compilate
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e25dd95f-b64c-4d8b-a3a4-379e1aa0ad55
ms.openlocfilehash: e74b52e471699fc663504fa42d6c7e502859adda
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291526"
---
# <a name="compiled-xpath-expressions"></a><span data-ttu-id="45595-102">Espressioni XPath compilate</span><span class="sxs-lookup"><span data-stu-id="45595-102">Compiled XPath Expressions</span></span>
<span data-ttu-id="45595-103">Un oggetto <xref:System.Xml.XPath.XPathExpression> rappresenta una query XPath compilata che viene restituita dal metodo statico <xref:System.Xml.XPath.XPathExpression.Compile%2A> della classe <xref:System.Xml.XPath.XPathExpression> oppure dal metodo <xref:System.Xml.XPath.XPathNavigator.Compile%2A> della classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="45595-103">An <xref:System.Xml.XPath.XPathExpression> object represents a compiled XPath query returned from either the static <xref:System.Xml.XPath.XPathExpression.Compile%2A> method of the <xref:System.Xml.XPath.XPathExpression> class or the <xref:System.Xml.XPath.XPathNavigator.Compile%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="the-xpathexpression-class"></a><span data-ttu-id="45595-104">Classe XPathExpression</span><span class="sxs-lookup"><span data-stu-id="45595-104">The XPathExpression Class</span></span>  
 <span data-ttu-id="45595-105">Una query XPath compilata rappresentata da un oggetto <xref:System.Xml.XPath.XPathExpression> risulta utile se la stessa query XPath viene usata più volte.</span><span class="sxs-lookup"><span data-stu-id="45595-105">A compiled XPath query represented by an <xref:System.Xml.XPath.XPathExpression> object is useful if the same XPath query is being used more than once.</span></span>  
  
 <span data-ttu-id="45595-106">Ad esempio, se si chiama il metodo <xref:System.Xml.XPath.XPathNavigator.Select%2A> più volte, anziché usare ogni volta una stringa che rappresenti la query XPath, è possibile usare il metodo <xref:System.Xml.XPath.XPathExpression.Compile%2A> della classe <xref:System.Xml.XPath.XPathExpression> oppure il metodo <xref:System.Xml.XPath.XPathNavigator.Compile%2A> della classe <xref:System.Xml.XPath.XPathNavigator> per compilare e memorizzare nella cache la query XPath in un oggetto <xref:System.Xml.XPath.XPathExpression> e poterla riutilizzare migliorando le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="45595-106">For example, when calling the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method multiple times, instead of using a string representing the XPath query each time, use the <xref:System.Xml.XPath.XPathExpression.Compile%2A> method of the <xref:System.Xml.XPath.XPathExpression> class or the <xref:System.Xml.XPath.XPathNavigator.Compile%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class to compile and cache the XPath query in an <xref:System.Xml.XPath.XPathExpression> object for reuse and improved performance.</span></span>  
  
 <span data-ttu-id="45595-107">Una volta compilato, l'oggetto <xref:System.Xml.XPath.XPathExpression> può essere usato come input ai seguenti metodi della classe <xref:System.Xml.XPath.XPathNavigator> in base al tipo restituito dalla query XPath.</span><span class="sxs-lookup"><span data-stu-id="45595-107">Once compiled, the <xref:System.Xml.XPath.XPathExpression> object may be used as input to the following <xref:System.Xml.XPath.XPathNavigator> class methods depending on the type returned from the XPath query.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Matches%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 <span data-ttu-id="45595-108">Nella tabella seguente vengono descritti ciascun tipo W3C XPath restituito, il tipo equivalente di Microsoft .NET Frameworks e i metodi che possono essere usati dall'oggetto <xref:System.Xml.XPath.XPathExpression> in base al relativo tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="45595-108">The following table describes each of the W3C XPath return types, their Microsoft .NET Framework equivalencies, and what methods the <xref:System.Xml.XPath.XPathExpression> object may be used with based on its return type.</span></span>  
  
|<span data-ttu-id="45595-109">Tipo W3C XPath restituito</span><span class="sxs-lookup"><span data-stu-id="45595-109">W3C XPath Return Type</span></span>|<span data-ttu-id="45595-110">Tipo equivalente di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="45595-110">.NET Framework Equivalent Type</span></span>|<span data-ttu-id="45595-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45595-111">Description</span></span>|<span data-ttu-id="45595-112">Metodi</span><span class="sxs-lookup"><span data-stu-id="45595-112">Methods</span></span>|  
|---------------------------|------------------------------------|-----------------|-------------|  
|`Node set`|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="45595-113">Raccolta non ordinata di nodi senza duplicati creati in ordine di documento.</span><span class="sxs-lookup"><span data-stu-id="45595-113">An unordered collection of nodes without duplicates created in document order.</span></span>|<span data-ttu-id="45595-114"><xref:System.Xml.XPath.XPathNavigator.Select%2A> o <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A></span><span class="sxs-lookup"><span data-stu-id="45595-114"><xref:System.Xml.XPath.XPathNavigator.Select%2A> or <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A></span></span>|  
|`Boolean`|<xref:System.Boolean>|<span data-ttu-id="45595-115">Valore `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="45595-115">A `true` or `false` value.</span></span>|<span data-ttu-id="45595-116"><xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> oppure</span><span class="sxs-lookup"><span data-stu-id="45595-116"><xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> or</span></span><br /><br /> <xref:System.Xml.XPath.XPathNavigator.Matches%2A>|  
|`Number`|<xref:System.Double>|<span data-ttu-id="45595-117">Numero a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="45595-117">A floating-point number.</span></span>|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
|`String`|<xref:System.String>|<span data-ttu-id="45595-118">Sequenza di caratteri UCS.</span><span class="sxs-lookup"><span data-stu-id="45595-118">A sequence of UCS characters.</span></span>|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
  
> [!NOTE]
> <span data-ttu-id="45595-119">Il metodo <xref:System.Xml.XPath.XPathNavigator.Matches%2A> accetta come parametro un'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="45595-119">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method accepts an XPath expression as its parameter.</span></span> <span data-ttu-id="45595-120">Il metodo <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> restituisce un oggetto <xref:System.Xml.XPath.XPathNavigator> e non uno dei tipi W3C XPath restituiti.</span><span class="sxs-lookup"><span data-stu-id="45595-120">The <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> method returns an <xref:System.Xml.XPath.XPathNavigator> object, not one of the W3C XPath return types.</span></span>  
  
### <a name="the-returntype-property"></a><span data-ttu-id="45595-121">Proprietà ReturnType</span><span class="sxs-lookup"><span data-stu-id="45595-121">The ReturnType Property</span></span>  
 <span data-ttu-id="45595-122">Una volta compilata una query XPath in un oggetto <xref:System.Xml.XPath.XPathExpression>, è possibile usare la proprietà <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> dell'oggetto <xref:System.Xml.XPath.XPathExpression> per determinare ciò che restituisce la query XPath.</span><span class="sxs-lookup"><span data-stu-id="45595-122">After an XPath query has been compiled into an <xref:System.Xml.XPath.XPathExpression> object, you can use the <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property of the <xref:System.Xml.XPath.XPathExpression> object to determine what the XPath query returns.</span></span>  
  
 <span data-ttu-id="45595-123">La proprietà <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> restituisce uno dei seguenti valori di enumerazione <xref:System.Xml.XPath.XPathResultType> che rappresenta il tipo W3C XPath restituito.</span><span class="sxs-lookup"><span data-stu-id="45595-123">The <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property returns one of the following <xref:System.Xml.XPath.XPathResultType> enumeration values representing the W3C XPath return types.</span></span>  
  
- <xref:System.Xml.XPath.XPathResultType.Any>  
  
- <xref:System.Xml.XPath.XPathResultType.Boolean>  
  
- <xref:System.Xml.XPath.XPathResultType.Error>  
  
- <xref:System.Xml.XPath.XPathResultType.Navigator>  
  
- <xref:System.Xml.XPath.XPathResultType.NodeSet>  
  
- <xref:System.Xml.XPath.XPathResultType.Number>  
  
- <xref:System.Xml.XPath.XPathResultType.String>  
  
 <span data-ttu-id="45595-124">Nell'esempio seguente viene usato l'oggetto <xref:System.Xml.XPath.XPathExpression> per restituire un numero e un set di nodi dal file `books.xml`.</span><span class="sxs-lookup"><span data-stu-id="45595-124">The following example uses the <xref:System.Xml.XPath.XPathExpression> object to return a number and a node set from the `books.xml` file.</span></span> <span data-ttu-id="45595-125">La proprietà <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> di ciascun oggetto <xref:System.Xml.XPath.XPathExpression> e i risultati dai metodi <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> e <xref:System.Xml.XPath.XPathNavigator.Select%2A> vengono scritti nella console.</span><span class="sxs-lookup"><span data-stu-id="45595-125">The <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> property of each <xref:System.Xml.XPath.XPathExpression> object as well as the results from the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> and <xref:System.Xml.XPath.XPathNavigator.Select%2A> methods are written to the console.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Returns a number.  
Dim query1 As XPathExpression = navigator.Compile("bookstore/book/price/text()*10")  
Console.WriteLine(query1.ReturnType)  
  
Dim number As Double = CType(navigator.Evaluate(query1), Double)  
Console.WriteLine(number)  
  
' Returns a node set.  
Dim query2 As XPathExpression = navigator.Compile("bookstore/book/price")  
Console.WriteLine(query2.ReturnType)  
  
Dim nodes As XPathNodeIterator = navigator.Select(query2)  
nodes.MoveNext()  
Console.WriteLine(nodes.Current.Value)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Returns a number.  
XPathExpression query1 = navigator.Compile("bookstore/book/price/text()*10");  
Console.WriteLine(query1.ReturnType);  
  
Double number = (Double)navigator.Evaluate(query1);  
Console.WriteLine(number);  
  
// Returns a node set.  
XPathExpression query2 = navigator.Compile("bookstore/book/price");  
Console.WriteLine(query2.ReturnType);  
  
XPathNodeIterator nodes = navigator.Select(query2);  
nodes.MoveNext();  
Console.WriteLine(nodes.Current.Value);  
```  
  
 <span data-ttu-id="45595-126">Nell'esempio il file `books.xml` viene considerato come input.</span><span class="sxs-lookup"><span data-stu-id="45595-126">The example takes the `books.xml` file as input.</span></span>  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="higher-performance-xpath-expressions"></a><span data-ttu-id="45595-127">Espressioni XPath a prestazioni più elevate</span><span class="sxs-lookup"><span data-stu-id="45595-127">Higher Performance XPath Expressions</span></span>  
 <span data-ttu-id="45595-128">Per ottimizzare le prestazioni, si consiglia di usare l'espressione XPath più specifica possibile nelle query.</span><span class="sxs-lookup"><span data-stu-id="45595-128">For better performance, use the most specific XPath expression possible in your queries.</span></span> <span data-ttu-id="45595-129">Ad esempio, se il nodo `book` è un nodo figlio del nodo `bookstore` e il nodo `bookstore` è l'elemento principale di un documento XML, l'uso dell'espressione XPath `/bookstore/book` garantisce una velocità maggiore rispetto all'utilizzo di `//book`.</span><span class="sxs-lookup"><span data-stu-id="45595-129">For example, if the `book` node is a child node of the `bookstore` node and the `bookstore` node is the top-most element in an XML document, using the XPath expression `/bookstore/book` is faster than using `//book`.</span></span> <span data-ttu-id="45595-130">Per identificare i nodi corrispondenti, infatti, l'espressione XPath `//book` eseguirà l'analisi di ciascun nodo nell'albero XML.</span><span class="sxs-lookup"><span data-stu-id="45595-130">The `//book` XPath expression will scan every node in the XML tree to identify matching nodes.</span></span>  
  
 <span data-ttu-id="45595-131">Inoltre, nei casi in cui i criteri di selezione sono semplici, l'uso dei metodi di navigazione dei set di nodi forniti dalla classe <xref:System.Xml.XPath.XPathNavigator> può garantire un livello di prestazioni più elevato rispetto a quello fornito dai metodi della classe <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="45595-131">Additionally, using the node set navigation methods supplied by the <xref:System.Xml.XPath.XPathNavigator> class may result in improved performance over the selection methods supplied by the <xref:System.Xml.XPath.XPathNavigator> class in cases where your selection criteria are simple.</span></span> <span data-ttu-id="45595-132">Ad esempio, se è necessario selezionare il primo nodo figlio del nodo corrente, risulta più veloce usare il metodo <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A> anziché l'espressione XPath `child::*[1]` e il metodo <xref:System.Xml.XPath.XPathNavigator.Select%2A>.</span><span class="sxs-lookup"><span data-stu-id="45595-132">For example, if you need to select the first child of the current node, it is faster to use the <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A> method than to use the `child::*[1]` XPath expression and the <xref:System.Xml.XPath.XPathNavigator.Select%2A> method.</span></span>  
  
 <span data-ttu-id="45595-133">Per altre informazioni sui metodi di navigazione del set di nodi della classe <xref:System.Xml.XPath.XPathNavigator>, vedere [Navigazione del set di nodi con XPathNavigator](node-set-navigation-using-xpathnavigator.md).</span><span class="sxs-lookup"><span data-stu-id="45595-133">For more information about the node set navigation methods of the <xref:System.Xml.XPath.XPathNavigator> class, see [Node Set Navigation Using XPathNavigator](node-set-navigation-using-xpathnavigator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45595-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45595-134">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="45595-135">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="45595-135">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="45595-136">Selezione di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="45595-136">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="45595-137">Valutazione di espressioni XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="45595-137">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="45595-138">Corrispondenza di nodi utilizzando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="45595-138">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="45595-139">Tipi di nodo riconosciuti con le query XPath</span><span class="sxs-lookup"><span data-stu-id="45595-139">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="45595-140">Query e spazi dei nomi XPath</span><span class="sxs-lookup"><span data-stu-id="45595-140">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)
