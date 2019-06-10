---
title: 'Procedura: Usare dizionari tramite LINQ to XML (C#)'
ms.date: 07/20/2015
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: 196720ff9c17e62f8da9e65e1b8c481fed5074cc
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484722"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a><span data-ttu-id="49c0d-102">Procedura: Usare dizionari tramite LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="49c0d-102">How to: Work with Dictionaries Using LINQ to XML (C#)</span></span>
<span data-ttu-id="49c0d-103">Spesso risulta utile eseguire la conversione in XML di varie strutture dati e la riconversione di altre strutture dati in XML.</span><span class="sxs-lookup"><span data-stu-id="49c0d-103">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="49c0d-104">In questo argomento è illustrata un'implementazione specifica di questo approccio generale con la conversione di un oggetto <xref:System.Collections.Generic.Dictionary%602> in XML e viceversa.</span><span class="sxs-lookup"><span data-stu-id="49c0d-104">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49c0d-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="49c0d-105">Example</span></span>  
 <span data-ttu-id="49c0d-106">L'esempio usa un tipo di costruzione funzionale in cui una query proietta nuovi oggetti <xref:System.Xml.Linq.XElement> e la raccolta risultante viene passata come argomento al costruttore dell'oggetto <xref:System.Xml.Linq.XElement> Root.</span><span class="sxs-lookup"><span data-stu-id="49c0d-106">This example uses a form of functional construction in which a query projects new <xref:System.Xml.Linq.XElement> objects, and the resulting collection is passed as an argument to the constructor of the Root <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
Dictionary<string, string> dict = new Dictionary<string, string>();  
dict.Add("Child1", "Value1");  
dict.Add("Child2", "Value2");  
dict.Add("Child3", "Value3");  
dict.Add("Child4", "Value4");  
XElement root = new XElement("Root",  
    from keyValue in dict  
    select new XElement(keyValue.Key, keyValue.Value)  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="49c0d-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="49c0d-107">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="49c0d-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="49c0d-108">Example</span></span>  
 <span data-ttu-id="49c0d-109">Nel codice seguente viene creato un dizionario da XML.</span><span class="sxs-lookup"><span data-stu-id="49c0d-109">The following code creates a dictionary from XML.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "Value1"),  
    new XElement("Child2", "Value2"),  
    new XElement("Child3", "Value3"),  
    new XElement("Child4", "Value4")  
);  
  
Dictionary<string, string> dict = new Dictionary<string, string>();  
foreach (XElement el in root.Elements())  
    dict.Add(el.Name.LocalName, el.Value);  
foreach (string str in dict.Keys)  
    Console.WriteLine("{0}:{1}", str, dict[str]);  
```  
  
 <span data-ttu-id="49c0d-110">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="49c0d-110">This code produces the following output:</span></span>  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  