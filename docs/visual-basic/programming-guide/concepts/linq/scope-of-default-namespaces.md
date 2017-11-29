---
title: Ambito degli spazi dei nomi predefinito in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3aaf5395f1216b0cb56f2d1f003e42ed30790012
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="41b7f-102">Ambito degli spazi dei nomi predefinito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41b7f-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="41b7f-103">Gli spazi dei nomi rappresentati nell'albero XML non sono inclusi nell'ambito delle query.</span><span class="sxs-lookup"><span data-stu-id="41b7f-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="41b7f-104">Se il codice XML è incluso in uno spazio dei nomi predefinito, è comunque necessario dichiarare una variabile <xref:System.Xml.Linq.XNamespace> e combinarla con il nome locale per creare un nome completo da usare nella query.</span><span class="sxs-lookup"><span data-stu-id="41b7f-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="41b7f-105">Uno dei problemi più comuni che viene riscontrato durante l'esecuzione di query su alberi XML è che, se l'albero XML include uno spazio dei nomi predefinito, lo sviluppatore scrive talvolta la query come se il codice XML non fosse incluso in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="41b7f-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="41b7f-106">Nel primo set di esempi riportati in questo argomento viene illustrato il tipico caricamento del codice XML in uno spazio dei nomi predefinito e l'esecuzione errata di query su tale codice.</span><span class="sxs-lookup"><span data-stu-id="41b7f-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="41b7f-107">Nel secondo set di esempi sono illustrate le correzioni necessarie da effettuare per poter eseguire query su codice XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="41b7f-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41b7f-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="41b7f-108">Example</span></span>  
 <span data-ttu-id="41b7f-109">In questo esempio vengono illustrate la creazione di codice XML in uno spazio dei nomi e una query che restituisce un set di risultati vuoto.</span><span class="sxs-lookup"><span data-stu-id="41b7f-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="41b7f-110">Codice</span><span class="sxs-lookup"><span data-stu-id="41b7f-110">Code</span></span>  
  
```vb  
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
  
### <a name="comments"></a><span data-ttu-id="41b7f-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="41b7f-111">Comments</span></span>  
 <span data-ttu-id="41b7f-112">Il risultato ottenuto dall'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="41b7f-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="41b7f-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="41b7f-113">Example</span></span>  
 <span data-ttu-id="41b7f-114">In questo esempio vengono illustrate la creazione di codice XML in uno spazio dei nomi e una query codificata correttamente.</span><span class="sxs-lookup"><span data-stu-id="41b7f-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="41b7f-115">Contrariamente all'esempio di codice errato precedente, l'approccio corretto quando si utilizza Visual Basic consiste nel dichiarare e inizializzare uno spazio dei nomi globale predefinito.</span><span class="sxs-lookup"><span data-stu-id="41b7f-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="41b7f-116">In questo modo tutte le proprietà XML vengono inserite nello spazio dei nomi predefinito.</span><span class="sxs-lookup"><span data-stu-id="41b7f-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="41b7f-117">Non è necessario apportare altre modifiche all'esempio per fare in modo che venga eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="41b7f-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="41b7f-118">Codice</span><span class="sxs-lookup"><span data-stu-id="41b7f-118">Code</span></span>  
  
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
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="41b7f-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="41b7f-119">Comments</span></span>  
 <span data-ttu-id="41b7f-120">Il risultato ottenuto dall'esempio è il seguente:</span><span class="sxs-lookup"><span data-stu-id="41b7f-120">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="41b7f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41b7f-121">See Also</span></span>  
 [<span data-ttu-id="41b7f-122">Utilizzo di spazi dei nomi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41b7f-122">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
