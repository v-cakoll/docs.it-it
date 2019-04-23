---
title: "Esercitazione: Hosting di oggetti visivi in un'applicazione Win32"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual objects in Win32 code [WPF]
- Win32 code [WPF], visual objects in
- hosting [WPF], visual objects in Win32 code
ms.assetid: f0e1600c-3217-43d5-875d-1864fa7fe628
ms.openlocfilehash: b260f96246f0d9e5447b74a05e1396bfef176197
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111462"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Esercitazione: Hosting di oggetti visivi in un'applicazione Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando è presente un investimento sostanziale [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] codice, potrebbe essere più efficace aggiungere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funzionalità all'applicazione anziché riscrivere il codice. Per fornire supporto per [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usati contemporaneamente in un'applicazione, i sottosistemi di grafici [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un meccanismo per l'hosting di oggetti in un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra.  
  
 Questa esercitazione descrive come scrivere un'applicazione di esempio [Hit Test with Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995), che gli host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetti visivi un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra.  

<a name="requirements"></a>   
## <a name="requirements"></a>Requisiti  
 Questa esercitazione presuppone una conoscenza di base della programmazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Per un'introduzione di base [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] programmazione, vedere [procedura dettagliata: Prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md). Per un'introduzione al [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programmazione, vedere uno qualsiasi dei numerosi manuali sull'argomento, in particolare *programmazione Windows* di Charles Petzold.  
  
> [!NOTE]
>  Questa esercitazione include numerosi esempi di codice relativi all'esempio associato. Tuttavia, per una questione di leggibilità, il codice di esempio completo non è compreso. Per il codice di esempio completo, vedere [Hit Test with Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Creazione di una finestra Win32 host  
 La chiave per ospitare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetti un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra è il <xref:System.Windows.Interop.HwndSource> classe. Questa classe esegue il wrapping di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetti un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra, consentendo di incorporarlo nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] come finestra figlio.  
  
 L'esempio seguente mostra il codice per la creazione di <xref:System.Windows.Interop.HwndSource> dell'oggetto come il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra contenitore per gli oggetti visivi. Per impostare lo stile della finestra, posizione e altri parametri per il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra, usare il <xref:System.Windows.Interop.HwndSourceParameters> oggetto.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
>  Il valore della <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> proprietà non può essere impostata su WS_EX_TRANSPARENT. Ciò significa che l'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra non può essere trasparente. Per questo motivo, il colore di sfondo dell'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] intervallo è impostato sullo stesso colore di sfondo della finestra padre.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Aggiunta di oggetti visivi alla finestra Win32 host  
 Dopo aver creato un host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra contenitore per gli oggetti visivi, è possibile aggiungere oggetti visivi a esso. È opportuno verificare che tutte le trasformazioni degli oggetti visivi, ad esempio le animazioni, non si estendano oltre i limiti dell'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] rettangolo di delimitazione della finestra.  
  
 L'esempio seguente mostra il codice per la creazione di <xref:System.Windows.Interop.HwndSource> dell'oggetto e l'aggiunta di oggetti visivi a esso.  
  
> [!NOTE]
>  Il <xref:System.Windows.Interop.HwndSource.RootVisual%2A> proprietà del <xref:System.Windows.Interop.HwndSource> oggetto è impostato per il primo oggetto visivo aggiunto all'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra. L'oggetto visivo radice definisce il nodo di primo livello della struttura ad albero di oggetti visivi. Eventuali oggetti visivi successivi aggiunti all'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra vengono aggiunti come oggetti figlio.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Implementazione del filtro messaggi Win32  
 L'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra per gli oggetti visivi richiede una procedura di filtro messaggi finestra per gestire i messaggi vengono inviati alla finestra dalla coda dell'applicazione. La procedura della finestra riceve i messaggi dal [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] sistema. Può trattarsi di messaggi di input o di messaggi di gestione della finestra. È possibile facoltativamente gestire un messaggio nella routine della finestra oppure passarlo al sistema per l'elaborazione predefinita.  
  
 Il <xref:System.Windows.Interop.HwndSource> oggetto su cui è definito come padre per gli oggetti visivi deve fare riferimento alla routine del filtro messaggi finestra è fornire. Quando si crea il <xref:System.Windows.Interop.HwndSource> dell'oggetto, impostare il <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> proprietà cui fare riferimento alla routine della finestra.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 L'esempio seguente illustra il codice per la gestione dei messaggi di rilascio dei pulsanti sinistro e destro del mouse. Il valore della coordinata del mouse posizione rilevata è contenuto nel valore della `lParam` parametro.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Elaborazione dei messaggi Win32  
 Il codice nell'esempio seguente viene illustrato come viene eseguito un hit test sulla gerarchia di oggetti visivi contenuta nell'host [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finestra. È possibile identificare se un punto è all'interno della geometria di un oggetto visivo, usando il <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> metodo per specificare l'oggetto visivo radice e il valore delle coordinate per eseguire l'hit test. In questo caso, l'oggetto visivo radice è il valore della <xref:System.Windows.Interop.HwndSource.RootVisual%2A> proprietà del <xref:System.Windows.Interop.HwndSource> oggetto.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Per altre informazioni sull'hit testing su oggetti visivi, vedere [Hit Testing a livello visivo](hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndSource>
- [Eseguire un hit Test con interoperatività Win32](https://go.microsoft.com/fwlink/?LinkID=159995)
- [Hit testing a livello visivo](hit-testing-in-the-visual-layer.md)
