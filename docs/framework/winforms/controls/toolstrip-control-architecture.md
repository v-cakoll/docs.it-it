---
title: Architettura del controllo ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: 91813928344f9210ce1383daa9ba7f765117833a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296212"
---
# <a name="toolstrip-control-architecture"></a>Architettura del controllo ToolStrip
Il <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.ToolStripItem> classi forniscono un sistema flessibile ed estendibile per la visualizzazione degli elementi della barra degli strumenti, stato e menu. Tutte queste classi sono contenute nel <xref:System.Windows.Forms> dello spazio dei nomi e sono tutti in genere vengono denominati con il prefisso "ToolStrip" (ad esempio <xref:System.Windows.Forms.ToolStripOverflow>) o con il suffisso "Strisce" (, ad esempio <xref:System.Windows.Forms.MenuStrip>).  
  
## <a name="toolstrip"></a>ToolStrip  
 Gli argomenti seguenti descrivono <xref:System.Windows.Forms.ToolStrip> e i controlli che derivano da essa.  
  
 <xref:System.Windows.Forms.ToolStrip> è la classe base astratta per <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, e <xref:System.Windows.Forms.ContextMenuStrip>. L'oggetto seguente modello Mostra il <xref:System.Windows.Forms.ToolStrip> gerarchia di ereditarietà.  
  
 ![Diagramma che mostra il modello a oggetti ToolStrip.](./media/toolstrip-control-architecture/toolstrip-object-model.gif)  
  
 È possibile accedere a tutti gli elementi in un <xref:System.Windows.Forms.ToolStrip> attraverso il <xref:System.Windows.Forms.ToolStrip.Items%2A> raccolta. È possibile accedere a tutti gli elementi in un <xref:System.Windows.Forms.ToolStripDropDownItem> attraverso il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> raccolta. In una classe derivata da <xref:System.Windows.Forms.ToolStrip>, è anche possibile usare il <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> proprietà a cui accedere solo gli elementi attualmente visualizzati. Questi sono gli elementi che non sono attualmente in un menu di overflow.  
  
 Gli elementi seguenti sono appositamente progettati per integrarsi perfettamente con entrambi <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per il <xref:System.Windows.Forms.ToolStrip> controllo:  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="menustrip"></a>MenuStrip  
 <xref:System.Windows.Forms.MenuStrip> è il contenitore di primo livello che sostituisce <xref:System.Windows.Forms.MainMenu>. Fornisce inoltre la gestione delle chiavi e più documenti (MDI) interfaccia funzionalità. A livello funzionale, <xref:System.Windows.Forms.ToolStripDropDownItem> e <xref:System.Windows.Forms.ToolStripMenuItem> funzionano insieme <xref:System.Windows.Forms.MenuStrip>, anche se vengono derivati dalla <xref:System.Windows.Forms.ToolStripItem>.  
  
 Gli elementi seguenti sono appositamente progettati per integrarsi perfettamente con entrambi <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per il <xref:System.Windows.Forms.MenuStrip> controllo:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="statusstrip"></a>StatusStrip  
 <xref:System.Windows.Forms.StatusStrip> sostituisce il <xref:System.Windows.Forms.StatusBar> controllo. Speciali funzionalità del <xref:System.Windows.Forms.StatusStrip> includono un layout di tabella personalizzata, il supporto per il ridimensionamento del form e lo spostamento di riquadri e il `Spring` proprietà, che consente un <xref:System.Windows.Forms.ToolStripStatusLabel> per riempire lo spazio disponibile automaticamente.  
  
 Gli elementi seguenti sono appositamente progettati per integrarsi perfettamente con entrambi <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per il <xref:System.Windows.Forms.StatusStrip> controllo:  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### <a name="contextmenustrip"></a>ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip> sostituisce <xref:System.Windows.Forms.ContextMenu>. È possibile associare un <xref:System.Windows.Forms.ContextMenuStrip> con qualsiasi controllo e un mouse a destra fare clic su Visualizza automaticamente il menu di scelta rapida (o menu di scelta rapida). È possibile mostrare un <xref:System.Windows.Forms.ContextMenuStrip> a livello di codice usando il <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> (metodo). <xref:System.Windows.Forms.ContextMenuStrip> supporta annullabile <xref:System.Windows.Forms.ToolStripDropDown.Opening> e <xref:System.Windows.Forms.ToolStripDropDown.Closing> eventi per gestire la compilazione dinamica e scenari a selezione multipla. <xref:System.Windows.Forms.ContextMenuStrip> supporta immagini, lo stato di controllo voce di menu, testo, le chiavi di accesso, tasti di scelta rapida e i menu a cascata.  
  
 Gli elementi seguenti sono appositamente progettati per integrarsi perfettamente con entrambi <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per il <xref:System.Windows.Forms.ContextMenuStrip> controllo:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="toolstrip-generic-features"></a>Funzionalità generiche di ToolStrip  
 Gli argomenti seguenti descrivono le funzionalità e il comportamento che sono generici per la <xref:System.Windows.Forms.ToolStrip> e i controlli derivati.  
  
