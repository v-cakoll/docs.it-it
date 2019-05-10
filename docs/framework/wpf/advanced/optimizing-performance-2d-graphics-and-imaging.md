---
title: 'Ottimizzazione delle prestazioni: Grafica 2D e creazione di immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], performance
- drawing [WPF], optimizing performance
- imaging [WPF], optimizing performance
- shapes [WPF], optimizing performance
- 2-D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: 1869a5c274b3308e718ca550e8e43ff6a72d4b5d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611846"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Ottimizzazione delle prestazioni: Grafica 2D e creazione di immagini
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un'ampia gamma di funzionalità di grafica 2D e creazione di immagini che possono essere ottimizzate in base ai requisiti dell'applicazione. Questo argomento fornisce informazioni sull'ottimizzazione delle prestazioni in queste aree.  

<a name="Drawing_and_Shapes"></a>   
## <a name="drawing-and-shapes"></a>Disegno e forme  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono fornite entrambe <xref:System.Windows.Media.Drawing> e <xref:System.Windows.Shapes.Shape> oggetti per rappresentare il contenuto del disegno grafico. Tuttavia <xref:System.Windows.Media.Drawing> gli oggetti sono costrutti più semplici rispetto <xref:System.Windows.Shapes.Shape> degli oggetti e offrono prestazioni migliori.  
  
 Oggetto <xref:System.Windows.Shapes.Shape> consente di disegnare una forma grafica sullo schermo. Dal momento che sono derivati dal <xref:System.Windows.FrameworkElement> (classe), <xref:System.Windows.Shapes.Shape> oggetti possono essere utilizzati all'interno di pannelli e nella maggior parte dei controlli.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre diversi livelli di accesso alla grafica e ai servizi di rendering. Al livello superiore, <xref:System.Windows.Shapes.Shape> gli oggetti sono facili da usare e forniscono molte utili funzionalità, quali layout e la gestione degli eventi. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre anche una serie di oggetti Shape pronti all'uso. Tutti gli oggetti shape ereditano dal <xref:System.Windows.Shapes.Shape> classe. Gli oggetti shape disponibili includono <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, e <xref:System.Windows.Shapes.Rectangle>.  
  
 <xref:System.Windows.Media.Drawing> gli oggetti, d'altra parte, non derivano dal <xref:System.Windows.FrameworkElement> classe e fornire un'implementazione più leggera per il rendering di forme, immagini e testo.  
  
 Esistono quattro tipi di <xref:System.Windows.Media.Drawing> oggetti:  
  
- <xref:System.Windows.Media.GeometryDrawing> Disegna una forma.  
  
- <xref:System.Windows.Media.ImageDrawing> Disegna un'immagine.  
  
- <xref:System.Windows.Media.GlyphRunDrawing> Disegna un testo.  
  
