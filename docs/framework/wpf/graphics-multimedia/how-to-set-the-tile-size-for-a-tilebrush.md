---
title: 'Procedura: impostare la dimensione degli elementi affiancati di un TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 16f0a4b3a5c9b9075126ba6d8f19d65169f70921
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Procedura: impostare la dimensione degli elementi affiancati di un TileBrush
In questo esempio viene illustrato come impostare la dimensione dei riquadri per un <xref:System.Windows.Media.TileBrush>. Per impostazione predefinita, un <xref:System.Windows.Media.TileBrush> produce un singolo riquadro che riempie completamente l'area da disegnare. È possibile eseguire l'override di questo comportamento impostando la <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà.  
  
 Il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specifica la dimensione dei riquadri per un <xref:System.Windows.Media.TileBrush>. Per impostazione predefinita, il valore di <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà è relativo alle dimensioni dell'area da disegnare. Per rendere il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specificare una dimensione assoluta della tessera, impostare il <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.ImageBrush>, un tipo di <xref:System.Windows.Media.TileBrush>per disegnare un rettangolo con i riquadri. L'esempio imposta ogni tessera su un valore pari a 50% x 50% dell'area di output (rettangolo). Di conseguenza, il rettangolo viene disegnato con quattro proiezioni dell'immagine.  
  
 L'immagine seguente illustra l'output generato dall'esempio.
  
 ![Esempio di affiancamento con un tratto con immagine](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 Nell'esempio successivo viene creato un <xref:System.Windows.Media.ImageBrush>, imposta il relativo <xref:System.Windows.Media.TileBrush.Viewport%2A> per `0,0,25,25` e il relativo <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> per <xref:System.Windows.Media.BrushMappingMode.Absolute>che viene utilizzato per disegnare il rettangolo di un altro. Di conseguenza, il pennello genera tessere con una larghezza pari a 25 pixel e un'altezza pari a 25 pixel.  
  
 L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![TileBrush affiancato con un viewport di 0,0,0.25,0.25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 Gli esempi precedenti fanno parte di un esempio più esaustivo. Per l'esempio completo, vedere [esempio ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
 Sebbene questo esempio viene utilizzato il <xref:System.Windows.Media.ImageBrush> (classe), il <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> si comportano in modo identico per l'altro <xref:System.Windows.Media.TileBrush> oggetti, vale a dire per <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush>. Per ulteriori informazioni su <xref:System.Windows.Media.ImageBrush> e l'altro <xref:System.Windows.Media.TileBrush> degli oggetti, vedere [il disegno di immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.TileBrush>  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Creare modelli di elementi affiancati differenti con un TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)
