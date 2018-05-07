---
title: 'Procedura: creare un controllo Expander con un controllo ScrollViewer'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 6c014d4f6a12bfb58c2ae68f580f632c9478c82f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>Procedura: creare un controllo Expander con un controllo ScrollViewer
In questo esempio viene illustrato come creare un <xref:System.Windows.Controls.Expander> controllo che contiene contenuto complesso, ad esempio un'immagine e testo. Nell'esempio viene inoltre incluso il contenuto del <xref:System.Windows.Controls.Expander> in un <xref:System.Windows.Controls.ScrollViewer> controllo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come creare un <xref:System.Windows.Controls.Expander>. Nell'esempio viene utilizzato un <xref:System.Windows.Controls.Primitives.BulletDecorator> controllo che contiene un'immagine e testo, per definire il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>. Oggetto <xref:System.Windows.Controls.ScrollViewer> controllo fornisce un metodo per scorrere il contenuto espanso.  
  
 Si noti che nell'esempio viene impostato il <xref:System.Windows.FrameworkElement.Height%2A> proprietà il <xref:System.Windows.Controls.ScrollViewer> anziché sul contenuto. Se il <xref:System.Windows.FrameworkElement.Height%2A> è impostato sul contenuto, il <xref:System.Windows.Controls.ScrollViewer> non consente all'utente di scorrere il contenuto. Il <xref:System.Windows.FrameworkElement.Width%2A> proprietà è impostata sul <xref:System.Windows.Controls.Expander> controllo e questa impostazione si applica al <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e il contenuto espanso.  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Expander>  
 [Panoramica sul controllo Expander](../../../../docs/framework/wpf/controls/expander-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
