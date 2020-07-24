---
title: Oggetti XName e XNamespace atomizzati (LINQ to XML) (C#)
description: Informazioni sugli oggetti XName e XNamespace atomizzati e sul modo in cui forniscono i vantaggi delle prestazioni per le query.
ms.date: 07/20/2015
ms.assetid: a5b21433-b49d-415c-b00e-bcbfb0d267d7
ms.openlocfilehash: 305a233adab5c860b5f9509ae25ccc5d633e7957
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104285"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-c"></a><span data-ttu-id="b6ca2-103">Oggetti XName e XNamespace atomizzati (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b6ca2-103">Atomized XName and XNamespace Objects (LINQ to XML) (C#)</span></span>
<span data-ttu-id="b6ca2-104">Gli oggetti <xref:System.Xml.Linq.XName> e <xref:System.Xml.Linq.XNamespace> sono *atomizzati*, ovvero, se contengono lo stesso nome completo fanno riferimento allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-104"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="b6ca2-105">Questo offre vantaggi a livello di prestazioni per le query: quando si confrontano due nomi atomizzati per verificarne l'uguaglianza, il linguaggio intermedio sottostante deve determinare solo se i due riferimenti puntano allo stesso oggetto.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-105">This yields performance benefits for queries: When you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="b6ca2-106">Il codice sottostante non deve eseguire confronti tra stringhe, che richiederebbero molto tempo.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-106">The underlying code does not have to do string comparisons, which would be time consuming.</span></span>  
  
## <a name="atomization-semantics"></a><span data-ttu-id="b6ca2-107">Semantica di atomizzazione</span><span class="sxs-lookup"><span data-stu-id="b6ca2-107">Atomization Semantics</span></span>  
 <span data-ttu-id="b6ca2-108">Atomizzazione significa che se due oggetti <xref:System.Xml.Linq.XName> hanno lo stesso nome locale e si trovano nello stesso spazio dei nomi, condividono la stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-108">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they are in the same namespace, they share the same instance.</span></span> <span data-ttu-id="b6ca2-109">Analogamente, se due oggetti <xref:System.Xml.Linq.XNamespace> hanno lo stesso URI dello spazio dei nomi, condividono la stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-109">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>  
  
 <span data-ttu-id="b6ca2-110">Affinché una classe consenta gli oggetti atomizzati, il costruttore per la classe deve essere privato, non pubblico.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-110">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="b6ca2-111">Se il costruttore fosse pubblico, sarebbe possibile creare un oggetto non atomizzato.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-111">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="b6ca2-112">Le classi <xref:System.Xml.Linq.XName> e <xref:System.Xml.Linq.XNamespace> implementano un operatore di conversione implicita per la conversione di una stringa in un oggetto <xref:System.Xml.Linq.XName> o <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-112">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="b6ca2-113">In questo modo è possibile ottenere un'istanza di questi oggetti.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-113">This is how you get an instance of these objects.</span></span> <span data-ttu-id="b6ca2-114">Non è possibile ottenere un'istanza tramite un costruttore, in quanto il costruttore è inaccessibile.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-114">You cannot get an instance by using a constructor, because the constructor is inaccessible.</span></span>  
  
 <span data-ttu-id="b6ca2-115"><xref:System.Xml.Linq.XName> e <xref:System.Xml.Linq.XNamespace> implementano anche gli operatori di uguaglianza e di disuguaglianza, per determinare se i due oggetti confrontati sono riferimenti alla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-115"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, to determine whether the two objects being compared are references to the same instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6ca2-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="b6ca2-116">Example</span></span>  
 <span data-ttu-id="b6ca2-117">Nel codice seguente vengono creati alcuni oggetti <xref:System.Xml.Linq.XElement> e viene dimostrato che i nomi identici condividono la stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-117">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>  
  
```csharp  
XElement r1 = new XElement("Root", "data1");  
XElement r2 = XElement.Parse("<Root>data2</Root>");  
  
if ((object)r1.Name == (object)r2.Name)  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.");  
else  
    Console.WriteLine("Different");  
  
XName n = "Root";  
  
if ((object)n == (object)r1.Name)  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.");  
else  
    Console.WriteLine("Different");  
```  
  
 <span data-ttu-id="b6ca2-118">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="b6ca2-118">This example produces the following output:</span></span>  
  
```output  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 <span data-ttu-id="b6ca2-119">Come illustrato in precedenza, il vantaggio degli oggetti atomizzati consiste nel fatto che quando si usa uno dei metodi dell'asse che accettano <xref:System.Xml.Linq.XName> come parametro, il metodo dell'asse deve determinare solo che due nomi fanno riferimento alla stessa istanza per selezionare gli elementi desiderati.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-119">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>  
  
 <span data-ttu-id="b6ca2-120">Nell'esempio seguente viene passato un oggetto <xref:System.Xml.Linq.XName> alla chiamata al metodo <xref:System.Xml.Linq.XContainer.Descendants%2A>, le cui prestazioni sono quindi migliori grazie al modello di atomizzazione.</span><span class="sxs-lookup"><span data-stu-id="b6ca2-120">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("C1", 1),  
    new XElement("Z1",  
        new XElement("C1", 2),  
        new XElement("C1", 1)  
    )  
);  
  
var query = from e in root.Descendants("C1")  
            where (int)e == 1  
            select e;  
  
foreach (var z in query)  
    Console.WriteLine(z);  
```  
  
 <span data-ttu-id="b6ca2-121">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="b6ca2-121">This example produces the following output:</span></span>  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