#### <a name="painting"></a>Disegno  
 È possibile eseguire il disegno personalizzato <xref:System.Windows.Forms.ToolStrip> controlli in vari modi. Come con altri controlli Windows Form, il <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.ToolStripItem> prevedono sottoponibile a override `OnPaint` metodi e `Paint` eventi. Come per il disegno standard, il sistema di coordinate è relativo all'area client del controllo. l'angolo superiore sinistro del controllo è 0, 0. Il `Paint` evento e `OnPaint` metodo per un <xref:System.Windows.Forms.ToolStripItem> si comportano come gli altri eventi di disegno del controllo.  
  
 Il <xref:System.Windows.Forms.ToolStrip> controlli forniscono anche accesso ottimizzato per il rendering degli elementi e contenitori tramite il <xref:System.Windows.Forms.ToolStripRenderer> (classe), che ha metodi sottoponibili a override per il disegno dello sfondo, sfondo dell'elemento, immagine di un elemento, elemento freccia, testo dell'elemento e il bordo del <xref:System.Windows.Forms.ToolStrip>. Gli argomenti dell'evento per questi metodi espongono diverse proprietà, ad esempio i rettangoli, colori e i formati di testo che è possibile modificare in base alle esigenze.  
  
 Per modificare alcuni aspetti del modo in cui viene disegnato un elemento, è in genere eseguire l'override di <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Se si sta scrivendo un nuovo elemento e si vuole controllare tutti gli aspetti del disegno, eseguire l'override di `OnPaint` (metodo). Dall'interno `OnPaint`, è possibile usare metodi dal <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Per impostazione predefinita, il <xref:System.Windows.Forms.ToolStrip> è double memorizzato nel buffer, sfruttando il <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> impostazione.  
  
#### <a name="parenting"></a>Genitorialità  
 Il concetto di proprietà e assegnazione di elementi padre del contenitore è più complesso in <xref:System.Windows.Forms.ToolStrip> controlla rispetto in altri controlli contenitore di Windows Form. Che è necessario per supportare scenari dinamici, ad esempio overflow, una condivisione di elementi di elenco a discesa in più <xref:System.Windows.Forms.ToolStrip> elementi e per supportare la generazione di un <xref:System.Windows.Forms.ContextMenuStrip> da un controllo.  
  
 Nell'elenco seguente vengono descritti i membri correlati a genitorialità e relativo utilizzo.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A> accede all'elemento che rappresenta l'origine dell'elemento di elenco a discesa. È simile alla <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, ma anziché restituire un controllo, viene restituito un <xref:System.Windows.Forms.ToolStripItem>.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A> Determina quale controllo è l'origine del <xref:System.Windows.Forms.ContextMenuStrip> quando più controlli condividono lo stesso <xref:System.Windows.Forms.ContextMenuStrip>.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A> è una funzione di accesso di sola lettura di <xref:System.Windows.Forms.ToolStripItem.Parent%2A> proprietà. Un elemento padre è diverso da un proprietario che un elemento padre indica l'oggetto corrente restituito <xref:System.Windows.Forms.ToolStrip> in cui l'elemento viene visualizzato, che potrebbe essere nell'area di overflow.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A> Restituisce il <xref:System.Windows.Forms.ToolStrip> la cui raccolta di elementi contiene corrente <xref:System.Windows.Forms.ToolStripItem>. Questo è il modo migliore per fare riferimento a <xref:System.Windows.Forms.ToolStrip.ImageList%2A> o altre proprietà di primo livello <xref:System.Windows.Forms.ToolStrip> senza scrivere codice speciale per gestire l'overflow.  
  
#### <a name="behavior-of-inherited-controls"></a>Comportamento dei controlli ereditati  
 I seguenti controlli sono bloccati ogni volta che vengono utilizzati nell'ereditarietà:  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel> che include i pannelli in una <xref:System.Windows.Forms.ToolStripContainer> e anche i singoli <xref:System.Windows.Forms.ToolStripPanel> controlli.  
  
 Ad esempio, creare una nuova applicazione Windows Forms utilizzando uno o più controlli nell'elenco precedente. Impostare il modificatore di accesso di uno o più controlli `public` o `protected`e quindi compilare il progetto. Aggiungere un form che eredita dal form prima e quindi selezionare un controllo ereditato. Viene visualizzato il controllo bloccato e si comporta come se fosse il modificatore di accesso `private`.  
  
