---
title: 'Procedura: Controllo Namespace prefissi (Visual Basic) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 7e5a05d2fa93e61338f450d0a4d890fa94c04fd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855400"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="5496d-102">Procedura: Controllo Namespace prefissi (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="5496d-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="5496d-103">In questo argomento viene descritto come controllare i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5496d-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5496d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="5496d-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="5496d-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5496d-105">Description</span></span>  
 <span data-ttu-id="5496d-106">In questo esempio vengono dichiarati due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5496d-106">This example declares two namespaces.</span></span> <span data-ttu-id="5496d-107">Specifica che il `http://www.adventure-works.com` dello spazio dei nomi ha il prefisso `aw`e che le `www.fourthcoffee.com` dello spazio dei nomi ha il prefisso `fc`.</span><span class="sxs-lookup"><span data-stu-id="5496d-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5496d-108">Codice</span><span class="sxs-lookup"><span data-stu-id="5496d-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="5496d-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="5496d-109">Comments</span></span>  
 <span data-ttu-id="5496d-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="5496d-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5496d-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5496d-111">See also</span></span>

- [<span data-ttu-id="5496d-112">Utilizzo di spazi dei nomi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5496d-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
