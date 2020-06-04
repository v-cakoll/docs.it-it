---
title: "Procedura: Concatenare chiamate al metodo dell'asse (LINQ to XML)"
ms.date: 07/20/2015
ms.assetid: e4e22942-39bd-460f-b3c0-9f09e53d3aa9
ms.openlocfilehash: 51396c9aaffb43badf405600251ed5cb06198dc3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375135"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-visual-basic"></a>Procedura: concatenare le chiamate al metodo dell'asse (LINQ to XML) (Visual Basic)
Uno schema comune da usare nel codice consiste nel chiamare un metodo dell'asse e quindi chiamare uno degli assi del metodo di estensione.  
  
 Sono disponibili due assi denominati `Elements` che restituiscono una raccolta di elementi: il metodo <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> e il metodo <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>. È possibile combinare questi due assi per individuare tutti gli elementi con un nome specificato a una data profondità dell'albero.  
  
## <a name="example"></a>Esempio  
 In questo esempio vengono usati <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> e <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> per individuare tutti gli elementi `Name` inclusi in tutti gli elementi `Address` di tutti gli elementi `PurchaseOrder`.  
  
 Questo esempio usa il documento XML seguente: [File XML di esempio: più ordini di acquisto (LINQ to XML)](sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```vb  
Dim purchaseOrders As XElement = XElement.Load("PurchaseOrders.xml")  
Dim names As IEnumerable(Of XElement) = _  
    From el In purchaseOrders.<PurchaseOrder>.<Address>.<Name> _  
    Select el  
For Each e As XElement In names  
    Console.WriteLine(e)  
Next  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 Questo esempio viene eseguito correttamente perché una delle implementazioni dell'asse `Elements` è un metodo di estensione su <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XContainer>. <xref:System.Xml.Linq.XElement> deriva da <xref:System.Xml.Linq.XContainer>, pertanto è possibile chiamare il metodo <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> sui risultati di una chiamata al metodo <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 Talvolta si desidera recuperare tutti gli elementi presenti a una data profondità dell'elemento in cui possono o meno esistere elementi predecessori intermedi. Ad esempio, nel documento seguente può essere necessario recuperare tutti gli elementi `ConfigParameter` che sono elementi figli dell'elemento `Customer`, ma non `ConfigParameter` che è un elemento figlio dell'elemento `Root`.  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 A tale scopo, è possibile usare l'asse <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> nel modo seguente:  
  
```vb  
Dim root As XElement = XElement.Load("Irregular.xml")  
Dim configParameters As IEnumerable(Of XElement) = _  
    root.<Customer>.<Config>.<ConfigParameter>  
For Each cp As XElement In configParameters  
    Console.WriteLine(cp)  
Next  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è illustrata la stessa tecnica per XML in uno spazio dei nomi. Per ulteriori informazioni, vedere [Cenni preliminari sugli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
 Nell'esempio viene usato il documento XML seguente: [File XML di esempio: più ordini di acquisto in uno spazio dei nomi](sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim purchaseOrders As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim names As IEnumerable(Of XElement) = _  
            From el In purchaseOrders.<aw:PurchaseOrder>.<aw:Address>.<aw:Name> _  
            Select el  
        For Each e As XElement In names  
            Console.WriteLine(e)  
        Next  
    End Sub  
End Module  
```  
  
 Nell'esempio viene prodotto l'output seguente:  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Assi LINQ to XML (Visual Basic)](linq-to-xml-axes.md)
