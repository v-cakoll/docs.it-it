---
title: 'Procedura: Generare un flusso di frammenti XML con accesso a informazioni di intestazione'
ms.date: 07/20/2015
ms.assetid: effd10df-87c4-4d7a-8a9a-1434d829dca5
ms.openlocfilehash: 8d0543ff5a772768292c0e3117f41bea9367d23a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397687"
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-visual-basic"></a><span data-ttu-id="d2359-102">Procedura: flusso di frammenti XML con accesso a informazioni di intestazione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2359-102">How to: Stream XML Fragments with Access to Header Information (Visual Basic)</span></span>
<span data-ttu-id="d2359-103">A volte è necessario leggere file XML arbitrariamente grandi e scrivere l'applicazione in modo tale che il footprint di memoria dell'applicazione sia prevedibile.</span><span class="sxs-lookup"><span data-stu-id="d2359-103">Sometimes you have to read arbitrarily large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="d2359-104">Se si tenta di popolare un albero XML con un file XML di grandi dimensioni, l'uso della memoria sarà proporzionale alla dimensione del file (ovvero, eccessivo).</span><span class="sxs-lookup"><span data-stu-id="d2359-104">If you attempt to populate an XML tree with a large XML file, your memory usage will be proportional to the size of the file—that is, excessive.</span></span> <span data-ttu-id="d2359-105">Pertanto, è necessario usare una tecnica di flusso in sostituzione.</span><span class="sxs-lookup"><span data-stu-id="d2359-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="d2359-106">Una delle opzioni disponibili consiste nello scrivere l'applicazione usando <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="d2359-106">One option is to write your application using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="d2359-107">Tuttavia, potrebbe essere necessario usare LINQ per eseguire una query sull'albero XML.</span><span class="sxs-lookup"><span data-stu-id="d2359-107">However, you might want to use LINQ to query the XML tree.</span></span> <span data-ttu-id="d2359-108">In questo caso, è possibile scrivere un metodo dell'asse personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d2359-108">If this is the case, you can write your own custom axis method.</span></span> <span data-ttu-id="d2359-109">Per ulteriori informazioni, vedere [procedura: scrivere un metodo dell'asse LINQ to XML (Visual Basic)](how-to-write-a-linq-to-xml-axis-method.md).</span><span class="sxs-lookup"><span data-stu-id="d2359-109">For more information, see [How to: Write a LINQ to XML Axis Method (Visual Basic)](how-to-write-a-linq-to-xml-axis-method.md).</span></span>  
  
 <span data-ttu-id="d2359-110">Per scrivere metodo dell'asse, scrivere un piccolo metodo che usa <xref:System.Xml.XmlReader> per leggere i nodi fino a raggiungere uno dei nodi di interesse.</span><span class="sxs-lookup"><span data-stu-id="d2359-110">To write your own axis method, you write a small method that uses the <xref:System.Xml.XmlReader> to read nodes until it reaches one of the nodes in which you are interested.</span></span> <span data-ttu-id="d2359-111">Il metodo chiama quindi <xref:System.Xml.Linq.XNode.ReadFrom%2A>, che legge da <xref:System.Xml.XmlReader> e crea un'istanza di un frammento XML.</span><span class="sxs-lookup"><span data-stu-id="d2359-111">The method then calls <xref:System.Xml.Linq.XNode.ReadFrom%2A>, which reads from the <xref:System.Xml.XmlReader> and instantiates an XML fragment.</span></span> <span data-ttu-id="d2359-112">È quindi possibile scrivere query LINQ sul metodo dell'asse personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d2359-112">You can then write LINQ queries on your custom axis method.</span></span>  
  
 <span data-ttu-id="d2359-113">Le tecniche di flusso sono maggiormente indicate nelle situazioni in cui è necessario elaborare solo una volta il documento di origine ed è possibile elaborare gli elementi in base all'ordine in cui sono riportati nel documento.</span><span class="sxs-lookup"><span data-stu-id="d2359-113">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="d2359-114">Determinati operatori di query standard, ad esempio <xref:System.Linq.Enumerable.OrderBy%2A>, scorrono l'origine, raccolgono tutti i dati, li ordinano e infine restituiscono il primo elemento nella sequenza.</span><span class="sxs-lookup"><span data-stu-id="d2359-114">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="d2359-115">Si noti che se si usa un operatore di query che materializza l'origine prima di restituire il primo elemento, non verrà mantenuto un footprint di memoria ridotto.</span><span class="sxs-lookup"><span data-stu-id="d2359-115">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2359-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="d2359-116">Example</span></span>  
 <span data-ttu-id="d2359-117">A volte il problema diventa più interessante.</span><span class="sxs-lookup"><span data-stu-id="d2359-117">Sometimes the problem gets just a little more interesting.</span></span> <span data-ttu-id="d2359-118">Nel documento XML seguente, il consumer del metodo dell'asse personalizzato deve conoscere anche il nome del cliente cui appartiene ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="d2359-118">In the following XML document, the consumer of your custom axis method also has to know the name of the customer that each item belongs to.</span></span>  
  
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
  
 <span data-ttu-id="d2359-119">L'approccio adottato in questo esempio prevede anche di cercare queste informazioni di intestazione, salvarle e quindi compilare un piccolo albero XML che contiene sia le informazioni di intestazione che i dettagli enumerati.</span><span class="sxs-lookup"><span data-stu-id="d2359-119">The approach that this example takes is to also watch for this header information, save the header information, and then build a small XML tree that contains both the header information and the detail that you are enumerating.</span></span> <span data-ttu-id="d2359-120">Il metodo dell'asse restituisce questo nuovo, piccolo albero XML.</span><span class="sxs-lookup"><span data-stu-id="d2359-120">The axis method then yields this new, small XML tree.</span></span> <span data-ttu-id="d2359-121">La query ha quindi accesso alle informazioni di intestazione oltre a quelle sui dettagli.</span><span class="sxs-lookup"><span data-stu-id="d2359-121">The query then has access to the header information as well as the detail information.</span></span>  
  
 <span data-ttu-id="d2359-122">Questo approccio prevede un footprint di memoria ridotto.</span><span class="sxs-lookup"><span data-stu-id="d2359-122">This approach has a small memory footprint.</span></span> <span data-ttu-id="d2359-123">Quando viene restituito un frammento XML, non viene mantenuto alcun riferimento al frammento precedente, che diventa disponibile per Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="d2359-123">As each detail XML fragment is yielded, no references are kept to the previous fragment, and it is available for garbage collection.</span></span> <span data-ttu-id="d2359-124">Si noti che con questa tecnica vengono creati molti oggetti temporanei sull'heap.</span><span class="sxs-lookup"><span data-stu-id="d2359-124">Note that this technique creates many short lived objects on the heap.</span></span>  
  
 <span data-ttu-id="d2359-125">Nell'esempio seguente viene illustrato come implementare e usare un metodo dell'asse personalizzato che genera un flusso di frammenti XML dal file specificato dall'URI.</span><span class="sxs-lookup"><span data-stu-id="d2359-125">The following example shows how to implement and use a custom axis method that streams XML fragments from the file specified by the URI.</span></span> <span data-ttu-id="d2359-126">Il metodo dell'asse personalizzato è stato scritto in modo tale da prevedere un documento contenente gli elementi `Customer`, `Name` e `Item`, disposti come nel documento `Source.xml` precedente.</span><span class="sxs-lookup"><span data-stu-id="d2359-126">This custom axis is specifically written such that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the above `Source.xml` document.</span></span> <span data-ttu-id="d2359-127">Si tratta di un'implementazione semplicistica.</span><span class="sxs-lookup"><span data-stu-id="d2359-127">It is a simplistic implementation.</span></span> <span data-ttu-id="d2359-128">Un'implementazione più solida sarebbe in grado di analizzare un documento non valido.</span><span class="sxs-lookup"><span data-stu-id="d2359-128">A more robust implementation would be prepared to parse an invalid document.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim xmlTree = <Root>  
                          <%=  
                              From el In New StreamCustomerItem("Source.xml")  
                              Let itemKey = CInt(el.<Key>.Value)  
                              Where itemKey >= 3 AndAlso itemKey <= 7  
                              Select <Item>  
                                         <Customer><%= el.Parent.<Name>.Value %></Customer>  
                                         <%= el.<Key> %>  
                                     </Item>  
                          %>  
                      </Root>  
  
        Console.WriteLine(xmlTree)  
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
  
 <span data-ttu-id="d2359-129">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="d2359-129">This code produces the following output:</span></span>  
  
```xml  
<Root>  
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
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2359-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2359-130">See also</span></span>

- [<span data-ttu-id="d2359-131">Programmazione LINQ to XML avanzata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2359-131">Advanced LINQ to XML Programming (Visual Basic)</span></span>](advanced-linq-to-xml-programming.md)
