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
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Procedura: ridimensionare un'area di disegno utilizzando un cursore
Questo esempio illustra come usare un controllo <xref:System.Windows.Controls.Primitives.Thumb> per ridimensionare un controllo <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Esempio  
 Il controllo <xref:System.Windows.Controls.Primitives.Thumb> fornisce funzionalità di trascinamento che possono essere utilizzate per spostare o ridimensionare i controlli monitorando gli eventi <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> del <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 L'utente inizia un'operazione di trascinamento premendo il pulsante sinistro del mouse quando il puntatore del mouse viene sospeso sul controllo <xref:System.Windows.Controls.Primitives.Thumb>. L'operazione di trascinamento continua fino a quando il pulsante sinistro del mouse rimane premuto. Durante l'operazione di trascinamento, il <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> può ripetersi più di una volta. Ogni volta che si verifica, la classe <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> fornisce la modifica nella posizione che corrisponde alla modifica della posizione del mouse. Quando l'utente rilascia il pulsante sinistro del mouse, l'operazione di trascinamento viene completata. L'operazione di trascinamento fornisce solo nuove coordinate; il <xref:System.Windows.Controls.Primitives.Thumb>non viene riposizionato automaticamente.  
  
 Nell'esempio seguente viene illustrato un controllo <xref:System.Windows.Controls.Primitives.Thumb> che rappresenta l'elemento figlio di un controllo <xref:System.Windows.Controls.Canvas>. Il gestore eventi per il relativo evento <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> fornisce la logica per spostare l'<xref:System.Windows.Controls.Primitives.Thumb> e ridimensionare il <xref:System.Windows.Controls.Canvas>. I gestori eventi per l'evento <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> modificano il colore del <xref:System.Windows.Controls.Primitives.Thumb> durante un'operazione di trascinamento. Nell'esempio seguente viene definita la <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 Nell'esempio seguente viene illustrato il gestore dell'evento <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> che sposta l'<xref:System.Windows.Controls.Primitives.Thumb> e ridimensiona il <xref:System.Windows.Controls.Canvas> in risposta a un movimento del mouse.  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 Nell'esempio seguente viene illustrato il gestore dell'evento <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>.  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 Nell'esempio seguente viene illustrato il gestore dell'evento <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>.  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Per l'esempio completo, vedere [esempio di funzionalità di trascinamento del pollice](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
