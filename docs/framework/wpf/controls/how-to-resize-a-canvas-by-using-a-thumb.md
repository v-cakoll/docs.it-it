---
title: "Procedura: ridimensionare un'area di disegno utilizzando un cursore"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: 84f5ac2b53124b7f4d7c15741e94b40e7ee81526
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124299"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="40d5b-102">Procedura: ridimensionare un'area di disegno utilizzando un cursore</span><span class="sxs-lookup"><span data-stu-id="40d5b-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="40d5b-103">Questo esempio illustra come usare un controllo <xref:System.Windows.Controls.Primitives.Thumb> per ridimensionare un controllo <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="40d5b-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40d5b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="40d5b-104">Example</span></span>  
 <span data-ttu-id="40d5b-105">Il controllo <xref:System.Windows.Controls.Primitives.Thumb> fornisce funzionalità di trascinamento che possono essere utilizzate per spostare o ridimensionare i controlli monitorando gli eventi <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> del <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="40d5b-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="40d5b-106">L'utente inizia un'operazione di trascinamento premendo il pulsante sinistro del mouse quando il puntatore del mouse viene sospeso sul controllo <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="40d5b-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="40d5b-107">L'operazione di trascinamento continua fino a quando il pulsante sinistro del mouse rimane premuto.</span><span class="sxs-lookup"><span data-stu-id="40d5b-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="40d5b-108">Durante l'operazione di trascinamento, il <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> può ripetersi più di una volta.</span><span class="sxs-lookup"><span data-stu-id="40d5b-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="40d5b-109">Ogni volta che si verifica, la classe <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> fornisce la modifica nella posizione che corrisponde alla modifica della posizione del mouse.</span><span class="sxs-lookup"><span data-stu-id="40d5b-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="40d5b-110">Quando l'utente rilascia il pulsante sinistro del mouse, l'operazione di trascinamento viene completata.</span><span class="sxs-lookup"><span data-stu-id="40d5b-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="40d5b-111">L'operazione di trascinamento fornisce solo nuove coordinate; il <xref:System.Windows.Controls.Primitives.Thumb>non viene riposizionato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="40d5b-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="40d5b-112">Nell'esempio seguente viene illustrato un controllo <xref:System.Windows.Controls.Primitives.Thumb> che rappresenta l'elemento figlio di un controllo <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="40d5b-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="40d5b-113">Il gestore eventi per il relativo evento <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> fornisce la logica per spostare l'<xref:System.Windows.Controls.Primitives.Thumb> e ridimensionare il <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="40d5b-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="40d5b-114">I gestori eventi per l'evento <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> modificano il colore del <xref:System.Windows.Controls.Primitives.Thumb> durante un'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="40d5b-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="40d5b-115">Nell'esempio seguente viene definita la <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="40d5b-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="40d5b-116">Nell'esempio seguente viene illustrato il gestore dell'evento <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> che sposta l'<xref:System.Windows.Controls.Primitives.Thumb> e ridimensiona il <xref:System.Windows.Controls.Canvas> in risposta a un movimento del mouse.</span><span class="sxs-lookup"><span data-stu-id="40d5b-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="40d5b-117">Nell'esempio seguente viene illustrato il gestore dell'evento <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>.</span><span class="sxs-lookup"><span data-stu-id="40d5b-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="40d5b-118">Nell'esempio seguente viene illustrato il gestore dell'evento <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>.</span><span class="sxs-lookup"><span data-stu-id="40d5b-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="40d5b-119">Per l'esempio completo, vedere [esempio di funzionalità di trascinamento del pollice](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).</span><span class="sxs-lookup"><span data-stu-id="40d5b-119">For the complete sample, see [Thumb Drag Functionality Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40d5b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40d5b-120">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
