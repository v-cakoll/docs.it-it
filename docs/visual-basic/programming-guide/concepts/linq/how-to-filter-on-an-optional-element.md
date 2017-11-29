---
title: 'Procedura: filtro su un elemento facoltativo (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a74b76ad-6889-4185-a189-d6ef2c63841e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 32183a26a02640c655030eff18d62329fb1c125a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-filter-on-an-optional-element-visual-basic"></a><span data-ttu-id="19cb1-102">Procedura: filtro su un elemento facoltativo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19cb1-102">How to: Filter on an Optional Element (Visual Basic)</span></span>
<span data-ttu-id="19cb1-103">Talvolta si desidera filtrare in base a un elemento anche se non si è certi che esista nel documento XML.</span><span class="sxs-lookup"><span data-stu-id="19cb1-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="19cb1-104">La ricerca deve essere eseguita in modo che se l'elemento specifico non include l'elemento figlio, non viene generata un'eccezione di riferimento null quando si applica un filtro sull'elemento.</span><span class="sxs-lookup"><span data-stu-id="19cb1-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="19cb1-105">Nell'esempio seguente l'elemento `Child5` non contiene un elemento figlio `Type`, tuttavia la query viene comunque eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="19cb1-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19cb1-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cb1-106">Example</span></span>  
 <span data-ttu-id="19cb1-107">In questo esempio viene usato il metodo di estensione <xref:System.Xml.Linq.Extensions.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="19cb1-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1>  
            <Text>Child One Text</Text>  
            <Type Value="Yes"/>  
        </Child1>  
        <Child2>  
            <Text>Child Two Text</Text>  
            <Type Value="Yes"/>  
        </Child2>  
        <Child3>  
            <Text>Child Three Text</Text>  
            <Type Value="No"/>  
        </Child3>  
        <Child4>  
            <Text>Child Four Text</Text>  
            <Type Value="Yes"/>  
        </Child4>  
        <Child5>  
            <Text>Child Five Text</Text>  
        </Child5>  
    </Root>  
Dim cList As IEnumerable(Of String) = _  
    From typeElement In root.Elements().<Type> _  
    Where typeElement.@Value = "Yes" _  
    Select typeElement.Parent.<Text>.Value  
Dim str As String  
For Each str In cList  
    Console.WriteLine(str)  
Next  
```  
  
 <span data-ttu-id="19cb1-108">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="19cb1-108">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="19cb1-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="19cb1-109">Example</span></span>  
 <span data-ttu-id="19cb1-110">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="19cb1-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="19cb1-111">Per ulteriori informazioni, vedere [utilizzo di spazi dei nomi XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="19cb1-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child1>  
                    <Text>Child One Text</Text>  
                    <Type Value="Yes"/>  
                </Child1>  
                <Child2>  
                    <Text>Child Two Text</Text>  
                    <Type Value="Yes"/>  
                </Child2>  
                <Child3>  
                    <Text>Child Three Text</Text>  
                    <Type Value="No"/>  
                </Child3>  
                <Child4>  
                    <Text>Child Four Text</Text>  
                    <Type Value="Yes"/>  
                </Child4>  
                <Child5>  
                    <Text>Child Five Text</Text>  
                </Child5>  
            </Root>  
        Dim cList As IEnumerable(Of String) = _  
            From typeElement In root.Elements().<Type> _  
            Where typeElement.@Value = "Yes" _  
            Select typeElement.Parent.<Text>.Value  
        Dim str As String  
        For Each str In cList  
            Console.WriteLine(str)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="19cb1-112">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="19cb1-112">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="19cb1-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19cb1-113">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="19cb1-114">Le query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19cb1-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="19cb1-115">Proprietà Child Axis XML</span><span class="sxs-lookup"><span data-stu-id="19cb1-115">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="19cb1-116">Proprietà axis dell'attributo XML</span><span class="sxs-lookup"><span data-stu-id="19cb1-116">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)  
 [<span data-ttu-id="19cb1-117">Proprietà Value XML</span><span class="sxs-lookup"><span data-stu-id="19cb1-117">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="19cb1-118">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19cb1-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="19cb1-119">Operazioni di proiezione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19cb1-119">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
