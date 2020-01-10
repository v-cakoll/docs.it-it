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
ms.openlocfilehash: 621684e14f9d1b599c4ef60e3731f0f58f31aacd
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740169"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Esercitazione: hosting di oggetti visivi in un'applicazione Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si ha un investimento sostanziale nel codice Win32, potrebbe essere più efficace aggiungere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funzionalità all'applicazione anziché riscrivere il codice. Per fornire supporto per i sottosistemi grafici Win32 e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] utilizzati simultaneamente in un'applicazione, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce un meccanismo per l'hosting di oggetti in una finestra di Win32.  
  
 In questa esercitazione viene descritto come scrivere un'applicazione di esempio, eseguire un [hit test con l'esempio di interoperatività Win32](https://go.microsoft.com/fwlink/?LinkID=159995)che ospita [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetti visivi in una finestra Win32.  

<a name="requirements"></a>   
## <a name="requirements"></a>Requisiti di  
 Questa esercitazione presuppone una conoscenza di base della programmazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e Win32. Per un'introduzione di base alla programmazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vedere [procedura dettagliata: applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md). Per un'introduzione alla programmazione Win32, vedere uno dei numerosi libri sull'argomento, in particolare *programmare Windows* di Charles Petzold.  
  
> [!NOTE]
> Questa esercitazione include numerosi esempi di codice relativi all'esempio associato. Tuttavia, per una questione di leggibilità, il codice di esempio completo non è compreso. Per il codice di esempio completo, vedere [esempio di hit test con interoperatività Win32](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
<a name="creating_the_host_win32_window"></a>   
## <a name="creating-the-host-win32-window"></a>Creazione di una finestra Win32 host  
 La chiave per ospitare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetti in una finestra Win32 è la classe <xref:System.Windows.Interop.HwndSource>. Questa classe esegue il wrapping degli oggetti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in una finestra Win32, consentendo di incorporarli nel [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] come finestra figlio.  
  
 Nell'esempio seguente viene illustrato il codice per la creazione dell'oggetto <xref:System.Windows.Interop.HwndSource> come finestra del contenitore Win32 per gli oggetti visivi. Per impostare lo stile della finestra, la posizione e altri parametri per la finestra Win32, utilizzare l'oggetto <xref:System.Windows.Interop.HwndSourceParameters>.  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> Impossibile impostare il valore della proprietà <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> su WS_EX_TRANSPARENT. Ciò significa che la finestra Win32 dell'host non può essere trasparente. Per questo motivo, il colore di sfondo della finestra Win32 host viene impostato sullo stesso colore di sfondo della finestra padre.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>   
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Aggiunta di oggetti visivi alla finestra Win32 host  
 Dopo aver creato una finestra del contenitore Win32 host per gli oggetti visivi, è possibile aggiungervi oggetti visivi. È necessario assicurarsi che tutte le trasformazioni degli oggetti visivi, ad esempio le animazioni, non si estendano oltre i limiti del rettangolo di delimitazione della finestra Win32 host.  
  
 Nell'esempio seguente viene illustrato il codice per la creazione dell'oggetto <xref:System.Windows.Interop.HwndSource> e l'aggiunta di oggetti visivi.  
  
> [!NOTE]
> La proprietà <xref:System.Windows.Interop.HwndSource.RootVisual%2A> dell'oggetto <xref:System.Windows.Interop.HwndSource> è impostata sul primo oggetto visivo aggiunto alla finestra Win32 host. L'oggetto visivo radice definisce il nodo di primo livello della struttura ad albero di oggetti visivi. Tutti gli oggetti visivi successivi aggiunti alla finestra Win32 host vengono aggiunti come oggetti figlio.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>   
## <a name="implementing-the-win32-message-filter"></a>Implementazione del filtro messaggi Win32  
 La finestra host Win32 per gli oggetti visivi richiede una procedura di filtro messaggi finestra per gestire i messaggi inviati alla finestra dalla coda dell'applicazione. La routine della finestra riceve i messaggi dal sistema Win32. Può trattarsi di messaggi di input o di messaggi di gestione della finestra. È possibile facoltativamente gestire un messaggio nella routine della finestra oppure passarlo al sistema per l'elaborazione predefinita.  
  
 L'oggetto <xref:System.Windows.Interop.HwndSource> definito come padre per gli oggetti visivi deve fare riferimento alla procedura di filtro messaggi della finestra fornita. Quando si crea l'oggetto <xref:System.Windows.Interop.HwndSource>, impostare la proprietà <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> per fare riferimento alla routine della finestra.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 L'esempio seguente illustra il codice per la gestione dei messaggi di rilascio dei pulsanti sinistro e destro del mouse. Il valore della coordinata della posizione di hit del mouse è contenuto nel valore del parametro `lParam`.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>   
## <a name="processing-the-win32-messages"></a>Elaborazione dei messaggi Win32  
 Il codice nell'esempio seguente illustra come viene eseguito un hit test sulla gerarchia di oggetti visivi contenuti nella finestra Win32 host. È possibile stabilire se un punto si trova all'interno della geometria di un oggetto visivo, usando il metodo <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> per specificare l'oggetto visivo radice e il valore della coordinata su cui eseguire l'hit test. In questo caso, l'oggetto visivo radice corrisponde al valore della proprietà <xref:System.Windows.Interop.HwndSource.RootVisual%2A> dell'oggetto <xref:System.Windows.Interop.HwndSource>.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Per altre informazioni sull'hit testing su oggetti visivi, vedere [hit testing a livello visivo](hit-testing-in-the-visual-layer.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndSource>
- [Esempio di hit test con interoperatività Win32](https://go.microsoft.com/fwlink/?LinkID=159995)
- [Hit testing a livello visivo](hit-testing-in-the-visual-layer.md)
