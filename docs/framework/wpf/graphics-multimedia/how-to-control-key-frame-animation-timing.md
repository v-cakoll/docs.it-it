---
title: 'Procedura: Controllare la durata delle animazioni con fotogrammi chiave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], timing
- timing key-frame animation
ms.assetid: b059216f-7d4b-4ca8-a019-bc287ee7bf16
ms.openlocfilehash: d0ea56b24f8fffeb688d297a675681bce3fdc4e0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489878"
---
# <a name="how-to-control-key-frame-animation-timing"></a>Procedura: Controllare la durata delle animazioni con fotogrammi chiave

In questo esempio viene illustrato come controllare l'intervallo di fotogrammi chiave all'interno di un'animazione con fotogrammi chiave. Analogamente alle altre animazioni, animazioni con fotogrammi chiave hanno un <xref:System.Windows.Media.Animation.Timeline.Duration%2A> proprietà. Oltre a specificare la durata di un'animazione, è necessario specificare quale parte di tale durata viene assegnata a ciascuno dei relativi fotogrammi chiave. Per assegnare l'ora, specificare un <xref:System.Windows.Media.Animation.KeyTime> per ogni fotogramma chiave l'animazione.

Il <xref:System.Windows.Media.Animation.KeyTime> per ogni fotogramma chiave specifica quando termina un fotogramma chiave (non specifica la durata di riproduzione di un fotogramma chiave). È possibile specificare una <xref:System.Windows.Media.Animation.KeyTime> come un <xref:System.TimeSpan> valore, come una percentuale o il <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> o <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> valore speciale.

## <a name="example"></a>Esempio

L'esempio seguente usa un <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> per animare un rettangolo sullo schermo. Le chiavi temporali i fotogrammi chiave sono impostate con <xref:System.TimeSpan> valori.

[!code-csharp[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimestimespanexample)]
[!code-vb[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimestimespanexample)]
[!code-xaml[keyframes_snip#KeyTimesTimeSpanExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimestimespanexample)]

La figura seguente illustra quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori di chiave vengono raggiunti a 3, 4 e 10 secondi](./media/graphicsmm-keyframe-keytime1-timespan.png "graphicsmm_keyframe_keytime1_timespan")

L'esempio seguente illustra un'animazione che è identica, ad eccezione del fatto che le chiavi temporali i fotogrammi chiave sono impostate con i valori in percentuale.

[!code-csharp[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespercentageexample)]
[!code-vb[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespercentageexample)]
[!code-xaml[keyframes_snip#KeyTimesPercentageExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespercentageexample)]

La figura seguente illustra quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori di chiave vengono raggiunti a 3, 4 e 10 secondi](./media/graphicsmm-keyframe-keytime2-percentage.png "graphicsmm_keyframe_keytime2_percentage")

L'esempio seguente usa <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> ora i valori di chiave.

[!code-csharp[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimesuniformexample)]
[!code-vb[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimesuniformexample)]
[!code-xaml[keyframes_snip#KeyTimesUniformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimesuniformexample)]

La figura seguente illustra quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori di chiave vengono raggiunti 3.3,6.6 e 9,9 secondi](./media/graphicsmm-keyframe-keytime3-uniform.png "graphicsmm_keyframe_keytime3_uniform")

L'esempio finale Usa <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> ora i valori di chiave.

[!code-csharp[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/KeyTimesExample.cs#keytimespacedexample)]
[!code-vb[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/keytimesexample.vb#keytimespacedexample)]
[!code-xaml[keyframes_snip#KeyTimesPacedExample](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/KeyTimesExample.xaml#keytimespacedexample)]

La figura seguente illustra quando viene raggiunto il valore di ogni fotogramma chiave.

![I valori di chiave vengono raggiunti a 0, 5 e 10 secondi](./media/graphicsmm-keyframe-keytime4-paced.png "graphicsmm_keyframe_keytime4_paced")

Per semplicità, le versioni di codice di questo esempio Usa le animazioni locali, non gli storyboard, perché si applichino solo una singola animazione a una singola proprietà, ma gli esempi possono essere modificati per usare invece gli storyboard. Per un esempio che illustra come dichiarare uno storyboard nel codice, vedere [animare una proprietà utilizzando uno Storyboard](how-to-animate-a-property-by-using-a-storyboard.md).

Per l'esempio completo, vedere [Esempio di animazione con fotogrammi chiave](https://go.microsoft.com/fwlink/?LinkID=160012). Per altre informazioni sulle animazioni con fotogrammi chiave, vedere la [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md).

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle animazioni con fotogrammi chiave](key-frame-animations-overview.md)
- [Cenni preliminari sull'animazione](animation-overview.md)
- [Procedure relative alle proprietà](animation-and-timing-how-to-topics.md)
