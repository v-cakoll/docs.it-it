---
title: 'Procedura: utilizzare i trigger di evento per controllare uno storyboard dopo il relativo avvio'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186708"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Procedura: utilizzare i trigger di evento per controllare uno storyboard dopo il relativo avvio

In questo esempio viene <xref:System.Windows.Media.Animation.Storyboard> illustrato come controllare un dopo l'avvio. Per iniziare <xref:System.Windows.Media.Animation.Storyboard> un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]utilizzando <xref:System.Windows.Media.Animation.BeginStoryboard>, utilizzare , che distribuisce le animazioni agli oggetti e alle proprietà che animano e quindi avvia lo storyboard. Se si <xref:System.Windows.Media.Animation.BeginStoryboard> assegna un nome <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> specificandone la proprietà, la si rende uno storyboard controllabile. È quindi possibile controllare in modo interattivo lo storyboard dopo l'avvio.

Usare le seguenti azioni <xref:System.Windows.EventTrigger> dello storyboard insieme agli oggetti per controllare uno storyboard.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: mette in pausa lo storyboard.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: riprende uno storyboard in pausa.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: modifica la velocità dello storyboard.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: sposta uno storyboard alla fine del periodo di riempimento, se ne ha uno.

- <xref:System.Windows.Media.Animation.StopStoryboard>: interrompe lo storyboard.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: rimuove lo storyboard, liberando risorse.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono utilizzate azioni di storyboard controllabili per controllare in modo interattivo uno storyboard.

> [!NOTE]
> Per visualizzare un esempio di controllo di uno storyboard tramite codice, vedere [Controllo di uno storyboard dopo l'avvio dell'utilizzo](how-to-control-a-storyboard-after-it-starts.md)dei relativi metodi interattivi .

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

Per ulteriori esempi, vedere raccolta di esempi di [animazione](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [Controllare uno storyboard in seguito al relativo avvio usando i metodi interattivi](how-to-control-a-storyboard-after-it-starts.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sugli storyboard](storyboards-overview.md)
