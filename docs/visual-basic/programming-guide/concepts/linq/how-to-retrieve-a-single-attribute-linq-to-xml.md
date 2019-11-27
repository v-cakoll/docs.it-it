---
title: 'Procedura: recuperare un singolo attributo (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 11b938d7-c011-4048-900e-8b9183c41c94
ms.openlocfilehash: 02afbc987cf9f55d16bb56912f3eaf45cd8c9a37
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347556"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="c54b6-102">Procedura: recuperare un singolo attributo (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c54b6-102">How to: Retrieve a Single Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c54b6-103">In questo argomento viene illustrato come recuperare un singolo attributo di un elemento, dato il relativo nome.</span><span class="sxs-lookup"><span data-stu-id="c54b6-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="c54b6-104">Questa procedura è utile per la scrittura di espressioni di query in cui si desidera trovare un elemento con un attributo specifico.</span><span class="sxs-lookup"><span data-stu-id="c54b6-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="c54b6-105">Il metodo <xref:System.Xml.Linq.XElement.Attribute%2A> della classe <xref:System.Xml.Linq.XElement> restituisce l'attributo <xref:System.Xml.Linq.XAttribute> con il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="c54b6-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c54b6-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="c54b6-106">Example</span></span>  
 <span data-ttu-id="c54b6-107">Nell'esempio seguente viene usato il metodo <xref:System.Xml.Linq.XElement.Attribute%2A>:</span><span class="sxs-lookup"><span data-stu-id="c54b6-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList = From el In cust...<Phone>  
For Each e As XElement In elList  
    Console.WriteLine(e.@type)  
Next  
```  
  
 <span data-ttu-id="c54b6-108">In questo esempio vengono individuati tutti i discendenti dell'albero denominato `Phone` e quindi l'attributo denominato `type`.</span><span class="sxs-lookup"><span data-stu-id="c54b6-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="c54b6-109">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c54b6-109">This code produces the following output:</span></span>  
  
```console  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="c54b6-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="c54b6-110">Example</span></span>  
 <span data-ttu-id="c54b6-111">Se si desidera recuperare il valore dell'attributo, è possibile eseguirne il cast, come nel caso degli oggetti <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="c54b6-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="c54b6-112">Nell'esempio che segue viene illustrato quanto descritto.</span><span class="sxs-lookup"><span data-stu-id="c54b6-112">The following example demonstrates this.</span></span>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList As IEnumerable(Of XElement) = _  
    From el In cust...<Phone> _  
    Select el  
For Each el As XElement In elList  
    Console.WriteLine(el.@type)  
Next  
```  
  
 <span data-ttu-id="c54b6-113">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c54b6-113">This code produces the following output:</span></span>  
  
```console  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="c54b6-114">fornisce operatori di cast espliciti per la classe <xref:System.Xml.Linq.XAttribute> in `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` e `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="c54b6-114">provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c54b6-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="c54b6-115">Example</span></span>  
 <span data-ttu-id="c54b6-116">Nell'esempio seguente viene illustrato lo stesso codice per un attributo all'interno di uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c54b6-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="c54b6-117">Per ulteriori informazioni, vedere [Cenni preliminari sugli spazi dei nomi (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c54b6-117">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim cust As XElement = _  
            <aw:PhoneNumbers>  
                <aw:Phone aw:type="home">555-555-5555</aw:Phone>  
                <aw:Phone aw:type="work">555-555-6666</aw:Phone>  
            </aw:PhoneNumbers>  
        Dim elList As IEnumerable(Of XElement) = _  
            From el In cust...<aw:Phone> _  
            Select el  
        For Each el As XElement In elList  
            Console.WriteLine(el.@aw:type)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c54b6-118">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="c54b6-118">This code produces the following output:</span></span>  
  
```console  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="c54b6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c54b6-119">See also</span></span>

- [<span data-ttu-id="c54b6-120">Assi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c54b6-120">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
