---
title: Funzioni di interpolazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
ms.openlocfilehash: 3ce7c1824dc53c154ba1091ea62c1b8950b757c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="easing-functions"></a>Funzioni di interpolazione
Le funzioni di interpolazione consentono di applicare formule matematiche personalizzate alle animazioni. Si può ad esempio fare in modo che un oggetto rimbalzi in modo realistico o si comporti come se fosse su una molla. È possibile usare animazioni con fotogrammi chiave o anche animazioni From/To/By per simulare questi effetti, ma l'operazione richiederebbe una quantità significativa di lavoro e l'animazione risulterebbe meno accurata rispetto all'uso di una formula matematica.  
  
 Oltre a creare la propria funzione di interpolazione personalizzata tramite l'eredità da <xref:System.Windows.Media.Animation.EasingFunctionBase>, è possibile utilizzare una delle numerose funzioni di interpolazione fornite dal runtime per creare effetti comuni.  
  
-   <xref:System.Windows.Media.Animation.BackEase>: Ritira il movimento di un'animazione leggermente prima di iniziare un'animazione nel percorso indicato.  
  
-   <xref:System.Windows.Media.Animation.BounceEase>: Crea un effetto di rimbalzo.  
  
-   <xref:System.Windows.Media.Animation.CircleEase>: Consente di creare un'animazione che accelera e/o decelera, usando una funzione circolare.  
  
-   <xref:System.Windows.Media.Animation.CubicEase>: Crea un'animazione che accelera e/o decelera, usando la formula *f*(*t*) = *t*<sup>3</sup>.  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>: Consente di creare un'animazione che è simile a una molla oscilla avanti e indietro fino ad arrestarsi.  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>: Consente di creare un'animazione che accelera e/o decelera, usando una formula esponenziale.  
  
-   <xref:System.Windows.Media.Animation.PowerEase>: Crea un'animazione che accelera e/o decelera, usando la formula *f*(*t*) = *t*<sup>p</sup> dove p è uguale al <xref:System.Windows.Media.Animation.PowerEase.Power%2A>proprietà.  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>: Crea un'animazione che accelera e/o decelera, usando la formula *f*(*t*) = *t*<sup>2</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>: Crea un'animazione che accelera e/o decelera, usando la formula *f*(*t*) = *t*<sup>4</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>: Creare un'animazione che accelera e/o decelera, usando la formula *f*(*t*) = *t*<sup>5</sup>.  
  
-   <xref:System.Windows.Media.Animation.SineEase>: Consente di creare un'animazione che accelera e/o decelera, usando una formula seno.  
  
 È possibile esplorare il comportamento di queste funzioni di interpolazione con l'esempio seguente.  
  
 [Eseguire l'esempio](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 Per applicare una funzione di interpolazione a un'animazione, utilizzare il `EasingFunction` proprietà dell'animazione specificare la funzione di interpolazione per applicare l'animazione. Nell'esempio seguente viene applicato un <xref:System.Windows.Media.Animation.BounceEase> interpolazione funzione da un <xref:System.Windows.Media.Animation.DoubleAnimation> per creare un effetto di rimbalzo.  
  
 [Eseguire l'esempio](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 Nell'esempio precedente la funzione di interpolazione è applicata a un'animazione From/To/By. Queste funzioni di interpolazione possono essere applicate anche ad animazioni con fotogrammi chiave. L'esempio seguente illustra come usare i fotogrammi chiave con funzioni di interpolazione a essi associate per creare l'animazione di un rettangolo che si contrae verso l'alto, rallenta, poi si espande verso il basso (come se cadesse) e rimbalza fino ad arrestarsi.  
  
 [Eseguire l'esempio](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 È possibile utilizzare il <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> proprietà per modificare la funzione di interpolazione comportamento, vale a dire, modificare la modalità di interpolazione l'animazione. Esistono tre possibili valori è possibile fornire per <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolazione segue la formula matematica associata alla funzione di interpolazione.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolazione segue interpolazione al 100% meno l'output della formula associata alla funzione di interpolazione.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Usa interpolazione <xref:System.Windows.Media.Animation.EasingMode.EaseIn> per la prima metà dell'animazione e <xref:System.Windows.Media.Animation.EasingMode.EaseOut> per la seconda metà.  
  
 Le immagini seguenti vengono illustrati i diversi valori di <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> in *f*(*x*) rappresenta l'avanzamento dell'animazione e *t* rappresenta il tempo.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![Grafici di BackEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![Grafici di BounceEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![Grafici di CircleEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![Grafici di CubicEase EasingMode.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase con grafici di EasingMode diversi.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![Grafici ExponentialEase di EasingMode diversi.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase con grafici di EasingMode diversi.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![QuadraticEase con grafici di EasingMode diversi](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase con grafici di EasingMode diversi.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase con grafici di EasingMode diversi.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase per valori di EasingMode diversi](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  È possibile utilizzare <xref:System.Windows.Media.Animation.PowerEase> per creare lo stesso comportamento di <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, e <xref:System.Windows.Media.Animation.QuinticEase> utilizzando il <xref:System.Windows.Media.Animation.PowerEase.Power%2A> proprietà. Ad esempio, se si desidera utilizzare <xref:System.Windows.Media.Animation.PowerEase> da sostituire per <xref:System.Windows.Media.Animation.CubicEase>, specificare un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valore 3.  
  
 Oltre a utilizzare le funzioni di interpolazione incluse in fase di esecuzione, è possibile creare funzioni di interpolazione personalizzate ereditando dalla <xref:System.Windows.Media.Animation.EasingFunctionBase>. L'esempio seguente illustra come creare una semplice funzione di interpolazione personalizzata. È possibile aggiungere la propria logica matematica per determinare la funzione di interpolazione comportamento eseguendo l'override di <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> metodo.  
  
 [Eseguire l'esempio](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
