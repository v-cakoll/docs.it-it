---
title: 'Procedura: impostare le proprietà di larghezza di un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: 72617744a8b2565857d19a1c6ef41bf4211c89ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>Procedura: impostare le proprietà di larghezza di un elemento
## <a name="example"></a>Esempio  
 In questo esempio vengono illustrate le differenze nel comportamento di rendering tra le quattro proprietà correlate alla larghezza in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 La <xref:System.Windows.FrameworkElement> classe espone quattro proprietà che descrivono le caratteristiche di larghezza di un elemento. Queste quattro proprietà possono essere in conflitto, e in tal caso, il valore ha la precedenza è determinato come segue: il <xref:System.Windows.FrameworkElement.MinWidth%2A> valore ha la precedenza sul <xref:System.Windows.FrameworkElement.MaxWidth%2A> valore, che a sua volta ha la precedenza sul <xref:System.Windows.FrameworkElement.Width%2A> valore. Una quarta proprietà <xref:System.Windows.FrameworkElement.ActualWidth%2A>è di sola lettura e la larghezza effettiva determinata dalle interazioni con il processo di layout di report.  
  
 Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] esempi disegno un <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) come figlio di <xref:System.Windows.Controls.Canvas>. È possibile modificare le proprietà di larghezza di un <xref:System.Windows.Shapes.Rectangle> mediante una serie di <xref:System.Windows.Controls.ListBox> gli elementi che rappresentano i valori delle proprietà <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, e <xref:System.Windows.FrameworkElement.Width%2A>. In questo modo, viene visualizzata in modo visivo la priorità di ogni proprietà.  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 Gli esempi di codice seguenti gestiscono gli eventi che il <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> genera eventi. Ogni metodo personalizzato accetta l'input di <xref:System.Windows.Controls.ListBox>, analizza il valore come un <xref:System.Double>e applica il valore della proprietà correlate alla larghezza specificata. I valori di larghezza sono inoltre convertiti in una stringa e scritti nei vari <xref:System.Windows.Controls.TextBlock> elementi (definizione di tali elementi non è illustrato nel codice XAML selezionato).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Per l'esempio completo, vedere [esempio confronto proprietà Width](http://go.microsoft.com/fwlink/?LinkID=160050).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.FrameworkElement.ActualWidth%2A>  
 <xref:System.Windows.FrameworkElement.MaxWidth%2A>  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Impostare le proprietà di altezza di un elemento](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)  
 [Esempio di confronto di proprietà Width](http://go.microsoft.com/fwlink/?LinkID=160050)
