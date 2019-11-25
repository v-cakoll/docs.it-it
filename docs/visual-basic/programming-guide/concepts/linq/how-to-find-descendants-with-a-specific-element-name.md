---
title: 'Procedura: trovare discendenti con un nome di elemento specifico'
ms.date: 07/20/2015
ms.assetid: 78915518-0d25-4051-ab55-929779989510
ms.openlocfilehash: 1a8aa07a79d05e62e0d5517c1675bc715e87de42
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344400"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-visual-basic"></a><span data-ttu-id="c1743-102">How to: Find Descendants with a Specific Element Name (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1743-102">How to: Find Descendants with a Specific Element Name (Visual Basic)</span></span>
<span data-ttu-id="c1743-103">Talvolta si desidera individuare tutti i discendenti con un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="c1743-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="c1743-104">È possibile scrivere codice per scorrere tutti i discendenti, tuttavia è più agevole usare l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="c1743-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1743-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1743-105">Example</span></span>  
 <span data-ttu-id="c1743-106">Nell'esempio seguente è illustrato come individuare discendenti in base al nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="c1743-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```vb  
Dim root As XElement = _  
    <root>  
        <para>  
            <r>  
                <t>Some text </t>  
            </r>  
            <n>  
                <r>  
                    <t>that is broken up into </t>  
                </r>  
            </n>  
            <n>  
                <r>  
                    <t>multiple segments.</t>  
                </r>  
            </n>  
        </para>  
    </root>  
  
Dim textSegs As IEnumerable(Of String) = _  
    From seg In root...<t> _  
    Select seg.Value  
  
Dim str As String = textSegs.Aggregate( _  
    New StringBuilder, _  
    Function(sb, i) sb.Append(i), _  
    Function(sb) sb.ToString)  
  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="c1743-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c1743-107">This code produces the following output:</span></span>  
  
```console  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="c1743-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="c1743-108">Example</span></span>  
 <span data-ttu-id="c1743-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c1743-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c1743-110">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c1743-110">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <root>  
                <para>  
                    <r>  
                        <t>Some text </t>  
                    </r>  
                    <n>  
                        <r>  
                            <t>that is broken up into </t>  
                        </r>  
                    </n>  
                    <n>  
                        <r>  
                            <t>multiple segments.</t>  
                        </r>  
                    </n>  
                </para>  
            </root>  
  
        Dim textSegs As IEnumerable(Of String) = _  
            From seg In root...<t> _  
            Select seg.Value  
  
        Dim str As String = textSegs.Aggregate( _  
            New StringBuilder, _  
            Function(sb, i) sb.Append(i), _  
            Function(sb) sb.ToString)  
  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c1743-111">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c1743-111">This code produces the following output:</span></span>  
  
```console  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1743-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1743-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- [<span data-ttu-id="c1743-113">Basic Queries (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1743-113">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
