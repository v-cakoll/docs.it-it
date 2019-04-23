---
title: 'Procedura: Ridimensionare le righe con un GridSplitter'
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: 6760a7a691af4f666294556cae3bc95a4299730a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074274"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a>Procedura: Ridimensionare le righe con un GridSplitter
Questo esempio viene illustrato come usare un oggetto orizzontale <xref:System.Windows.Controls.GridSplitter> per ridistribuire lo spazio tra le due righe in una <xref:System.Windows.Controls.Grid> senza modificare le dimensioni del <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Esempio  
 **Come creare un oggetto GridSplitter si sovrapponga al bordo di una riga**  
  
 Per specificare una <xref:System.Windows.Controls.GridSplitter> che ridimensiona righe adiacenti in un <xref:System.Windows.Controls.Grid>, impostare il <xref:System.Windows.Controls.Grid.Row%2A> proprietà associata a una delle righe che si intende ridimensionare. Se il <xref:System.Windows.Controls.Grid> ha più di una colonna, impostare il <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà associata per specificare il numero di colonne. Impostare quindi le <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> al <xref:System.Windows.VerticalAlignment.Top> o <xref:System.Windows.VerticalAlignment.Bottom> (l'allineamento impostato dipende dalle due righe si intende ridimensionare). Infine, impostare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà <xref:System.Windows.HorizontalAlignment.Stretch>.  
  
 Nell'esempio seguente viene illustrato come definire un controllo orizzontale <xref:System.Windows.Controls.GridSplitter> che ridimensiona righe adiacenti.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 Oggetto <xref:System.Windows.Controls.GridSplitter> che non occupa una riga può essere nascosto da altri controlli presenti il <xref:System.Windows.Controls.Grid>. Per altre informazioni su come evitare questo problema, vedere [Assicurarsi che GridSplitter sia visibile](how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Come creare un oggetto GridSplitter che occupa una riga**  
  
 Per specificare una <xref:System.Windows.Controls.GridSplitter> che occupa una riga in un <xref:System.Windows.Controls.Grid>, impostare il <xref:System.Windows.Controls.Grid.Row%2A> proprietà associata a una delle righe che si intende ridimensionare. Se il <xref:System.Windows.Controls.Grid> ha più di una colonna, impostare il <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà associata al numero di colonne. Quindi impostare il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> al <xref:System.Windows.VerticalAlignment.Center>, impostare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà <xref:System.Windows.HorizontalAlignment.Stretch>e impostare il <xref:System.Windows.Controls.RowDefinition.Height%2A> della riga che contiene il <xref:System.Windows.Controls.GridSplitter> per <xref:System.Windows.GridLength.Auto%2A>.  
  
 Nell'esempio seguente viene illustrato come definire un controllo orizzontale <xref:System.Windows.Controls.GridSplitter> che occupa una riga e ridimensiona le righe ai lati.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GridSplitter>
- [Procedure relative alle proprietà](gridsplitter-how-to-topics.md)
