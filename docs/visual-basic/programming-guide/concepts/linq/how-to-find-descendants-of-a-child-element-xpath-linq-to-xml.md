---
title: 'Procedura: Trovare discendenti di un elemento figlio (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: a958af40-f754-4409-85f9-7746978d4cb3
ms.openlocfilehash: aa6a66f4a53fc74b5946a395f7b61218e680f530
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405222"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-visual-basic"></a>Procedura: trovare discendenti di un elemento figlio (XPath-LINQ to XML) (Visual Basic)
In questo argomento viene illustrato come ottenere gli elementi discendenti di un elemento figlio con un determinato nome.  
  
 L'espressione XPath è:  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a>Esempio  
 In questo esempio sono simulati i problemi di estrazione di testo da una rappresentazione XML di un documento di elaborazione testi. Vengono dapprima selezionati tutti gli elementi `Paragraph` e quindi tutti gli elementi discendenti `Text` di ogni elemento `Paragraph`. Gli elementi discendenti `Text` dell'elemento `Comment` non vengono selezionati.  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Paragraph>  
            <Text>This is the start of</Text>  
        </Paragraph>  
        <Comment>  
            <Text>This comment is not part of the paragraph text.</Text>  
        </Comment>  
        <Paragraph>  
            <Annotation Emphasis='true'>  
                <Text> a sentence.</Text>  
            </Annotation>  
        </Paragraph>  
        <Paragraph>  
            <Text>This is a second sentence.</Text>  
        </Paragraph>  
    </Root>  
  
' LINQ to XML query  
Dim str1 As String = _  
    root.<Paragraph>...<Text>.Select(Function(ByVal s) s.Value). _  
    Aggregate( _  
        New StringBuilder(), _  
        Function(ByVal s, ByVal i) s.Append(i), _  
        Function(ByVal s) s.ToString())  
  
' XPath expression  
Dim str2 As String = DirectCast(root.XPathEvaluate("./Paragraph//Text/text()"), IEnumerable) _  
    .Cast(Of XText)().Select(Function(ByVal s) s.Value) _  
    .Aggregate( _  
        New StringBuilder(), _  
        Function(ByVal s, ByVal i) s.Append(i), _  
        Function(ByVal s) s.ToString())  
  
If str1 = str2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(str2)  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```console  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to XML per gli utenti di XPath (Visual Basic)](linq-to-xml-for-xpath-users.md)
