---
title: 'Procedura: impostare la dimensione degli elementi affiancati di un TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tilepropertys
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: e1ba1a25281ffdd1cc00e0bed0efe4f8508780be
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467835"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Procedura: impostare la dimensione degli elementi affiancati di un TileBrush
In questo esempio viene illustrato come impostare la dimensione delle tessere per un <xref:System.Windows.Media.TileBrush>. Per impostazione predefinita, un <xref:System.Windows.Media.TileBrush> produce una sola tessera che riempie completamente l'area da disegnare. È possibile eseguire l'override di questo comportamento impostando il <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà.  
  
 Il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specifica la dimensione delle tessere per un <xref:System.Windows.Media.TileBrush>. Per impostazione predefinita, il valore della <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà è relativo alle dimensioni dell'area da disegnare. Per rendere il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specificare una dimensione assoluta della tessera, impostare il <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' <xref:System.Windows.Media.ImageBrush>, un tipo di <xref:System.Windows.Media.TileBrush>per disegnare un rettangolo con tessere. L'esempio imposta ogni tessera su un valore pari a 50% x 50% dell'area di output (rettangolo). Di conseguenza, il rettangolo viene disegnato con quattro proiezioni dell'immagine.  
  
 L'immagine seguente illustra l'output generato dall'esempio.
  
 ![Esempio di affiancamento con un tratto con immagine](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 L'esempio successivo crea un <xref:System.Windows.Media.ImageBrush>, imposta relativo <xref:System.Windows.Media.TileBrush.Viewport%2A> a `0,0,25,25` e la relativa <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> a <xref:System.Windows.Media.BrushMappingMode.Absolute>e lo usa per disegnare un altro rettangolo. Di conseguenza, il pennello genera tessere con una larghezza pari a 25 pixel e un'altezza pari a 25 pixel.  
  
 L'immagine seguente illustra l'output generato dall'esempio.  
  
 ![TileBrush affiancato con un viewport di 0,0,0.25,0.25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 Gli esempi precedenti fanno parte di un esempio più esaustivo. Per l'esempio completo, vedere [esempio ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).  
  
 Sebbene questo esempio Usa la <xref:System.Windows.Media.ImageBrush> (classe), il <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> le proprietà si comportano in modo identico per gli altri <xref:System.Windows.Media.TileBrush> oggetti, vale a dire, per <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush>. Per altre informazioni sulle <xref:System.Windows.Media.ImageBrush> e l'altra <xref:System.Windows.Media.TileBrush> oggetti, vedere [disegnare con immagini, disegni e oggetti visivi](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.TileBrush>  
 [Disegnare con oggetti Image, Drawing e Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Creare modelli di elementi affiancati differenti con un TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)
