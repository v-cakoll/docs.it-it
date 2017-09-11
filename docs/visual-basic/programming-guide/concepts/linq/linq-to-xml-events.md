---
title: Eventi LINQ to XML (Visual Basic) | Documenti di Microsoft
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
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
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
ms.openlocfilehash: e2358808dfeafab1576a686563e6025f90e78954
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-events-visual-basic"></a><span data-ttu-id="54744-102">Eventi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54744-102">LINQ to XML Events (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="54744-103">gli eventi consentono di ricevere una notifica quando un albero XML viene modificato.</span><span class="sxs-lookup"><span data-stu-id="54744-103"> events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="54744-104">È possibile aggiungere eventi a un'istanza di qualsiasi <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="54744-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="54744-105">Il gestore eventi riceverà quindi gli eventi per apportare modifiche a cui <xref:System.Xml.Linq.XObject>e dei relativi discendenti.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="54744-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="54744-106">Ad esempio, è possibile aggiungere un gestore eventi alla radice dell'albero e gestire tutte le modifiche apportate alla struttura da tale gestore.</span><span class="sxs-lookup"><span data-stu-id="54744-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="54744-107">Per esempi di [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] gli eventi, vedere <xref:System.Xml.Linq.XObject.Changing>e <xref:System.Xml.Linq.XObject.Changed>.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="54744-107">For examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="54744-108">Tipi ed eventi</span><span class="sxs-lookup"><span data-stu-id="54744-108">Types and Events</span></span>  
 <span data-ttu-id="54744-109">Con gli eventi è possibile usare i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="54744-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="54744-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="54744-110">Type</span></span>|<span data-ttu-id="54744-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54744-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="54744-112"><xref:System.Xml.Linq.XObjectChange></xref:System.Xml.Linq.XObjectChange></span><span class="sxs-lookup"><span data-stu-id="54744-112"><xref:System.Xml.Linq.XObjectChange></span></span>|<span data-ttu-id="54744-113">Specifica il tipo di evento quando viene generato un evento per un <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="54744-113">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="54744-114"><xref:System.Xml.Linq.XObjectChangeEventArgs></xref:System.Xml.Linq.XObjectChangeEventArgs></span><span class="sxs-lookup"><span data-stu-id="54744-114"><xref:System.Xml.Linq.XObjectChangeEventArgs></span></span>|<span data-ttu-id="54744-115">Fornisce dati per il <xref:System.Xml.Linq.XObject.Changing>e <xref:System.Xml.Linq.XObject.Changed>gli eventi.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="54744-115">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="54744-116">Gli eventi seguenti vengono generati quando si modifica una struttura ad albero XML:</span><span class="sxs-lookup"><span data-stu-id="54744-116">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="54744-117">Evento</span><span class="sxs-lookup"><span data-stu-id="54744-117">Event</span></span>|<span data-ttu-id="54744-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54744-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="54744-119"><xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="54744-119"><xref:System.Xml.Linq.XObject.Changing></span></span>|<span data-ttu-id="54744-120">Si verifica poco prima che il <xref:System.Xml.Linq.XObject>o dei relativi discendenti viene modificato.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="54744-120">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<span data-ttu-id="54744-121"><xref:System.Xml.Linq.XObject.Changed></xref:System.Xml.Linq.XObject.Changed></span><span class="sxs-lookup"><span data-stu-id="54744-121"><xref:System.Xml.Linq.XObject.Changed></span></span>|<span data-ttu-id="54744-122">Si verifica quando un <xref:System.Xml.Linq.XObject>è stato modificato o uno qualsiasi dei relativi discendenti viene modificato.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="54744-122">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="54744-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="54744-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="54744-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="54744-124">Description</span></span>  
 <span data-ttu-id="54744-125">Gli eventi sono utili quando si desidera gestire alcune informazioni di aggregazione in un albero XML.</span><span class="sxs-lookup"><span data-stu-id="54744-125">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="54744-126">Ad esempio, si desidera gestire un totale di fattura che corrisponde alla somma delle voci della fattura.</span><span class="sxs-lookup"><span data-stu-id="54744-126">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="54744-127">In questo esempio vengono usati gli eventi per gestire il totale di tutti gli elementi figlio sotto l'elemento `Items` complesso.</span><span class="sxs-lookup"><span data-stu-id="54744-127">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="54744-128">Codice</span><span class="sxs-lookup"><span data-stu-id="54744-128">Code</span></span>  
  
```vb  
Module Module1  
    Dim WithEvents items As XElement = Nothing  
    Dim total As XElement = Nothing  
    Dim root As XElement = _  
            <Root>  
                <Total>0</Total>  
                <Items></Items>  
            </Root>  
  
    Private Sub XObjectChanged( _  
            ByVal sender As Object, _  
            ByVal cea As XObjectChangeEventArgs) _  
            Handles items.Changed  
        Select Case cea.ObjectChange  
            Case XObjectChange.Add  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
            Case XObjectChange.Remove  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
        End Select  
        Console.WriteLine("Changed {0} {1}", _  
                            sender.GetType().ToString(), _  
                            cea.ObjectChange.ToString())  
    End Sub  
  
    Sub Main()  
        total = root.<Total>(0)  
        items = root.<Items>(0)  
        items.SetElementValue("Item1", 25)  
        items.SetElementValue("Item2", 50)  
        items.SetElementValue("Item2", 75)  
        items.SetElementValue("Item3", 133)  
        items.SetElementValue("Item1", Nothing)  
        items.SetElementValue("Item4", 100)  
        Console.WriteLine("Total:{0}", CInt(total))  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="54744-129">Commenti</span><span class="sxs-lookup"><span data-stu-id="54744-129">Comments</span></span>  
 <span data-ttu-id="54744-130">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="54744-130">This code produces the following output:</span></span>  
  
```  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="54744-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54744-131">See Also</span></span>  
 [<span data-ttu-id="54744-132">LINQ to XML (Visual Basic) di programmazione avanzata</span><span class="sxs-lookup"><span data-stu-id="54744-132">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
