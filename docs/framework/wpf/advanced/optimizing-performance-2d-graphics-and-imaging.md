---
title: 'Ottimizzazione delle prestazioni: grafica bidimensionale e creazione di immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], performance
- drawing [WPF], optimizing performance
- imaging [WPF], optimizing performance
- shapes [WPF], optimizing performance
- 2D graphics [WPF]
- images [WPF], optimizing performance
ms.assetid: e335601e-28c8-4d64-ba27-778fffd55f72
ms.openlocfilehash: eb3686367873276587572addda436471cd1abf27
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291794"
---
# <a name="optimizing-performance-2d-graphics-and-imaging"></a>Ottimizzazione delle prestazioni: grafica bidimensionale e creazione di immagini
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre un'ampia gamma di funzionalità di grafica 2D e creazione di immagini che possono essere ottimizzate in base ai requisiti dell'applicazione. Questo argomento fornisce informazioni sull'ottimizzazione delle prestazioni in queste aree.  

<a name="Drawing_and_Shapes"></a>
## <a name="drawing-and-shapes"></a>Disegno e forme  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce <xref:System.Windows.Media.Drawing> sia <xref:System.Windows.Shapes.Shape> gli oggetti che per rappresentare il contenuto del disegno grafico. Tuttavia, <xref:System.Windows.Media.Drawing> gli oggetti <xref:System.Windows.Shapes.Shape> sono costrutti più semplici rispetto agli oggetti e forniscono caratteristiche di prestazioni migliori.  
  
 A <xref:System.Windows.Shapes.Shape> consente di disegnare una forma grafica sullo schermo. Poiché derivano <xref:System.Windows.FrameworkElement> dalla <xref:System.Windows.Shapes.Shape> classe , gli oggetti possono essere utilizzati all'interno di pannelli e la maggior parte dei controlli.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre diversi livelli di accesso alla grafica e ai servizi di rendering. Al livello superiore, <xref:System.Windows.Shapes.Shape> gli oggetti sono facili da usare e forniscono molte funzionalità utili, ad esempio il layout e la gestione degli eventi. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre anche una serie di oggetti Shape pronti all'uso. Tutti gli oggetti <xref:System.Windows.Shapes.Shape> forma ereditano dalla classe. Gli oggetti <xref:System.Windows.Shapes.Ellipse>forma <xref:System.Windows.Shapes.Line> <xref:System.Windows.Shapes.Path>disponibili <xref:System.Windows.Shapes.Polygon> <xref:System.Windows.Shapes.Polyline>includono <xref:System.Windows.Shapes.Rectangle>, , , , e .  
  
 <xref:System.Windows.Media.Drawing>Gli oggetti, d'altra parte, <xref:System.Windows.FrameworkElement> non derivano dalla classe e forniscono un'implementazione più leggera per il rendering di forme, immagini e testo.  
  
 Esistono quattro tipi <xref:System.Windows.Media.Drawing> di oggetti:  
  
- <xref:System.Windows.Media.GeometryDrawing>Disegna una forma.  
  
- <xref:System.Windows.Media.ImageDrawing>Disegna un'immagine.  
  
- <xref:System.Windows.Media.GlyphRunDrawing>Disegna testo.  
  
