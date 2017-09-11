---
title: 'Procedura: eseguire il Debug di set di risultati di Query vuoti (Visual Basic) | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: b242c90a-d2b8-4309-8a1e-e4e70736c727
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 85a0d070c415924ef116367b0202c01bef6d8ace
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-debug-empty-query-results-sets-visual-basic"></a><span data-ttu-id="ef2ba-102">Procedura: eseguire il Debug di set di risultati di Query vuoti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef2ba-102">How to: Debug Empty Query Results Sets (Visual Basic)</span></span>
<span data-ttu-id="ef2ba-103">Uno dei problemi più comuni che viene riscontrato durante l'esecuzione di query su alberi XML è che, se l'albero XML include uno spazio dei nomi predefinito, lo sviluppatore scrive talvolta la query come se il codice XML non fosse incluso in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ef2ba-103">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="ef2ba-104">Nel primo set di esempi riportati in questo argomento viene illustrato il tipico caricamento del codice XML in uno spazio dei nomi predefinito e l'esecuzione errata di query su tale codice.</span><span class="sxs-lookup"><span data-stu-id="ef2ba-104">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, and is queried improperly.</span></span>  
  
 <span data-ttu-id="ef2ba-105">Nel secondo set di esempi sono illustrate le correzioni necessarie da effettuare per poter eseguire query su codice XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ef2ba-105">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
 <span data-ttu-id="ef2ba-106">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="ef2ba-106">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef2ba-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef2ba-107">Example</span></span>  
 <span data-ttu-id="ef2ba-108">In questo esempio è illustrata la creazione di codice XML in uno spazio dei nomi e una query che restituisce un set di risultati vuoto.</span><span class="sxs-lookup"><span data-stu-id="ef2ba-108">This example shows creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns='http://www.adventure-works.com'>  
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
Console.WriteLine("Result set follows:")  
For Each el As XElement In c1  
    Console.WriteLine(el.Value)  
Next  
Console.WriteLine("End of result set")  
```  
  
 <span data-ttu-id="ef2ba-109">Il risultato ottenuto dall'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ef2ba-109">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="ef2ba-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="ef2ba-110">Example</span></span>  
 <span data-ttu-id="ef2ba-111">In questo esempio vengono illustrate la creazione di codice XML in uno spazio dei nomi, nonché una query codificata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ef2ba-111">This example shows creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="ef2ba-112">La soluzione consiste nel dichiarare e inizializzare uno spazio dei nomi globale predefinito.</span><span class="sxs-lookup"><span data-stu-id="ef2ba-112">The solution is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="ef2ba-113">In questo modo tutte le proprietà XML vengono inserite nello spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="ef2ba-113">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="ef2ba-114">Non è necessario apportare altre modifiche all'esempio per fare in modo che venga eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="ef2ba-114">No other modifications are required to the example to make it work properly.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
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
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ef2ba-115">Il risultato ottenuto dall'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="ef2ba-115">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef2ba-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef2ba-116">See Also</span></span>  
 [<span data-ttu-id="ef2ba-117">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef2ba-117">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
