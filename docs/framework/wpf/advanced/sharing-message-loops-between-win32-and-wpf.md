---
title: Condivisione dei cicli di messaggi tra Win32 e WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
ms.openlocfilehash: e1b96284d69645876d3e383beb03a2cc540d8b7b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731714"
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Condivisione dei cicli di messaggi tra Win32 e WPF
In questo argomento viene descritto come implementare un ciclo di messaggi per l'interoperabilità con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], utilizzando l'esposizione del ciclo di messaggi esistente in <xref:System.Windows.Threading.Dispatcher> o creando un ciclo di messaggi separato sul lato Win32 del codice di interoperabilità.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher e il ciclo di messaggi  
 Uno scenario normale per l'interoperabilità e il supporto degli eventi da tastiera consiste nell'implementare <xref:System.Windows.Interop.IKeyboardInputSink>o la sottoclasse da classi che implementano già <xref:System.Windows.Interop.IKeyboardInputSink>, ad esempio <xref:System.Windows.Interop.HwndSource> o <xref:System.Windows.Interop.HwndHost>. Tuttavia, il supporto per i sink di tastiera non risolve tutte le possibili esigenze del ciclo di messaggi durante l'invio e la ricezione di messaggi tra i limiti di interoperatività. Per formalizzare un'architettura del ciclo di messaggi dell'applicazione, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce la classe <xref:System.Windows.Interop.ComponentDispatcher>, che definisce un protocollo semplice per il completamento di un ciclo di messaggi.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> è una classe statica che espone diversi membri. L'ambito di ogni metodo è associato in modo implicito al thread chiamante. Un ciclo di messaggi deve chiamare alcune di queste API in momenti critici, come definito nella sezione successiva.  
  
 <xref:System.Windows.Interop.ComponentDispatcher> fornisce eventi che possono essere ascoltati da altri componenti (ad esempio il sink della tastiera). La classe <xref:System.Windows.Threading.Dispatcher> chiama tutti i metodi di <xref:System.Windows.Interop.ComponentDispatcher> appropriati in una sequenza appropriata. Se si implementa un ciclo di messaggi personalizzato, il codice è responsabile della chiamata di <xref:System.Windows.Interop.ComponentDispatcher> metodi in modo analogo.  
  
 La chiamata di <xref:System.Windows.Interop.ComponentDispatcher> metodi in un thread richiamerà solo i gestori eventi registrati su tale thread.  
  
## <a name="writing-message-loops"></a>Scrittura di cicli di messaggi  
 Di seguito è riportato un elenco di controllo dei membri di <xref:System.Windows.Interop.ComponentDispatcher> che verrà usato se si scrive il proprio ciclo di messaggi:  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: il ciclo di messaggi deve chiamare questo oggetto per indicare che il thread è modale.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: il ciclo di messaggi deve chiamare questo oggetto per indicare che il thread è stato ripristinato come non modale.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: il ciclo di messaggi deve chiamare questo oggetto per indicare che <xref:System.Windows.Interop.ComponentDispatcher> deve generare l'evento di <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>. <xref:System.Windows.Interop.ComponentDispatcher> non genererà <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> se <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> è `true`, ma i cicli di messaggi possono scegliere di chiamare <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> anche se <xref:System.Windows.Interop.ComponentDispatcher> non è in grado di rispondere allo stato modale.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: il ciclo di messaggi deve chiamare questo oggetto per indicare che è disponibile un nuovo messaggio. Il valore restituito indica se un listener a un evento <xref:System.Windows.Interop.ComponentDispatcher> ha gestito il messaggio. Se <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> restituisce `true` (gestito), il dispatcher non deve eseguire altre operazioni con il messaggio. Se il valore restituito è `false`, è previsto che il dispatcher chiami la funzione Win32 `TranslateMessage`, quindi chiama `DispatchMessage`.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>Utilizzo di ComponentDispatcher e della gestione dei messaggi esistente  
 Di seguito è riportato un elenco di controllo dei membri <xref:System.Windows.Interop.ComponentDispatcher> che si utilizzeranno se si utilizza il ciclo di messaggi inerente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: restituisce un valore che indica se l'applicazione non è più modale, ad esempio se è stato eseguito il push di un ciclo di messaggi modale. <xref:System.Windows.Interop.ComponentDispatcher> possibile tenere traccia di questo stato poiché la classe mantiene un conteggio di <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> e <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> chiamate dal ciclo di messaggi.  
  
