---
title: Panoramica sui gestori eventi
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: 10ba458197973ede35849a86fec35003f139b8d2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743467"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="cb6c2-102">Panoramica dei gestori eventi (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="cb6c2-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="cb6c2-103">Un gestore eventi è un metodo associato a un evento.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="cb6c2-104">Quando viene generato l'evento, il codice all'interno del gestore eventi viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="cb6c2-105">Ogni gestore eventi fornisce due parametri che consentono di gestire correttamente l'evento.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="cb6c2-106">Nell'esempio seguente viene illustrato un gestore eventi per l'evento <xref:System.Windows.Forms.Control.Click> di un controllo <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 <span data-ttu-id="cb6c2-107">Il primo parametro,`sender`, fornisce un riferimento all'oggetto che ha generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="cb6c2-108">Il secondo parametro, `e`nell'esempio precedente, passa un oggetto specifico dell'evento che viene gestito.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="cb6c2-109">Facendo riferimento alle proprietà dell'oggetto (e talvolta ai relativi metodi), è possibile ottenere informazioni come la posizione del mouse per gli eventi del mouse o i dati trasferiti negli eventi di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="cb6c2-110">In genere, ogni evento produce un gestore eventi con un tipo di oggetto evento diverso per il secondo parametro.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="cb6c2-111">Alcuni gestori di eventi, ad esempio quelli per gli eventi <xref:System.Windows.Forms.Control.MouseDown> e <xref:System.Windows.Forms.Control.MouseUp>, hanno lo stesso tipo di oggetto per il secondo parametro.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="cb6c2-112">Per questi tipi di eventi, è possibile usare lo stesso gestore eventi per gestire entrambi gli eventi.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="cb6c2-113">È anche possibile usare lo stesso gestore eventi per gestire lo stesso evento per controlli diversi.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="cb6c2-114">Se, ad esempio, si dispone di un gruppo di controlli <xref:System.Windows.Forms.RadioButton> in un form, è possibile creare un singolo gestore eventi per l'evento <xref:System.Windows.Forms.Control.Click> e fare in modo che ogni <xref:System.Windows.Forms.Control.Click> evento del controllo venga associato al singolo gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="cb6c2-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="cb6c2-115">Per altre informazioni, vedere [procedura: connettere più eventi a un singolo gestore eventi in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="cb6c2-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6c2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb6c2-116">See also</span></span>

- [<span data-ttu-id="cb6c2-117">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="cb6c2-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="cb6c2-118">Informazioni generali sugli eventi</span><span class="sxs-lookup"><span data-stu-id="cb6c2-118">Events Overview</span></span>](events-overview-windows-forms.md)
