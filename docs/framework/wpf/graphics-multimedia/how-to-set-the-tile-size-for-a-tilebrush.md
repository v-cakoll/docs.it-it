---
title: 'Procedura: impostare la dimensione degli elementi affiancati di un TileBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- TileBrush [WPF], size of tile properties
- Viewport property of TileBrush [WPF]
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
ms.openlocfilehash: af7bab59a292549b29dad9b6a7417f22b1b84e48
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186832"
---
# <a name="how-to-set-the-tile-size-for-a-tilebrush"></a>Procedura: impostare la dimensione degli elementi affiancati di un TileBrush

In questo esempio viene illustrato come <xref:System.Windows.Media.TileBrush>impostare le dimensioni del riquadro per un oggetto . Per impostazione <xref:System.Windows.Media.TileBrush> predefinita, un singolo riquadro produce una singola tessera che riempie completamente l'area che si sta disegnando. È possibile eseguire l'override di questo comportamento impostando le <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà e <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> .

La <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà specifica la dimensione <xref:System.Windows.Media.TileBrush>del riquadro per un oggetto . Per impostazione predefinita, <xref:System.Windows.Media.TileBrush.Viewport%2A> il valore della proprietà è relativo alle dimensioni dell'area da disegnare. Per fare <xref:System.Windows.Media.TileBrush.Viewport%2A> in modo che la <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> proprietà <xref:System.Windows.Media.BrushMappingMode.Absolute>specifichi una dimensione assoluta del riquadro, impostate la proprietà su .

## <a name="example"></a>Esempio

Nell'esempio seguente <xref:System.Windows.Media.ImageBrush>viene utilizzato <xref:System.Windows.Media.TileBrush>un , un tipo di , per disegnare un rettangolo con riquadri. L'esempio imposta ogni riquadro al 50% per il 50% dell'area di output (il rettangolo). Di conseguenza, il rettangolo viene disegnato con quattro proiezioni dell'immagine.

La figura seguente mostra l'output prodotto dall'esempio:The following illustration shows the output that the example produces:

![Rettangolo con quattro ciliegie che illustrano l'appuntatura con un pennello immagine.](./media/how-to-set-the-tile-size-for-a-tilebrush/rectangle-tile-image-brush.png)

[!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]

Nell'esempio successivo <xref:System.Windows.Media.ImageBrush>viene <xref:System.Windows.Media.TileBrush.Viewport%2A> creato `0,0,25,25` un <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> <xref:System.Windows.Media.BrushMappingMode.Absolute>oggetto , che viene impostato su e su e utilizzato per disegnare un altro rettangolo. Di conseguenza, il pennello genera tessere con una larghezza pari a 25 pixel e un'altezza pari a 25 pixel.

La figura seguente mostra l'output prodotto dall'esempio:The following illustration shows the output that the example produces:

![Rettangolo con quarantotto ciliegie che mostrano un TileBrush affiancato con un Viewport.](./media/how-to-set-the-tile-size-for-a-tilebrush/25-x-25-viewport-tilebrush.png)

[!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]

Gli esempi precedenti fanno parte di un esempio più esaustivo. Per l'esempio completo, vedere [Esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush).

Sebbene in <xref:System.Windows.Media.ImageBrush> questo esempio <xref:System.Windows.Media.TileBrush.Viewport%2A> <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> venga utilizzata la classe <xref:System.Windows.Media.TileBrush> , le proprietà <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush>si comportano in modo identico per gli altri oggetti, ovvero for e . Per ulteriori <xref:System.Windows.Media.ImageBrush> informazioni su <xref:System.Windows.Media.TileBrush> e sugli altri oggetti, vedere [Disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.TileBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Creare modelli di elementi affiancati differenti con un TileBrush](how-to-create-different-tile-patterns-with-a-tilebrush.md)
