---
title: Cenni preliminari sulle animazioni con fotogrammi chiave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], key-frame
- key frames [WPF], about key-frame animations
- multiple animation target values [WPF]
ms.assetid: 10028f97-bb63-41fc-b8ad-663dac7ea203
ms.openlocfilehash: a4606b73835087a406d989960d7a6e24ad218769
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362981"
---
# <a name="key-frame-animations-overview"></a>Cenni preliminari sulle animazioni con fotogrammi chiave
Questo argomento presenta le animazioni con fotogrammi chiave. Le animazioni con fotogrammi chiave consentono di usare più di due valori di destinazione e di controllare il metodo di interpolazione di un'animazione.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questi cenni preliminari, è necessario conoscere le animazioni e le sequenze temporali di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Per un'introduzione alle animazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md). È anche utile per acquisire familiarità con le animazioni From/To/By. Per altre informazioni, vedere Cenni preliminari sulle animazioni From/To/By.  
  
<a name="whatisakeyframeanimation"></a>   
## <a name="what-is-a-key-frame-animation"></a>Che cos'è un'animazione con fotogrammi chiave?  
 Questo tipo di animazione, così come quelle From/To/By, aggiunge un'animazione al valore di una proprietà di destinazione. Crea una transizione tra i relativi valori di destinazione sulla relativa <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Se tuttavia un'animazione From/To/By crea una transizione tra due valori, una singola animazione con fotogrammi chiave può creare transizioni tra un qualsiasi numero di valori di destinazione. A differenza di un'animazione From/To/By , un'animazione con fotogrammi chiave non ha le proprietà From, To o By con cui impostare i relativi valori di destinazione. I valori di destinazione di un'animazione con fotogrammi chiave vengono descritti tramite oggetti fotogrammi chiave (da qui il termine "animazione con fotogrammi chiave"). Per specificare i valori di destinazione dell'animazione, creare oggetti fotogrammi chiave e aggiungerli dell'animazione <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> raccolta. Quando viene eseguita l'animazione, viene eseguita una transizione tra i fotogrammi specificati.  
  
 Oltre a supportare più valori di destinazione, alcuni metodi di fotogrammi chiave supportano anche più metodi di interpolazione. Il metodo di interpolazione di un'animazione definisce la modalità di transizione da un valore a quello successivo. Esistono tre tipi di interpolazione: discreta, lineare e spline.  
  
 Per aggiungere un'animazione con fotogrammi chiave, completare la procedura seguente.  
  
-   Dichiarare l'animazione e specificare la relativa <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, come si farebbe per un'animazione from/to/by.  
  
-   Per ogni valore di destinazione, creare un fotogramma chiave del tipo appropriato, impostarne il valore e <xref:System.Windows.Media.Animation.KeyTime>e aggiungerlo all'animazione <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> raccolta.  
  
-   Associare l'animazione a una proprietà, come si farebbe con un'animazione From/To/By. Per altre informazioni sull'applicazione di un'animazione a una proprietà usando uno storyboard, vedere [Cenni preliminari sugli storyboard](storyboards-overview.md).  
  
 L'esempio seguente usa un' <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> animare una <xref:System.Windows.Shapes.Rectangle> elemento in quattro posizioni diverse.  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
 Come From/To/By animazione, un'animazione con fotogrammi chiave può essere applicata a una proprietà usando un <xref:System.Windows.Media.Animation.Storyboard> nel markup e codice o tramite il <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metodo nel codice. È anche possibile usare un'animazione con fotogrammi chiave per creare un <xref:System.Windows.Media.Animation.AnimationClock> e applicarlo a una o più proprietà. Per altre informazioni sui diversi metodi per l'applicazione di animazioni, vedere [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="key-frame-animation-types"></a>Tipi di animazione con fotogrammi chiave  
 Poiché le animazioni generano valori di proprietà, esistono diversi tipi di animazione per i diversi tipi di proprietà. Per animare una proprietà che accetta un <xref:System.Double> (ad esempio un elemento <xref:System.Windows.FrameworkElement.Width%2A> proprietà), usare un'animazione che produce <xref:System.Double> valori. Per animare una proprietà che accetta un <xref:System.Windows.Point>, usare un'animazione che produce <xref:System.Windows.Point> valori e così via.  
  
 Le classi di animazione con fotogrammi chiave appartengono al <xref:System.Windows.Media.Animation> dello spazio dei nomi e sono conformi alla convenzione di denominazione seguente:  
  
 *\<Tipo>* `AnimationUsingKeyFrames`  
  
 Dove *\<Tipo>* è il tipo di valore cui è stata aggiunta un'animazione dalla classe.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre le classi di animazione con fotogrammi chiave seguenti.  
  
