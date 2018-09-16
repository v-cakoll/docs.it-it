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
ms.openlocfilehash: 19bb494d6f478c8cb7adda770f441470c4b2d19f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45677669"
---
# <a name="handling-user-input"></a><span data-ttu-id="83331-102">Gestione dell'input dell'utente</span><span class="sxs-lookup"><span data-stu-id="83331-102">Handling User Input</span></span>
<span data-ttu-id="83331-103">In questo argomento descrive gli eventi di tastiera e mouse principali forniti da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="83331-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="83331-104">Quando si gestisce un evento, gli autori dei controlli devono eseguire l'override del metodo protetto `On`*EventName* anziché associare un delegato all'evento.</span><span class="sxs-lookup"><span data-stu-id="83331-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="83331-105">Per una panoramica degli eventi, vedere [Generazione di eventi da un componente](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span><span class="sxs-lookup"><span data-stu-id="83331-105">For a review of events, see [Raising Events from a Component](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83331-106">Se non sono presenti dati associati a un evento, un'istanza della classe di base <xref:System.EventArgs> viene passato come argomento per il `On` *EventName* (metodo).</span><span class="sxs-lookup"><span data-stu-id="83331-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="83331-107">Eventi della tastiera</span><span class="sxs-lookup"><span data-stu-id="83331-107">Keyboard Events</span></span>  
 <span data-ttu-id="83331-108">Gli eventi della tastiera comuni che il controllo può gestire sono <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, e <xref:System.Windows.Forms.Control.KeyUp>.</span><span class="sxs-lookup"><span data-stu-id="83331-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="83331-109">Nome evento</span><span class="sxs-lookup"><span data-stu-id="83331-109">Event Name</span></span>|<span data-ttu-id="83331-110">Metodo di cui eseguire l'override</span><span class="sxs-lookup"><span data-stu-id="83331-110">Method to Override</span></span>|<span data-ttu-id="83331-111">Descrizione dell'evento</span><span class="sxs-lookup"><span data-stu-id="83331-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="83331-112">Generato solo quando un tasto viene premuto inizialmente.</span><span class="sxs-lookup"><span data-stu-id="83331-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="83331-113">Generato ogni volta che un tasto viene premuto.</span><span class="sxs-lookup"><span data-stu-id="83331-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="83331-114">Se un tasto viene tenuto premuto, un <xref:System.Windows.Forms.Control.KeyPress> evento viene generato alla frequenza di ripetizione definita dal sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="83331-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="83331-115">Viene generato quando un tasto viene rilasciato.</span><span class="sxs-lookup"><span data-stu-id="83331-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="83331-116">La gestione dell'input da tastiera è notevolmente più complessa dell'override degli eventi nella tabella precedente ed esula dall'ambito di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="83331-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="83331-117">Per altre informazioni, vedere [Input dell'utente in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="83331-117">For more information, see [User Input in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="83331-118">Eventi del mouse</span><span class="sxs-lookup"><span data-stu-id="83331-118">Mouse Events</span></span>  
 <span data-ttu-id="83331-119">Gli eventi del mouse che il controllo può gestire sono <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, e <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="83331-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="83331-120">Nome evento</span><span class="sxs-lookup"><span data-stu-id="83331-120">Event Name</span></span>|<span data-ttu-id="83331-121">Metodo di cui eseguire l'override</span><span class="sxs-lookup"><span data-stu-id="83331-121">Method to Override</span></span>|<span data-ttu-id="83331-122">Descrizione dell'evento</span><span class="sxs-lookup"><span data-stu-id="83331-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="83331-123">Viene generato quando il pulsante del mouse viene premuto mentre il puntatore si trova sopra il controllo.</span><span class="sxs-lookup"><span data-stu-id="83331-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="83331-124">Viene generato quando il puntatore del mouse entra nell'area del controllo.</span><span class="sxs-lookup"><span data-stu-id="83331-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="83331-125">Viene generato quando il puntatore è posizionato sul controllo.</span><span class="sxs-lookup"><span data-stu-id="83331-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="83331-126">Viene generato quando il puntatore esce dall'area del controllo.</span><span class="sxs-lookup"><span data-stu-id="83331-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="83331-127">Viene generato quando il puntatore si sposta nell'area del controllo.</span><span class="sxs-lookup"><span data-stu-id="83331-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="83331-128">Viene generato quando il pulsante del mouse viene rilasciato mentre il puntatore si trova sul controllo o il puntatore esce dall'area del controllo.</span><span class="sxs-lookup"><span data-stu-id="83331-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="83331-129">Il frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseDown> evento.</span><span class="sxs-lookup"><span data-stu-id="83331-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="83331-130">Il frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseMove> evento.</span><span class="sxs-lookup"><span data-stu-id="83331-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="83331-131">Il frammento di codice seguente viene illustrato un esempio di override di <xref:System.Windows.Forms.Control.MouseUp> evento.</span><span class="sxs-lookup"><span data-stu-id="83331-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="83331-132">Per il codice sorgente completo dell'esempio `FlashTrackBar`, vedere [Procedura: Creare un controllo di Windows Forms che visualizzi lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="83331-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83331-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83331-133">See Also</span></span>  
 [<span data-ttu-id="83331-134">Eventi dei controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="83331-134">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [<span data-ttu-id="83331-135">Definizione di un evento</span><span class="sxs-lookup"><span data-stu-id="83331-135">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [<span data-ttu-id="83331-136">Eventi</span><span class="sxs-lookup"><span data-stu-id="83331-136">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="83331-137">Input dell'utente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83331-137">User Input in Windows Forms</span></span>](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
