---
title: 'Procedura: Recuperare il valore superficiale di un elemento (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 730a6670-fb8c-41fc-8a1b-eb97a837e432
ms.openlocfilehash: a861acafe3b9561b1237e6b6449374374c723805
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505797"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-visual-basic"></a>Procedura: Recuperare il valore superficiale di un elemento (Visual Basic)
In questo argomento viene illustrato come ottenere il valore superficiale di un elemento. Per valore superficiale si intende un valore che appartiene solo all'elemento specifico, a differenza del valore completo che include i valori di tutti gli elementi discendenti concatenati in una singola stringa.  
  
 Quando si recupera il valore di un elemento eseguendo il cast o usando la proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>, si ottiene il valore completo. Per recuperare il valore superficiale, è possibile usare il metodo di estensione `ShallowValue`, come illustrato nell'esempio seguente. Il recupero del valore superficiale risulta utile quando si desidera selezionare gli elementi in base al relativo contenuto.  
  
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
  
```vb  
Module Module1  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function ShallowValue(ByVal xe As XElement)  
        Return xe _  
               .Nodes() _  
               .OfType(Of XText)() _  
               .Aggregate(New StringBuilder(), _  
                              Function(s, c) s.Append(c), _  
                              Function(s) s.ToString())  
    End Function  
  
    Sub Main()  
        Dim root As XElement = XElement.Load("Report.xml")  
  
        Dim query As IEnumerable(Of XElement) = _  
            From el In root.Descendants() _  
            Where (el.ShallowValue().StartsWith("=")) _  
            Select el  
  
        For Each q As XElement In query  
            Console.WriteLine("{0}{1}{2}", _  
                q.Name.ToString().PadRight(8), _  
                q.Attribute("Name").ToString().PadRight(20), _  
                q.ShallowValue())  
        Next  
    End Sub  
End Module  
```  
  
 Questo esempio produce il seguente output:  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a>Vedere anche
- [Assi LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