#### <a name="toolstripcontainer-support-of-inheritance"></a>ToolStripContainer supporto dell'ereditarietà  
 Il <xref:System.Windows.Forms.ToolStripContainer> controllo supporta scenari di ereditarietà limitati, simili all'esempio seguente:  
  
1. Creare una nuova applicazione Windows Forms.  
  
2. Aggiungere un tipo <xref:System.Windows.Forms.ToolStripContainer> al form.  
  
3. Impostare il modificatore di accesso dei <xref:System.Windows.Forms.ToolStripContainer> al `public` o `protected`.  
  
4. Aggiungere qualsiasi combinazione di <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, e <xref:System.Windows.Forms.ContextMenuStrip> controlli per il <xref:System.Windows.Forms.ToolStripPanel> aree del <xref:System.Windows.Forms.ToolStripContainer>.  
  
5. Compilare il progetto.  
  
6. Aggiungere un form che eredita dal form prima.  
  
7. Selezionare il controllo ereditato <xref:System.Windows.Forms.ToolStripContainer> nel form.  
  
#### <a name="inherited-behavior-of-child-controls"></a>Ereditato il comportamento dei controlli figlio  
 Dopo aver completato i passaggi precedenti, ereditato si verifica quanto segue:  
  
-   Nella finestra di progettazione, il controllo viene visualizzato con un'icona ereditata.  
  
-   Il <xref:System.Windows.Forms.ToolStripPanel> controlli sono bloccati; non è possibile selezionare o ridisporre il relativo contenuto.  
  
-   È possibile aggiungere controlli per il <xref:System.Windows.Forms.ToolStripContentPanel>, spostare i controlli e renderle di controlli figlio di <xref:System.Windows.Forms.ToolStripContentPanel>.  
  
-   Le modifiche persistono dopo la compilazione del form.  
  
    > [!NOTE]
    >  Rimuovere i modificatori di accesso da tutti i <xref:System.Windows.Forms.ToolStripPanel> controlli che fanno parte di un <xref:System.Windows.Forms.ToolStripContainer>. Il modificatore di accesso del <xref:System.Windows.Forms.ToolStripContainer> governa l'intero controllo.  
  
#### <a name="partial-trust"></a>Attendibilità parziale  
 Le limitazioni di `ToolStrip`con attendibilità parziale sono progettati per impedire l'immissione accidentale di informazioni personali che potrebbero essere utilizzate da persone non autorizzate o servizi. Le misure di protezione sono i seguenti:  
  
-   `ToolStripDropDown` i controlli richiedono <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> per visualizzare gli elementi in un <xref:System.Windows.Forms.ToolStripControlHost>. Questo vale per i controlli intrinseci, ad esempio <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>, e <xref:System.Windows.Forms.ToolStripProgressBar> come controlli nonché alle creati dall'utente. Se questo requisito non viene soddisfatta, questi elementi non vengono visualizzati. Non viene generata alcuna eccezione.  
  
-   Impostando il <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> proprietà `false` non è consentita e l'annullabile <xref:System.Windows.Forms.ToolStripDropDown.Closing> evento parametro viene ignorato. Ciò rende Impossibile immettere più di una sequenza di tasti senza chiudere l'elemento di elenco a discesa. Se questo requisito non viene soddisfatta, tali elementi non vengono visualizzati. Non viene generata alcuna eccezione.  
  
-   Gestione degli eventi molti sequenze di tasti non verrà generato se si verificano in contesti con attendibilità parziale diverso da <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>.  
  
-   Le chiavi di accesso non vengono elaborati quando <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> non è stata concessa.  
  
#### <a name="usage"></a>Utilizzo  
 I modelli di utilizzo seguenti hanno un impatto <xref:System.Windows.Forms.ToolStrip> layout, l'interazione di tastiera e il comportamento degli utenti finali:  
  
-   Aggiunto un <xref:System.Windows.Forms.ToolStripPanel>  
  
     Il <xref:System.Windows.Forms.ToolStrip> può essere riposizionato all'interno di <xref:System.Windows.Forms.ToolStripPanel> e tra i controlli <xref:System.Windows.Forms.ToolStripPanel>s. Il `Dock` proprietà viene ignorata e se il <xref:System.Windows.Forms.ToolStrip.Stretch%2A> proprietà è `false`, alle dimensioni del <xref:System.Windows.Forms.ToolStrip> aumenta man mano che gli elementi vengono aggiunti al <xref:System.Windows.Forms.ToolStripPanel>. In genere, il <xref:System.Windows.Forms.ToolStrip> non fa parte l'ordine di tabulazione.  
  
-   Ancorato  
  
     Il <xref:System.Windows.Forms.ToolStrip> viene posizionato su un lato di un contenitore in una posizione fissa e e consente di espandere le dimensioni sul bordo dell'intero a cui è ancorata. In genere, il <xref:System.Windows.Forms.ToolStrip> non fa parte l'ordine di tabulazione.  
  
