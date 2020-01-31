---
title: Interoperabilità Windows Forms e WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- nester interoperation [WPF]
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
- hybrid control [WPF interoperability]
ms.assetid: 9e8aa6b6-112c-4579-98d1-c974917df499
ms.openlocfilehash: 5141b84ecd002d920f0d4130bdc2529c0fce4994
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794049"
---
# <a name="wpf-and-windows-forms-interoperation"></a>Interoperatività di WPF e Windows Form
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e Windows Forms presentano due architetture diverse per la creazione di interfacce dell'applicazione. Lo spazio dei nomi <xref:System.Windows.Forms.Integration?displayProperty=nameWithType> fornisce classi che consentono scenari comuni di interoperatività. Le due classi principali che implementano le funzionalità di interoperatività sono <xref:System.Windows.Forms.Integration.WindowsFormsHost> e <xref:System.Windows.Forms.Integration.ElementHost>. Questo argomento descrive gli scenari di interoperatività supportati e indica quelli non supportati.  
  
> [!NOTE]
> Particolare attenzione viene dedicata allo scenario del *controllo ibrido*. Un controllo ibrido è costituito da un controllo di una tecnologia annidato in un controllo di un'altra tecnologia. Questa situazione viene anche definita *interoperatività annidata*. Un *controllo ibrido multilivello* prevede più di un livello di annidamento dei controlli ibridi. Un esempio di interoperabilità annidata multilivello è un controllo Windows Forms che contiene un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], che contiene un altro controllo Windows Forms. I controlli ibridi multilivello non sono supportati.  

<a name="Windows_Presentation_Foundation_Application_Hosting"></a>   
## <a name="hosting-windows-forms-controls-in-wpf"></a>Hosting di controlli Windows Form in WPF  
 Gli scenari di interoperatività seguenti sono supportati quando un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospita un controllo Windows Forms:  
  
- Il controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] può ospitare uno o più controlli Windows Forms con XAML.  
  
- Può ospitare uno o più controlli Windows Forms usando il codice.  
  
- Può ospitare Windows Forms controlli contenitore che contengono altri controlli Windows Forms.  
  
- Può ospitare un form Master-Details con un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] master e Windows Forms dettagli.  
  
- Può ospitare un form Master-Details con un Windows Forms master e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dettagli.  
  
- Può ospitare uno o più controlli ActiveX.  
  
- Può ospitare uno o più controlli compositi.  
  
- Può ospitare controlli ibridi tramite [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
- Può ospitare controlli ibridi tramite il codice.  
  
### <a name="layout-support"></a>Supporto del layout  
 Nell'elenco seguente vengono descritte le limitazioni note quando l'elemento <xref:System.Windows.Forms.Integration.WindowsFormsHost> tenta di integrare il controllo Windows Forms ospitato nel sistema di layout di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- In alcuni casi, i controlli Windows Forms non possono essere ridimensionati o possono essere ridimensionati solo a dimensioni specifiche. Ad esempio, un controllo Windows Forms <xref:System.Windows.Forms.ComboBox> supporta solo una singola altezza, che è definita dalle dimensioni del carattere del controllo. In un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout dinamico, che presuppone che gli elementi possano essere allungati verticalmente, un controllo <xref:System.Windows.Forms.ComboBox> ospitato non si estenderà come previsto.  
  
- Non è possibile ruotare o inclinare i controlli Windows Forms. Ad esempio, quando si ruota l'interfaccia utente di 90 gradi, i controlli Windows Forms ospitati manterranno la posizione verticale.  
  
- Nella maggior parte dei casi, i controlli Windows Forms non supportano la scalabilità proporzionale. Anche se le dimensioni complessive del controllo vengono ridimensionate, i controlli figlio e gli elementi componente del controllo potrebbero non venire ridimensionati come previsto. Questa limitazione dipende dal modo in cui ogni controllo Windows Forms supporta il ridimensionamento.  
  
- In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è possibile modificare l'ordine z degli elementi per controllare il comportamento di sovrapposizione. Un controllo Windows Forms ospitato viene disegnato in un HWND separato, pertanto viene sempre disegnato sopra gli elementi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- I controlli Windows Forms supportano la scalabilità automatica in base alle dimensioni del carattere. In un'interfaccia utente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], modificando le dimensioni del carattere non si ridimensiona l'intero layout, anche se è possibile che vengano ridimensionati dinamicamente singoli elementi.  
  
