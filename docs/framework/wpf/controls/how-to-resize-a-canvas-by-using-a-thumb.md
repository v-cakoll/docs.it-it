---
title: "Procedura: Ridimensionare un'area di disegno usando un cursore"
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
ms.openlocfilehash: 14942157429b029147d47e2f88428c56e66523d1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979953"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Procedura: Ridimensionare un'area di disegno usando un cursore
In questo esempio viene illustrato come utilizzare un <xref:System.Windows.Controls.Primitives.Thumb> controllo per ridimensionare un <xref:System.Windows.Controls.Canvas> controllo.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.Primitives.Thumb> controllo fornisce funzionalità di trascinamento che può essere utilizzata per spostare o ridimensionare i controlli monitorando il <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> gli eventi del <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 L'utente inizia un'operazione di trascinamento premendo il pulsante sinistro del mouse quando il puntatore del mouse viene posizionato su di <xref:System.Windows.Controls.Primitives.Thumb> controllo. L'operazione di trascinamento continua fino a quando il pulsante sinistro del mouse rimane premuto. Durante l'operazione di trascinamento, il <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> può ricorrere più di una volta. Ogni volta che si verifica, il <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> classe fornisce la modifica nella posizione corrispondente alla modifica della posizione del mouse. Quando l'utente rilascia il pulsante sinistro del mouse, l'operazione di trascinamento viene completata. L'operazione di trascinamento fornisce solo le nuove coordinate; non riposizionata automaticamente il <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 L'esempio seguente mostra una <xref:System.Windows.Controls.Primitives.Thumb> controllo che rappresenta l'elemento figlio di un <xref:System.Windows.Controls.Canvas> controllo. Il gestore eventi per relativi <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> evento fornisce la logica per spostare il <xref:System.Windows.Controls.Primitives.Thumb> e ridimensionare il <xref:System.Windows.Controls.Canvas>. I gestori eventi per il <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> eventi modificare il colore del <xref:System.Windows.Controls.Primitives.Thumb> durante un'operazione di trascinamento. L'esempio seguente definisce il <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 L'esempio seguente mostra le <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> gestore dell'evento che si sposta il <xref:System.Windows.Controls.Primitives.Thumb> e ridimensiona il <xref:System.Windows.Controls.Canvas> in risposta a un movimento del mouse.  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 L'esempio seguente illustra il <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> gestore dell'evento.  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 L'esempio seguente illustra il <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> gestore dell'evento.  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Per l'esempio completo, vedere [esempio di funzionalità di trascinamento Thumb](https://go.microsoft.com/fwlink/?LinkID=160042).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
