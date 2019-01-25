---
title: 'Procedura: Applicare le proprietà Stretch al contenuto di un Viewbox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
ms.openlocfilehash: 9ddf3e8fb0c1a75c8917dfd50876f9259e292fb1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711720"
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a>Procedura: Applicare le proprietà Stretch al contenuto di un Viewbox
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come modificare il valore della <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> e <xref:System.Windows.Controls.Viewbox.Stretch%2A> delle proprietà di un <xref:System.Windows.Controls.Viewbox>.  
  
 Il primo esempio viene utilizzata [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] per definire un <xref:System.Windows.Controls.Viewbox> elemento. Assegna un <xref:System.Windows.FrameworkElement.MaxWidth%2A> e <xref:System.Windows.FrameworkElement.MaxHeight%2A> di 400. Viene annidato un' <xref:System.Windows.Controls.Image> elemento all'interno di <xref:System.Windows.Controls.Viewbox>. <xref:System.Windows.Controls.Button> gli elementi che corrispondono ai valori della proprietà per il <xref:System.Windows.Controls.Viewbox.Stretch%2A> e <xref:System.Windows.Controls.StretchDirection> enumerazioni modificano il comportamento di adattamento di annidata <xref:System.Windows.Controls.Image>.  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 Gli handle di file code-behind seguente il <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gli eventi che precedente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio viene definito.  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.Viewbox>
- <xref:System.Windows.Media.Stretch>
- <xref:System.Windows.Controls.StretchDirection>
