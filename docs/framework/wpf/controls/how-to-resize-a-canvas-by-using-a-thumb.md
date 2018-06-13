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
ms.openlocfilehash: c3e7176b0578c8fdc5f4331ad8f3b464f3a88b51
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555064"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Procedura: ridimensionare un'area di disegno utilizzando un cursore
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Controls.Primitives.Thumb> controllo per ridimensionare un <xref:System.Windows.Controls.Canvas> controllo.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.Primitives.Thumb> controllo fornisce funzionalità di trascinamento che può essere utilizzata per spostare o ridimensionare i controlli mediante il monitoraggio di <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> gli eventi del <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 L'utente inizia un'operazione di trascinamento premendo il pulsante sinistro del mouse quando il puntatore del mouse viene posizionato sul <xref:System.Windows.Controls.Primitives.Thumb> controllo. L'operazione di trascinamento continua finché il pulsante sinistro del mouse rimane premuto. Durante l'operazione di trascinamento, il <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> può comparire più volte. Ogni volta che si verifica, la <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> classe fornisce la modifica nella posizione che corrisponde alla modifica della posizione del mouse. Quando l'utente rilascia il pulsante sinistro del mouse, l'operazione di trascinamento viene completata. L'operazione di trascinamento fornisce solo le nuove coordinate; Riposiziona automaticamente il <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 Nell'esempio seguente un <xref:System.Windows.Controls.Primitives.Thumb> controllo che rappresenta l'elemento figlio di un <xref:System.Windows.Controls.Canvas> controllo. Il gestore eventi per il relativo <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> evento fornisce la logica per spostare il <xref:System.Windows.Controls.Primitives.Thumb> e ridimensionare il <xref:System.Windows.Controls.Canvas>. I gestori eventi per il <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> eventi modificare il colore del <xref:System.Windows.Controls.Primitives.Thumb> durante un'operazione di trascinamento. L'esempio seguente definisce il <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xaml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 Nell'esempio seguente il <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> gestore dell'evento che si sposta il <xref:System.Windows.Controls.Primitives.Thumb> e viene ridimensionato il <xref:System.Windows.Controls.Canvas> in risposta a un movimento del mouse.  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 Nell'esempio seguente il <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> gestore dell'evento.  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 Nell'esempio seguente il <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> gestore dell'evento.  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Per l'esempio completo, vedere [esempio funzionalità di trascinamento Thumb](http://go.microsoft.com/fwlink/?LinkID=160042).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Primitives.Thumb>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
