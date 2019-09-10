---
title: "Procedura: Controllare uno storyboard dopo l'avvio"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: de30cfdb49df721cb4d6845dc67464e8a5b61f93
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855869"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Procedura: Controllare uno storyboard dopo l'avvio

Questo esempio illustra come usare il codice per controllare un <xref:System.Windows.Media.Animation.Storyboard> oggetto dopo che è stato avviato. Per controllare uno storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usare <xref:System.Windows.Trigger> gli <xref:System.Windows.TriggerAction> oggetti e. per un esempio, vedere [usare i trigger di evento per controllare uno storyboard dopo l'avvio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).

Per avviare uno storyboard, usare il relativo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo, che distribuisce le animazioni dello Storyboard alle proprietà che animano e avvia lo storyboard.

Per rendere controllabile uno storyboard, usare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo e specificare **true** come secondo parametro. È quindi possibile usare i metodi interattivi dello storyboard per sospendere, riprendere, cercare, arrestare, velocizzare o rallentare lo storyboard oppure spostarlo al periodo di riempimento. Di seguito è riportato un elenco dei metodi interattivi dello storyboard:

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Sospende lo storyboard.

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Riprende uno storyboard sospeso.

- <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Imposta la velocità interattiva dello storyboard.

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Cerca nello storyboard la posizione specificata.

- <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Cerca lo storyboard nella posizione specificata. A differenza del <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> metodo, questa operazione viene elaborata prima del ciclo successivo.

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Sposta lo storyboard al periodo di riempimento, se ne esiste uno.

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Arresta lo storyboard.

Nell'esempio seguente vengono utilizzati diversi metodi storyboard per controllare in modo interattivo uno storyboard.

> [!NOTE]
> Per vedere un esempio di controllo di uno storyboard con i [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]trigger con, vedere [usare i trigger di evento per controllare uno storyboard dopo l'avvio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).

## <a name="example"></a>Esempio

[!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
[!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]

## <a name="see-also"></a>Vedere anche

- [Usare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
