---
title: 'Procedura: ridimensionare un''area di disegno utilizzando un cursore'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c73509d58112e47f707e82243005bfdf9edca151
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="f7bc4-102">Procedura: ridimensionare un'area di disegno utilizzando un cursore</span><span class="sxs-lookup"><span data-stu-id="f7bc4-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="f7bc4-103">In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Controls.Primitives.Thumb> controllo per ridimensionare un <xref:System.Windows.Controls.Canvas> controllo.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7bc4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f7bc4-104">Example</span></span>  
 <span data-ttu-id="f7bc4-105">Il <xref:System.Windows.Controls.Primitives.Thumb> controllo fornisce funzionalità di trascinamento che può essere utilizzata per spostare o ridimensionare i controlli mediante il monitoraggio di <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> gli eventi del <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="f7bc4-106">L'utente inizia un'operazione di trascinamento premendo il pulsante sinistro del mouse quando il puntatore del mouse viene posizionato sul <xref:System.Windows.Controls.Primitives.Thumb> controllo.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="f7bc4-107">L'operazione di trascinamento continua finché il pulsante sinistro del mouse rimane premuto.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="f7bc4-108">Durante l'operazione di trascinamento, il <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> può comparire più volte.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="f7bc4-109">Ogni volta che si verifica, la <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> classe fornisce la modifica nella posizione che corrisponde alla modifica della posizione del mouse.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="f7bc4-110">Quando l'utente rilascia il pulsante sinistro del mouse, l'operazione di trascinamento viene completata.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="f7bc4-111">L'operazione di trascinamento fornisce solo le nuove coordinate; Riposiziona automaticamente il <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="f7bc4-112">Nell'esempio seguente un <xref:System.Windows.Controls.Primitives.Thumb> controllo che rappresenta l'elemento figlio di un <xref:System.Windows.Controls.Canvas> controllo.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="f7bc4-113">Il gestore eventi per il relativo <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> evento fornisce la logica per spostare il <xref:System.Windows.Controls.Primitives.Thumb> e ridimensionare il <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="f7bc4-114">I gestori eventi per il <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> eventi modificare il colore del <xref:System.Windows.Controls.Primitives.Thumb> durante un'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="f7bc4-115">L'esempio seguente definisce il <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="f7bc4-116">Nell'esempio seguente il <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> gestore dell'evento che si sposta il <xref:System.Windows.Controls.Primitives.Thumb> e viene ridimensionato il <xref:System.Windows.Controls.Canvas> in risposta a un movimento del mouse.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="f7bc4-117">Nell'esempio seguente il <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="f7bc4-118">Nell'esempio seguente il <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="f7bc4-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="f7bc4-119">Per l'esempio completo, vedere [esempio funzionalità di trascinamento Thumb](http://go.microsoft.com/fwlink/?LinkID=160042).</span><span class="sxs-lookup"><span data-stu-id="f7bc4-119">For the complete sample, see [Thumb Drag Functionality Sample](http://go.microsoft.com/fwlink/?LinkID=160042).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7bc4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7bc4-120">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.Thumb>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
