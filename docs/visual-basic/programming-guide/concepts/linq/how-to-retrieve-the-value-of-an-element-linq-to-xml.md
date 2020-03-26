---
title: 'Procedura: recuperare il valore di un elemento (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
ms.openlocfilehash: b1a61091dc59b403c5d967609e8870492c24347f
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80248934"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a><span data-ttu-id="53487-102">Procedura: recuperare il valore di un elemento (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53487-102">How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="53487-103">In questo argomento viene illustrato come ottenere il valore degli elementi.</span><span class="sxs-lookup"><span data-stu-id="53487-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="53487-104">Questa operazione può essere eseguita in due modi.</span><span class="sxs-lookup"><span data-stu-id="53487-104">There are two main ways to do this.</span></span> <span data-ttu-id="53487-105">È possibile eseguire il cast di un oggetto <xref:System.Xml.Linq.XElement> o  <xref:System.Xml.Linq.XAttribute> nel tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="53487-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="53487-106">L'operatore di conversione esplicito converte quindi il contenuto dell'elemento o dell'attributo nel tipo specificato e lo assegna alla variabile.</span><span class="sxs-lookup"><span data-stu-id="53487-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="53487-107">In alternativa, è possibile usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> o <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="53487-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="53487-108">Con Visual Basic l'approccio migliore consiste nell'utilizzo della proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="53487-108">With Visual Basic, the best approach is to use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53487-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="53487-109">Example</span></span>  
 <span data-ttu-id="53487-110">Per recuperare il valore di un elemento, è sufficiente eseguire il cast dell'oggetto <xref:System.Xml.Linq.XElement> nel tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="53487-110">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="53487-111">È sempre possibile eseguire il cast di un elemento in una stringa, come segue:</span><span class="sxs-lookup"><span data-stu-id="53487-111">You can always cast an element to a string, as follows:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="53487-112">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="53487-112">This example produces the following output:</span></span>  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="53487-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="53487-113">Example</span></span>  
 <span data-ttu-id="53487-114">È anche possibile eseguire il cast di elementi in tipi diversi da stringa.</span><span class="sxs-lookup"><span data-stu-id="53487-114">You can also cast elements to types other than string.</span></span> <span data-ttu-id="53487-115">Ad esempio, se un elemento contiene un Integer, è possibile eseguirne il cast in `int`, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="53487-115">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 <span data-ttu-id="53487-116">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="53487-116">This example produces the following output:</span></span>  
  
```xml  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="53487-117">fornisce operatori di cast espliciti per i seguenti tipi di dati: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` e `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="53487-117">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="53487-118">fornisce gli stessi operatori di cast per gli oggetti <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="53487-118">provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53487-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="53487-119">Example</span></span>  
 <span data-ttu-id="53487-120">È possibile usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A> per recuperare il contenuto di un elemento:</span><span class="sxs-lookup"><span data-stu-id="53487-120">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="53487-121">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="53487-121">This example produces the following output:</span></span>  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="53487-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="53487-122">Example</span></span>  
 <span data-ttu-id="53487-123">A volte, si tenta di recuperare il valore di un elemento anche se non si è certi che esista.</span><span class="sxs-lookup"><span data-stu-id="53487-123">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="53487-124">In questo caso, quando si assegna l'elemento di `string` cui è stato eseguito il cast a un tipo nullable (uno o `Nothing`uno dei tipi di valore nullable in .NET Framework), se l'elemento non esiste, la variabile assegnata viene semplicemente impostata su .</span><span class="sxs-lookup"><span data-stu-id="53487-124">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable value types in the .NET Framework), if the element does not exist the assigned variable is just set to `Nothing`.</span></span> <span data-ttu-id="53487-125">Nel codice seguente viene dimostrato che quando non si è certi che l'elemento esista, è preferibile eseguire il cast anziché usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="53487-125">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
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
  
 <span data-ttu-id="53487-126">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="53487-126">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="53487-127">In generale, è possibile scrivere codice più semplice quando si usa il cast per recuperare il contenuto di elementi e attributi.</span><span class="sxs-lookup"><span data-stu-id="53487-127">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53487-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53487-128">See also</span></span>

- [<span data-ttu-id="53487-129">Assi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53487-129">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
