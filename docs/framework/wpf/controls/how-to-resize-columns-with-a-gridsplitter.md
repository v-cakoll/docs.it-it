---
title: 'Procedura: Ridimensionare le colonne con un GridSplitter'
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: 93106ee25d98a056dfa5ba1a064c9803bebb072e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374128"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a>Procedura: Ridimensionare le colonne con un GridSplitter
In questo esempio viene illustrato come creare un parametro vertical <xref:System.Windows.Controls.GridSplitter> per ridistribuire lo spazio tra le due colonne in un <xref:System.Windows.Controls.Grid> senza modificare le dimensioni del <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Esempio  
 **Come creare un oggetto GridSplitter che si sovrapponga al bordo di una colonna**  
  
 Per specificare una <xref:System.Windows.Controls.GridSplitter> che ridimensiona colonne adiacenti in un <xref:System.Windows.Controls.Grid>, impostare il <xref:System.Windows.Controls.Grid.Column%2A> proprietà associata a una delle colonne che si intende ridimensionare. Se il <xref:System.Windows.Controls.Grid> ha più di una riga, impostare il <xref:System.Windows.Controls.Grid.RowSpan%2A> proprietà associata per il numero di righe. Impostare quindi le <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà <xref:System.Windows.HorizontalAlignment.Left> o <xref:System.Windows.HorizontalAlignment.Right> (l'allineamento impostato dipende dalle due colonne che si intende ridimensionare). Infine, impostare il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà <xref:System.Windows.VerticalAlignment.Stretch>.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 Oggetto <xref:System.Windows.Controls.GridSplitter> che non dispone di una propria colonna può essere nascosto da altri controlli presenti il <xref:System.Windows.Controls.Grid>. Per altre informazioni su come evitare questo problema, vedere [Assicurarsi che GridSplitter sia visibile](how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Come creare un oggetto GridSplitter che occupa una colonna**  
  
 Per specificare una <xref:System.Windows.Controls.GridSplitter> che occupa una colonna in una <xref:System.Windows.Controls.Grid>, impostare il <xref:System.Windows.Controls.Grid.Column%2A> proprietà associata a una delle colonne che si intende ridimensionare. Se l'oggetto Grid ha più di una riga, impostare il <xref:System.Windows.Controls.Grid.RowSpan%2A> proprietà associata per il numero di righe. Quindi impostare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> al <xref:System.Windows.HorizontalAlignment.Center>, impostare il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà <xref:System.Windows.VerticalAlignment.Stretch>e impostare il <xref:System.Windows.Controls.ColumnDefinition.Width%2A> della colonna che contiene il <xref:System.Windows.Controls.GridSplitter> per <xref:System.Windows.GridLength.Auto%2A>.  
  
 Nell'esempio seguente viene illustrato come definire un parametro vertical <xref:System.Windows.Controls.GridSplitter> che occupa una colonna e ridimensiona le colonne ai lati.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.GridSplitter>
- [Procedure relative alle proprietà](gridsplitter-how-to-topics.md)