- <xref:System.Windows.Media.DrawingGroup>Disegna altri disegni. È possibile usare un gruppo di disegni per combinare altri disegni in un unico disegno composto.  
  
 L'oggetto <xref:System.Windows.Media.GeometryDrawing> viene utilizzato per eseguire il rendering del contenuto della geometria. La <xref:System.Windows.Media.Geometry> classe e le classi concrete che <xref:System.Windows.Media.CombinedGeometry> <xref:System.Windows.Media.EllipseGeometry>derivano <xref:System.Windows.Media.PathGeometry>da essa, ad esempio , e , forniscono un mezzo per eseguire il rendering di grafica 2D e fornire supporto per l'hit testing e il ritaglio. Gli oggetti Geometry possono essere usati per definire, ad esempio, l'area di un controllo o l'area di ritaglio da applicare a un'immagine e possono essere semplici aree, quali rettangoli o cerchi, oppure aree composite create con due o più oggetti Geometry. È possibile creare aree <xref:System.Windows.Media.PathSegment>geometriche più complesse <xref:System.Windows.Media.ArcSegment> <xref:System.Windows.Media.BezierSegment>combinando <xref:System.Windows.Media.QuadraticBezierSegment>oggetti derivati, ad esempio , e .  
  
 In superficie, <xref:System.Windows.Media.Geometry> la classe <xref:System.Windows.Shapes.Shape> e la classe sono simili. Entrambi vengono utilizzati nel rendering di grafica 2D ed entrambi hanno <xref:System.Windows.Media.EllipseGeometry> classi <xref:System.Windows.Shapes.Ellipse>concrete simili che derivano da esse, ad esempio, e . Esistono tuttavia importanti differenze tra questi due set di classi. Per uno, <xref:System.Windows.Media.Geometry> la classe manca di <xref:System.Windows.Shapes.Shape> alcune delle funzionalità della classe, come la capacità di disegnare se stessa. Per disegnare un oggetto Geometry, è necessario usare un'altra classe, ad esempio DrawingContext, Drawing o Path (notare che Path è un oggetto Shape) per poter eseguire l'operazione di disegno. Le proprietà di rendering come riempimento, traccia e spessore del tratto si trovano sulla classe che disegna l'oggetto geometrico, mentre un oggetto forma contiene queste proprietà. Un modo per considerare questa differenza è che un oggetto geometria definisce una regione, ad esempio un cerchio, mentre un oggetto forma definisce una regione, definisce il modo in cui tale regione viene riempita e delineata e partecipa al sistema di layout.  
  
 Poiché <xref:System.Windows.Shapes.Shape> gli <xref:System.Windows.FrameworkElement> oggetti derivano dalla classe, il loro utilizzo può aggiungere un consumo di memoria significativamente maggiore nell'applicazione. Se in realtà non <xref:System.Windows.FrameworkElement> hai bisogno delle funzionalità per il <xref:System.Windows.Media.Drawing> tuo contenuto grafico, prendi in considerazione l'uso degli oggetti più leggeri.  
  
 Per ulteriori <xref:System.Windows.Media.Drawing> informazioni sugli oggetti, vedere [Cenni](../graphics-multimedia/drawing-objects-overview.md)preliminari sugli oggetti della Carta .  
  
<a name="StreamGeometry_Objects"></a>
## <a name="streamgeometry-objects"></a>Oggetto StreamGeometry  
 L'oggetto è un'alternativa <xref:System.Windows.Media.StreamGeometry> leggera alla <xref:System.Windows.Media.PathGeometry> creazione di forme geometriche. Utilizzare <xref:System.Windows.Media.StreamGeometry> un quando è necessario descrivere una geometria complessa. <xref:System.Windows.Media.StreamGeometry>è ottimizzato per <xref:System.Windows.Media.PathGeometry> la gestione di molti oggetti <xref:System.Windows.Media.PathGeometry> e offre prestazioni migliori rispetto all'utilizzo di molti oggetti singoli.  
  
 Nell'esempio riportato di seguito viene <xref:System.Windows.Media.StreamGeometry> utilizzata [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]la sintassi degli attributi per creare un triangolare in .  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Per ulteriori <xref:System.Windows.Media.StreamGeometry> informazioni sugli oggetti, vedere Creazione di [una forma utilizzando un StreamGeometry](../graphics-multimedia/how-to-create-a-shape-using-a-streamgeometry.md).  
  
<a name="DrawingVisual_Objects"></a>
## <a name="drawingvisual-objects"></a>Oggetti DrawingVisual  
 L'oggetto <xref:System.Windows.Media.DrawingVisual> è una classe di disegno leggera utilizzata per eseguire il rendering di forme, immagini o testo. Questa classe è considerata semplice perché non offre la gestione di layout o eventi, con un conseguente aumento delle prestazioni. Per questo motivo, i disegni sono ideali per sfondi e ClipArt. Per altre informazioni, vedere [Uso degli oggetti DrawingVisual](../graphics-multimedia/using-drawingvisual-objects.md).  
  
<a name="Images"></a>
## <a name="images"></a>Immagini  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce un miglioramento significativo rispetto alle funzionalità di imaging nelle versioni precedenti di Windows. Le funzionalità di creazione di immagini, ad esempio la visualizzazione di una bitmap o l'utilizzo di un'immagine in un controllo comune, sono state gestite principalmente da GDI (Microsoft Windows Graphics Device Interface) o dall'API (Application Programming Interface) di Microsoft Windows GDI. Queste API fornivano funzionalità di imaging di base, ma mancavano di funzionalità quali il supporto per l'estendibilità dei codec e il supporto delle immagini ad alta fedeltà. Le API WPF Imaging sono state riprogettate per superare le carenze di GDI e GDI e forniscono un nuovo set di API per visualizzare e usare le immagini all'interno delle applicazioni.  
  
 Per ottenere prestazioni migliori durante l'uso di immagini, seguire questi consigli:  
  
- Se l'applicazione richiede la visualizzazione di immagini di anteprima, creare una versione ridotta dell'immagine. Per impostazione predefinita, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] carica l'immagine e la decodifica con le dimensioni originali. Se si vuole soltanto un'immagine di anteprima, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] decodifica comunque l'immagine con le dimensioni originali e successivamente la riduce alle dimensioni di un'anteprima. Per evitare questo inutile sovraccarico, è possibile richiedere a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di decodificare l'immagine con le dimensioni dell'anteprima oppure richiedere a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di caricare direttamente l'immagine di anteprima.  
  
