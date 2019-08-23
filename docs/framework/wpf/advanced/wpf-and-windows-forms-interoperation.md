---
title: Interoperatività di WPF e Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 0326f283cb271d1578e94b648e423c6f88c579f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917393"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Interoperatività di WPF e Windows Form
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] presentano due architetture diverse per la creazione di interfacce delle applicazioni. Lo <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> spazio dei nomi fornisce classi che consentono scenari comuni di interoperatività. Le due classi principali che implementano le funzionalità di <xref:System.Windows.Forms.Integration.WindowsFormsHost> interoperatività sono e <xref:System.Windows.Forms.Integration.ElementHost>. Questo argomento descrive gli scenari di interoperatività supportati e indica quelli non supportati.  
  
> [!NOTE]
> Particolare attenzione viene dedicata allo scenario del *controllo ibrido*. Un controllo ibrido è costituito da un controllo di una tecnologia annidato in un controllo di un'altra tecnologia. Questa situazione viene anche definita *interoperatività annidata*. Un *controllo ibrido multilivello* prevede più di un livello di annidamento dei controlli ibridi. Un esempio di interoperatività annidata multilivello è costituito da un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] che contiene un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], che contiene un altro controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. I controlli ibridi multilivello non sono supportati.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## <a name="hosting-windows-forms-controls-in-wpf"></a>Hosting di controlli Windows Form in WPF  
 Gli scenari di interoperatività seguenti sono supportati [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] quando un controllo ospita un controllo Windows Forms:  
  
- Il controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] può ospitare uno o più controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tramite XAML.  
  
- Può ospitare uno o più controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tramite il codice.  
  
