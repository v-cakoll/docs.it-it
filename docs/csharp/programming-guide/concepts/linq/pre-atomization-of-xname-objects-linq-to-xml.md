---
title: Pre-atomizzazione di oggetti XName (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: e84fbbe7-f072-4771-bfbb-059d18e1ad15
ms.openlocfilehash: 2fd754a352bd2988e52ec9c67a9915a8e587b107
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591490"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-c"></a><span data-ttu-id="49cff-102">Pre-atomizzazione di oggetti XName (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="49cff-102">Pre-Atomization of XName Objects (LINQ to XML) (C#)</span></span>
<span data-ttu-id="49cff-103">Per migliorare le prestazioni in LINQ to XML, è possibile pre-atomizzare gli oggetti <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="49cff-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="49cff-104">Questa operazione consiste nell'assegnare una stringa a un oggetto <xref:System.Xml.Linq.XName> prima di creare l'albero XML usando i costruttori delle classi <xref:System.Xml.Linq.XElement> e <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="49cff-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="49cff-105">Anziché passare una stringa al costruttore, che utilizzerebbe la conversione implicita da stringa a <xref:System.Xml.Linq.XName>, è possibile passare l'oggetto <xref:System.Xml.Linq.XName> inizializzato.</span><span class="sxs-lookup"><span data-stu-id="49cff-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="49cff-106">Questa operazione consente di migliorare le prestazioni quando si crea un albero XML di grandi dimensioni in cui sono ripetuti nomi specifici.</span><span class="sxs-lookup"><span data-stu-id="49cff-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="49cff-107">A tale scopo, è necessario dichiarare e inizializzare gli oggetti <xref:System.Xml.Linq.XName> prima di costruire l'albero XML, quindi usare gli oggetti <xref:System.Xml.Linq.XName> anziché specificare le stringhe per i nomi di elementi e attributi.</span><span class="sxs-lookup"><span data-stu-id="49cff-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="49cff-108">Questa tecnica può consentire un miglioramento significativo delle prestazioni se si crea un numero elevato di elementi (o attributi) con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="49cff-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="49cff-109">Se si decide di usare la pre-atomizzazione, è prima necessario testarla nel proprio scenario.</span><span class="sxs-lookup"><span data-stu-id="49cff-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49cff-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="49cff-110">Example</span></span>  
 <span data-ttu-id="49cff-111">L'esempio seguente illustra questa operazione.</span><span class="sxs-lookup"><span data-stu-id="49cff-111">The following example demonstrates this.</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="49cff-112">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="49cff-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="49cff-113">Nell'esempio seguente è illustrata la stessa tecnica per un documento XML in uno spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="49cff-113">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XName Root = aw + "Root";  
XName Data = aw + "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XAttribute(XNamespace.Xmlns + "aw", aw),  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="49cff-114">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="49cff-114">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="49cff-115">L'esempio seguente è più simile a quello che potrebbe verificarsi in un caso reale.</span><span class="sxs-lookup"><span data-stu-id="49cff-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="49cff-116">In questo esempio il contenuto dell'elemento viene fornito da una query:</span><span class="sxs-lookup"><span data-stu-id="49cff-116">In this example, the content of the element is supplied by a query:</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
DateTime t1 = DateTime.Now;  
XElement root = new XElement(Root,  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement(Data,  
        new XAttribute(ID, i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
 <span data-ttu-id="49cff-117">L'esempio precedente offre prestazioni migliori rispetto all'esempio seguente, in cui i nomi non sono pre-atomizzati:</span><span class="sxs-lookup"><span data-stu-id="49cff-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```csharp  
DateTime t1 = DateTime.Now;  
XElement root = new XElement("Root",  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement("Data",  
        new XAttribute("ID", i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="49cff-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49cff-118">See also</span></span>

- [<span data-ttu-id="49cff-119">Oggetti XName e XNamespace atomizzati (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="49cff-119">Atomized XName and XNamespace Objects (LINQ to XML) (C#)</span></span>](./atomized-xname-and-xnamespace-objects-linq-to-xml.md)
