---
title: 'Procedura: far ruotare sul posto un elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7dac2b1afb9d0ed385f3c25c2e30a93ea8a24f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
