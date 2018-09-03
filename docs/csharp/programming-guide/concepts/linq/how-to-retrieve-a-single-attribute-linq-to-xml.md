---
title: 'Procedura: Recuperare un singolo attributo (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: 55da36099af72259a4e72205f142ab855f000c4f
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2018
ms.locfileid: "43252785"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-c"></a><span data-ttu-id="6e6be-102">Procedura: Recuperare un singolo attributo (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6e6be-102">How to: Retrieve a Single Attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="6e6be-103">In questo argomento viene illustrato come recuperare un singolo attributo di un elemento, dato il relativo nome.</span><span class="sxs-lookup"><span data-stu-id="6e6be-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="6e6be-104">Questa procedura è utile per la scrittura di espressioni di query in cui si desidera trovare un elemento con un attributo specifico.</span><span class="sxs-lookup"><span data-stu-id="6e6be-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="6e6be-105">Il metodo <xref:System.Xml.Linq.XElement.Attribute%2A> della classe <xref:System.Xml.Linq.XElement> restituisce l'attributo <xref:System.Xml.Linq.XAttribute> con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="6e6be-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e6be-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e6be-106">Example</span></span>  
 <span data-ttu-id="6e6be-107">Nell'esempio seguente viene usato il metodo <xref:System.Xml.Linq.XElement.Attribute%2A>:</span><span class="sxs-lookup"><span data-stu-id="6e6be-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="6e6be-108">In questo esempio vengono individuati tutti i discendenti dell'albero denominato `Phone` e quindi l'attributo denominato `type`.</span><span class="sxs-lookup"><span data-stu-id="6e6be-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="6e6be-109">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="6e6be-109">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="6e6be-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e6be-110">Example</span></span>  
 <span data-ttu-id="6e6be-111">Se si desidera recuperare il valore dell'attributo, è possibile eseguirne il cast, come nel caso degli oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="6e6be-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="6e6be-112">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="6e6be-112">The following example demonstrates this.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =   
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="6e6be-113">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="6e6be-113">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="6e6be-114"> fornisce operatori di cast espliciti per la classe <xref:System.Xml.Linq.XAttribute> in `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` e `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="6e6be-114"> provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e6be-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e6be-115">Example</span></span>  
 <span data-ttu-id="6e6be-116">Nell'esempio seguente viene illustrato lo stesso codice per un attributo all'interno di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6e6be-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="6e6be-117">Per altre informazioni, vedere [Utilizzo degli spazi dei nomi XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="6e6be-117">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement cust = new XElement(aw + "PhoneNumbers",  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "home"),  
        "555-555-5555"),  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants(aw + "Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute(aw + "type"));  
```  
  
 <span data-ttu-id="6e6be-118">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="6e6be-118">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e6be-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e6be-119">See Also</span></span>  
 [<span data-ttu-id="6e6be-120">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="6e6be-120">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