-   Posizionati in modo assoluto  
  
     Il <xref:System.Windows.Forms.ToolStrip> è simile ad altri controlli, in quanto viene inserito dal <xref:System.Windows.Forms.Control.Location%2A> proprietà, ha una dimensione fissa e in genere partecipa nell'ordine di tabulazione.  
  
#### <a name="keyboard-interaction"></a>Interazione della tastiera  
  
##### <a name="access-keys"></a>Chiavi di accesso  
 Chiavi di accesso combinato con o in seguito il tasto ALT, sono un modo per attivare un controllo con la tastiera. <xref:System.Windows.Forms.ToolStrip> supporta le chiavi di accesso esplicite e implicite. Definizione esplicita viene utilizzato un carattere e commerciale (&) che precede la lettera. Definizione implicita viene utilizzato un algoritmo che tenta di trovare un elemento corrispondente in base all'ordine dei caratteri in un determinato `Text` proprietà.  
  
##### <a name="shortcut-keys"></a>Tasti di scelta rapida  
 Tasti di scelta rapida utilizzati da un <xref:System.Windows.Forms.MenuStrip> usare una combinazione del <xref:System.Windows.Forms.Keys> enumerazione, ovvero non specifici dell'ordine, per definire il tasto di scelta rapida. È anche possibile usare il <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> proprietà per visualizzare un tasto di scelta rapida con solo testo, ad esempio visualizzando "CANC" anziché "Delete".  
  
##### <a name="navigation"></a>Navigazione  
 Il tasto ALT attiva i <xref:System.Windows.Forms.MenuStrip> a cui punta <xref:System.Windows.Forms.Form.MainMenuStrip%2A>. Da qui, CTRL + TAB consente di spostarsi tra <xref:System.Windows.Forms.ToolStrip> controlli all'interno di `ToolStripPanel`s. Il tasto TAB e i tasti di direzione del tastierino numerico consentono di spostarsi tra gli elementi in un <xref:System.Windows.Forms.ToolStrip>. Un algoritmo particolare gestisce lo spostamento nell'area di overflow. Barra spaziatrice seleziona una <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, o <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
##### <a name="focus-and-validation"></a>Lo stato attivo e convalida  
 Se attivato tramite il tasto ALT, il <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ToolStrip> in genere non eseguire né rimuovere lo stato attivo dal controllo attualmente con lo stato attivo. Se è disponibile un controllo ospitato all'interno di <xref:System.Windows.Forms.MenuStrip> o un elenco a discesa del <xref:System.Windows.Forms.MenuStrip>, il controllo riceve lo stato attivo quando l'utente preme il tasto TAB. In generale, il <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter>, e <xref:System.Windows.Forms.Control.Leave> gli eventi di <xref:System.Windows.Forms.MenuStrip> non vengano generati quando vengono attivati da tastiera. In questi casi, usare il <xref:System.Windows.Forms.MenuStrip.MenuActivate> e <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> eventi invece.  
  
 Per impostazione predefinita <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> è `false`. Chiamare <xref:System.Windows.Forms.ContainerControl.Validate%2A> in modo esplicito sul form per eseguire la convalida.  
  
#### <a name="layout"></a>Layout  
 Controllano <xref:System.Windows.Forms.ToolStrip> layout scegliendo uno dei membri di <xref:System.Windows.Forms.ToolStripLayoutStyle> con il <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> proprietà.  
  
##### <a name="stack-layouts"></a>Layout di stack  
 Impilamento è la disposizione degli elementi adiacenti a entrambe le estremità del <xref:System.Windows.Forms.ToolStrip>. L'elenco seguente descrive i layout di stack.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow> è il valore predefinito. Questa impostazione fa in modo che il <xref:System.Windows.Forms.ToolStrip> per modificare il layout automaticamente in base al <xref:System.Windows.Forms.ToolStrip.Orientation%2A> proprietà per gestire il trascinamento e gli scenari di ancoraggio.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow> esegue il rendering di <xref:System.Windows.Forms.ToolStrip> elementi verticalmente accanto a altro.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow> esegue il rendering di <xref:System.Windows.Forms.ToolStrip> elementi accanto a altro in senso orizzontale.  
  
