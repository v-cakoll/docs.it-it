---
title: Ambito degli spazi dei nomi predefiniti in C#1
ms.date: 07/20/2015
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: 77345bfb2a4814c8cd38405c4481bea86fa84823
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613857"
---
# <a name="scope-of-default-namespaces-in-c"></a><span data-ttu-id="e7c5f-102">Ambito degli spazi dei nomi predefiniti in C#</span><span class="sxs-lookup"><span data-stu-id="e7c5f-102">Scope of Default Namespaces in C#</span></span>
<span data-ttu-id="e7c5f-103">Gli spazi dei nomi rappresentati nell'albero XML non sono inclusi nell'ambito delle query.</span><span class="sxs-lookup"><span data-stu-id="e7c5f-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="e7c5f-104">Se il codice XML è incluso in uno spazio dei nomi predefinito, è comunque necessario dichiarare una variabile <xref:System.Xml.Linq.XNamespace> e combinarla con il nome locale per creare un nome completo da usare nella query.</span><span class="sxs-lookup"><span data-stu-id="e7c5f-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="e7c5f-105">Uno dei problemi più comuni che viene riscontrato durante l'esecuzione di query su alberi XML è che, se l'albero XML include uno spazio dei nomi predefinito, lo sviluppatore scrive talvolta la query come se il codice XML non fosse incluso in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e7c5f-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="e7c5f-106">Nel primo set di esempi riportati in questo argomento viene illustrato il tipico caricamento del codice XML in uno spazio dei nomi predefinito e l'esecuzione errata di query su tale codice.</span><span class="sxs-lookup"><span data-stu-id="e7c5f-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="e7c5f-107">Nel secondo set di esempi sono illustrate le correzioni necessarie da effettuare per poter eseguire query su codice XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="e7c5f-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7c5f-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7c5f-108">Example</span></span>  
 <span data-ttu-id="e7c5f-109">In questo esempio vengono illustrate la creazione di codice XML in uno spazio dei nomi e una query che restituisce un set di risultati vuoto.</span><span class="sxs-lookup"><span data-stu-id="e7c5f-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7c5f-110">Codice</span><span class="sxs-lookup"><span data-stu-id="e7c5f-110">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="e7c5f-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="e7c5f-111">Comments</span></span>  
 <span data-ttu-id="e7c5f-112">Il risultato ottenuto dall'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e7c5f-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="e7c5f-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7c5f-113">Example</span></span>  
 <span data-ttu-id="e7c5f-114">In questo esempio vengono illustrate la creazione di codice XML in uno spazio dei nomi e una query codificata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e7c5f-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="e7c5f-115">Contrariamente all'esempio di codice errato precedente, l'approccio corretto in C# consiste nel dichiarare e inizializzare un oggetto <xref:System.Xml.Linq.XNamespace> e usarlo se si specificano oggetti <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="e7c5f-115">In contrast to the incorrectly coded example above, the correct approach when using C# is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="e7c5f-116">In questo caso l'argomento del metodo <xref:System.Xml.Linq.XElement.Elements%2A> è un oggetto <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="e7c5f-116">In this case, the argument to the <xref:System.Xml.Linq.XElement.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e7c5f-117">Codice</span><span class="sxs-lookup"><span data-stu-id="e7c5f-117">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="e7c5f-118">Commenti</span><span class="sxs-lookup"><span data-stu-id="e7c5f-118">Comments</span></span>  
 <span data-ttu-id="e7c5f-119">Il risultato ottenuto dall'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="e7c5f-119">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7c5f-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7c5f-120">See also</span></span>

- [<span data-ttu-id="e7c5f-121">Uso degli spazi dei nomi XML (C#)</span><span class="sxs-lookup"><span data-stu-id="e7c5f-121">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
