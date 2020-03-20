---
title: Interoperabilità di WPF e Windows FormWPF and Windows Forms interop
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 76d1e97c92946267aa1217f52c93594fb63d20de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187155"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Interoperatività di WPF e Windows Form
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]e Windows Form presentano due diverse architetture per la creazione di interfacce di applicazioni. Lo <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> spazio dei nomi fornisce classi che abilitano scenari di interoperabilità comuni. Le due classi chiave che <xref:System.Windows.Forms.Integration.WindowsFormsHost> implementano le funzionalità di interoperabilità sono e <xref:System.Windows.Forms.Integration.ElementHost>. Questo argomento descrive gli scenari di interoperatività supportati e indica quelli non supportati.  
  
> [!NOTE]
> Particolare attenzione viene dedicata allo scenario del *controllo ibrido*. Un controllo ibrido è costituito da un controllo di una tecnologia annidato in un controllo di un'altra tecnologia. Questa situazione viene anche definita *interoperatività annidata*. Un *controllo ibrido multilivello* prevede più di un livello di annidamento dei controlli ibridi. Un esempio di un'interazione annidata a più [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] livelli è un controllo Windows Form che contiene un controllo, che contiene un altro controllo Windows Form.An example of a multilevel nested interoperation is a Windows Forms control that contains a control, which contains another Windows Forms control. I controlli ibridi multilivello non sono supportati.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>
## <a name="hosting-windows-forms-controls-in-wpf"></a>Hosting di controlli Windows Form in WPF  
 I seguenti scenari di interoperabilità sono supportati quando un controllo ospita un controllo Windows Form:The following interoperation scenarios are supported when a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control hosts a Windows Forms control:  
  
- Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo può ospitare uno o più controlli Windows Form usando XAML.  
  
- Può ospitare uno o più controlli Windows Form utilizzando il codice.  
  
- Può ospitare controlli contenitore Windows Form che contengono altri controlli Windows Form.It may host Windows Forms container controls that contain other Windows Forms controls.  
  
- Può ospitare un form master/dettaglio con un master e dettagli di Windows Form.It may host a master/detail form with a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] master and Windows Forms details.  
  
- Può ospitare un form master/dettaglio con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un master di Windows Form e dettagli.  
  
- Può ospitare uno o più controlli ActiveX.  
  
- Può ospitare uno o più controlli compositi.  
  
- Può ospitare controlli ibridi tramite [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
- Può ospitare controlli ibridi tramite il codice.  
  
### <a name="layout-support"></a>Supporto del layout  
 Nell'elenco seguente vengono descritte <xref:System.Windows.Forms.Integration.WindowsFormsHost> le limitazioni note quando l'elemento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tenta di integrare il relativo controllo Windows Form ospitato nel sistema di layout.  
  
- In alcuni casi, i controlli Windows Form non possono essere ridimensionati o possono essere ridimensionati solo a dimensioni specifiche. Ad esempio, un <xref:System.Windows.Forms.ComboBox> controllo Windows Form supporta solo una singola altezza, definita dalla dimensione del carattere del controllo. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un layout dinamico, che presuppone che gli <xref:System.Windows.Forms.ComboBox> elementi possano estendersi verticalmente, un controllo ospitato non si estenderà come previsto.  
  
- I controlli Windows Form non possono essere ruotati o inclinati. Ad esempio, quando si ruota l'interfaccia utente di 90 gradi, i controlli Windows Form ospitati manterranno la posizione eretta.  
  
- Nella maggior parte dei casi, i controlli Windows Form non supportano il ridimensionamento proporzionale. Anche se le dimensioni complessive del controllo vengono ridimensionate, i controlli figlio e gli elementi componente del controllo potrebbero non venire ridimensionati come previsto. Questa limitazione dipende da quanto bene ogni controllo Windows Form supporta il ridimensionamento.  
  
- In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è possibile modificare l'ordine z degli elementi per controllare il comportamento di sovrapposizione. Un controllo Windows Form ospitato viene disegnato in un HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] separato, pertanto viene sempre disegnato sopra gli elementi.  
  
- I controlli Windows Form supportano la scalabilità automatica in base alla dimensione del carattere. In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], modificando le dimensioni del carattere non si ridimensiona l'intero layout, anche se è possibile che vengano ridimensionati dinamicamente singoli elementi.  
  
