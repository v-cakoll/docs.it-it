---
title: "Procedura: Aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush"
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: e440cf49b8b16051361650f9659dc6006c2e7b56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072159"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Procedura: Aggiungere un'animazione al colore o all'opacità di un oggetto SolidColorBrush
In questo esempio illustra come animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente usa tre animazioni per animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> e <xref:System.Windows.Media.Brush.Opacity%2A> di un <xref:System.Windows.Media.SolidColorBrush>.  
  
-   La prima animazione, un <xref:System.Windows.Media.Animation.ColorAnimation>, viene modificato il colore del pennello per <xref:System.Windows.Media.Colors.Gray%2A> quando il mouse viene spostato il rettangolo.  
  
-   La successiva animazione, un'altra <xref:System.Windows.Media.Animation.ColorAnimation>, viene modificato il colore del pennello per <xref:System.Windows.Media.Colors.Orange%2A> quando il mouse lascia il rettangolo.  
  
-   L'ultima animazione, un <xref:System.Windows.Media.Animation.DoubleAnimation>, cambia l'opacità del pennello in 0,0 quando viene premuto il pulsante sinistro del mouse.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Per un esempio più completo, che mostra come aggiungere un'animazione di diversi tipi di pennelli, vedere la [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973). Per altre informazioni sulle animazioni, vedere la [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Per coerenza con altri esempi di animazione, nelle versioni del codice di questo esempio viene usano un <xref:System.Windows.Media.Animation.Storyboard> oggetto per applicare le animazioni. Tuttavia, quando si applica una sola animazione al codice, è più semplice usare il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo invece di usare un <xref:System.Windows.Media.Animation.Storyboard>. Per un esempio, vedere [Animare una proprietà senza utilizzare uno storyboard](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli)