### <a name="ambient-properties"></a>Proprietà di ambiente  
 Alcune delle proprietà di ambiente dei controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno Windows Forms equivalenti. Queste proprietà di ambiente vengono propagate ai controlli Windows Forms ospitati ed esposte come proprietà pubbliche nel controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Il controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> converte ogni proprietà di ambiente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nell'equivalente Windows Forms.  
  
 Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamento di  
 La tabella seguente descrive il comportamento dell'interoperatività.  
  
|Comportamento di|Supportato|Non supportato|  
|--------------|---------------|-------------------|  
|Trasparenza|Il rendering del controllo Windows Forms supporta la trasparenza. Lo sfondo del controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] padre può diventare lo sfondo dei controlli Windows Forms ospitati.|Alcuni controlli Windows Forms non supportano la trasparenza. Ad esempio, i controlli <xref:System.Windows.Forms.TextBox> e <xref:System.Windows.Forms.ComboBox> non saranno trasparenti se ospitati da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|  
|Tabulazione|L'ordine di tabulazione per i controlli Windows Forms ospitati è identico a quello in cui tali controlli sono ospitati in un'applicazione basata su Windows Forms.<br /><br /> La tabulazione da un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a un controllo Windows Forms con il tasto TAB e i tasti MAIUSC + TAB funzionano come di consueto.<br /><br /> Windows Forms controlli che hanno un valore della proprietà <xref:System.Windows.Forms.Control.TabStop%2A> di `false` non ricevono lo stato attivo quando l'utente esegue la tabulazione dei controlli.<br /><br /> -Ogni controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> dispone di un valore <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A>, che determina quando il controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> riceve lo stato attivo.<br />-Windows Forms i controlli contenuti all'interno di un contenitore di <xref:System.Windows.Forms.Integration.WindowsFormsHost> seguono l'ordine specificato dalla proprietà <xref:System.Windows.Forms.Control.TabIndex%2A>. La tabulazione dall'ultimo indice di tabulazione assegna lo stato attivo al successivo controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], se presente. Se non esiste un altro controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] attivabile, la tabulazione torna al primo controllo Windows Forms nell'ordine di tabulazione.<br />-   <xref:System.Windows.Forms.Integration.WindowsFormsHost.TabIndex%2A> valori per i controlli all'interno del <xref:System.Windows.Forms.Integration.WindowsFormsHost> sono relativi ai controlli di pari livello Windows Forms contenuti nel controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />- La tabulazione rispetta il comportamento specifico del controllo. Se, ad esempio, si preme il tasto TAB in un controllo <xref:System.Windows.Forms.TextBox> con un valore <xref:System.Windows.Forms.TextBoxBase.AcceptsTab%2A> proprietà, `true` immette una scheda nella casella di testo anziché spostare lo stato attivo.|Non applicabile.|  
|Navigazione con i tasti di direzione|-La navigazione con i tasti di direzione nel controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> è identica a quella di un normale controllo contenitore Windows Forms: i tasti freccia su e freccia sinistra selezionano il controllo precedente, la freccia giù e i tasti freccia destra selezionano il controllo successivo.<br />-I tasti freccia su e freccia sinistra dal primo controllo contenuto nel controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> eseguono la stessa azione del tasto di scelta rapida MAIUSC + TAB. Se è presente un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] attivabile, lo stato attivo si sposta all'esterno del controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Questo comportamento differisce dal comportamento di <xref:System.Windows.Forms.ContainerControl> standard in quanto non viene eseguito il wrapping all'ultimo controllo. Se non esiste un altro controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] attivabile, lo stato attivo torna all'ultimo controllo Windows Forms nell'ordine di tabulazione.<br />-I tasti freccia giù e freccia destra dall'ultimo controllo contenuto nel controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> eseguono la stessa azione del tasto TAB. Se è presente un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] attivabile, lo stato attivo si sposta all'esterno del controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>. Questo comportamento differisce dal comportamento di <xref:System.Windows.Forms.ContainerControl> standard in quanto non viene eseguito il wrapping al primo controllo. Se non esiste un altro controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] attivabile, lo stato attivo torna al primo controllo Windows Forms nell'ordine di tabulazione.|Non applicabile.|  
|Tasti di scelta rapida|I tasti di scelta rapida funzionano come di consueto, salvo diversa indicazione nella colonna "Non supportato".|I tasti di scelta rapida duplicati tra diverse tecnologie non funzionano come i normali tasti di scelta rapida duplicati. Quando un acceleratore viene duplicato tra le tecnologie, con almeno un controllo Windows Forms e l'altro in un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], il controllo Windows Forms riceve sempre il tasto di scelta rapida. Lo stato attivo non passa tra i controlli quando il tasto di scelta rapida duplicato viene premuto.|  
|Tasti di scelta rapida|Le combinazioni di tasti funzionano come di consueto, salvo diversa indicazione nella colonna "Non supportato".|-Windows Forms i tasti di scelta rapida gestiti in fase di pre-elaborazione hanno sempre la precedenza sui tasti di scelta rapida [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Se, ad esempio, è stato definito un controllo <xref:System.Windows.Forms.ToolStrip> con i tasti di scelta rapida CTRL + S ed è presente un comando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] associato a CTRL + S, il gestore di controllo <xref:System.Windows.Forms.ToolStrip> viene sempre richiamato per primo, indipendentemente dallo stato attivo.<br />-Windows Forms i tasti di scelta rapida gestiti dall'evento <xref:System.Windows.Forms.Control.KeyDown> vengono elaborati per ultimi in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. È possibile evitare questo comportamento eseguendo l'override del metodo <xref:System.Windows.Forms.Control.IsInputKey%2A> del controllo Windows Forms o gestendo l'evento <xref:System.Windows.Forms.Control.PreviewKeyDown>. Restituire `true` dal metodo <xref:System.Windows.Forms.Control.IsInputKey%2A> oppure impostare il valore della proprietà <xref:System.Windows.Forms.PreviewKeyDownEventArgs.IsInputKey%2A?displayProperty=nameWithType> su `true` nel gestore dell'evento <xref:System.Windows.Forms.Control.PreviewKeyDown>.|  
|Comportamento di AcceptsReturn, AcceptsTab e di altri controlli|Le proprietà che modificano il comportamento predefinito della tastiera funzionano come di consueto, presupponendo che il controllo Windows Forms esegua l'override del metodo <xref:System.Windows.Forms.Control.IsInputKey%2A> per restituire `true`.|Windows Forms controlli che modificano il comportamento predefinito della tastiera gestendo l'evento <xref:System.Windows.Forms.Control.KeyDown> vengono elaborati per ultimi nel controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host. Per questo motivo possono generare un comportamento imprevisto.|  
|Eventi Enter e Leave|Quando lo stato attivo non passa al controllo <xref:System.Windows.Forms.Integration.ElementHost> che lo contiene, gli eventi Enter e Leave vengono generati come di consueto quando lo stato attivo cambia in un singolo controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>.|Gli eventi Enter e Leave non vengono generati quando si verificano i cambiamenti seguenti dello stato attivo:<br /><br /> -Dall'interno all'esterno di un controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-Dall'esterno all'interno di un controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-All'esterno di un controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost>.<br />-Da un controllo Windows Forms ospitato in un controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> a un controllo <xref:System.Windows.Forms.Integration.ElementHost> ospitato all'interno della stessa <xref:System.Windows.Forms.Integration.WindowsFormsHost>.|  
|Multithreading|Sono supportati tutti i tipi di multithreading.|Entrambe le tecnologie Windows Forms e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presuppongono un modello di concorrenza a thread singolo. Durante il debug, le chiamate agli oggetti framework da altri thread generano un'eccezione per applicare questo requisito.|  
|Sicurezza -|Tutti gli scenari di interoperatività richiedono l'attendibilità totale.|Non sono ammessi scenari di interoperatività con attendibilità parziale.|  
|Accessibilità|Sono supportati tutti gli scenari di accessibilità. I prodotti di Assistive Technology funzionano correttamente quando vengono usati per applicazioni ibride che contengono controlli sia Windows Forms che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
|Appunti|Tutte le operazioni degli Appunti funzionano come di consueto. Sono incluse le trascinamenti e le paste tra Windows Forms e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] i controlli.|Non applicabile.|  
|Funzionalità di trascinamento|Tutte le operazioni di trascinamento funzionano come di consueto, Sono incluse le operazioni tra Windows Forms e i controlli di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
  