- Decodificare sempre l'immagine con le dimensioni desiderate e non con quelle predefinite. Richiedere quindi a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di eseguire la codifica secondo le dimensioni desiderate e non in base a quelle predefinite. In questo modo è possibile ridurre non solo il working set dell'applicazione ma anche la velocità di esecuzione.  
  
- Se possibile, combinare le immagini in un'unica immagine, come una pellicola cinematografica composta da più immagini.  
  
- Per ulteriori informazioni, consultate [Cenni preliminari sulla creazione di immagini.](../graphics-multimedia/imaging-overview.md)  
  
### <a name="bitmapscalingmode"></a>BitmapScalingMode  
 Quando si anima la scala di qualsiasi bitmap, l'algoritmo di ricampionamento delle immagini di alta qualità predefinito può talvolta consumare risorse di sistema sufficienti per causare una riduzione della frequenza fotogrammi, causando in modo efficace il balbettamento delle animazioni. Impostando la <xref:System.Windows.Media.RenderOptions.BitmapScalingMode%2A> proprietà <xref:System.Windows.Media.RenderOptions> dell'oggetto su <xref:System.Windows.Media.BitmapScalingMode.LowQuality>, è possibile creare un'animazione più uniforme durante il ridimensionamento di una bitmap. <xref:System.Windows.Media.BitmapScalingMode.LowQuality>mode indica [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] al motore di rendering di passare da un algoritmo ottimizzato per la qualità a un algoritmo ottimizzato per la velocità durante l'elaborazione delle immagini.  
  
 Nell'esempio seguente viene <xref:System.Windows.Media.BitmapScalingMode> illustrato come impostare l'oggetto per un oggetto immagine.  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet2)]
 [!code-vb[RenderOptions#RenderOptionsSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet2)]  
  
### <a name="cachinghint"></a>CachingHint  
 Per impostazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predefinita, il <xref:System.Windows.Media.TileBrush> contenuto sottoposto <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush>a rendering degli oggetti viene memorizzato nella cache, ad esempio e . Negli scenari statici in cui <xref:System.Windows.Media.TileBrush> il contenuto o l'uso di nella scena non cambiano, questo ha senso, poiché conserva la memoria video. Non ha molto senso quando <xref:System.Windows.Media.TileBrush> un oggetto con contenuto statico viene utilizzato in modo <xref:System.Windows.Media.DrawingBrush> <xref:System.Windows.Media.VisualBrush> non statico, ad esempio quando un oggetto statico o viene mappato alla superficie di un oggetto 3D rotante. Il comportamento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predefinito di consiste nell'eseguire <xref:System.Windows.Media.DrawingBrush> nuovamente <xref:System.Windows.Media.VisualBrush> il rendering dell'intero contenuto di o per ogni fotogramma, anche se il contenuto non cambia.  
  
 Impostando la <xref:System.Windows.Media.RenderOptions.CachingHint%2A> proprietà <xref:System.Windows.Media.RenderOptions> dell'oggetto su <xref:System.Windows.Media.CachingHint.Cache>, è possibile migliorare le prestazioni utilizzando le versioni memorizzate nella cache degli oggetti pennello affiancati.  
  
 I <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMinimum%2A> <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> valori delle proprietà e sono <xref:System.Windows.Media.TileBrush> valori di dimensione relativi che determinano quando l'oggetto deve essere rigenerato a causa di modifiche della scala. Ad esempio, impostando <xref:System.Windows.Media.RenderOptions.CacheInvalidationThresholdMaximum%2A> la proprietà su 2.0, la cache per l'unica <xref:System.Windows.Media.TileBrush> deve essere rigenerata quando la sua dimensione supera il doppio delle dimensioni della cache corrente.  
  
 Nell'esempio riportato di seguito viene illustrato <xref:System.Windows.Media.DrawingBrush>come utilizzare l'opzione hint di memorizzazione nella cache per un oggetto .  
  
 [!code-csharp[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/RenderOptions/CSharp/Window1.xaml.cs#renderoptionssnippet3)]
 [!code-vb[RenderOptions#RenderOptionsSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RenderOptions/visualbasic/window1.xaml.vb#renderoptionssnippet3)]  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout e progettazione](optimizing-performance-layout-and-design.md)
- [Comportamento degli oggetti](optimizing-performance-object-behavior.md)
- [Risorse dell'applicazione](optimizing-performance-application-resources.md)
- [Testo](optimizing-performance-text.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
- [Suggerimenti sulle animazioni](../graphics-multimedia/animation-tips-and-tricks.md)
