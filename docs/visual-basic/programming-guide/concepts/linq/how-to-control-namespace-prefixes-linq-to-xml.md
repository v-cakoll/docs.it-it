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
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a>Procedura: Prefissi dello spazio dei nomi del controllo (Visual Basic) (LINQ to XML)
In questo argomento viene descritto come controllare i prefissi di spazio dei nomi.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>DESCRIZIONE  
 In questo esempio vengono dichiarati due spazi dei nomi. Specifica `http://www.adventure-works.com` che lo spazio dei nomi ha il `aw`prefisso e che lo `www.fourthcoffee.com` spazio dei nomi ha il `fc`prefisso.  
  
### <a name="code"></a>Codice  
  
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
  
### <a name="comments"></a>Commenti  
 Questo esempio produce il seguente output:  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica degli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
