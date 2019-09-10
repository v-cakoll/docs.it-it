---
title: 'Procedura: Usare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 32591edd065a8122b84ff14102f672ccf6001d67
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855857"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Procedura: Usare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio

Questo esempio Mostra come controllare un oggetto <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio. Per avviare un <xref:System.Windows.Media.Animation.Storyboard> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]utilizzando, utilizzare <xref:System.Windows.Media.Animation.BeginStoryboard>, che distribuisce le animazioni agli oggetti e alle proprietà a cui viene aggiunta un'animazione, quindi avvia lo storyboard. Se si assegna <xref:System.Windows.Media.Animation.BeginStoryboard> un nome specificando la <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> relativa proprietà, lo si imposta come storyboard controllabile. È quindi possibile controllare in modo interattivo lo storyboard dopo l'avvio.

Utilizzare le seguenti azioni storyboard insieme <xref:System.Windows.EventTrigger> agli oggetti per controllare uno storyboard.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Sospende lo storyboard.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Riprende uno storyboard sospeso.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Modifica la velocità dello storyboard.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Sposta uno storyboard alla fine del periodo di riempimento, se presente.

- <xref:System.Windows.Media.Animation.StopStoryboard>: Arresta lo storyboard.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Rimuove lo storyboard, liberando le risorse.

## <a name="example"></a>Esempio

Nell'esempio seguente vengono utilizzate azioni storyboard controllabili per controllare in modo interattivo uno storyboard.

> [!NOTE]
> Per vedere un esempio di controllo di uno storyboard tramite il codice, vedere [controllare uno storyboard dopo l'avvio usando i metodi interattivi](how-to-control-a-storyboard-after-it-starts.md).

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

Per altri esempi, vedere la [raccolta di esempio Animation](https://go.microsoft.com/fwlink/?LinkID=159969).

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
