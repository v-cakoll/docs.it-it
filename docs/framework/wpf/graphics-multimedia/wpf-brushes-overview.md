---
title: Cenni preliminari sui pennelli di WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 29f0bc77306df5639c188295f9f5dff7f18b4706
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962852"
---
# <a name="wpf-brushes-overview"></a>Cenni preliminari sui pennelli di WPF
Tutto ciò che è visibile sullo schermo è visibile perché è stato disegnato da un pennello. Ad esempio, viene utilizzato un pennello per descrivere lo sfondo di un pulsante, il primo piano del testo e il riempimento di una forma. In questo argomento vengono presentati i concetti relativi [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] al disegno con i pennelli e vengono forniti esempi. I pennelli consentono di disegnare oggetti [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] con colori semplici a tinta unita, fino a set complessi di motivi e immagini.  
  
<a name="paintingwithbrush"></a>   
## <a name="painting-with-a-brush"></a>Disegno con un pennello  
 <xref:System.Windows.Media.Brush> "Disegna" un'area con l'output. Pennelli diversi hanno tipi di output diversi. Alcuni pennelli disegnano un'area con un colore a tinta unita, altri con una sfumatura, un motivo, un'immagine o un disegno. Nella figura seguente vengono illustrati esempi di ognuno dei <xref:System.Windows.Media.Brush> diversi tipi.  
  
 ![Tipi di pennello](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Esempi di pennelli  
  
 La maggior parte degli oggetti visivi consente di specificare il modo in cui vengono disegnati. Nella tabella seguente sono elencati alcuni oggetti e proprietà comuni con cui è possibile utilizzare <xref:System.Windows.Media.Brush>.  
  
|Classe|Proprietà dei pennelli|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 Nelle sezioni seguenti vengono descritti i <xref:System.Windows.Media.Brush> diversi tipi e viene fornito un esempio di ciascuna di esse.  
  
<a name="paintwithsolidcolorbrush"></a>   
## <a name="paint-with-a-solid-color"></a>Disegna con un colore a tinta unita  
 Disegna un'area con un oggetto a tinta unita <xref:System.Windows.Media.Color>. <xref:System.Windows.Media.SolidColorBrush> Esistono diversi modi per specificare l'oggetto di un <xref:System.Windows.Media.SolidColorBrush.Color%2A> oggetto <xref:System.Windows.Media.SolidColorBrush>. ad esempio, è possibile specificare i relativi canali alfa, rosso, blu e verde oppure utilizzare uno dei colori <xref:System.Windows.Media.Colors> predefiniti forniti dalla classe.  
  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.SolidColorBrush> un oggetto per <xref:System.Windows.Shapes.Shape.Fill%2A> disegnare l' <xref:System.Windows.Shapes.Rectangle>oggetto di un oggetto. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando un oggetto SolidColorBrush](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
Rettangolo disegnato usando un oggetto SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Per ulteriori informazioni sulla <xref:System.Windows.Media.SolidColorBrush> classe, vedere Cenni preliminari sul [disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>   
## <a name="paint-with-a-linear-gradient"></a>Disegnare con una sfumatura lineare  
 <xref:System.Windows.Media.LinearGradientBrush> Disegna un'area con una sfumatura lineare. Una sfumatura lineare combina due o più colori su una riga, l'asse delle sfumature. Usare <xref:System.Windows.Media.GradientStop> gli oggetti per specificare i colori nella sfumatura e le rispettive posizioni.  
  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.LinearGradientBrush> un oggetto per <xref:System.Windows.Shapes.Shape.Fill%2A> disegnare l' <xref:System.Windows.Shapes.Rectangle>oggetto di un oggetto. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando un oggetto LinearGradientBrush](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Rettangolo disegnato usando un oggetto LinearGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Per ulteriori informazioni sulla <xref:System.Windows.Media.LinearGradientBrush> classe, vedere Cenni preliminari sul [disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>   
## <a name="paint-with-a-radial-gradient"></a>Disegnare con una sfumatura radiale  
 <xref:System.Windows.Media.RadialGradientBrush> Disegna un'area con una sfumatura radiale. Una sfumatura radiale unisce due o più colori in un cerchio. Come per la <xref:System.Windows.Media.LinearGradientBrush> classe, gli oggetti <xref:System.Windows.Media.GradientStop> vengono usati per specificare i colori nella sfumatura e le rispettive posizioni.  
  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.RadialGradientBrush> un oggetto per <xref:System.Windows.Shapes.Shape.Fill%2A> disegnare l' <xref:System.Windows.Shapes.Rectangle>oggetto di un oggetto. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando un RadialGradientBrush](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Rettangolo disegnato usando un RadialGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Per ulteriori informazioni sulla <xref:System.Windows.Media.RadialGradientBrush> classe, vedere Cenni preliminari sul [disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>   
## <a name="paint-with-an-image"></a>Disegnare con un'immagine  
 Disegna un'area con un oggetto <xref:System.Windows.Media.ImageSource>. <xref:System.Windows.Media.ImageBrush>  
  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.ImageBrush> un oggetto per <xref:System.Windows.Shapes.Shape.Fill%2A> disegnare l' <xref:System.Windows.Shapes.Rectangle>oggetto di un oggetto. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato da ImageBrush](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Rettangolo disegnato usando un'immagine  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Per altre informazioni sulla <xref:System.Windows.Media.ImageBrush> classe, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>   
## <a name="paint-with-a-drawing"></a>Disegnare con un disegno  
 Disegna un'area con un oggetto <xref:System.Windows.Media.Drawing>. <xref:System.Windows.Media.DrawingBrush> Un <xref:System.Windows.Media.Drawing> oggetto può contenere forme, immagini, testo e supporti.  
  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.DrawingBrush> un oggetto per <xref:System.Windows.Shapes.Shape.Fill%2A> disegnare l' <xref:System.Windows.Shapes.Rectangle>oggetto di un oggetto. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando DrawingBrush](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Rettangolo disegnato usando DrawingBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Per altre informazioni sulla <xref:System.Windows.Media.DrawingBrush> classe, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>   
## <a name="paint-with-a-visual"></a>Disegnare con un oggetto visivo  
 Disegna un'area con un <xref:System.Windows.Media.Visual> oggetto. <xref:System.Windows.Media.VisualBrush> Esempi di oggetti visivi <xref:System.Windows.Controls.Button>sono <xref:System.Windows.Controls.Page>, e <xref:System.Windows.Controls.MediaElement>. Un <xref:System.Windows.Media.VisualBrush> consente inoltre di proiettare contenuto da una parte dell'applicazione in un'altra area; è molto utile per la creazione di effetti di reflection e l'ingrandimento di parti dello schermo.  
  
 Nell'esempio seguente viene usato <xref:System.Windows.Media.VisualBrush> un oggetto per <xref:System.Windows.Shapes.Shape.Fill%2A> disegnare l' <xref:System.Windows.Shapes.Rectangle>oggetto di un oggetto. Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato utilizzando VisualBrush](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Rettangolo disegnato utilizzando VisualBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Per altre informazioni sulla <xref:System.Windows.Media.VisualBrush> classe, vedere [disegnare con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>   
## <a name="paint-using-predefined-and-system-brushes"></a>Disegno usando pennelli di sistema e predefiniti  
 Per praticità, Windows Presentation Foundation (WPF) fornisce un set di pennelli di sistema e predefiniti che è possibile utilizzare per disegnare oggetti.  
  
- Per un elenco dei pennelli predefiniti disponibili, vedere la <xref:System.Windows.Media.Brushes> classe. Per un esempio che illustra come usare un pennello predefinito, vedere [disegnare un'area con un colore a tinta unita](how-to-paint-an-area-with-a-solid-color.md).  
  
- Per un elenco dei pennelli di sistema disponibili, <xref:System.Windows.SystemColors> vedere la classe. Per un esempio, vedere [disegnare un'area con un pennello di sistema](how-to-paint-an-area-with-a-system-brush.md).  
  
<a name="commonbrushfeatures"></a>   
## <a name="common-brush-features"></a>Funzionalità di pennelli comuni  
 <xref:System.Windows.Media.Brush>gli oggetti forniscono <xref:System.Windows.Media.Brush.Opacity%2A> una proprietà che può essere utilizzata per rendere trasparente o parzialmente trasparente un pennello. Il valore 0 rende un pennello completamente trasparente, mentre un <xref:System.Windows.Media.Brush.Opacity%2A> valore pari a 1 rende un pennello completamente opaco. <xref:System.Windows.Media.Brush.Opacity%2A> Nell'esempio seguente viene utilizzata <xref:System.Windows.Media.Brush.Opacity%2A> la proprietà per <xref:System.Windows.Media.SolidColorBrush> rendere opaco il 25%.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Se il pennello contiene colori parzialmente trasparenti, il valore di opacità del colore viene combinato attraverso la moltiplicazione con il valore di opacità del pennello. Se, ad esempio, un pennello ha un valore di opacità pari a 0,5 e un colore usato nel pennello ha anche un valore di opacità pari a 0,5, il colore di output avrà un valore di opacità di 0,25.  
  
> [!NOTE]
> È più efficiente modificare il valore di opacità di un pennello rispetto a modificare l'opacità di un intero elemento usando la relativa <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> proprietà.  
  
 È possibile ruotare, ridimensionare, inclinare e tradurre il contenuto di un pennello utilizzando <xref:System.Windows.Media.Brush.Transform%2A> le <xref:System.Windows.Media.Brush.RelativeTransform%2A> relative proprietà o. Per altre informazioni, vedere [Cenni preliminari sulla trasformazione](brush-transformation-overview.md)di pennelli.  
  
 Poiché si tratta <xref:System.Windows.Media.Animation.Animatable> di oggetti <xref:System.Windows.Media.Brush> , gli oggetti possono essere animati. Per altre informazioni, vedere [Panoramica dell'animazione](animation-overview.md).  
  
<a name="freezable_features"></a>   
### <a name="freezable-features"></a>Funzionalità di Freezable  
 Poiché eredita dalla <xref:System.Windows.Freezable> classe, la <xref:System.Windows.Media.Brush> classe fornisce diverse funzionalità speciali: <xref:System.Windows.Media.Brush> gli oggetti possono essere dichiarati come [risorse](../advanced/xaml-resources.md), condivisi tra più oggetti e clonati. Inoltre, tutti i <xref:System.Windows.Media.Brush> tipi eccetto <xref:System.Windows.Media.VisualBrush> possono essere resi di sola lettura per migliorare le prestazioni e rendere thread-safe.  
  
 Per ulteriori informazioni sulle diverse funzionalità fornite dagli <xref:System.Windows.Freezable> oggetti, vedere Cenni preliminari sugli [oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Per ulteriori informazioni sul motivo <xref:System.Windows.Media.VisualBrush> per cui gli oggetti non possono essere <xref:System.Windows.Media.VisualBrush> bloccati, vedere la pagina tipo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973) (Esempio di pennelli)
- [Esempio di ImageBrush](https://go.microsoft.com/fwlink/?LinkID=160005)
- [Esempio VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049)
- [Procedure relative alle proprietà](brushes-how-to-topics.md)
- [Altri suggerimenti relativi alle prestazioni](../advanced/optimizing-performance-other-recommendations.md)
