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
ms.openlocfilehash: 764e7e802ccaff50b76229b9441380bfe77fefb5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933344"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Ottimizzazione delle prestazioni: Grafica 2D e creazione di immagini
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un'ampia gamma di funzionalità di grafica 2D e creazione di immagini che possono essere ottimizzate in base ai requisiti dell'applicazione. Questo argomento fornisce informazioni sull'ottimizzazione delle prestazioni in queste aree.  

<a name="Drawing_and_Shapes"></a>   
## <a name="drawing-and-shapes"></a>Disegno e forme  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce oggetti <xref:System.Windows.Shapes.Shape> e per rappresentare il contenuto del disegno grafico. <xref:System.Windows.Media.Drawing> Tuttavia, <xref:System.Windows.Media.Drawing> gli oggetti sono costrutti più semplici <xref:System.Windows.Shapes.Shape> rispetto agli oggetti e offrono caratteristiche di prestazioni migliori.  
  
 Un <xref:System.Windows.Shapes.Shape> oggetto consente di disegnare una forma grafica sullo schermo. Poiché derivano dalla <xref:System.Windows.FrameworkElement> classe, <xref:System.Windows.Shapes.Shape> gli oggetti possono essere utilizzati all'interno di pannelli e la maggior parte dei controlli.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre diversi livelli di accesso alla grafica e ai servizi di rendering. Al livello superiore, <xref:System.Windows.Shapes.Shape> gli oggetti sono facili da usare e offrono numerose funzionalità utili, ad esempio il layout e la gestione degli eventi. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre anche una serie di oggetti Shape pronti all'uso. Tutti gli oggetti Shape ereditano <xref:System.Windows.Shapes.Shape> dalla classe. Gli oggetti Shape disponibili <xref:System.Windows.Shapes.Ellipse>includono <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>,, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, e <xref:System.Windows.Shapes.Rectangle>.  
  
 <xref:System.Windows.Media.Drawing>gli oggetti, d'altra parte, non derivano dalla <xref:System.Windows.FrameworkElement> classe e forniscono un'implementazione più leggera per il rendering di forme, immagini e testo.  
  
 Sono disponibili quattro tipi di <xref:System.Windows.Media.Drawing> oggetti:  
  
- <xref:System.Windows.Media.GeometryDrawing>Disegna una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>Disegna un'immagine.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>Disegna il testo.  
  
- <xref:System.Windows.Media.DrawingGroup>Disegna altri disegni. Usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 L' <xref:System.Windows.Media.GeometryDrawing> oggetto viene utilizzato per eseguire il rendering del contenuto della geometria. La <xref:System.Windows.Media.Geometry> classe e le classi concrete che derivano da esso, <xref:System.Windows.Media.CombinedGeometry>ad <xref:System.Windows.Media.EllipseGeometry>esempio, <xref:System.Windows.Media.PathGeometry>e, forniscono un mezzo per il rendering di immagini 2D, oltre a fornire il supporto per l'hit testing e il ritaglio. Gli oggetti Geometry possono essere usati per definire, ad esempio, l'area di un controllo o l'area di ritaglio da applicare a un'immagine e possono essere semplici aree, quali rettangoli o cerchi, oppure aree composite create con due o più oggetti Geometry. È possibile creare aree geometriche più <xref:System.Windows.Media.PathSegment>complesse combinando oggetti derivati da, <xref:System.Windows.Media.BezierSegment> <xref:System.Windows.Media.ArcSegment>ad esempio <xref:System.Windows.Media.QuadraticBezierSegment>, e.  
  
 Sulla superficie, la <xref:System.Windows.Media.Geometry> classe e la <xref:System.Windows.Shapes.Shape> classe sono molto simili. Entrambi vengono usati nel rendering di grafica 2D ed entrambi hanno classi concrete simili che derivano da esse, ad esempio <xref:System.Windows.Media.EllipseGeometry> e <xref:System.Windows.Shapes.Ellipse>. Esistono tuttavia importanti differenze tra questi due set di classi. Per uno, la <xref:System.Windows.Media.Geometry> classe non dispone di alcune funzionalità <xref:System.Windows.Shapes.Shape> della classe, ad esempio la possibilità di disegnarla. Per disegnare un oggetto Geometry, è necessario usare un'altra classe, ad esempio DrawingContext, Drawing o Path (notare che Path è un oggetto Shape) per poter eseguire l'operazione di disegno. Le proprietà di rendering, tra cui il riempimento, il tratto e lo spessore del tratto, si trovano nella classe che consente di disegnare l'oggetto Geometry, ma sono contenute direttamente in un oggetto Shape. In altre parole, un oggetto Geometry definisce un'area, ad esempio un cerchio, mentre un oggetto Shape definisce un'area, il modo in cui questa viene riempita e delineata e partecipa al sistema di layout.  
  
 Poiché <xref:System.Windows.Shapes.Shape> gli oggetti derivano <xref:System.Windows.FrameworkElement> dalla classe, l'uso di tali oggetti può aumentare significativamente il consumo di memoria nell'applicazione. Se non sono necessarie le <xref:System.Windows.FrameworkElement> funzionalità per il contenuto grafico, provare a usare gli <xref:System.Windows.Media.Drawing> oggetti più semplici.  
  
 Per altre informazioni sugli <xref:System.Windows.Media.Drawing> oggetti, vedere [Cenni preliminari sugli oggetti Drawing](../graphics-multimedia/drawing-objects-overview.md).  
  
