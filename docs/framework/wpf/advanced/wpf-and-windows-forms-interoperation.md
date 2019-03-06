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
ms.openlocfilehash: e6fe459ab00622860cd10e4e119e943e588f06b2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352945"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Interoperatività di WPF e Windows Form
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] presentano due architetture diverse per la creazione di interfacce delle applicazioni. Il <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> dello spazio dei nomi fornisce classi che supportano gli scenari di interoperatività comuni. Sono le due classi principali che implementano le capacità di interoperatività <xref:System.Windows.Forms.Integration.WindowsFormsHost> e <xref:System.Windows.Forms.Integration.ElementHost>. Questo argomento descrive gli scenari di interoperatività supportati e indica quelli non supportati.  
  
> [!NOTE]
>  Particolare attenzione viene dedicata allo scenario del *controllo ibrido*. Un controllo ibrido è costituito da un controllo di una tecnologia annidato in un controllo di un'altra tecnologia. Questa situazione viene anche definita *interoperatività annidata*. Un *controllo ibrido multilivello* prevede più di un livello di annidamento dei controlli ibridi. Un esempio di interoperatività annidata multilivello è costituito da un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] che contiene un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], che contiene un altro controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. I controlli ibridi multilivello non sono supportati.  
  
  
<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## <a name="hosting-windows-forms-controls-in-wpf"></a>Hosting di controlli Windows Form in WPF  
 Sono supportati gli scenari di interoperatività seguenti quando un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospita un controllo Windows Form:  
  
-   Il controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] può ospitare uno o più controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tramite XAML.  
  
-   Può ospitare uno o più controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tramite il codice.  
  
