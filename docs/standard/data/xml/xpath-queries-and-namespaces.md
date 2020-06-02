---
title: Query e spazi dei nomi XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ef6402be-2f8e-4be2-8d3e-a80891cdef8b
ms.openlocfilehash: d3314a7ff4cf957dac4cd8ad0416aad434b19af2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283195"
---
# <a name="xpath-queries-and-namespaces"></a><span data-ttu-id="c2da5-102">Query e spazi dei nomi XPath</span><span class="sxs-lookup"><span data-stu-id="c2da5-102">XPath Queries and Namespaces</span></span>
<span data-ttu-id="c2da5-103">Le query XPath tengono in considerazione gli spazi dei nomi in un documento XML e possono usare i prefissi degli spazi dei nomi per qualificare i nomi di elemento e di attributo.</span><span class="sxs-lookup"><span data-stu-id="c2da5-103">XPath queries are aware of namespaces in an XML document and can use namespace prefixes to qualify element and attribute names.</span></span> <span data-ttu-id="c2da5-104">La qualifica dei nomi di elemento e di attributo con un prefisso dello spazio dei nomi limita i nodi restituiti da una query XPath ai soli nodi che appartengono a uno spazio dei nomi specifico.</span><span class="sxs-lookup"><span data-stu-id="c2da5-104">Qualifying element and attribute names with a namespace prefix limits the nodes returned by an XPath query to only those nodes that belong to a specific namespace.</span></span>  
  
 <span data-ttu-id="c2da5-105">Se ad esempio il mapping del prefisso `books` è lo spazio dei nomi `http://www.contoso.com/books`, la query XPath `/books:books/books:book` seguente selezionerà solo quegli elementi `book` nello spazio dei nomi `http://www.contoso.com/books`.</span><span class="sxs-lookup"><span data-stu-id="c2da5-105">For example if the prefix `books` maps to the namespace `http://www.contoso.com/books`, then the following XPath query `/books:books/books:book` selects only those `book` elements in the namespace `http://www.contoso.com/books`.</span></span>  
  
## <a name="the-xmlnamespacemanager"></a><span data-ttu-id="c2da5-106">XmlNamespaceManager</span><span class="sxs-lookup"><span data-stu-id="c2da5-106">The XmlNamespaceManager</span></span>  
 <span data-ttu-id="c2da5-107">Per usare gli spazi dei nomi in una query XPath, un oggetto derivato dall'interfaccia <xref:System.Xml.IXmlNamespaceResolver> come la classe <xref:System.Xml.XmlNamespaceManager> viene costruito con l'URI e il prefisso dello spazio dei nomi da includere nella query XPath.</span><span class="sxs-lookup"><span data-stu-id="c2da5-107">To use namespaces in an XPath query, an object derived from the <xref:System.Xml.IXmlNamespaceResolver> interface like the <xref:System.Xml.XmlNamespaceManager> class is constructed with the namespace URI and prefix to include in the XPath query.</span></span>  
  
 <span data-ttu-id="c2da5-108">L'oggetto <xref:System.Xml.XmlNamespaceManager> può essere usato nella query in ciascuno dei seguenti modi.</span><span class="sxs-lookup"><span data-stu-id="c2da5-108">The <xref:System.Xml.XmlNamespaceManager> object may be used in the query in each of the following ways.</span></span>  
  
- <span data-ttu-id="c2da5-109">L'oggetto <xref:System.Xml.XmlNamespaceManager> viene associato a un oggetto <xref:System.Xml.XPath.XPathExpression> esistente mediante il metodo <xref:System.Xml.XPath.XPathExpression.SetContext%2A> dell'oggetto <xref:System.Xml.XPath.XPathExpression>.</span><span class="sxs-lookup"><span data-stu-id="c2da5-109">The <xref:System.Xml.XmlNamespaceManager> object is associated with an existing <xref:System.Xml.XPath.XPathExpression> object by using the <xref:System.Xml.XPath.XPathExpression.SetContext%2A> method of the <xref:System.Xml.XPath.XPathExpression> object.</span></span> <span data-ttu-id="c2da5-110">È anche possibile compilare un nuovo oggetto <xref:System.Xml.XPath.XPathExpression> usando il metodo statico <xref:System.Xml.XPath.XPathExpression.Compile%2A>, che accetta una stringa che rappresenta l'espressione XPath e un oggetto <xref:System.Xml.XmlNamespaceManager> come parametri e restituisce un nuovo oggetto <xref:System.Xml.XPath.XPathExpression>.</span><span class="sxs-lookup"><span data-stu-id="c2da5-110">You may also compile a new <xref:System.Xml.XPath.XPathExpression> object using the static <xref:System.Xml.XPath.XPathExpression.Compile%2A> method which takes a string representing the XPath expression and an <xref:System.Xml.XmlNamespaceManager> object as parameters and returns a new <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
- <span data-ttu-id="c2da5-111">Lo stesso oggetto <xref:System.Xml.XmlNamespaceManager> viene passato come parametro a un metodo della classe <xref:System.Xml.XPath.XPathNavigator> che lo accetti assieme a una stringa che rappresenta l'espressione XPath.</span><span class="sxs-lookup"><span data-stu-id="c2da5-111">The <xref:System.Xml.XmlNamespaceManager> object itself is passed as a parameter to an accepting <xref:System.Xml.XPath.XPathNavigator> class method along with a string representing the XPath expression.</span></span>  
  
 <span data-ttu-id="c2da5-112">Di seguito sono indicati i metodi della classe <xref:System.Xml.XPath.XPathNavigator> che accettano come parametro un oggetto derivato dall'interfaccia <xref:System.Xml.IXmlNamespaceResolver>.</span><span class="sxs-lookup"><span data-stu-id="c2da5-112">The following are the methods of the <xref:System.Xml.XPath.XPathNavigator> class that accept an object derived from the <xref:System.Xml.IXmlNamespaceResolver> interface as a parameter.</span></span>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
