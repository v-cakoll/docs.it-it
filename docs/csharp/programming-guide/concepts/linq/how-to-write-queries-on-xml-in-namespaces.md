---
title: 'Procedura: Scrivere query in XML negli spazi dei nomi (C#)'
ms.date: 07/20/2015
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: a5de5ffdafc2dd191a35860150e48a86a3603f3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33320330"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a><span data-ttu-id="d13fa-102">Procedura: Scrivere query in XML negli spazi dei nomi (C#)</span><span class="sxs-lookup"><span data-stu-id="d13fa-102">How to: Write Queries on XML in Namespaces (C#)</span></span>
<span data-ttu-id="d13fa-103">Per scrivere una query su XML inclusa in uno spazio dei nomi, è necessario usare oggetti <xref:System.Xml.Linq.XName> con lo spazio dei nomi corretto.</span><span class="sxs-lookup"><span data-stu-id="d13fa-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="d13fa-104">Per C#, l'approccio più comune consiste nell'inizializzare un oggetto <xref:System.Xml.Linq.XNamespace> usando una stringa contenente l'URI, quindi usare l'overload dell'operatore di addizione per combinare lo spazio dei nomi con il nome locale.</span><span class="sxs-lookup"><span data-stu-id="d13fa-104">For C#, the most common approach is to initialize an <xref:System.Xml.Linq.XNamespace> using a string that contains the URI, then use the addition operator overload to combine the namespace with the local name.</span></span>  
  
 <span data-ttu-id="d13fa-105">Nel primo set di esempi in questo argomento è illustrato come creare un albero XML in uno spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="d13fa-105">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="d13fa-106">Nel secondo set viene illustrato come creare un albero XML in uno spazio dei nomi con un prefisso.</span><span class="sxs-lookup"><span data-stu-id="d13fa-106">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d13fa-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="d13fa-107">Example</span></span>  
 <span data-ttu-id="d13fa-108">Nell'esempio seguente viene creato un albero XML incluso in uno spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="d13fa-108">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="d13fa-109">Viene quindi recuperata una raccolta di elementi.</span><span class="sxs-lookup"><span data-stu-id="d13fa-109">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="d13fa-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="d13fa-110">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="d13fa-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d13fa-111">Example</span></span>  
 <span data-ttu-id="d13fa-112">In C# le query vengono scritte in modo identico a prescindere che vengano scritte in un albero XML che usa uno spazio dei nomi con un prefisso o in un albero XML con uno spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="d13fa-112">In C#, you write queries in the same way regardless of whether you are writing queries on an XML tree that uses a namespace with a prefix or on an XML tree with a default namespace.</span></span>  
  
 <span data-ttu-id="d13fa-113">Nell'esempio seguente viene creato un albero XML incluso in uno spazio dei nomi con un prefisso.</span><span class="sxs-lookup"><span data-stu-id="d13fa-113">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="d13fa-114">Viene quindi recuperata una raccolta di elementi.</span><span class="sxs-lookup"><span data-stu-id="d13fa-114">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="d13fa-115">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="d13fa-115">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="d13fa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d13fa-116">See Also</span></span>  
 [<span data-ttu-id="d13fa-117">Uso degli spazi dei nomi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="d13fa-117">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
