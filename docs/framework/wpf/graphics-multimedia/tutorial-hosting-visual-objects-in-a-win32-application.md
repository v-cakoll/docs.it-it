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
ms.openlocfilehash: d04357e0770bbf8eebe8f40a86a19ddc9baae3ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187422"
---
# <a name="tutorial-hosting-visual-objects-in-a-win32-application"></a>Esercitazione: hosting di oggetti visivi in un'applicazione Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce un ambiente completo per la creazione di applicazioni. Tuttavia, quando si dispone di un investimento sostanziale nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] codice Win32, potrebbe essere più efficace aggiungere funzionalità all'applicazione anziché riscrivere il codice. Per fornire il supporto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per Win32 e sottosistemi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] grafici utilizzati contemporaneamente in un'applicazione, fornisce un meccanismo per l'hosting di oggetti in una finestra Win32.  
  
 In questa esercitazione viene descritto come scrivere un'applicazione di esempio, [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting), che ospita [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] oggetti visivi in una finestra Win32.  

<a name="requirements"></a>
## <a name="requirements"></a>Requisiti  
 In questa esercitazione si presuppone [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] una familiarità di base con la programmazione Win32 e Win32.This tutorial assumes a basic familiarity with both and Win32 programming. Per un'introduzione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di base alla programmazione, vedere [Procedura dettagliata: prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md). Per un'introduzione alla programmazione Win32, vedere uno dei numerosi libri sull'argomento, in particolare *Programming Windows* di Charles Petzold.  
  
> [!NOTE]
> Questa esercitazione include numerosi esempi di codice relativi all'esempio associato. Tuttavia, per una questione di leggibilità, il codice di esempio completo non è compreso. Per il codice di esempio completo, vedere [Hit Test with Win32 Interoperation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting).  
  
<a name="creating_the_host_win32_window"></a>
## <a name="creating-the-host-win32-window"></a>Creazione di una finestra Win32 host  
 La chiave [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per ospitare oggetti in una <xref:System.Windows.Interop.HwndSource> finestra Win32 è la classe. Questa classe esegue [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il wrapping degli oggetti in una finestra Win32, consentendo ne di incorporarli nella [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] finestra come finestra figlio.  
  
 Nell'esempio seguente viene illustrato <xref:System.Windows.Interop.HwndSource> il codice per la creazione dell'oggetto come finestra contenitore Win32 per gli oggetti visivi. Per impostare lo stile, la posizione e altri parametri <xref:System.Windows.Interop.HwndSourceParameters> della finestra Win32, utilizzare l'oggetto .  
  
 [!code-csharp[VisualsHitTesting#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#101)]
 [!code-vb[VisualsHitTesting#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#101)]  
  
> [!NOTE]
> Il valore <xref:System.Windows.Interop.HwndSourceParameters.ExtendedWindowStyle%2A> della proprietà non può essere impostato su WS_EX_TRANSPARENT. Ciò significa che la finestra Win32 host non può essere trasparente. Per questo motivo, il colore di sfondo della finestra Win32 host è impostato sullo stesso colore di sfondo della finestra padre.  
  
<a name="adding_visual_objects_to_the_host_win32_window"></a>
## <a name="adding-visual-objects-to-the-host-win32-window"></a>Aggiunta di oggetti visivi alla finestra Win32 host  
 Dopo aver creato una finestra contenitore Win32 host per gli oggetti visivi, è possibile aggiungervi oggetti visivi. È necessario assicurarsi che tutte le trasformazioni degli oggetti visivi, ad esempio le animazioni, non si estendano oltre i limiti del rettangolo di delimitazione della finestra Win32 host.  
  
 Nell'esempio seguente viene illustrato <xref:System.Windows.Interop.HwndSource> il codice per la creazione dell'oggetto e l'aggiunta di oggetti visivi.  
  
> [!NOTE]
> La <xref:System.Windows.Interop.HwndSource.RootVisual%2A> proprietà <xref:System.Windows.Interop.HwndSource> dell'oggetto viene impostata sul primo oggetto visivo aggiunto alla finestra Win32 host. L'oggetto visivo radice definisce il nodo di primo livello della struttura ad albero di oggetti visivi. Tutti gli oggetti visivi successivi aggiunti alla finestra Win32 host vengono aggiunti come oggetti figlio.  
  
 [!code-csharp[VisualsHitTesting#100](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#100)]
 [!code-vb[VisualsHitTesting#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#100)]  
  
<a name="implementing_the_win32_message_filter"></a>
## <a name="implementing-the-win32-message-filter"></a>Implementazione del filtro messaggi Win32  
 La finestra Win32 host per gli oggetti visivi richiede una procedura di filtro dei messaggi della finestra per gestire i messaggi inviati alla finestra dalla coda dell'applicazione. La routine della finestra riceve messaggi dal sistema Win32. Può trattarsi di messaggi di input o di messaggi di gestione della finestra. È possibile facoltativamente gestire un messaggio nella routine della finestra oppure passarlo al sistema per l'elaborazione predefinita.  
  
 L'oggetto <xref:System.Windows.Interop.HwndSource> definito come padre per gli oggetti visivi deve fare riferimento alla routine di filtro messaggi della finestra fornita. Quando si <xref:System.Windows.Interop.HwndSource> crea l'oggetto, impostare la <xref:System.Windows.Interop.HwndSourceParameters.HwndSourceHook%2A> proprietà in modo che faccia riferimento alla routine della finestra.  
  
 [!code-csharp[VisualsHitTesting#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#102)]
 [!code-vb[VisualsHitTesting#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#102)]  
  
 L'esempio seguente illustra il codice per la gestione dei messaggi di rilascio dei pulsanti sinistro e destro del mouse. Il valore della coordinata della posizione di `lParam` hit del mouse è contenuto nel valore del parametro.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
<a name="processing_the_win32_messages"></a>
## <a name="processing-the-win32-messages"></a>Elaborazione dei messaggi Win32  
 Il codice nell'esempio seguente mostra come viene eseguito un hit test sulla gerarchia di oggetti visivi contenuti nella finestra Win32 host. È possibile identificare se un punto si trova all'interno <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> della geometria di un oggetto visivo, utilizzando il metodo per specificare l'oggetto visivo radice e il valore delle coordinate con cui eseguire l'hit test. In questo caso, l'oggetto visivo <xref:System.Windows.Interop.HwndSource.RootVisual%2A> radice <xref:System.Windows.Interop.HwndSource> è il valore della proprietà dell'oggetto.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Per ulteriori informazioni [sull'hit](hit-testing-in-the-visual-layer.md)testing su oggetti visivi, vedere Hit Testing nel livello visivo .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.HwndSource>
- [Hit Test with Win32 Interoperation Sample (Esempio di hit test con interoperatività Win32)](https://github.com/microsoft/WPF-Samples/tree/master/Visual%20Layer/VisualsHitTesting)
- [Hit testing a livello visivo](hit-testing-in-the-visual-layer.md)
