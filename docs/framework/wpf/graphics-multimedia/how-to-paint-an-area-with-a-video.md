---
title: "Procedura: Disegnare un'area con un video"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
ms.openlocfilehash: be09d1310847cd7214ea795a704c25d994f07b7a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151177"
---
# <a name="how-to-paint-an-area-with-a-video"></a>Procedura: Disegnare un'area con un video
In questo esempio viene illustrato come disegnare un'area con supporto di memorizzazione. Un modo per disegnare un'area con supporto consiste nell'utilizzare un <xref:System.Windows.Controls.MediaElement> insieme a un <xref:System.Windows.Media.VisualBrush>. Usare la <xref:System.Windows.Controls.MediaElement> per caricare e riprodurre i contenuti multimediali e quindi utilizzarla per impostare il <xref:System.Windows.Media.VisualBrush.Visual%2A> proprietà del <xref:System.Windows.Media.VisualBrush>. È quindi possibile usare il <xref:System.Windows.Media.VisualBrush> per disegnare un'area con elementi multimediali caricati.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa un' <xref:System.Windows.Controls.MediaElement> e una <xref:System.Windows.Media.VisualBrush> per disegnare il <xref:System.Windows.Controls.TextBlock.Foreground%2A> di un <xref:System.Windows.Controls.TextBlock> controllo con i video. Questo esempio viene impostato il <xref:System.Windows.Controls.MediaElement.IsMuted%2A> proprietà del <xref:System.Windows.Controls.MediaElement> a `true` in modo che non riprodurre suoni.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a>Esempio  
 In quanto <xref:System.Windows.Media.VisualBrush> eredita il <xref:System.Windows.Media.TileBrush> (classe), offre diverse modalità di affiancamento. Impostando il <xref:System.Windows.Media.TileBrush.TileMode%2A> proprietà di un <xref:System.Windows.Media.VisualBrush> a <xref:System.Windows.Media.TileMode.Tile> e impostando il <xref:System.Windows.Media.TileBrush.Viewport%2A> proprietà su un valore più piccola dell'area da disegnare, è possibile creare un modello affiancato.  
  
 Nell'esempio seguente è identico all'esempio precedente, tranne il fatto che il <xref:System.Windows.Media.VisualBrush> genera un modello dal video.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](~/samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 Per informazioni su come aggiungere un file di contenuto, ad esempio un file multimediale, per l'applicazione, vedere [WPF Application Resource, contenuto e i file di dati](../app-development/wpf-application-resource-content-and-data-files.md). Quando si aggiunge un file multimediale, è necessario aggiungerlo come un file di contenuto, non come un file di risorse.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.VisualBrush>
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Panoramica sugli oggetti TileBrush](tilebrush-overview.md)
- [Panoramica delle funzionalità multimediali](multimedia-overview.md)
