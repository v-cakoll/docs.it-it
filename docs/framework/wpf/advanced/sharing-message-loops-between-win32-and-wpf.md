---
title: Condivisione dei cicli di messaggi tra Win32 e WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: 74055ec3facb7db9145c4c0e969d57da24eccbc8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053418"
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Condivisione dei cicli di messaggi tra Win32 e WPF
In questo argomento descrive come implementare un ciclo di messaggi per essere interoperabile con i [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], tramite l'utilizzo esistente del messaggio l'esposizione di ciclo in <xref:System.Windows.Threading.Dispatcher> o tramite la creazione di un ciclo di messaggi separate nel [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] lato del codice di interoperabilità.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher e il ciclo di messaggi  
 Uno scenario comune di supporto per gli eventi della tastiera e interoperabilità consiste nell'implementare <xref:System.Windows.Interop.IKeyboardInputSink>, o di sottoclassi da classi che implementano già <xref:System.Windows.Interop.IKeyboardInputSink>, ad esempio <xref:System.Windows.Interop.HwndSource> o <xref:System.Windows.Interop.HwndHost>. Tuttavia, il supporto di sink della tastiera non si applica tutte le esigenze di ciclo di messaggi possibili che possono verificarsi quando l'invio e ricezione dei messaggi attraverso i limiti di interoperatività. Per formalizzare un'architettura di ciclo di messaggi dell'applicazione, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce il <xref:System.Windows.Interop.ComponentDispatcher> (classe), che definisce un protocollo semplice per un ciclo di messaggi da seguire.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> è una classe statica che espone vari membri. L'ambito di ogni metodo in modo implicito è associato al thread chiamante. Un ciclo di messaggi deve chiamare alcune di esse [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] nei momenti critici (come definito nella sezione successiva).  
  
 <xref:System.Windows.Interop.ComponentDispatcher> fornisce gli eventi che possono essere in ascolto altri componenti (ad esempio, il sink della tastiera). Il <xref:System.Windows.Threading.Dispatcher> classe chiamate tutte appropriate <xref:System.Windows.Interop.ComponentDispatcher> metodi in una sequenza appropriata. Se si implementa il proprio ciclo di messaggi, il codice è responsabile della chiamata <xref:System.Windows.Interop.ComponentDispatcher> metodi in modo analogo.  
  
 La chiamata a <xref:System.Windows.Interop.ComponentDispatcher> metodi su un thread solo richiama gestori di eventi che sono stati registrati in tale thread.  
  
