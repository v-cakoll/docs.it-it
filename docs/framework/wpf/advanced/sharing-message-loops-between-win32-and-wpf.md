---
title: Condivisione dei cicli di messaggi tra Win32 e WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Win32 code [WPF], sharing message loops
- message loops [WPF]
- sharing message loops [WPF]
- interoperability [WPF], Win32
ms.assetid: 39ee888c-e5ec-41c8-b11f-7b851a554442
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3122100f93d15c04c109564e1abd2dc13f37990
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="sharing-message-loops-between-win32-and-wpf"></a>Condivisione dei cicli di messaggi tra Win32 e WPF
In questo argomento viene descritto come implementare un ciclo di messaggi per l'interoperabilità con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], tramite l'utilizzo esistente messaggio esposizione del ciclo in <xref:System.Windows.Threading.Dispatcher> oppure creando un ciclo di messaggi separati sul [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] lato del codice di interoperabilità.  
  
## <a name="componentdispatcher-and-the-message-loop"></a>ComponentDispatcher e il ciclo di messaggi  
 Uno scenario comune di supporto degli eventi di interoperabilità e la tastiera consiste nell'implementare <xref:System.Windows.Interop.IKeyboardInputSink>, o di sottoclassi da classi che implementano già <xref:System.Windows.Interop.IKeyboardInputSink>, ad esempio <xref:System.Windows.Interop.HwndSource> o <xref:System.Windows.Interop.HwndHost>. Tuttavia, il supporto del sink di tastiera non soddisfare tutte le esigenze ciclo possibile messaggio che potrebbe essere durante l'invio e ricezione di messaggi tra i limiti di interoperabilità. Per formalizzare un'architettura di ciclo di messaggi dell'applicazione, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] fornisce il <xref:System.Windows.Interop.ComponentDispatcher> (classe), che definisce un protocollo semplice per un ciclo di messaggi da seguire.  
  
 <xref:System.Windows.Interop.ComponentDispatcher>è una classe statica che espone molti membri. L'ambito di ogni metodo in modo implicito è associato al thread chiamante. Un ciclo di messaggi è necessario chiamare alcune [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] nei momenti critici (come definito nella sezione successiva).  
  
 <xref:System.Windows.Interop.ComponentDispatcher>fornisce gli eventi che altri componenti (ad esempio il sink di tastiera) possono restare in attesa. Il <xref:System.Windows.Threading.Dispatcher> classe chiamate tutti i <xref:System.Windows.Interop.ComponentDispatcher> metodi in una sequenza appropriata. Se si implementa un ciclo di messaggi, il codice è responsabile della chiamata <xref:System.Windows.Interop.ComponentDispatcher> metodi in modo simile.  
  
 La chiamata <xref:System.Windows.Interop.ComponentDispatcher> metodi su un thread solo richiama i gestori eventi registrati su tale thread.  
  
## <a name="writing-message-loops"></a>Cicli di messaggi di scrittura  
 Di seguito è riportato un elenco di controllo <xref:System.Windows.Interop.ComponentDispatcher> membri che è necessario utilizzare scrivere un ciclo di messaggi:  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A>: il ciclo di messaggi deve chiamare questo metodo per indicare che il thread è modale.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A>: il ciclo di messaggi deve chiamare questo metodo per indicare che il thread è stato ripristinato allo stato non modale.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A>: il ciclo di messaggi deve chiamare questo metodo per indicare che <xref:System.Windows.Interop.ComponentDispatcher> deve generare il <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> evento. <xref:System.Windows.Interop.ComponentDispatcher>non genererà <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle> se <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A> è `true`, ma i cicli di messaggi è possono scegliere di chiamare <xref:System.Windows.Interop.ComponentDispatcher.RaiseIdle%2A> anche se <xref:System.Windows.Interop.ComponentDispatcher> non può rispondere ai si trova nello stato modale.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A>: il ciclo di messaggi deve chiamare questo metodo per indicare che è disponibile un nuovo messaggio. Il valore restituito indica se un listener per un <xref:System.Windows.Interop.ComponentDispatcher> evento gestito il messaggio. Se <xref:System.Windows.Interop.ComponentDispatcher.RaiseThreadMessage%2A> restituisce `true` (gestito), il dispatcher non deve eseguire altre operazioni con il messaggio. Se il valore restituito è `false`, il dispatcher chiami il [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] funzione `TranslateMessage`, quindi chiamare `DispatchMessage`.  
  
