---
title: 'Procedura: far ruotare sul posto un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a37952af621c79d231b45a247c92d3576a533580
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-an-element-spin-in-place"></a>Procedura: far ruotare sul posto un elemento
Questo esempio viene illustrato come creare un elemento di selezione tramite un <xref:System.Windows.Media.RotateTransform> e <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 Nell'esempio seguente viene applicato il <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento. Nell'esempio viene utilizzato un <xref:System.Windows.Media.Animation.DoubleAnimation> per animare la <xref:System.Windows.Media.RotateTransform.Angle%2A> del <xref:System.Windows.Media.RotateTransform>. Per far ruotare sul posto l'elemento, nell'esempio viene impostato il <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà dell'elemento per il punto (0,5, 0,5).  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Per un esempio completo che include più trasformazioni, vedere [esempio trasformazioni 2D](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
