---
title: 'Procedura: controllare la durata delle animazioni con fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: 8cfd2be0bbc526ed92a5fb1b558a5a41dc9c3113
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344729"
---
# <a name="how-to-control-key-frame-animation-timing"></a>Procedura: controllare la durata delle animazioni con fotogrammi chiave

Questo esempio mostra come controllare la temporizzazione dei fotogrammi chiave all'interno di un'animazione con fotogrammi chiave. Come altre animazioni, le <xref:System.Windows.Media.Animation.Timeline.Duration%2A> animazioni con fotogrammi chiave hanno una proprietà. Oltre a specificare la durata di un'animazione, è necessario specificare quale parte di tale durata viene assegnata a ciascuno dei relativi fotogrammi chiave. Per allocare il tempo, <xref:System.Windows.Media.Animation.KeyTime> specificare un per ogni fotogramma chiave nell'animazione.

Il <xref:System.Windows.Media.Animation.KeyTime> per ogni fotogramma chiave specifica quando termina un fotogramma chiave (non specifica la durata di riproduzione di un fotogramma chiave). È possibile <xref:System.Windows.Media.Animation.KeyTime> specificare <xref:System.TimeSpan> un valore, come percentuale o come <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> valore <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> o speciale.

## <a name="example"></a>Esempio

Nell'esempio seguente <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> viene utilizzato un per animare un rettangolo sullo schermo. I tempi chiave dei fotogrammi chiave sono impostati con <xref:System.TimeSpan> valori.

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

La figura seguente mostra quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori dei fotogrammi chiave vengono raggiunti a 3, 4 e 10 secondi](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")

L'esempio seguente mostra un'animazione identica, con la differenza che i tempi chiave dei fotogrammi chiave sono impostati con valori percentuali.

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

La figura seguente mostra quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori dei fotogrammi chiave vengono raggiunti a 3, 4 e 10 secondi](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")

Nell'esempio <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> successivo vengono utilizzati i valori di ora chiave.

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

La figura seguente mostra quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori dei fotogrammi chiave vengono raggiunti a 3,3, 6,6 e 9,9 secondi](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")

Nell'esempio <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> finale vengono utilizzati valori temporali chiave.

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

La figura seguente mostra quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori dei fotogrammi chiave vengono raggiunti a 0, 5 e 10 secondi](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")

Per semplicità, le versioni di codice di questo esempio usano animazioni locali, non storyboard, perché solo una singola animazione viene applicata a una singola proprietà, ma gli esempi possono essere modificati per usare gli storyboard. Per un esempio che illustra come dichiarare uno storyboard nel codice, vedere [Animare una proprietà tramite uno Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).

Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation). Per ulteriori informazioni sulle animazioni con fotogrammi chiave, consultate Cenni preliminari sulle animazioni con [fotogrammi chiave.](key-frame-animations-overview.md)

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative](animation-and-timing-how-to-topics.md)
