---
title: 'Procedura: Impostare la dimensione degli elementi affiancati di un TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: 80b5dfc668464df829db593668bea8a9a4ec09e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839696"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Procedura: Impostare la dimensione degli elementi affiancati di un TileBrush

In questo esempio viene illustrato come impostare la dimensione delle tessere per un <xref:System.Windows.Media.TileBrush>. Per impostazione predefinita, un <xref:System.Windows.Media.TileBrush> produce una sola tessera che riempie completamente l'area da disegnare. È possibile eseguire l'override di questo comportamento impostando il <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà.

Il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specifica la dimensione delle tessere per un <xref:System.Windows.Media.TileBrush>. Per impostazione predefinita, il valore della <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà è relativo alle dimensioni dell'area da disegnare. Per rendere il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specificare una dimensione assoluta della tessera, impostare il <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute>.

## <a name="example"></a>Esempio

L'esempio seguente usa un' <xref:System.Windows.Media.ImageBrush>, un tipo di <xref:System.Windows.Media.TileBrush>per disegnare un rettangolo con tessere. L'esempio imposta ogni tessera portandolo al 50% x 50% dell'area di output (rettangolo). Di conseguenza, il rettangolo viene disegnato con quattro proiezioni dell'immagine.

Nella figura seguente mostra l'output di esempio generato:

![Un rettangolo con quattro gratta dimostrazione affiancamento con un pennello immagine.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

L'esempio successivo crea un <xref:System.Windows.Media.ImageBrush>, imposta relativo <xref:System.Windows.Media.TileBrush.Viewport%2A> a `0,0,25,25` e la relativa <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> a <xref:System.Windows.Media.BrushMappingMode.Absolute>e lo usa per disegnare un altro rettangolo. Di conseguenza, il pennello genera tessere con una larghezza pari a 25 pixel e un'altezza pari a 25 pixel.

Nella figura seguente mostra l'output di esempio generato:

![Un rettangolo con cerchiato-gratta dimostrazione di un oggetto TileBrush affiancato con un Viewport.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

Gli esempi precedenti fanno parte di un esempio più esaustivo. Per l'esempio completo, vedere [esempio ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005).

Sebbene questo esempio Usa la <xref:System.Windows.Media.ImageBrush> (classe), il <xref:System.Windows.Media.TileBrush.Viewport%2A> e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> le proprietà si comportano in modo identico per gli altri <xref:System.Windows.Media.TileBrush> oggetti, vale a dire, per <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush>. Per altre informazioni sulle <xref:System.Windows.Media.ImageBrush> e l'altra <xref:System.Windows.Media.TileBrush> oggetti, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.TileBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Creare modelli di elementi affiancati differenti con un TileBrush](how-to-create-different-tile-patterns-with-a-tilebrush.md)
