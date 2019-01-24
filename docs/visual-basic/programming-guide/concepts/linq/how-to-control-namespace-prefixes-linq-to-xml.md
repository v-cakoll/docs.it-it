---
title: 'Procedura: Controllo Namespace prefissi (Visual Basic) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 91117307caf7e55bd8b512fbd841760616f0b2c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623742"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="110d8-102">Procedura: Controllo Namespace prefissi (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="110d8-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="110d8-103">In questo argomento viene descritto come controllare i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="110d8-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="110d8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="110d8-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="110d8-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="110d8-105">Description</span></span>  
 <span data-ttu-id="110d8-106">In questo esempio vengono dichiarati due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="110d8-106">This example declares two namespaces.</span></span> <span data-ttu-id="110d8-107">Specifica che il `http://www.adventure-works.com` dello spazio dei nomi ha il prefisso `aw`e che le `www.fourthcoffee.com` dello spazio dei nomi ha il prefisso `fc`.</span><span class="sxs-lookup"><span data-stu-id="110d8-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="110d8-108">Codice</span><span class="sxs-lookup"><span data-stu-id="110d8-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="110d8-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="110d8-109">Comments</span></span>  
 <span data-ttu-id="110d8-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="110d8-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="110d8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="110d8-111">See also</span></span>
- [<span data-ttu-id="110d8-112">Utilizzo di spazi dei nomi XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="110d8-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
