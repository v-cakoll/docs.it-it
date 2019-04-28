---
title: 'Procedura: Scrivere query in XML negli spazi dei nomi (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: 4efa1de254a0264752514c5ae6e601a66fa56f95
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614830"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a><span data-ttu-id="ed9cc-102">Procedura: Scrivere query in XML negli spazi dei nomi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed9cc-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>
<span data-ttu-id="ed9cc-103">Per scrivere una query su XML inclusa in uno spazio dei nomi, è necessario usare oggetti <xref:System.Xml.Linq.XName> con lo spazio dei nomi corretto.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="ed9cc-104">In Visual Basic, l'approccio più comune consiste nel definire uno spazio dei nomi globale, quindi usare valori letterali e proprietà XML che usano lo spazio dei nomi globale.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-104">In Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="ed9cc-105">È possibile definire uno spazio dei nomi globale predefinito, nel qual caso gli elementi dei valori letterali XML saranno inclusi nello spazio dei nomi per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-105">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="ed9cc-106">In alternativa, è possibile definire uno spazio dei nomi globale con un prefisso e quindi usare il prefisso come richiesto nei valori letterali e nelle proprietà XML.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-106">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals, and in XML properties.</span></span> <span data-ttu-id="ed9cc-107">Come con altri tipi di XML, gli attributi non sono mai inclusi in alcuno spazio dei nomi per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-107">As with other forms of XML, attributes are always in no namespace by default.</span></span>  
  
 <span data-ttu-id="ed9cc-108">Nel primo set di esempi in questo argomento è illustrato come creare un albero XML in uno spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-108">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="ed9cc-109">Nel secondo set viene illustrato come creare un albero XML in uno spazio dei nomi con un prefisso.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-109">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed9cc-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed9cc-110">Example</span></span>  
 <span data-ttu-id="ed9cc-111">Nell'esempio seguente viene creato un albero XML incluso in uno spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-111">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="ed9cc-112">Viene quindi recuperata una raccolta di elementi.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-112">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ed9cc-113">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="ed9cc-113">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="ed9cc-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="ed9cc-114">Example</span></span>  
 <span data-ttu-id="ed9cc-115">In Visual Basic, tuttavia, la scrittura di query in un albero XML che usa uno spazio dei nomi con un prefisso, è piuttosto diversa dall'esecuzione di query in un albero XML con uno spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-115">In Visual Basic, however, writing queries on an XML tree that uses a namespace with a prefix is quite different from querying an XML tree in a default namespace.</span></span> <span data-ttu-id="ed9cc-116">Lo spazio dei nomi con un prefisso viene in genere importato usando l'istruzione `Imports`.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-116">Typically you use the `Imports` statement to import the namespace with a prefix.</span></span> <span data-ttu-id="ed9cc-117">Il prefisso viene quindi usato nei nomi di elementi e attributi quando si crea l'albero XML.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-117">You then use the prefix in the element and attribute names when you construct the XML tree.</span></span> <span data-ttu-id="ed9cc-118">Il prefisso viene inoltre usato durante l'esecuzione di query su un albero XML tramite proprietà XML.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-118">You also use the prefix when querying an XML tree using XML properties.</span></span>  
  
 <span data-ttu-id="ed9cc-119">Nell'esempio seguente viene creato un albero XML incluso in uno spazio dei nomi con un prefisso.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-119">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="ed9cc-120">Viene quindi recuperata una raccolta di elementi.</span><span class="sxs-lookup"><span data-stu-id="ed9cc-120">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ed9cc-121">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="ed9cc-121">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed9cc-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed9cc-122">See also</span></span>

- [<span data-ttu-id="ed9cc-123">Utilizzo di spazi dei nomi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ed9cc-123">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
