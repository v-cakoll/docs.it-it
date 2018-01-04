---
title: "Procedura: impostare le proprietà di altezza di un elemento"
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
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc06eea281f7761abfae74edf1547fc914b5655a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Procedura: impostare le proprietà di altezza di un elemento
## <a name="example"></a>Esempio  
 In questo esempio vengono illustrate le differenze nel comportamento di rendering tra le quattro proprietà correlate all'altezza in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 La <xref:System.Windows.FrameworkElement> classe espone quattro proprietà che descrivono le caratteristiche dell'altezza di un elemento. Queste quattro proprietà possono essere in conflitto, e in tal caso, il valore ha la precedenza è determinato come segue: il <xref:System.Windows.FrameworkElement.MinHeight%2A> valore ha la precedenza sul <xref:System.Windows.FrameworkElement.MaxHeight%2A> valore, che a sua volta ha la precedenza sul <xref:System.Windows.FrameworkElement.Height%2A> valore. Una quarta proprietà <xref:System.Windows.FrameworkElement.ActualHeight%2A>è di sola lettura e l'altezza effettiva determinata dalle interazioni con il processo di layout di report.  
  
 Nell'esempio [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] esempi disegno un <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) come figlio di <xref:System.Windows.Controls.Canvas>. È possibile modificare le proprietà di altezza di un <xref:System.Windows.Shapes.Rectangle> mediante una serie di <xref:System.Windows.Controls.ListBox> gli elementi che rappresentano i valori delle proprietà <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, e <xref:System.Windows.FrameworkElement.Height%2A>. In questo modo, viene visualizzata in modo visivo la priorità di ogni proprietà.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 Gli esempi di codice seguenti gestiscono gli eventi che il <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> genera eventi. Ogni gestore accetta l'input di <xref:System.Windows.Controls.ListBox>, analizza il valore come un <xref:System.Double>e applica il valore della proprietà correlate altezza specificata. I valori di altezza vengono inoltre convertiti in una stringa e scritti nei vari <xref:System.Windows.Controls.TextBlock> elementi (definizione di tali elementi non è illustrato nel codice XAML selezionato).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Per l'esempio completo, vedere [esempio di proprietà di altezza](http://go.microsoft.com/fwlink/?LinkID=159993).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.ActualHeight%2A>  
 <xref:System.Windows.FrameworkElement.MaxHeight%2A>  
 <xref:System.Windows.FrameworkElement.MinHeight%2A>  
 <xref:System.Windows.FrameworkElement.Height%2A>  
 [Impostare le proprietà di larghezza di un elemento](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [Esempio di proprietà di altezza](http://go.microsoft.com/fwlink/?LinkID=159993)
