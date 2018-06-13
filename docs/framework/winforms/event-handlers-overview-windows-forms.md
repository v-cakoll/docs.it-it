---
title: Cenni preliminari sui gestori eventi (Windows Form)
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
ms.openlocfilehash: 2970cf0f83339fe86faf4af7da80bb17bd25acfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538157"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="72033-102">Cenni preliminari sui gestori eventi (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="72033-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="72033-103">Un gestore eventi è un metodo che è associato a un evento.</span><span class="sxs-lookup"><span data-stu-id="72033-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="72033-104">Quando viene generato l'evento, viene eseguito il codice nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="72033-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="72033-105">Ogni gestore di evento fornisce due parametri che consentono di gestire correttamente l'evento.</span><span class="sxs-lookup"><span data-stu-id="72033-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="72033-106">Nell'esempio seguente viene illustrato un gestore eventi per un <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Click> evento.</span><span class="sxs-lookup"><span data-stu-id="72033-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
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
  
 <span data-ttu-id="72033-107">Il primo parametro,`sender`, fornisce un riferimento all'oggetto che ha generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="72033-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="72033-108">Il secondo parametro, `e`, nell'esempio precedente passa un oggetto specifico per l'evento che viene gestito.</span><span class="sxs-lookup"><span data-stu-id="72033-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="72033-109">Facendo riferimento alle proprietà dell'oggetto (e, in alcuni casi, i metodi), è possibile ottenere informazioni quali il percorso del puntatore del mouse per gli eventi del mouse o i dati trasferiti negli eventi di trascinamento e rilascio.</span><span class="sxs-lookup"><span data-stu-id="72033-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="72033-110">In genere, ogni evento produce un gestore eventi con un tipo di oggetto evento diverso per il secondo parametro.</span><span class="sxs-lookup"><span data-stu-id="72033-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="72033-111">Gestori di eventi, ad esempio quelle per il <xref:System.Windows.Forms.Control.MouseDown> e <xref:System.Windows.Forms.Control.MouseUp> gli eventi, hanno lo stesso tipo di oggetto per il secondo parametro.</span><span class="sxs-lookup"><span data-stu-id="72033-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="72033-112">Per questi tipi di eventi, è possibile utilizzare lo stesso gestore eventi per gestire entrambi gli eventi.</span><span class="sxs-lookup"><span data-stu-id="72033-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="72033-113">È anche possibile utilizzare lo stesso gestore eventi per gestire lo stesso evento per diversi controlli.</span><span class="sxs-lookup"><span data-stu-id="72033-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="72033-114">Ad esempio, se si dispone di un gruppo di <xref:System.Windows.Forms.RadioButton> controlli in un form, è possibile creare un unico gestore eventi per il <xref:System.Windows.Forms.Control.Click> evento e di ciascun controllo <xref:System.Windows.Forms.Control.Click> associato al gestore dell'evento singolo evento.</span><span class="sxs-lookup"><span data-stu-id="72033-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="72033-115">Per ulteriori informazioni, vedere [procedura: connettere più eventi a un singolo gestore eventi in Windows Form](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="72033-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72033-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72033-116">See Also</span></span>  
 [<span data-ttu-id="72033-117">Creazione di gestori eventi in Windows Form</span><span class="sxs-lookup"><span data-stu-id="72033-117">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="72033-118">Informazioni generali sugli eventi</span><span class="sxs-lookup"><span data-stu-id="72033-118">Events Overview</span></span>](../../../docs/framework/winforms/events-overview-windows-forms.md)
