---
title: 'Procedura: Trovare elementi figlio in base alla posizione (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 6831e1db-5e97-444f-a7a1-d0a87104b005
ms.openlocfilehash: d6dd1150ae3e4ad586e476b777b1f7d47d60c261
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405261"
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-visual-basic"></a>Procedura: trovare elementi figlio in base alla posizione (XPath-LINQ to XML) (Visual Basic)
Talvolta si desidera individuare elementi in base alla posizione, ad esempio il secondo elemento oppure dal terzo al quinto elemento.  
  
 L'espressione XPath è:  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 Sono disponibili due approcci per la scrittura di query [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in modalità lazy. È possibile usare gli operatori <xref:System.Linq.Enumerable.Skip%2A> e <xref:System.Linq.Enumerable.Take%2A> oppure l'overload <xref:System.Linq.Enumerable.Where%2A> che accetta un indice. Quando si usa l'overload <xref:System.Linq.Enumerable.Where%2A>, viene usata un'espressione lambda che accetta due argomenti. Nell'esempio seguente sono illustrati entrambi i metodi di selezione basata sulla posizione.  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono individuati gli elementi `Test` compresi tra il secondo e il quarto. Il risultato è una raccolta di elementi.  
  
 Questo esempio usa il documento XML seguente: [File XML di esempio: configurazione di test (LINQ to XML)](sample-xml-file-test-configuration-linq-to-xml.md).  
  
```vb  
Dim testCfg As XElement = XElement.Load("TestConfig.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test").Skip(1).Take(3)  
  
'LINQ to XML query  
Dim list2 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test"). _  
    Where(Function(ByVal el, ByVal idx) idx >= 1 And idx <= 3)  
  
' XPath expression  
Dim list3 As IEnumerable(Of XElement) = _  
    testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]")  
  
If list1.Count() = list2.Count() And _  
       list1.Count() = list3.Count() And _  
       list1.Intersect(list2).Count() = list1.Count() And _  
       list1.Intersect(list3).Count() = list1.Count() Then  
  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```console  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to XML per gli utenti di XPath (Visual Basic)](linq-to-xml-for-xpath-users.md)
