---
title: 'Procedura: Recuperare il valore di un attributo (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 48ad3c0ab079012793fd9eea89d52fc3a7b1698f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397804"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a>Procedura: recuperare il valore di un attributo (LINQ to XML) (Visual Basic)
In questo argomento viene illustrato come ottenere il valore di attributi. Per eseguire questa operazione, è possibile scegliere tra due alternative. È possibile eseguire il cast di un <xref:System.Xml.Linq.XAttribute> al tipo desiderato; l'operatore di conversione esplicito converte quindi il contenuto dell'elemento o dell'attributo al tipo specificato. In alternativa, è possibile usare la proprietà <xref:System.Xml.Linq.XAttribute.Value%2A>. L'esecuzione del cast costituisce in genere l'approccio migliore. Se si esegue il cast dell'attributo a un tipo di valore Nullable, il codice è più semplice da scrivere quando si recupera il valore di un attributo che potrebbe o meno esistere. Per esempi di questa tecnica, vedere [procedura: recuperare il valore di un elemento (LINQ to XML) (Visual Basic)](how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
## <a name="example"></a>Esempio  
 In Visual Basic è possibile usare la proprietà integrata dell'attributo per recuperare il valore di un attributo.  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>Esempio  
 In Visual Basic è possibile usare la proprietà integrata dell'attributo per impostare il valore di un attributo. Se inoltre si usa la proprietà integrata dell'attributo per impostare il valore di un attributo non esistente, l'attributo verrà creato.  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come recuperare il valore di un attributo quando l'attributo è in uno spazio dei nomi. Per ulteriori informazioni, vedere [Cenni preliminari sugli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```console  
abcde  
```  
  
## <a name="see-also"></a>Vedere anche

- [Assi LINQ to XML (Visual Basic)](linq-to-xml-axes.md)