<a name="Windows_Forms_Application_Hosting_Windows"></a>   
## <a name="hosting-wpf-controls-in-windows-forms"></a>Hosting di controlli WPF in Windows Form  
 Gli scenari di interoperatività seguenti sono supportati quando un controllo Windows Forms ospita un controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
- Hosting di uno o più controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tramite il codice.  
  
- Associazione di una finestra delle proprietà a uno o più controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitati.  
  
- Hosting di una o più pagine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in un form.  
  
- Apertura di una finestra [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Hosting di un form Master-Details con un Windows Forms master e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dettagli.  
  
- Hosting di un form Master-Details con un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] master e Windows Forms dettagli.  
  
- Hosting di controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] personalizzati.  
  
- Hosting di controlli ibridi.  
  
### <a name="ambient-properties"></a>Proprietà di ambiente  
 Alcune delle proprietà di ambiente dei controlli Windows Forms hanno [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] equivalenti. Queste proprietà di ambiente vengono propagate ai controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitati ed esposte come proprietà pubbliche nel controllo <xref:System.Windows.Forms.Integration.ElementHost>. Il controllo <xref:System.Windows.Forms.Integration.ElementHost> converte ogni proprietà di ambiente Windows Forms nell'equivalente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Per altre informazioni, vedere [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md).  
  
