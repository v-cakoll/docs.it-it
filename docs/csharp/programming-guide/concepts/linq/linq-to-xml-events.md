---
title: Eventi LINQ to XML (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5ccc3928795f188b7cf7b23d88a1f35ff043b889
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-xml-events-c"></a><span data-ttu-id="12d97-102">Eventi LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="12d97-102">LINQ to XML Events (C#)</span></span>
<span data-ttu-id="12d97-103">Gli eventi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] consentono di ricevere una notifica quando un albero XML viene modificato.</span><span class="sxs-lookup"><span data-stu-id="12d97-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="12d97-104">È possibile aggiungere eventi a un'istanza di qualsiasi oggetto <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="12d97-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="12d97-105">Il gestore eventi riceverà quindi gli eventi relativi alle modifiche apportate a <xref:System.Xml.Linq.XObject> e a tutti i relativi discendenti.</span><span class="sxs-lookup"><span data-stu-id="12d97-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="12d97-106">Ad esempio, è possibile aggiungere un gestore eventi alla radice dell'albero e gestire tutte le modifiche apportate alla struttura da tale gestore.</span><span class="sxs-lookup"><span data-stu-id="12d97-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="12d97-107">Per esempi di eventi [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], vedere <xref:System.Xml.Linq.XObject.Changing> e <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="12d97-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="12d97-108">Tipi ed eventi</span><span class="sxs-lookup"><span data-stu-id="12d97-108">Types and Events</span></span>  
 <span data-ttu-id="12d97-109">Con gli eventi è possibile usare i tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="12d97-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="12d97-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="12d97-110">Type</span></span>|<span data-ttu-id="12d97-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12d97-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="12d97-112">Specifica il tipo di evento quando viene generato un evento per un oggetto <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="12d97-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="12d97-113">Fornisce i dati per gli eventi <xref:System.Xml.Linq.XObject.Changing> e <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="12d97-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="12d97-114">Gli eventi seguenti vengono generati quando si modifica una struttura ad albero XML:</span><span class="sxs-lookup"><span data-stu-id="12d97-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="12d97-115">Evento</span><span class="sxs-lookup"><span data-stu-id="12d97-115">Event</span></span>|<span data-ttu-id="12d97-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12d97-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="12d97-117">Si verifica poco prima che l'oggetto <xref:System.Xml.Linq.XObject> o uno qualsiasi dei relativi discendenti venga modificato.</span><span class="sxs-lookup"><span data-stu-id="12d97-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="12d97-118">Si verifica quando un oggetto <xref:System.Xml.Linq.XObject> o uno qualsiasi dei relativi discendenti viene modificato.</span><span class="sxs-lookup"><span data-stu-id="12d97-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="12d97-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="12d97-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="12d97-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12d97-120">Description</span></span>  
 <span data-ttu-id="12d97-121">Gli eventi sono utili quando si desidera gestire alcune informazioni di aggregazione in un albero XML.</span><span class="sxs-lookup"><span data-stu-id="12d97-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="12d97-122">Ad esempio, si desidera gestire un totale di fattura che corrisponde alla somma delle voci della fattura.</span><span class="sxs-lookup"><span data-stu-id="12d97-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="12d97-123">In questo esempio vengono usati gli eventi per gestire il totale di tutti gli elementi figlio sotto l'elemento `Items` complesso.</span><span class="sxs-lookup"><span data-stu-id="12d97-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="12d97-124">Codice</span><span class="sxs-lookup"><span data-stu-id="12d97-124">Code</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Total", "0"),  
    new XElement("Items")  
);  
XElement total = root.Element("Total");  
XElement items = root.Element("Items");  
items.Changed += (object sender, XObjectChangeEventArgs cea) =>  
{  
    switch (cea.ObjectChange)  
    {  
        case XObjectChange.Add:  
            if (sender is XElement)  
                total.Value = ((int)total + (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total + (int)((XText)sender).Parent).ToString();  
            break;  
        case XObjectChange.Remove:  
            if (sender is XElement)  
                total.Value = ((int)total - (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total - Int32.Parse(((XText)sender).Value)).ToString();  
            break;  
    }  
    Console.WriteLine("Changed {0} {1}",  
      sender.GetType().ToString(), cea.ObjectChange.ToString());  
};  
items.SetElementValue("Item1", 25);  
items.SetElementValue("Item2", 50);  
items.SetElementValue("Item2", 75);  
items.SetElementValue("Item3", 133);  
items.SetElementValue("Item1", null);  
items.SetElementValue("Item4", 100);  
Console.WriteLine("Total:{0}", (int)total);  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a><span data-ttu-id="12d97-125">Commenti</span><span class="sxs-lookup"><span data-stu-id="12d97-125">Comments</span></span>  
 <span data-ttu-id="12d97-126">L'output del codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="12d97-126">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="12d97-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12d97-127">See Also</span></span>  
 [<span data-ttu-id="12d97-128">Programmazione LINQ to XML avanzata (C#)</span><span class="sxs-lookup"><span data-stu-id="12d97-128">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)