|Tipo di proprietà|Classe di animazione From/To/By corrispondente|Metodi di interpolazione supportati|  
|-------------------|------------------------------------------------|-------------------------------------|  
|<xref:System.Boolean>|<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>|Discreta|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16AnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32AnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64AnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>|Discreta|  
|<xref:System.Object>|<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>|Discreta|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.String>|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Discreta|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>|Discreta, lineare, spline|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimationUsingKeyFrames>|Discreta, lineare, spline|  
  
<a name="animation_target_values"></a>   
## <a name="target-values-key-frames-and-key-times"></a>Valori di destinazione (fotogrammi chiave) e chiavi temporali  
 Così come esistono diversi tipi di animazioni con fotogrammi chiave per l'animazione di diversi tipi di proprietà, esistono anche diversi tipi di oggetti fotogrammi chiave: uno per ogni tipo di valore animato e metodo di interpolazione supportato. I tipi di fotogrammi chiave sono conformi alle convenzione di denominazione seguente:  
  
 *\<Metodo di interpolazione>\<Tipo>* `KeyFrame`  
  
 Dove *\<Metodo di interpolazione>* è il metodo di interpolazione usato dal fotogramma chiave e *\<Tipo>* è il tipo di valore cui è stata aggiunta un'animazione dalla classe. Un'animazione con fotogrammi chiave che supporta tutti e tre i metodi di interpolazione disporrà di tre tipi di fotogrammi chiave che è possibile usare. Ad esempio, è possibile usare tre tipi di fotogrammi chiave con una <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>: <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>, <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>, e <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>. I metodi di interpolazione sono descritti in dettaglio in una sezione successiva.  
  
 Lo scopo principale di un fotogramma chiave consiste nello specificare un <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> e un <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>. Ogni tipo di fotogramma chiave offre queste due proprietà.  
  
-   Il <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> proprietà specifica il valore di destinazione per quel fotogramma chiave.  
  
-   Il <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> proprietà specifica quando (all'interno dell'animazione <xref:System.Windows.Media.Animation.Timeline.Duration%2A>) di un fotogramma chiave <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> viene raggiunto.  
  
 Quando viene avviata un'animazione con fotogrammi chiave, esegue l'iterazione attraverso i relativi fotogrammi chiave nell'ordine definito dalla loro <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> proprietà.  
  
-   Se non è presente alcun fotogramma chiave all'ora 0, l'animazione crea una transizione tra il valore corrente della proprietà di destinazione e il <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> del primo fotogramma chiave; in caso contrario, l'output dell'animazione valore diventa il valore del primo fotogramma chiave.  
  
-   L'animazione crea una transizione tra il <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> dei fotogrammi chiave primi e secondo usando il metodo di interpolazione specificato dal secondo fotogramma chiave. La transizione inizia in corrispondenza del primo fotogramma chiave <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> e termina quando il secondo fotogramma chiave <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> viene raggiunto.  
  
-   L'animazione continua, creando transizioni tra ogni fotogramma chiave successivo e quello precedente.  
  
