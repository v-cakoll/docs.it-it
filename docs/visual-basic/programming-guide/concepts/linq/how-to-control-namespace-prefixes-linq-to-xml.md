---
title: 'Procedura: Prefissi dello spazio dei nomi del controllo (Visual Basic) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 2b89b49aa76df526c08143cad49685386ffd5e7c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "68709827"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="dbe55-102">Procedura: Prefissi dello spazio dei nomi del controllo (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="dbe55-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="dbe55-103">In questo argomento viene descritto come controllare i prefissi di spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dbe55-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbe55-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="dbe55-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="dbe55-105">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="dbe55-105">Description</span></span>  
 <span data-ttu-id="dbe55-106">In questo esempio vengono dichiarati due spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="dbe55-106">This example declares two namespaces.</span></span> <span data-ttu-id="dbe55-107">Specifica `http://www.adventure-works.com` che lo spazio dei nomi ha il `aw`prefisso e che lo `www.fourthcoffee.com` spazio dei nomi ha il `fc`prefisso.</span><span class="sxs-lookup"><span data-stu-id="dbe55-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="dbe55-108">Codice</span><span class="sxs-lookup"><span data-stu-id="dbe55-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="dbe55-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="dbe55-109">Comments</span></span>  
 <span data-ttu-id="dbe55-110">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="dbe55-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dbe55-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbe55-111">See also</span></span>

- [<span data-ttu-id="dbe55-112">Panoramica degli spazi dei nomi (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dbe55-112">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
