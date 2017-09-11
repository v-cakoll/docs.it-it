---
title: 'Procedura: eseguire una Query LINQ to XML tramite XPath (Visual Basic) | Documenti di Microsoft'
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
ms.assetid: e1f69a20-1efa-452d-9089-c472fa84b3d5
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 586182367ea26539384ea630dde301fe447915b8
ms.contentlocale: it-it
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-query-linq-to-xml-using-xpath-visual-basic"></a><span data-ttu-id="4d868-102">Procedura: eseguire una Query LINQ to XML tramite XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d868-102">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>
<span data-ttu-id="4d868-103">In questo argomento vengono presentati i metodi di estensione che consentono di eseguire una query su un albero XML usando XPath.</span><span class="sxs-lookup"><span data-stu-id="4d868-103">This topic introduces the extension methods that enable you to query an XML tree by using XPath.</span></span> <span data-ttu-id="4d868-104">Per informazioni dettagliate sull'utilizzo di questi metodi di estensione, vedere <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</xref:System.Xml.XPath.Extensions?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4d868-104">For detailed information about using these extension methods, see <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</span></span>  
  
 <span data-ttu-id="4d868-105">A meno che non esista un motivo molto specifico per eseguire query tramite XPATH, ad esempio l'uso esteso di codice legacy, è preferibile non usare XPATH con LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="4d868-105">Unless you have a very specific reason for querying using XPath, such as extensive use of legacy code, using XPath with LINQ to XML is not recommended.</span></span> <span data-ttu-id="4d868-106">Le query XPath non eseguirà nonché [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span><span class="sxs-lookup"><span data-stu-id="4d868-106">XPath queries will not perform as well as [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d868-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="4d868-107">Example</span></span>  
 <span data-ttu-id="4d868-108">Nell'esempio seguente viene creata un piccolo albero XML e viene utilizzato <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>per selezionare un set di elementi.</xref:System.Xml.XPath.Extensions.XPathSelectElements%2A></span><span class="sxs-lookup"><span data-stu-id="4d868-108">The following example creates a small XML tree and uses <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> to select a set of elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child1>2</Child1>  
        <Child1>3</Child1>  
        <Child2>4</Child2>  
        <Child2>5</Child2>  
        <Child2>6</Child2>  
    </Root>  
  
Dim list As IEnumerable(Of XElement) = root.XPathSelectElements("./Child2")  
For Each el As XElement In list  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="4d868-109">Questo esempio produce il seguente output:</span><span class="sxs-lookup"><span data-stu-id="4d868-109">This example produces the following output:</span></span>  
  
```  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d868-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d868-110">See Also</span></span>  
 [<span data-ttu-id="4d868-111">Tecniche di Query (LINQ to XML) avanzate (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d868-111">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)

