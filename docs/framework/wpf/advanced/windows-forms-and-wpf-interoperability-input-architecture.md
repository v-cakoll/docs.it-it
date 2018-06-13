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
ms.openlocfilehash: 250f34e3e5420a613bc7b1035c62af90665e71ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549059"
---
# <a name="windows-forms-and-wpf-interoperability-input-architecture"></a>Architettura di input per l'interoperabilità tra Windows Form e WPF
Interazione tra il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] richiede che entrambe le tecnologie dispongano dell'elaborazione dell'input di tastiera appropriato. In questo argomento viene descritto come queste tecnologie implementano tastiera e l'elaborazione dei messaggi per consentire l'interoperabilità nelle applicazioni ibride.  
  
 In questo argomento sono contenute le seguenti sottosezioni:  
  
-   Finestre di dialogo e i moduli non modali  
  
-   Tastiera WindowsFormsHost ed elaborazione dei messaggi  
  
-   Tastiera ElementHost ed elaborazione dei messaggi  
  
## <a name="modeless-forms-and-dialog-boxes"></a>Finestre di dialogo e i moduli non modali  
 Chiamare il <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A> metodo il <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento per aprire una casella del form o finestra di dialogo non modale da un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione basata su.  
  
 Chiamare il <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A> metodo il <xref:System.Windows.Forms.Integration.ElementHost> controllo per aprire un non modale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pagina un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-applicazione basata su.  
  
## <a name="windowsformshost-keyboard-and-message-processing"></a>Tastiera WindowsFormsHost ed elaborazione dei messaggi  
 Quando sono ospitati da un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-applicazione, basata su [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tastiera e il messaggio di elaborazione è costituita da quanto segue:  
  
-   Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> classe acquisisce i messaggi dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ciclo di messaggi, viene implementata dalla <xref:System.Windows.Interop.ComponentDispatcher> classe.  
  
-   Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> classe crea un surrogato [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ciclo di messaggi per garantire che ordinario [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] si verifica l'elaborazione della tastiera.  
  
-   Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> classe implementa il <xref:System.Windows.Interop.IKeyboardInputSink> interfaccia per coordinare la gestione dello stato attivo con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> effettuano la registrazione di controlli e avviare i relativi cicli di messaggi.  
  
 Le sezioni seguenti descrivono queste parti del processo in maggior dettaglio.  
  
### <a name="acquiring-messages-from-the-wpf-message-loop"></a>Acquisizione di messaggi dal ciclo di messaggi WPF  
 Il <xref:System.Windows.Interop.ComponentDispatcher> classe implementa la gestione del ciclo di messaggi per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il <xref:System.Windows.Interop.ComponentDispatcher> classe fornisce hook per consentire ai client esterni per filtrare i messaggi prima [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] li elabora.  
  
 Gli handle di implementazione interoperabilità di <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> evento, che consente di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli per elaborare i messaggi prima [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli.  
  
### <a name="surrogate-windows-forms-message-loop"></a>Ciclo di messaggi surrogato Windows Form  
 Per impostazione predefinita, il <xref:System.Windows.Forms.Application?displayProperty=nameWithType> classe contiene il ciclo di messaggi primario per [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] applicazioni. Durante l'interoperabilità, il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] messaggio ciclo non elabora i messaggi. Pertanto, questa logica deve essere riprodotti. Il gestore per il <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> evento esegue i passaggi seguenti:  
  
1.  Filtro del messaggio tramite il <xref:System.Windows.Forms.IMessageFilter> interfaccia.  
  
2.  Chiamate di <xref:System.Windows.Forms.Control.PreProcessMessage%2A?displayProperty=nameWithType> metodo.  
  
3.  Converte e invia il messaggio, se necessario.  
  
4.  Passa il messaggio al controllo host, se nessun altro controllo di elaborare il messaggio.  
  
### <a name="ikeyboardinputsink-implementation"></a>Implementazione IKeyboardInputSink  
 Il ciclo di messaggi surrogato gestisce la gestione della tastiera. Pertanto, il <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> è l'unico metodo <xref:System.Windows.Interop.IKeyboardInputSink> membro che richiede un'implementazione nel <xref:System.Windows.Forms.Integration.WindowsFormsHost> classe.  
  
 Per impostazione predefinita, il <xref:System.Windows.Interop.HwndHost> classe restituisce `false` per relativo <xref:System.Windows.Interop.HwndHost.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> implementazione. In questo modo si impedisce la tabulazione da un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il controllo a un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo.  
  
 Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> implementazione del <xref:System.Windows.Interop.IKeyboardInputSink.TabInto%2A?displayProperty=nameWithType> metodo esegue i passaggi seguenti:  
  
1.  Trova la prima o nell'ultima [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo che è contenuto il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo e che può ricevere lo stato attivo. La scelta del controllo dipende dalle informazioni di attraversamento.  
  
2.  Imposta lo stato attivo al controllo e restituisce `true`.  
  
3.  Se nessun controllo può ricevere lo stato attivo, restituisce `false`.  
  
### <a name="windowsformshost-registration"></a>Registrazione di WindowsFormsHost  
 Quando l'handle della finestra per un <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo viene creato, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo chiama un metodo statico interno che registra la propria presenza per il ciclo di messaggi.  
  
 Durante la registrazione di <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo esamina il ciclo di messaggi. Se il ciclo di messaggi non è stato avviato, il <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> il gestore dell'evento. Il ciclo di messaggi è considerato in esecuzione quando il <xref:System.Windows.Interop.ComponentDispatcher.ThreadFilterMessage?displayProperty=nameWithType> è associato il gestore di evento.  
  
 Quando viene eliminato definitivamente l'handle di finestra, il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo rimosso dalla registrazione.  
  
## <a name="elementhost-keyboard-and-message-processing"></a>Tastiera ElementHost ed elaborazione dei messaggi  
 Quando sono ospitati da un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] applicazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tastiera e il messaggio di elaborazione è costituita da quanto segue:  
  
-   <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.IKeyboardInputSink>, e <xref:System.Windows.Interop.IKeyboardInputSite> implementazioni di interfacce.  
  
-   Tasti freccia e TAB.  
  
-   Tasti di comando e finestre di dialogo.  
  
-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] elaborazione di tasti di scelta rapida.  
  
 Le sezioni seguenti descrivono queste parti in modo più dettagliato.  
  
### <a name="interface-implementations"></a>Implementazioni di interfaccia  
 In [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], i messaggi della tastiera vengono indirizzati all'handle della finestra del controllo che ha lo stato attivo. Nel <xref:System.Windows.Forms.Integration.ElementHost> (controllo), questi messaggi vengono indirizzati all'elemento ospitato. A tale scopo, il <xref:System.Windows.Forms.Integration.ElementHost> controllo fornisce un' <xref:System.Windows.Interop.HwndSource> istanza. Se il <xref:System.Windows.Forms.Integration.ElementHost> controllo ha lo stato attivo, il <xref:System.Windows.Interop.HwndSource> istanza indirizza la maggior parte dei tasti di input in modo che possa essere elaborato dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> classe.  
  
 Il <xref:System.Windows.Interop.HwndSource> classe implementa il <xref:System.Windows.Interop.IKeyboardInputSink> e <xref:System.Windows.Interop.IKeyboardInputSite> interfacce.  
  
 Interoperabilità della tastiera si basa sull'implementazione di <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> metodo freccia e tasto TAB di handle di chiave di input che consente di spostare lo stato attivo dagli elementi ospitati.  
  
### <a name="tabbing-and-arrow-keys"></a>TAB e i tasti di direzione  
 Il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] la logica di selezione viene eseguito il mapping per il <xref:System.Windows.Interop.HwndSource.System%23Windows%23Interop%23IKeyboardInputSink%23TabInto%2A> e <xref:System.Windows.Interop.IKeyboardInputSite.OnNoMoreTabStops%2A> metodi da implementare freccia e TAB chiave di navigazione. Si esegue l'override di <xref:System.Windows.Forms.Integration.ElementHost.Select%2A> metodo esegue il mapping.  
  