##### <a name="other-features-of-stack-layouts"></a>Altre funzionalità di layout di Stack  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> Determina la fine del <xref:System.Windows.Forms.ToolStrip> a cui l'elemento è allineato.  
  
 Quando gli elementi non corrispondono all'interno di <xref:System.Windows.Forms.ToolStrip>, viene automaticamente visualizzato un pulsante di overflow. Il <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> l'impostazione della proprietà determina se un elemento deve essere visualizzato nell'area di overflow, in base alle esigenze o mai.  
  
 Nel <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento, è possibile esaminare il <xref:System.Windows.Forms.ToolStripItem.Placement%2A> proprietà per determinare se un elemento è stato inserito nella classe principale <xref:System.Windows.Forms.ToolStrip>, l'overflow <xref:System.Windows.Forms.ToolStrip>, o se non è visualizzato affatto. Le cause tipiche perché non viene visualizzato un elemento sono che sul principale non è sufficienti per l'elemento <xref:System.Windows.Forms.ToolStrip> e la relativa <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> è stata impostata su <xref:System.Windows.Forms.ToolStripItemOverflow.Never>.  
  
 Rendere un <xref:System.Windows.Forms.ToolStrip> mobile inserendolo un <xref:System.Windows.Forms.ToolStripPanel> e l'impostazione relativa <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> a <xref:System.Windows.Forms.ToolStripGripStyle.Visible>.  
  
##### <a name="other-layout-options"></a>Altre opzioni di Layout  
 Le altre opzioni di layout sono <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> e <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>.  
  
##### <a name="flow-layout"></a>Layout di flusso  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> layout è quello predefinito per <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, e <xref:System.Windows.Forms.ToolStripOverflow>. È simile al <xref:System.Windows.Forms.FlowLayoutPanel>. Le funzionalità di <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> layout sono i seguenti:  
  
-   Tutte le funzionalità del <xref:System.Windows.Forms.FlowLayoutPanel> esposte dal <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> proprietà. È necessario eseguire il cast di <xref:System.Windows.Forms.LayoutSettings> classe a un <xref:System.Windows.Forms.FlowLayoutSettings> classe.  
  
-   È possibile usare la <xref:System.Windows.Forms.ToolStripItem.Dock%2A> e <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> proprietà nel codice per allineare gli elementi all'interno della riga.  
  
-   La proprietà <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> viene ignorata.  
  
-   Nel <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento, è possibile esaminare il <xref:System.Windows.Forms.ToolStripItem.Placement%2A> proprietà per determinare se un elemento è stato inserito nell'oggetto principale <xref:System.Windows.Forms.ToolStrip> o non sono sufficienti.  
  
-   Il triangolo di ridimensionamento non viene eseguito il rendering e pertanto una <xref:System.Windows.Forms.ToolStrip> nelle <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> stile di layout in un <xref:System.Windows.Forms.ToolStripPanel> non può essere spostato.  
  
-   Il <xref:System.Windows.Forms.ToolStrip> pulsante di overflow non viene eseguito il rendering, e <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> viene ignorato.  
  
##### <a name="table-layout"></a>Layout tabella  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> layout è quello predefinito <xref:System.Windows.Forms.StatusStrip>. È simile a <xref:System.Windows.Forms.TableLayoutPanel>. Le funzionalità di <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> layout sono i seguenti:  
  
-   Tutte le funzionalità del <xref:System.Windows.Forms.TableLayoutPanel> esposte dal <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> proprietà. È necessario eseguire il cast di <xref:System.Windows.Forms.LayoutSettings> classe a un <xref:System.Windows.Forms.TableLayoutSettings> classe.  
  
-   È possibile usare la <xref:System.Windows.Forms.ToolStripItem.Dock%2A> e <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> proprietà nel codice per allineare gli elementi all'interno della cella di tabella.  
  
-   La proprietà <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> viene ignorata.  
  
-   Nel <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento, è possibile esaminare il <xref:System.Windows.Forms.ToolStripItem.Placement%2A> proprietà per determinare se un elemento è stato inserito nell'oggetto principale <xref:System.Windows.Forms.ToolStrip> o non sono sufficienti.  
  
-   Il triangolo di ridimensionamento non viene eseguito il rendering e pertanto una <xref:System.Windows.Forms.ToolStrip> nelle <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> stile di layout in un <xref:System.Windows.Forms.ToolStripPanel> non può essere spostato.  
  
-   Il <xref:System.Windows.Forms.ToolStrip> pulsante di overflow non viene eseguito il rendering, e <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> viene ignorato.  
  
