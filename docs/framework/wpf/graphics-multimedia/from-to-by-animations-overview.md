---
title: Cenni preliminari sulle animazioni da-a-da
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 135f01823d374b30f8d4d41762d2267a254f98c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186454"
---
# <a name="fromtoby-animations-overview"></a>Cenni preliminari sulle animazioni From/To/By
Questo argomento descrive come usare le animazioni From/To/By per animare le proprietà di dipendenza. Un'animazione From/To/By crea una transizione tra due valori.  
  
<a name="prereq"></a>
## <a name="prerequisites"></a>Prerequisites  
 Per comprendere questo argomento, è [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] necessario avere familiarità con le funzionalità delle animazioni. Per un'introduzione alle funzionalità di animazione, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
<a name="whatisanimation"></a>
## <a name="what-is-a-fromtoby-animation"></a>Descrizione di un'animazione From/To/By  
 Un'animazione From/To/By <xref:System.Windows.Media.Animation.AnimationTimeline> è un tipo di che crea una transizione tra un valore iniziale e un valore finale. La quantità di tempo necessaria per il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> completamento della transizione è determinata dall'animazione.  
  
 È possibile applicare un From/To/By animazione <xref:System.Windows.Media.Animation.Storyboard> a una proprietà utilizzando <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> un in markup e codice o utilizzando il metodo nel codice. È inoltre possibile utilizzare un From/To/By Animation per creare un'animazione <xref:System.Windows.Media.Animation.AnimationClock> e applicarla a una o più proprietà. Per ulteriori informazioni sui diversi metodi per l'applicazione di animazioni, vedere Cenni preliminari sulle tecniche di [animazione](property-animation-techniques-overview.md)delle proprietà .  
  
 Le animazioni From/To/By non possono avere più di due valori di destinazione. Se è necessaria un'animazione con più di due valori di destinazione, usare un'animazione con fotogrammi chiave. Le animazioni con fotogrammi chiave sono descritte in [Cenni preliminari sulle animazioni](key-frame-animations-overview.md)con fotogrammi chiave .  
  
<a name="animation_types"></a>
## <a name="fromtoby-animation-types"></a>Tipi di animazione From/To/By  
 Poiché le animazioni generano valori di proprietà, esistono diversi tipi di animazione per i diversi tipi di proprietà. Per animare una <xref:System.Double>proprietà che <xref:System.Windows.FrameworkElement.Width%2A> accetta un oggetto , ad <xref:System.Double> esempio la proprietà di un elemento, utilizzare un'animazione che produce valori. Per animare una <xref:System.Windows.Point>proprietà che accetta <xref:System.Windows.Point> un oggetto , utilizzare un'animazione che produce valori e così via.  
  
 Le classi di animazione From/To/By appartengono allo <xref:System.Windows.Media.Animation> spazio dei nomi e utilizzano la convenzione di denominazione seguente:  
  
 * \<Tipo>*`Animation`  
  
 Dove * \<Type>* è il tipo di valore che la classe anima.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre le classi di animazioni From/To/By seguenti.  
  
|Tipo di proprietà|Classe di animazione From/To/By corrispondente|  
|-------------------|------------------------------------------------|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimation>|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimation>|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16Animation>|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32Animation>|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64Animation>|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimation>|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimation>|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimation>|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimation>|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimation>|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimation>|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimation>|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimation>|  
  
<a name="anim_values"></a>
## <a name="target-values"></a>Valori di destinazione  
 Un'animazione From/To/By crea una transizione tra due valori di destinazione. È comune specificare un valore iniziale <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> (impostarlo utilizzando la proprietà ) <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> e un valore finale (impostarlo utilizzando la proprietà ). È anche possibile tuttavia specificare solo un valore iniziale, un valore di destinazione o un valore di scostamento. In questi casi, l'animazione ottiene il valore di destinazione mancante dalla proprietà che viene animata. L'elenco seguente descrive le diverse modalità per specificare i valori di destinazione di un'animazione.  
  
- **Valore iniziale**  
  
     Utilizzare <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> la proprietà quando si desidera specificare in modo esplicito il valore iniziale di un'animazione. È possibile <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> utilizzare la proprietà da <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> sola o con la proprietà o . Se si specifica <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> solo la proprietà , l'animazione passa da tale valore al valore di base della proprietà animata.  
  
- **Valore finale**  
  
     Per specificare un valore finale <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> di un'animazione, utilizzare la relativa proprietà. Se si <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> utilizza la proprietà da sola, l'animazione ottiene il valore iniziale dalla proprietà che viene animata o dall'output di un'altra animazione applicata alla stessa proprietà. È possibile <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> utilizzare la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà con la proprietà per specificare in modo esplicito i valori iniziali e finali per l'animazione.  
  
- **Valore di scostamento**  
  
     La <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà consente di specificare un offset anziché un valore iniziale o finale esplicito per l'animazione. La <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà di un'animazione specifica in base a quanto l'animazione modifica un valore per tutta la durata. È possibile <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> utilizzare la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> da sola o con la proprietà . Se si specifica <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> solo la proprietà , l'animazione aggiunge il valore di offset al valore di base della proprietà o all'output di un'altra animazione.  
  
