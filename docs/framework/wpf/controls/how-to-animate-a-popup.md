---
title: 'Procedura: animare un controllo Popup'
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: 05b84eea7fe983340ebb8c5cdb20ff39eb2f0858
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553754"
---
# <a name="how-to-animate-a-popup"></a>Procedura: animare un controllo Popup
In questo esempio mostra due modi per aggiungere un'animazione a un <xref:System.Windows.Controls.Primitives.Popup> controllo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente imposta il <xref:System.Windows.Controls.Primitives.PopupAnimation> un valore di proprietà <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, causando il <xref:System.Windows.Controls.Primitives.Popup> "diapositiva-in" quando viene visualizzata.  
  
 Per ruotare il <xref:System.Windows.Controls.Primitives.Popup>, questo esempio viene assegnato un <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà il <xref:System.Windows.Controls.Canvas>, che è l'elemento figlio del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Per la trasformazione funzionare correttamente, è necessario impostare l'esempio di <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> proprietà `true`. Inoltre, il <xref:System.Windows.FrameworkElement.Margin%2A> sul <xref:System.Windows.Controls.Canvas> deve specificare quantità di spazio sufficiente per il <xref:System.Windows.Controls.Primitives.Popup> da ruotare.  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 L'esempio seguente viene illustrato come un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento che si verifica quando un <xref:System.Windows.Controls.Button> si fa clic, i trigger il <xref:System.Windows.Media.Animation.Storyboard> che inizia l'animazione.  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Controls.Primitives.BulletDecorator>  
 <xref:System.Windows.Media.RotateTransform>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Controls.Primitives.Popup>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/popup-how-to-topics.md)  
 [Panoramica sul controllo Popup](../../../../docs/framework/wpf/controls/popup-overview.md)
