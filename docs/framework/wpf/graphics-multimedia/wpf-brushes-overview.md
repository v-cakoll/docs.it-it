---
title: Panoramica dei pennelli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], about brushes
ms.assetid: ecea1955-420b-45c6-bf43-c1404c072c41
ms.openlocfilehash: 7a9474b392052900952f5b677ad94b16025de8dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186570"
---
# <a name="wpf-brushes-overview"></a>Cenni preliminari sui pennelli di WPF
Tutto ciò che è visibile sullo schermo è visibile perché è stato dipinto da un pennello. Ad esempio, un pennello viene utilizzato per descrivere lo sfondo di un pulsante, il primo piano del testo e il riempimento di una forma. In questo argomento vengono introdotti i concetti di pittura con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] pennelli e vengono forniti esempi. I pennelli consentono di disegnare oggetti [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] con colori semplici a tinta unita, fino a set complessi di motivi e immagini.  
  
<a name="paintingwithbrush"></a>
## <a name="painting-with-a-brush"></a>Dipingere con un pennello  
 Un <xref:System.Windows.Media.Brush> "dipinge" un'area con la sua uscita. Pennelli diversi hanno diversi tipi di output. Alcuni pennelli disegnano un'area con un colore a tinta unita, altri con una sfumatura, un motivo, un'immagine o un disegno. Nella figura seguente vengono illustrati <xref:System.Windows.Media.Brush> esempi di ognuno dei diversi tipi.  
  
 ![Tipi di pennello](./media/graphicsmm-brushtypes.jpg "graphicsmm_brushtypes")  
Esempi di pennelli  
  
 La maggior parte degli oggetti visivi consente di specificare la modalità di disegno. Nella tabella seguente sono elencati alcuni oggetti <xref:System.Windows.Media.Brush>e proprietà comuni con cui è possibile utilizzare un oggetto .  
  
|Classe|Proprietà dei pennelli|  
|-----------|----------------------|  
|<xref:System.Windows.Controls.Border>|<xref:System.Windows.Controls.Border.BorderBrush%2A>, <xref:System.Windows.Controls.Border.Background%2A>|  
|<xref:System.Windows.Controls.Control>|<xref:System.Windows.Controls.Control.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>|  
|<xref:System.Windows.Controls.Panel>|<xref:System.Windows.Controls.Panel.Background%2A>|  
|<xref:System.Windows.Media.Pen>|<xref:System.Windows.Media.Pen.Brush%2A>|  
|<xref:System.Windows.Shapes.Shape>|<xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>|  
|<xref:System.Windows.Controls.TextBlock>|<xref:System.Windows.Controls.TextBlock.Background%2A>|  
  
 Nelle sezioni seguenti <xref:System.Windows.Media.Brush> vengono descritti i diversi tipi e ne viene fornito un esempio.  
  
<a name="paintwithsolidcolorbrush"></a>
## <a name="paint-with-a-solid-color"></a>Dipingere con un colore a tinta unita  
 A <xref:System.Windows.Media.SolidColorBrush> dipinge un'area con un solido <xref:System.Windows.Media.Color>. Esistono diversi modi per specificare <xref:System.Windows.Media.SolidColorBrush.Color%2A> il <xref:System.Windows.Media.SolidColorBrush>di un : ad esempio, è possibile specificare i canali alfa, rosso, blu e verde o utilizzare uno dei colori predefiniti forniti dalla <xref:System.Windows.Media.Colors> classe.  
  
 Nell'esempio riportato di seguito viene utilizzato un <xref:System.Windows.Media.SolidColorBrush> oggetto per disegnare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>oggetto . Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando SolidColorBrush](./media/graphicsmm-brush-ovw-solidcolorbrush.png "graphicsmm_brush_ovw_solidcolorbrush")  
