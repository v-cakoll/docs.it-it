---
title: "Esercitazione: hosting di oggetti visivi in un'applicazione Win32"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
ms.openlocfilehash: cc78dfd22b0ad2726ce8870a4e03f539ec691d85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565350"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Esercitazione: hosting di oggetti visivi in un'applicazione Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si dispone di un investimento sostanziale in [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] codice, potrebbe essere più efficace aggiungere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funzionalità all'applicazione anziché riscrivere il codice. Per fornire supporto per [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sottosistemi grafici usati contemporaneamente in un'applicazione, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un meccanismo per l'hosting di oggetti in un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra.  
  
 In questa esercitazione viene illustrato come scrivere un'applicazione di esempio, [Hit Test con interoperatività Win32](http://go.microsoft.com/fwlink/?LinkID=159995), tale host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetti visivi un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra.  
  

  
<a name="requirements"></a>   
## <a name="requirements"></a>Requisiti  
 Questa esercitazione presuppone una conoscenza di base della programmazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Per un'introduzione a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di programmazione, vedere [procedura dettagliata: applicazione desktop WPF prima](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md). Per un'introduzione ai [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] di programmazione, vedere uno dei numerosi manuali sull'argomento, in particolare *programmazione Windows* di Charles Petzold.  
  
> [!NOTE]
>  Questa esercitazione include numerosi esempi di codice relativi all'esempio associato. Tuttavia, per una questione di leggibilità, il codice di esempio completo non è compreso. Per il codice di esempio completo, vedere [Hit Test con interoperatività Win32](http://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Creazione di una finestra Win32 host  
 La chiave per ospitare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli oggetti in un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra è la <xref:System.Windows.Interop.HwndSource> classe. Questa classe esegue il wrapping di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gli oggetti in un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra, di modo che possano essere incorporate nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] come finestra figlio.  
  
 Nell'esempio seguente viene illustrato il codice per la creazione di <xref:System.Windows.Interop.HwndSource> oggetto come il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra contenitore per gli oggetti visivi. Per impostare lo stile della finestra, posizione e altri parametri per il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra, utilizzare il <xref:System.Windows.Interop.HwndSourceParameters> oggetto.  
  
 [!code-csharp[VisualsHitTesting#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  Il valore di <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> proprietà non può essere impostata su WS_EX_TRANSPARENT. Ciò significa che l'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra non può essere trasparente. Per questo motivo, il colore di sfondo dell'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra è impostata sullo stesso colore di sfondo della finestra padre.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Aggiunta di oggetti visivi alla finestra Win32 host  
 Dopo aver creato un host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra contenitore per gli oggetti visivi, è possibile aggiungere oggetti visivi a esso. È necessario verificare che tutte le trasformazioni di oggetti visivi, ad esempio le animazioni, non si estendano oltre i limiti dell'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] rettangolo di delimitazione della finestra.  
  
 Nell'esempio seguente viene illustrato il codice per la creazione di <xref:System.Windows.Interop.HwndSource> dell'oggetto e aggiungere oggetti visivi.  
  
> [!NOTE]
>  Il <xref:System.Windows.Interop.HwndSource.RootVisual%2A> proprietà del <xref:System.Windows.Interop.HwndSource> oggetto è impostato per il primo oggetto visivo aggiunto all'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra. L'oggetto visivo radice definisce il nodo di primo livello della struttura ad albero di oggetti visivi. Eventuali oggetti visivi successivamente aggiunti all'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra vengono aggiunti come oggetti figlio.  
  
 [!code-csharp[VisualsHitTesting#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Implementazione del filtro messaggi Win32  
 L'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra per gli oggetti visivi richiede una procedura di filtro di messaggi di finestra per gestire i messaggi inviati alla finestra dalla coda dell'applicazione. La procedura di finestra riceve i messaggi dal [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] sistema. Può trattarsi di messaggi di input o di messaggi di gestione della finestra. È possibile facoltativamente gestire un messaggio nella routine della finestra oppure passarlo al sistema per l'elaborazione predefinita.  
  
 Il <xref:System.Windows.Interop.HwndSource> oggetto definito come padre per gli oggetti visivi deve fare riferimento alla routine di filtro di messaggi di finestra è fornire. Quando si crea il <xref:System.Windows.Interop.HwndSource> dell'oggetto, impostare il <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> proprietà per fare riferimento alla routine della finestra.  
  
 [!code-csharp[VisualsHitTesting#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 L'esempio seguente illustra il codice per la gestione dei messaggi di rilascio dei pulsanti sinistro e destro del mouse. Il valore della coordinata del mouse posizione rilevata è contenuto nel valore della `lParam` parametro.  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Elaborazione dei messaggi Win32  
 Il codice nell'esempio seguente viene illustrata l'esecuzione sulla gerarchia di oggetti visivi contenuta nell'host di un hit test [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra. È possibile individuare se un punto è all'interno della geometria di un oggetto visivo, utilizzando il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> per specificare l'oggetto visivo radice e il valore della coordinata per l'hit test. In questo caso, l'oggetto visivo radice è il valore di <xref:System.Windows.Interop.HwndSource.RootVisual%2A> proprietà del <xref:System.Windows.Interop.HwndSource> oggetto.  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Per ulteriori informazioni sull'hit testing su oggetti visivi, vedere [Hit Testing nel livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Interop.HwndSource>  
 [Hit Test con esempio di interoperatività Win32](http://go.microsoft.com/fwlink/?LinkID=159995)  
 [Hit testing a livello visivo](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)