## <a name="toolstripitem"></a>ToolStripItem  
 Gli argomenti seguenti descrivono <xref:System.Windows.Forms.ToolStripItem> e i controlli che derivano da essa.  
  
 <xref:System.Windows.Forms.ToolStripItem> è la classe base astratta per tutti gli elementi che costituiscono un <xref:System.Windows.Forms.ToolStrip>. L'oggetto seguente modello Mostra il <xref:System.Windows.Forms.ToolStripItem> gerarchia di ereditarietà.  
  
 ![Diagramma che mostra il modello a oggetti ToolStripItem.](./media/toolstrip-control-architecture/toolstripitem-object-model.gif)  
  
 <xref:System.Windows.Forms.ToolStripItem> classi di ereditare direttamente da <xref:System.Windows.Forms.ToolStripItem>, o ereditare indirettamente <xref:System.Windows.Forms.ToolStripItem> attraverso <xref:System.Windows.Forms.ToolStripControlHost> o <xref:System.Windows.Forms.ToolStripDropDownItem>.  
  
 <xref:System.Windows.Forms.ToolStripItem> i controlli devono essere contenuti in un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, o <xref:System.Windows.Forms.ContextMenuStrip> e non possono essere aggiunti direttamente a un form. Le varie classi di contenitori sono progettate per contenere un sottoinsieme appropriato di <xref:System.Windows.Forms.ToolStripItem> controlli.  
  
 La tabella seguente elenca le scorte <xref:System.Windows.Forms.ToolStripItem> controlli e i contenitori in cui sono più appropriati. Anche se uno qualsiasi <xref:System.Windows.Forms.ToolStrip> elemento possa essere ospitato in qualsiasi <xref:System.Windows.Forms.ToolStrip>-contenitore, derivato questi elementi sono stati progettati per essere inserito in contenitori seguenti:  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown> non viene visualizzato nella casella degli strumenti della finestra di progettazione.  
  
|Elemento contenuto|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|  
|<xref:System.Windows.Forms.ToolStripButton>|Yes|No|No|No|Yes|  
|<xref:System.Windows.Forms.ToolStripComboBox>|Yes|Yes|Yes|No|Yes|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|Yes|No|No|Yes|Yes|  
|<xref:System.Windows.Forms.ToolStripLabel>|Yes|No|No|Yes|Yes|  
|<xref:System.Windows.Forms.ToolStripSeparator>|Yes|Yes|Yes|No|Yes|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Yes|No|No|Yes|Yes|  
|<xref:System.Windows.Forms.ToolStripTextBox>|Yes|Yes|Yes|No|Sì|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|No|Yes|Yes|No|No|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|No|No|No|Sì|No|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|Sì|No|No|Sì|No|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Yes|Yes|No|Yes|Yes|  
  
### <a name="toolstripbutton"></a>ToolStripButton  
 <xref:System.Windows.Forms.ToolStripButton> è l'elemento pulsante <xref:System.Windows.Forms.ToolStrip>. È possibile visualizzarla con vari stili di bordo ed è possibile usarlo per rappresentare e attivare gli stati operativi. È anche possibile definire in modo che abbia lo stato attivo per impostazione predefinita.  
  
### <a name="toolstriplabel"></a>ToolStripLabel  
 Il <xref:System.Windows.Forms.ToolStripLabel> fornisce funzionalità di etichetta in <xref:System.Windows.Forms.ToolStrip> controlli. Il <xref:System.Windows.Forms.ToolStripLabel> è simile a un <xref:System.Windows.Forms.ToolStripButton> che non riceve lo stato attivo per impostazione predefinita e non sottoposto a rendering come premuto o evidenziato.  
  
 <xref:System.Windows.Forms.ToolStripLabel> come un elemento host supporta le chiavi di accesso.  
  
 Usare la <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>, e <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> delle proprietà in un <xref:System.Windows.Forms.ToolStripLabel> per supportare il controllo di collegamento in un <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel> è una versione di <xref:System.Windows.Forms.ToolStripLabel> progettata appositamente per l'utilizzo in <xref:System.Windows.Forms.StatusStrip>. Le funzionalità speciali includono <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>, e <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
### <a name="toolstripseparator"></a>ToolStripSeparator  
 Il <xref:System.Windows.Forms.ToolStripSeparator> aggiunge una linea verticale oppure orizzontale a una barra degli strumenti o menu, a seconda dell'orientamento. Fornisce il raggruppamento o distinguere tra elementi, ad esempio quelli di un menu.  
  
 È possibile aggiungere un <xref:System.Windows.Forms.ToolStripSeparator> in fase di progettazione selezionandolo dall'elenco elenco a discesa. Tuttavia, è anche possibile creare automaticamente un <xref:System.Windows.Forms.ToolStripSeparator> digitando un segno meno (-) nel nodo modello della finestra di progettazione o nel <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> (metodo).  
  
### <a name="toolstripcontrolhost"></a>ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost> è la classe base astratta per <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>, e <xref:System.Windows.Forms.ToolStripProgressBar>. <xref:System.Windows.Forms.ToolStripControlHost> può ospitare altri controlli, inclusi i controlli personalizzati, in due modi:  
  
-   Creare un <xref:System.Windows.Forms.ToolStripControlHost> con una classe che deriva da <xref:System.Windows.Forms.Control>. Per un accesso completo al controllo contenuto e le proprietà, è necessario eseguire il cast di <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> proprietà per l'effettivo della classe rappresenta.  
  
