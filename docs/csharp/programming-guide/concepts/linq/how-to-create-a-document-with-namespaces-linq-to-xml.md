---
title: Come creare un documento con spazi dei nomi (C#) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 429b0b0b41f2201b983f931e469b25ff406b91ac
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141330"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a><span data-ttu-id="c33ae-102">Come creare un documento con spazi dei nomi (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="c33ae-102">How to create a document with namespaces (C#) (LINQ to XML)</span></span>
<span data-ttu-id="c33ae-103">In questo argomento viene illustrato come creare documenti con spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c33ae-103">This topic shows how to create documents with namespaces.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c33ae-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="c33ae-104">Example</span></span>  
 <span data-ttu-id="c33ae-105">Per creare un elemento o un attributo in uno spazio dei nomi, è prima necessario dichiarare e inizializzare un oggetto <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="c33ae-105">To create an element or an attribute that is in a namespace, you first declare and initialize an <xref:System.Xml.Linq.XNamespace> object.</span></span> <span data-ttu-id="c33ae-106">È quindi possibile usare l'overload dell'operatore di addizione per combinare lo spazio dei nomi con il nome locale, espresso come stringa.</span><span class="sxs-lookup"><span data-stu-id="c33ae-106">You then use the addition operator overload to combine the namespace with the local name, expressed as a string.</span></span>  
  
 <span data-ttu-id="c33ae-107">Nell'esempio seguente viene creato un documento con un solo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c33ae-107">The following example creates a document with one namespace.</span></span> <span data-ttu-id="c33ae-108">Per impostazione predefinita, in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] questo documento viene serializzato con uno spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="c33ae-108">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] serializes this document with a default namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="c33ae-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c33ae-109">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="c33ae-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="c33ae-110">Example</span></span>  
 <span data-ttu-id="c33ae-111">Nell'esempio seguente viene creato un documento con un solo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c33ae-111">The following example creates a document with one namespace.</span></span> <span data-ttu-id="c33ae-112">nonché un attributo che dichiara lo spazio dei nomi con un prefisso.</span><span class="sxs-lookup"><span data-stu-id="c33ae-112">It also creates an attribute that declares the namespace with a namespace prefix.</span></span> <span data-ttu-id="c33ae-113">Per creare un attributo che dichiara uno spazio dei nomi con un prefisso, è possibile creare un attributo il cui nome è il prefisso dello spazio dei nomi e tale nome si trova nello spazio dei nomi <xref:System.Xml.Linq.XNamespace.Xmlns%2A>.</span><span class="sxs-lookup"><span data-stu-id="c33ae-113">To create an attribute that declares a namespace with a prefix, you create an attribute where the name of the attribute is the namespace prefix, and this name is in the <xref:System.Xml.Linq.XNamespace.Xmlns%2A> namespace.</span></span> <span data-ttu-id="c33ae-114">Il valore di questo attributo è l'URI dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c33ae-114">The value of this attribute is the URI of the namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="c33ae-115">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c33ae-115">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="c33ae-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="c33ae-116">Example</span></span>  
 <span data-ttu-id="c33ae-117">Nell'esempio seguente è illustrata la creazione di un documento che contiene due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c33ae-117">The following example shows the creation of a document that contains two namespaces.</span></span> <span data-ttu-id="c33ae-118">Uno è lo spazio dei nomi predefinito,</span><span class="sxs-lookup"><span data-stu-id="c33ae-118">One is the default namespace.</span></span> <span data-ttu-id="c33ae-119">mentre l'altro è uno spazio dei nomi con prefisso.</span><span class="sxs-lookup"><span data-stu-id="c33ae-119">Another is a namespace with a prefix.</span></span>  
  
 <span data-ttu-id="c33ae-120">Se si includono gli attributi dello spazio dei nomi nell'elemento radice, gli spazi dei nomi vengono serializzati in modo tale che `http://www.adventure-works.com` corrisponda allo spazio dei nomi predefinito e `www.fourthcoffee.com` venga serializzato con il prefisso "fc".</span><span class="sxs-lookup"><span data-stu-id="c33ae-120">By including namespace attributes in the root element, the namespaces are serialized so that `http://www.adventure-works.com` is the default namespace, and `www.fourthcoffee.com` is serialized with a prefix of "fc".</span></span> <span data-ttu-id="c33ae-121">Per creare un attributo che dichiara uno spazio dei nomi predefinito, viene creato un attributo denominato "xmlns" e senza spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c33ae-121">To create an attribute that declares a default namespace, you create an attribute with the name "xmlns", without a namespace.</span></span> <span data-ttu-id="c33ae-122">Il valore dell'attributo è l'URI dello spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="c33ae-122">The value of the attribute is the default namespace URI.</span></span>  
  
```csharp  
// The http://www.adventure-works.com namespace is forced to be the default namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute("xmlns", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="c33ae-123">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c33ae-123">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="c33ae-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="c33ae-124">Example</span></span>  
 <span data-ttu-id="c33ae-125">Nell'esempio seguente viene creato un documento contenente due spazi dei nomi, entrambi con prefisso.</span><span class="sxs-lookup"><span data-stu-id="c33ae-125">The following example creates a document that contains two namespaces, both with namespace prefixes.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),  
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="c33ae-126">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c33ae-126">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="c33ae-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="c33ae-127">Example</span></span>  
 <span data-ttu-id="c33ae-128">È possibile ottenere lo stesso risultato anche usando nomi espansi anziché dichiarando e creando un oggetto <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="c33ae-128">Another way to accomplish the same result is to use expanded names instead of declaring and creating an <xref:System.Xml.Linq.XNamespace> object.</span></span>  
  
 <span data-ttu-id="c33ae-129">Questo approccio può tuttavia incidere sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c33ae-129">This approach has performance implications.</span></span> <span data-ttu-id="c33ae-130">Ogni volta che si passa una stringa che contiene un nome espanso a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] deve analizzare il nome, individuare lo spazio dei nomi atomicizzato e individuare il nome atomicizzato.</span><span class="sxs-lookup"><span data-stu-id="c33ae-130">Each time you pass a string that contains an expanded name to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] must parse the name, find the atomized namespace, and find the atomized name.</span></span> <span data-ttu-id="c33ae-131">Questo processo impiega il tempo della CPU.</span><span class="sxs-lookup"><span data-stu-id="c33ae-131">This process takes CPU time.</span></span> <span data-ttu-id="c33ae-132">Se le prestazioni sono importanti, è consigliabile dichiarare e usare un oggetto <xref:System.Xml.Linq.XNamespace> in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="c33ae-132">If performance is important, you might want to declare and use an <xref:System.Xml.Linq.XNamespace> object explicitly.</span></span>  
  
 <span data-ttu-id="c33ae-133">Se le prestazioni rappresentano un problema rilevante, per altre informazioni vedere [Pre-atomizzazione di oggetti XName (LINQ to XML) (C#)](./pre-atomization-of-xname-objects-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c33ae-133">If performance is an important issue, see [Pre-Atomization of XName Objects (LINQ to XML) (C#)](./pre-atomization-of-xname-objects-linq-to-xml.md) for more information</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="c33ae-134">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="c33ae-134">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c33ae-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c33ae-135">See also</span></span>

- [<span data-ttu-id="c33ae-136">Panoramica degli spazi dei nomi (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="c33ae-136">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
