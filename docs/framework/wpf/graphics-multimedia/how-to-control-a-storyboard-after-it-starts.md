---
title: "Procedura: Controllare uno Storyboard dopo l'avvio"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 98eba600f64c8b656e3597b429cc69766f398f7b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361057"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Procedura: Controllare uno Storyboard dopo l'avvio
Questo esempio illustra come usare il codice al controllo un <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio. Per controllare uno storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usare <xref:System.Windows.Trigger> e <xref:System.Windows.TriggerAction> oggetti; per un esempio, vedere [usare i trigger di evento per controllare un Storyboard dopo il relativo avvio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Per avviare uno storyboard, usare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo, che distribuisce le animazioni dello storyboard per le proprietà che vengono animati, avvia lo storyboard.  
  
 Per rendere uno storyboard controllabile, si utilizza il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo e specificare **true** come secondo parametro. È quindi possibile usare metodi interattivi dello storyboard per sospendere, riprendere, seek, arrestare, velocizzare, o rallentare lo storyboard o spostarlo al periodo di riempimento. Di seguito è riportato un elenco di metodi interattiva dello storyboard:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Sospende lo storyboard.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Riprende uno storyboard sospeso.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Imposta velocità interattiva dello storyboard.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Cerca lo storyboard nella posizione specificata.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Cerca lo storyboard nella posizione specificata. A differenza di <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> (metodo), questa operazione viene elaborata prima il tick successivo.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Sposta in avanti di uno storyboard a un periodo di riempimento, se presente.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Interrompe lo storyboard.  
  
 Nell'esempio seguente vengono utilizzati vari metodi di storyboard per controllare uno storyboard in modo interattivo.  
  
 **Nota:** Per vedere un esempio di controllo dell'utilizzo di trigger con uno storyboard [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [usare i trigger di evento per controllare un Storyboard dopo il relativo avvio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a>Vedere anche
- [Usare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
