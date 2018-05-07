---
title: 'Procedura: utilizzare i metodi di scorrimento del contenuto di ScrollViewer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: b4da666934be7dd182838d870e54e496b2646901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a>Procedura: utilizzare i metodi di scorrimento del contenuto di ScrollViewer
In questo esempio viene illustrato come utilizzare i metodi di scorrimento di <xref:System.Windows.Controls.ScrollViewer> elemento. Questi metodi consentono lo scorrimento incrementale del contenuto, tramite la riga o pagina, in un <xref:System.Windows.Controls.ScrollViewer>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ScrollViewer> denominato `sv1`, che ospita un elemento figlio <xref:System.Windows.Controls.TextBlock> elemento. Poiché il <xref:System.Windows.Controls.TextBlock> è più grande del padre <xref:System.Windows.Controls.ScrollViewer>, vengono visualizzate le barre di scorrimento per consentire lo scorrimento. <xref:System.Windows.Controls.Button> gli elementi che rappresentano i diversi metodi di scorrimento sono ancorati a sinistra in un apposito <xref:System.Windows.Controls.StackPanel>. Ogni <xref:System.Windows.Controls.Button> nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file chiama un metodo personalizzato correlato che controlla il comportamento di scorrimento in <xref:System.Windows.Controls.ScrollViewer>.  
  
 [!code-xaml[ScrollViewerMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 L'esempio seguente usa il <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> e <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> metodi.  
  
 [!code-csharp[ScrollViewerMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ScrollViewer>  
 <xref:System.Windows.Controls.StackPanel>