A Rectangle painted using a SolidColorBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmsolidcolorbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmsolidcolorbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMSolidColorBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmsolidcolorbrushexampleinline)]  
  
 Per ulteriori informazioni <xref:System.Windows.Media.SolidColorBrush> sulla classe , vedere Cenni preliminari sul [disegno con colori a tinta unita e gradienti](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithlineargradientbrush"></a>
## <a name="paint-with-a-linear-gradient"></a>Disegnare con una sfumatura lineare  
 Un <xref:System.Windows.Media.LinearGradientBrush> oggetto disegna un'area con una sfumatura lineare. Una sfumatura lineare fonde due o più colori su una linea, l'asse delle sfumature. Gli <xref:System.Windows.Media.GradientStop> oggetti consentono di specificare i colori nel gradiente e le relative posizioni.  
  
 Nell'esempio riportato di seguito viene utilizzato un <xref:System.Windows.Media.LinearGradientBrush> oggetto per disegnare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>oggetto . Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando LinearGradientBrush](./media/graphicsmm-brush-ovw-lineargradientbrush.jpg "graphicsmm_brush_ovw_lineargradientbrush")  
Oggetto Rectangle disegnato usando un LinearGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmlineargradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmlineargradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMLinearGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmlineargradientbrushexampleinline)]  
  
 Per ulteriori informazioni <xref:System.Windows.Media.LinearGradientBrush> sulla classe , vedere Cenni preliminari sul [disegno con colori a tinta unita e gradienti](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithradialgradientbrush"></a>
## <a name="paint-with-a-radial-gradient"></a>Disegnare con un gradiente radiale  
 Un <xref:System.Windows.Media.RadialGradientBrush> oggetto disegna un'area con una sfumatura radiale. Una sfumatura radiale fonde due o più colori in un cerchio. Come per <xref:System.Windows.Media.LinearGradientBrush> la classe, si utilizzano <xref:System.Windows.Media.GradientStop> gli oggetti per specificare i colori nel gradiente e le relative posizioni.  
  
 Nell'esempio riportato di seguito viene utilizzato un <xref:System.Windows.Media.RadialGradientBrush> oggetto per disegnare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>oggetto . Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando RadialGradientBrush](./media/graphicsmm-brush-ovw-radialgradientbrush.jpg "graphicsmm_brush_ovw_radialgradientbrush")  
Oggetto Rectangle disegnato usando un RadialGradientBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmradialgradientbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmradialgradientbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMRadialGradientBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmradialgradientbrushexampleinline)]  
  
 Per ulteriori informazioni <xref:System.Windows.Media.RadialGradientBrush> sulla classe , vedere Cenni preliminari sul [disegno con colori a tinta unita e gradienti](painting-with-solid-colors-and-gradients-overview.md).  
  
<a name="paintwithimage"></a>
## <a name="paint-with-an-image"></a>Dipingere con un'immagine  
 Un <xref:System.Windows.Media.ImageBrush> dipinge un'area con un <xref:System.Windows.Media.ImageSource>oggetto .  
  
 Nell'esempio riportato di seguito viene utilizzato un <xref:System.Windows.Media.ImageBrush> oggetto per disegnare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>oggetto . Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando ImageBrush](./media/graphicsmm-brush-ovw-imagebrush.jpg "graphicsmm_brush_ovw_imagebrush")  