- gli eventi <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> e <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> seguono le regole standard per le chiamate di delegati. I delegati vengono richiamati in un ordine non specificato e tutti i delegati vengono richiamati anche se il primo contrassegna il messaggio come gestito.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: indica un tempo appropriato ed efficiente per l'elaborazione inattiva (non sono presenti altri messaggi in sospeso per il thread). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> non verrà generato se il thread è modale.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: generato per tutti i messaggi elaborati dal message pump.  
  
- <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: generato per tutti i messaggi che non sono stati gestiti durante <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Un messaggio viene considerato gestito se dopo l'evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> o <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>, il parametro `handled` passato per riferimento nei dati dell'evento viene `true`. I gestori di eventi devono ignorare il messaggio se `handled` è `true`, perché questo significa che il messaggio è stato gestito prima dal gestore diverso. I gestori eventi di entrambi gli eventi possono modificare il messaggio. Il dispatcher deve inviare il messaggio modificato e non il messaggio originale non modificato. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> viene recapitato a tutti i listener, ma l'intenzione architettonica è che solo la finestra di primo livello contenente l'elemento HWND a cui i messaggi destinati devono richiamare il codice in risposta al messaggio.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Modo in cui HwndSource considera gli eventi ComponentDispatcher  
 Se la <xref:System.Windows.Interop.HwndSource> è una finestra di primo livello (nessun HWND padre), verrà registrata con <xref:System.Windows.Interop.ComponentDispatcher>. Se <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> viene generato e se il messaggio è destinato alle finestre figlio o <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndSource> chiama la sequenza di sink della tastiera <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A><xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A>.  
  
 Se il <xref:System.Windows.Interop.HwndSource> non è una finestra di primo livello (con un HWND padre), non vi sarà alcuna gestione. Per la gestione è prevista solo la finestra di primo livello ed è prevista una finestra di primo livello con supporto per il sink della tastiera come parte di uno scenario di interoperabilità.  
  
 Se <xref:System.Windows.Interop.HwndHost.WndProc%2A> su un <xref:System.Windows.Interop.HwndSource> viene chiamato senza che venga chiamato per primo un metodo di sink della tastiera appropriato, l'applicazione riceverà gli eventi di tastiera di livello superiore, ad esempio <xref:System.Windows.UIElement.KeyDown>. Tuttavia, non verrà chiamato alcun metodo di sink della tastiera, che elude le funzionalità desiderate del modello di input da tastiera, ad esempio il supporto della chiave di accesso. Questo problema potrebbe verificarsi perché il ciclo di messaggi non ha notificato correttamente al thread pertinente il <xref:System.Windows.Interop.ComponentDispatcher>o perché l'elemento HWND padre non ha richiamato le risposte appropriate per il sink della tastiera.  
  
 Un messaggio che va al sink della tastiera potrebbe non essere inviato a HWND se sono stati aggiunti hook per quel messaggio usando il metodo <xref:System.Windows.Interop.HwndSource.AddHook%2A>. Il messaggio potrebbe essere stato gestito a livello di message pump direttamente e non inviato alla funzione `DispatchMessage`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Interop.ComponentDispatcher>
- <xref:System.Windows.Interop.IKeyboardInputSink>
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Modello di threading](threading-model.md)
- [Cenni preliminari sull'input](input-overview.md)
