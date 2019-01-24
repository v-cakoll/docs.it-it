---
title: 'Procedura: Serializzare tramite DataContractSerializer (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: ecaea518-8a0f-4249-b4e5-9b3fb0cdd8ad
ms.openlocfilehash: cde857e1883d822b442b51c2931fd2fb92c24247
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714321"
---
# <a name="how-to-serialize-using-datacontractserializer-visual-basic"></a>Procedura: Serializzare tramite DataContractSerializer (Visual Basic)
In questo argomento viene illustrato un esempio in cui viene usato <xref:System.Runtime.Serialization.DataContractSerializer> per eseguire la serializzazione e la deserializzazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono creati diversi oggetti contenenti oggetti <xref:System.Xml.Linq.XElement>. Tali oggetti vengono quindi serializzati in file di testo e successivamente deserializzati dagli stessi file di testo.  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Linq  
Imports System.IO  
Imports System.Runtime.Serialization  
  
Public Class XLinqTest  
    Shared Sub Main()  
        Test(Of XElement)(CreateXElement())  
        Test(Of XElementContainer)(New XElementContainer())  
        Test(Of XElementNullContainer)(New XElementNullContainer())  
    End Sub  
  
    Public Shared Sub Test(Of T)(ByRef obj)  
        Dim s As DataContractSerializer = New DataContractSerializer(GetType(T))  
        Using fs As FileStream = File.Open("test" & GetType(T).Name & ".xml", FileMode.Create)  
            Console.WriteLine("Testing for type: {0}", GetType(T))  
            s.WriteObject(fs, obj)  
        End Using  
  
        Using fs As FileStream = File.Open("test" & GetType(T).Name & ".xml", FileMode.Open)  
            Dim s2 As Object = s.ReadObject(fs)  
            If s2 Is Nothing Then  
                Console.WriteLine("  Deserialized object is null (Nothing in VB)")  
            Else  
                Console.WriteLine("  Deserialized type: {0}", s2.GetType())  
            End If  
        End Using  
    End Sub  
  
    Public Shared Function CreateXElement() As XElement  
        Return New XElement(XName.Get("NameInNamespace", "http://www.adventure-works.org"))  
    End Function  
End Class  
  
<DataContract()> _  
Public Class XElementContainer  
    <DataMember()> _  
    Public member As XElement  
  
    Public Sub XElementContainer()  
        member = XLinqTest.CreateXElement()  
    End Sub  
End Class  
  
<DataContract()> _  
Public Class XElementNullContainer  
    <DataMember()> _  
    Public member As XElement  
  
    Public Sub XElementNullContainer()  
        member = Nothing  
    End Sub  
End Class  
```  
  
 Questo esempio produce il seguente output:  
  
```  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
```  
  
## <a name="see-also"></a>Vedere anche
- [Serializzazione di oggetti grafici contenenti oggetti XElement (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-object-graphs-that-contain-xelement-objects.md)
