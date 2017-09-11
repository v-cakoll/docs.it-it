---
title: Scomporre oggetti XName e XNamespace (LINQ to XML) (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 1303d0be3715bb6462ef28b1b2286b999661d240
ms.contentlocale: it-it
ms.lasthandoff: 06/01/2017


---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="75f12-102">Scomporre oggetti XName e XNamespace (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75f12-102">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="75f12-103"><xref:System.Xml.Linq.XName>e <xref:System.Xml.Linq.XNamespace>sono oggetti *atomizzati*; ovvero, se contengono lo stesso nome completo, fanno riferimento allo stesso oggetto.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="75f12-103"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="75f12-104">Questo offre vantaggi a livello di prestazioni per le query: quando si confrontano due nomi atomizzati per verificarne l'uguaglianza, il linguaggio intermedio sottostante deve determinare solo se i due riferimenti puntano allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="75f12-104">This yields performance benefits for queries: When you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="75f12-105">Il codice sottostante non deve eseguire confronti tra stringhe, che richiederebbero molto tempo.</span><span class="sxs-lookup"><span data-stu-id="75f12-105">The underlying code does not have to do string comparisons, which would be time consuming.</span></span>  
  
## <a name="atomization-semantics"></a><span data-ttu-id="75f12-106">Semantica di atomizzazione</span><span class="sxs-lookup"><span data-stu-id="75f12-106">Atomization Semantics</span></span>  
 <span data-ttu-id="75f12-107">Atomizzazione significa che se due <xref:System.Xml.Linq.XName>gli oggetti hanno lo stesso nome locale e si trovano nello stesso spazio dei nomi, condividono la stessa istanza.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="75f12-107">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they are in the same namespace, they share the same instance.</span></span> <span data-ttu-id="75f12-108">Nello stesso modo, se due <xref:System.Xml.Linq.XNamespace>gli oggetti hanno lo stesso URI dei nomi, condividono la stessa istanza.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="75f12-108">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>  
  
 <span data-ttu-id="75f12-109">Affinché una classe consenta gli oggetti atomizzati, il costruttore per la classe deve essere privato, non pubblico.</span><span class="sxs-lookup"><span data-stu-id="75f12-109">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="75f12-110">Se il costruttore fosse pubblico, sarebbe possibile creare un oggetto non atomizzato.</span><span class="sxs-lookup"><span data-stu-id="75f12-110">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="75f12-111"><xref:System.Xml.Linq.XName>E <xref:System.Xml.Linq.XNamespace>le classi implementano un operatore di conversione implicita per convertire una stringa in un <xref:System.Xml.Linq.XName>o <xref:System.Xml.Linq.XNamespace>.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="75f12-111">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="75f12-112">In questo modo è possibile ottenere un'istanza di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="75f12-112">This is how you get an instance of these objects.</span></span> <span data-ttu-id="75f12-113">Non è possibile ottenere un'istanza tramite un costruttore, in quanto il costruttore è inaccessibile.</span><span class="sxs-lookup"><span data-stu-id="75f12-113">You cannot get an instance by using a constructor, because the constructor is inaccessible.</span></span>  
  
 <span data-ttu-id="75f12-114"><xref:System.Xml.Linq.XName>e <xref:System.Xml.Linq.XNamespace>implementare anche gli operatori di uguaglianza e disuguaglianza, per determinare se i due oggetti confrontati sono riferimenti alla stessa istanza.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="75f12-114"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, to determine whether the two objects being compared are references to the same instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75f12-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="75f12-115">Example</span></span>  
 <span data-ttu-id="75f12-116">Il codice seguente vengono creati alcuni <xref:System.Xml.Linq.XElement>gli oggetti e viene dimostrato che i nomi identici condividono la stessa istanza.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="75f12-116">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>  
  
```vb  
Dim r1 As New XElement("Root", "data1")  
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")  
  
If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
Dim n As XName = "Root"  
  
If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
```  
  
 <span data-ttu-id="75f12-117">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="75f12-117">This example produces the following output:</span></span>  
  
```  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 <span data-ttu-id="75f12-118">Come accennato in precedenza, il vantaggio degli oggetti atomizzati è che quando si utilizza uno dei metodi dell'asse che accettano un <xref:System.Xml.Linq.XName>come parametro, il metodo dell'asse deve determinare solo che due nomi fanno riferimento alla stessa istanza per selezionare gli elementi desiderati.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="75f12-118">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>  
  
 <span data-ttu-id="75f12-119">Nell'esempio seguente viene passato un <xref:System.Xml.Linq.XName>per il <xref:System.Xml.Linq.XContainer.Descendants%2A>chiamata al metodo, che quindi offre prestazioni migliori grazie al modello di atomizzazione.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="75f12-119">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>  
  
```vb  
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))  
  
Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e  
  
For Each z As var In query  
    Console.WriteLine(z)  
Next  
```  
  
 <span data-ttu-id="75f12-120">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="75f12-120">This example produces the following output:</span></span>  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="75f12-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75f12-121">See Also</span></span>  
 [<span data-ttu-id="75f12-122">Prestazioni (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75f12-122">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

