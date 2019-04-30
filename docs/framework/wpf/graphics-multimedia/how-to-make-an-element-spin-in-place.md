---
title: 'Procedura: Far ruotare sul posto un elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: aca9bd577f2882e31e8d49abe5eeb5ade86f95f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947252"
---
# <a name="how-to-make-an-element-spin-in-place"></a>Procedura: Far ruotare sul posto un elemento
Questo esempio viene illustrato come far ruotare utilizzando un elemento una <xref:System.Windows.Media.RotateTransform> e un <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 L'esempio seguente applica il <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.UIElement.RenderTransform%2A> proprietà dell'elemento. L'esempio Usa una <xref:System.Windows.Media.Animation.DoubleAnimation> animare il <xref:System.Windows.Media.RotateTransform.Angle%2A> del <xref:System.Windows.Media.RotateTransform>. Per rendere l'elemento ruotare sul posto, nell'esempio viene impostato il <xref:System.Windows.UIElement.RenderTransformOrigin%2A> proprietà dell'elemento per il punto (0,5, 0,5).  
  
## <a name="example"></a>Esempio  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Per l'esempio completo, che include altri esempi di trasformazione, vedere [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
