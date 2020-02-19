---
title: 'Procedura: far ruotare sul posto un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: 2e72389a11e48629c2763fcbd9f7b1945ffff5dd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452792"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Procedura: far ruotare sul posto un elemento
In questo esempio viene illustrato come eseguire la rotazione di un elemento utilizzando un <xref:System.Windows.Media.RotateTransform> e una <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Nell'esempio seguente viene applicato il <xref:System.Windows.Media.RotateTransform> alla proprietà <xref:System.Windows.UIElement.RenderTransform%2A> dell'elemento. Nell'esempio viene utilizzato un <xref:System.Windows.Media.Animation.DoubleAnimation> per animare il <xref:System.Windows.Media.RotateTransform.Angle%2A> dell'<xref:System.Windows.Media.RotateTransform>. Per far ruotare l'elemento, nell'esempio viene impostata la proprietà <xref:System.Windows.UIElement.RenderTransformOrigin%2A> dell'elemento sul punto (0,5, 0,5).  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Per l'esempio completo, che include altri esempi di trasformazione, vedere [esempio di trasformazioni 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
