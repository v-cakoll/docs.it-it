---
title: 'Procedura: utilizzare i trigger di evento per controllare uno storyboard dopo il relativo avvio'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: c864668026c4f8bb58a4d6c4c36f96fb07445a9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561294"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Procedura: utilizzare i trigger di evento per controllare uno storyboard dopo il relativo avvio
In questo esempio viene illustrato come controllare un <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio. Per avviare un <xref:System.Windows.Media.Animation.Storyboard> utilizzando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilizzare <xref:System.Windows.Media.Animation.BeginStoryboard>, che distribuisce le animazioni agli oggetti e proprietà animate e quindi avvia lo storyboard. Se si fornisce <xref:System.Windows.Media.Animation.BeginStoryboard> un nome, specificando il relativo <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> proprietà consentono di uno storyboard controllabile. È quindi possibile controllare in modo interattivo lo storyboard dopo l'avvio.  
  
 Utilizzare le seguenti azioni di storyboard con <xref:System.Windows.EventTrigger> oggetti per controllare uno storyboard.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Sospende lo storyboard.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Consente di riprendere uno storyboard in pausa.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Modifica la velocità di storyboard.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Sposta uno storyboard alla fine del periodo di riempimento, se presente.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Interrompe lo storyboard.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Rimuove lo storyboard, liberando risorse.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente usa azioni di storyboard controllabili per controllare in modo interattivo uno storyboard.  
  
 **Nota:** per un esempio di controllo di uno storyboard tramite codice, vedere la sezione [metodi del controllo un Storyboard dopo che viene avviato utilizzando relativo interattivo](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Per ulteriori esempi, vedere il [raccolta](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [Controllare uno storyboard in seguito al relativo avvio usando i metodi interattivi](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
