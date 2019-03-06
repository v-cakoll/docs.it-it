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
ms.openlocfilehash: 456308e37bddc1df86b49085139a3810c4959a58
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354505"
---
# <a name="easing-functions"></a>Funzioni di interpolazione
Le funzioni di interpolazione consentono di applicare formule matematiche personalizzate alle animazioni. Si può ad esempio fare in modo che un oggetto rimbalzi in modo realistico o si comporti come se fosse su una molla. È possibile usare animazioni con fotogrammi chiave o anche animazioni From/To/By per simulare questi effetti, ma l'operazione richiederebbe una quantità significativa di lavoro e l'animazione risulterebbe meno accurata rispetto all'uso di una formula matematica.  
  
 Oltre a creare una funzione di interpolazione personalizzata ereditando da <xref:System.Windows.Media.Animation.EasingFunctionBase>, è possibile usare una delle numerose funzioni di interpolazione fornite dal runtime per creare effetti di uso comune.  
  
-   <xref:System.Windows.Media.Animation.BackEase>: Ritrae leggermente il movimento di un'animazione prima che inizi ad animarsi nel tracciato indicato.  
  
-   <xref:System.Windows.Media.Animation.BounceEase>: Crea un effetto di rimbalzo.  
  
-   <xref:System.Windows.Media.Animation.CircleEase>: Crea un'animazione che accelera e/o rallenta usando una funzione circolare.  
  
-   <xref:System.Windows.Media.Animation.CubicEase>: Crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) = *t*<sup>3</sup>.  
  
-   <xref:System.Windows.Media.Animation.ElasticEase>: Crea un'animazione simile a una molla che oscilla avanti e indietro fino ad arrestarsi.  
  
-   <xref:System.Windows.Media.Animation.ExponentialEase>: Crea un'animazione che accelera e/o rallenta usando una formula esponenziale.  
  
-   <xref:System.Windows.Media.Animation.PowerEase>: Crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) = *t*<sup>p</sup> dove p è uguale al <xref:System.Windows.Media.Animation.PowerEase.Power%2A>proprietà.  
  
-   <xref:System.Windows.Media.Animation.QuadraticEase>: Crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) = *t*<sup>2</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuarticEase>: Crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) = *t*<sup>4</sup>.  
  
-   <xref:System.Windows.Media.Animation.QuinticEase>: Creare un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) = *t*<sup>5</sup>.  
  
-   <xref:System.Windows.Media.Animation.SineEase>: Crea un'animazione che accelera e/o decelera usando una formula sinusoidale.  
  
 Per applicare una funzione di interpolazione a un'animazione, usare il `EasingFunction` proprietà dell'animazione specificare la funzione di interpolazione da applicare all'animazione. L'esempio seguente applica un' <xref:System.Windows.Media.Animation.BounceEase> funzione di interpolazione un <xref:System.Windows.Media.Animation.DoubleAnimation> per creare un effetto di rimbalzo.  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 Nell'esempio precedente la funzione di interpolazione è applicata a un'animazione From/To/By. Queste funzioni di interpolazione possono essere applicate anche ad animazioni con fotogrammi chiave. L'esempio seguente illustra come usare i fotogrammi chiave con funzioni di interpolazione a essi associate per creare l'animazione di un rettangolo che si contrae verso l'alto, rallenta, poi si espande verso il basso (come se cadesse) e rimbalza fino ad arrestarsi.  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 È possibile usare il <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> proprietà per modificare l'interpolazione comportamento della funzione, vale a dire, modificare la modalità di interpolazione dell'animazione. Esistono tre possibili valori è possibile concedere per <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: L'interpolazione segue la formula matematica associata alla funzione di interpolazione.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: L'interpolazione segue l'interpolazione al 100% meno l'output della formula associata alla funzione di interpolazione.  
  
-   <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Usa l'interpolazione <xref:System.Windows.Media.Animation.EasingMode.EaseIn> nella prima metà dell'animazione e <xref:System.Windows.Media.Animation.EasingMode.EaseOut> per la seconda metà.  
  
 I grafici seguenti illustrano i diversi valori della <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> in cui *f*(*x*) rappresenta l'avanzamento dell'animazione e *t* rappresenta l'ora.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![Grafici di BackEase EasingMode.](./media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![Grafici di BounceEase EasingMode.](./media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![Grafici di CircleEase EasingMode.](./media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![Grafici di CubicEase EasingMode.](./media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase con grafici di EasingMode diversi.](./media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![Grafici ExponentialEase di EasingMode diversi.](./media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase con grafici di EasingMode diversi.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![QuadraticEase con grafici di EasingMode diversi](./media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase con grafici di EasingMode diversi.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase con grafici di EasingMode diversi.](./media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase per valori di EasingMode diversi](./media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
>  È possibile usare <xref:System.Windows.Media.Animation.PowerEase> per creare lo stesso comportamento <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, e <xref:System.Windows.Media.Animation.QuinticEase> usando la <xref:System.Windows.Media.Animation.PowerEase.Power%2A> proprietà. Ad esempio, se si desidera utilizzare <xref:System.Windows.Media.Animation.PowerEase> per sostituire <xref:System.Windows.Media.Animation.CubicEase>, specificare un <xref:System.Windows.Media.Animation.PowerEase.Power%2A> valore 3.  
  
 Oltre a usare le funzioni di interpolazione incluse in fase di esecuzione, è possibile creare funzioni di interpolazione personalizzate ereditando da <xref:System.Windows.Media.Animation.EasingFunctionBase>. L'esempio seguente illustra come creare una semplice funzione di interpolazione personalizzata. È possibile aggiungere logica matematica personalizzata per determinare la funzione di interpolazione comportamento eseguendo l'override di <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> (metodo).   
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