<a name="StreamGeometry_Objects"></a>   
## <a name="streamgeometry-objects"></a>Oggetto StreamGeometry  
 L' <xref:System.Windows.Media.StreamGeometry> oggetto è un'alternativa semplice a <xref:System.Windows.Media.PathGeometry> per la creazione di forme geometriche. Usare un <xref:System.Windows.Media.StreamGeometry> oggetto quando è necessario descrivere una geometria complessa. <xref:System.Windows.Media.StreamGeometry>è ottimizzato per la <xref:System.Windows.Media.PathGeometry> gestione di molti oggetti e offre prestazioni migliori rispetto all' <xref:System.Windows.Media.PathGeometry> utilizzo di molti singoli oggetti.  
  
 Nell'esempio seguente viene usata la sintassi degli attributi per creare <xref:System.Windows.Media.StreamGeometry> un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]triangolare in.  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Per altre informazioni sugli <xref:System.Windows.Media.StreamGeometry> oggetti, vedere [creare una forma usando un StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>   
## <a name="drawingvisual-objects"></a>Oggetti DrawingVisual  
 L' <xref:System.Windows.Media.DrawingVisual> oggetto è una classe di disegno semplificata utilizzata per il rendering di forme, immagini o testo. Questa classe è considerata semplice perché non offre la gestione di layout o eventi, con un conseguente aumento delle prestazioni. Per questo motivo, i disegni sono ideali per sfondi e ClipArt. Per altre informazioni, vedere [Uso degli oggetti DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>   
## <a name="images"></a>Immagini  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]la creazione di immagini offre un miglioramento significativo rispetto alle funzionalità di creazione di immagini nelle versioni precedenti di Windows. Le funzionalità per la creazione di immagini, come la visualizzazione di una bitmap o l'uso di un'immagine per un controllo comune, venivano gestite inizialmente dalle API (Application Programming Interface) Graphics Device Interface (GDI) o GDI+ di Microsoft Windows. Queste API offrivano funzionalità di base per la creazione di immagini, ma erano sprovviste di funzionalità come il supporto per l'estendibilità dei codec o per immagini ad alta fedeltà. Le API per la creazione di immagini di WPF sono state riprogettate per colmare le carenze di GDI e GDI+ e offrire un nuovo set di API per visualizzare e usare le immagini all'interno delle applicazioni.  
  
 Per ottenere prestazioni migliori durante l'uso di immagini, seguire questi consigli:  
  
- Se l'applicazione richiede la visualizzazione di immagini di anteprima, creare una versione ridotta dell'immagine. Per impostazione predefinita, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] carica l'immagine e la decodifica con le dimensioni originali. Se si vuole soltanto un'immagine di anteprima, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] decodifica comunque l'immagine con le dimensioni originali e successivamente la riduce alle dimensioni di un'anteprima. Per evitare questo inutile sovraccarico, è possibile richiedere a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di decodificare l'immagine con le dimensioni dell'anteprima oppure richiedere a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di caricare direttamente l'immagine di anteprima.  
  
