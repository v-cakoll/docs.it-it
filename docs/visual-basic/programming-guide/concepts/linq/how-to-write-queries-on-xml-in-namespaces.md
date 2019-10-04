---
title: 'Procedura: Scrivere query in XML negli spazi dei nomi (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: 71e66791b41e26ea13f828ef6239a8db9a9365b0
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835001"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a>Procedura: Scrivere query in XML negli spazi dei nomi (Visual Basic)
Per scrivere una query su XML inclusa in uno spazio dei nomi, è necessario usare oggetti <xref:System.Xml.Linq.XName> con lo spazio dei nomi corretto.  
  
 In Visual Basic, l'approccio più comune consiste nel definire uno spazio dei nomi globale, quindi usare valori letterali e proprietà XML che usano lo spazio dei nomi globale. È possibile definire uno spazio dei nomi globale predefinito, nel qual caso gli elementi dei valori letterali XML saranno inclusi nello spazio dei nomi per impostazione predefinita. In alternativa, è possibile definire uno spazio dei nomi globale con un prefisso e quindi usare il prefisso come richiesto nei valori letterali e nelle proprietà XML. Come con altri tipi di XML, gli attributi non sono mai inclusi in alcuno spazio dei nomi per impostazione predefinita.  
  
 Nel primo set di esempi in questo argomento è illustrato come creare un albero XML in uno spazio dei nomi predefinito. Nel secondo set viene illustrato come creare un albero XML in uno spazio dei nomi con un prefisso.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un albero XML incluso in uno spazio dei nomi predefinito. Viene quindi recuperata una raccolta di elementi.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 Questo esempio produce il seguente output:  
  
```console  
1  
2  
3  
```  
  
## <a name="example"></a>Esempio  
 In Visual Basic, tuttavia, la scrittura di query in un albero XML che usa uno spazio dei nomi con un prefisso, è piuttosto diversa dall'esecuzione di query in un albero XML con uno spazio dei nomi predefinito. Lo spazio dei nomi con un prefisso viene in genere importato usando l'istruzione `Imports`. Il prefisso viene quindi usato nei nomi di elementi e attributi quando si crea l'albero XML. Il prefisso viene inoltre usato durante l'esecuzione di query su un albero XML tramite proprietà XML.  
  
 Nell'esempio seguente viene creato un albero XML incluso in uno spazio dei nomi con un prefisso. Viene quindi recuperata una raccolta di elementi.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 Questo esempio produce il seguente output:  
  
```console  
1  
2  
3  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica degli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
