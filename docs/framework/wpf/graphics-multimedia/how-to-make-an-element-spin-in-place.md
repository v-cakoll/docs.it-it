---
title: 'Procedura: far ruotare sul posto un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112076"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Procedura: far ruotare sul posto un elemento
In questo esempio viene illustrato come <xref:System.Windows.Media.RotateTransform> fare <xref:System.Windows.Media.Animation.DoubleAnimation>in modo che un elemento si scandigli utilizzando a e un oggetto .  
  
 Nell'esempio seguente <xref:System.Windows.Media.RotateTransform> viene <xref:System.Windows.UIElement.RenderTransform%2A> applicato l'oggetto alla proprietà dell'elemento . Nell'esempio <xref:System.Windows.Media.Animation.DoubleAnimation> viene utilizzato <xref:System.Windows.Media.RotateTransform.Angle%2A> un <xref:System.Windows.Media.RotateTransform>per animare l'oggetto dell'oggetto . Per fare in modo che l'elemento si giri sul posto, l'esempio imposta la <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà dell'elemento sul punto (0,5, 0,5).  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Per l'esempio completo, che include altri esempi di trasformazione, vedere Esempio di [trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
