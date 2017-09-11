---
title: 'Procedura: controllare i prefissi Namespace (Visual Basic) (LINQ to XML) | Documenti di Microsoft'
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
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 87db9e5384bee835ca4fde141765eabf9a7cfedb
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="a60cf-102">Procedura: controllare i prefissi dello spazio dei nomi (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="a60cf-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="a60cf-103">In questo argomento viene descritto come controllare i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a60cf-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a60cf-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a60cf-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a60cf-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a60cf-105">Description</span></span>  
 <span data-ttu-id="a60cf-106">In questo esempio vengono dichiarati due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="a60cf-106">This example declares two namespaces.</span></span> <span data-ttu-id="a60cf-107">Specifica che il `http://www.adventure-works.com` dello spazio dei nomi ha il prefisso `aw`e che il `www.fourthcoffee.com` dello spazio dei nomi ha il prefisso `fc`.</span><span class="sxs-lookup"><span data-stu-id="a60cf-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a60cf-108">Codice</span><span class="sxs-lookup"><span data-stu-id="a60cf-108">Code</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="a60cf-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="a60cf-109">Comments</span></span>  
 <span data-ttu-id="a60cf-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="a60cf-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a60cf-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a60cf-111">See Also</span></span>  
 [<span data-ttu-id="a60cf-112">Utilizzo di spazi dei nomi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a60cf-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