-   Infine, le transizioni di animazione al valore del fotogramma chiave con la maggiore chiave temporale che è uguale a o minore dell'animazione <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 Se l'animazione <xref:System.Windows.Media.Animation.Timeline.Duration%2A> viene <xref:System.Windows.Duration.Automatic%2A> o dai relativi <xref:System.Windows.Media.Animation.Timeline.Duration%2A> è uguale all'ora dell'ultimo fotogramma chiave, l'animazione viene terminata. In caso contrario, se l'animazione <xref:System.Windows.Duration> è maggiore della chiave temporale dell'ultimo fotogramma chiave, l'animazione mantiene il valore del fotogramma chiave fino a quando non raggiunge la fine del relativo <xref:System.Windows.Duration>. Come tutte le animazioni, un'animazione con fotogrammi chiave Usa relativo <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> proprietà per determinare se mantiene il valore finale quando raggiunge la fine del periodo attivo. Per altre informazioni, vedere [Cenni preliminari sui comportamenti temporali](timing-behaviors-overview.md).  
  
 L'esempio seguente usa il <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> oggetto definito nell'esempio precedente per illustrare come il <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> e <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> funzionamento delle proprietà.  
  
-   Il primo fotogramma chiave imposta immediatamente il valore di output dell'animazione su 0.  
  
-   Il secondo fotogramma chiave aggiunge un'animazione da 0 a 350. Viene avviato dopo la fine del primo fotogramma chiave (0 secondi), viene riprodotto per 2 secondi e viene terminato alle 0:0:2.  
  
-   Il terzo fotogramma chiave aggiunge un'animazione da 350 a 50. Viene avviato dopo la fine del secondo fotogramma chiave (2 secondi), viene riprodotto per 5 secondi e viene terminato alle 0:0:7.  
  
-   Il quarto fotogramma chiave aggiunge un'animazione da 50 a 200. Viene avviato dopo la fine del terzo fotogramma chiave (7 secondi), viene riprodotto per 1 secondo e viene terminato alle 0:0:8.  
  
-   Poiché il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> dell'animazione è stata impostata su 10 secondi, l'animazione mantiene il relativo valore finale per due secondi prima di terminare in fase di = 0:0:10.  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
<a name="interpolationmethods"></a>   
## <a name="interpolation-methods"></a>Metodi di interpolazione  
 Nelle sezioni precedenti è stato indicato che alcune animazioni con fotogrammi chiave supportano più metodi di interpolazione. L'interpolazione di un'animazione descrive la modalità di transizione di un'animazione tra valori per la relativa durata. Selezionando il tipo di fotogramma chiave da usare con l'animazione, è possibile definire il metodo di interpolazione per tale segmento di fotogrammi chiave. Esistono tre diversi tipi di metodi di interpolazione: lineare, discreta e spline.  
  
### <a name="linear-interpolation"></a>Interpolazione lineare  
 Con l'interpolazione lineare, l'animazione avanza a una velocità costante della durata del segmento. Se ad esempio un segmento di fotogramma chiave esegue una transizione da 0 a 10 per una durata di 5 secondi, l'animazione restituirà i valori seguenti alle ore specificate:  
  
|Ora|Valore di output|  
|----------|------------------|  
|0|0|  
|1|2|  
|2|4|  
|3|6|  
|4|8|  
|4.25|8.5|  
|4.5|9|  
|5|10|  
  
### <a name="discrete-interpolation"></a>Interpolazione discreta  
 Con l'interpolazione discreta, la funzione di animazione passa da un valore a quello successivo senza interpolazione. Se un segmento di fotogramma chiave esegue una transizione da 0 a 10 per una durata di 5 secondi, l'animazione restituirà i valori seguenti alle ore specificate:  
  
|Ora|Valore di output|  
|----------|------------------|  
|0|0|  
|1|0|  
|2|0|  
|3|0|  
|4|0|  
|4.25|0|  
|4.5|0|  
|5|10|  
  
 Si noti come l'animazione non modifica il valore di output fino alla fine della durata del segmento.  
  
 L'interpolazione spline è più complessa. e viene descritta nella sezione successiva.  
  
