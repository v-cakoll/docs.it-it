---
title: "Procedura: aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush"
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 2457bdb794d81e7c482f735cad4ade34564328e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559324"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Procedura: aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush
In questo esempio viene illustrato come animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa tre animazioni per animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush>.  
  
-   La prima animazione, un <xref:System.Windows.Media.Animation.ColorAnimation>, modifica il colore del pennello per <xref:System.Windows.Media.Colors.Gray%2A> quando il mouse viene spostato il rettangolo.  
  
-   La successiva animazione, un altro <xref:System.Windows.Media.Animation.ColorAnimation>, modifica il colore del pennello per <xref:System.Windows.Media.Colors.Orange%2A> quando il puntatore del mouse esce dall'area del rettangolo.  
  
-   L'ultima animazione, un <xref:System.Windows.Media.Animation.DoubleAnimation>, cambia l'opacità del pennello in 0,0 quando viene premuto il pulsante sinistro del mouse.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Per un esempio più completo che illustra come aggiungere un'animazione a tipi diversi di pennelli, vedere il [esempio](http://go.microsoft.com/fwlink/?LinkID=159973). Per ulteriori informazioni sull'animazione, vedere il [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Per coerenza con gli altri esempi di animazione, nelle versioni del codice di questo esempio viene utilizzato un <xref:System.Windows.Media.Animation.Storyboard> oggetto a cui applicare le animazioni. Tuttavia, quando si applica un'animazione sola nel codice, è più semplice l'utilizzo di <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo anziché un <xref:System.Windows.Media.Animation.Storyboard>. Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli)