## <a name="using-componentdispatcher-and-existing-message-handling"></a>Utilizzo di ComponentDispatcher e gestione del messaggio esistente  
 Di seguito è riportato un elenco di controllo <xref:System.Windows.Interop.ComponentDispatcher> membri che è necessario utilizzare inerente il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ciclo di messaggi.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.IsThreadModal%2A>: indica se l'applicazione è modale (ad esempio, un ciclo di messaggi modale è stato inserito). <xref:System.Windows.Interop.ComponentDispatcher>possibile rilevare questo stato perché la classe gestisce un conteggio di <xref:System.Windows.Interop.ComponentDispatcher.PushModal%2A> e <xref:System.Windows.Interop.ComponentDispatcher.PopModal%2A> chiamate dal ciclo di messaggi.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>e <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> eventi conformi alle regole standard per le chiamate del delegato. I delegati vengono richiamati nell'ordine specificato e tutti i delegati richiamati anche se il primo messaggio viene contrassegnato come gestito.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>: indica un tempo appropriato ed efficiente per periodi di inattività elaborazione (non sono presenti altri messaggi in sospeso per il thread). <xref:System.Windows.Interop.ComponentDispatcher.ThreadIdle>non essere generato se il thread è modale.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>: generato per tutti i messaggi che elabora il message pump.  
  
-   <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>: generato per tutti i messaggi che non sono stati gestiti durante <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage>.  
  
 Un messaggio viene considerato gestito se dopo il <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage> evento o <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> evento, il `handled` parametro passato per riferimento nei dati dell'evento è `true`. I gestori eventi devono ignorare il messaggio se `handled` è `true`, perché ciò significa che il messaggio è stato gestito prima da altro handler. Gestori eventi per entrambi gli eventi possono modificare il messaggio. Il dispatcher deve inviare il messaggio modificato e non subisce Modifica messaggio originale. <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage>viene recapitato a tutti i listener, ma l'architettura solo la finestra di primo livello contenente l'HWND in corrispondenza del quale i messaggi destinati devono richiamare il codice in risposta al messaggio.  
  
## <a name="how-hwndsource-treats-componentdispatcher-events"></a>Eventi ComponentDispatcher di HwndSource  
 Se il <xref:System.Windows.Interop.HwndSource> è una finestra di primo livello (nessun HWND padre), verrà registrato con <xref:System.Windows.Interop.ComponentDispatcher>. Se <xref:System.Windows.Interop.ComponentDispatcher.ThreadPreprocessMessage> viene generato, e se il messaggio è destinato il <xref:System.Windows.Interop.HwndSource> o finestre figlio, <xref:System.Windows.Interop.HwndSource> chiamate relativo <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TranslateAccelerator%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A>, <xref:System.Windows.Interop.IKeyboardInputSink.OnMnemonic%2A> sequenza sink di tastiera.  
  
 Se il <xref:System.Windows.Interop.HwndSource> non è una finestra di primo livello (dispone di un HWND padre), non sarà presente alcuna gestione. Solo la finestra di primo livello deve eseguire la gestione e si deve essere una finestra di primo livello con il supporto del sink di tastiera come parte di qualsiasi scenario di interoperabilità.  
  
 Se <xref:System.Windows.Interop.HwndHost.WndProc%2A> su un <xref:System.Windows.Interop.HwndSource> viene chiamato senza un metodo del sink di tastiera appropriato, l'applicazione riceverà gli eventi di tastiera di livello superiore, ad esempio <xref:System.Windows.UIElement.KeyDown>. Tuttavia, nessun metodo sink di tastiera viene chiamato, che consente di evitare un'utile keyboard features: modello di input, ad esempio il supporto di chiave di accesso. Questa situazione può verificarsi perché il ciclo di messaggi non ha notificato correttamente il thread pertinente sul <xref:System.Windows.Interop.ComponentDispatcher>, oppure perché l'HWND padre non ha richiamato le risposte del sink di tastiera corrette.  
  
 Un messaggio che passa al sink di tastiera potrebbe non essere inviato all'HWND se sono state aggiunte hook per tale messaggio tramite il <xref:System.Windows.Interop.HwndSource.AddHook%2A> metodo. Il messaggio potrebbe essere gestito in e non inviato a livello del message pump di `DispatchMessage` (funzione).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Interop.ComponentDispatcher>  
 <xref:System.Windows.Interop.IKeyboardInputSink>  
 [Interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 [Modello di threading](../../../../docs/framework/wpf/advanced/threading-model.md)  
 [Cenni preliminari sull'input](../../../../docs/framework/wpf/advanced/input-overview.md)
