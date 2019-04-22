---
title: 'Procedura: Controllare il tipo di una proiezione (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a0171276-0b46-4817-aee5-a8d5191b12fe
ms.openlocfilehash: dd09914a75a8d4b20ddf9ff452f046bf7671152f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831405"
---
# <a name="how-to-control-the-type-of-a-projection-visual-basic"></a>Procedura: Controllare il tipo di una proiezione (Visual Basic)
Per proiezione si intende il processo in cui un unico set di dati viene accettato e filtrato, ne viene cambiata la forma e persino il tipo. Le proiezioni vengono eseguite nella maggior parte delle espressioni di query. Quasi tutte le espressioni di query illustrate in questa sezione restituiscono il tipo <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, tuttavia è possibile controllare il tipo della proiezione per creare raccolte di altri tipi. In questo argomento viene illustrato come eseguire questa operazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito un nuovo tipo `Customer`. L'espressione di query crea quindi un'istanza per nuovi oggetti `Customer` nella clausola `Select`. Il tipo dell'espressione di query diventa quindi <xref:System.Collections.Generic.IEnumerable%601> di `Customer`.  
  
 Nell'esempio viene usato il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
```vb  
Public Class Customer  
    Private customerIDValue As String  
    Public Property CustomerID() As String  
        Get  
            Return customerIDValue  
        End Get  
        Set(ByVal value As String)  
            customerIDValue = value  
        End Set  
    End Property  
  
    Private companyNameValue As String  
    Public Property CompanyName() As String  
        Get  
            Return companyNameValue  
        End Get  
        Set(ByVal value As String)  
            companyNameValue = value  
        End Set  
    End Property  
  
    Private contactNameValue As String  
    Public Property ContactName() As String  
        Get  
            Return contactNameValue  
        End Get  
        Set(ByVal value As String)  
            contactNameValue = value  
        End Set  
    End Property  
  
    Public Sub New(ByVal customerID As String, _  
                   ByVal companyName As String, _  
                   ByVal contactName As String)  
        CustomerIDValue = customerID  
        CompanyNameValue = companyName  
        ContactNameValue = contactName  
    End Sub  
  
    Public Overrides Function ToString() As String  
        Return String.Format("{0}:{1}:{2}", Me.CustomerID, Me.CompanyName, Me.ContactName)  
    End Function  
End Class  
  
Sub Main()  
    Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
    Dim custList As IEnumerable(Of Customer) = _  
        From el In custOrd.<Customers>.<Customer> _  
        Select New Customer( _  
            el.@<CustomerID>, _  
            el.<CompanyName>.Value, _  
            el.<ContactName>.Value _  
        )  
    For Each cust In custList  
        Console.WriteLine(cust)  
    Next  
End Sub  
```  
  
 L'output del codice è il seguente:  
  
```  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.Enumerable.Select%2A>
- [Proiezioni e trasformazioni (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