<a name="examples"></a>
## <a name="using-fromtoby-values"></a>Uso dei valori From/To/By  
 Nelle sezioni seguenti viene <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>descritto <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>come <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> utilizzare le proprietà , e insieme o separatamente.  
  
 Negli esempi di questa <xref:System.Windows.Media.Animation.DoubleAnimation>sezione viene utilizzata ciascuna un'animazione From/To/By per animare la <xref:System.Windows.FrameworkElement.Width%2A> proprietà di un <xref:System.Windows.Shapes.Rectangle> oggetto di 10 pixel di 10 pixel indipendente dal dispositivo e un'animazione di 100 pixel indipendenti dal dispositivo.  
  
 Anche se ogni <xref:System.Windows.Media.Animation.DoubleAnimation>esempio utilizza un , le proprietà From, To e By di tutte le animazioni From/To/By si comportano in modo identico. Sebbene ognuno di <xref:System.Windows.Media.Animation.Storyboard>questi esempi utilizzi un oggetto , è possibile usare le animazioni From/To/By in altri modi. Per ulteriori informazioni, consultate [Cenni preliminari](property-animation-techniques-overview.md)sulle tecniche di animazione delle proprietà.  
  
### <a name="fromto"></a>Da/A  
 Quando si <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> impostano i valori e <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> insieme, l'animazione <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> avanza dal valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà, al valore specificato dalla proprietà .  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> la <xref:System.Windows.Media.Animation.DoubleAnimation> proprietà dell'oggetto <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> viene impostata su 50 e la relativa proprietà su 300. Di conseguenza, <xref:System.Windows.FrameworkElement.Width%2A> il <xref:System.Windows.Shapes.Rectangle> del è animato da 50 a 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>A  
 Quando si imposta <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> solo la proprietà , l'animazione avanza dal valore di base della proprietà animata o dall'output di un'animazione di composizione precedentemente applicata alla stessa proprietà, al valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà .  
  
 ("Composizione animazione" si <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.ClockState.Filling> riferisce a un'animazione che in precedenza veniva applicata <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> alla stessa proprietà che è ancora attiva quando l'animazione corrente è stata applicata utilizzando il comportamento di passaggio.)  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> viene impostata solo la proprietà dell'oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> su 300. Poiché non è stato <xref:System.Windows.Media.Animation.DoubleAnimation> specificato alcun valore iniziale, <xref:System.Windows.FrameworkElement.Width%2A> il valore di base (100) della proprietà viene utilizzato come valore iniziale. <xref:System.Windows.FrameworkElement.Width%2A> L'oggetto <xref:System.Windows.Shapes.Rectangle> viene animato da 100 al valore di destinazione dell'animazione di 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>Con  
 Quando si imposta <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> solo la proprietà di un'animazione, l'animazione avanza dal valore di base della proprietà a cui si sta aggiungendo <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> un'animazione o dall'output di un'animazione di composizione alla somma di tale valore e del valore specificato dalla proprietà.  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> viene impostata solo la proprietà dell'oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> su 300. Poiché nell'esempio non viene <xref:System.Windows.Media.Animation.DoubleAnimation> specificato un valore <xref:System.Windows.FrameworkElement.Width%2A> iniziale, viene utilizzato il valore di base della proprietà 100 come valore iniziale. Il valore finale viene <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> determinato aggiungendo il valore dell'animazione, 300, al valore iniziale, 100: 400. Di conseguenza, <xref:System.Windows.FrameworkElement.Width%2A> l'oggetto <xref:System.Windows.Shapes.Rectangle> viene animato da 100 a 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 Quando si <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> impostano le proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> e di un'animazione, l'animazione avanza dal valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà, al valore specificato dalla somma delle proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e .  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> la <xref:System.Windows.Media.Animation.DoubleAnimation> proprietà dell'oggetto <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> viene impostata su 50 e la relativa proprietà su 300. Il valore finale viene <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> determinato aggiungendo il valore dell'animazione, 300, al valore iniziale, 50: 350. Di conseguenza, <xref:System.Windows.FrameworkElement.Width%2A> l'oggetto <xref:System.Windows.Shapes.Rectangle> viene animato da 50 a 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>From  
 Quando si specifica <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> solo il valore di un'animazione, l'animazione avanza dal valore specificato dalla <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà, al valore di base della proprietà che viene animata o all'output di un'animazione di composizione.  
  
 Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> viene impostata solo la proprietà dell'oggetto <xref:System.Windows.Media.Animation.DoubleAnimation> su 50. Poiché non è stato <xref:System.Windows.Media.Animation.DoubleAnimation> specificato alcun valore <xref:System.Windows.FrameworkElement.Width%2A> finale, viene utilizzato il valore di base della proprietà 100 come valore finale. <xref:System.Windows.FrameworkElement.Width%2A> L'oggetto <xref:System.Windows.Shapes.Rectangle> viene animato da 50 <xref:System.Windows.FrameworkElement.Width%2A> al valore di base della proprietà 100.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Se si impostano entrambe le <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> e le proprietà di un'animazione, la proprietà viene ignorata.  
  
<a name="otheranimationtypes"></a>
## <a name="other-animation-types"></a>Altri tipi di animazione  
 Le animazioni From/To/By non sono [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'unico tipo di animazioni che fornisce: fornisce anche animazioni con fotogrammi chiave e animazioni di percorso.  
  
- Un'animazione con fotogrammi chiave è applicabile a un numero qualsiasi di valori di destinazione, descritti mediante i fotogrammi chiave. Per ulteriori informazioni, consultate Cenni preliminari sulle animazioni con [fotogrammi chiave.](key-frame-animations-overview.md)  
  
- Un'animazione percorso genera <xref:System.Windows.Media.PathGeometry>valori di output da un oggetto . Per ulteriori informazioni, vedere [Cenni preliminari sulle animazioni](path-animations-overview.md)di percorso .  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente inoltre di creare i tipi di animazione personalizzata. Per ulteriori informazioni, vedere [Cenni preliminari sulle animazioni personalizzate](custom-animations-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Panoramica sulle animazioni tracciato](path-animations-overview.md)
- [Cenni preliminari sulle animazioni personalizzate](custom-animations-overview.md)
- [Esempio di valori di destinazione dell'animazione From/To/By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