- <xref:System.Windows.Media.DrawingGroup> Esegue altri disegni. Usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 Il <xref:System.Windows.Media.GeometryDrawing> oggetto viene usato per eseguire il rendering di contenuto della geometria. Il <xref:System.Windows.Media.Geometry> classi e le classi concrete che ne derivano, come <xref:System.Windows.Media.CombinedGeometry>, <xref:System.Windows.Media.EllipseGeometry>, e <xref:System.Windows.Media.PathGeometry>, forniscono un mezzo per il rendering grafica 2D, nonché fornire hit testing e il supporto di ritaglio. Gli oggetti Geometry possono essere usati per definire, ad esempio, l'area di un controllo o l'area di ritaglio da applicare a un'immagine e possono essere semplici aree, quali rettangoli o cerchi, oppure aree composite create con due o più oggetti Geometry. È possibile creare aree geometriche più complesse combinando <xref:System.Windows.Media.PathSegment>-derivato oggetti, ad esempio <xref:System.Windows.Media.ArcSegment>, <xref:System.Windows.Media.BezierSegment>, e <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
 Nell'area della <xref:System.Windows.Media.Geometry> classe e il <xref:System.Windows.Shapes.Shape> sono molto simili. Entrambi vengono utilizzati per il rendering di grafica 2D e classi concrete simili che ne derivano, ad esempio, dispongono <xref:System.Windows.Media.EllipseGeometry> e <xref:System.Windows.Shapes.Ellipse>. Esistono tuttavia importanti differenze tra questi due set di classi. Per uno, il <xref:System.Windows.Media.Geometry> classe non dispone di alcune delle funzionalità del <xref:System.Windows.Shapes.Shape> (classe), ad esempio la possibilità di disegnarsi da solo. Per disegnare un oggetto Geometry, è necessario usare un'altra classe, ad esempio DrawingContext, Drawing o Path (notare che Path è un oggetto Shape) per poter eseguire l'operazione di disegno. Le proprietà di rendering, tra cui il riempimento, il tratto e lo spessore del tratto, si trovano nella classe che consente di disegnare l'oggetto Geometry, ma sono contenute direttamente in un oggetto Shape. In altre parole, un oggetto Geometry definisce un'area, ad esempio un cerchio, mentre un oggetto Shape definisce un'area, il modo in cui questa viene riempita e delineata e partecipa al sistema di layout.  
  
 Poiché <xref:System.Windows.Shapes.Shape> oggetti derivano dal <xref:System.Windows.FrameworkElement> classe utilizzando li può aggiungere significativamente maggiore consumo di memoria nell'applicazione. Se si necessita di <xref:System.Windows.FrameworkElement> le funzionalità per il contenuto grafico, è consigliabile usare la leggera <xref:System.Windows.Media.Drawing> oggetti.  
  
 Per ulteriori informazioni sul <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sugli oggetti Drawing](../graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## <a name="streamgeometry-objects"></a>Oggetto StreamGeometry  
 Il <xref:System.Windows.Media.StreamGeometry> oggetto è un'alternativa semplificata a <xref:System.Windows.Media.PathGeometry> per la creazione di forme geometriche. Usare un <xref:System.Windows.Media.StreamGeometry> quando è necessario descrivere una geometria complessa. <xref:System.Windows.Media.StreamGeometry> è ottimizzato per la gestione di molti <xref:System.Windows.Media.PathGeometry> degli oggetti e offre prestazioni migliori rispetto all'uso di molti singoli <xref:System.Windows.Media.PathGeometry> oggetti.  
  
 L'esempio seguente usa la sintassi degli attributi per creare una forma di triangolo <xref:System.Windows.Media.StreamGeometry> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Per ulteriori informazioni sul <xref:System.Windows.Media.StreamGeometry> oggetti, vedere [creare forme tramite un oggetto StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## <a name="drawingvisual-objects"></a>Oggetti DrawingVisual  
 Il <xref:System.Windows.Media.DrawingVisual> oggetto è una classe che consente di eseguire il rendering di forme, immagini o testo di disegno semplificata. Questa classe è considerata semplice perché non offre la gestione di layout o eventi, con un conseguente aumento delle prestazioni. Per questo motivo, i disegni sono ideali per sfondi e ClipArt. Per altre informazioni, vedere [Uso degli oggetti DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## <a name="images"></a>Immagini  
 Le funzionalità per la creazione di immagini di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offrono miglioramenti significativi rispetto alle funzionalità per la creazione di immagini delle precedenti versioni di [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]. Le funzionalità per la creazione di immagini, come la visualizzazione di una bitmap o l'uso di un'immagine per un controllo comune, venivano gestite inizialmente dalle API (Application Programming Interface) Graphics Device Interface (GDI) o GDI+ di Microsoft Windows. Queste API offrivano funzionalità di base per la creazione di immagini, ma erano sprovviste di funzionalità come il supporto per l'estendibilità dei codec o per immagini ad alta fedeltà. Le API per la creazione di immagini di WPF sono state riprogettate per colmare le carenze di GDI e GDI+ e offrire un nuovo set di API per visualizzare e usare le immagini all'interno delle applicazioni.  
  
 Per ottenere prestazioni migliori durante l'uso di immagini, seguire questi consigli:  
  
- Se l'applicazione richiede la visualizzazione di immagini di anteprima, creare una versione ridotta dell'immagine. Per impostazione predefinita, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] carica l'immagine e la decodifica con le dimensioni originali. Se si vuole soltanto un'immagine di anteprima, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] decodifica comunque l'immagine con le dimensioni originali e successivamente la riduce alle dimensioni di un'anteprima. Per evitare questo inutile sovraccarico, è possibile richiedere a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di decodificare l'immagine con le dimensioni dell'anteprima oppure richiedere a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di caricare direttamente l'immagine di anteprima.  
  
