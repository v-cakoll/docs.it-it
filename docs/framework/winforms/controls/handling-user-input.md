---
title: Gestione dell'input dell'utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: a230611bfbb0a7f21a96de22674377887cc93c2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527800"
---
# <a name="handling-user-input"></a><span data-ttu-id="3abac-102">Gestione dell'input dell'utente</span><span class="sxs-lookup"><span data-stu-id="3abac-102">Handling User Input</span></span>
<span data-ttu-id="3abac-103">In questo argomento vengono descritti gli eventi di tastiera e mouse principali forniti da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3abac-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3abac-104">Quando si gestisce un evento, gli autori dei controlli devono eseguire l'override del metodo protetto `On`*EventName* anziché associare un delegato all'evento.</span><span class="sxs-lookup"><span data-stu-id="3abac-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="3abac-105">Per una panoramica degli eventi, vedere [Generazione di eventi da un componente](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span><span class="sxs-lookup"><span data-stu-id="3abac-105">For a review of events, see [Raising Events from a Component](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3abac-106">Se non sono presenti dati associati a un evento, un'istanza della classe di base <xref:System.EventArgs> viene passato come argomento per il `On` *EventName* metodo.</span><span class="sxs-lookup"><span data-stu-id="3abac-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="3abac-107">Eventi della tastiera</span><span class="sxs-lookup"><span data-stu-id="3abac-107">Keyboard Events</span></span>  
 <span data-ttu-id="3abac-108">Gli eventi della tastiera che è in grado di gestire il controllo sono <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, e <xref:System.Windows.Forms.Control.KeyUp>.</span><span class="sxs-lookup"><span data-stu-id="3abac-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="3abac-109">Nome evento</span><span class="sxs-lookup"><span data-stu-id="3abac-109">Event Name</span></span>|<span data-ttu-id="3abac-110">Metodo di cui eseguire l'override</span><span class="sxs-lookup"><span data-stu-id="3abac-110">Method to Override</span></span>|<span data-ttu-id="3abac-111">Descrizione dell'evento</span><span class="sxs-lookup"><span data-stu-id="3abac-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="3abac-112">Generato solo quando un tasto viene premuto inizialmente.</span><span class="sxs-lookup"><span data-stu-id="3abac-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="3abac-113">Generato ogni volta che un tasto viene premuto.</span><span class="sxs-lookup"><span data-stu-id="3abac-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="3abac-114">Se una si tiene premuto, un <xref:System.Windows.Forms.Control.KeyPress> evento viene generato alla frequenza definita dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3abac-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="3abac-115">Viene generato quando un tasto viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="3abac-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="3abac-116">La gestione dell'input da tastiera è notevolmente più complessa dell'override degli eventi nella tabella precedente ed esula dall'ambito di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3abac-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="3abac-117">Per altre informazioni, vedere [Input dell'utente in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3abac-117">For more information, see [User Input in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="3abac-118">Eventi del mouse</span><span class="sxs-lookup"><span data-stu-id="3abac-118">Mouse Events</span></span>  
 <span data-ttu-id="3abac-119">Gli eventi del mouse in grado di gestire il controllo sono <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, e <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="3abac-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="3abac-120">Nome evento</span><span class="sxs-lookup"><span data-stu-id="3abac-120">Event Name</span></span>|<span data-ttu-id="3abac-121">Metodo di cui eseguire l'override</span><span class="sxs-lookup"><span data-stu-id="3abac-121">Method to Override</span></span>|<span data-ttu-id="3abac-122">Descrizione dell'evento</span><span class="sxs-lookup"><span data-stu-id="3abac-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="3abac-123">Viene generato quando il pulsante del mouse viene premuto mentre il puntatore si trova sopra il controllo.</span><span class="sxs-lookup"><span data-stu-id="3abac-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="3abac-124">Viene generato quando il puntatore del mouse entra nell'area del controllo.</span><span class="sxs-lookup"><span data-stu-id="3abac-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="3abac-125">Viene generato quando il puntatore è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="3abac-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="3abac-126">Viene generato quando il puntatore esce dall'area del controllo.</span><span class="sxs-lookup"><span data-stu-id="3abac-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="3abac-127">Viene generato quando il puntatore si sposta nell'area del controllo.</span><span class="sxs-lookup"><span data-stu-id="3abac-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="3abac-128">Viene generato quando il pulsante del mouse viene rilasciato mentre il puntatore si trova sul controllo o il puntatore esce dall'area del controllo.</span><span class="sxs-lookup"><span data-stu-id="3abac-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="3abac-129">Frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseDown> evento.</span><span class="sxs-lookup"><span data-stu-id="3abac-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="3abac-130">Frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseMove> evento.</span><span class="sxs-lookup"><span data-stu-id="3abac-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="3abac-131">Frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseUp> evento.</span><span class="sxs-lookup"><span data-stu-id="3abac-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="3abac-132">Per il codice sorgente completo dell'esempio `FlashTrackBar`, vedere [Procedura: Creare un controllo di Windows Forms che visualizzi lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="3abac-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3abac-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3abac-133">See Also</span></span>  
 [<span data-ttu-id="3abac-134">Eventi dei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="3abac-134">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [<span data-ttu-id="3abac-135">Definizione di un evento</span><span class="sxs-lookup"><span data-stu-id="3abac-135">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [<span data-ttu-id="3abac-136">Eventi</span><span class="sxs-lookup"><span data-stu-id="3abac-136">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="3abac-137">Input dell'utente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3abac-137">User Input in Windows Forms</span></span>](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