<a name="anim_spline"></a>   
### <a name="splined-interpolation"></a>Interpolazione spline  
 L'interpolazione spline può essere usata per ottenere effetti temporali più realistici. Poiché le animazioni vengono spesso usate per riprodurre gli effetti che si verificano nel mondo reale, gli sviluppatori potrebbero aver bisogno di controllare in modo accurato l'accelerazione e la decelerazione degli oggetti e modificare con precisione i segmenti temporali. I fotogrammi chiave spline consentono di eseguire animazioni con l'interpolazione spline. Con altri fotogrammi chiave, si specifica un <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> e <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>. Con un fotogramma chiave spline, si specifica anche un <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>. L'esempio seguente mostra un singolo fotogramma chiave spline per un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. Si noti che il <xref:System.Windows.Media.Animation.KeySpline> proprietà; che è ciò che rende un fotogramma chiave spline diverso dagli altri tipi di fotogrammi chiave.  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Una curva di Bézier cubica è definita da un punto iniziale, un punto finale e due punti di controllo. Il <xref:System.Windows.Media.Animation.KeySpline> proprietà di un fotogramma chiave spline definisce i due punti di controllo di una curva di Bézier che si estende da (0,0) a (1,1). Il primo punto di controllo determina il fattore di curvatura della prima metà della curva di Bézier e il secondo punto di controllo determina il fattore di curvatura della seconda metà del segmento di Bézier. La curva risultante descrive la frequenza di modifica per quel fotogramma chiave spline. Maggiore è l'inclinazione della curva, più elevata sarà la velocità con la quale il fotogramma chiave modifica i suoi valori. Man mano che la curva si appiattisce, il fotogramma chiave modifica i valori più lentamente.  
  
 È possibile usare <xref:System.Windows.Media.Animation.KeySpline> simulare traiettorie fisiche, ad esempio che rientrano acqua o rimbalza sfere o applicare altri "variazione in entrata" e "variazione in uscita" effetti alle animazioni di movimento. Per gli effetti con interazione dell'utente come le dissolvenze sullo sfondo o la riassociazione del pulsante di controllo, è possibile applicare l'interpolazione spline per aumentare o diminuire in modo specifico la velocità di modifica di un'animazione.  
  
 Nell'esempio seguente viene specificato un <xref:System.Windows.Media.Animation.KeySpline> pari a 0,1 1,0, che crea la curva di Bézier seguente.  
  
 ![Una curva di Bézier](./media/graphicsmm-keyspline-0-1-1-0.png "graphicsmm_keyspline_0_1_1_0")  
Un key spline con punti di controllo (0.0, 1.0) e (1.0, 0.0)  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 L'animazione aggiunta a questo fotogramma chiave all'inizio è rapida, poi rallenta e quindi accelera nuovamente prima della fine.  
  
 Nell'esempio seguente viene specificato un <xref:System.Windows.Media.Animation.KeySpline> di 0.75,1.0 0.5,0.25, che crea la curva di Bézier seguente.  
  
 ![Una curva di Bézier](./media/graphicsmm-keyspline-025-050-075-10.png "graphicsmm_keyspline_025_050_075_10")  