-   Estendere <xref:System.Windows.Forms.ToolStripControlHost>e nel costruttore predefinito della classe ereditata, chiamare il costruttore di classe di base passando a una classe che deriva da <xref:System.Windows.Forms.Control>. Questa opzione consente di eseguire il wrapping di metodi di controllo comuni e proprietà per semplificare l'accesso in un <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripcombobox"></a>ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox> è il <xref:System.Windows.Forms.ComboBox> ottimizzata per l'hosting in un <xref:System.Windows.Forms.ToolStrip>. Un subset di proprietà ed eventi del controllo ospitato sono esposti al <xref:System.Windows.Forms.ToolStripComboBox> livello, ma sottostante <xref:System.Windows.Forms.ComboBox> controllo risulta accessibile tramite il <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> proprietà.  
  
### <a name="toolstriptextbox"></a>ToolStripTextBox  
 <xref:System.Windows.Forms.ToolStripTextBox> è il <xref:System.Windows.Forms.TextBox> ottimizzata per l'hosting in un <xref:System.Windows.Forms.ToolStrip>. Un subset di proprietà ed eventi del controllo ospitato sono esposti al <xref:System.Windows.Forms.ToolStripTextBox> livello, ma sottostante <xref:System.Windows.Forms.TextBox> controllo risulta accessibile tramite il <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> proprietà.  
  
### <a name="toolstripprogressbar"></a>ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar> è il <xref:System.Windows.Forms.ProgressBar> ottimizzata per l'hosting in un <xref:System.Windows.Forms.ToolStrip>. Un subset di proprietà ed eventi del controllo ospitato sono esposti al <xref:System.Windows.Forms.ToolStripProgressBar> livello, ma sottostante <xref:System.Windows.Forms.ProgressBar> controllo risulta accessibile tramite il <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> proprietà.  
  
### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem> è la classe base astratta per <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton>, e <xref:System.Windows.Forms.ToolStripSplitButton>, che possono ospitare direttamente gli elementi o elementi di altri host in un contenitore di elenco a discesa. A questo scopo, impostare il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> proprietà per un <xref:System.Windows.Forms.ToolStripDropDown> e impostando il <xref:System.Windows.Forms.ToolStrip.Items%2A> proprietà del <xref:System.Windows.Forms.ToolStripDropDown>. Accedere a questi elementi di elenco a discesa direttamente tramiti il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> proprietà.  
  
### <a name="toolstripmenuitem"></a>ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem> è un <xref:System.Windows.Forms.ToolStripDropDownItem> che interagisce con <xref:System.Windows.Forms.ToolStripDropDownMenu> e <xref:System.Windows.Forms.ContextMenuStrip> per gestire la disposizione di colonna, layout e l'evidenziazione speciale per i menu.  
  
### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton> aspetto <xref:System.Windows.Forms.ToolStripButton>, ma mostra un'area di riepilogo a discesa quando viene selezionato dall'utente. Visualizzare o nascondere la freccia giù, impostando il <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> proprietà. <xref:System.Windows.Forms.ToolStripDropDownButton> Ospita una <xref:System.Windows.Forms.ToolStripOverflowButton> che consente di visualizzare gli elementi di overflow di <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripsplitbutton"></a>ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton> Combina le funzionalità di pulsante e pulsante a discesa.  
  
 Usare la <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> proprietà per sincronizzare il <xref:System.Windows.Forms.Control.Click> evento della voce di elenco a discesa scelta con l'elemento visualizzato sul pulsante.  
  
### <a name="toolstripitem-generic-features"></a>Funzionalità generiche di ToolStripItem  
 <xref:System.Windows.Forms.ToolStripItem> fornisce le seguenti funzionalità generiche e le opzioni per i controlli che ereditano:  
  
-   Eventi principali  
  
-   Gestione delle immagini  
  
-   Allineamento  
  
-   Relazione di tipo text e image  
  
-   Stile di visualizzazione  
  
#### <a name="core-events"></a>Eventi principali  
 <xref:System.Windows.Forms.ToolStripItem> controlli ricevono le proprie risorse, mouse e gli eventi di disegno fare clic su e possono eseguire qualche pre-elaborazione anche dalla tastiera.  
  