-   Può ospitare controlli contenitore [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] che contengono altri controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   Può ospitare un form master - dettagli con un master [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e dettagli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   Può ospitare un form master - dettagli con un master [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e dettagli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Può ospitare uno o più controlli [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)].  
  
-   Può ospitare uno o più controlli compositi.  
  
-   Può ospitare controlli ibridi tramite [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
-   Può ospitare controlli ibridi tramite il codice.  
  
### <a name="layout-support"></a>Supporto del layout  
 Nell'elenco seguente descrive le limitazioni note quando la <xref:System.Windows.Forms.Integration.WindowsFormsHost> elemento tenta di integrare relativo ospitato [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sul controllo nel [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di layout.  
  
-   In alcuni casi, i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non possono essere ridimensionati oppure possono essere ridimensionati solo in dimensioni specifiche. Ad esempio, un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.ComboBox> controllo supporta una sola altezza, definita dalla dimensione del carattere del controllo. In un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout dinamico, in cui si presuppone che gli elementi possano essere ridimensionati verticalmente, un ambiente host <xref:System.Windows.Forms.ComboBox> controllo non verrà ridimensionato come previsto.  
  
-   I controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non possono essere ruotati o inclinati. Ad esempio, quando si ruota l'interfaccia utente di 90 gradi, i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitati manterranno la posizione verticale.  
  
-   Nella maggior parte dei casi, i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non supportano il ridimensionamento proporzionale. Anche se le dimensioni complessive del controllo vengono ridimensionate, i controlli figlio e gli elementi componente del controllo potrebbero non venire ridimensionati come previsto. Questa limitazione dipende dal modo in cui ogni controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] supporta il ridimensionamento.  
  
-   In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è possibile modificare l'ordine z degli elementi per controllare il comportamento di sovrapposizione. Un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitato viene disegnato in un elemento HWND separato, in modo che venga disegnato sempre sopra gli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   I controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] supportano il ridimensionamento automatico in base alla dimensione del carattere. In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], modificando le dimensioni del carattere non si ridimensiona l'intero layout, anche se è possibile che vengano ridimensionati dinamicamente singoli elementi.  
  
### <a name="ambient-properties"></a>Proprietà di ambiente  
 Alcune delle proprietà di ambiente dei controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno equivalenti [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]. Queste proprietà di ambiente vengono propagate a ospitato [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlla ed esposte come proprietà pubbliche sul <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo. Il <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo converte ogni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proprietà di ambiente nel relativo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] equivalente.  
  
 Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamento  
 La tabella seguente descrive il comportamento dell'interoperatività.  
  
|Comportamento|Supportato|Non supportato|  
|--------------|---------------|-------------------|  
|Trasparenza|Il rendering del controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] supporta la trasparenza. Lo sfondo del controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] padre può diventare lo sfondo dei controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitati.|Alcuni controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] non supportano la trasparenza. Ad esempio, il <xref:System.Windows.Forms.TextBox> e <xref:System.Windows.Forms.ComboBox> controlli non sono trasparenti se ospitati da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Tabulazione|L'ordine di tabulazione per i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] ospitati è identico quando tali controlli vengono ospitati in un'applicazione basata su [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].<br /><br /> La tabulazione da un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] con TAB e l'abbreviazione da tastiera MAIUSC+TAB funzionano come di consueto.<br /><br /> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] i controlli che hanno una <xref:System.Windows.Forms.Control.TabStop%2A> valore della proprietà `false` non viene visualizzato lo stato attivo quando l'utente tramite i controlli.<br /><br /> -Ognuno <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo ha un <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> valore, che determina il momento che <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo riceverà lo stato attivo.<br />-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] i controlli che sono contenuti all'interno di un <xref:System.Windows.Forms.Integration.WindowsFormsHost> contenitore seguono l'ordine specificato dal <xref:System.Windows.Forms.Control.TabIndex%2A> proprietà. La tabulazione dall'ultimo indice di tabulazione assegna lo stato attivo al successivo controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se presente. Se non esiste un altro controllo con stato attivabile [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], la tabulazione torna al primo controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] nell'ordine di tabulazione.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> i valori per i controlli all'interno di <xref:System.Windows.Forms.Integration.WindowsFormsHost> sono di pari livello [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controlli contenuti nel <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo.<br />- La tabulazione rispetta il comportamento specifico del controllo. Ad esempio, premendo il tasto TAB in un <xref:System.Windows.Forms.TextBox> controllo dotato di un <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> valore della proprietà `true` si inserisce una tabulazione nella casella di testo anziché spostare lo stato attivo.|Non applicabile.|  
|Navigazione con i tasti di direzione|-La navigazione con le chiavi nel <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo è lo stesso comportamento di un normale [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo contenitore: La freccia su e freccia sinistra seleziona il controllo precedente e i tasti freccia su e freccia destra selezionano il controllo successivo.<br />-Il backup delle chiavi di frecce su e sinistra dal primo controllo contenuto nel <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo eseguire la stessa azione come scelta rapida da tastiera MAIUSC + TAB. Se è presente un attivabile [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (controllo), lo stato attivo viene spostato all'esterno di <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo. Questo comportamento è diverso dallo standard <xref:System.Windows.Forms.ContainerControl> in quanto nessun eseguendo il wrapping all'ultimo controllo si verifica. Se non esiste un altro controllo con stato attivabile [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], lo stato attivo torna all'ultimo controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] nell'ordine di tabulazione.<br />-La PREMUTI i tasti freccia su e freccia destra dall'ultimo controllo contenuto nel <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo eseguire la stessa azione di TAB. Se è presente un attivabile [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (controllo), lo stato attivo viene spostato all'esterno di <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo. Questo comportamento è diverso dallo standard <xref:System.Windows.Forms.ContainerControl> comportamento che si verifica alcun ritorno a capo al primo controllo. Se non esiste un altro controllo con stato attivabile [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], lo stato attivo torna al primo controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] nell'ordine di tabulazione.|Non applicabile.|  
|Tasti di scelta rapida|I tasti di scelta rapida funzionano come di consueto, salvo diversa indicazione nella colonna "Non supportato".|I tasti di scelta rapida duplicati tra diverse tecnologie non funzionano come i normali tasti di scelta rapida duplicati. Quando un tasto di scelta rapida è duplicato tra diverse tecnologie e almeno uno si applica a un controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e l'altro a un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] riceve sempre il tasto di scelta rapida. Lo stato attivo non passa tra i controlli quando il tasto di scelta rapida duplicato viene premuto.|  
|Combinazione di tasti|Le combinazioni di tasti funzionano come di consueto, salvo diversa indicazione nella colonna "Non supportato".|Le combinazioni di tasti -   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] gestite in fase di pre-elaborazione hanno sempre la precedenza rispetto alle combinazioni di tasti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ad esempio, se si dispone di un <xref:System.Windows.Forms.ToolStrip> controllare con tasti di scelta rapida CTRL + S definiti e non esiste un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] comando associato a CTRL + S, la <xref:System.Windows.Forms.ToolStrip> gestore dei controlli viene sempre richiamato prima di tutto, indipendentemente dallo stato attivo.<br />-   [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] tasti di scelta rapida che vengono gestiti tramite il <xref:System.Windows.Forms.Control.KeyDown> evento vengono elaborate per ultime [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. È possibile impedire questo comportamento eseguendo l'override di [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] del controllo <xref:System.Windows.Forms.Control.IsInputKey%2A> metodo o la gestione il <xref:System.Windows.Forms.Control.PreviewKeyDown> evento. Restituire `true` dal <xref:System.Windows.Forms.Control.IsInputKey%2A> metodo, o impostare il valore della <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> proprietà `true` nel <xref:System.Windows.Forms.Control.PreviewKeyDown> gestore dell'evento.|  
|Comportamento di AcceptsReturn, AcceptsTab e di altri controlli|Proprietà che modificano il comportamento predefinito della tastiera funzionano come di consueto, supponendo che il [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllare le sostituzioni di <xref:System.Windows.Forms.Control.IsInputKey%2A> metodo restituisca `true`.|[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] i controlli che modificare l'impostazione predefinita comportamento della tastiera gestendo il <xref:System.Windows.Forms.Control.KeyDown> evento vengono elaborate per ultime nell'host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo. Per questo motivo possono generare un comportamento imprevisto.|  
|Eventi Enter e Leave|Quando lo stato attivo non passa la contenente <xref:System.Windows.Forms.Integration.ElementHost> controllare, Enter e Leave vengono generati come di consueto quando cambia lo stato attivo in un singolo <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo.|Gli eventi Enter e Leave non vengono generati quando si verificano i cambiamenti seguenti dello stato attivo:<br /><br /> -Dall'interno all'esterno una <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo.<br />-Da esterno a interno un <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo.<br />-Di fuori un <xref:System.Windows.Forms.Integration.WindowsFormsHost> controllo.<br />-Da un [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controllo ospitato in un <xref:System.Windows.Forms.Integration.WindowsFormsHost> il controllo a un <xref:System.Windows.Forms.Integration.ElementHost> controllo ospitato nello stesso <xref:System.Windows.Forms.Integration.WindowsFormsHost>.|  
|Multithreading|Sono supportati tutti i tipi di multithreading.|Le tecnologie [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presuppongono un modello di concorrenza a thread singolo. Durante il debug, le chiamate agli oggetti framework da altri thread generano un'eccezione per applicare questo requisito.|  
|Sicurezza|Tutti gli scenari di interoperatività richiedono l'attendibilità totale.|Non sono ammessi scenari di interoperatività con attendibilità parziale.|  
|Accessibilità|Sono supportati tutti gli scenari di accessibilità. I prodotti con tecnologia per l'accessibilità funzionano correttamente quando vengono usati per applicazioni ibride che contengono sia il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
|Appunti|Tutte le operazioni degli Appunti funzionano come di consueto. Ciò include le operazioni taglia e incolla tra i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
|Funzionalità di trascinamento|Tutte le operazioni di trascinamento funzionano come di consueto, incluse le operazioni tra i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## <a name="hosting-wpf-controls-in-windows-forms"></a>Hosting di controlli WPF in Windows Form  
 Sono supportati gli scenari di interoperatività seguenti quando si ospita un controllo Windows Form un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controllo:  
  
-   Hosting di uno o più controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tramite il codice.  
  
-   Associazione di una finestra delle proprietà a uno o più controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitati.  
  
-   Hosting di una o più pagine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in un form.  
  
-   Apertura di una finestra [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Hosting di un form master - dettagli con un master [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e dettagli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Hosting di un form master - dettagli con un master [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e dettagli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].  
  
-   Hosting di controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] personalizzati.  
  
-   Hosting di controlli ibridi.  
  
### <a name="ambient-properties"></a>Proprietà di ambiente  
 Alcune delle proprietà di ambiente dei controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] hanno equivalenti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Queste proprietà di ambiente vengono propagate a ospitato [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controlla ed esposte come proprietà pubbliche sul <xref:System.Windows.Forms.Integration.ElementHost> controllo. Il <xref:System.Windows.Forms.Integration.ElementHost> controllo converte ogni [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] proprietà di ambiente relative [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalente.  
  
 Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamento  
 La tabella seguente descrive il comportamento dell'interoperatività.  
  
|Comportamento|Supportato|Non supportato|  
|--------------|---------------|-------------------|  
|Trasparenza|Il rendering del controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta la trasparenza. Lo sfondo del controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] padre può diventare lo sfondo dei controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitati.|Non applicabile.|  
|Multithreading|Sono supportati tutti i tipi di multithreading.|Le tecnologie [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presuppongono un modello di concorrenza a thread singolo. Durante il debug, le chiamate agli oggetti framework da altri thread generano un'eccezione per applicare questo requisito.|  
|Sicurezza|Tutti gli scenari di interoperatività richiedono l'attendibilità totale.|Non sono ammessi scenari di interoperatività con attendibilità parziale.|  
|Accessibilità|Sono supportati tutti gli scenari di accessibilità. I prodotti con tecnologia per l'accessibilità funzionano correttamente quando vengono usati per applicazioni ibride che contengono sia il controllo [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] sia [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
|Appunti|Tutte le operazioni degli Appunti funzionano come di consueto. Ciò include le operazioni taglia e incolla tra i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
|Funzionalità di trascinamento|Tutte le operazioni di trascinamento funzionano come di consueto, incluse le operazioni tra i controlli [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Procedura dettagliata: Hosting di controlli Windows Form in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettagliata: Hosting di un controllo composito WPF in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md)
