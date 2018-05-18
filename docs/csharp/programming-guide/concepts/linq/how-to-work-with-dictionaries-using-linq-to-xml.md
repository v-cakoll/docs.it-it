---
title: 'Procedura: Usare dizionari tramite LINQ to XML (C#)'
ms.date: 07/20/2015
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: 3f3b2a19f2527ef5d2fececf916c09256e90af7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a>Procedura: Usare dizionari tramite LINQ to XML (C#)
Spesso risulta utile eseguire la conversione in XML di varie strutture dati e la riconversione di altre strutture dati in XML. In questo argomento è illustrata un'implementazione specifica di questo approccio generale con la conversione di un oggetto <xref:System.Collections.Generic.Dictionary%602> in XML e viceversa.  
  
## <a name="example"></a>Esempio  
 L'esempio usa un tipo di costruzione funzionale in cui una query proietta nuovi oggetti <xref:System.Xml.Linq.XElement> e la raccolta risultante viene passata come argomento al costruttore dell'oggetto <xref:System.Xml.Linq.XElement> Root.  
  
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
  
 L'output del codice è il seguente:  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a>Esempio  
 Nel codice seguente viene creato un dizionario da XML.  
  
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
  
 L'output del codice è il seguente:  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Projections and Transformations (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md) (Proiezioni e trasformazioni (LINQ to XML) in C#)
