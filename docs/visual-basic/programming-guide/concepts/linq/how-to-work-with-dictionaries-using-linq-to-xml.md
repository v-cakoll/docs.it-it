---
title: 'Procedura: Usare dizionari tramite LINQ to XML (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 6cb3f969-1986-414a-b850-87418712edea
ms.openlocfilehash: 9f08430aeb92b9c6e0b7b08481027fb3b5b77cad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572344"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-visual-basic"></a>Procedura: Usare dizionari tramite LINQ to XML (Visual Basic)
Spesso risulta utile eseguire la conversione in XML di varie strutture dati e la riconversione di altre strutture dati in XML. In questo argomento è illustrata un'implementazione specifica di questo approccio generale con la conversione di un oggetto <xref:System.Collections.Generic.Dictionary%602> in XML e viceversa.  
  
## <a name="example"></a>Esempio  
 Questo esempio Usa i valori letterali XML e una query in un'espressione incorporata. La query proietta nuovi <xref:System.Xml.Linq.XElement> oggetti, che quindi diventano il nuovo contenuto per il `Root` <xref:System.Xml.Linq.XElement> oggetto.  
  
```vb  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)()  
dict.Add("Child1", "Value1")  
dict.Add("Child2", "Value2")  
dict.Add("Child3", "Value3")  
dict.Add("Child4", "Value4")  
Dim root As XElement = _  
    <Root>  
        <%= From keyValue In dict _  
            Select New XElement(keyValue.Key, keyValue.Value) %>  
    </Root>  
Console.WriteLine(root)  
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
  
```vb  
Dim root As XElement = _  
        <Root>  
            <Child1>Value1</Child1>  
            <Child2>Value2</Child2>  
            <Child3>Value3</Child3>  
            <Child4>Value4</Child4>  
        </Root>  
  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)  
For Each el As XElement In root.Elements  
    dict.Add(el.Name.LocalName, el.Value)  
Next  
For Each str As String In dict.Keys  
    Console.WriteLine("{0}:{1}", str, dict(str))  
Next  
```  
  
 L'output del codice è il seguente:  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a>Vedere anche
- [Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