### <a name="behavior"></a>Comportamento di  
 La tabella seguente descrive il comportamento dell'interoperatività.  
  
|Comportamento di|Supportato|Non supportato|  
|--------------|---------------|-------------------|  
|Trasparenza|Il rendering del controllo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta la trasparenza. Lo sfondo del controllo Windows Forms padre può diventare lo sfondo dei controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ospitati.|Non applicabile.|  
|Multithreading|Sono supportati tutti i tipi di multithreading.|Entrambe le tecnologie Windows Forms e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presuppongono un modello di concorrenza a thread singolo. Durante il debug, le chiamate agli oggetti framework da altri thread generano un'eccezione per applicare questo requisito.|  
|Sicurezza -|Tutti gli scenari di interoperatività richiedono l'attendibilità totale.|Non sono ammessi scenari di interoperatività con attendibilità parziale.|  
|Accessibilità|Sono supportati tutti gli scenari di accessibilità. I prodotti di Assistive Technology funzionano correttamente quando vengono usati per applicazioni ibride che contengono controlli sia Windows Forms che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
|Appunti|Tutte le operazioni degli Appunti funzionano come di consueto. Sono incluse le trascinamenti e le paste tra Windows Forms e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] i controlli.|Non applicabile.|  
|Funzionalità di trascinamento|Tutte le operazioni di trascinamento funzionano come di consueto, Sono incluse le operazioni tra Windows Forms e i controlli di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].|Non applicabile.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Procedura dettagliata: hosting di controlli Windows Form in WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Procedura dettaglia: hosting di un controllo WPF composito in Windows Form](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Mapping di proprietà di Windows Form e WPF](windows-forms-and-wpf-property-mapping.md)
