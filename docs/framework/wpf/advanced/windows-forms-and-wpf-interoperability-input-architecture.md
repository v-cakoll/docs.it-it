---
title: Architettura di input di interoperabilità Windows Forms e WPF
titleSuffix: ''
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
ms.openlocfilehash: f79971ba13691ccc36420e39696b7b8a46e5ce0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745055"
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Architettura di input per l'interoperabilità tra Windows Form e WPF
L'interoperabilità tra il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] richiede che entrambe le tecnologie dispongano dell'elaborazione dell'input da tastiera appropriata. Questo argomento descrive il modo in cui queste tecnologie implementano l'elaborazione dei messaggi e della tastiera per abilitare l'interoperatività uniforme nelle applicazioni ibride.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
- Moduli e finestre di dialogo non modali  
  
- Elaborazione della tastiera e del messaggio WindowsFormsHost  
  
- Elaborazione di messaggi e tastiera ElementHost  
  
## <a name="modeless-forms-and-dialog-boxes"></a>Moduli e finestre di dialogo non modali  
 Chiamare il metodo <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> sull'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> per aprire un form o una finestra di dialogo non modale da un'applicazione basata su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Chiamare il metodo <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> sul controllo <xref:System.Windows.Forms.Integration.ElementHost> per aprire una pagina di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non modale in un'applicazione basata su [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>Elaborazione della tastiera e del messaggio WindowsFormsHost  
 Quando è ospitato da un'applicazione basata su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] l'elaborazione di tastiera e messaggi è costituita dai seguenti elementi:  
  
- La classe <xref:System.Windows.Forms.Integration.WindowsFormsHost> acquisisce i messaggi dal ciclo di messaggi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], implementato dalla classe <xref:System.Windows.Interop.ComponentDispatcher>.  
  
- La classe <xref:System.Windows.Forms.Integration.WindowsFormsHost> crea un ciclo di messaggi [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] surrogati per garantire che si verifichi l'elaborazione ordinaria di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tastiera.  
  
- La classe <xref:System.Windows.Forms.Integration.WindowsFormsHost> implementa l'interfaccia <xref:System.Windows.Interop.IKeyboardInputSink> per coordinare la gestione dello stato attivo con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- I controlli <xref:System.Windows.Forms.Integration.WindowsFormsHost> si registrano e avviano i cicli di messaggi.  
  
 Le sezioni seguenti descrivono in modo più dettagliato queste parti del processo.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>Acquisizione di messaggi dal ciclo di messaggi WPF  
 La classe <xref:System.Windows.Interop.ComponentDispatcher> implementa la gestione del ciclo di messaggi per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La classe <xref:System.Windows.Interop.ComponentDispatcher> fornisce hook per consentire ai client esterni di filtrare i messaggi prima di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] li elabora.  
  
 L'implementazione dell'interoperatività gestisce l'evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>, che consente ai controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] di elaborare i messaggi prima di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli.  
  
### <a name="surrogate-windows-forms-message-loop"></a>Ciclo di messaggi Windows Forms surrogati  
 Per impostazione predefinita, la classe <xref:System.Windows.Forms.Application?displayProperty=nameWithType> contiene il ciclo di messaggi primario per le applicazioni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Durante l'interoperatività, il ciclo di messaggi [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non elabora i messaggi. Pertanto, è necessario riprodurre questa logica. Il gestore per l'evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> esegue i passaggi seguenti:  
  
1. Filtra il messaggio usando l'interfaccia <xref:System.Windows.Forms.IMessageFilter>.  
  
2. Chiama il metodo <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType>.  
  
3. Converte e invia il messaggio, se necessario.  
  
4. Passa il messaggio al controllo di hosting, se nessun altro controllo elabora il messaggio.  
  
### <a name="ikeyboardinputsink-implementation"></a>Implementazione di IKeyboardInputSink  
 Il ciclo di messaggi surrogati gestisce la gestione della tastiera. Pertanto, il <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> metodo è l'unico membro <xref:System.Windows.Interop.IKeyboardInputSink> che richiede un'implementazione nella classe <xref:System.Windows.Forms.Integration.WindowsFormsHost>.  
  
 Per impostazione predefinita, la classe <xref:System.Windows.Interop.HwndHost> restituisce `false` per la relativa implementazione di <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A>. In questo modo si impedisce la tabulazione da un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 L'implementazione <xref:System.Windows.Forms.Integration.WindowsFormsHost> del metodo <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> esegue i passaggi seguenti:  
  
1. Trova il primo o l'ultimo controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] contenuto dal controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> e che può ricevere lo stato attivo. La scelta del controllo dipende dalle informazioni di attraversamento.  
  
2. Imposta lo stato attivo sul controllo e restituisce `true`.  
  
3. Se nessun controllo può ricevere lo stato attivo, restituisce `false`.  
  
