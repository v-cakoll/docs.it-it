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
ms.openlocfilehash: 07628d26c8222c7c01f58826a36a15e13dc31ff4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181871"
---
# <a name="path-animations-overview"></a>Panoramica sulle animazioni tracciato
<a name="introduction"></a> Questo argomento presenta le animazioni tracciato, che consentono di usare un tracciato geometrico per generare valori di output. Le animazioni tracciato sono utili per lo spostamento e rotazione di oggetti lungo tracciati complessi.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Prerequisites  
 Per comprendere questo argomento, è [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] necessario avere familiarità con le funzionalità delle animazioni. Per un'introduzione alle funzionalità di animazione, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
 Poiché si <xref:System.Windows.Media.PathGeometry> utilizza un oggetto per definire un'animazione percorso, è necessario avere familiarità anche con <xref:System.Windows.Media.PathGeometry> e i diversi tipi di <xref:System.Windows.Media.PathSegment> oggetti. Per ulteriori informazioni, vedere [Cenni preliminari sulla geometria](geometry-overview.md).  
  
<a name="what_is_a_path_animation"></a>
## <a name="what-is-a-path-animation"></a>Che cos'è un'animazione tracciato?  
 Un'animazione percorso <xref:System.Windows.Media.Animation.AnimationTimeline> è un <xref:System.Windows.Media.PathGeometry> tipo di che usa un come input. Anziché impostare una proprietà From, To o By (come per un'animazione From/To/By) o utilizzare fotogrammi chiave (come usate `PathGeometry` per un'animazione con fotogrammi chiave), definite un percorso geometrico e lo utilizzate per impostare la proprietà dell'animazione del tracciato. Con l'avanzamento dell'animazione tracciato, le informazioni relative a x, y e all'angolo vengono lette dal tracciato e usate per generare l'output.  
  
 Le animazioni tracciato sono estremamente utili per aggiungere un'animazione a un oggetto lungo un tracciato complesso. Un modo per spostare un oggetto <xref:System.Windows.Media.MatrixTransform> lungo <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> un tracciato consiste nell'utilizzare a e a per trasformare un oggetto lungo un percorso complesso. Nell'esempio riportato di <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> seguito viene <xref:System.Windows.Media.MatrixTransform.Matrix%2A> illustrata <xref:System.Windows.Media.MatrixTransform>questa tecnica utilizzando l'oggetto per animare la proprietà di un oggetto . L'oggetto <xref:System.Windows.Media.MatrixTransform> viene applicato a un pulsante e ne fa muovere lungo un tracciato curvo. Poiché <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> la proprietà `true`è impostata su , il rettangolo ruota lungo la tangente del percorso.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 Per altre informazioni sulla sintassi del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] percorso utilizzata nell'esempio, vedere panoramica della [sintassi](path-markup-syntax.md) di markup del percorso. Per l'esempio completo, vedere Esempio di [animazione del percorso](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
 È possibile applicare un'animazione percorso <xref:System.Windows.Media.Animation.Storyboard> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] a una proprietà usando <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> un codice in e o il metodo nel codice. È inoltre possibile utilizzare un'animazione percorso per creare un <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a una o più proprietà. Per ulteriori informazioni sui diversi metodi per l'applicazione di animazioni, vedere Cenni preliminari sulle tecniche di [animazione](property-animation-techniques-overview.md)delle proprietà .  
  
<a name="animation_types"></a>
## <a name="path-animation-types"></a>Tipi di animazione tracciato  
 Poiché le animazioni generano valori di proprietà, esistono diversi tipi di animazione per i diversi tipi di proprietà. Per animare una <xref:System.Double> proprietà che <xref:System.Windows.Media.TranslateTransform.X%2A> accetta un <xref:System.Windows.Media.TranslateTransform>oggetto (ad esempio <xref:System.Double> la proprietà di un oggetto ), si utilizza un'animazione che produce valori. Per animare una <xref:System.Windows.Point>proprietà che accetta un <xref:System.Windows.Point> oggetto , si utilizza un'animazione che produce valori e così via.  
  
 Le classi di <xref:System.Windows.Media.Animation> animazione del percorso appartengono allo spazio dei nomi e usano la convenzione di denominazione seguente:Path animation classes belong to the namespace and use the following naming convention:  
  
 * \<Tipo>*`AnimationUsingPath`  
  
 Dove * \<Type>* è il tipo di valore che la classe anima.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre le classi di animazione tracciato seguenti.  
  
|Tipo di proprietà|Classe di animazione tracciato corrispondente|Esempio|  
|-------------------|----------------------------------------|-------------|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingPath>|[Animare un oggetto lungo un tracciato (animazione Double)](how-to-animate-an-object-along-a-path-double-animation.md)|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>|[Aggiungere un'animazione a un oggetto lungo un tracciato (animazione Matrix)](how-to-animate-an-object-along-a-path-matrix-animation.md)|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingPath>|[Animare un oggetto lungo un tracciato (animazione Point)](how-to-animate-an-object-along-a-path-point-animation.md)|  
  
 A <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> <xref:System.Windows.Media.Matrix> genera valori <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.PathGeometry%2A>dal relativo oggetto . Se utilizzato <xref:System.Windows.Media.MatrixTransform>con <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> un oggetto , un oggetto può spostare un oggetto lungo un tracciato. Se si <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> imposta la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> `true`proprietà di su , l'oggetto viene ruotato anche lungo le curve del tracciato.  
  
 A <xref:System.Windows.Media.Animation.PointAnimationUsingPath> <xref:System.Windows.Point> genera valori dalle coordinate x e <xref:System.Windows.Media.Animation.PointAnimationUsingPath.PathGeometry%2A>y dei relativi valori . Utilizzando un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> oggetto per animare una proprietà che accetta <xref:System.Windows.Point> valori, è possibile spostare un oggetto lungo un percorso. Un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> oggetto non può ruotare gli oggetti.  
  
 A <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> <xref:System.Double> genera valori <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.PathGeometry%2A>dal relativo oggetto . Impostando la <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath.Source%2A> proprietà, è possibile <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> specificare se utilizza la coordinata x, la coordinata y o l'angolo del percorso come output. È possibile <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> utilizzare un oggetto per ruotare un oggetto o spostarlo lungo l'asse x o l'asse y.  
  
<a name="pathanimationinput"></a>
## <a name="path-animation-input"></a>Input dell'animazione tracciato  
 Ogni classe di <xref:System.Windows.Media.PathGeometry> animazione percorso fornisce una proprietà per specificare il relativo input. L'animazione <xref:System.Windows.Media.PathGeometry> del percorso utilizza l'oggetto per generare i valori di output. La <xref:System.Windows.Media.PathGeometry> classe consente di descrivere più figure complesse composte da archi, curve e linee.  
  
 Al centro di <xref:System.Windows.Media.PathGeometry> un c'è una collezione di <xref:System.Windows.Media.PathFigure> oggetti; questi oggetti sono così denominati perché ogni figura <xref:System.Windows.Media.PathGeometry>descrive una forma discreta nel file . Ognuno <xref:System.Windows.Media.PathFigure> è costituito da uno o più <xref:System.Windows.Media.PathSegment> oggetti, ognuno dei quali descrive un segmento della figura.  
  
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
  
 I segmenti in <xref:System.Windows.Media.PathFigure> un vengono combinati in una singola forma geometrica, che utilizza il punto finale di un segmento come punto iniziale del segmento successivo. La <xref:System.Windows.Media.PathFigure.StartPoint%2A> proprietà <xref:System.Windows.Media.PathFigure> di un oggetto specifica il punto da cui viene disegnato il primo segmento. Ogni segmento successivo inizia in corrispondenza del punto finale del segmento precedente. Ad esempio, una `10,50` linea `10,150` verticale da <xref:System.Windows.Media.PathFigure.StartPoint%2A> a `10,50` può essere <xref:System.Windows.Media.LineSegment> definita <xref:System.Windows.Media.LineSegment.Point%2A> impostando `10,150`la proprietà su e creando un'impostazione di proprietà di .  
  
 Per ulteriori <xref:System.Windows.Media.PathGeometry> informazioni sugli oggetti, vedere Cenni preliminari sulla [geometria](geometry-overview.md).  
  
 In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è inoltre possibile utilizzare una <xref:System.Windows.Media.PathGeometry.Figures%2A> sintassi <xref:System.Windows.Media.PathGeometry>abbreviata speciale per impostare la proprietà di un oggetto . Per altre informazioni, vedere Cenni preliminari sulla [sintassi di markup del percorso.](path-markup-syntax.md)  
  
 Per altre informazioni sulla sintassi del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] percorso utilizzata nell'esempio, vedere panoramica della [sintassi](path-markup-syntax.md) di markup del percorso.  
  
## <a name="see-also"></a>Vedere anche

- [Path Animation Sample (Esempio di animazione tracciato)](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Sintassi di markup del percorso](path-markup-syntax.md)
- [Procedure relative all'animazione percorso](path-animation-how-to-topics.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)
