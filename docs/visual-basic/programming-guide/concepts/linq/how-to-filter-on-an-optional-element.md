---
title: 'Procedura: filtro su un elemento facoltativo (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a74b76ad-6889-4185-a189-d6ef2c63841e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 32183a26a02640c655030eff18d62329fb1c125a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-filter-on-an-optional-element-visual-basic"></a>Procedura: filtro su un elemento facoltativo (Visual Basic)
Talvolta si desidera filtrare in base a un elemento anche se non si è certi che esista nel documento XML. La ricerca deve essere eseguita in modo che se l'elemento specifico non include l'elemento figlio, non viene generata un'eccezione di riferimento null quando si applica un filtro sull'elemento. Nell'esempio seguente l'elemento `Child5` non contiene un elemento figlio `Type`, tuttavia la query viene comunque eseguita correttamente.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usato il metodo di estensione <xref:System.Xml.Linq.Extensions.Elements%2A>.  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1>  
            <Text>Child One Text</Text>  
            <Type Value="Yes"/>  
        </Child1>  
        <Child2>  
            <Text>Child Two Text</Text>  
            <Type Value="Yes"/>  
        </Child2>  
        <Child3>  
            <Text>Child Three Text</Text>  
            <Type Value="No"/>  
        </Child3>  
        <Child4>  
            <Text>Child Four Text</Text>  
            <Type Value="Yes"/>  
        </Child4>  
        <Child5>  
            <Text>Child Five Text</Text>  
        </Child5>  
    </Root>  
Dim cList As IEnumerable(Of String) = _  
    From typeElement In root.Elements().<Type> _  
    Where typeElement.@Value = "Yes" _  
    Select typeElement.Parent.<Text>.Value  
Dim str As String  
For Each str In cList  
    Console.WriteLine(str)  
Next  
```  
  
 L'output del codice è il seguente:  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi. Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child1>  
                    <Text>Child One Text</Text>  
                    <Type Value="Yes"/>  
                </Child1>  
                <Child2>  
                    <Text>Child Two Text</Text>  
                    <Type Value="Yes"/>  
                </Child2>  
                <Child3>  
                    <Text>Child Three Text</Text>  
                    <Type Value="No"/>  
                </Child3>  
                <Child4>  
                    <Text>Child Four Text</Text>  
                    <Type Value="Yes"/>  
                </Child4>  
                <Child5>  
                    <Text>Child Five Text</Text>  
                </Child5>  
            </Root>  
        Dim cList As IEnumerable(Of String) = _  
            From typeElement In root.Elements().<Type> _  
            Where typeElement.@Value = "Yes" _  
            Select typeElement.Parent.<Text>.Value  
        Dim str As String  
        For Each str In cList  
            Console.WriteLine(str)  
        Next  
    End Sub  
End Module  
```  
  
 L'output del codice è il seguente:  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>  
 [Le query di base (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [Proprietà Child Axis XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [Proprietà axis dell'attributo XML](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)  
 [Proprietà Value XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [Panoramica degli operatori query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [Operazioni di proiezione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
