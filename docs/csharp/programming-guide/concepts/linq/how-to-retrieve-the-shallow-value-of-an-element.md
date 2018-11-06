---
title: 'Procedura: Recuperare il valore superficiale di un elemento (C#)'
ms.date: 07/20/2015
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
ms.openlocfilehash: 2555b2f17120e4dce670a9fef9fc6a126a47e935
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180648"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a>Procedura: Recuperare il valore superficiale di un elemento (C#)
In questo argomento viene illustrato come ottenere il valore superficiale di un elemento. Per valore superficiale si intende un valore che appartiene solo all'elemento specifico, a differenza del valore completo che include i valori di tutti gli elementi discendenti concatenati in una singola stringa.  
  
 Quando si recupera il valore di un elemento eseguendo il cast o usando la proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>, si ottiene il valore completo. Per recuperare il valore superficiale, è possibile usare il metodo di estensione `ShallowValue`, come mostrato nell'esempio seguente. Il recupero del valore superficiale risulta utile quando si desidera selezionare gli elementi in base al relativo contenuto.  
  
 Nell'esempio seguente viene dichiarato un metodo di estensione che recupera il valore superficiale di un elemento. Questo metodo di estensione viene quindi usato in una query per elencare tutti gli elementi che contengono un valore calcolato.  
  
## <a name="example"></a>Esempio  
 Il file di testo seguente, Report.xml, è l'origine di questo esempio.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 Questo esempio produce il seguente output:  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a>Vedere anche

- [Assi LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