Un rettangolo dipinto con un'immagine  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmimagebrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmimagebrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMImageBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmimagebrushexampleinline)]  
  
 Per ulteriori informazioni <xref:System.Windows.Media.ImageBrush> sulla classe , vedere [Disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithdrawing"></a>
## <a name="paint-with-a-drawing"></a>Dipingere con un disegno  
 Un <xref:System.Windows.Media.DrawingBrush> oggetto dipinge <xref:System.Windows.Media.Drawing>un'area con un oggetto . A <xref:System.Windows.Media.Drawing> può contenere forme, immagini, testo ed elementi multimediali.  
  
 Nell'esempio riportato di seguito viene utilizzato un <xref:System.Windows.Media.DrawingBrush> oggetto per disegnare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>oggetto . Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando DrawingBrush](./media/graphicsmm-brush-ovw-drawingbrush.jpg "graphicsmm_brush_ovw_drawingbrush")  
Oggetto Rectangle disegnato con un DrawingBrush  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmdrawingbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmdrawingbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmdrawingbrushexampleinline)]  
  
 Per ulteriori informazioni <xref:System.Windows.Media.DrawingBrush> sulla classe , vedere [Disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithvisual"></a>
## <a name="paint-with-a-visual"></a>Dipingere con un oggetto visivoPaint with a Visual  
 Un <xref:System.Windows.Media.VisualBrush> oggetto dipinge <xref:System.Windows.Media.Visual> un'area con un oggetto. Esempi di oggetti <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Page>Visual <xref:System.Windows.Controls.MediaElement>includono , , e . A <xref:System.Windows.Media.VisualBrush> consente inoltre di proiettare il contenuto da una parte dell'applicazione in un'altra area. è molto utile per creare effetti di riflessione e ingrandire parti dello schermo.  
  
 Nell'esempio riportato di seguito viene utilizzato un <xref:System.Windows.Media.VisualBrush> oggetto per disegnare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>oggetto . Nella figura seguente viene illustrato il rettangolo disegnato.  
  
 ![Rettangolo disegnato usando VisualBrush](./media/graphicsmm-brush-ovw-visualbrush.jpg "graphicsmm_brush_ovw_visualbrush")  
Oggetto Rectangle disegnato con un VisualBrushA  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTypesExample.cs#graphicsmmvisualbrushexampleinline)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtypesexample.vb#graphicsmmvisualbrushexampleinline)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMVisualBrushExampleInline](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTypesExample.xaml#graphicsmmvisualbrushexampleinline)]  
  
 Per ulteriori informazioni <xref:System.Windows.Media.VisualBrush> sulla classe , vedere [Disegno con immagini, disegni e oggetti visivi](painting-with-images-drawings-and-visuals.md).  
  
<a name="paintwithpredefinedbrushesandsystemcolors"></a>
## <a name="paint-using-predefined-and-system-brushes"></a>Disegnare utilizzando pennelli predefiniti e di sistema  
 Per comodità, Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (  
  
- Per un elenco dei pennelli predefiniti <xref:System.Windows.Media.Brushes> disponibili, consultate la classe. Per un esempio che illustra come utilizzare un pennello predefinito, consultate [Disegnare un'area con un colore a tinta unita.](how-to-paint-an-area-with-a-solid-color.md)  
  
- Per un elenco dei pennelli di <xref:System.Windows.SystemColors> sistema disponibili, consultate la classe. Per un esempio, consultate [Disegnare un'area con un pennello](how-to-paint-an-area-with-a-system-brush.md)di sistema.  
  
<a name="commonbrushfeatures"></a>
## <a name="common-brush-features"></a>Caratteristiche comuni del pennello  
 <xref:System.Windows.Media.Brush>Gli oggetti <xref:System.Windows.Media.Brush.Opacity%2A> forniscono una proprietà che può essere utilizzata per rendere trasparente o parzialmente trasparente un pennello. Un <xref:System.Windows.Media.Brush.Opacity%2A> valore pari a 0 rende <xref:System.Windows.Media.Brush.Opacity%2A> un pennello completamente trasparente, mentre un valore pari a 1 rende un pennello completamente opaco. Nell'esempio seguente <xref:System.Windows.Media.Brush.Opacity%2A> viene utilizzata <xref:System.Windows.Media.SolidColorBrush> la proprietà per rendere opaco il 25%.  
  
 [!code-xaml[BrushOverviewExamples_snip#OpacityExample1XAML](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/OpacityExample.xaml#opacityexample1xaml)]  
  
 [!code-csharp[BrushOverviewExamples_snip#OpacityExample1CSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/OpacityExample.cs#opacityexample1csharp)]  
  
 Se il pennello contiene colori parzialmente trasparenti, il valore di opacità del colore viene combinato attraverso la moltiplicazione con il valore di opacità del pennello. Ad esempio, se un pennello ha un valore di opacità pari a 0,5 e un colore utilizzato nel pennello ha anche un valore di opacità pari a 0,5, il colore di output ha un valore di opacità pari a 0,25.  
  
> [!NOTE]
> È più efficiente modificare il valore di opacità di un pennello piuttosto che modificare <xref:System.Windows.UIElement.Opacity%2A?displayProperty=nameWithType> l'opacità di un intero elemento usando la relativa proprietà.  
  
 È possibile ruotare, ridimensionare, inclinare e traslare il contenuto di un pennello usando le relative <xref:System.Windows.Media.Brush.Transform%2A> <xref:System.Windows.Media.Brush.RelativeTransform%2A> proprietà. Per ulteriori informazioni, consultate [Cenni preliminari sulla trasformazione del pennello.](brush-transformation-overview.md)  
  
 Poiché <xref:System.Windows.Media.Animation.Animatable> sono <xref:System.Windows.Media.Brush> oggetti, gli oggetti possono essere animati. Per ulteriori informazioni, consultate [Cenni preliminari sull'animazione.](animation-overview.md)  
  
<a name="freezable_features"></a>
### <a name="freezable-features"></a>Funzionalità di Freezable  
 Poiché eredita dalla <xref:System.Windows.Freezable> classe <xref:System.Windows.Media.Brush> , la classe <xref:System.Windows.Media.Brush> fornisce diverse funzionalità speciali: gli oggetti possono essere dichiarati come [risorse](../../../desktop-wpf/fundamentals/xaml-resources-define.md), condivisi tra più oggetti e clonati. Inoltre, tutti <xref:System.Windows.Media.Brush> i <xref:System.Windows.Media.VisualBrush> tipi tranne possono essere resi di sola lettura per migliorare le prestazioni e reso thread-safe.  
  
 Per ulteriori informazioni sulle diverse <xref:System.Windows.Freezable> funzionalità fornite dagli oggetti, vedere Cenni preliminari sugli [oggetti Freezable](../advanced/freezable-objects-overview.md).  
  
 Per ulteriori informazioni <xref:System.Windows.Media.VisualBrush> sui motivi per cui <xref:System.Windows.Media.VisualBrush> gli oggetti non possono essere bloccati, vedere la pagina del tipo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Brush>
- <xref:System.Windows.Media.Brushes>
- [Cenni sul disegno con colori a tinta unita e sfumature](painting-with-solid-colors-and-gradients-overview.md)
- [Disegnare con oggetti Image, Drawing e Visual](painting-with-images-drawings-and-visuals.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
- [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes) (Esempio di pennelli)
- [Esempio ImageBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [Esempio VisualBrush](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
- [Argomenti relativi alle procedure](brushes-how-to-topics.md)
- [Altri suggerimenti relativi alle prestazioni](../advanced/optimizing-performance-other-recommendations.md)
