---
title: 'Procedura: controllare uno storyboard in seguito al relativo avvio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 051ac6fea73b207fb5ef4d6293c5e996552f1281
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Procedura: controllare uno storyboard in seguito al relativo avvio
In questo esempio viene illustrato come utilizzare codice per controllare un <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio. Per controllare uno storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilizzare <xref:System.Windows.Trigger> e <xref:System.Windows.TriggerAction> oggetti; ad esempio, vedere [utilizzare trigger di evento per controllare un Storyboard dopo l'avvio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Per avviare uno storyboard, utilizzare il relativo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo, che distribuisce le animazioni dello storyboard per la proprietà animate e avvia lo storyboard.  
  
 Per rendere controllabile uno storyboard, si utilizza il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> (metodo) e specificare **true** come secondo parametro. È quindi possibile utilizzare metodi interattivi dello storyboard per sospendere, riprendere, cercare, arrestare, accelerare o rallentare lo storyboard o spostarlo al periodo di riempimento. Di seguito è riportato un elenco di metodi interattivi dello storyboard:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Sospende lo storyboard.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Consente di riprendere uno storyboard sospeso.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Imposta la velocità interattiva dello storyboard.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Cerca lo storyboard nel percorso specificato.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Cerca lo storyboard nel percorso specificato. A differenza di <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> (metodo), questa operazione viene elaborata prima del tick successivo.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Sposta lo storyboard al periodo di riempimento, se presente.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Interrompe lo storyboard.  
  
 Nell'esempio seguente, vengono utilizzati vari metodi di storyboard per controllare in modo interattivo uno storyboard.  
  
 **Nota:** per vedere un esempio di controllo di uno storyboard tramite trigger con [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], vedere [utilizzare i trigger di evento per controllare un Storyboard dopo l'avvio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## <a name="example"></a>Esempio  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a>Vedere anche  
 [Usare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
