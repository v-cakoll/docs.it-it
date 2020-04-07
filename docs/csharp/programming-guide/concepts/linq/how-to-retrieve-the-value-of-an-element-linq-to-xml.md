---
title: Come recuperare il valore di un elemento (LINQ to XML) (C
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: c4bb78e937fe0de08242923cdd7cd638abf571c7
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805827"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="7eb4c-102">Come recuperare il valore di un elemento (LINQ to XML) (C</span><span class="sxs-lookup"><span data-stu-id="7eb4c-102">How to retrieve the value of an element (LINQ to XML) (C#)</span></span>

<span data-ttu-id="7eb4c-103">In questo articolo viene illustrato come ottenere il valore degli elementi.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-103">This article shows how to get the value of elements.</span></span> <span data-ttu-id="7eb4c-104">Ci sono due modi principali per ottenere il valore:</span><span class="sxs-lookup"><span data-stu-id="7eb4c-104">There are two main ways to get the value:</span></span>

- <span data-ttu-id="7eb4c-105">Eseguire <xref:System.Xml.Linq.XElement> il <xref:System.Xml.Linq.XAttribute> cast di un o an al tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-105">Cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="7eb4c-106">L'operatore di conversione esplicito converte quindi il contenuto dell'elemento o dell'attributo nel tipo specificato e lo assegna alla variabile.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span>

- <span data-ttu-id="7eb4c-107">Utilizzare <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> le <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> proprietà o .</span><span class="sxs-lookup"><span data-stu-id="7eb4c-107">Use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> or <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="7eb4c-108">È inoltre possibile impostare il valore utilizzando queste proprietà.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-108">You can also set the value using these properties.</span></span>

<span data-ttu-id="7eb4c-109">Con C , il cast è in genere l'approccio migliore.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-109">With C#, casting is generally the better approach.</span></span> <span data-ttu-id="7eb4c-110">Se si esegue il cast dell'elemento o dell'attributo su un tipo di valore nullable, il codice è più semplice da scrivere quando si recupera il valore di un elemento (o attributo) che potrebbe o meno esistere.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-110">If you cast the element or attribute to a nullable value type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="7eb4c-111">[L'ultimo esempio](#element-might-not-exist-example) in questo articolo dimostra che il cast è più semplice nel caso in cui l'elemento potrebbe non esistere.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-111">The [last example](#element-might-not-exist-example) in this article demonstrates that casting is simpler in the case where the element might not exist.</span></span> <span data-ttu-id="7eb4c-112">Tuttavia, non è possibile impostare il contenuto di un elemento tramite cast, operazione che è invece eseguibile tramite la proprietà <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-112">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="string-cast-example"></a><span data-ttu-id="7eb4c-113">Esempio di cast di stringhe</span><span class="sxs-lookup"><span data-stu-id="7eb4c-113">String cast example</span></span>  
 <span data-ttu-id="7eb4c-114">Per recuperare il valore di <xref:System.Xml.Linq.XElement> un elemento, eseguire il cast dell'oggetto al tipo desiderato.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-114">To retrieve the value of an element, cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="7eb4c-115">È possibile eseguire il cast di un elemento in una stringa, come indicato di seguito:You can cast an element to a string, as follows:</span><span class="sxs-lookup"><span data-stu-id="7eb4c-115">You can cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="7eb4c-116">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7eb4c-116">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="integer-cast-example"></a><span data-ttu-id="7eb4c-117">Esempio di cast di IntegerInteger</span><span class="sxs-lookup"><span data-stu-id="7eb4c-117">Integer cast example</span></span>  
 <span data-ttu-id="7eb4c-118">È anche possibile eseguire il cast di elementi in tipi diversi da stringa.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-118">You can also cast elements to types other than string.</span></span> <span data-ttu-id="7eb4c-119">Ad esempio, se un elemento contiene un Integer, è possibile eseguirne il cast in `int`, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="7eb4c-119">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="7eb4c-120">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7eb4c-120">This example produces the following output:</span></span>  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="7eb4c-121">fornisce operatori di cast espliciti per i seguenti tipi di dati: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` e `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-121">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="7eb4c-122">fornisce gli stessi operatori di cast per gli oggetti <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-122">provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="value-property-example"></a><span data-ttu-id="7eb4c-123">Esempio di proprietà Value</span><span class="sxs-lookup"><span data-stu-id="7eb4c-123">Value property example</span></span>  
 <span data-ttu-id="7eb4c-124">È possibile usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A> per recuperare il contenuto di un elemento:</span><span class="sxs-lookup"><span data-stu-id="7eb4c-124">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="7eb4c-125">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="7eb4c-125">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="element-might-not-exist-example"></a><span data-ttu-id="7eb4c-126">L'elemento potrebbe non esistere nell'esempio</span><span class="sxs-lookup"><span data-stu-id="7eb4c-126">Element might not exist example</span></span>
 <span data-ttu-id="7eb4c-127">A volte si tenta di recuperare il valore di un elemento anche se non si è sicuri se esiste.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-127">Sometimes you try to retrieve the value of an element even though you're not sure if it exists.</span></span> <span data-ttu-id="7eb4c-128">In questo caso, quando si assegna l'elemento di cui è stato eseguito il cast a un `null`tipo di riferimento nullable o a un tipo di valore nullable, se l'elemento non esiste, la variabile assegnata viene impostata su .</span><span class="sxs-lookup"><span data-stu-id="7eb4c-128">In this case, when you assign the casted element to a nullable reference type or nullable value type, if the element does not exist, the assigned variable is set to `null`.</span></span> <span data-ttu-id="7eb4c-129">Nel codice seguente viene dimostrato che quando non si è certi che l'elemento esista, è preferibile eseguire il cast anziché usare la proprietà <xref:System.Xml.Linq.XElement.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-129">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
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
  
 <span data-ttu-id="7eb4c-130">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="7eb4c-130">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="7eb4c-131">In generale, è possibile scrivere codice più semplice quando si usa il cast per recuperare il contenuto di elementi e attributi.</span><span class="sxs-lookup"><span data-stu-id="7eb4c-131">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eb4c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7eb4c-132">See also</span></span>

- [<span data-ttu-id="7eb4c-133">Assi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="7eb4c-133">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
