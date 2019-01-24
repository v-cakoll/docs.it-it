---
title: 'Procedura: Utilizzare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: e4cfaf2352c3cca2b67a8e6a5d4c933399583e5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663648"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Procedura: Utilizzare i trigger di eventi per controllare uno storyboard in seguito al relativo avvio
In questo esempio viene illustrato come controllare un <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio. Per avviare un <xref:System.Windows.Media.Animation.Storyboard> usando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usare <xref:System.Windows.Media.Animation.BeginStoryboard>, che distribuisce le animazioni agli oggetti e proprietà animate e quindi avvia lo storyboard. Qualora il Licenziatario fornisca <xref:System.Windows.Media.Animation.BeginStoryboard> specificando un nome relativo <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> proprietà, si renderla uno storyboard controllabile. È quindi possibile controllare in modo interattivo lo storyboard dopo l'avvio.  
  
 Usare le seguenti azioni di storyboard con <xref:System.Windows.EventTrigger> oggetti per controllare uno storyboard.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Sospende lo storyboard.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Riprende uno storyboard sospeso.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Modifica la velocità dello storyboard.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Sposta uno storyboard alla fine del periodo di riempimento, se presente.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Interrompe lo storyboard.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Rimuove lo storyboard, liberando così risorse.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente usa azioni dello storyboard controllabili per controllare uno storyboard in modo interattivo.  
  
 **Nota:** Per un esempio di controllare uno storyboard tramite codice, vedere [controllare un Storyboard dopo che viene avviata usando relativi metodi interattivi](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Per altri esempi, vedere la [raccolta di esempi di animazione](https://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [Controllare uno storyboard in seguito al relativo avvio usando i metodi interattivi](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)
- [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
