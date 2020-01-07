---
title: Come recuperare il valore di un elemento (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: 775e7282408910cc06b7d660d84cb6f80ef47949
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347422"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="8ddc2-102">Come recuperare il valore di un elemento (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="8ddc2-102">How to retrieve the value of an element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="8ddc2-103">In questo argomento viene illustrato come ottenere il valore degli elementi.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="8ddc2-104">Questa operazione può essere eseguita in due modi.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-104">There are two main ways to do this.</span></span> <span data-ttu-id="8ddc2-105">È possibile eseguire il cast di un oggetto <xref:System.Xml.Linq.XElement> o  <xref:System.Xml.Linq.XAttribute> nel tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="8ddc2-106">L'operatore di conversione esplicito converte quindi il contenuto dell'elemento o dell'attributo nel tipo specificato e lo assegna alla variabile.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="8ddc2-107">In alternativa, è possibile usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> o <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="8ddc2-108">Con C#, tuttavia, l'esecuzione del cast è in genere l'approccio migliore.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-108">With C#, however, casting is generally the better approach.</span></span> <span data-ttu-id="8ddc2-109">Se si esegue il cast dell'elemento o dell'attributo in un tipo nullable, sarà più semplice scrivere il codice quando si recupera il valore di un elemento (o attributo) che potrebbe o meno esistere.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-109">If you cast the element or attribute to a nullable type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="8ddc2-110">Tale comportamento è illustrato nell'ultimo esempio di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-110">The last example in this topic demonstrates this.</span></span> <span data-ttu-id="8ddc2-111">Tuttavia, non è possibile impostare il contenuto di un elemento tramite cast, operazione che è invece eseguibile tramite la proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-111">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ddc2-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ddc2-112">Example</span></span>  
 <span data-ttu-id="8ddc2-113">Per recuperare il valore di un elemento, è sufficiente eseguire il cast dell'oggetto <xref:System.Xml.Linq.XElement> nel tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-113">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="8ddc2-114">È sempre possibile eseguire il cast di un elemento in una stringa, come segue:</span><span class="sxs-lookup"><span data-stu-id="8ddc2-114">You can always cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="8ddc2-115">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8ddc2-115">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="8ddc2-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ddc2-116">Example</span></span>  
 <span data-ttu-id="8ddc2-117">È anche possibile eseguire il cast di elementi in tipi diversi da stringa.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-117">You can also cast elements to types other than string.</span></span> <span data-ttu-id="8ddc2-118">Ad esempio, se un elemento contiene un Integer, è possibile eseguirne il cast in `int`, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8ddc2-118">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="8ddc2-119">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8ddc2-119">This example produces the following output:</span></span>  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="8ddc2-120">fornisce operatori di cast espliciti per i seguenti tipi di dati: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` e `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-120">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="8ddc2-121">fornisce gli stessi operatori di cast per gli oggetti <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-121">provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ddc2-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ddc2-122">Example</span></span>  
 <span data-ttu-id="8ddc2-123">È possibile usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A> per recuperare il contenuto di un elemento:</span><span class="sxs-lookup"><span data-stu-id="8ddc2-123">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");   
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="8ddc2-124">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="8ddc2-124">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="8ddc2-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="8ddc2-125">Example</span></span>  
 <span data-ttu-id="8ddc2-126">A volte, si tenta di recuperare il valore di un elemento anche se non si è certi che esista.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-126">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="8ddc2-127">In questo caso, quando si assegna l'elemento sottoposto a cast a un tipo nullable (`string` o uno dei tipi nullable di .NET Framework), se l'elemento non esiste la variabile assegnata viene semplicemente impostata su `null`.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-127">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable types in the .NET Framework), if the element does not exist the assigned variable is just set to `null`.</span></span> <span data-ttu-id="8ddc2-128">Nel codice seguente viene dimostrato che quando non si è certi che l'elemento esista, è preferibile eseguire il cast anziché usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-128">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 <span data-ttu-id="8ddc2-129">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="8ddc2-129">This code produces the following output:</span></span>  
  
```output  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="8ddc2-130">In generale, è possibile scrivere codice più semplice quando si usa il cast per recuperare il contenuto di elementi e attributi.</span><span class="sxs-lookup"><span data-stu-id="8ddc2-130">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ddc2-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ddc2-131">See also</span></span>

- [<span data-ttu-id="8ddc2-132">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="8ddc2-132">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
