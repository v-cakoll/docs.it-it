---
title: 'Procedura: Trasformare un pennello'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: a83f3b1c046e94faa8816e8c310f438b4711048a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769381"
---
# <a name="how-to-transform-a-brush"></a>Procedura: Trasformare un pennello
In questo esempio viene illustrato come trasformare <xref:System.Windows.Media.Brush> gli oggetti utilizzando le due proprietà di trasformazione: <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 Gli esempi seguenti usano un <xref:System.Windows.Media.RotateTransform> ruotare il contenuto di un <xref:System.Windows.Media.ImageBrush> di 45 gradi.  
  
 La figura seguente mostra il <xref:System.Windows.Media.ImageBrush> senza un <xref:System.Windows.Media.RotateTransform>, con la <xref:System.Windows.Media.RotateTransform> applicato al <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà e con il <xref:System.Windows.Media.RotateTransform> applicate al <xref:System.Windows.Media.Brush.Transform%2A> proprietà.  
  
 ![Impostazioni RelativeTransform e Transform di Brush](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>Esempio  
 Il primo esempio applica un' <xref:System.Windows.Media.RotateTransform> per il <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà di un <xref:System.Windows.Media.ImageBrush>. Il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> delle proprietà di un <xref:System.Windows.Media.RotateTransform> sono entrambe impostate su 0,5, ovvero la coordinata relativa del punto centrale del contenuto dell'oggetto. Di conseguenza, il <xref:System.Windows.Media.ImageBrush> contenuto ruota intorno al relativo centro.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Si applica anche nel secondo esempio una <xref:System.Windows.Media.RotateTransform> a un <xref:System.Windows.Media.ImageBrush>; tuttavia, questo esempio viene usato il <xref:System.Windows.Media.Brush.Transform%2A> proprietà invece del <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà.  
  
 Per ruotare il pennello intorno al relativo centro, l'esempio imposta il <xref:System.Windows.Media.RotateTransform.CenterX%2A> e <xref:System.Windows.Media.RotateTransform.CenterY%2A> delle proprietà del <xref:System.Windows.Media.RotateTransform> oggetto su coordinate assolute. Poiché il pennello disegna un rettangolo di 175 x 90 pixel, il punto centrale del rettangolo è (87,5, 45).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Per una descrizione del modo in cui il <xref:System.Windows.Media.Brush.RelativeTransform%2A> e <xref:System.Windows.Media.Brush.Transform%2A> delle proprietà, vedere la [Cenni preliminari sulle trasformazione Brush](brush-transformation-overview.md).  
  
 Per l'esempio completo, vedere [Brushes Sample (Esempio di pennelli)](https://go.microsoft.com/fwlink/?LinkID=159973). Per altre informazioni sui pennelli, vedere [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sulle proprietà di trasformazione Brush](brush-transformation-overview.md)
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Cenni preliminari sulle trasformazioni](transforms-overview.md)
