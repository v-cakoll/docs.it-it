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
ms.openlocfilehash: 92969778c04c6ac634a2964c402d6c3439b96b49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186061"
---
# <a name="how-to-paint-an-area-with-an-image"></a>Procedura: disegnare un'area con un'immagine
In questo esempio viene <xref:System.Windows.Media.ImageBrush> illustrato come utilizzare la classe per disegnare un'area con un'immagine. Un <xref:System.Windows.Media.ImageBrush> visualizza una singola immagine, <xref:System.Windows.Media.ImageBrush.ImageSource%2A> specificata dalla relativa proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente <xref:System.Windows.Controls.Control.Background%2A> viene disegnato l'oggetto di un pulsante utilizzando un oggetto . <xref:System.Windows.Media.ImageBrush>  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/PaintingWithImagesExample.cs#imagebrushexamplewholepage)]  
  
 Per impostazione <xref:System.Windows.Media.ImageBrush> predefinita, un'immagine allunga la propria immagine per riempire completamente l'area che si sta disegnando. Nell'esempio precedente, l'immagine viene adattata per riempire il pulsante, possibilmente distorcendo l'immagine. È possibile controllare questo <xref:System.Windows.Media.TileBrush.Stretch%2A> comportamento <xref:System.Windows.Media.TileBrush> impostando <xref:System.Windows.Media.Stretch.Uniform> <xref:System.Windows.Media.Stretch.UniformToFill>la proprietà su o , in modo che il pennello mantenga le proporzioni dell'immagine.  
  
 Se si <xref:System.Windows.Media.TileBrush.Viewport%2A> impostano le proprietà e <xref:System.Windows.Media.TileBrush.TileMode%2A> di un oggetto , è possibile creare un motivo ripetuto. <xref:System.Windows.Media.ImageBrush> L'esempio seguente disegna un pulsante con un modello creato da un'immagine.  
  
 [!code-csharp[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TiledImageBrushExample.cs#tiledimagebrushexamplewholepage)]
 [!code-vb[UsingImageBrush_snip#TiledImageBrushExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UsingImageBrush_snip/VisualBasic/TiledImageBrushExample.vb#tiledimagebrushexamplewholepage)]  
  
 Per ulteriori informazioni <xref:System.Windows.Media.ImageBrush> sulla classe , vedere [Disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
 Questo esempio di codice fa parte di <xref:System.Windows.Media.ImageBrush> un esempio più esaustivo fornito per la classe. Per l'esempio completo, vedere [Esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).  
  
## <a name="see-also"></a>Vedere anche

- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
