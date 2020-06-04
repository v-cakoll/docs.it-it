---
title: 'Procedura: Creare un documento con spazi dei nomi (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
ms.openlocfilehash: a440c9d810798eb5ebd025a336cbb17fface23b4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414634"
---
# <a name="how-to-create-a-document-with-namespaces-linq-to-xml-visual-basic"></a>Procedura: creare un documento con spazi dei nomi (LINQ to XML) (Visual Basic)
In questo argomento viene illustrato come creare un documento con spazi dei nomi in Visual Basic.  
  
 Quando si usano valori letterali XML in Visual Basic, gli utenti possono definire un unico spazio dei nomi XML predefinito globale. Tale spazio dei nomi è quello predefinito sia per i valori letterali XML che per le proprietà XML. Lo spazio dei nomi XML predefinito può essere definito a livello di progetto o di file. Se viene definito a livello di file, sostituisce quello predefinito a livello di progetto.  
  
 È inoltre possibile definire altri spazi dei nomi e specificarne i prefissi.  
  
 Per definire spazi dei nomi predefiniti e spazi dei nomi con prefissi, usare la parola chiave `Imports`.  
  
 Per ulteriori informazioni, vedere [Introduzione ai valori letterali XML in Visual Basic](introduction-to-xml-literals.md).  
  
 Notare che lo spazio dei nomi XML predefinito si applica solo agli elementi e non agli attributi. Per impostazione predefinita, gli attributi non sono inclusi in nessuno spazio dei nomi. È tuttavia possibile usare un prefisso dello spazio dei nomi per inserire un attributo in uno spazio dei nomi.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene creato un documento contenente uno spazio dei nomi.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child aw:Att="attvalue"/>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child aw:Att="attvalue" />  
</aw:Root>  
```  
  
## <a name="example"></a>Esempio  
 In questo esempio viene creato un documento contenente due spazi dei nomi, uno dei quali è quello predefinito.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child Att="attvalue"/>  
                <fc:Child2>child2 content</fc:Child2>  
            </Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">  
  <Child Att="attvalue" />  
  <fc:Child2>child2 content</fc:Child2>  
</Root>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un documento contenente più spazi dei nomi, tutti con prefisso.  
  
 Quando si serializza un albero XML, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] genera dichiarazioni degli spazi dei nomi in base alle necessità in modo che ogni elemento venga inserito nel relativo spazio dei nomi definito.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica degli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
