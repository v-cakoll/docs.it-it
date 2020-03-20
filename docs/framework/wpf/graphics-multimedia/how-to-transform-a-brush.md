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
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187329"
---
# <a name="how-to-transform-a-brush"></a>Procedura: trasformare un oggetto Brush
In questo esempio <xref:System.Windows.Media.Brush> viene illustrato come trasformare <xref:System.Windows.Media.Brush.RelativeTransform%2A> gli <xref:System.Windows.Media.Brush.Transform%2A>oggetti utilizzando le relative due proprietà di trasformazione: e .  
  
 Negli esempi seguenti <xref:System.Windows.Media.RotateTransform> viene utilizzato un <xref:System.Windows.Media.ImageBrush> per ruotare il contenuto di un oggetto di 45 gradi.  
  
 Nella figura seguente <xref:System.Windows.Media.ImageBrush> viene <xref:System.Windows.Media.RotateTransform>illustrato <xref:System.Windows.Media.RotateTransform> l'oggetto <xref:System.Windows.Media.Brush.RelativeTransform%2A> without a <xref:System.Windows.Media.RotateTransform> , con <xref:System.Windows.Media.Brush.Transform%2A> l'oggetto applicato alla proprietà e con l'oggetto applicato alla proprietà .  
  
 ![Impostazioni RelativeTransform e Transform di Brush](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Esempio  
 Nel primo esempio <xref:System.Windows.Media.RotateTransform> viene <xref:System.Windows.Media.Brush.RelativeTransform%2A> applicato <xref:System.Windows.Media.ImageBrush>un alla proprietà di un oggetto . Le <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> proprietà e <xref:System.Windows.Media.RotateTransform> di un oggetto sono entrambe impostate su 0,5, che è la coordinata relativa del punto centrale di questo contenuto. Di conseguenza, <xref:System.Windows.Media.ImageBrush> il contenuto ruota intorno al suo centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Il secondo esempio <xref:System.Windows.Media.RotateTransform> applica <xref:System.Windows.Media.ImageBrush>anche a a un oggetto ; tuttavia, in <xref:System.Windows.Media.Brush.Transform%2A> questo esempio <xref:System.Windows.Media.Brush.RelativeTransform%2A> viene utilizzata la proprietà anziché la proprietà .  
  
 Per ruotare il pennello intorno <xref:System.Windows.Media.RotateTransform.CenterX%2A> al <xref:System.Windows.Media.RotateTransform.CenterY%2A> centro, <xref:System.Windows.Media.RotateTransform> l'esempio imposta le proprietà e dell'oggetto su coordinate assolute. Poiché il pennello disegna un rettangolo di 175 x 90 pixel, il punto centrale del rettangolo è (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Per una descrizione <xref:System.Windows.Media.Brush.RelativeTransform%2A> del <xref:System.Windows.Media.Brush.Transform%2A> funzionamento delle proprietà e , vedere Cenni preliminari [sulla trasformazione del pennello](brush-transformation-overview.md).  
  
 Per l'esempio completo, vedere [Brushes Sample (Esempio di pennelli)](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Per altre informazioni sui pennelli, vedere [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sulle proprietà di trasformazione Brush](brush-transformation-overview.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