### <a name="windowsformshost-registration"></a>Registrazione WindowsFormsHost  
 Quando viene creato l'handle della finestra per un controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>, il controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> chiama un metodo statico interno che registra la sua presenza per il ciclo di messaggi.  
  
 Durante la registrazione, il controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> esamina il ciclo di messaggi. Se il ciclo di messaggi non è stato avviato, viene creato il gestore dell'evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>. Il ciclo di messaggi viene considerato in esecuzione quando viene collegato il gestore dell'evento <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType>.  
  
 Quando l'handle della finestra viene eliminato definitivamente, il controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> si rimuove dalla registrazione.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>Elaborazione di messaggi e tastiera ElementHost  
 Quando è ospitato da un'applicazione [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] l'elaborazione della tastiera e del messaggio è costituita dagli elementi seguenti:  
  
- implementazioni dell'interfaccia <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>e <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
- Tabulazione e tasti di direzione.  
  
- Chiavi di comando e chiavi della finestra di dialogo.  
  
- elaborazione dell'acceleratore [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
 Le sezioni seguenti descrivono queste parti in modo più dettagliato.  
  
### <a name="interface-implementations"></a>Implementazioni di interfacce  
 In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], i messaggi della tastiera vengono instradati all'handle della finestra del controllo con lo stato attivo. Nel controllo <xref:System.Windows.Forms.Integration.ElementHost> questi messaggi vengono instradati all'elemento ospitato. A tale scopo, il controllo <xref:System.Windows.Forms.Integration.ElementHost> fornisce un'istanza di <xref:System.Windows.Interop.HwndSource>. Se il controllo <xref:System.Windows.Forms.Integration.ElementHost> dispone dello stato attivo, l'istanza <xref:System.Windows.Interop.HwndSource> instrada la maggior parte degli input da tastiera, in modo che possa essere elaborata dalla classe <xref:System.Windows.Input.InputManager> di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 La classe <xref:System.Windows.Interop.HwndSource> implementa le interfacce <xref:System.Windows.Interop.IKeyboardInputSink> e <xref:System.Windows.Interop.IKeyboardInputSite>.  
  
 L'interoperatività della tastiera si basa sull'implementazione del metodo <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> per gestire il tasto TAB e l'input del tasto di direzione che sposta lo stato attivo fuori dagli elementi ospitati.  
  
### <a name="tabbing-and-arrow-keys"></a>Tabulazione e tasti di direzione  
 Viene eseguito il mapping della logica di selezione [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ai metodi <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> e <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> per implementare la navigazione tra le schede e i tasti freccia. Eseguendo l'override del metodo <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> viene eseguito questo mapping.  
  
### <a name="command-keys-and-dialog-box-keys"></a>Chiavi di comando e chiavi della finestra di dialogo  
 Per fornire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la prima opportunità per elaborare le chiavi di comando e le chiavi di dialogo, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] la pre-elaborazione dei comandi è connessa al metodo <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>. L'override del metodo <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> connette le due tecnologie.  
  
 Con il metodo <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A>, gli elementi ospitati sono in grado di gestire qualsiasi messaggio chiave, ad esempio WM_KEYDOWN, WM_KEYUP, WM_SYSKEYDOWN o WM_SYSKEYUP, inclusi i tasti di comando, ad esempio TAB, ENTER, ESC e i tasti di direzione. Se un messaggio chiave non viene gestito, viene inviato il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] gerarchia predecessore per la gestione.  
  
### <a name="accelerator-processing"></a>Elaborazione acceleratore  
 Per elaborare correttamente i tasti di scelta rapida, è necessario che [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] elaborazione dell'acceleratore sia connessa alla classe di <xref:System.Windows.Input.AccessKeyManager> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Inoltre, tutti i messaggi di WM_CHAR devono essere indirizzati correttamente agli elementi ospitati.  
  
 Poiché l'implementazione <xref:System.Windows.Interop.HwndSource> predefinita del metodo <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> restituisce `false`, WM_CHAR i messaggi vengono elaborati utilizzando la logica seguente:  
  
- Viene eseguito l'override del metodo <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> per assicurarsi che tutti i messaggi di WM_CHAR vengano inviati agli elementi ospitati.  
  
- Se viene premuto il tasto ALT, il messaggio viene WM_SYSCHAR. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non esegue la pre-elaborazione di questo messaggio tramite il metodo <xref:System.Windows.Forms.Control.IsInputChar%2A>. Pertanto, viene eseguito l'override del metodo <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> per eseguire una query sul [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> per un tasto di scelta rapida registrato. Se viene trovato un acceleratore registrato, <xref:System.Windows.Input.AccessKeyManager> lo elabora.  
  
- Se il tasto ALT non viene premuto, la classe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> elabora l'input non gestito. Se l'input è un acceleratore, il <xref:System.Windows.Input.AccessKeyManager> lo elabora. L'evento <xref:System.Windows.Input.InputManager.PostProcessInput> viene gestito per WM_CHAR messaggi non elaborati.  
  
 Quando l'utente preme il tasto ALT, i segnali visivi Accelerator vengono visualizzati nell'intero form. Per supportare questo comportamento, tutti i controlli <xref:System.Windows.Forms.Integration.ElementHost> sul form attivo ricevono WM_SYSKEYDOWN messaggi, indipendentemente dal controllo con lo stato attivo.  
  
 I messaggi vengono inviati solo ai controlli <xref:System.Windows.Forms.Integration.ElementHost> nel modulo attivo.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
