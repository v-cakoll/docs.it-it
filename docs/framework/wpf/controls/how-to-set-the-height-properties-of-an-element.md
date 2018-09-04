---
title: 'Procedura: impostare le proprietà di altezza di un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 4d4aade743507001f825c19994e2f5feb1726ac4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525474"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Procedura: impostare le proprietà di altezza di un elemento
## <a name="example"></a>Esempio  
 In questo esempio vengono illustrate le differenze nel comportamento di rendering tra le quattro proprietà correlate all'altezza in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 Il <xref:System.Windows.FrameworkElement> classe espone quattro proprietà che descrivono le caratteristiche dell'altezza di un elemento. Possono verificarsi conflitti tra queste quattro proprietà e in tal caso, il valore ha la precedenza viene determinato come segue: il <xref:System.Windows.FrameworkElement.MinHeight%2A> valore ha la precedenza sul <xref:System.Windows.FrameworkElement.MaxHeight%2A> valore, che a sua volta ha la precedenza sul <xref:System.Windows.FrameworkElement.Height%2A> valore. Una proprietà di quarta <xref:System.Windows.FrameworkElement.ActualHeight%2A>è di sola lettura e l'altezza effettivo a quanto determinato dalle interazioni con il processo di layout di report.  
  
 Quanto segue [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] negli esempi viene tracciato un <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) come elemento figlio <xref:System.Windows.Controls.Canvas>. È possibile modificare le proprietà height di una <xref:System.Windows.Shapes.Rectangle> tramite una serie di <xref:System.Windows.Controls.ListBox> gli elementi che rappresentano i valori delle proprietà <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, e <xref:System.Windows.FrameworkElement.Height%2A>. In questo modo, viene visualizzata in modo visivo la priorità di ogni proprietà.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 Gli esempi di codice seguenti gestiscono gli eventi che il <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> generati dagli eventi. Ogni gestore elabora l'input dal <xref:System.Windows.Controls.ListBox>, analizza il valore come un <xref:System.Double>e applica il valore della proprietà correlate alla altezza specificata. I valori di altezza sono inoltre convertiti in una stringa e scritti nei vari <xref:System.Windows.Controls.TextBlock> elementi (definizione di tali elementi non viene visualizzato nella finestra di XAML selezionato).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Per l'esempio completo, vedere [esempio di proprietà di altezza](https://go.microsoft.com/fwlink/?LinkID=159993).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>  
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>  
 <xref:System.Windows.FrameworkElement.MinHeight%2A>  
 <xref:System.Windows.FrameworkElement.Height%2A>  
 [Impostare le proprietà di larghezza di un elemento](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Esempio di proprietà di altezza](https://go.microsoft.com/fwlink/?LinkID=159993)
