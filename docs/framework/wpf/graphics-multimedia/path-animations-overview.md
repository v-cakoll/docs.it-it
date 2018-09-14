---
title: Panoramica sulle animazioni tracciato
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], paths
- path animations [WPF]
ms.assetid: 979c732c-df74-47a6-be96-8e07b3707d53
ms.openlocfilehash: 0f795ad00823e7b1c37221f7417b09d3982c4c18
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45507703"
---
# <a name="path-animations-overview"></a>Panoramica sulle animazioni tracciato
<a name="introduction"></a> Questo argomento presenta le animazioni tracciato, che consentono di usare un tracciato geometrico per generare valori di output. Le animazioni tracciato sono utili per lo spostamento e rotazione di oggetti lungo tracciati complessi.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le funzionalità di animazione. Per un'introduzione alle funzionalità di animazione, vedere la [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Perché si usa un' <xref:System.Windows.Media.PathGeometry> oggetto per definire un'animazione tracciato, è anche necessario conoscere <xref:System.Windows.Media.PathGeometry> e i diversi tipi di <xref:System.Windows.Media.PathSegment> oggetti. Per altre informazioni, vedere la [panoramica delle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a>Che cos'è un'animazione tracciato?  
 Un'animazione tracciato è un tipo di <xref:System.Windows.Media.Animation.AnimationTimeline> che usa un <xref:System.Windows.Media.PathGeometry> come input. Anziché impostare un From a, o dalla proprietà (come avviene per From/To/By animazione) oppure usando i fotogrammi chiave (come si utilizza per un'animazione con fotogrammi chiave), si definiscono un tracciato geometrico e usarlo per impostare il `PathGeometry` proprietà dell'animazione tracciato. Con l'avanzamento dell'animazione tracciato, le informazioni relative a x, y e all'angolo vengono lette dal tracciato e usate per generare l'output.  
  
 Le animazioni tracciato sono estremamente utili per aggiungere un'animazione a un oggetto lungo un tracciato complesso. Un modo per spostare un oggetto lungo un tracciato consiste nell'usare un <xref:System.Windows.Media.MatrixTransform> e un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> per trasformare un oggetto lungo un tracciato complesso. L'esempio seguente illustra questa tecnica usando il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto da animare il <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>. Il <xref:System.Windows.Media.MatrixTransform> viene applicato a un pulsante e ne determina lo spostamento lungo un tracciato curvo. Poiché il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> è impostata su `true`, il rettangolo ruota lungo la tangente del percorso.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Per altre informazioni sulla sintassi del percorso che viene utilizzata per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio, vedere il [sintassi di Markup del percorso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Panoramica. Per l'esempio completo, vedere [esempio di animazione tracciato](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
 È possibile applicare un'animazione tracciato a una proprietà usando un <xref:System.Windows.Media.Animation.Storyboard> nelle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e nel codice o tramite il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo nel codice. È anche possibile usare un'animazione tracciato per creare un <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a una o più proprietà. Per altre informazioni sui diversi metodi per l'applicazione di animazioni, vedere [Cenni preliminari sulle tecniche di animazione di proprietà](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a>Tipi di animazione tracciato  
 Poiché le animazioni generano valori di proprietà, esistono diversi tipi di animazione per i diversi tipi di proprietà. Per animare una proprietà che accetta un <xref:System.Double> (ad esempio il <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà di un <xref:System.Windows.Media.TranslateTransform>), usare un'animazione che produce <xref:System.Double> valori. Per animare una proprietà che accetta un <xref:System.Windows.Point>, usare un'animazione che produce <xref:System.Windows.Point> valori e così via.  
  
 Classi di animazione tracciato appartengono al <xref:System.Windows.Media.Animation> dello spazio dei nomi e usano la convenzione di denominazione seguente:  
  
 *\<Tipo>* `AnimationUsingPath`  
  
 Dove *\<Tipo>* è il tipo di valore cui è stata aggiunta un'animazione dalla classe.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre le classi di animazione tracciato seguenti.  
  
|Tipo di proprietà|Classe di animazione tracciato corrispondente|Esempio|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Animare un oggetto lungo un tracciato (animazione Double)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Animare un oggetto lungo un tracciato (animazione Matrix)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Animare un oggetto lungo un tracciato (animazione Point)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 Oggetto <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> genera <xref:System.Windows.Media.Matrix> i valori dal relativo <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>. Se usato con un <xref:System.Windows.Media.MatrixTransform>, un <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> può spostare un oggetto lungo un tracciato. Se si imposta la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> proprietà del <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> a `true`, viene anche ruotato lungo le curve del tracciato l'oggetto.  
  
 Oggetto <xref:System.Windows.Media.Animation.PointAnimationUsingPath> genera <xref:System.Windows.Point> i valori dalle coordinate x e y della relativa <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>. Usando un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> animare una proprietà che accetta <xref:System.Windows.Point> valori, è possibile spostare un oggetto lungo un tracciato. Oggetto <xref:System.Windows.Media.Animation.PointAnimationUsingPath> non può ruotare gli oggetti.  
  
 Oggetto <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> genera <xref:System.Double> i valori dal relativo <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>. Impostando il <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> proprietà, è possibile specificare se il <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> Usa le coordinate x, relativa alla coordinata y o angolo del tracciato come output. È possibile usare un <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> per ruotare un oggetto o spostarlo lungo l'asse x o asse y.  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a>Input dell'animazione tracciato  
 Ogni classe di animazione tracciato fornisce una <xref:System.Windows.Media.PathGeometry> proprietà per specificare il relativo input. L'animazione tracciato Usa la <xref:System.Windows.Media.PathGeometry> per generare i valori di output. Il <xref:System.Windows.Media.PathGeometry> classe consente di descrivere più figure complesse costituite da archi, curve e linee.  
  
 Il fulcro di un' <xref:System.Windows.Media.PathGeometry> è una raccolta di <xref:System.Windows.Media.PathFigure> oggetti, questi oggetti così chiamati perché ogni figura descrive una forma discreta nel <xref:System.Windows.Media.PathGeometry>. Ciascuna <xref:System.Windows.Media.PathFigure> è costituito da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali descrive un segmento della figura.  
  
 Esistono diversi tipi di segmenti.  
  
|Tipo di segmento|Descrizione|  
|------------------|-----------------|  
|<xref:System.Windows.Media.ArcSegment>|Crea un arco ellittico tra due punti.|  
|<xref:System.Windows.Media.BezierSegment>|Crea una curva di Bézier cubica tra due punti.|  
|<xref:System.Windows.Media.LineSegment>|Crea una linea tra due punti.|  
|<xref:System.Windows.Media.PolyBezierSegment>|Crea una serie di curve di Bézier cubiche.|  
|<xref:System.Windows.Media.PolyLineSegment>|Crea una serie di linee.|  
|<xref:System.Windows.Media.PolyQuadraticBezierSegment>|Crea una serie di curve di Bézier quadratiche.|  
|<xref:System.Windows.Media.QuadraticBezierSegment>|Crea una curva di Bézier quadratica.|  
  
 I segmenti in un <xref:System.Windows.Media.PathFigure> vengono combinati in una singola forma geometrica, che usa il punto finale di un segmento come punto iniziale del segmento successivo. Il <xref:System.Windows.Media.PathFigure.StartPoint%2A> proprietà di un <xref:System.Windows.Media.PathFigure> specifica il punto da cui viene tracciato il primo segmento. Ogni segmento successivo inizia in corrispondenza del punto finale del segmento precedente. Ad esempio, una linea verticale da `10,50` a `10,150` può essere definita impostando la <xref:System.Windows.Media.PathFigure.StartPoint%2A> proprietà `10,50` e la creazione di un <xref:System.Windows.Media.LineSegment> con un <xref:System.Windows.Media.LineSegment.Point%2A> impostazione della proprietà di `10,150`.  
  
 Per altre informazioni sulle <xref:System.Windows.Media.PathGeometry> oggetti, vedere la [panoramica delle classi Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 Nelle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è anche possibile usare una sintassi abbreviata speciale per impostare il <xref:System.Windows.Media.PathGeometry.Figures%2A> proprietà di un <xref:System.Windows.Media.PathGeometry>. Per altre informazioni, vedere [sintassi di Markup del percorso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Panoramica.  
  
 Per altre informazioni sulla sintassi del percorso che viene utilizzata per il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio, vedere il [sintassi di Markup del percorso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Panoramica.  
  
## <a name="see-also"></a>Vedere anche  
 [Path Animation Sample (Esempio di animazione tracciato)](https://go.microsoft.com/fwlink/?LinkID=160028)  
 [Sintassi di markup del percorso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [Procedure relative all'animazione percorso](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sulle tecniche di animazione delle proprietà](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
