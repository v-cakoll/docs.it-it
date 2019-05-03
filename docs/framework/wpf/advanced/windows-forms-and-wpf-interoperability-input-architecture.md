---
title: Architettura di input per l'interoperabilità tra Windows Form e WPF
ms.date: 03/30/2017
helpviewer_keywords:
- input architecture [WPF interoperability]
- messages [WPF]
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- modeless forms [WPF]
- ElementHost keyboard and messages [WPF]
- keyboard interoperation [WPF]
- WindowsFormsHost keyboard and messages [WPF]
- modeless dialog boxes [WPF]
ms.assetid: 0eb6f137-f088-4c5e-9e37-f96afd28f235
ms.openlocfilehash: 2df754c0c47ea99c0892e0b9365da5589f2eab76
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007097"
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Architettura di input per l'interoperabilità tra Windows Form e WPF
Interoperatività tra il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] necessario dispongano di entrambe le tecnologie dell'elaborazione dell'input da tastiera appropriato. In questo argomento viene descritto come tali tecnologie implementano da tastiera e con elaborazione dei messaggi per consentire l'interoperabilità senza problemi in applicazioni ibride.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
- Form non modali e le finestre di dialogo  
  
- WindowsFormsHost tastiera e l'elaborazione dei messaggi  
  
- Tastiera ElementHost e l'elaborazione dei messaggi  
  
## <a name="modeless-forms-and-dialog-boxes"></a>Form non modali e le finestre di dialogo  
 Chiamare il <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> metodo sul <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento per aprire una finestra di form o finestra di dialogo non modale da un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su.  
  
 Chiamare il <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> metodo sul <xref:System.Windows.Forms.Integration.ElementHost> controllo per aprire un non modale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nella pagina un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-applicazione basata su.  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>WindowsFormsHost tastiera e l'elaborazione dei messaggi  
 Quando ospitate da un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione, basata su [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tastiera e il messaggio di elaborazione è costituita da quanto segue:  
  
- Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> classe acquisisce i messaggi dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ciclo di messaggi viene implementata dal <xref:System.Windows.Interop.ComponentDispatcher> classe.  
  
- Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> classe crea un surrogato [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] loop di messaggi per verificare che tale ordinario [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] viene eseguita l'elaborazione della tastiera.  
  
- Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> classe implementa le <xref:System.Windows.Interop.IKeyboardInputSink> interface per coordinare la gestione dello stato attivo con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controlli effettuano la registrazione e avviare i cicli di messaggi.  
  
 Le sezioni seguenti descrivono queste parti del processo in modo più dettagliato.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>Acquisizione di messaggi dal ciclo di messaggi WPF  
 Il <xref:System.Windows.Interop.ComponentDispatcher> classe implementa la gestione del ciclo di messaggi per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il <xref:System.Windows.Interop.ComponentDispatcher> classe fornisce hook per consentire ai client esterni per filtrare i messaggi prima [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] li elabora.  
  
 Gli handle di interoperatività implementazione di <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> evento, che consente [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli per elaborare i messaggi prima [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli.  
  
### <a name="surrogate-windows-forms-message-loop"></a>Ciclo di messaggi di surrogato Windows Form  
 Per impostazione predefinita, il <xref:System.Windows.Forms.Application?displayProperty=nameWithType> classe contiene il ciclo di messaggi principale per [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] applicazioni. Durante l'interoperabilità, la [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] messaggio ciclo non elabora i messaggi. Pertanto, questa logica deve essere riprodotti. Il gestore per il <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> evento esegue i passaggi seguenti:  
  
1. Filtra il messaggio usando la <xref:System.Windows.Forms.IMessageFilter> interfaccia.  
  
2. Le chiamate di <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> (metodo).  
  
3. Converte e invia il messaggio, se necessario.  
  
4. Passa il messaggio al controllo host, se nessun altro controllo elabora il messaggio.  
  
### <a name="ikeyboardinputsink-implementation"></a>Implementazione IKeyboardInputSink  
 Il ciclo di messaggi di surrogati gestisce la gestione della tastiera. Pertanto, il <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> metodo è l'unico <xref:System.Windows.Interop.IKeyboardInputSink> membro che richiede un'implementazione nel <xref:System.Windows.Forms.Integration.WindowsFormsHost> classe.  
  
 Per impostazione predefinita, il <xref:System.Windows.Interop.HwndHost> classe restituisce `false` per la relativa <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> implementazione. Ciò impedisce la tabulazione da un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il controllo a un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.  
  
 Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> implementazione del <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> metodo esegue i passaggi seguenti:  
  
1. Trova il primo o ultimo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo contenuta il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo e che può ricevere lo stato attivo. La scelta del controllo dipende dalle informazioni di attraversamento.  
  
2. Imposta lo stato attivo al controllo e restituisce `true`.  
  
3. Se nessun controllo può ricevere lo stato attivo, restituisce `false`.  
  
### <a name="windowsformshost-registration"></a>Registrazione WindowsFormsHost  
 Quando l'handle della finestra per un <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo viene creato, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo chiama un metodo statico interno che registra la propria presenza per il ciclo di messaggi.  
  
 Durante la registrazione di <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo esamina il ciclo di messaggi. Se il ciclo di messaggi non è stato avviato, il <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> il gestore dell'evento. Il ciclo di messaggi è considerato in esecuzione quando il <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> è associato il gestore eventi.  
  
 Quando viene eliminato definitivamente l'handle di finestra, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo rimosso dalla registrazione.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>Tastiera ElementHost e l'elaborazione dei messaggi  
 Quando ospitate da un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] dell'applicazione, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tastiera e il messaggio di elaborazione è costituita da quanto segue:  
  
- <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>, e <xref:System.Windows.Interop.IKeyboardInputSite> implementazioni di interfacce.  
  
- Tasti freccia e TAB.  
  
- Comando chiavi e chiavi di finestra di dialogo.  
  
- [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] elaborazione di tasti di scelta rapida.  
  
 Le sezioni seguenti descrivono queste parti in modo più dettagliato.  
  
### <a name="interface-implementations"></a>Implementazioni dell'interfaccia  
 In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], vengono instradati i messaggi della tastiera all'handle della finestra del controllo che ha lo stato attivo. Nel <xref:System.Windows.Forms.Integration.ElementHost> (controllo), questi messaggi vengono instradati all'elemento ospitato. A tale scopo, il <xref:System.Windows.Forms.Integration.ElementHost> controllo fornisce un' <xref:System.Windows.Interop.HwndSource> istanza. Se il <xref:System.Windows.Forms.Integration.ElementHost> controllo ha lo stato attivo, il <xref:System.Windows.Interop.HwndSource> istanza instrada la maggior parte dei tasti di input in modo che possa essere elaborato dalle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> classe.  
  
 Il <xref:System.Windows.Interop.HwndSource> classe implementa le <xref:System.Windows.Interop.IKeyboardInputSink> e <xref:System.Windows.Interop.IKeyboardInputSite> interfacce.  
  
 Interoperabilità da tastiera si basa sull'implementazione di <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> metodo freccia e tasto TAB di handle di chiave input che viene spostato all'esterno di elementi di hosting.  
  
### <a name="tabbing-and-arrow-keys"></a>Tasti freccia e TAB  
 Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] viene eseguito il mapping per la logica di selezione per il <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> e <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> metodi da implementare freccia e TAB chiave navigazione. Si esegue l'override di <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> metodo esegue il mapping.  
  
