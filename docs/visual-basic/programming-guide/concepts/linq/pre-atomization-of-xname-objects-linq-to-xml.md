---
title: Pre-atomizzazione di oggetti XName (LINQ to XML) (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4871fab18d04ce9d715299fd06138c493e666466
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="11092-102">Pre-atomizzazione di oggetti XName (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11092-102">Pre-Atomization of XName Objects (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="11092-103">Per migliorare le prestazioni in LINQ to XML, è possibile pre-atomizzare <xref:System.Xml.Linq.XName>oggetti.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="11092-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="11092-104">Pre-atomizzazione significa che si assegna una stringa di un <xref:System.Xml.Linq.XName>dell'oggetto prima di creare la struttura ad albero XML usando i costruttori del <xref:System.Xml.Linq.XElement>e <xref:System.Xml.Linq.XAttribute>classi.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="11092-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="11092-105">Quindi, anziché passare una stringa al costruttore, che utilizzerebbe la conversione implicita da stringa a <xref:System.Xml.Linq.XName>, si passa l'inizializzato <xref:System.Xml.Linq.XName>oggetto.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="11092-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="11092-106">Questa operazione consente di migliorare le prestazioni quando si crea un albero XML di grandi dimensioni in cui sono ripetuti nomi specifici.</span><span class="sxs-lookup"><span data-stu-id="11092-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="11092-107">A tale scopo, è necessario dichiarare e inizializzare <xref:System.Xml.Linq.XName>oggetti prima di costruire la struttura ad albero XML, quindi utilizzare il <xref:System.Xml.Linq.XName>oggetti anziché specificare le stringhe per i nomi di elementi e attributi.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="11092-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="11092-108">Questa tecnica può consentire un miglioramento significativo delle prestazioni se si crea un numero elevato di elementi (o attributi) con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="11092-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="11092-109">Se si decide di usare la pre-atomizzazione, è prima necessario testarla nel proprio scenario.</span><span class="sxs-lookup"><span data-stu-id="11092-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11092-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="11092-110">Example</span></span>  
 <span data-ttu-id="11092-111">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="11092-111">The following example demonstrates this.</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="11092-112">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="11092-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="11092-113">Nell'esempio seguente è illustrata la stessa tecnica per un documento XML in uno spazio dei nomi:</span><span class="sxs-lookup"><span data-stu-id="11092-113">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```vb  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim Root__1 As XName = aw + "Root"  
Dim Data As XName = aw + "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XAttribute(XNamespace.Xmlns + "aw", aw), New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="11092-114">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="11092-114">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="11092-115">L'esempio seguente è più simile a quello che potrebbe verificarsi in un caso reale.</span><span class="sxs-lookup"><span data-stu-id="11092-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="11092-116">In questo esempio il contenuto dell'elemento viene fornito da una query:</span><span class="sxs-lookup"><span data-stu-id="11092-116">In this example, the content of the element is supplied by a query:</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim t1 As DateTime = DateTime.Now  
Dim root__2 As New XElement(Root__1, From i In System.Linq.Enumerable.Range(1, 100000)New XElement(Data, New XAttribute(ID, i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
 <span data-ttu-id="11092-117">L'esempio precedente offre prestazioni migliori rispetto all'esempio seguente, in cui i nomi non sono pre-atomizzati:</span><span class="sxs-lookup"><span data-stu-id="11092-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```vb  
Dim t1 As DateTime = DateTime.Now  
Dim root As New XElement("Root", From i In System.Linq.Enumerable.Range(1, 100000)New XElement("Data", New XAttribute("ID", i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="11092-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11092-118">See Also</span></span>  
 <span data-ttu-id="11092-119">[Prestazioni (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="11092-119">[Performance (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md) </span></span>  
<span data-ttu-id="11092-120"> [Scomporre oggetti XName e XNamespace (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="11092-120"> [Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)</span></span>
