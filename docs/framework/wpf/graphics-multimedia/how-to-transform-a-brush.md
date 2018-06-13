---
title: 'Procedura: trasformare un oggetto Brush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: 5caa00a378101ff4dff7745a18c3ec8905cc168b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561602"
---
# <a name="how-to-transform-a-brush"></a>Procedura: trasformare un oggetto Brush
In questo esempio viene illustrato come trasformare <xref:System.Windows.Media.Brush> oggetti utilizzando le proprietà di due trasformazione: <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 Negli esempi seguenti viene utilizzato un <xref:System.Windows.Media.RotateTransform> per ruotare il contenuto di un <xref:System.Windows.Media.ImageBrush> di 45 gradi.  
  
 Nella figura seguente il <xref:System.Windows.Media.ImageBrush> senza un <xref:System.Windows.Media.RotateTransform>, con la <xref:System.Windows.Media.RotateTransform> applicato al <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà e con il <xref:System.Windows.Media.RotateTransform> applicato al <xref:System.Windows.Media.Brush.Transform%2A> proprietà.  
  
 ![Impostazioni RelativeTransform e Transform di Brush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Esempio  
 Il primo esempio viene applicato un <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà di un <xref:System.Windows.Media.ImageBrush>. Il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> le proprietà di un <xref:System.Windows.Media.RotateTransform> sono entrambe impostate su 0,5, che è la coordinata relativa del punto centrale del contenuto dell'oggetto. Di conseguenza, il <xref:System.Windows.Media.ImageBrush> contenuto ruota intorno al centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Si applica anche nel secondo esempio una <xref:System.Windows.Media.RotateTransform> per un <xref:System.Windows.Media.ImageBrush>; tuttavia, questo esempio viene utilizzato il <xref:System.Windows.Media.Brush.Transform%2A> proprietà anziché il <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà.  
  
 Per ruotare il pennello rispetto al centro, nell'esempio viene impostato il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> le proprietà del <xref:System.Windows.Media.RotateTransform> oggetto coordinate assolute. Poiché il pennello disegna un rettangolo di 175 x 90 pixel, il punto centrale del rettangolo è (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Per una descrizione di come <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A> proprietà, vedere il [Brush Transformation Overview](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Per l'esempio completo, vedere [Brushes Sample (Esempio di pennelli)](http://go.microsoft.com/fwlink/?LinkID=159973). Per altre informazioni sui pennelli, vedere [Cenni sul disegno con colori a tinta unita e sfumature](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sulle proprietà di trasformazione Brush](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)  
 [Cenni sul disegno con colori a tinta unita e sfumature](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [Cenni preliminari sulle trasformazioni](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