### <a name="command-keys-and-dialog-box-keys"></a>Tasti di comando e finestre di dialogo  
 Per concedere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la prima opportunità per elaborare le chiavi di comando e le chiavi di finestra di dialogo, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] comando pre-elaborazione è connesso il <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> (metodo). Si esegue l'override di <xref:System.Windows.Forms.Control.ProcessCmdKey%2A?displayProperty=nameWithType> metodo connette le due tecnologie.  
  
 Con il <xref:System.Windows.Interop.IKeyboardInputSink.TranslateAccelerator%2A> metodo, gli elementi di hosting possono gestire qualsiasi messaggio chiave, ad esempio WM_KEYUP, il messaggio WM_KEYDOWN, WM_SYSKEYDOWN o WM_SYSKEYUP, inclusi i tasti di comando, ad esempio, invio, ESC, freccia e TAB. Se un messaggio chiave non viene gestito, viene inviato il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] gerarchia predecessore per la gestione.  
  
### <a name="accelerator-processing"></a>Elaborazione di tasti di scelta rapida  
 Per elaborare correttamente, i tasti di scelta rapida [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] l'elaborazione di tasti di scelta rapida deve essere connessa al [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> classe. Inoltre, tutti i messaggi WM_CHAR devono essere indirizzati correttamente a elementi ospitati.  
  
 Poiché il valore predefinito <xref:System.Windows.Interop.HwndSource> implementazione del <xref:System.Windows.Interop.IKeyboardInputSink.TranslateChar%2A> restituisce `false`, messaggi WM_CHAR vengono elaborati utilizzando la logica seguente:  
  
-   Il <xref:System.Windows.Forms.Control.IsInputChar%2A?displayProperty=nameWithType> viene eseguito l'override di metodo per garantire che tutti i messaggi WM_CHAR vengono inoltrati agli elementi ospitati.  
  
-   Se viene premuto il tasto ALT, il messaggio è WM_SYSCHAR. [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non elabora il messaggio tramite la <xref:System.Windows.Forms.Control.IsInputChar%2A> metodo. Pertanto, il <xref:System.Windows.Forms.Control.ProcessMnemonic%2A> metodo sottoposto a override a query il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.AccessKeyManager> per un acceleratore registrato. Se viene trovato un acceleratore registrato, <xref:System.Windows.Input.AccessKeyManager> elabora.  
  
-   Se non viene premuto il tasto ALT, il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.InputManager> classe elabora l'input non gestito. Se l'input è un acceleratore, il <xref:System.Windows.Input.AccessKeyManager> elabora. Il <xref:System.Windows.Input.InputManager.PostProcessInput> per i messaggi che sono stati elaborati non WM_CHAR viene gestito l'evento.  
  
 Quando l'utente preme il tasto ALT, segnali visivi tasti di scelta rapida vengono visualizzati nel form intero. Per supportare questo comportamento, tutti <xref:System.Windows.Forms.Integration.ElementHost> controlli nel form attivo ricevono messaggi WM_SYSKEYDOWN, indipendentemente da quale controllo è attivo.  
  
 I messaggi vengono inviati solo a <xref:System.Windows.Forms.Integration.ElementHost> controlli nel form attivo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.EnableWindowsFormsInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost.EnableModelessKeyboardInterop%2A>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [Interoperatività di WPF e Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
