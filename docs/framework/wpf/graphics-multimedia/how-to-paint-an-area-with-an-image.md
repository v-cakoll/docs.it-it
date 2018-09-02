---
title: "Procedura: disegnare un'area con un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], painting with
- painting [WPF], with images
- brushes [WPF], painting with images
ms.assetid: 3432c533-1fc7-492d-94ee-0b13d60125ae
ms.openlocfilehash: 5899531291c22ada76213905d0f2ca6944fcbba7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43408020"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Procedura: disegnare un'area con un'immagine
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Media.ImageBrush> classe disegnare un'area con un'immagine. Un' <xref:System.Windows.Media.ImageBrush> Visualizza una singola immagine specificata dal relativo <xref:System.Windows.Media.ImageBrush.ImageSource%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Di seguito viene riportato di seguito viene disegnata la <xref:System.Windows.Controls.Control.Background%2A> di un pulsante usando un <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 Per impostazione predefinita, un <xref:System.Windows.Media.ImageBrush> estende la propria immagine per riempire completamente l'area da disegnare. Nell'esempio precedente, l'immagine viene adattata per riempire il pulsante, possibilmente distorcendo l'immagine. È possibile controllare questo comportamento impostando il <xref:System.Windows.Media.TileBrush.Stretch%2A> proprietà di <xref:System.Windows.Media.TileBrush> al <xref:System.Windows.Media.Stretch.Uniform> o <xref:System.Windows.Media.Stretch.UniformToFill>, in modo che il pennello conservi le proporzioni dell'immagine.  
  
 Se si impostano i <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un <xref:System.Windows.Media.ImageBrush>, è possibile creare un criterio di ripetizione. L'esempio seguente disegna un pulsante con un modello creato da un'immagine.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Per altre informazioni sul <xref:System.Windows.Media.ImageBrush> classe, vedere [disegnare con immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Questo esempio di codice fa parte di un esempio più esaustivo fornito per il <xref:System.Windows.Media.ImageBrush> classe. Per l'esempio completo, vedere [esempio ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
## <a name="see-also"></a>Vedere anche  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
