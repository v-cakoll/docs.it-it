---
title: 'Procedura: eseguire una query LINQ to XML tramite XPath'
ms.date: 07/20/2015
ms.assetid: e1f69a20-1efa-452d-9089-c472fa84b3d5
ms.openlocfilehash: 563756c019ddd458d46f47c843e32ddc7bbaacd1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347650"
---
# <a name="how-to-query-linq-to-xml-using-xpath-visual-basic"></a>How to: Query LINQ to XML Using XPath (Visual Basic)
In questo argomento vengono presentati i metodi di estensione che consentono di eseguire una query su un albero XML usando XPath. Per informazioni dettagliate sull'utilizzo di questi metodi di estensione, vedere <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
 A meno che non esista un motivo molto specifico per eseguire query tramite XPATH, ad esempio l'uso esteso di codice legacy, è preferibile non usare XPATH con LINQ to XML. Le query XPath non vengono eseguite con le stesse prestazioni delle query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata un piccolo albero XML e viene usato <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> per selezionare un set di elementi.  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child1>2</Child1>  
        <Child1>3</Child1>  
        <Child2>4</Child2>  
        <Child2>5</Child2>  
        <Child2>6</Child2>  
    </Root>  
  
Dim list As IEnumerable(Of XElement) = root.XPathSelectElements("./Child2")  
For Each el As XElement In list  
    Console.WriteLine(el)  
Next  
```  
  
 Questo esempio produce il seguente output:  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Advanced Query Techniques (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)