### <a name="command-keys-and-dialog-box-keys"></a>Le chiavi di comandi e finestre di dialogo  
 Per concedere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la prima opportunità per l'elaborazione comando chiavi e chiavi di finestra di dialogo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] comando pre-elaborazione è connesso al <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> (metodo). Si esegue l'override di <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> metodo connette le due tecnologie.  
  
 Con la <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> metodo, gli elementi di hosting possono gestire qualsiasi messaggio chiave, ad esempio WM_KEYUP, di WM_KEYDOWN, WM_SYSKEYDOWN o WM_SYSKEYUP, incluse le chiavi di comando, ad esempio, invio, ESC, tasti freccia e TAB. Se non viene gestito un messaggio relativo ai tasti, viene inviato il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] gerarchia predecessore per la gestione.  
  
### <a name="accelerator-processing"></a>Elaborazione di tasti di scelta rapida  
 Per elaborare correttamente gli acceleratori [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] elaborazione di tasti di scelta rapida deve essere connessa al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> classe. Inoltre, tutti i messaggi WM_CHAR devono essere indirizzati correttamente agli elementi ospitati.  
  
 Poiché il valore predefinito <xref:System.Windows.Interop.HwndSource> implementazione del <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> restituzione del metodo `false`, vengono elaborati messaggi WM_CHAR adottando la logica seguente:  
  
- Il <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> è sottoposto a override per garantire che tutti i messaggi WM_CHAR vengono inoltrati a elementi di hosting.  
  
- Se viene premuto il tasto ALT, il messaggio è WM_SYSCHAR. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non elabora il messaggio tramite la <xref:System.Windows.Forms.Control.IsInputChar%2A> (metodo). Pertanto, il <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> è sottoposto a override a query i [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> per un tasto di scelta rapida registrato. Se viene trovato un tasto di scelta rapida registrato, <xref:System.Windows.Input.AccessKeyManager> lo elabora.  
  
- Se non viene premuto il tasto ALT, il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> classe elabora l'input non gestita. Se l'input è un acceleratore, il <xref:System.Windows.Input.AccessKeyManager> lo elabora. Il <xref:System.Windows.Input.InputManager.PostProcessInput> evento viene gestito per i messaggi WM_CHAR che non sono stati elaborati.  
  
 Quando l'utente preme il tasto ALT, vengono visualizzati segnali visivi di tasti di scelta rapida in tutto il modulo. Per supportare questo comportamento, tutti <xref:System.Windows.Forms.Integration.ElementHost> controlli nel form attivo ricevano WM_SYSKEYDOWN, indipendentemente da quale controllo ha lo stato attivo.  
  
 I messaggi vengono inviati solo a <xref:System.Windows.Forms.Integration.ElementHost> controlli nel form attivo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
