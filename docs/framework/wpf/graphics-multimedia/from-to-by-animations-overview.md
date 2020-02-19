---
title: Cenni preliminari sulle animazioni from-to-by
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 661c035f55ba1fb550726d75921cd01a72b2eecc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449000"
---
# <a name="fromtoby-animations-overview"></a>Cenni preliminari sulle animazioni From/To/By
Questo argomento descrive come usare le animazioni From/To/By per animare le proprietà di dipendenza. Un'animazione From/To/By crea una transizione tra due valori.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario avere familiarità con le funzionalità di animazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per un'introduzione alle funzionalità di animazione, vedere [Cenni preliminari sull'animazione](animation-overview.md).  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>Descrizione di un'animazione From/To/By  
 Un'animazione from/to/by è un tipo di <xref:System.Windows.Media.Animation.AnimationTimeline> che crea una transizione tra un valore iniziale e un valore finale. La quantità di tempo necessaria per il completamento della transizione è determinata dall'<xref:System.Windows.Media.Animation.Timeline.Duration%2A> dell'animazione.  
  
 È possibile applicare un'animazione from/to/by a una proprietà usando un <xref:System.Windows.Media.Animation.Storyboard> nel markup e nel codice oppure usando il metodo <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> nel codice. È anche possibile usare un'animazione from/to/by per creare una <xref:System.Windows.Media.Animation.AnimationClock> e applicarla a una o più proprietà. Per altre informazioni sui diversi metodi per l'applicazione di animazioni, vedere [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md).  
  
 Le animazioni From/To/By non possono avere più di due valori di destinazione. Se è necessaria un'animazione con più di due valori di destinazione, usare un'animazione con fotogrammi chiave. Le animazioni con fotogrammi chiave sono descritte in [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>Tipi di animazione From/To/By  
 Poiché le animazioni generano valori di proprietà, esistono diversi tipi di animazione per i diversi tipi di proprietà. Per animare una proprietà che accetta un <xref:System.Double>, ad esempio la proprietà <xref:System.Windows.FrameworkElement.Width%2A> di un elemento, usare un'animazione che produce valori di <xref:System.Double>. Per animare una proprietà che accetta una <xref:System.Windows.Point>, utilizzare un'animazione che produce valori <xref:System.Windows.Point> e così via.  
  
 Le classi di animazione from/to/by appartengono allo spazio dei nomi <xref:System.Windows.Media.Animation> e utilizzano la convenzione di denominazione seguente:  
  
 *tipo di\<>* `Animation`  
  
 Dove *\<Tipo>* è il tipo di valore cui è stata aggiunta un'animazione dalla classe.  
  
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
 Un'animazione From/To/By crea una transizione tra due valori di destinazione. È normale specificare un valore iniziale (impostarlo utilizzando la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>) e un valore finale (impostarlo utilizzando la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>). È anche possibile tuttavia specificare solo un valore iniziale, un valore di destinazione o un valore di scostamento. In questi casi, l'animazione ottiene il valore di destinazione mancante dalla proprietà che viene animata. L'elenco seguente descrive le diverse modalità per specificare i valori di destinazione di un'animazione.  
  
- **Valore iniziale**  
  
     Utilizzare la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> quando si desidera specificare in modo esplicito il valore iniziale di un'animazione. È possibile utilizzare la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> da sola o con la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> o <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>. Se si specifica solo la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, l'animazione esegue la transizione da tale valore al valore di base della proprietà animata.  
  
- **Valore finale**  
  
     Per specificare un valore finale di un'animazione, usare la relativa proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>. Se si usa la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> autonomamente, l'animazione ottiene il valore iniziale dalla proprietà a cui si sta aggiungendo un'animazione o dall'output di un'altra animazione applicata alla stessa proprietà. È possibile utilizzare la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> insieme alla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> per specificare in modo esplicito i valori iniziale e finale per l'animazione.  
  
- **Valore di scostamento**  
  
     Il <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà consente di specificare un offset anziché un valore iniziale o finale esplicito per l'animazione. La proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> di un'animazione specifica la quantità di tempo per cui l'animazione modifica un valore per la relativa durata. È possibile utilizzare la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> da sola o con la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>. Se si specifica solo la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, l'animazione aggiunge il valore di offset al valore di base della proprietà o all'output di un'altra animazione.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>Uso dei valori From/To/By  
 Le sezioni seguenti descrivono come usare le proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> insieme o separatamente.  
  
 Gli esempi in questa sezione usano ogni un <xref:System.Windows.Media.Animation.DoubleAnimation>, ovvero un tipo di animazione from/to/by, per animare la proprietà <xref:System.Windows.FrameworkElement.Width%2A> di un <xref:System.Windows.Shapes.Rectangle> che corrisponde a 10 pixel indipendenti dal dispositivo e 100 dispositivi indipendenti.  
  
 Sebbene ogni esempio usi un <xref:System.Windows.Media.Animation.DoubleAnimation>, le proprietà from, to e by di tutte le animazioni from/to/by si comportano in modo identico. Sebbene ognuno di questi esempi usi una <xref:System.Windows.Media.Animation.Storyboard>, è possibile usare le animazioni from/to/by in altri modi. Per altre informazioni, vedere [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>Da/A  
 Quando si impostano insieme i valori <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, l'animazione avanza dal valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, al valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  
  
 Nell'esempio seguente viene impostata la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> della <xref:System.Windows.Media.Animation.DoubleAnimation> su 50 e la relativa proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> su 300. Di conseguenza, il <xref:System.Windows.FrameworkElement.Width%2A> della <xref:System.Windows.Shapes.Rectangle> viene animato da 50 a 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>Per  
 Quando si imposta solo la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, l'animazione avanza dal valore di base della proprietà animata o dall'output di un'animazione di composizione applicata in precedenza alla stessa proprietà, al valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  
  
 ("Animazione di composizione" si riferisce a una <xref:System.Windows.Media.Animation.ClockState.Active> o <xref:System.Windows.Media.Animation.ClockState.Filling> animazione applicata in precedenza alla stessa proprietà che è ancora in vigore quando l'animazione corrente è stata applicata usando il comportamento di continuità <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>.)  
  
 Nell'esempio seguente viene impostata solo la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> della <xref:System.Windows.Media.Animation.DoubleAnimation> su 300. Poiché non è stato specificato alcun valore iniziale, il <xref:System.Windows.Media.Animation.DoubleAnimation> utilizza il valore di base (100) della proprietà <xref:System.Windows.FrameworkElement.Width%2A> come valore iniziale. Il <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> viene animato da 100 al valore di destinazione dell'animazione 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>Utente  
 Quando si imposta solo la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> di un'animazione, l'animazione avanza dal valore di base della proprietà a cui si sta aggiungendo un'animazione oppure dall'output di un'animazione di composizione alla somma di tale valore e del valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
 Nell'esempio seguente viene impostata solo la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> della <xref:System.Windows.Media.Animation.DoubleAnimation> su 300. Poiché nell'esempio non viene specificato un valore iniziale, il <xref:System.Windows.Media.Animation.DoubleAnimation> utilizza il valore di base della proprietà <xref:System.Windows.FrameworkElement.Width%2A>, 100, come valore iniziale. Il valore finale è determinato dall'aggiunta del valore <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> dell'animazione 300 al valore iniziale, 100:400. Di conseguenza, il <xref:System.Windows.FrameworkElement.Width%2A> della <xref:System.Windows.Shapes.Rectangle> viene animato da 100 a 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 Quando si impostano le proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> di un'animazione, l'animazione avanza dal valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, al valore specificato dalla somma delle proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
 Nell'esempio seguente viene impostata la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> della <xref:System.Windows.Media.Animation.DoubleAnimation> su 50 e la relativa proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> su 300. Il valore finale è determinato dall'aggiunta del valore <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> dell'animazione 300 al valore iniziale, 50:350. Di conseguenza, il <xref:System.Windows.FrameworkElement.Width%2A> della <xref:System.Windows.Shapes.Rectangle> viene animato da 50 a 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>Da  
 Quando si specifica solo il valore <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> di un'animazione, l'animazione avanza dal valore specificato dalla proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, al valore di base della proprietà che viene animata o all'output di un'animazione di composizione.  
  
 Nell'esempio seguente viene impostata solo la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> della <xref:System.Windows.Media.Animation.DoubleAnimation> su 50. Poiché non è stato specificato alcun valore finale, il <xref:System.Windows.Media.Animation.DoubleAnimation> utilizza il valore di base della proprietà <xref:System.Windows.FrameworkElement.Width%2A>, 100, come valore finale. Il <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> viene animato da 50 al valore di base della proprietà <xref:System.Windows.FrameworkElement.Width%2A>, 100.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Se si impostano le proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> di un'animazione, la proprietà <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> viene ignorata.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>Altri tipi di animazione  
 Le animazioni from/to/by non sono l'unico tipo di animazione fornito da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: fornisce anche animazioni con fotogrammi chiave e animazioni di percorso.  
  
- Un'animazione con fotogrammi chiave è applicabile a un numero qualsiasi di valori di destinazione, descritti mediante i fotogrammi chiave. Per altre informazioni, vedere [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).  
  
- Un'animazione tracciato genera valori di output da un <xref:System.Windows.Media.PathGeometry>. Per altre informazioni, vedere [Cenni preliminari sulle animazioni Path](path-animations-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente inoltre di creare i tipi di animazione personalizzata. Per altre informazioni, vedere [Cenni preliminari sulle animazioni personalizzate](custom-animations-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Panoramica sulle animazioni tracciato](path-animations-overview.md)
- [Cenni preliminari sulle animazioni personalizzate](custom-animations-overview.md)
- [Esempio di valori di destinazione dell'animazione From/To/By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
