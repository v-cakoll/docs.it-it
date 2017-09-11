---
title: 'Procedura: trovare discendenti di un elemento figlio (XPath-LINQ to XML) (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: a958af40-f754-4409-85f9-7746978d4cb3
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 7cefc078e22e5d2922f7f31c5ea08ae44f1bb8c0
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="26059-102">Procedura: trovare discendenti di un elemento figlio (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26059-102">How to: Find Descendants of a Child Element (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="26059-103">In questo argomento viene illustrato come ottenere gli elementi discendenti di un elemento figlio con un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="26059-103">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="26059-104">L'espressione XPath è:</span><span class="sxs-lookup"><span data-stu-id="26059-104">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="26059-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="26059-105">Example</span></span>  
 <span data-ttu-id="26059-106">In questo esempio sono simulati i problemi di estrazione di testo da una rappresentazione XML di un documento di elaborazione testi.</span><span class="sxs-lookup"><span data-stu-id="26059-106">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="26059-107">Vengono dapprima selezionati tutti gli elementi `Paragraph` e quindi tutti gli elementi discendenti `Text` di ogni elemento `Paragraph`.</span><span class="sxs-lookup"><span data-stu-id="26059-107">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="26059-108">Gli elementi discendenti `Text` dell'elemento `Comment` non vengono selezionati.</span><span class="sxs-lookup"><span data-stu-id="26059-108">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Paragraph>  
            <Text>This is the start of</Text>  
        </Paragraph>  
        <Comment>  
            <Text>This comment is not part of the paragraph text.</Text>  
        </Comment>  
        <Paragraph>  
            <Annotation Emphasis='true'>  
                <Text> a sentence.</Text>  
            </Annotation>  
        </Paragraph>  
        <Paragraph>  
            <Text>  This is a second sentence.</Text>  
        </Paragraph>  
    </Root>  
  
' LINQ to XML query  
Dim str1 As String = _  
    root.<Paragraph>...<Text>.Select(Function(ByVal s) s.Value). _  
    Aggregate( _  
        New StringBuilder(), _  
        Function(ByVal s, ByVal i) s.Append(i), _  
        Function(ByVal s) s.ToString())  
  
' XPath expression  
Dim str2 As String = DirectCast(root.XPathEvaluate("./Paragraph//Text/text()"), IEnumerable) _  
    .Cast(Of XText)().Select(Function(ByVal s) s.Value) _  
    .Aggregate( _  
        New StringBuilder(), _  
        Function(ByVal s, ByVal i) s.Append(i), _  
        Function(ByVal s) s.ToString())  
  
If str1 = str2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(str2)  
```  
  
 <span data-ttu-id="26059-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="26059-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  
## <a name="see-also"></a><span data-ttu-id="26059-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26059-110">See Also</span></span>  
 [<span data-ttu-id="26059-111">LINQ to XML per gli utenti di XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26059-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

