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
ms.openlocfilehash: a25bde5098af853c3906a174a189fc35f33f0525
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186491"
---
# <a name="easing-functions"></a>Funzioni di interpolazione
Le funzioni di interpolazione consentono di applicare formule matematiche personalizzate alle animazioni. Si può ad esempio fare in modo che un oggetto rimbalzi in modo realistico o si comporti come se fosse su una molla. È possibile usare animazioni con fotogrammi chiave o anche animazioni From/To/By per simulare questi effetti, ma l'operazione richiederebbe una quantità significativa di lavoro e l'animazione risulterebbe meno accurata rispetto all'uso di una formula matematica.  
  
 Oltre a creare una funzione di andamento <xref:System.Windows.Media.Animation.EasingFunctionBase>personalizzata ereditando da , è possibile utilizzare una delle diverse funzioni di andamento fornite dal runtime per creare effetti comuni.  
  
- <xref:System.Windows.Media.Animation.BackEase>: ritrae leggermente il movimento di un'animazione prima che inizi ad animarsi nel tracciato indicato.  
  
- <xref:System.Windows.Media.Animation.BounceEase>: crea un effetto di rimbalzo.  
  
- <xref:System.Windows.Media.Animation.CircleEase>: crea un'animazione che accelera e/o decelera utilizzando una funzione circolare.  
  
- <xref:System.Windows.Media.Animation.CubicEase>: crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) : *t*<sup>3</sup>.  
  
- <xref:System.Windows.Media.Animation.ElasticEase>: crea un'animazione che assomiglia a una molla che oscilla avanti e indietro fino a quando non si ferma.  
  
- <xref:System.Windows.Media.Animation.ExponentialEase>: crea un'animazione che accelera e/o decelera utilizzando una formula esponenziale.  
  
- <xref:System.Windows.Media.Animation.PowerEase>: crea un'animazione che accelera e/o decelera utilizzando la formula <xref:System.Windows.Media.Animation.PowerEase.Power%2A> *f*(*t*) - *t*<sup>p</sup> dove p è uguale alla proprietà.  
  
- <xref:System.Windows.Media.Animation.QuadraticEase>: crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) : *t*<sup>2</sup>.  
  
- <xref:System.Windows.Media.Animation.QuarticEase>: crea un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) : *t*<sup>4</sup>.  
  
- <xref:System.Windows.Media.Animation.QuinticEase>: consente di creare un'animazione che accelera e/o decelera utilizzando la formula *f*(*t*) : *t*<sup>5</sup>.  
  
- <xref:System.Windows.Media.Animation.SineEase>: crea un'animazione che accelera e/o decelera utilizzando una formula sinusoidale.  
  
 Per applicare una funzione di andamento `EasingFunction` a un'animazione, utilizzare la proprietà dell'animazione specificare la funzione di andamento da applicare all'animazione. Nell'esempio seguente <xref:System.Windows.Media.Animation.BounceEase> viene applicata <xref:System.Windows.Media.Animation.DoubleAnimation> una funzione di andamento a un oggetto per creare un effetto di rimbalzo.  
  
 [!code-xaml[BounceEase_snippet#BounceEase](~/samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 Nell'esempio precedente la funzione di interpolazione è applicata a un'animazione From/To/By. Queste funzioni di interpolazione possono essere applicate anche ad animazioni con fotogrammi chiave. L'esempio seguente illustra come usare i fotogrammi chiave con funzioni di interpolazione a essi associate per creare l'animazione di un rettangolo che si contrae verso l'alto, rallenta, poi si espande verso il basso (come se cadesse) e rimbalza fino ad arrestarsi.  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](~/samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 È possibile <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> utilizzare la proprietà per modificare il modo in cui si comporta la funzione di interpolazione, ovvero modificare la modalità di interpolazione dell'animazione. Ci sono tre possibili valori <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>che puoi dare per:  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseIn>: l'interpolazione segue la formula matematica associata alla funzione di interpolazione.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseOut>: l'interpolazione segue l'interpolazione al 100% meno l'output della formula associata alla funzione di interpolazione.  
  
- <xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: l'interpolazione viene utilizzata <xref:System.Windows.Media.Animation.EasingMode.EaseIn> per <xref:System.Windows.Media.Animation.EasingMode.EaseOut> la prima metà dell'animazione e per la seconda metà.  
  
 I grafici seguenti illustrano <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> i diversi valori di dove *f*(*x*) rappresenta lo stato di avanzamento dell'animazione e *t* rappresenta il tempo.  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 ![Grafici di EasingMode per BackEase.](./media/backease-graph.png "BackEase_Graph")  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 ![Grafici di EasingMode per BounceEase.](./media/bounceease-graph.png "BounceEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 ![Grafici di EasingMode per CircleEase.](./media/circleease-graph.png "CircleEase_Graph")  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 ![Grafici di EasingMode per CubicEase.](./media/cubicease-graph.png "CubicEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 ![ElasticEase con grafici di EasingMode diversi.](./media/elasticease-graph.png "ElasticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 ![Grafici di ExponentialEase con EasingMode diversi.](./media/exponentialease-graph.png "ExponentialEase_Graph")  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 ![QuarticEase con grafici di EasingMode diversi.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 ![QuadraticEase con grafici di diversi asinisti](./media/quadraticease-graph.png "QuadraticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 ![QuarticEase con grafici di EasingMode diversi.](./media/quarticease-graph.png "QuarticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 ![QuinticEase con grafici di EasingMode diversi.](./media/quinticease-graph.png "QuinticEase_Graph")  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 ![SineEase per valori EasingMode diversi](./media/sineease-graph.png "SineEase_Graph")  
  
> [!NOTE]
> È possibile <xref:System.Windows.Media.Animation.PowerEase> utilizzare per creare <xref:System.Windows.Media.Animation.CubicEase> <xref:System.Windows.Media.Animation.QuadraticEase>lo <xref:System.Windows.Media.Animation.QuarticEase>stesso <xref:System.Windows.Media.Animation.QuinticEase> comportamento <xref:System.Windows.Media.Animation.PowerEase.Power%2A> di , , e utilizzando la proprietà . Ad esempio, se si <xref:System.Windows.Media.Animation.PowerEase> desidera <xref:System.Windows.Media.Animation.CubicEase>utilizzare per <xref:System.Windows.Media.Animation.PowerEase.Power%2A> sostituire , specificare un valore pari a 3.  
  
 Oltre a utilizzare le funzioni di andamento incluse in fase di esecuzione, è possibile <xref:System.Windows.Media.Animation.EasingFunctionBase>creare funzioni di andamento personalizzate ereditando da . L'esempio seguente illustra come creare una semplice funzione di interpolazione personalizzata. È possibile aggiungere la propria logica matematica per il modo in <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> cui si comporta la funzione di andamento eseguendo l'override del metodo.
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](~/samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
