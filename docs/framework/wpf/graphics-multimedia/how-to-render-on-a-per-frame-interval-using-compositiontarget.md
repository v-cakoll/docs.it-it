---
title: 'Procedura: eseguire il rendering in un intervallo per frame tramite CompositionTarget'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CompositionTarget objects [WPF], rendering per frame
- rendering per frame using CompositionTarget objects [WPF]
ms.assetid: 701246cd-66b7-4d69-ada9-17b3b433d95d
ms.openlocfilehash: 7c080c6deca63eacdf0e1123f4ca8bbb495ed9ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561660"
---
# <a name="how-to-render-on-a-per-frame-interval-using-compositiontarget"></a>Procedura: eseguire il rendering in un intervallo per frame tramite CompositionTarget
Il motore delle animazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] offre molte funzionalità per la creazione di animazioni basate su fotogrammi. Esistono tuttavia scenari di applicazione in cui è necessario un controllo con granularità più fine sul rendering per fotogramma. Il <xref:System.Windows.Media.CompositionTarget> oggetto offre la possibilità di creare animazioni personalizzate basate su un callback per frame.  
  
 <xref:System.Windows.Media.CompositionTarget> è una classe statica che rappresenta l'area di visualizzazione in cui viene disegnata l'applicazione. Il <xref:System.Windows.Media.CompositionTarget.Rendering> evento viene generato ogni volta che viene disegnata la scena dell'applicazione. La frequenza dei fotogrammi di rendering è il numero di volte al secondo in cui viene disegnata la scena.  
  
> [!NOTE]
>  Per un esempio di codice completo utilizzando <xref:System.Windows.Media.CompositionTarget>, vedere [utilizzando l'esempio CompositionTarget](http://go.microsoft.com/fwlink/?LinkID=160045).  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Media.CompositionTarget.Rendering> evento viene generato durante il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] processo di rendering. Nell'esempio seguente viene illustrato come registrare un <xref:System.EventHandler> delegare statica <xref:System.Windows.Media.CompositionTarget.Rendering> metodo <xref:System.Windows.Media.CompositionTarget>.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget1)]
 [!code-vb[CompositionTargetSample#CompositionTarget1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget1)]  
  
 È possibile usare il metodo del gestore eventi di rendering per creare il contenuto del disegno personalizzato. Questo metodo del gestore eventi viene chiamato una volta per ogni fotogramma. Ogni volta che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] esegue il marshalling dei dati di rendering salvati in modo permanente nella struttura ad albero visuale sul grafico della scena di composizione, viene chiamato il metodo del gestore eventi. Il metodo del gestore eventi viene chiamato anche se le modifiche alla struttura ad albero visuale forzano aggiornamenti al grafico della scena di composizione. Si noti che il metodo del gestore eventi verrà chiamato dopo l'elaborazione del layout. È tuttavia possibile modificare il layout nel metodo del gestore eventi, ovvero il layout verrà ulteriormente elaborato prima del rendering.  
  
 Nell'esempio seguente viene illustrato come è possibile fornire un disegno personalizzato in un <xref:System.Windows.Media.CompositionTarget> metodo del gestore eventi. In questo caso, il colore di sfondo di <xref:System.Windows.Controls.Canvas> viene disegnata con un valore di colore in base alla posizione di coordinate del mouse. Se si sposta il puntatore del mouse all'interno di <xref:System.Windows.Controls.Canvas>, le modifiche ai colori di sfondo. Viene anche calcolata la frequenza media dei fotogrammi in base al tempo trascorso e al numero totale dei fotogrammi sottoposti a rendering.  
  
 [!code-csharp[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositionTargetSample/CSharp/Window1.xaml.cs#compositiontarget2)]
 [!code-vb[CompositionTargetSample#CompositionTarget2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CompositionTargetSample/visualbasic/window1.xaml.vb#compositiontarget2)]  
  
 Si potrebbe rilevare che un disegno personalizzato procede a velocità diverse in computer diversi. Questo avviene poiché il disegno personalizzato dipende dalla frequenza dei fotogrammi. A seconda del sistema è in esecuzione e il carico di lavoro del sistema, il <xref:System.Windows.Media.CompositionTarget.Rendering> evento può essere chiamato un diverso numero di volte al secondo. Per informazioni su come determinare le prestazioni e le funzionalità hardware grafiche per un dispositivo che esegue un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [Livelli di rendering della grafica](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 Aggiunta o rimozione di un rendering <xref:System.EventHandler> delegato durante la generazione dell'evento sarà ritardata fino al termine dell'evento viene attivato. Questo comportamento è coerente con la modalità <xref:System.MulticastDelegate>-eventi di base vengono gestiti in Common Language Runtime (CLR). Si noti anche che gli eventi di rendering non verranno necessariamente chiamati in un ordine particolare. Se si dispone di più <xref:System.EventHandler> delegati che si basano su un ordine specifico, è necessario registrare un solo <xref:System.Windows.Media.CompositionTarget.Rendering> evento e multiplex i delegati in corrette ordinare manualmente.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Media.CompositionTarget>  
 [Cenni preliminari sul rendering della grafica WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
