---
title: 'Procedura: Animare un controllo Popup'
ms.date: 03/30/2017
helpviewer_keywords:
- Popup control [WPF], animating
- animation [WPF], Popup controls
ms.assetid: acaa2a0a-6137-4efd-9cd1-75ece222e390
ms.openlocfilehash: b70d9c4cb1bca26a6c77d3a7c50add517ca8ef92
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150111"
---
# <a name="how-to-animate-a-popup"></a>Procedura: Animare un controllo Popup
Questo esempio illustra due modi per animare un <xref:System.Windows.Controls.Primitives.Popup> controllo.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente imposta la <xref:System.Windows.Controls.Primitives.PopupAnimation> un valore della proprietà <xref:System.Windows.Controls.Primitives.PopupAnimation.Slide>, determinando in tal modo il <xref:System.Windows.Controls.Primitives.Popup> "diapositiva-in" quando viene visualizzato.  
  
 Per poter essere ruotate il <xref:System.Windows.Controls.Primitives.Popup>, in questo esempio viene assegnato un <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà la <xref:System.Windows.Controls.Canvas>, che è l'elemento figlio del <xref:System.Windows.Controls.Primitives.Popup>.  
  
 Per la trasformazione a funzionare correttamente, l'esempio è necessario impostare il <xref:System.Windows.Controls.Primitives.Popup.AllowsTransparency%2A> proprietà `true`. Inoltre, il <xref:System.Windows.FrameworkElement.Margin%2A> nella <xref:System.Windows.Controls.Canvas> contenuto è necessario specificare uno spazio sufficiente per il <xref:System.Windows.Controls.Primitives.Popup> per ruotare.  
  
 [!code-xaml[AnimatedPopup#RotateTransform2](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform2)]  
  
 L'esempio seguente mostra come un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento si verifica quando un <xref:System.Windows.Controls.Button> viene fatto clic, i trigger la <xref:System.Windows.Media.Animation.Storyboard> che inizia l'animazione.  
  
 [!code-xaml[AnimatedPopup#RotateTransform1](~/samples/snippets/csharp/VS_Snippets_Wpf/AnimatedPopup/CS/Window1.xaml#rotatetransform1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Controls.Primitives.BulletDecorator>
- <xref:System.Windows.Media.RotateTransform>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Controls.Primitives.Popup>
- [Procedure relative](popup-how-to-topics.md)
- [Cenni preliminari sul controllo Popup](popup-overview.md)