## <a name="writing-message-loops"></a>Cicli di messaggi di scrittura  
 Di seguito è riportato un elenco di controllo <xref:System.Windows.Interop.ComponentDispatcher> membri che è necessario utilizzare per scrivere il proprio ciclo di messaggi:  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: il ciclo di messaggi deve chiamare questo metodo per indicare che il thread è modale.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: il ciclo di messaggi deve chiamare questo metodo per indicare che il thread è stato ripristinato allo stato non modale.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: deve chiamare questo metodo per indicare che il ciclo di messaggi <xref:System.Windows.Interop.ComponentDispatcher> deve generare il <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> evento. <xref:System.Windows.Interop.ComponentDispatcher> non genererà <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> se <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> viene `true`, ma i cicli di messaggi possono scegliere di chiamare <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> anche se <xref:System.Windows.Interop.ComponentDispatcher> non può rispondere se si trova nello stato modale.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: il ciclo di messaggi deve chiamare questo metodo per indicare che è disponibile un nuovo messaggio. Il valore restituito indica se un listener per un <xref:System.Windows.Interop.ComponentDispatcher> il messaggio di evento gestito. Se <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> restituisce `true` (gestito), il dispatcher deve eseguire altre operazioni con il messaggio. Se il valore restituito sarà `false`, il dispatcher per chiamare il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] funzione `TranslateMessage`, quindi chiamare `DispatchMessage`.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>Usando ComponentDispatcher e con la gestione dei messaggi  
 Di seguito è riportato un elenco di controllo <xref:System.Windows.Interop.ComponentDispatcher> membri utilizzerà se ci si affida l'intrinseca [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] loop di messaggi.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: restituisce se l'applicazione è diventato modale (ad esempio, un ciclo modale di messaggio è stato eseguito il push). <xref:System.Windows.Interop.ComponentDispatcher> può rilevare questo stato perché la classe gestisce un conteggio dei <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> e <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> chiamate dal ciclo di messaggi.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> e <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> eventi conformi alle regole standard per le chiamate del delegato. I delegati vengono richiamati in un ordine non specificato e tutti i delegati vengono richiamati anche se il primo contrassegna il messaggio come gestito.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: indica un tempo appropriato ed efficiente per l'elaborazione inattiva (non sono presenti altri messaggi in sospeso per il thread). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> non essere generato se il thread è modale.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: generati per tutti i messaggi che elabora il message pump.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: generati per tutti i messaggi che non sono stati gestiti durante <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Un messaggio viene considerato gestito se dopo il <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> evento o <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> evento, il `handled` parametro passato per riferimento nei dati dell'evento è `true`. I gestori eventi devono ignorare il messaggio se `handled` è `true`, perché ciò significa che il messaggio è stato gestito prima di tutto il gestore diverso. I gestori di eventi sia per gli eventi possono modificare il messaggio. Il dispatcher deve inviare il messaggio modificato e non il messaggio non modificato originale. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> viene recapitato a tutti i listener, ma l'intenzione dell'architettura solo la finestra di primo livello che contiene l'oggetto HWND in corrispondenza del quale i messaggi di destinazione devono richiamare il codice in risposta al messaggio.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Gli eventi ComponentDispatcher di HwndSource  
 Se il <xref:System.Windows.Interop.HwndSource> è una finestra di primo livello (nessun valore HWND padre), verrà registrato con <xref:System.Windows.Interop.ComponentDispatcher>. Se <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> viene generato, e se il messaggio è destinato il <xref:System.Windows.Interop.HwndSource> finestre figlio, o <xref:System.Windows.Interop.HwndSource> chiamate relativo <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> sequenza di sink di tastiera.  
  
 Se il <xref:System.Windows.Interop.HwndSource> non è una finestra di primo livello (ha un valore HWND padre), non sarà presente alcuna gestione. È previsto solo la finestra di primo livello per eseguire la gestione e vi deve essere una finestra di primo livello con il supporto di sink della tastiera come parte di tutti gli scenari di interoperatività.  
  
 Se <xref:System.Windows.Interop.HwndHost.WndProc%2A> in un <xref:System.Windows.Interop.HwndSource> viene chiamato senza un metodo di sink della tastiera appropriato viene chiamato per primo, l'applicazione riceverà gli eventi di tastiera di livello superiore, ad esempio <xref:System.Windows.UIElement.KeyDown>. Tuttavia, nessun metodo sink della tastiera verrà chiamato, che consente di evitare funzionalità di modello di input da tastiera utile ad esempio il supporto di chiavi di accesso. Questa situazione può verificarsi perché il ciclo di messaggi non ha notificato correttamente i thread rilevanti nel <xref:System.Windows.Interop.ComponentDispatcher>, oppure perché il valore HWND padre non ha richiamato le risposte di sink della tastiera appropriate.  
  
 Inviato un messaggio che va per il sink della tastiera potrebbe non essere per l'oggetto HWND se hook per il messaggio è stato aggiunto usando il <xref:System.Windows.Interop.HwndSource.AddHook%2A> (metodo). Il messaggio potrebbe essere stato gestito a livello del message pump direttamente e non inviato al `DispatchMessage` (funzione).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.ComponentDispatcher>
- <xref:System.Windows.Interop.IKeyboardInputSink>
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Modello di threading](threading-model.md)
- [Cenni preliminari sull'input](input-overview.md)
