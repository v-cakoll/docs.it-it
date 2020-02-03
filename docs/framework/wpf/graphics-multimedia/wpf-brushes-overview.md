---
title: Panoramica sui pennelli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 18ca9b79a6ee801638a54fcb227c44e9aea21fd0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746212"
---
# <a name="wpf-brushes-overview"></a>Cenni preliminari sui pennelli di WPF
Tutto ciò che è visibile sullo schermo è visibile perché è stato disegnato da un pennello. Ad esempio, viene utilizzato un pennello per descrivere lo sfondo di un pulsante, il primo piano del testo e il riempimento di una forma. In questo argomento vengono presentati i concetti relativi al disegno con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] pennelli e vengono forniti esempi. I pennelli consentono di disegnare oggetti [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] con colori semplici a tinta unita, fino a set complessi di motivi e immagini.  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>Disegno con un pennello  
 Un <xref:System.Windows.Media.Brush> "disegna" un'area con l'output. Pennelli diversi hanno tipi di output diversi. Alcuni pennelli disegnano un'area con un colore a tinta unita, altri con una sfumatura, un motivo, un'immagine o un disegno. Nella figura seguente vengono illustrati esempi di ognuno dei diversi tipi di <xref:System.Windows.Media.Brush>.  
  
 ![Tipi di pennello](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Esempi di pennelli  
  
 La maggior parte degli oggetti visivi consente di specificare il modo in cui vengono disegnati. Nella tabella seguente sono elencati alcuni oggetti e proprietà comuni con i quali è possibile utilizzare un <xref:System.Windows.Media.Brush>.  
  
|Classe|Proprietà dei pennelli|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 Nelle sezioni seguenti vengono descritti i diversi tipi di <xref:System.Windows.Media.Brush> e viene fornito un esempio di ciascuna di esse.  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>Disegna con un colore a tinta unita  
 Un <xref:System.Windows.Media.SolidColorBrush> disegna un'area con una <xref:System.Windows.Media.Color>a tinta unita. Esistono diversi modi per specificare il <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush>. ad esempio, è possibile specificare i relativi canali alfa, rosso, blu e verde oppure utilizzare uno dei colori predefiniti forniti dalla classe <xref:System.Windows.Media.Colors>.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.SolidColorBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando un oggetto SolidColorBrush](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
Rettangolo disegnato usando un oggetto SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Per ulteriori informazioni sulla classe <xref:System.Windows.Media.SolidColorBrush>, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>Disegnare con una sfumatura lineare  
 Un <xref:System.Windows.Media.LinearGradientBrush> disegna un'area con una sfumatura lineare. Una sfumatura lineare combina due o più colori su una riga, l'asse delle sfumature. Usare <xref:System.Windows.Media.GradientStop> oggetti per specificare i colori nella sfumatura e le rispettive posizioni.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.LinearGradientBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando un oggetto LinearGradientBrush](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Rettangolo disegnato usando un oggetto LinearGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Per ulteriori informazioni sulla classe <xref:System.Windows.Media.LinearGradientBrush>, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>Disegnare con una sfumatura radiale  
 Un <xref:System.Windows.Media.RadialGradientBrush> disegna un'area con una sfumatura radiale. Una sfumatura radiale unisce due o più colori in un cerchio. Come per la classe <xref:System.Windows.Media.LinearGradientBrush>, è possibile usare <xref:System.Windows.Media.GradientStop> oggetti per specificare i colori nella sfumatura e le rispettive posizioni.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.RadialGradientBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando un RadialGradientBrush](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Rettangolo disegnato usando un RadialGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Per ulteriori informazioni sulla classe <xref:System.Windows.Media.RadialGradientBrush>, vedere [Cenni preliminari sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>Disegnare con un'immagine  
 Un <xref:System.Windows.Media.ImageBrush> disegna un'area con una <xref:System.Windows.Media.ImageSource>.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.ImageBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato da ImageBrush](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Rettangolo disegnato usando un'immagine  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Per altre informazioni sulla classe <xref:System.Windows.Media.ImageBrush>, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>Disegnare con un disegno  
 Un <xref:System.Windows.Media.DrawingBrush> disegna un'area con una <xref:System.Windows.Media.Drawing>. Un <xref:System.Windows.Media.Drawing> può contenere forme, immagini, testo e supporti.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.DrawingBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando DrawingBrush](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Rettangolo disegnato usando DrawingBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Per altre informazioni sulla classe <xref:System.Windows.Media.DrawingBrush>, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>Disegnare con un oggetto visivo  
 Un <xref:System.Windows.Media.VisualBrush> disegna un'area con un oggetto <xref:System.Windows.Media.Visual>. Esempi di oggetti visivi includono <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Page>e <xref:System.Windows.Controls.MediaElement>. Un <xref:System.Windows.Media.VisualBrush> consente inoltre di proiettare il contenuto da una parte dell'applicazione in un'altra area; è molto utile per la creazione di effetti di reflection e l'ingrandimento di parti dello schermo.  
  
 Nell'esempio seguente viene usato un <xref:System.Windows.Media.VisualBrush> per disegnare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato utilizzando VisualBrush](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Rettangolo disegnato utilizzando VisualBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Per altre informazioni sulla classe <xref:System.Windows.Media.VisualBrush>, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>Disegno usando pennelli di sistema e predefiniti  
 Per praticità, Windows Presentation Foundation (WPF) fornisce un set di pennelli di sistema e predefiniti che è possibile utilizzare per disegnare oggetti.  
  
- Per un elenco dei pennelli predefiniti disponibili, vedere la classe <xref:System.Windows.Media.Brushes>. Per un esempio che illustra come usare un pennello predefinito, vedere [disegnare un'area con un colore a tinta unita](how-to-paint-an-area-with-a-solid-color.md).  
  
- Per un elenco dei pennelli di sistema disponibili, vedere la classe <xref:System.Windows.SystemColors>. Per un esempio, vedere [disegnare un'area con un pennello di sistema](how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>Funzionalità di pennelli comuni  
 gli oggetti <xref:System.Windows.Media.Brush> forniscono una proprietà <xref:System.Windows.Media.Brush.Opacity%2A> che può essere utilizzata per rendere trasparente o parzialmente trasparente un pennello. Un <xref:System.Windows.Media.Brush.Opacity%2A> valore 0 rende un pennello completamente trasparente, mentre un valore <xref:System.Windows.Media.Brush.Opacity%2A> 1 rende un pennello completamente opaco. Nell'esempio seguente viene utilizzata la proprietà <xref:System.Windows.Media.Brush.Opacity%2A> per rendere opaca <xref:System.Windows.Media.SolidColorBrush> il 25%.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Se il pennello contiene colori parzialmente trasparenti, il valore di opacità del colore viene combinato attraverso la moltiplicazione con il valore di opacità del pennello. Se, ad esempio, un pennello ha un valore di opacità pari a 0,5 e un colore usato nel pennello ha anche un valore di opacità pari a 0,5, il colore di output avrà un valore di opacità di 0,25.  
  
> [!NOTE]
> È più efficiente modificare il valore di opacità di un pennello rispetto a modificare l'opacità di un intero elemento usando la relativa proprietà <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType>.  
  
 È possibile ruotare, ridimensionare, inclinare e tradurre il contenuto di un pennello usando le proprietà <xref:System.Windows.Media.Brush.Transform%2A> o <xref:System.Windows.Media.Brush.RelativeTransform%2A>. Per altre informazioni, vedere [Cenni preliminari sulla trasformazione di pennelli](brush-transformation-overview.md).  
  
 Poiché si tratta di oggetti <xref:System.Windows.Media.Animation.Animatable>, <xref:System.Windows.Media.Brush> oggetti possono essere animati. Per altre informazioni, vedere [Panoramica dell'animazione](animation-overview.md).  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Funzionalità di Freezable  
 Poiché eredita dalla classe <xref:System.Windows.Freezable>, la classe <xref:System.Windows.Media.Brush> fornisce diverse funzionalità speciali: <xref:System.Windows.Media.Brush> oggetti possono essere dichiarati come [risorse](../../../desktop-wpf/fundamentals/xaml-resources-define.md), condivisi tra più oggetti e clonati. Inoltre, tutti i tipi di <xref:System.Windows.Media.Brush> ad eccezione di <xref:System.Windows.Media.VisualBrush> possono essere resi di sola lettura per migliorare le prestazioni e rendere thread-safe.  
  
 Per ulteriori informazioni sulle diverse funzionalità fornite dagli oggetti <xref:System.Windows.Freezable>, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Per ulteriori informazioni sui motivi per cui non è possibile bloccare gli oggetti <xref:System.Windows.Media.VisualBrush>, vedere la pagina relativa al tipo di <xref:System.Windows.Media.VisualBrush>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli)
- [Esempio di ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [Esempio VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
- [Procedure relative alla struttura ad albero e alla serializzazione degli elementi](brushes-how-to-topics.md)
- [Altri suggerimenti relativi alle prestazioni](../advanced/optimizing-performance-other-recommendations.md)