### <a name="the-default-namespace"></a><span data-ttu-id="c2da5-113">Spazio dei nomi predefinito</span><span class="sxs-lookup"><span data-stu-id="c2da5-113">The Default Namespace</span></span>  
 <span data-ttu-id="c2da5-114">Nel seguente documento XML lo spazio dei nomi predefinito con un prefisso vuoto viene usato per dichiarare lo spazio dei nomi `http://www.contoso.com/books`.</span><span class="sxs-lookup"><span data-stu-id="c2da5-114">In the XML document that follows, the default namespace with an empty prefix is used to declare the `http://www.contoso.com/books` namespace.</span></span>  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <author>Author Name</author>  
        <price>5.50</price>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="c2da5-115">XPath considera il prefisso vuoto come lo spazio dei nomi `null`.</span><span class="sxs-lookup"><span data-stu-id="c2da5-115">XPath treats the empty prefix as the `null` namespace.</span></span> <span data-ttu-id="c2da5-116">In altre parole, nelle query XPath possono essere usati solo i prefissi il cui mapping corrisponde a uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c2da5-116">In other words, only prefixes mapped to namespaces can be used in XPath queries.</span></span> <span data-ttu-id="c2da5-117">Ciò significa che, se si desidera eseguire una query relativa a uno spazio dei nomi in un documento XML, anche se si tratta dello spazio dei nomi predefinito, è necessario definire un prefisso per tale spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c2da5-117">This means that if you want to query against a namespace in an XML document, even if it is the default namespace, you need to define a prefix for it.</span></span>  
  
 <span data-ttu-id="c2da5-118">Ad esempio, se non si definisce un prefisso per il documento XML indicato sopra, la query XPath `/books/book` non restituirà alcun risultato.</span><span class="sxs-lookup"><span data-stu-id="c2da5-118">For example, without defining a prefix for the XML document above, the XPath query `/books/book` would not return any results.</span></span>  
  
 <span data-ttu-id="c2da5-119">È necessario che sia associato un prefisso, per impedire ambiguità durante le operazioni di query su documenti con alcuni nodi che non rientrano in uno spazio dei nomi e alcuni nodi che rientrano in uno spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="c2da5-119">A prefix must be bound to prevent ambiguity when querying documents with some nodes not in a namespace, and some in a default namespace.</span></span>  
  
 <span data-ttu-id="c2da5-120">Il codice seguente definisce un prefisso per lo spazio dei nomi predefinito e seleziona tutti gli elementi `book` dallo spazio dei nomi `http://www.contoso.com/books`.</span><span class="sxs-lookup"><span data-stu-id="c2da5-120">The following code defines a prefix for the default namespace and selects all the `book` elements from the `http://www.contoso.com/books` namespace.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim query As XPathExpression = navigator.Compile("/books:books/books:book")  
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(navigator.NameTable)  
manager.AddNamespace("books", "http://www.contoso.com/books")  
query.SetContext(manager)  
Dim nodes As XPathNodeIterator = navigator.Select(query)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathExpression query = navigator.Compile("/books:books/books:book");  
XmlNamespaceManager manager = new XmlNamespaceManager(navigator.NameTable);  
manager.AddNamespace("books", "http://www.contoso.com/books");  
query.SetContext(manager);  
XPathNodeIterator nodes = navigator.Select(query);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2da5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2da5-121">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="c2da5-122">Elaborazione di dati XML con il modello di dati XPath</span><span class="sxs-lookup"><span data-stu-id="c2da5-122">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="c2da5-123">Selezione di dati XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c2da5-123">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="c2da5-124">Valutazione di espressioni XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c2da5-124">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="c2da5-125">Corrispondenza di nodi utilizzando XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="c2da5-125">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)
- [<span data-ttu-id="c2da5-126">Tipi di nodo riconosciuti con le query XPath</span><span class="sxs-lookup"><span data-stu-id="c2da5-126">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="c2da5-127">Espressioni XPath compilate</span><span class="sxs-lookup"><span data-stu-id="c2da5-127">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)