#### <a name="image-handling"></a>Gestione delle immagini  
 Il <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>, e <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> riguardano i vari aspetti della gestione delle immagini. Utilizzare le immagini nei <xref:System.Windows.Forms.ToolStrip> controlli impostando direttamente queste proprietà o impostando l'esecuzione solo in fase di <xref:System.Windows.Forms.ToolStrip.ImageList%2A> proprietà.  
  
 Il ridimensionamento delle immagini è determinato dall'interazione delle proprietà in entrambe <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.ToolStripItem>, come indicato di seguito:  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A> rappresenta la scala dell'immagine finale, come determinato dalla combinazione dell'immagine <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> impostazione e il contenitore <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> impostazione.  
  
    -   Se <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> viene `true` (predefinito) e <xref:System.Windows.Forms.ToolStripItemImageScaling> viene <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>, si verifica alcun ridimensionamento immagine e il <xref:System.Windows.Forms.ToolStrip> dimensioni sono quello dell'elemento più grande o prescritta dimensioni minime.  
  
    -   Se <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> viene `false` e <xref:System.Windows.Forms.ToolStripItemImageScaling> viene <xref:System.Windows.Forms.ToolStripItemImageScaling.None>, nessuno dei due immagini né <xref:System.Windows.Forms.ToolStrip> il ridimensionamento viene eseguito.  
  
#### <a name="alignment"></a>Allineamento  
 Il valore della <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> proprietà determina la fine del <xref:System.Windows.Forms.ToolStrip> in cui viene visualizzato un elemento. Il <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> proprietà viene utilizzata solo quando lo stile di layout del <xref:System.Windows.Forms.ToolStrip> è impostato su uno dei valori di overflow dello stack.  
  
 Gli elementi vengono inseriti nel <xref:System.Windows.Forms.ToolStrip> nell'ordine in cui vengono visualizzati gli elementi della raccolta di elementi. Per modificare a livello di codice in cui viene disposta un elemento, usare il <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> metodo per spostare l'elemento nella raccolta. Questo metodo consente di spostare l'elemento ma non duplicarla.  
  
#### <a name="text-and-image-relationship"></a>Testo e immagine relazione  
 Il <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> proprietà definisce la posizione relativa dell'immagine rispetto al testo su un <xref:System.Windows.Forms.ToolStripItem>. Gli elementi che non dispongono di un'immagine, testo o entrambi sono considerati come casi particolari, in modo che il <xref:System.Windows.Forms.ToolStripItem> non visualizzi un'area vuota per gli elementi mancanti.  
  
#### <a name="display-style"></a>Stile di visualizzazione  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> Consente di impostare i valori delle proprietà di testo e immagine di un elemento mentre si visualizza solo gli elementi desiderati. Ciò in genere consente di modificare lo stile di visualizzazione quando viene visualizzato lo stesso elemento in un contesto diverso.  
  
## <a name="accessory-classes"></a>Classi degli accessori  
 Le classi che forniscono varie altre funzionalità includono:  
  
-   <xref:System.Windows.Forms.ToolStripManager> supporta <xref:System.Windows.Forms.ToolStrip>-attività per l'intera applicazione, ad esempio le opzioni di unione, le impostazioni e renderer correlate.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> è possibile applicare uno stile specifico o un tema a un <xref:System.Windows.Forms.ToolStrip> facilmente.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> Consente di creare penne e pennelli basate su una tabella dei colori sostituibile (<xref:System.Windows.Forms.ProfessionalColorTable>).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> Applica i colori di sistema e uno stile di visualizzazione bidimensionale di <xref:System.Windows.Forms.ToolStrip> applicazioni.  
  
-   <xref:System.Windows.Forms.ToolStripContainer> è simile a <xref:System.Windows.Forms.SplitContainer>. Usa quattro pannelli ancorati lato (istanze di <xref:System.Windows.Forms.ToolStripPanel>) e un pannello centrale (un'istanza di <xref:System.Windows.Forms.ToolStripContentPanel>) per creare una disposizione tipica. Non è possibile rimuovere i pannelli lato, ma è possibile nasconderle. Non è possibile rimuovere né nascondere il pannello centrale. È possibile disporre di uno o più <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, o <xref:System.Windows.Forms.StatusStrip> controlli nei pannelli di lato e si possono usare il pannello centrale per altri controlli. Il <xref:System.Windows.Forms.ToolStripContentPanel> fornisce inoltre un modo per ottenere supporto dei renderer nel corpo del form per un aspetto coerente. <xref:System.Windows.Forms.ToolStripContainer> non supporta l'interfaccia a documenti multipli (MDI).  
  
-   <xref:System.Windows.Forms.ToolStripPanel> fornisce lo spazio per lo spostamento e la disposizione <xref:System.Windows.Forms.ToolStrip> controlli. È possibile usare un solo pannello se si sceglie, e <xref:System.Windows.Forms.ToolStripPanel> funziona bene in scenari MDI.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)
- [Controllo ToolStrip](toolstrip-control-windows-forms.md)
- [Controllo MenuStrip](menustrip-control-windows-forms.md)
- [Controllo StatusStrip](statusstrip-control.md)
- [Controllo ContextMenuStrip](contextmenustrip-control.md)
- [Controllo BindingNavigator](bindingnavigator-control-windows-forms.md)
