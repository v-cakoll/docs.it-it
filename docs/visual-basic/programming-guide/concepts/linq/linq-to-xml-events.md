---
title: Eventi LINQ to XML
ms.date: 07/20/2015
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
ms.openlocfilehash: d00f6f1b2a14ac73c1bcd4a1f74b9714ca304da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368816"
---
# <a name="linq-to-xml-events-visual-basic"></a><span data-ttu-id="01784-102">Eventi LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01784-102">LINQ to XML Events (Visual Basic)</span></span>
<span data-ttu-id="01784-103">Gli eventi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consentono di ricevere una notifica quando un albero XML viene modificato.</span><span class="sxs-lookup"><span data-stu-id="01784-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="01784-104">È possibile aggiungere eventi a un'istanza di qualsiasi oggetto <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="01784-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="01784-105">Il gestore eventi riceverà quindi gli eventi relativi alle modifiche apportate a <xref:System.Xml.Linq.XObject> e a tutti i relativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="01784-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="01784-106">Ad esempio, è possibile aggiungere un gestore eventi alla radice dell'albero e gestire tutte le modifiche apportate alla struttura da tale gestore.</span><span class="sxs-lookup"><span data-stu-id="01784-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="01784-107">Per esempi di eventi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], vedere <xref:System.Xml.Linq.XObject.Changing> e <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="01784-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="01784-108">Tipi ed eventi</span><span class="sxs-lookup"><span data-stu-id="01784-108">Types and Events</span></span>  
 <span data-ttu-id="01784-109">Con gli eventi è possibile usare i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="01784-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="01784-110">Type</span><span class="sxs-lookup"><span data-stu-id="01784-110">Type</span></span>|<span data-ttu-id="01784-111">Description</span><span class="sxs-lookup"><span data-stu-id="01784-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="01784-112">Specifica il tipo di evento quando viene generato un evento per un oggetto <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="01784-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="01784-113">Fornisce i dati per gli eventi <xref:System.Xml.Linq.XObject.Changing> e <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="01784-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="01784-114">Gli eventi seguenti vengono generati quando si modifica una struttura ad albero XML:</span><span class="sxs-lookup"><span data-stu-id="01784-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="01784-115">Event</span><span class="sxs-lookup"><span data-stu-id="01784-115">Event</span></span>|<span data-ttu-id="01784-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01784-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="01784-117">Si verifica poco prima che l'oggetto <xref:System.Xml.Linq.XObject> o uno qualsiasi dei relativi discendenti venga modificato.</span><span class="sxs-lookup"><span data-stu-id="01784-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="01784-118">Si verifica quando un oggetto <xref:System.Xml.Linq.XObject> o uno qualsiasi dei relativi discendenti viene modificato.</span><span class="sxs-lookup"><span data-stu-id="01784-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="01784-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="01784-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="01784-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01784-120">Description</span></span>  
 <span data-ttu-id="01784-121">Gli eventi sono utili quando si desidera gestire alcune informazioni di aggregazione in un albero XML.</span><span class="sxs-lookup"><span data-stu-id="01784-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="01784-122">Ad esempio, si desidera gestire un totale di fattura che corrisponde alla somma delle voci della fattura.</span><span class="sxs-lookup"><span data-stu-id="01784-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="01784-123">In questo esempio vengono usati gli eventi per gestire il totale di tutti gli elementi figlio sotto l'elemento `Items` complesso.</span><span class="sxs-lookup"><span data-stu-id="01784-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="01784-124">Codice</span><span class="sxs-lookup"><span data-stu-id="01784-124">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="01784-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="01784-125">Comments</span></span>  
 <span data-ttu-id="01784-126">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="01784-126">This code produces the following output:</span></span>  
  
```console  
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
  
## <a name="see-also"></a><span data-ttu-id="01784-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01784-127">See also</span></span>

- [<span data-ttu-id="01784-128">Programmazione LINQ to XML avanzata (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01784-128">Advanced LINQ to XML Programming (Visual Basic)</span></span>](advanced-linq-to-xml-programming.md)
