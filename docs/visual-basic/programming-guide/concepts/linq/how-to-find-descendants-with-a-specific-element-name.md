---
title: 'Procedura: Trovare discendenti con un nome di elemento specifico'
ms.date: 07/20/2015
ms.assetid: 78915518-0d25-4051-ab55-929779989510
ms.openlocfilehash: 19e0807f3bb7e83061b2076a177107eec126e717
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405209"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-visual-basic"></a><span data-ttu-id="09621-102">Procedura: trovare discendenti con un nome di elemento specifico (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09621-102">How to: Find Descendants with a Specific Element Name (Visual Basic)</span></span>
<span data-ttu-id="09621-103">Talvolta si desidera individuare tutti i discendenti con un determinato nome.</span><span class="sxs-lookup"><span data-stu-id="09621-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="09621-104">È possibile scrivere codice per scorrere tutti i discendenti, tuttavia è più agevole usare l'asse <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="09621-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="09621-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="09621-105">Example</span></span>  
 <span data-ttu-id="09621-106">Nell'esempio seguente è illustrato come individuare discendenti in base al nome dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="09621-106">The following example shows how to find descendants based on the element name.</span></span>  
  
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
  
 <span data-ttu-id="09621-107">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="09621-107">This code produces the following output:</span></span>  
  
```console  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="09621-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="09621-108">Example</span></span>  
 <span data-ttu-id="09621-109">Nell'esempio seguente è illustrata la stessa query per XML in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="09621-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="09621-110">Per ulteriori informazioni, vedere [Cenni preliminari sugli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="09621-110">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="09621-111">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="09621-111">This code produces the following output:</span></span>  
  
```console  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="09621-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09621-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- [<span data-ttu-id="09621-113">Query di base (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09621-113">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)
