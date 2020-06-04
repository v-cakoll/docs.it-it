---
title: 'Procedura: Recuperare il valore di un elemento (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
ms.openlocfilehash: b8ff44416f0fbb590119af7e11714e449185d977
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397791"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a>Procedura: recuperare il valore di un elemento (LINQ to XML) (Visual Basic)
In questo argomento viene illustrato come ottenere il valore degli elementi. Questa operazione può essere eseguita in due modi. È possibile eseguire il cast di un oggetto <xref:System.Xml.Linq.XElement> o  <xref:System.Xml.Linq.XAttribute> nel tipo desiderato. L'operatore di conversione esplicito converte quindi il contenuto dell'elemento o dell'attributo nel tipo specificato e lo assegna alla variabile. In alternativa, è possibile usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> o <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>.  
  
 Con Visual Basic l'approccio migliore consiste nell'utilizzo della proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 Per recuperare il valore di un elemento, è sufficiente eseguire il cast dell'oggetto <xref:System.Xml.Linq.XElement> nel tipo desiderato. È sempre possibile eseguire il cast di un elemento in una stringa, come segue:  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Esempio  
 È anche possibile eseguire il cast di elementi in tipi diversi da stringa. Ad esempio, se un elemento contiene un Integer, è possibile eseguirne il cast in `int`, come illustrato nel codice seguente:  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] fornisce operatori di cast espliciti per i seguenti tipi di dati: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` e `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] fornisce gli stessi operatori di cast per gli oggetti <xref:System.Xml.Linq.XAttribute>.  
  
## <a name="example"></a>Esempio  
 È possibile usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A> per recuperare il contenuto di un elemento:  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Esempio  
 A volte, si tenta di recuperare il valore di un elemento anche se non si è certi che esista. In questo caso, quando si assegna l'elemento sottoposto a cast a un tipo Nullable ( `string` o uno dei tipi di valore nullable nel .NET Framework), se l'elemento non esiste, la variabile assegnata viene semplicemente impostata su `Nothing` . Nel codice seguente viene dimostrato che quando non si è certi che l'elemento esista, è preferibile eseguire il cast anziché usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A>.  
  
```vb  
Dim root As XElement = <Root>  
                           <Child1>child 1 content</Child1>  
                           <Child2>2</Child2>  
                       </Root>  
  
' The following assignments show why it is easier to use  
' casting when the element might or might not exist.  
  
Dim c1 As String = CStr(root.Element("Child1"))  
Console.WriteLine("c1:{0}", IIf(c1 Is Nothing, "element does not exist", c1))  
  
Dim c2 As Nullable(Of Integer) = CType(root.Element("Child2"), Nullable(Of Integer))  
Console.WriteLine("c2:{0}", IIf(Not (c2.HasValue), "element does not exist", c2.ToString()))  
  
Dim c3 As String = CStr(root.Element("Child3"))  
Console.WriteLine("c3:{0}", IIf(c3 Is Nothing, "element does not exist", c3))  
  
Dim c4 As Nullable(Of Integer) = CType(root.Element("Child4"), Nullable(Of Integer))  
Console.WriteLine("c4:{0}", IIf(Not (c4.HasValue), "element does not exist", c4.ToString()))  
  
Console.WriteLine()  
  
' The following assignments show the required code when using  
' the Value property when the attribute might or might not exist.  
' Notice that this is more difficult than the casting approach.  
  
Dim e1 As XElement = root.Element("Child1")  
Dim v1 As String  
If (e1 Is Nothing) Then  
    v1 = Nothing  
Else  
    v1 = e1.Value  
End If  
Console.WriteLine("v1:{0}", IIf(v1 Is Nothing, "element does not exist", v1))  
  
Dim e2 As XElement = root.Element("Child2")  
Dim v2 As Nullable(Of Integer)  
If (e2 Is Nothing) Then  
    v2 = Nothing  
Else  
    v2 = e2.Value  
End If  
Console.WriteLine("v2:{0}", IIf(Not (v2.HasValue), "element does not exist", v2))  
  
Dim e3 As XElement = root.Element("Child3")  
Dim v3 As String  
If (e3 Is Nothing) Then  
    v3 = Nothing  
Else  
    v3 = e3.Value  
End If  
Console.WriteLine("v3:{0}", IIf(v3 Is Nothing, "element does not exist", v3))  
  
Dim e4 As XElement = root.Element("Child4")  
Dim v4 As Nullable(Of Integer)  
If (e4 Is Nothing) Then  
    v4 = Nothing  
Else  
    v4 = e4.Value  
End If  
Console.WriteLine("v4:{0}", IIf(Not (v4.HasValue), "element does not exist", v4))  
```  
  
 L'output del codice è il seguente:  
  
```console  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 In generale, è possibile scrivere codice più semplice quando si usa il cast per recuperare il contenuto di elementi e attributi.  
  
## <a name="see-also"></a>Vedere anche

- [Assi LINQ to XML (Visual Basic)](linq-to-xml-axes.md)