- Può ospitare controlli contenitore [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] che contengono altri controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
- Può ospitare un form master - dettagli con un master [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e dettagli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
- Può ospitare un form master - dettagli con un master [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e dettagli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Può ospitare uno o più controlli ActiveX.  
  
- Può ospitare uno o più controlli compositi.  
  
- Può ospitare controlli ibridi tramite [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
- Può ospitare controlli ibridi tramite il codice.  
  
### <a name="layout-support"></a>Supporto del layout  
 Nell'elenco seguente vengono descritte le limitazioni note quando <xref:System.Windows.Forms.Integration.WindowsFormsHost> l'elemento tenta di integrare il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo ospitato nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di layout.  
  
- In alcuni casi, i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non possono essere ridimensionati oppure possono essere ridimensionati solo in dimensioni specifiche. Ad esempio, un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> controllo supporta una sola altezza, che è definita dalle dimensioni del carattere del controllo. In un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout dinamico, che presuppone che gli elementi possano essere allungati verticalmente, un controllo ospitato <xref:System.Windows.Forms.ComboBox> non si estenderà come previsto.  
  
- I controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non possono essere ruotati o inclinati. Ad esempio, quando si ruota l'interfaccia utente di 90 gradi, i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitati manterranno la posizione verticale.  
  
- Nella maggior parte dei casi, i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non supportano il ridimensionamento proporzionale. Anche se le dimensioni complessive del controllo vengono ridimensionate, i controlli figlio e gli elementi componente del controllo potrebbero non venire ridimensionati come previsto. Questa limitazione dipende dal modo in cui ogni controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] supporta il ridimensionamento.  
  
- In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è possibile modificare l'ordine z degli elementi per controllare il comportamento di sovrapposizione. Un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato viene disegnato in un elemento HWND separato, in modo che venga disegnato sempre sopra gli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- I controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] supportano il ridimensionamento automatico in base alla dimensione del carattere. In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], modificando le dimensioni del carattere non si ridimensiona l'intero layout, anche se è possibile che vengano ridimensionati dinamicamente singoli elementi.  
  
### <a name="ambient-properties"></a>Proprietà di ambiente  
 Alcune delle proprietà di ambiente dei controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno equivalenti [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Queste proprietà di ambiente vengono propagate ai [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli ospitati ed esposte come <xref:System.Windows.Forms.Integration.WindowsFormsHost> proprietà pubbliche nel controllo. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo converte ogni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà di ambiente nel relativo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] equivalente.  
  
 Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamento  
 La tabella seguente descrive il comportamento dell'interoperatività.  
  
|Comportamento|Supportato|Non supportate|  
|--------------|---------------|-------------------|  
|Trasparenza|Il rendering del controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] supporta la trasparenza. Lo sfondo del controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] padre può diventare lo sfondo dei controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitati.|Alcuni controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non supportano la trasparenza. I <xref:System.Windows.Forms.TextBox> controlli e <xref:System.Windows.Forms.ComboBox> , ad esempio, non saranno trasparenti se ospitati da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Tabulazione|L'ordine di tabulazione per i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitati è identico quando tali controlli vengono ospitati in un'applicazione basata su [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].<br /><br /> La tabulazione da un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con TAB e l'abbreviazione da tastiera MAIUSC+TAB funzionano come di consueto.<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]i controlli che hanno <xref:System.Windows.Forms.Control.TabStop%2A> un valore della `false` proprietà di non ricevono lo stato attivo quando l'utente esegue la tabulazione dei controlli.<br /><br /> -Ogni <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo ha un <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> valore che determina quando il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo riceve lo stato attivo.<br />-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]i controlli contenuti all'interno di <xref:System.Windows.Forms.Integration.WindowsFormsHost> un contenitore seguono l'ordine specificato <xref:System.Windows.Forms.Control.TabIndex%2A> dalla proprietà. La tabulazione dall'ultimo indice di tabulazione assegna lo stato attivo al successivo controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se presente. Se non esiste un altro controllo con stato attivabile [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], la tabulazione torna al primo controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] nell'ordine di tabulazione.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>i valori per i <xref:System.Windows.Forms.Integration.WindowsFormsHost> controlli all'interno di sono relativi ai controlli di pari livello <xref:System.Windows.Forms.Integration.WindowsFormsHost> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] contenuti nel controllo.<br />- La tabulazione rispetta il comportamento specifico del controllo. Se, ad esempio, si preme il tasto <xref:System.Windows.Forms.TextBox> Tab in un controllo <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> con un valore `true` della proprietà, viene attivata una scheda nella casella di testo anziché spostare lo stato attivo.|Non applicabile.|  
|Navigazione con i tasti di direzione|-La navigazione con i <xref:System.Windows.Forms.Integration.WindowsFormsHost> tasti di direzione nel controllo è identica a quella di un normale [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo contenitore: I tasti freccia su e freccia sinistra selezionano il controllo precedente e la freccia giù e i tasti freccia destra selezionano il controllo successivo.<br />-I tasti freccia su e freccia sinistra del primo controllo contenuto nel <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo eseguono la stessa operazione del tasto di scelta rapida MAIUSC + TAB. Se è presente un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo attivabile, lo stato attivo si sposta all'esterno del <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo. Questo comportamento differisce dal comportamento standard <xref:System.Windows.Forms.ContainerControl> in quanto non viene eseguito il wrapping all'ultimo controllo. Se non esiste un altro controllo con stato attivabile [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], lo stato attivo torna all'ultimo controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] nell'ordine di tabulazione.<br />-I tasti freccia giù e freccia destra dall'ultimo controllo contenuto nel <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo eseguono la stessa azione del tasto TAB. Se è presente un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo attivabile, lo stato attivo si sposta all'esterno del <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo. Questo comportamento differisce dal comportamento standard <xref:System.Windows.Forms.ContainerControl> in quanto non viene eseguito il wrapping al primo controllo. Se non esiste un altro controllo con stato attivabile [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], lo stato attivo torna al primo controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] nell'ordine di tabulazione.|Non applicabile.|  
|Tasti di scelta rapida|I tasti di scelta rapida funzionano come di consueto, salvo diversa indicazione nella colonna "Non supportato".|I tasti di scelta rapida duplicati tra diverse tecnologie non funzionano come i normali tasti di scelta rapida duplicati. Quando un tasto di scelta rapida è duplicato tra diverse tecnologie e almeno uno si applica a un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e l'altro a un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] riceve sempre il tasto di scelta rapida. Lo stato attivo non passa tra i controlli quando il tasto di scelta rapida duplicato viene premuto.|  
|Combinazione di tasti|Le combinazioni di tasti funzionano come di consueto, salvo diversa indicazione nella colonna "Non supportato".|Le combinazioni di tasti -   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] gestite in fase di pre-elaborazione hanno sempre la precedenza rispetto alle combinazioni di tasti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Se, ad esempio, è stato <xref:System.Windows.Forms.ToolStrip> definito un controllo con tasti di scelta rapida Ctrl + s ed è [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presente un comando associato a Ctrl + s <xref:System.Windows.Forms.ToolStrip> , il gestore di controllo viene sempre richiamato per primo, indipendentemente dallo stato attivo.<br />-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]i <xref:System.Windows.Forms.Control.KeyDown> tasti di scelta rapida gestiti dall'evento vengono elaborati per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ultimi in. È possibile evitare questo comportamento eseguendo l'override del [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.IsInputKey%2A> metodo del controllo o gestendo <xref:System.Windows.Forms.Control.PreviewKeyDown> l'evento. Restituire `true` `true` <xref:System.Windows.Forms.Control.PreviewKeyDown> dal metodo o impostare il valore della proprietàsunelgestoreeventi.<xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.Control.IsInputKey%2A>|  
|Comportamento di AcceptsReturn, AcceptsTab e di altri controlli|Le proprietà che modificano il comportamento predefinito della tastiera funzionano come di consueto [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] , supponendo <xref:System.Windows.Forms.Control.IsInputKey%2A> che il controllo `true`esegua l'override del metodo da restituire.|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]i controlli che modificano il comportamento predefinito della <xref:System.Windows.Forms.Control.KeyDown> tastiera gestendo l'evento vengono elaborati per ultimi nel controllo host. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Per questo motivo possono generare un comportamento imprevisto.|  
|Eventi Enter e Leave|Quando lo stato attivo non passa al controllo <xref:System.Windows.Forms.Integration.ElementHost> contenitore, gli eventi Enter e Leave vengono generati come di consueto quando lo stato attivo cambia <xref:System.Windows.Forms.Integration.WindowsFormsHost> in un unico controllo.|Gli eventi Enter e Leave non vengono generati quando si verificano i cambiamenti seguenti dello stato attivo:<br /><br /> -Dall'interno all'esterno di <xref:System.Windows.Forms.Integration.WindowsFormsHost> un controllo.<br />-Dall'esterno all'interno di <xref:System.Windows.Forms.Integration.WindowsFormsHost> un controllo.<br />-All'esterno <xref:System.Windows.Forms.Integration.WindowsFormsHost> di un controllo.<br />-Da un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo ospitato in un <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo a un <xref:System.Windows.Forms.Integration.ElementHost> controllo ospitato all'interno della <xref:System.Windows.Forms.Integration.WindowsFormsHost>stessa.|  
|Multithreading|Sono supportati tutti i tipi di multithreading.|Le tecnologie [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presuppongono un modello di concorrenza a thread singolo. Durante il debug, le chiamate agli oggetti framework da altri thread generano un'eccezione per applicare questo requisito.|  
|Security|Tutti gli scenari di interoperatività richiedono l'attendibilità totale.|Non sono ammessi scenari di interoperatività con attendibilità parziale.|  
|Accessibilità|Sono supportati tutti gli scenari di accessibilità. I prodotti con tecnologia per l'accessibilità funzionano correttamente quando vengono usati per applicazioni ibride che contengono sia il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
|Appunti|Tutte le operazioni degli Appunti funzionano come di consueto. Ciò include le operazioni taglia e incolla tra i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
|Funzionalità di trascinamento|Tutte le operazioni di trascinamento funzionano come di consueto, incluse le operazioni tra i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## <a name="hosting-wpf-controls-in-windows-forms"></a>Hosting di controlli WPF in Windows Form  
 Gli scenari di interoperatività seguenti sono supportati quando un controllo Windows Forms [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospita un controllo:  
  
- Hosting di uno o più controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tramite il codice.  
  
- Associazione di una finestra delle proprietà a uno o più controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitati.  
  
- Hosting di una o più pagine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in un form.  
  
- Apertura di una finestra [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hosting di un form master - dettagli con un master [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e dettagli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hosting di un form master - dettagli con un master [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e dettagli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
- Hosting di controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] personalizzati.  
  
- Hosting di controlli ibridi.  
  
### <a name="ambient-properties"></a>Proprietà di ambiente  
 Alcune delle proprietà di ambiente dei controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hanno equivalenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Queste proprietà di ambiente vengono propagate ai [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlli ospitati ed esposte come <xref:System.Windows.Forms.Integration.ElementHost> proprietà pubbliche nel controllo. Il <xref:System.Windows.Forms.Integration.ElementHost> controllo converte ogni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proprietà di ambiente nell' [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalente.  
  
 Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamento  
 La tabella seguente descrive il comportamento dell'interoperatività.  
  
|Comportamento|Supportato|Non supportate|  
|--------------|---------------|-------------------|  
|Trasparenza|Il rendering del controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta la trasparenza. Lo sfondo del controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] padre può diventare lo sfondo dei controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitati.|Non applicabile.|  
|Multithreading|Sono supportati tutti i tipi di multithreading.|Le tecnologie [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presuppongono un modello di concorrenza a thread singolo. Durante il debug, le chiamate agli oggetti framework da altri thread generano un'eccezione per applicare questo requisito.|  
|Security|Tutti gli scenari di interoperatività richiedono l'attendibilità totale.|Non sono ammessi scenari di interoperatività con attendibilità parziale.|  
|Accessibilità|Sono supportati tutti gli scenari di accessibilità. I prodotti con tecnologia per l'accessibilità funzionano correttamente quando vengono usati per applicazioni ibride che contengono sia il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
|Appunti|Tutte le operazioni degli Appunti funzionano come di consueto. Ciò include le operazioni taglia e incolla tra i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
|Funzionalità di trascinamento|Tutte le operazioni di trascinamento funzionano come di consueto, incluse le operazioni tra i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Procedura dettagliata: Hosting di un controllo Windows Forms in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo Windows Forms composito in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md)