### <a name="ambient-properties"></a>Proprietà di ambiente  
 Alcune delle proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di ambiente dei controlli hanno equivalenti di Windows Form.Some of the ambient properties of controls have Windows Forms equivalents. Queste proprietà di ambiente vengono propagate ai controlli Windows <xref:System.Windows.Forms.Integration.WindowsFormsHost> Form ospitati ed esposte come proprietà pubbliche nel controllo. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo converte ogni proprietà di ambiente nel relativo equivalente di Windows Form.The control translates each [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ambient property into its Windows Forms equivalent.  
  
 Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamento  
 La tabella seguente descrive il comportamento dell'interoperatività.  
  
|Comportamento|Supportato|Non supportate|  
|--------------|---------------|-------------------|  
|Trasparenza|Il rendering dei controlli Windows Form supporta la trasparenza. Lo sfondo del [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo padre può diventare lo sfondo dei controlli Windows Form ospitati.|Alcuni controlli Windows Form non supportano la trasparenza. Ad esempio, <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.ComboBox> i controlli e non saranno [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]trasparenti quando sono ospitati da .|  
|Tabulazione|L'ordine di tabulazione per i controlli Windows Form ospitati è lo stesso di quando tali controlli sono ospitati in un'applicazione basata su Windows Form.Tab order for hosted Windows Forms controls is the same as when those controls are hosted in a Windows Forms-based application.<br /><br /> La tabulazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] da un controllo a un controllo Windows Form con il tasto TAB e i tasti MAIUSC e TAB funziona come di consueto.<br /><br /> Controlli Windows Form <xref:System.Windows.Forms.Control.TabStop%2A> che hanno `false` un valore della proprietà di non ricevono lo stato attivo quando l'utente scorre i controlli.<br /><br /> - <xref:System.Windows.Forms.Integration.WindowsFormsHost> Ogni controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> ha un valore, che determina quando tale controllo riceverà lo stato attivo.- Each control has a value, which determines when that <xref:System.Windows.Forms.Integration.WindowsFormsHost> control will receive focus.<br />- I controlli Windows Form <xref:System.Windows.Forms.Integration.WindowsFormsHost> contenuti all'interno <xref:System.Windows.Forms.Control.TabIndex%2A> di un contenitore seguono l'ordine specificato dalla proprietà . La tabulazione dall'ultimo indice di tabulazione assegna lo stato attivo al successivo controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se presente. Se non esiste [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nessun altro controllo attivabile, la tabulazione torna al primo controllo Windows Form nell'ordine di tabulazione.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>i valori per <xref:System.Windows.Forms.Integration.WindowsFormsHost> i controlli all'interno di sono <xref:System.Windows.Forms.Integration.WindowsFormsHost> relativi ai controlli Windows Form di pari livello contenuti nel controllo.<br />- La tabulazione rispetta il comportamento specifico del controllo. Ad esempio, premendo il <xref:System.Windows.Forms.TextBox> tasto TAB <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> in un `true` controllo che dispone di un valore di proprietà di consente di immettere una scheda nella casella di testo anziché spostare lo stato attivo.|Non applicabile.|  
|Navigazione con i tasti di direzione|- Navigazione con i <xref:System.Windows.Forms.Integration.WindowsFormsHost> tasti freccia nel controllo è lo stesso di un normale controllo contenitore Windows Form: i tasti freccia su e freccia SINISTRA selezionare il controllo precedente e i tasti freccia giù e freccia DESTRA selezionare il controllo successivo.<br />- I tasti FRECCIA SU e FRECCIA SINISTRA del <xref:System.Windows.Forms.Integration.WindowsFormsHost> primo controllo contenuto nel controllo eseguono la stessa azione della scelta rapida da tastiera MAIUSC e TAB. Se è presente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un controllo attivabile, lo stato attivo si sposta all'esterno del <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo. Questo comportamento è diverso <xref:System.Windows.Forms.ContainerControl> dal comportamento standard in quanto non viene eseguito alcun wrapping all'ultimo controllo. Se non esiste [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nessun altro controllo attivabile, lo stato attivo torna all'ultimo controllo Windows Form nell'ordine di tabulazione.<br />- I tasti FRECCIA GIU' e FRECCIA DESTRA <xref:System.Windows.Forms.Integration.WindowsFormsHost> dell'ultimo controllo contenuto nel controllo eseguono la stessa azione del tasto TAB. Se è presente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un controllo attivabile, lo stato attivo si sposta all'esterno del <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo. Questo comportamento è diverso <xref:System.Windows.Forms.ContainerControl> dal comportamento standard in quanto non viene eseguito il wrapping al primo controllo. Se non esiste [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nessun altro controllo attivabile, lo stato attivo torna al primo controllo Windows Form nell'ordine di tabulazione.|Non applicabile.|  
|Tasti di scelta rapida|I tasti di scelta rapida funzionano come di consueto, salvo diversa indicazione nella colonna "Non supportato".|I tasti di scelta rapida duplicati tra diverse tecnologie non funzionano come i normali tasti di scelta rapida duplicati. Quando un tasto di scelta rapida viene duplicato tra le tecnologie, con almeno uno su un controllo Windows Form e l'altro su un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo, il controllo Windows Form riceve sempre il tasto di scelta rapida. Lo stato attivo non passa tra i controlli quando il tasto di scelta rapida duplicato viene premuto.|  
|Combinazione di tasti|Le combinazioni di tasti funzionano come di consueto, salvo diversa indicazione nella colonna "Non supportato".|- I tasti di scelta rapida di Windows Form gestiti in fase di pre-elaborazione hanno sempre la precedenza sui tasti di scelta rapida.- Windows Forms shortcut keys that are handled at the preprocessing stage always take precedence over [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] shortcut keys. Se, ad esempio, <xref:System.Windows.Forms.ToolStrip> si dispone di un controllo con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] i tasti di scelta <xref:System.Windows.Forms.ToolStrip> rapida CTRL e se è presente un comando associato a CTRL, il gestore del controllo viene sempre richiamato per primo, indipendentemente dallo stato attivo.<br />- I tasti di scelta rapida <xref:System.Windows.Forms.Control.KeyDown> di Windows [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Form gestiti dall'evento vengono elaborati per ultimi in . È possibile evitare questo comportamento eseguendo l'override del metodo del <xref:System.Windows.Forms.Control.IsInputKey%2A> controllo Windows Form o gestendo l'evento. <xref:System.Windows.Forms.Control.PreviewKeyDown> Restituire `true` dal <xref:System.Windows.Forms.Control.IsInputKey%2A> metodo o impostare <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> il `true` valore <xref:System.Windows.Forms.Control.PreviewKeyDown> della proprietà su nel gestore eventi.|  
|Comportamento di AcceptsReturn, AcceptsTab e di altri controlli|Le proprietà che modificano il comportamento predefinito della tastiera funzionano <xref:System.Windows.Forms.Control.IsInputKey%2A> come `true`di consueto, presupponendo che il controllo Windows Form eserciti da un override del metodo da restituire.|I controlli Windows Form che modificano il comportamento predefinito della tastiera gestendo l'evento <xref:System.Windows.Forms.Control.KeyDown> vengono elaborati per ultimi nel controllo host. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Per questo motivo possono generare un comportamento imprevisto.|  
|Eventi Enter e Leave|Quando lo stato attivo <xref:System.Windows.Forms.Integration.ElementHost> non passa al controllo contenitore, gli eventi Enter <xref:System.Windows.Forms.Integration.WindowsFormsHost> e Leave vengono generati come di consueto quando lo stato attivo cambia in un singolo controllo.|Gli eventi Enter e Leave non vengono generati quando si verificano i cambiamenti seguenti dello stato attivo:<br /><br /> - Dall'interno <xref:System.Windows.Forms.Integration.WindowsFormsHost> all'esterno di un controllo.<br />- Dall'esterno <xref:System.Windows.Forms.Integration.WindowsFormsHost> all'interno di un controllo.<br />- Fuori <xref:System.Windows.Forms.Integration.WindowsFormsHost> da un controllo.<br />- Da un controllo Windows <xref:System.Windows.Forms.Integration.WindowsFormsHost> Form ospitato in un controllo a un <xref:System.Windows.Forms.Integration.ElementHost> controllo ospitato all'interno dello stesso <xref:System.Windows.Forms.Integration.WindowsFormsHost>oggetto .|  
|Multithreading|Sono supportati tutti i tipi di multithreading.|Sia Windows Form [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che le tecnologie presuppongono un modello di concorrenza a thread singolo. Durante il debug, le chiamate agli oggetti framework da altri thread generano un'eccezione per applicare questo requisito.|  
|Security|Tutti gli scenari di interoperatività richiedono l'attendibilità totale.|Non sono ammessi scenari di interoperatività con attendibilità parziale.|  
|Accessibilità|Sono supportati tutti gli scenari di accessibilità. I prodotti di Assistive Technology funzionano correttamente quando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono utilizzati per applicazioni ibride che contengono sia Windows Form che controlli.|Non applicabile.|  
|Appunti|Tutte le operazioni degli Appunti funzionano come di consueto. Ciò include il taglio e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incolla tra Windows Form e controlli.|Non applicabile.|  
|Funzionalità di trascinamento|Tutte le operazioni di trascinamento funzionano come di consueto, Sono incluse le operazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tra Windows Form e controlli.|Non applicabile.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>
## <a name="hosting-wpf-controls-in-windows-forms"></a>Hosting di controlli WPF in Windows Form  
 I seguenti scenari di interoperabilità sono supportati [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] quando un controllo Windows Form ospita un controllo:The following interoperation scenarios are supported when a Windows Forms control hosts a control:  
  
- Hosting di uno o più controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tramite il codice.  
  
- Associazione di una finestra delle proprietà a uno o più controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitati.  
  
- Hosting di una o più pagine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in un form.  
  
- Apertura di una finestra [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hosting di un form master/dettaglio [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con un master di Windows Form e dettagli.  
  
- Hosting di un form [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] master/dettaglio con un master e dettagli di Windows Form.Hosting a master/detail form with a master and Windows Forms details.  
  
- Hosting di controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] personalizzati.  
  
- Hosting di controlli ibridi.  
  
### <a name="ambient-properties"></a>Proprietà di ambiente  
 Alcune delle proprietà di ambiente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dei controlli Windows Form hanno equivalenti. Queste proprietà di ambiente vengono propagate ai controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Forms.Integration.ElementHost> ospitati ed esposte come proprietà pubbliche nel controllo. Il <xref:System.Windows.Forms.Integration.ElementHost> controllo converte ogni proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di ambiente Windows Form nell'equivalente.  
  
 Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamento  
 La tabella seguente descrive il comportamento dell'interoperatività.  
  
|Comportamento|Supportato|Non supportate|  
|--------------|---------------|-------------------|  
|Trasparenza|Il rendering del controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta la trasparenza. Lo sfondo del controllo Windows Form padre può [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] diventare lo sfondo dei controlli ospitati.|Non applicabile.|  
|Multithreading|Sono supportati tutti i tipi di multithreading.|Sia Windows Form [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che le tecnologie presuppongono un modello di concorrenza a thread singolo. Durante il debug, le chiamate agli oggetti framework da altri thread generano un'eccezione per applicare questo requisito.|  
|Security|Tutti gli scenari di interoperatività richiedono l'attendibilità totale.|Non sono ammessi scenari di interoperatività con attendibilità parziale.|  
|Accessibilità|Sono supportati tutti gli scenari di accessibilità. I prodotti di Assistive Technology funzionano correttamente quando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono utilizzati per applicazioni ibride che contengono sia Windows Form che controlli.|Non applicabile.|  
|Appunti|Tutte le operazioni degli Appunti funzionano come di consueto. Ciò include il taglio e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incolla tra Windows Form e controlli.|Non applicabile.|  
|Funzionalità di trascinamento|Tutte le operazioni di trascinamento funzionano come di consueto, Sono incluse le operazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tra Windows Form e controlli.|Non applicabile.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Procedura dettagliata: hosting di controlli Windows Form in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md)
