---
title: 'Procedura: ridimensionare le colonne con un GridSplitter'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d68d829e5543b1c299668493c11b62ccb11d81af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a>Procedura: ridimensionare le colonne con un GridSplitter
In questo esempio viene illustrato come creare un oggetto verticale <xref:System.Windows.Controls.GridSplitter> per ridistribuire lo spazio tra le due colonne in un <xref:System.Windows.Controls.Grid> senza modificare le dimensioni del <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Esempio  
 **Come creare un oggetto GridSplitter che si sovrapponga al bordo di una colonna**  
  
 Per specificare un <xref:System.Windows.Controls.GridSplitter> che ridimensiona le colonne adiacenti in un <xref:System.Windows.Controls.Grid>, impostare il <xref:System.Windows.Controls.Grid.Column%2A> proprietà associata a una delle colonne che vuoi ridimensionare. Se il <xref:System.Windows.Controls.Grid> ha più di una riga, impostare il <xref:System.Windows.Controls.Grid.RowSpan%2A> proprietà associata al numero di righe. Impostare quindi la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà <xref:System.Windows.HorizontalAlignment.Left> o <xref:System.Windows.HorizontalAlignment.Right> (l'allineamento impostato dipende dalle due colonne che si desidera ridimensionare). Infine, impostare il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà <xref:System.Windows.VerticalAlignment.Stretch>.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 A <xref:System.Windows.Controls.GridSplitter> che non ha una propria colonna può essere nascosto da altri controlli di <xref:System.Windows.Controls.Grid>. Per altre informazioni su come evitare questo problema, vedere [Assicurarsi che GridSplitter sia visibile](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Come creare un oggetto GridSplitter che occupa una colonna**  
  
 Per specificare un <xref:System.Windows.Controls.GridSplitter> che occupa una colonna in un <xref:System.Windows.Controls.Grid>, impostare il <xref:System.Windows.Controls.Grid.Column%2A> proprietà associata a una delle colonne che vuoi ridimensionare. Se la griglia contiene più di una riga, impostare il <xref:System.Windows.Controls.Grid.RowSpan%2A> proprietà associata al numero di righe. Quindi impostare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> a <xref:System.Windows.HorizontalAlignment.Center>, impostare il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> proprietà <xref:System.Windows.VerticalAlignment.Stretch>e impostare il <xref:System.Windows.Controls.ColumnDefinition.Width%2A> della colonna che contiene il <xref:System.Windows.Controls.GridSplitter> a <xref:System.Windows.GridLength.Auto%2A>.  
  
 Nell'esempio seguente viene illustrato come definire un verticale <xref:System.Windows.Controls.GridSplitter> che occupa una colonna e ridimensiona le colonne in entrambi i lati.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.GridSplitter>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
