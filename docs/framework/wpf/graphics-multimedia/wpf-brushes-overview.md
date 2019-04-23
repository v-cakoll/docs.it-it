---
title: Cenni preliminari sui pennelli di WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 14e3d095d50f41e5b20a79d76c464bcf28c99327
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132210"
---
# <a name="wpf-brushes-overview"></a>Cenni preliminari sui pennelli di WPF
Tutti gli elementi visibili sullo schermo è visibili perché sono stati disegnati con un pennello. Ad esempio, un pennello viene usato per descrivere lo sfondo di un pulsante, il primo piano del testo e il riempimento di una forma. In questo argomento introduce i concetti di disegno con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] pennelli e vengono forniti esempi. I pennelli consentono di disegnare oggetti [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] con colori semplici a tinta unita, fino a set complessi di motivi e immagini.  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>Disegno con un pennello  
 Oggetto <xref:System.Windows.Media.Brush> "disegna" un'area con il proprio output. Pennelli diversi hanno tipi diversi di output. Alcune pennelli disegnano un'area con un colore a tinta unita, altri utenti con una sfumatura, modello, immagine o disegno. La figura seguente mostra alcuni esempi della ognuno dei diversi <xref:System.Windows.Media.Brush> tipi.  
  
 ![Tipi di pennello](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Esempi di pennello  
  
 La maggior parte degli oggetti visivi consentono di specificare la modalità di disegno. La tabella seguente elenca alcuni oggetti e proprietà a cui è possibile utilizzare comuni un <xref:System.Windows.Media.Brush>.  
  
|Classe|Proprietà dei pennelli|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 Le sezioni seguenti descrivono le diverse <xref:System.Windows.Media.Brush> tipi e viene fornito un esempio della ognuno.  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>Disegno con colori a tinta unita  
 Oggetto <xref:System.Windows.Media.SolidColorBrush> disegna un'area con un solido <xref:System.Windows.Media.Color>. Esistono diversi modi per specificare il <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush>: ad esempio, è possibile specificare i canali alfa, rossi, blu e verde o usare uno dei colore predefiniti fornito dal <xref:System.Windows.Media.Colors> classe.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.SolidColorBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. La figura seguente mostra il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando SolidColorBrush](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
Rettangolo disegnato usando SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Per altre informazioni sul <xref:System.Windows.Media.SolidColorBrush> classe, vedere [disegno con colori a tinta unita e sfumature Panoramica](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>Disegno con una sfumatura lineare  
 Oggetto <xref:System.Windows.Media.LinearGradientBrush> disegna un'area con una sfumatura lineare. Una sfumatura lineare unisce due o più dei colori in una riga, l'asse delle sfumature. Si utilizza <xref:System.Windows.Media.GradientStop> oggetti per specificare i colori nella sfumatura e le relative posizioni.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.LinearGradientBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. La figura seguente mostra il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando LinearGradientBrush](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Rettangolo disegnato usando LinearGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Per altre informazioni sul <xref:System.Windows.Media.LinearGradientBrush> classe, vedere [disegno con colori a tinta unita e sfumature Panoramica](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>Disegno con una sfumatura radiale  
 Oggetto <xref:System.Windows.Media.RadialGradientBrush> disegna un'area con una sfumatura radiale. Una sfumatura radiale unisce due o più dei colori in un cerchio. Come con le <xref:System.Windows.Media.LinearGradientBrush> (classe), è utilizzare <xref:System.Windows.Media.GradientStop> oggetti per specificare i colori nella sfumatura e le relative posizioni.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.RadialGradientBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. La figura seguente mostra il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando RadialGradientBrush](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Rettangolo disegnato usando RadialGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Per altre informazioni sul <xref:System.Windows.Media.RadialGradientBrush> classe, vedere [disegno con colori a tinta unita e sfumature Panoramica](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>Disegno con un'immagine  
 Un' <xref:System.Windows.Media.ImageBrush> disegna un'area con un <xref:System.Windows.Media.ImageSource>.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.ImageBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. La figura seguente mostra il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando ImageBrush](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Rettangolo disegnato usando un'immagine  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Per altre informazioni sul <xref:System.Windows.Media.ImageBrush> classe, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>Disegno con un disegno  
 Oggetto <xref:System.Windows.Media.DrawingBrush> disegna un'area con un <xref:System.Windows.Media.Drawing>. Oggetto <xref:System.Windows.Media.Drawing> può contenere le forme, immagini, testo e supporti.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.DrawingBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. La figura seguente mostra il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando DrawingBrush](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Rettangolo disegnato usando DrawingBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Per altre informazioni sul <xref:System.Windows.Media.DrawingBrush> classe, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>Disegno con un oggetto visivo  
 Oggetto <xref:System.Windows.Media.VisualBrush> disegna un'area con un <xref:System.Windows.Media.Visual> oggetto. Esempi di oggetti visivi <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>, e <xref:System.Windows.Controls.MediaElement>. Oggetto <xref:System.Windows.Media.VisualBrush> consente inoltre di contenuto del progetto da una parte dell'applicazione in un'altra area; è molto utile per la creazione di effetti di reflection e ingrandimento delle parti dello schermo.  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.VisualBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. La figura seguente mostra il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando VisualBrush](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Rettangolo disegnato usando VisualBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Per altre informazioni sul <xref:System.Windows.Media.VisualBrush> classe, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>Disegnare con pennelli di sistema e predefiniti  
 Per praticità, Windows Presentation Foundation (WPF) fornisce un set di pennelli predefiniti e sistema che è possibile utilizzare per disegnare gli oggetti.  
  
-   Per un elenco dei pennelli predefiniti disponibili, vedere il <xref:System.Windows.Media.Brushes> classe. Per un esempio che illustra come usare un pennello predefinito, vedere [disegnare un'Area con colori a tinta unita](how-to-paint-an-area-with-a-solid-color.md).  
  
-   Per un elenco dei pennelli di sistema disponibili, vedere il <xref:System.Windows.SystemColors> classe. Per un esempio, vedere [disegnare un'Area con un pennello di sistema](how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>Funzionalità comuni dei pennelli  
 <xref:System.Windows.Media.Brush> gli oggetti forniscono un <xref:System.Windows.Media.Brush.Opacity%2A> proprietà che può essere usata per rendere un pennello trasparente o parzialmente trasparenti. Un' <xref:System.Windows.Media.Brush.Opacity%2A> valore pari a 0 lo rende completamente trasparente, mentre un <xref:System.Windows.Media.Brush.Opacity%2A> valore pari a 1 lo rende completamente opaco. L'esempio seguente usa il <xref:System.Windows.Media.Brush.Opacity%2A> proprietà per rendere un <xref:System.Windows.Media.SolidColorBrush> opaco al 25%.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Se il pennello contiene colori parzialmente trasparenti, il valore di opacità del colore viene combinato, tramite la moltiplicazione con il valore di opacità del pennello. Ad esempio, se un pennello ha un valore di opacità pari a 0,5 e un colore utilizzato per il pennello ha anche un valore di opacità pari a 0,5, il colore di output ha un valore di opacità pari 0,25.  
  
> [!NOTE]
>  È più efficiente per cambiare il valore di opacità di un pennello, piuttosto che modificare l'opacità di un intero elemento usando relativo <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> proprietà.  
  
 È possibile ruotare, ridimensionare, inclinare e traslare il contenuto del pennello utilizzando relativi <xref:System.Windows.Media.Brush.Transform%2A> o <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà. Per altre informazioni, vedere [Panoramica di trasformazione Brush](brush-transformation-overview.md).  
  
 Essendo <xref:System.Windows.Media.Animation.Animatable> oggetti, <xref:System.Windows.Media.Brush> oggetti possono essere animati. Per altre informazioni, vedere [Panoramica dell'animazione](animation-overview.md).  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Funzionalità di Freezable  
 Poiché eredita dal <xref:System.Windows.Freezable> (classe), il <xref:System.Windows.Media.Brush> classe fornisce diverse funzionalità speciali: <xref:System.Windows.Media.Brush> gli oggetti possono essere dichiarati come [risorse](../advanced/xaml-resources.md), condivisi tra più oggetti e la clonazione. Inoltre, tutti i <xref:System.Windows.Media.Brush> tipi, ad eccezione <xref:System.Windows.Media.VisualBrush> può essere reso di sola lettura per migliorare le prestazioni e resi thread-safe.  
  
 Per altre informazioni sulle diverse funzionalità fornita da <xref:System.Windows.Freezable> oggetti, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Per altre informazioni sui motivi per cui <xref:System.Windows.Media.VisualBrush> gli oggetti non possono essere bloccati, vedere il <xref:System.Windows.Media.VisualBrush> pagina del tipo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli)
- [Esempio ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [Esempio VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
- [Procedure relative alle proprietà](brushes-how-to-topics.md)
- [Altri suggerimenti relativi alle prestazioni](../advanced/optimizing-performance-other-recommendations.md)