Un key spline con punti di controllo (0.25, 0.5) e (0.75, 1.0)  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  
  
 Poiché la curvatura della curva di Bézier cambia molto poco, l'animazione aggiunta a questo fotogramma chiave ha una velocità quasi costante e rallenta leggermente verso la fine.  
  
 L'esempio seguente usa un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> per animare la posizione del rettangolo. Poiché il <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> Usa <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> oggetti, la transizione tra ogni valore del fotogramma chiave Usa l'interpolazione spline.  
  
 [!code-xaml[keyframes_ovw_snippet#SplinedInterpolationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  
  
 L'interpolazione spline può risultare difficile da comprendere. Può essere utile fare delle prove con impostazioni diverse. L'[esempio di animazione con key spline](https://go.microsoft.com/fwlink/?LinkID=160011) consente di modificare i valori key spline e di visualizzarne il risultato su un'animazione.  
  
<a name="combininginterpolationmethods"></a>   
### <a name="combining-interpolation-methods"></a>Uso combinato dei metodi di interpolazione  
 È possibile usare i fotogrammi chiave con tipi di interpolazione diversi in una singola animazione con fotogrammi chiave. Quando si susseguono animazioni con due fotogrammi chiave con interpolazioni diverse, il metodo di interpolazione del secondo fotogramma chiave viene usato per creare la transizione dal primo valore al secondo.  
  
 Nell'esempio seguente, un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> creato che usa l'interpolazione lineare, spline e discreta.  
  
 [!code-xaml[keyframes_ovw_snippet#ComboInterpolationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#combointerpolationexample)]  
  
<a name="keytimes"></a>   
## <a name="more-about-duration-and-key-times"></a>Altre informazioni sulla durata e sulle chiavi temporali  
 Analogamente alle altre animazioni, animazioni con fotogrammi chiave hanno un <xref:System.Windows.Duration> proprietà. Oltre a specificare l'animazione <xref:System.Windows.Duration>, è necessario specificare quale parte della durata viene assegnato a ogni fotogramma chiave. A tale scopo, che descrivono un <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> per ognuno dei fotogrammi chiave dell'animazione. Ogni fotogramma chiave <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> specifica quando termina tale fotogramma chiave.  
  
 Il <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> proprietà non specifica la durata di riproduzione della chiave temporale. La quantità di tempo di riproduzione di un fotogramma chiave dipende da quando termina il fotogramma chiave, da quando è terminato il fotogramma chiave precedente e dalla durata dell'animazione. Chiavi temporali possono essere specificate come un valore di ora, una percentuale o valori speciali <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 L'elenco seguente descrive modi diversi per specificare le chiavi temporali.  
  
### <a name="timespan-values"></a>Valori TimeSpan  
 È possibile usare <xref:System.TimeSpan> i valori per specificare un <xref:System.Windows.Media.Animation.KeyTime>. Il valore deve essere maggiore o uguale a 0 e minore o uguale alla durata dell'animazione. L'esempio seguente illustra un'animazione con una durata di 10 secondi e quattro fotogrammi chiave le cui chiavi temporali sono specificate come valori.  
  
-   Il primo fotogramma chiave aggiunge un'animazione dal valore di base a 100 per i primi 3 secondi e viene terminato alle 0:0:03.  
  
-   Il secondo fotogramma chiave aggiunge un'animazione da 100 a 200. Viene avviato dopo la fine del primo fotogramma chiave (3 secondi), viene riprodotto per 5 secondi e viene terminato alle 0:0:8.  
  
-   Il terzo fotogramma chiave aggiunge un'animazione da 200 a 500. Viene avviato dopo la fine del secondo fotogramma chiave (8 secondi), viene riprodotto per 1 secondo e viene terminato alle 0:0:9.  
  
-   Il quarto fotogramma chiave aggiunge un'animazione da 500 a 600. Viene avviato dopo la fine del terzo fotogramma chiave (9 secondi), viene riprodotto per 1 secondo e viene terminato alle 0:0:10.  
  
 [!code-xaml[keyframes_ovw_snippet#TimeSpanKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#timespankeytimeexample)]  
  
### <a name="percentage-values"></a>Valori percentuali  
 Un valore percentuale specifica che il fotogramma chiave termina in una determinata percentuale dell'animazione <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] specificare la percentuale come numero seguito dal simbolo `%`. Nel codice, si utilizza il <xref:System.Windows.Media.Animation.KeyTime.FromPercent%2A> metodo e passare un <xref:System.Double> che indica la percentuale. Il valore deve essere maggiore o uguale a 0 e minore o uguale a 100%. L'esempio seguente illustra un'animazione con una durata di 10 secondi e quattro fotogrammi chiave le cui chiavi temporali sono specificate come percentuali.  
  
-   Il primo fotogramma chiave aggiunge un'animazione dal valore di base a 100 per i primi 3 secondi e viene terminato alle 0:0:3.  
  
-   Il secondo fotogramma chiave aggiunge un'animazione da 100 a 200. Viene avviato dopo la fine del primo fotogramma chiave (3 secondi), viene riprodotto per 5 secondi e viene terminato alle 0:0:8 (0,8 * 10 = 8).  
  
-   Il terzo fotogramma chiave aggiunge un'animazione da 200 a 500. Viene avviato dopo la fine del secondo fotogramma chiave (8 secondi), viene riprodotto per 1 secondo e viene terminato alle 0:0:9 (0,9 * 10 = 9).  
  
-   Il quarto fotogramma chiave aggiunge un'animazione da 500 a 600. Viene avviato dopo la fine del terzo fotogramma chiave (9 secondi), viene riprodotto per 1 secondo e viene terminato alle 0:0:10 (1 * 10 = 10).  
  
 [!code-xaml[keyframes_ovw_snippet#PercentageKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#percentagekeytimeexample)]  
  
### <a name="special-value-uniform"></a>Valore speciale, Uniform  
 Usare <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> quando si desidera ogni fotogramma chiave impieghi la stessa quantità di tempo.  
  
 Oggetto <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> chiave temporale divide equamente il tempo disponibile per il numero di fotogrammi chiave per determinare l'ora di fine di ogni fotogramma chiave. Nell'esempio seguente illustra un'animazione con una durata di 10 secondi e quattro fotogrammi chiave le cui chiavi temporali sono specificati come <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>.  
  
-   Il primo fotogramma chiave aggiunge un'animazione dal valore di base a 100 per i primi 2,5 secondi e viene terminato alle 0:0:2.5.  
  
-   Il secondo fotogramma chiave aggiunge un'animazione da 100 a 200. Viene avviato dopo la fine del primo fotogramma chiave (2,5 secondi), viene riprodotto per circa 2,5 secondi e viene terminato alle 0:0:5.  
  
-   Il terzo fotogramma chiave aggiunge un'animazione da 200 a 500. Viene avviato dopo la fine del secondo fotogramma chiave (5 secondi), viene riprodotto per 2,5 secondi e viene terminato alle 0:0:7.5.  
  
-   Il quarto fotogramma chiave aggiunge un'animazione da 500 a 600. Viene avviato dopo la fine del secondo fotogramma chiave (7,5 secondi), viene riprodotto per 2,5 secondi e viene terminato alle 0:0:1.  
  
 [!code-xaml[keyframes_ovw_snippet#UniformKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#uniformkeytimeexample)]  
  
### <a name="special-value-paced"></a>Valore speciale, Paced  
 Usare <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> quando si desidera aggiungere un'animazione a una velocità costante.  
  
 Oggetto <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> chiave temporale assegna il tempo disponibile in base alla lunghezza di ogni fotogramma chiave per determinare la durata di ogni fotogramma.  In questo modo la velocità dell'animazione rimarrà costante.  Nell'esempio seguente illustra un'animazione con una durata di 10 secondi e tre fotogrammi chiave le cui chiavi temporali sono specificati come <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 [!code-xaml[keyframes_ovw_snippet#PacedKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#pacedkeytimeexample)]  
  
 Si noti che, se chiave ora l'ultimo fotogramma chiave <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> o <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>, la chiave temporale risolta imposterà fino al 100%. Se il primo fotogramma chiave di un'animazione a più fotogrammi presenta il valore Paced, la relativa chiave temporale risolta sarà impostata su 0. (Se la raccolta di fotogrammi chiave contiene solo un singolo fotogramma chiave con valore Paced, la relativa chiave temporale risolta sarà impostata su 100%).  
  
 Fotogrammi chiave diversi in una singola animazione con fotogrammi chiave possono usare tipi diversi di chiavi temporali.  
  
<a name="combiningkeytimes"></a>   
## <a name="combining-key-times-out-of-order-key-frames"></a>Uso combinato di chiavi temporali, fotogrammi chiave non ordinati  
 È possibile usare i fotogrammi chiave con diversi <xref:System.Windows.Media.Animation.KeyTime> i tipi valore in stessa animazione. Non è necessario ma è consigliabile aggiungere i fotogrammi chiave nell'ordine in cui devono essere riprodotti. L'animazione e il sistema di temporizzazione sono in grado di risolvere i fotogrammi chiave nell'ordine errato. I fotogrammi chiave con chiavi temporali non valide vengono ignorati.  
  
 L'elenco seguente descrive la procedura con cui vengono risolte le chiavi temporali per i fotogrammi chiave di un'animazione con fotogrammi chiave.  
  
1.  Risolvere <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> valori.  
  
2.  Determinare il *tempo di interpolazione totale* dell'animazione, il tempo totale che impiega l'animazione con fotogrammi chiave per completare un'iterazione in avanti.  
  
    1.  Se l'animazione <xref:System.Windows.Media.Animation.Timeline.Duration%2A> non è <xref:System.Windows.Duration.Automatic%2A> oppure <xref:System.Windows.Duration.Forever%2A>, il tempo di interpolazione totale è il valore dell'animazione <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà.  
  
    2.  In caso contrario, il tempo di interpolazione totale è il più grande <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> specificato tra i relativi fotogrammi chiave, se presente.  
  
    3.  In caso contrario, il tempo di interpolazione totale è pari a 1 secondo.  
  
3.  Usare il valore di tempo di interpolazione totale per risolvere <xref:System.Windows.Media.Animation.KeyTimeType.Percent> <xref:System.Windows.Media.Animation.KeyTime> valori.  
  
4.  Risolvere l'ultimo fotogramma chiave, se non è stato risolto nei passaggi precedenti. Se il <xref:System.Windows.Media.Animation.KeyTime> dell'ultimo fotogramma chiave viene <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, il relativo tempo risolto sarà uguale al tempo di interpolazione totale.  
  
     Se il <xref:System.Windows.Media.Animation.KeyTime> del primo fotogramma chiave è <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> e questa animazione ha più di un fotogramma chiave, risolvere i relativi <xref:System.Windows.Media.Animation.KeyTime> valore a zero; se è presente un solo fotogramma chiave e il relativo <xref:System.Windows.Media.Animation.KeyTime> valore è <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, viene risolto al totale tempo di interpolazione, come descritto nel passaggio precedente.  
  
5.  Risolvere rimanente <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> valori: ognuno è assegnata una porzione uguale del tempo disponibile.  Durante questo processo, sono state risolte <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> i valori vengono temporaneamente considerati <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> valori e get ora di risoluzione di una password temporanea.  
  
6.  Risolvere i <xref:System.Windows.Media.Animation.KeyTime> i valori dei fotogrammi chiave con chiavi temporali non specificate usando i fotogrammi chiave dichiarati più adiacenti che hanno risolto <xref:System.Windows.Media.Animation.KeyTime> valori.  
  
7.  Risolvere rimanente <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> valori. <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> usare il <xref:System.Windows.Media.Animation.KeyTime> adiacenti ai valori della chiave fotogrammi per determinare i relativi tempi risolti.  L'obiettivo è quello di garantire che la velocità dell'animazione sia costante in prossimità del tempo risolto del fotogramma chiave.  
  
8.  Ordinare i fotogrammi chiave in base al tempo risolto (chiave primaria) e all'ordine di dichiarazione (chiave secondaria), ad esempio, usare un ordinamento stabile basato su risolti del fotogramma chiave <xref:System.Windows.Media.Animation.KeyTime> valori.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.Animation.KeyTime>
- <xref:System.Windows.Media.Animation.KeySpline>
- <xref:System.Windows.Media.Animation.Timeline>
- [Esempio di animazione Key Spline](https://go.microsoft.com/fwlink/?LinkID=160011)
- [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
- [Procedure relative ai fotogrammi chiave](key-frame-animation-how-to-topics.md)
- [Cenni preliminari sui comportamenti temporali](timing-behaviors-overview.md)