- Decodificare sempre l'immagine con le dimensioni desiderate e non con quelle predefinite. Richiedere quindi a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di eseguire la codifica secondo le dimensioni desiderate e non in base a quelle predefinite. In questo modo è possibile ridurre non solo il working set dell'applicazione ma anche la velocità di esecuzione.  
  
- Se possibile, combinare le immagini in un'unica immagine, come una pellicola cinematografica composta da più immagini.  
  
- Per altre informazioni, vedere [Panoramica della creazione dell'immagine](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Quando si aggiunge un'animazione alla scala di una bitmap, è possibile che l'algoritmo di ricampionamento delle immagini di alta qualità determini un consumo di risorse di sistema tale da rallentare la frequenza dei fotogrammi, provocando lo stuttering delle animazioni. Impostando il <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> proprietà del <xref:System.Windows.Media.RenderOptions> oggetto <xref:System.Windows.Media.BitmapScalingMode.LowQuality> quando si ridimensiona una bitmap, è possibile creare un'animazione più fluida. <xref:System.Windows.Media.BitmapScalingMode.LowQuality> indica la modalità di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] motore di rendering per passare da un algoritmo ottimizzato per la qualità a un algoritmo ottimizzato per la velocità durante l'elaborazione di immagini.  
  
 Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Media.BitmapScalingMode> per un oggetto immagine.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 Per impostazione predefinita [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] memorizza nella cache il contenuto di rendering <xref:System.Windows.Media.TileBrush> oggetti, ad esempio <xref:System.Windows.Media.DrawingBrush> e <xref:System.Windows.Media.VisualBrush>. Negli scenari statici in cui il contenuto e l'uso del <xref:System.Windows.Media.TileBrush> nella scena, in questo senso, poiché consente di conservare memoria video. Non apporta ha senso se un <xref:System.Windows.Media.TileBrush> con contenuto statico viene usato in modo non statico, ad esempio, quando un valore statico <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> è mappato alla superficie di un oggetto 3D rotante. Il comportamento predefinito di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste nell'eseguire nuovamente il rendering dell'intero contenuto del <xref:System.Windows.Media.DrawingBrush> o <xref:System.Windows.Media.VisualBrush> per ogni fotogramma, anche se il contenuto rimane invariato.  
  
 Impostando il <xref:System.Windows.Media.RenderOptions.CachingHint%2A> proprietà del <xref:System.Windows.Media.RenderOptions> oggetto <xref:System.Windows.Media.CachingHint.Cache> è possibile migliorare le prestazioni tramite versioni memorizzate nella cache degli oggetti pennello affiancati.  
  
 Il <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> e <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> i valori delle proprietà sono valori di dimensione relativi che determinano quando il <xref:System.Windows.Media.TileBrush> oggetto deve essere rigenerato a causa di modifiche di ridimensionamento. Ad esempio, impostando il <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> proprietà a 2.0, la cache per il <xref:System.Windows.Media.TileBrush> deve solo essere rigenerate quando la relativa dimensione supera due volte la dimensione della cache corrente.  
  
 Nell'esempio seguente viene illustrato come utilizzare l'opzione di hint per la memorizzazione nella cache per un <xref:System.Windows.Media.DrawingBrush>.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](optimizing-performance-layout-and-design.md)
- [Comportamento dell'oggetto](optimizing-performance-object-behavior.md)
- [Risorse di applicazioni](optimizing-performance-application-resources.md)
- [per](optimizing-performance-text.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
- [Suggerimenti sulle animazioni](../graphics-multimedia/animation-tips-and-tricks.md)
