---
title: 'Procedura: eseguire la trasformazione del flusso di documenti XML di grandi dimensioni'
ms.date: 07/20/2015
ms.assetid: 3d954cc9-4b3c-4b47-8132-ff7541cff53b
ms.openlocfilehash: f5e6063f0a850c03a605d75b0cbdc0bf9e03b325
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "78267015"
---
# <a name="how-to-perform-streaming-transform-of-large-xml-documents-visual-basic"></a><span data-ttu-id="c47c5-102">Procedura: eseguire la trasformazione di flusso di documenti XML di grandi dimensioni (Visual Basic)How to: Perform Streaming Transform of Large XML Documents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c47c5-102">How to: Perform Streaming Transform of Large XML Documents (Visual Basic)</span></span>
<span data-ttu-id="c47c5-103">A volte è necessario trasformare file XML di grandi dimensioni e scrivere l'applicazione in modo tale che il footprint di memoria dell'applicazione sia prevedibile.</span><span class="sxs-lookup"><span data-stu-id="c47c5-103">Sometimes you have to transform large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="c47c5-104">Se si tenta di popolare un albero XML con un file XML molto grande, l'uso della memoria sarà proporzionale alla dimensione del file (ovvero, eccessivo).</span><span class="sxs-lookup"><span data-stu-id="c47c5-104">If you try to populate an XML tree with a very large XML file, your memory usage will be proportional to the size of the file (that is, excessive).</span></span> <span data-ttu-id="c47c5-105">Pertanto, è necessario usare una tecnica di flusso in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="c47c5-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="c47c5-106">Le tecniche di flusso sono maggiormente indicate nelle situazioni in cui è necessario elaborare solo una volta il documento di origine ed è possibile elaborare gli elementi in base all'ordine in cui sono riportati nel documento.</span><span class="sxs-lookup"><span data-stu-id="c47c5-106">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="c47c5-107">Determinati operatori di query standard, ad esempio <xref:System.Linq.Enumerable.OrderBy%2A>, scorrono l'origine, raccolgono tutti i dati, li ordinano e infine restituiscono il primo elemento nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="c47c5-107">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="c47c5-108">Si noti che se si usa un operatore di query che materializza l'origine prima di restituire il primo elemento, non verrà mantenuto un footprint di memoria ridotto per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c47c5-108">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint for your application.</span></span>  
  
 <span data-ttu-id="c47c5-109">Anche se si utilizza la tecnica descritta in Procedura: eseguire il flusso di frammenti XML con accesso alle informazioni di [intestazione (Visual Basic),](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md)se si tenta di assemblare una struttura ad albero XML contenente il documento trasformato, l'utilizzo della memoria sarà troppo elevato.</span><span class="sxs-lookup"><span data-stu-id="c47c5-109">Even if you use the technique described in [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md), if you try to assemble an XML tree that contains the transformed document, memory usage will be too great.</span></span>  
  
 <span data-ttu-id="c47c5-110">Sono disponibili due approcci principali:</span><span class="sxs-lookup"><span data-stu-id="c47c5-110">There are two main approaches.</span></span> <span data-ttu-id="c47c5-111">il primo consiste nell'usare le caratteristiche di elaborazione posticipata di <xref:System.Xml.Linq.XStreamingElement>.</span><span class="sxs-lookup"><span data-stu-id="c47c5-111">One approach is to use the deferred processing characteristics of <xref:System.Xml.Linq.XStreamingElement>.</span></span> <span data-ttu-id="c47c5-112">L'altro prevede la creazione di un oggetto <xref:System.Xml.XmlWriter> e l'uso delle funzionalità di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per scrivere elementi in un oggetto <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="c47c5-112">Another approach is to create an <xref:System.Xml.XmlWriter>, and use the capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="c47c5-113">In questo argomento vengono descritti entrambi gli approcci.</span><span class="sxs-lookup"><span data-stu-id="c47c5-113">This topic demonstrates both approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c47c5-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="c47c5-114">Example</span></span>  
 <span data-ttu-id="c47c5-115">L'esempio seguente si basa sull'esempio in Procedura: eseguire il flusso di [frammenti XML con accesso alle informazioni di intestazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span><span class="sxs-lookup"><span data-stu-id="c47c5-115">The following example builds on the example in [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>  
  
 <span data-ttu-id="c47c5-116">In questo esempio vengono usate le funzionalità di esecuzione posticipata di <xref:System.Xml.Linq.XStreamingElement> per generare il flusso di output.</span><span class="sxs-lookup"><span data-stu-id="c47c5-116">This example uses the deferred execution capabilities of <xref:System.Xml.Linq.XStreamingElement> to stream the output.</span></span> <span data-ttu-id="c47c5-117">È possibile trasformare un documento di dimensioni molto grandi mantenendo un footprint di memoria ridotto.</span><span class="sxs-lookup"><span data-stu-id="c47c5-117">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="c47c5-118">Si noti che il metodo dell'asse personalizzato (`StreamCustomerItem`) è stato scritto in modo tale da prevedere un documento contenente elementi `Customer`, `Name` e `Item`, disposti come nel documento Source.xml seguente.</span><span class="sxs-lookup"><span data-stu-id="c47c5-118">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="c47c5-119">Tuttavia, un'implementazione più solida sarebbe in grado di analizzare un documento non valido.</span><span class="sxs-lookup"><span data-stu-id="c47c5-119">A more robust implementation, however, would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="c47c5-120">Il documento seguente, Source.xml, è il documento di origine:</span><span class="sxs-lookup"><span data-stu-id="c47c5-120">The following is the source document, Source.xml:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
```vb  
Module Module1  
    Sub Main()  
        Dim root = New XStreamingElement("Root",  
            From el In New StreamCustomerItem("Source.xml")  
            Select <Item>  
                       <Customer><%= el.Parent.<Name>.Value %></Customer>  
                       <%= el.<Key> %>  
                   </Item>  
            )  
        root.Save("Test.xml")  
        Console.WriteLine(My.Computer.FileSystem.ReadAllText("Test.xml"))  
    End Sub  
End Module  
  
Public Class StreamCustomerItem  
    Implements IEnumerable(Of XElement)  
  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamCustomerItemEnumerator(_uri)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamCustomerItemEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _customerName As String  
    Private _reader As Xml.XmlReader  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
        _reader = Xml.XmlReader.Create(_uri)  
        _reader.MoveToContent()  
    End Sub  
  
    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current  
        Get  
            Return _current  
        End Get  
    End Property  
  
    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current  
        Get  
            Return Me.Current  
        End Get  
    End Property  
  
    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext  
        Dim item As XElement  
        Dim name As XElement  
  
        ' Parse the file, save header information when encountered, and return the  
        ' current Item XElement.  
  
        ' loop through Customer elements  
        While _reader.Read()  
            If _reader.NodeType = Xml.XmlNodeType.Element Then  
                Select Case _reader.Name  
                    Case "Customer"  
                        ' move to Name element  
                        While _reader.Read()  
  
                            If _reader.NodeType = Xml.XmlNodeType.Element AndAlso  
                                _reader.Name = "Name" Then  
  
                                name = TryCast(XElement.ReadFrom(_reader), XElement)  
                                _customerName = If(name IsNot Nothing, name.Value, "")  
                                Exit While  
                            End If  
  
                        End While  
                    Case "Item"  
                        item = TryCast(XElement.ReadFrom(_reader), XElement)  
                        Dim tempRoot = <Root>  
                                           <Name><%= _customerName %></Name>  
                                           <%= item %>  
                                       </Root>  
                        _current = item  
                        Return True  
                End Select  
            End If  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_uri)  
        _reader.MoveToContent()  
    End Sub  
  
#Region "IDisposable Support"  
    Private disposedValue As Boolean ' To detect redundant calls  
  
    ' IDisposable  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposedValue Then  
            If disposing Then  
                _reader.Close()  
            End If  
        End If  
        Me.disposedValue = True  
    End Sub  
  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
#End Region  
  
End Class  
```  
  
 <span data-ttu-id="c47c5-121">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c47c5-121">This code produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="c47c5-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="c47c5-122">Example</span></span>  
 <span data-ttu-id="c47c5-123">L'esempio seguente si basa anche sull'esempio in Procedura: eseguire il flusso di frammenti XML con accesso alle informazioni di [intestazione (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span><span class="sxs-lookup"><span data-stu-id="c47c5-123">The following example also builds on the example in [How to: Stream XML Fragments with Access to Header Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>  
  
 <span data-ttu-id="c47c5-124">In questo esempio viene usata la funzionalità di [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] per scrivere elementi in <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="c47c5-124">This example uses the capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="c47c5-125">È possibile trasformare un documento di dimensioni molto grandi mantenendo un footprint di memoria ridotto.</span><span class="sxs-lookup"><span data-stu-id="c47c5-125">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="c47c5-126">Si noti che il metodo dell'asse personalizzato (`StreamCustomerItem`) è stato scritto in modo tale da prevedere un documento contenente elementi `Customer`, `Name` e `Item`, disposti come nel documento Source.xml seguente.</span><span class="sxs-lookup"><span data-stu-id="c47c5-126">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="c47c5-127">Tuttavia, un'implementazione più affidabile convaliderebbe il documento di origine con uno schema XSD oppure verrebbe preparata per analizzare un documento non valido.</span><span class="sxs-lookup"><span data-stu-id="c47c5-127">A more robust implementation, however, would either validate the source document with an XSD, or would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="c47c5-128">In questo esempio viene usato lo stesso documento di origine, Source.xml, dell'esempio precedente in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="c47c5-128">This example uses the same source document, Source.xml, as the previous example in this topic.</span></span> <span data-ttu-id="c47c5-129">Viene inoltre prodotto esattamente lo stesso output.</span><span class="sxs-lookup"><span data-stu-id="c47c5-129">It also produces exactly the same output.</span></span>  
  
 <span data-ttu-id="c47c5-130">Per generare il flusso di output XML, è preferibile usare <xref:System.Xml.Linq.XStreamingElement> anziché scrivere in <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="c47c5-130">Using <xref:System.Xml.Linq.XStreamingElement> for streaming the output XML is preferred over writing to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim srcTree =  
            From el In New StreamCustomerItem("Source.xml")  
            Select <Item>  
                       <Customer><%= el.Parent.<Name>.Value %></Customer>  
                       <%= el.<Key> %>  
                   </Item>  
  
        Dim xws = New Xml.XmlWriterSettings()  
        xws.OmitXmlDeclaration = True  
        xws.Indent = True  
        Using xw = Xml.XmlWriter.Create("Output.xml", xws)  
            xw.WriteStartElement("Root")  
            For Each el In srcTree  
                el.WriteTo(xw)  
            Next  
            xw.WriteEndElement()  
        End Using  
  
        Dim s = My.Computer.FileSystem.ReadAllText("Output.xml")  
        Console.WriteLine(s)  
    End Sub  
End Module  
  
Public Class StreamCustomerItem  
    Implements IEnumerable(Of XElement)  
  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamCustomerItemEnumerator(_uri)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamCustomerItemEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _customerName As String  
    Private _reader As Xml.XmlReader  
    Private _uri As String  
  
    Public Sub New(ByVal uri As String)  
        _uri = uri  
        _reader = Xml.XmlReader.Create(_uri)  
        _reader.MoveToContent()  
    End Sub  
  
    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current  
        Get  
            Return _current  
        End Get  
    End Property  
  
    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current  
        Get  
            Return Me.Current  
        End Get  
    End Property  
  
    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext  
        Dim item As XElement  
        Dim name As XElement  
  
        ' Parse the file, save header information when encountered, and return the  
        ' current Item XElement.  
  
        ' loop through Customer elements  
        While _reader.Read()  
            If _reader.NodeType = Xml.XmlNodeType.Element Then  
                Select Case _reader.Name  
                    Case "Customer"  
                        ' move to Name element  
                        While _reader.Read()  
  
                            If _reader.NodeType = Xml.XmlNodeType.Element AndAlso  
                                _reader.Name = "Name" Then  
  
                                name = TryCast(XElement.ReadFrom(_reader), XElement)  
                                _customerName = If(name IsNot Nothing, name.Value, "")  
                                Exit While  
                            End If  
  
                        End While  
                    Case "Item"  
                        item = TryCast(XElement.ReadFrom(_reader), XElement)  
                        Dim tempRoot = <Root>  
                                           <Name><%= _customerName %></Name>  
                                           <%= item %>  
                                       </Root>  
                        _current = item  
                        Return True  
                End Select  
            End If  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_uri)  
        _reader.MoveToContent()  
    End Sub  
  
#Region "IDisposable Support"  
    Private disposedValue As Boolean ' To detect redundant calls  
  
    ' IDisposable  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposedValue Then  
            If disposing Then  
                _reader.Close()  
            End If  
        End If  
        Me.disposedValue = True  
    End Sub  
  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
#End Region  
  
End Class  
```  
  
 <span data-ttu-id="c47c5-131">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c47c5-131">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c47c5-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c47c5-132">See also</span></span>

- [<span data-ttu-id="c47c5-133">Programmazione LINQ to XML avanzata (Visual Basic)Advanced LINQ to XML Programming (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c47c5-133">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
