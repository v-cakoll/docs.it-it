---
title: Eventi LINQ to XML
ms.date: 07/20/2015
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
ms.openlocfilehash: d00f6f1b2a14ac73c1bcd4a1f74b9714ca304da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368816"
---
# <a name="linq-to-xml-events-visual-basic"></a>Eventi LINQ to XML (Visual Basic)
Gli eventi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consentono di ricevere una notifica quando un albero XML viene modificato.  
  
 È possibile aggiungere eventi a un'istanza di qualsiasi oggetto <xref:System.Xml.Linq.XObject>. Il gestore eventi riceverà quindi gli eventi relativi alle modifiche apportate a <xref:System.Xml.Linq.XObject> e a tutti i relativi discendenti. Ad esempio, è possibile aggiungere un gestore eventi alla radice dell'albero e gestire tutte le modifiche apportate alla struttura da tale gestore.  
  
 Per esempi di eventi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], vedere <xref:System.Xml.Linq.XObject.Changing> e <xref:System.Xml.Linq.XObject.Changed>.  
  
## <a name="types-and-events"></a>Tipi ed eventi  
 Con gli eventi è possibile usare i tipi seguenti:  
  
|Type|Description|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|Specifica il tipo di evento quando viene generato un evento per un oggetto <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|Fornisce i dati per gli eventi <xref:System.Xml.Linq.XObject.Changing> e <xref:System.Xml.Linq.XObject.Changed>.|  
  
 Gli eventi seguenti vengono generati quando si modifica una struttura ad albero XML:  
  
|Event|Descrizione|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|Si verifica poco prima che l'oggetto <xref:System.Xml.Linq.XObject> o uno qualsiasi dei relativi discendenti venga modificato.|  
|<xref:System.Xml.Linq.XObject.Changed>|Si verifica quando un oggetto <xref:System.Xml.Linq.XObject> o uno qualsiasi dei relativi discendenti viene modificato.|  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Gli eventi sono utili quando si desidera gestire alcune informazioni di aggregazione in un albero XML. Ad esempio, si desidera gestire un totale di fattura che corrisponde alla somma delle voci della fattura. In questo esempio vengono usati gli eventi per gestire il totale di tutti gli elementi figlio sotto l'elemento `Items` complesso.  
  
### <a name="code"></a>Codice  
  
```vb  
Module Module1  
    Dim WithEvents items As XElement = Nothing  
    Dim total As XElement = Nothing  
    Dim root As XElement = _  
            <Root>  
                <Total>0</Total>  
                <Items></Items>  
            </Root>  
  
    Private Sub XObjectChanged( _  
            ByVal sender As Object, _  
            ByVal cea As XObjectChangeEventArgs) _  
            Handles items.Changed  
        Select Case cea.ObjectChange  
            Case XObjectChange.Add  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
            Case XObjectChange.Remove  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
        End Select  
        Console.WriteLine("Changed {0} {1}", _  
                            sender.GetType().ToString(), _  
                            cea.ObjectChange.ToString())  
    End Sub  
  
    Sub Main()  
        total = root.<Total>(0)  
        items = root.<Items>(0)  
        items.SetElementValue("Item1", 25)  
        items.SetElementValue("Item2", 50)  
        items.SetElementValue("Item2", 75)  
        items.SetElementValue("Item3", 133)  
        items.SetElementValue("Item1", Nothing)  
        items.SetElementValue("Item4", 100)  
        Console.WriteLine("Total:{0}", CInt(total))  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>Commenti  
 L'output del codice è il seguente:  
  
```console  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione LINQ to XML avanzata (Visual Basic)](advanced-linq-to-xml-programming.md)
