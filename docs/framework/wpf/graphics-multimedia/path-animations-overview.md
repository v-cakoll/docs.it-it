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
ms.openlocfilehash: 466e22a5b40ddb4f3674422ac7620832b44be51d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565689"
---
# <a name="path-animations-overview"></a>Panoramica sulle animazioni tracciato
<a name="introduction"></a> Questo argomento presenta le animazioni tracciato, che consentono di usare un tracciato geometrico per generare valori di output. Le animazioni tracciato sono utili per lo spostamento e rotazione di oggetti lungo tracciati complessi.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le funzionalità di animazione. Per un'introduzione alle funzionalità di animazione, vedere il [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Poiché si utilizza un <xref:System.Windows.Media.PathGeometry> oggetto per definire un'animazione percorso, è necessario inoltre conoscere con <xref:System.Windows.Media.PathGeometry> e i diversi tipi di <xref:System.Windows.Media.PathSegment> oggetti. Per ulteriori informazioni, vedere il [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>   
## <a name="what-is-a-path-animation"></a>Che cos'è un'animazione tracciato?  
 Un'animazione percorso è un tipo di <xref:System.Windows.Media.Animation.AnimationTimeline> che utilizza un <xref:System.Windows.Media.PathGeometry> come input. Anziché impostare da, a o dalla proprietà (come avviene per da/a/da animazione) oppure usando i fotogrammi chiave (come si utilizza per un'animazione con fotogramma chiave), si definisce un percorso geometrico e utilizzarlo per impostare il `PathGeometry` proprietà dell'animazione percorso. Con l'avanzamento dell'animazione tracciato, le informazioni relative a x, y e all'angolo vengono lette dal tracciato e usate per generare l'output.  
  
 Le animazioni tracciato sono estremamente utili per aggiungere un'animazione a un oggetto lungo un tracciato complesso. Per spostare un oggetto lungo un percorso consiste nell'usare un <xref:System.Windows.Media.MatrixTransform> e <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> per trasformare un oggetto lungo un percorso complesso. L'esempio seguente illustra questa tecnica utilizzando il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> oggetto da cui iniziare l'animazione di <xref:System.Windows.Media.MatrixTransform.Matrix%2A> proprietà di un <xref:System.Windows.Media.MatrixTransform>. Il <xref:System.Windows.Media.MatrixTransform> viene applicato a un pulsante e determina lo spostamento lungo un percorso curvo. Poiché il <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> è impostata su `true`, il rettangolo ruota lungo la tangente del percorso.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Per ulteriori informazioni sulla sintassi del percorso che viene utilizzata per la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio, vedere il [sintassi del percorso di Markup](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Panoramica. Per l'esempio completo, vedere [percorso animazione esempio](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 È possibile applicare un'animazione percorso a una proprietà tramite un <xref:System.Windows.Media.Animation.Storyboard> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e nel codice o tramite il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo nel codice. È inoltre possibile utilizzare un'animazione percorso per creare un <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a una o più proprietà. Per ulteriori informazioni sui diversi metodi per l'applicazione di animazioni, vedere [Property Animation Techniques Overview](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="path-animation-types"></a>Tipi di animazione tracciato  
 Poiché le animazioni generano valori di proprietà, esistono diversi tipi di animazione per i diversi tipi di proprietà. Per aggiungere un'animazione a una proprietà che accetta un <xref:System.Double> (ad esempio il <xref:System.Windows.Media.TranslateTransform.X%2A> proprietà di un <xref:System.Windows.Media.TranslateTransform>), si utilizza un'animazione che produce <xref:System.Double> valori. Per aggiungere un'animazione a una proprietà che accetta un <xref:System.Windows.Point>, si utilizza un'animazione che produce <xref:System.Windows.Point> valori e così via.  
  
 Le classi di animazione percorso appartengono al <xref:System.Windows.Media.Animation> dello spazio dei nomi e utilizzare la convenzione di denominazione seguente:  
  
 *\<Tipo>* `AnimationUsingPath`  
  
 Dove *\<Tipo>* è il tipo di valore cui è stata aggiunta un'animazione dalla classe.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre le classi di animazione tracciato seguenti.  
  
|Tipo di proprietà|Classe di animazione tracciato corrispondente|Esempio|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Animare un oggetto lungo un tracciato (animazione Double)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Animare un oggetto lungo un tracciato (animazione Matrix)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Animare un oggetto lungo un tracciato (animazione Point)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 Oggetto <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> genera <xref:System.Windows.Media.Matrix> i valori relativi <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>. Quando si utilizza un <xref:System.Windows.Media.MatrixTransform>, <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> può spostare un oggetto lungo un percorso. Se si imposta la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> proprietà del <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> a `true`, anche l'oggetto ruotato lungo la curva delle curve del percorso.  
  
 Oggetto <xref:System.Windows.Media.Animation.PointAnimationUsingPath> genera <xref:System.Windows.Point> valori dalle coordinate x e y della relativa <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>. Utilizzando un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> per aggiungere un'animazione a una proprietà che accetta <xref:System.Windows.Point> valori, è possibile spostare un oggetto lungo un percorso. Oggetto <xref:System.Windows.Media.Animation.PointAnimationUsingPath> non è possibile ruotare gli oggetti.  
  
 Oggetto <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> genera <xref:System.Double> i valori relativi <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>. Impostando il <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> proprietà, è possibile specificare se il <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> utilizza la coordinata x, coordinata y o l'angolo del percorso come output. È possibile utilizzare un <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> ruotare un oggetto o lo spostamento lungo l'asse x o asse y.  
  
<a name="pathanimationinput"></a>   
## <a name="path-animation-input"></a>Input dell'animazione tracciato  
 Ogni classe di animazione percorso fornisce un <xref:System.Windows.Media.PathGeometry> proprietà per specificare il relativo input. L'animazione percorso utilizza il <xref:System.Windows.Media.PathGeometry> per generare i valori di output. La <xref:System.Windows.Media.PathGeometry> classe consente di descrivere figure più complesse sono composte da archi, curve e linee.  
  
 Il fulcro di un <xref:System.Windows.Media.PathGeometry> è una raccolta di <xref:System.Windows.Media.PathFigure> oggetti; questi oggetti vengono così denominate perché ogni figura descrive una forma discreta nel <xref:System.Windows.Media.PathGeometry>. Ogni <xref:System.Windows.Media.PathFigure> è costituito da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali descrive un segmento della figura.  
  
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
  
 I segmenti in un <xref:System.Windows.Media.PathFigure> vengono combinate in una singola forma geometrica, che utilizza il punto finale di un segmento come punto iniziale del segmento successivo. Il <xref:System.Windows.Media.PathFigure.StartPoint%2A> proprietà di un <xref:System.Windows.Media.PathFigure> specifica il punto da cui viene disegnato il primo segmento. Ogni segmento successivo inizia in corrispondenza del punto finale del segmento precedente. Ad esempio, una linea verticale da `10,50` per `10,150` possono essere definite tramite l'impostazione di <xref:System.Windows.Media.PathFigure.StartPoint%2A> proprietà `10,50` e la creazione di un <xref:System.Windows.Media.LineSegment> con un <xref:System.Windows.Media.LineSegment.Point%2A> impostazione della proprietà `10,150`.  
  
 Per ulteriori informazioni su <xref:System.Windows.Media.PathGeometry> degli oggetti, vedere il [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è inoltre possibile utilizzare una sintassi abbreviata speciale per impostare il <xref:System.Windows.Media.PathGeometry.Figures%2A> proprietà di un <xref:System.Windows.Media.PathGeometry>. Per ulteriori informazioni, vedere [sintassi del percorso di Markup](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Panoramica.  
  
 Per ulteriori informazioni sulla sintassi del percorso che viene utilizzata per la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio, vedere il [sintassi del percorso di Markup](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) Panoramica.  
  
## <a name="see-also"></a>Vedere anche  
 [Path Animation Sample (Esempio di animazione tracciato)](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [Sintassi di markup del percorso](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md)  
 [Procedure relative all'animazione percorso](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sulle tecniche di animazione delle proprietà](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