- Decodificare sempre l'immagine con le dimensioni desiderate e non con quelle predefinite. Richiedere quindi a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di eseguire la codifica secondo le dimensioni desiderate e non in base a quelle predefinite. In questo modo è possibile ridurre non solo il working set dell'applicazione ma anche la velocità di esecuzione.  
  
- Se possibile, combinare le immagini in un'unica immagine, come una pellicola cinematografica composta da più immagini.  
  
- Per altre informazioni, vedere [Panoramica della creazione dell'immagine](../graphics-multimedia/imaging-overview.md).  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Quando si aggiunge un'animazione alla scala di una bitmap, è possibile che l'algoritmo di ricampionamento delle immagini di alta qualità determini un consumo di risorse di sistema tale da rallentare la frequenza dei fotogrammi, provocando lo stuttering delle animazioni. Impostando la <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> proprietà <xref:System.Windows.Media.RenderOptions> dell'oggetto su <xref:System.Windows.Media.BitmapScalingMode.LowQuality> è possibile creare un'animazione più uniforme durante il ridimensionamento di una bitmap. <xref:System.Windows.Media.BitmapScalingMode.LowQuality>Mode indica [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al motore di rendering di passare da un algoritmo ottimizzato per la qualità a un algoritmo ottimizzato per la velocità durante l'elaborazione di immagini.  
  
 Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.Media.BitmapScalingMode> per un oggetto Image.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 Per impostazione predefinita [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , non memorizza nella cache il contenuto <xref:System.Windows.Media.TileBrush> sottoposto a rendering <xref:System.Windows.Media.DrawingBrush> degli <xref:System.Windows.Media.VisualBrush>oggetti, ad esempio e. Negli scenari statici in cui non è stato modificato né il <xref:System.Windows.Media.TileBrush> contenuto né l'uso di nella scena, questo ha senso, poiché consente di conservare la memoria video. Non è molto utile quando un <xref:System.Windows.Media.TileBrush> oggetto con contenuto statico viene usato in modo non statico, ad esempio quando viene eseguito il mapping di un oggetto statico <xref:System.Windows.Media.VisualBrush> <xref:System.Windows.Media.DrawingBrush> o alla superficie di un oggetto 3D rotante. Il comportamento predefinito di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] prevede di eseguire nuovamente il rendering dell'intero contenuto dell' <xref:System.Windows.Media.DrawingBrush> oggetto <xref:System.Windows.Media.VisualBrush> o per ogni frame, anche se il contenuto non è in corso di modifica.  
  
 Impostando la <xref:System.Windows.Media.RenderOptions.CachingHint%2A> proprietà <xref:System.Windows.Media.RenderOptions> dell'oggetto su <xref:System.Windows.Media.CachingHint.Cache> è possibile migliorare le prestazioni utilizzando le versioni memorizzate nella cache degli oggetti pennello affiancati.  
  
 I <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> valori <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> delle proprietà e sono valori di dimensione relativa che determinano quando l' <xref:System.Windows.Media.TileBrush> oggetto deve essere rigenerato a causa di modifiche della scala. Se ad esempio si imposta la <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> proprietà su 2,0, la cache <xref:System.Windows.Media.TileBrush> per deve essere rigenerata solo quando la dimensione supera il doppio della dimensione della cache corrente.  
  
 Nell'esempio seguente viene illustrato come utilizzare l'opzione relativa all'hint di memorizzazione <xref:System.Windows.Media.DrawingBrush>nella cache per un oggetto.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](optimizing-performance-layout-and-design.md)
- [Comportamento dell'oggetto](optimizing-performance-object-behavior.md)
- [Risorse di applicazioni](optimizing-performance-application-resources.md)
- [Text](optimizing-performance-text.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
- [Suggerimenti sulle animazioni](../graphics-multimedia/animation-tips-and-tricks.md)
