---
title: Cenni preliminari sulle animazioni da / To / By
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: d36be70a8c1287274c3820aec3aa789830914ceb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64615407"
---
# <a name="fromtoby-animations-overview"></a>Cenni preliminari sulle animazioni From/To/By
Questo argomento descrive come usare le animazioni From/To/By per animare le proprietà di dipendenza. Un'animazione From/To/By crea una transizione tra due valori.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le funzionalità di animazione. Per un'introduzione alle funzionalità di animazione, vedere la [Cenni preliminari sull'animazione](animation-overview.md).  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>Descrizione di un'animazione From/To/By  
 From/To/By animazione è un tipo di <xref:System.Windows.Media.Animation.AnimationTimeline> che crea una transizione tra un valore iniziale e un valore finale. La quantità di tempo necessario per completare la transizione è determinata dal <xref:System.Windows.Media.Animation.Timeline.Duration%2A> di tale animazione.  
  
 È possibile applicare From/To/By animazione a una proprietà usando un <xref:System.Windows.Media.Animation.Storyboard> nel markup e codice o tramite il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo nel codice. È anche possibile usare un'animazione From/To/By per creare un <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a una o più proprietà. Per altre informazioni sui diversi metodi per l'applicazione di animazioni, vedere [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md).  
  
 Le animazioni From/To/By non possono avere più di due valori di destinazione. Se è necessaria un'animazione con più di due valori di destinazione, usare un'animazione con fotogrammi chiave. Animazioni con fotogrammi chiave sono vedere la [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>Tipi di animazione From/To/By  
 Poiché le animazioni generano valori di proprietà, esistono diversi tipi di animazione per i diversi tipi di proprietà. Per animare una proprietà che accetta un <xref:System.Double>, ad esempio il <xref:System.Windows.FrameworkElement.Width%2A> proprietà di un elemento, usare un'animazione che produca <xref:System.Double> valori. Per animare una proprietà che accetta un <xref:System.Windows.Point>, usare un'animazione che produca <xref:System.Windows.Point> valori e così via.  
  
 Le classi di animazione From/To/By appartengono al <xref:System.Windows.Media.Animation> dello spazio dei nomi e usano la convenzione di denominazione seguente:  
  
 *\<Tipo>* `Animation`  
  
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
 Un'animazione From/To/By crea una transizione tra due valori di destinazione. È pratica comune specificare un valore iniziale (impostarlo tramite il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà) e un valore finale (impostarlo tramite la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà). È anche possibile tuttavia specificare solo un valore iniziale, un valore di destinazione o un valore di scostamento. In questi casi, l'animazione ottiene il valore di destinazione mancante dalla proprietà che viene animata. L'elenco seguente descrive le diverse modalità per specificare i valori di destinazione di un'animazione.  
  
- **Valore iniziale**  
  
     Usare il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà quando si desidera specificare in modo esplicito il valore iniziale di un'animazione. È possibile usare la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà da solo o con il <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> o <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà. Se si specifica solo il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà, le transizioni di animazione da tale valore al valore di base della proprietà animata.  
  
- **Valore finale**  
  
     Per specificare un valore finale di un'animazione, usare il <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà. Se si usa il <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà autonomamente, l'animazione ottiene il valore iniziale dalla proprietà animata o dall'output di un'altra animazione applicata alla stessa proprietà. È possibile usare la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà con il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà per specificare in modo esplicito i valori dell'animazione iniziale e finale.  
  
- **Valore di scostamento**  
  
     Il <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà consente di specificare uno scostamento anziché un esplicita valore iniziale o finale dell'animazione. Il <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà di un'animazione specifica di quanto l'animazione viene modificato un valore per la relativa durata. È possibile usare la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà da solo o con il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà. Se si specifica solo il <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà, l'animazione aggiunge il valore di offset al valore di base della proprietà o all'output di un'altra animazione.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>Uso dei valori From/To/By  
 Le sezioni seguenti descrivono come usare il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà insieme o separatamente.  
  
 Gli esempi in questa sezione ogni uso un <xref:System.Windows.Media.Animation.DoubleAnimation>, che è un tipo di animazione From/To/By, per animare la <xref:System.Windows.FrameworkElement.Width%2A> proprietà di un <xref:System.Windows.Shapes.Rectangle> ovvero 10 device independent pixel e 100 device independent pixel di larghezza.  
  
 Benché ogni esempio usi un <xref:System.Windows.Media.Animation.DoubleAnimation>, From, To e By le proprietà di tutti i From/To/By animazioni si comportano in modo identico. Anche se ognuno di questi esempi viene utilizzato un <xref:System.Windows.Media.Animation.Storyboard>, è possibile usare le animazioni From/To/By in altri modi. Per altre informazioni, vedere [Cenni preliminari sulle tecniche di animazione di proprietà](property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>Da/A  
 Quando si imposta il <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> l'animazione avanza dal valore specificato dall'insieme, i valori di <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà, al valore specificato da di <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà.  
  
 L'esempio seguente imposta la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà del <xref:System.Windows.Media.Animation.DoubleAnimation> fino a 50 e il relativo <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà su 300. Di conseguenza, il <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> viene animata da 50 a 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>A  
 Quando si imposta solo la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà, l'animazione avanza dal valore di base della proprietà animata, o dall'output di un'animazione in composizione applicata in precedenza alla stessa proprietà, al valore specificato da di <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà.  
  
 ("Composizione di animazione" fa riferimento a un <xref:System.Windows.Media.Animation.ClockState.Active> oppure <xref:System.Windows.Media.Animation.ClockState.Filling> applicata in precedenza alla stessa proprietà che è ancora attivo quando è stata applicata l'animazione corrente usando il <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> HandoffBehavior.)  
  
 L'esempio seguente imposta solo la <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> proprietà del <xref:System.Windows.Media.Animation.DoubleAnimation> su 300. Poiché è stato specificato alcun valore iniziale, il <xref:System.Windows.Media.Animation.DoubleAnimation> Usa il valore di base (100) del <xref:System.Windows.FrameworkElement.Width%2A> proprietà come valore iniziale. Il <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> viene animata da 100 al valore di destinazione dell'animazione di 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>Utente  
 Quando si imposta solo la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà di un'animazione, l'animazione avanza dal valore di base della proprietà animata, o dall'output di un'animazione in composizione alla somma di quel valore e il valore specificato da di <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà.  
  
 L'esempio seguente imposta solo la <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà del <xref:System.Windows.Media.Animation.DoubleAnimation> su 300. Poiché l'esempio non viene specificato un valore iniziale, il <xref:System.Windows.Media.Animation.DoubleAnimation> Usa il valore del prezzo di <xref:System.Windows.FrameworkElement.Width%2A> proprietà, 100, come valore iniziale. Il valore finale è determinato dall'aggiunta di <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> valore dell'animazione, 300, al valore iniziale 100: 400. Di conseguenza, il <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> viene animata da 100 a 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 Quando si imposta la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> delle proprietà di un'animazione, l'animazione avanza dal valore specificato dal <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà, al valore specificato per la somma del <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà.  
  
 L'esempio seguente imposta la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà del <xref:System.Windows.Media.Animation.DoubleAnimation> fino a 50 e il relativo <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà su 300. Il valore finale è determinato dall'aggiunta di <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> valore dell'animazione, 300, al valore iniziale 50: 350. Di conseguenza, il <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> viene animata da 50 a 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>Da  
 Quando si specifica solo le <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> valore di un'animazione, l'animazione avanza dal valore specificato da di <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà, il valore di base della proprietà animata o all'output di un'animazione in composizione.  
  
 L'esempio seguente imposta solo la <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> proprietà del <xref:System.Windows.Media.Animation.DoubleAnimation> fino a 50. Perché è stato specificato alcun valore finale, il <xref:System.Windows.Media.Animation.DoubleAnimation> Usa il valore del prezzo di <xref:System.Windows.FrameworkElement.Width%2A> proprietà, 100, come valore finale. Il <xref:System.Windows.FrameworkElement.Width%2A> del <xref:System.Windows.Shapes.Rectangle> viene animata da 50 al valore di base del <xref:System.Windows.FrameworkElement.Width%2A> proprietà, 100.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Se si impostano entrambi il <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> e il <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> delle proprietà di un'animazione, il <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> proprietà viene ignorata.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>Altri tipi di animazione  
 Le animazioni From/To/By non sono l'unico tipo di animazioni che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce: fornisce inoltre le animazioni con fotogrammi chiave e animazioni tracciato.  
  
- Un'animazione con fotogrammi chiave è applicabile a un numero qualsiasi di valori di destinazione, descritti mediante i fotogrammi chiave. Per altre informazioni, vedere la [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).  
  
- Un'animazione tracciato genera valori di output da un <xref:System.Windows.Media.PathGeometry>. Per altre informazioni, vedere la [panoramica sulle animazioni tracciato](path-animations-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente inoltre di creare i tipi di animazione personalizzata. Per altre informazioni, vedere la [Cenni preliminari sulle animazioni personalizzate](custom-animations-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Panoramica sulle animazioni tracciato](path-animations-overview.md)
- [Cenni preliminari sulle animazioni personalizzate](custom-animations-overview.md)
- [Esempio di valori di destinazione dell'animazione From/To/By](https://go.microsoft.com/fwlink/?LinkID=159988)
