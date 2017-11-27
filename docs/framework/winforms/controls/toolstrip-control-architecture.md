---
title: Architettura del controllo ToolStrip
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
caps.latest.revision: "32"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6884598e6b883ab5e6369be5f2f796a194c7f930
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="toolstrip-control-architecture"></a>Architettura del controllo ToolStrip
Il <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.ToolStripItem> classi forniscono un sistema flessibile ed estendibile per la visualizzazione di elementi della barra degli strumenti, stato e menu. Queste classi sono contenute nel <xref:System.Windows.Forms> dello spazio dei nomi e sono tutti in genere denominati con il prefisso "ToolStrip" (ad esempio <xref:System.Windows.Forms.ToolStripOverflow>) o con il suffisso "Strip" (ad esempio <xref:System.Windows.Forms.MenuStrip>).  
  
## <a name="toolstrip"></a>ToolStrip  
 Gli argomenti seguenti descrivono <xref:System.Windows.Forms.ToolStrip> e i controlli che derivano da essa.  
  
 <xref:System.Windows.Forms.ToolStrip>è la classe base astratta per <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, e <xref:System.Windows.Forms.ContextMenuStrip>. L'oggetto seguente modello Mostra il <xref:System.Windows.Forms.ToolStrip> gerarchia di ereditarietà.  
  
 ![Modello a oggetti ToolStrip](../../../../docs/framework/winforms/controls/media/toolstripobjectmodel.gif "ToolStripObjectModel")  
Modello a oggetti ToolStrip  
  
 È possibile accedere a tutti gli elementi di un <xref:System.Windows.Forms.ToolStrip> tramite il <xref:System.Windows.Forms.ToolStrip.Items%2A> insieme. È possibile accedere a tutti gli elementi di un <xref:System.Windows.Forms.ToolStripDropDownItem> tramite il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> insieme. In una classe derivata da <xref:System.Windows.Forms.ToolStrip>, è inoltre possibile utilizzare il <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> proprietà per accedere solo agli elementi che sono attualmente visualizzati. Questi sono gli elementi che non sono attualmente in un menu di overflow.  
  
 Gli elementi seguenti sono progettati per integrarsi perfettamente con entrambi <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per il <xref:System.Windows.Forms.ToolStrip> controllo:  
  
-   <xref:System.Windows.Forms.ToolStripButton>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="menustrip"></a>MenuStrip  
 <xref:System.Windows.Forms.MenuStrip>è il contenitore di livello superiore che sostituisce <xref:System.Windows.Forms.MainMenu>. Oltre a funzionalità chiave e gestione interface (MDI). A livello funzionale, <xref:System.Windows.Forms.ToolStripDropDownItem> e <xref:System.Windows.Forms.ToolStripMenuItem> funzionano insieme a <xref:System.Windows.Forms.MenuStrip>, sebbene derivino da <xref:System.Windows.Forms.ToolStripItem>.  
  
 Gli elementi seguenti sono progettati per integrarsi perfettamente con entrambi <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per il <xref:System.Windows.Forms.MenuStrip> controllo:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="statusstrip"></a>StatusStrip  
 <xref:System.Windows.Forms.StatusStrip>sostituisce il <xref:System.Windows.Forms.StatusBar> controllo. Le funzionalità speciali di <xref:System.Windows.Forms.StatusStrip> includono un layout di tabella personalizzata, il supporto per il ridimensionamento del form e spostando i riquadri e `Spring` proprietà, che consente un <xref:System.Windows.Forms.ToolStripStatusLabel> per riempire lo spazio disponibile automaticamente.  
  
 Gli elementi seguenti sono progettati per integrarsi perfettamente con entrambi <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per il <xref:System.Windows.Forms.StatusStrip> controllo:  
  
-   <xref:System.Windows.Forms.ToolStripStatusLabel>  
  
-   <xref:System.Windows.Forms.ToolStripDropDownButton>  
  
-   <xref:System.Windows.Forms.ToolStripSplitButton>  
  
-   <xref:System.Windows.Forms.ToolStripProgressBar>  
  
### <a name="contextmenustrip"></a>ContextMenuStrip  
 <xref:System.Windows.Forms.ContextMenuStrip>sostituisce <xref:System.Windows.Forms.ContextMenu>. È possibile associare un <xref:System.Windows.Forms.ContextMenuStrip> con qualsiasi controllo e destro del mouse fare clic su Visualizza automaticamente il menu di contesto (o di menu di scelta rapida). È possibile visualizzare un <xref:System.Windows.Forms.ContextMenuStrip> a livello di codice utilizzando il <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> metodo. <xref:System.Windows.Forms.ContextMenuStrip>supporta annullabile <xref:System.Windows.Forms.ToolStripDropDown.Opening> e <xref:System.Windows.Forms.ToolStripDropDown.Closing> eventi per gestire la compilazione dinamica e scenari a selezione multipla. <xref:System.Windows.Forms.ContextMenuStrip>supporta le immagini, lo stato di controllo voce di menu, testo, tasti di scelta, collegamenti e menu a discesa.  
  
 Gli elementi seguenti sono progettati per integrarsi perfettamente con entrambi <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer> in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per il <xref:System.Windows.Forms.ContextMenuStrip> controllo:  
  
-   <xref:System.Windows.Forms.ToolStripMenuItem>  
  
-   <xref:System.Windows.Forms.ToolStripSeparator>  
  
-   <xref:System.Windows.Forms.ToolStripTextBox>  
  
-   <xref:System.Windows.Forms.ToolStripComboBox>  
  
### <a name="toolstrip-generic-features"></a>Funzionalità generiche di ToolStrip  
 Gli argomenti seguenti descrivono le funzionalità e il comportamento che sono generici per la <xref:System.Windows.Forms.ToolStrip> e i controlli derivati.  
  
#### <a name="painting"></a>Disegno  
 È possibile eseguire il disegno personalizzato nel <xref:System.Windows.Forms.ToolStrip> controlli in vari modi. Come con altri controlli Windows Form, il <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.ToolStripItem> prevedono sottoponibile a override `OnPaint` metodi e `Paint` eventi. Come per il disegno standard, il sistema di coordinate relative all'area client del controllo. l'angolo superiore sinistro del controllo è 0, 0. Il `Paint` evento e `OnPaint` metodo per un <xref:System.Windows.Forms.ToolStripItem> si comportano come gli altri eventi di disegno del controllo.  
  
 Il <xref:System.Windows.Forms.ToolStrip> controlli forniscono anche accesso ottimizzato per il rendering degli elementi e contenitore, tramite il <xref:System.Windows.Forms.ToolStripRenderer> (classe), che ha metodi sottoponibili a override per il disegno di sfondo, sfondo di un elemento, elemento immagine, freccia di elemento, testo dell'elemento e il bordo del <xref:System.Windows.Forms.ToolStrip>. Gli argomenti dell'evento per questi metodi espongono diverse proprietà, quali rettangoli, colori e formati di testo che è possibile modificare come desiderato.  
  
 Per modificare solo alcuni aspetti della modalità di disegno di un elemento, è in genere eseguire l'override di <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Se si sta scrivendo un nuovo elemento e si desidera controllare tutti gli aspetti del disegno, eseguire l'override di `OnPaint` metodo. Dall'interno `OnPaint`, è possibile utilizzare i metodi di <xref:System.Windows.Forms.ToolStripRenderer>.  
  
 Per impostazione predefinita, il <xref:System.Windows.Forms.ToolStrip> viene applicato il doppio buffer, sfruttando la possibilità del <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> impostazione.  
  
#### <a name="parenting"></a>Relazione padre-figlio  
 Il concetto di proprietà e l'elemento padre del contenitore è più complesso in <xref:System.Windows.Forms.ToolStrip> i controlli di altri controlli contenitore di Windows Form. È necessario per supportare scenari dinamici, ad esempio overflow, una condivisione di elementi di elenco a discesa in più <xref:System.Windows.Forms.ToolStrip> elementi e per supportare la generazione di un <xref:System.Windows.Forms.ContextMenuStrip> da un controllo.  
  
 Nell'elenco seguente vengono descritti i membri correlati per elemento padre e il relativo utilizzo.  
  
-   <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A>accede all'elemento che rappresenta l'origine dell'elemento di elenco a discesa. È simile a <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>, ma anziché restituire un controllo, viene restituito un <xref:System.Windows.Forms.ToolStripItem>.  
  
-   <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>Determina quale controllo è l'origine del <xref:System.Windows.Forms.ContextMenuStrip> quando più controlli condividono lo stesso <xref:System.Windows.Forms.ContextMenuStrip>.  
  
-   <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A>è una funzione di accesso di sola lettura di <xref:System.Windows.Forms.ToolStripItem.Parent%2A> proprietà. Un elemento padre differisce da un proprietario che un elemento padre indica l'oggetto corrente restituito <xref:System.Windows.Forms.ToolStrip> in cui l'elemento viene visualizzata, che potrebbe essere nell'area di riversamento.  
  
-   <xref:System.Windows.Forms.ToolStripItem.Owner%2A>Restituisce il <xref:System.Windows.Forms.ToolStrip> la cui raccolta di elementi contiene corrente <xref:System.Windows.Forms.ToolStripItem>. Questo è il modo migliore per fare riferimento a <xref:System.Windows.Forms.ToolStrip.ImageList%2A> o altre proprietà di primo livello <xref:System.Windows.Forms.ToolStrip> senza scrivere codice speciale per gestire l'overflow.  
  
#### <a name="behavior-of-inherited-controls"></a>Comportamento dei controlli ereditati  
 Ogni volta che vengono utilizzati nell'ereditarietà, vengono bloccati i controlli seguenti:  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
-   <xref:System.Windows.Forms.MenuStrip>  
  
-   <xref:System.Windows.Forms.ContextMenuStrip>  
  
-   <xref:System.Windows.Forms.StatusStrip>  
  
-   <xref:System.Windows.Forms.ToolStripPanel>che include i pannelli in un <xref:System.Windows.Forms.ToolStripContainer> e anche i singoli <xref:System.Windows.Forms.ToolStripPanel> controlli.  
  
 Ad esempio, creare una nuova applicazione Windows Form utilizzando uno o più dei controlli nell'elenco precedente. Impostare il modificatore di accesso di uno o più controlli per `public` o `protected`e quindi compilare il progetto. Aggiungere un form che eredita dal form prima e quindi selezionare un controllo ereditato. Il controllo viene visualizzato bloccato, si comporta come se fosse il modificatore di accesso `private`.  
  
#### <a name="toolstripcontainer-support-of-inheritance"></a>Supporto di ToolStripContainer dell'ereditarietà  
 Il <xref:System.Windows.Forms.ToolStripContainer> controllo supporta scenari di ereditarietà limitati, simili all'esempio seguente:  
  
1.  Creare una nuova applicazione Windows Form.  
  
2.  Aggiungere un tipo <xref:System.Windows.Forms.ToolStripContainer> al form.  
  
3.  Impostare il modificatore di accesso del <xref:System.Windows.Forms.ToolStripContainer> a `public` o `protected`.  
  
4.  Aggiungere qualsiasi combinazione di <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, e <xref:System.Windows.Forms.ContextMenuStrip> controlli per il <xref:System.Windows.Forms.ToolStripPanel> le aree del <xref:System.Windows.Forms.ToolStripContainer>.  
  
5.  Compilare il progetto.  
  
6.  Aggiungere un form che eredita dal primo form.  
  
7.  Selezionare il controllo ereditato <xref:System.Windows.Forms.ToolStripContainer> nel form.  
  
#### <a name="inherited-behavior-of-child-controls"></a>Comportamento ereditato dei controlli figlio  
 Dopo aver completato i passaggi precedenti, si verifica il comportamento ereditato seguente:  
  
-   Nella finestra di progettazione, il controllo viene visualizzata un'icona ereditata.  
  
-   Il <xref:System.Windows.Forms.ToolStripPanel> controlli sono bloccati; non è possibile selezionare o ridisporre il relativo contenuto.  
  
-   È possibile aggiungere controlli al <xref:System.Windows.Forms.ToolStripContentPanel>, spostare i controlli e renderli di controlli figlio di <xref:System.Windows.Forms.ToolStripContentPanel>.  
  
-   Le modifiche vengono mantenute dopo la compilazione del form.  
  
    > [!NOTE]
    >  Rimuovere i modificatori di accesso da tutti i <xref:System.Windows.Forms.ToolStripPanel> controlli che fanno parte di un <xref:System.Windows.Forms.ToolStripContainer>. Il modificatore di accesso del <xref:System.Windows.Forms.ToolStripContainer> determina l'intero controllo.  
  
#### <a name="partial-trust"></a>Attendibilità parziale  
 Le limitazioni di `ToolStrip`con attendibilità parziale sono progettati per impedire l'immissione accidentale di informazioni personali che potrebbero essere utilizzate per gli utenti non autorizzati o servizi. Le misure di protezione sono i seguenti:  
  
-   `ToolStripDropDown`i controlli richiedono <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> per visualizzare gli elementi in un <xref:System.Windows.Forms.ToolStripControlHost>. Questo vale per i controlli intrinseci, ad esempio <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>, e <xref:System.Windows.Forms.ToolStripProgressBar> come controlli nonché creati dall'utente. Se questo requisito non viene soddisfatta, è possibile che questi elementi non vengono visualizzati. Non viene generata alcuna eccezione.  
  
-   L'impostazione di <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> proprietà `false` non è consentito e l'annullabile <xref:System.Windows.Forms.ToolStripDropDown.Closing> evento parametro viene ignorato. Questo rende Impossibile immettere più di una sequenza di tasti senza chiudere l'elemento di elenco a discesa. Se questo requisito non viene soddisfatta, è possibile che tali elementi non vengono visualizzati. Non viene generata alcuna eccezione.  
  
-   Gestione degli eventi molti sequenze di tasti non verrà generato se si verificano in contesti con attendibilità parziale, diverso da <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>.  
  
-   Chiavi di accesso non sono elaborate quando <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> non è stata concessa.  
  
#### <a name="usage"></a>Utilizzo  
 Modelli di utilizzo seguenti abbiano conseguenze sulla <xref:System.Windows.Forms.ToolStrip> layout, l'interazione di tastiera e il comportamento dell'utente finale:  
  
-   Unite in join in una<xref:System.Windows.Forms.ToolStripPanel>  
  
     Il <xref:System.Windows.Forms.ToolStrip> può essere riposizionato all'interno di <xref:System.Windows.Forms.ToolStripPanel> e attraverso <xref:System.Windows.Forms.ToolStripPanel>s. Il `Dock` proprietà viene ignorata e se il <xref:System.Windows.Forms.ToolStrip.Stretch%2A> proprietà è `false`, la dimensione il <xref:System.Windows.Forms.ToolStrip> aumentano quando vengono aggiunti elementi il <xref:System.Windows.Forms.ToolStripPanel>. In genere, il <xref:System.Windows.Forms.ToolStrip> non fa parte nell'ordine di tabulazione.  
  
-   Ancorato  
  
     Il <xref:System.Windows.Forms.ToolStrip> viene posizionato su un lato di un contenitore in una posizione fissa, le relative dimensioni si espandono in tutto il bordo a cui è ancorata. In genere, il <xref:System.Windows.Forms.ToolStrip> non fa parte nell'ordine di tabulazione.  
  
-   Posizionati  
  
     Il <xref:System.Windows.Forms.ToolStrip> è simile ad altri controlli, in quanto viene inserito dal <xref:System.Windows.Forms.Control.Location%2A> ha dimensioni fisse, proprietà e in genere partecipa nell'ordine di tabulazione.  
  
#### <a name="keyboard-interaction"></a>Interazione della tastiera  
  
##### <a name="access-keys"></a>Chiavi di accesso  
 In combinazione con o dopo il tasto ALT, chiavi di accesso sono un modo per attivare un controllo tramite la tastiera. <xref:System.Windows.Forms.ToolStrip>supporta entrambe le chiavi di accesso esplicite e implicite. Definizione esplicita utilizza una e commerciale (&) alla lettera precedente. La definizione implicita viene utilizzato un algoritmo che tenta di trovare un elemento corrispondente in base all'ordine dei caratteri in un determinato `Text` proprietà.  
  
##### <a name="shortcut-keys"></a>Tasti di scelta rapida  
 Tasti di scelta rapida utilizzati da un <xref:System.Windows.Forms.MenuStrip> utilizzare una combinazione del <xref:System.Windows.Forms.Keys> enumerazione (che non è specifico dell'ordine) per definire il tasto di scelta rapida. È inoltre possibile utilizzare il <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> proprietà per visualizzare un tasto di scelta rapida con solo testo, ad esempio che visualizza "CANC" anziché "Elimina".  
  
##### <a name="navigation"></a>Navigazione  
 Il tasto ALT attiva il <xref:System.Windows.Forms.MenuStrip> a cui puntava <xref:System.Windows.Forms.Form.MainMenuStrip%2A>. Da qui, CTRL + TAB consente di spostarsi tra <xref:System.Windows.Forms.ToolStrip> controlli all'interno di `ToolStripPanel`s. Il tasto TAB e i tasti di direzione del tastierino numerico consentono di spostarsi tra gli elementi in un <xref:System.Windows.Forms.ToolStrip>. Un algoritmo speciale gestisce lo spostamento nell'area di overflow. Barra spaziatrice seleziona un <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, o <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
##### <a name="focus-and-validation"></a>Lo stato attivo e convalida  
 Se attivato premendo il tasto ALT, il <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ToolStrip> in genere non assume né rimuove lo stato attivo dal controllo che ha attualmente lo stato attivo. Se c'è un controllo ospitato all'interno di <xref:System.Windows.Forms.MenuStrip> o un elenco a discesa del <xref:System.Windows.Forms.MenuStrip>, il controllo riceve lo stato attivo quando l'utente preme il tasto TAB. In generale, il <xref:System.Windows.Forms.Control.GotFocus>, <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter>, e <xref:System.Windows.Forms.Control.Leave> gli eventi di <xref:System.Windows.Forms.MenuStrip> non può essere generata quando vengono attivati tramite la tastiera. In tali casi, utilizzare il <xref:System.Windows.Forms.MenuStrip.MenuActivate> e <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> eventi invece.  
  
 Per impostazione predefinita, <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> è `false`. Chiamare <xref:System.Windows.Forms.ContainerControl.Validate%2A> in modo esplicito sul form per eseguire la convalida.  
  
#### <a name="layout"></a>Layout  
 È possibile controllare <xref:System.Windows.Forms.ToolStrip> layout scegliendo uno dei membri di <xref:System.Windows.Forms.ToolStripLayoutStyle> con il <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> proprietà.  
  
##### <a name="stack-layouts"></a>Layout di stack  
 Stacking è la disposizione di elementi adiacenti a entrambe le estremità del <xref:System.Windows.Forms.ToolStrip>. Nell'elenco seguente vengono descritti i layout di stack.  
  
-   Il valore predefinito è <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow>. Questa impostazione determina il <xref:System.Windows.Forms.ToolStrip> per modificare il layout automaticamente in base al <xref:System.Windows.Forms.ToolStrip.Orientation%2A> proprietà per gestire il trascinamento e scenari di ancoraggio.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>esegue il rendering di <xref:System.Windows.Forms.ToolStrip> elementi accanto a altro in senso verticale.  
  
-   <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow>esegue il rendering di <xref:System.Windows.Forms.ToolStrip> elementi accanto a altro in senso orizzontale.  
  
##### <a name="other-features-of-stack-layouts"></a>Altre funzionalità di layout di Stack  
 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A>Determina la fine di <xref:System.Windows.Forms.ToolStrip> a cui l'elemento viene allineato.  
  
 Quando gli elementi non corrispondono all'interno di <xref:System.Windows.Forms.ToolStrip>, viene automaticamente visualizzato un pulsante di overflow. Il <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> impostazione della proprietà determina se un elemento viene visualizzato nell'area di riversamento sempre, in base alle esigenze, o mai.  
  
 Nel <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento, è possibile controllare il <xref:System.Windows.Forms.ToolStripItem.Placement%2A> proprietà per determinare se un elemento è stato inserito nella classe principale <xref:System.Windows.Forms.ToolStrip>, l'overflow <xref:System.Windows.Forms.ToolStrip>, o se non viene visualizzato affatto. Le cause comuni per cui non viene visualizzato un elemento sono che l'elemento non è contenuto principale <xref:System.Windows.Forms.ToolStrip> e il relativo <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> è stata impostata su <xref:System.Windows.Forms.ToolStripItemOverflow.Never>.  
  
 Rendere una <xref:System.Windows.Forms.ToolStrip> mobile inserendolo un <xref:System.Windows.Forms.ToolStripPanel> e impostando il relativo <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> per <xref:System.Windows.Forms.ToolStripGripStyle.Visible>.  
  
##### <a name="other-layout-options"></a>Altre opzioni di Layout  
 Le altre opzioni di layout sono <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> e <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>.  
  
##### <a name="flow-layout"></a>Layout di flusso  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>layout è quello predefinito per <xref:System.Windows.Forms.ContextMenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, e <xref:System.Windows.Forms.ToolStripOverflow>. È simile al <xref:System.Windows.Forms.FlowLayoutPanel>. Le funzionalità di <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> layout sono i seguenti:  
  
-   Tutte le funzionalità di <xref:System.Windows.Forms.FlowLayoutPanel> esposte dal <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> proprietà. È necessario eseguire il cast di <xref:System.Windows.Forms.LayoutSettings> classe per un <xref:System.Windows.Forms.FlowLayoutSettings> classe.  
  
-   È possibile utilizzare il <xref:System.Windows.Forms.ToolStripItem.Dock%2A> e <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> proprietà nel codice per allineare gli elementi all'interno della riga.  
  
-   La proprietà <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> viene ignorata.  
  
-   Nel <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento, è possibile controllare il <xref:System.Windows.Forms.ToolStripItem.Placement%2A> proprietà per determinare se un elemento è stato inserito nella classe principale <xref:System.Windows.Forms.ToolStrip> o eccessive.  
  
-   Riquadro di ridimensionamento non viene eseguito e pertanto un <xref:System.Windows.Forms.ToolStrip> in <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> lo stile di layout in un <xref:System.Windows.Forms.ToolStripPanel> non può essere spostato.  
  
-   Il <xref:System.Windows.Forms.ToolStrip> pulsante di overflow non viene eseguito, e <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> viene ignorato.  
  
##### <a name="table-layout"></a>Layout di tabella  
 <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>layout è quello predefinito per <xref:System.Windows.Forms.StatusStrip>. È simile a <xref:System.Windows.Forms.TableLayoutPanel>. Le funzionalità di <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> layout sono i seguenti:  
  
-   Tutte le funzionalità di <xref:System.Windows.Forms.TableLayoutPanel> esposte dal <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> proprietà. È necessario eseguire il cast di <xref:System.Windows.Forms.LayoutSettings> classe per un <xref:System.Windows.Forms.TableLayoutSettings> classe.  
  
-   È possibile utilizzare il <xref:System.Windows.Forms.ToolStripItem.Dock%2A> e <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> proprietà nel codice per allineare gli elementi all'interno della cella di tabella.  
  
-   La proprietà <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> viene ignorata.  
  
-   Nel <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> evento, è possibile controllare il <xref:System.Windows.Forms.ToolStripItem.Placement%2A> proprietà per determinare se un elemento è stato inserito nella classe principale <xref:System.Windows.Forms.ToolStrip> o eccessive.  
  
-   Riquadro di ridimensionamento non viene eseguito e pertanto un <xref:System.Windows.Forms.ToolStrip> in <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> lo stile di layout in un <xref:System.Windows.Forms.ToolStripPanel> non può essere spostato.  
  
-   Il <xref:System.Windows.Forms.ToolStrip> pulsante di overflow non viene eseguito, e <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> viene ignorato.  
  
## <a name="toolstripitem"></a>ToolStripItem  
 Gli argomenti seguenti descrivono <xref:System.Windows.Forms.ToolStripItem> e i controlli che derivano da essa.  
  
 <xref:System.Windows.Forms.ToolStripItem>è la classe base astratta per tutti gli elementi che costituiscono un <xref:System.Windows.Forms.ToolStrip>. L'oggetto seguente modello Mostra il <xref:System.Windows.Forms.ToolStripItem> gerarchia di ereditarietà.  
  
 ![Modello a oggetti ToolStripItem](../../../../docs/framework/winforms/controls/media/toolstripitemobjectmodel.gif "ToolStripItemObjectModel")  
Modello a oggetti ToolStripItem  
  
 <xref:System.Windows.Forms.ToolStripItem>classi di ereditare direttamente da <xref:System.Windows.Forms.ToolStripItem>, o indirettamente da <xref:System.Windows.Forms.ToolStripItem> tramite <xref:System.Windows.Forms.ToolStripControlHost> o <xref:System.Windows.Forms.ToolStripDropDownItem>.  
  
 <xref:System.Windows.Forms.ToolStripItem>controlli devono essere contenuti in un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.StatusStrip>, o <xref:System.Windows.Forms.ContextMenuStrip> e non possono essere aggiunti direttamente a un form. Le classi di contenitori diversi sono progettate per contenere un sottoinsieme appropriato di <xref:System.Windows.Forms.ToolStripItem> controlli.  
  
 La tabella seguente elenca le scorte <xref:System.Windows.Forms.ToolStripItem> controlli e i contenitori in cui sono più appropriati. Anche se qualsiasi <xref:System.Windows.Forms.ToolStrip> può essere ospitato in qualsiasi elemento <xref:System.Windows.Forms.ToolStrip>-derivato contenitore, questi elementi sono stati progettati per essere inserito nei contenitori seguenti:  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripDropDown>non viene visualizzato nella casella degli strumenti della finestra di progettazione.  
  
|Elemento di contenuto|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|  
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|  
|<xref:System.Windows.Forms.ToolStripButton>|Sì|No|No|No|Sì|  
|<xref:System.Windows.Forms.ToolStripComboBox>|Sì|Sì|Sì|No|Sì|  
|<xref:System.Windows.Forms.ToolStripSplitButton>|Sì|No|No|Sì|Sì|  
|<xref:System.Windows.Forms.ToolStripLabel>|Sì|No|No|Sì|Sì|  
|<xref:System.Windows.Forms.ToolStripSeparator>|Sì|Sì|Sì|No|Sì|  
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Sì|No|No|Sì|Sì|  
|<xref:System.Windows.Forms.ToolStripTextBox>|Sì|Sì|Sì|No|Sì|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|No|Sì|Sì|No|No|  
|<xref:System.Windows.Forms.ToolStripStatusLabel>|No|No|No|Sì|No|  
|<xref:System.Windows.Forms.ToolStripProgressBar>|Sì|No|No|Sì|No|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Sì|Sì|No|Sì|Sì|  
  
### <a name="toolstripbutton"></a>ToolStripButton  
 <xref:System.Windows.Forms.ToolStripButton>è l'elemento del pulsante per <xref:System.Windows.Forms.ToolStrip>. È possibile visualizzarlo con vari stili del bordo e usarlo per rappresentare e attivare gli stati operativi. È inoltre possibile definire in modo da avere lo stato attivo per impostazione predefinita.  
  
### <a name="toolstriplabel"></a>ToolStripLabel  
 Il <xref:System.Windows.Forms.ToolStripLabel> fornisce la funzionalità di etichetta in <xref:System.Windows.Forms.ToolStrip> controlli. Il <xref:System.Windows.Forms.ToolStripLabel> è simile a un <xref:System.Windows.Forms.ToolStripButton> che riceve lo stato attivo per impostazione predefinita e che non eseguono il rendering come premuto o evidenziato.  
  
 <xref:System.Windows.Forms.ToolStripLabel>come un elemento host supporta chiavi di accesso.  
  
 Utilizzare il <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>, e <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> proprietà in un <xref:System.Windows.Forms.ToolStripLabel> per supportare il controllo di collegamento in un <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel  
 <xref:System.Windows.Forms.ToolStripStatusLabel>è una versione di <xref:System.Windows.Forms.ToolStripLabel> progettato appositamente per l'utilizzo in <xref:System.Windows.Forms.StatusStrip>. Le funzionalità speciali includono <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>, e <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
### <a name="toolstripseparator"></a>ToolStripSeparator  
 Il <xref:System.Windows.Forms.ToolStripSeparator> aggiunge una riga orizzontale o verticale a una barra degli strumenti o menu, a seconda dell'orientamento. Fornisce il raggruppamento o la distinzione tra elementi, ad esempio quelli di un menu.  
  
 È possibile aggiungere un <xref:System.Windows.Forms.ToolStripSeparator> in fase di progettazione scegliendolo da un elenco a discesa. Tuttavia, è anche possibile creare automaticamente un <xref:System.Windows.Forms.ToolStripSeparator> digitando un trattino (-) nel nodo modello di progettazione o nel <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> metodo.  
  
### <a name="toolstripcontrolhost"></a>ToolStripControlHost  
 <xref:System.Windows.Forms.ToolStripControlHost>è la classe base astratta per <xref:System.Windows.Forms.ToolStripComboBox>, <xref:System.Windows.Forms.ToolStripTextBox>, e <xref:System.Windows.Forms.ToolStripProgressBar>. <xref:System.Windows.Forms.ToolStripControlHost>può ospitare altri controlli, inclusi i controlli personalizzati, in due modi:  
  
-   Costruire un <xref:System.Windows.Forms.ToolStripControlHost> con una classe che deriva da <xref:System.Windows.Forms.Control>. Per un accesso completo al controllo contenuto e le proprietà, è necessario eseguire il cast di <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> proprietà per l'effettivo della classe rappresenta.  
  
-   Estendere <xref:System.Windows.Forms.ToolStripControlHost>e il costruttore predefinito della classe ereditata, chiamare il costruttore di classe di base passando una classe che deriva da <xref:System.Windows.Forms.Control>. Questa opzione consente di eseguire il wrapping di metodi di controllo comuni e proprietà per semplificare l'accesso in un <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripcombobox"></a>ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripComboBox>è il <xref:System.Windows.Forms.ComboBox> ottimizzata per l'hosting in un <xref:System.Windows.Forms.ToolStrip>. Un subset di proprietà ed eventi del controllo ospitato sono esposti nel <xref:System.Windows.Forms.ToolStripComboBox> livello, ma sottostante <xref:System.Windows.Forms.ComboBox> controllo è completamente accessibile tramite la <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> proprietà.  
  
### <a name="toolstriptextbox"></a>ToolStripComboBox  
 <xref:System.Windows.Forms.ToolStripTextBox>è il <xref:System.Windows.Forms.TextBox> ottimizzata per l'hosting in un <xref:System.Windows.Forms.ToolStrip>. Un subset di proprietà ed eventi del controllo ospitato sono esposti nel <xref:System.Windows.Forms.ToolStripTextBox> livello, ma sottostante <xref:System.Windows.Forms.TextBox> controllo è completamente accessibile tramite la <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> proprietà.  
  
### <a name="toolstripprogressbar"></a>ToolStripProgressBar  
 <xref:System.Windows.Forms.ToolStripProgressBar>è il <xref:System.Windows.Forms.ProgressBar> ottimizzata per l'hosting in un <xref:System.Windows.Forms.ToolStrip>. Un subset di proprietà ed eventi del controllo ospitato sono esposti nel <xref:System.Windows.Forms.ToolStripProgressBar> livello, ma sottostante <xref:System.Windows.Forms.ProgressBar> controllo è completamente accessibile tramite la <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> proprietà.  
  
### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem  
 <xref:System.Windows.Forms.ToolStripDropDownItem>è la classe base astratta per <xref:System.Windows.Forms.ToolStripMenuItem>, <xref:System.Windows.Forms.ToolStripDropDownButton>, e <xref:System.Windows.Forms.ToolStripSplitButton>, che possono ospitare direttamente gli elementi o ospitare elementi aggiuntivi in un contenitore di riepilogo a discesa. A questo scopo, impostare il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> proprietà per un <xref:System.Windows.Forms.ToolStripDropDown> e impostando il <xref:System.Windows.Forms.ToolStrip.Items%2A> proprietà del <xref:System.Windows.Forms.ToolStripDropDown>. Accedere a questi elementi di elenco a discesa direttamente tramiti il <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> proprietà.  
  
### <a name="toolstripmenuitem"></a>ToolStripMenuItem  
 <xref:System.Windows.Forms.ToolStripMenuItem>è un <xref:System.Windows.Forms.ToolStripDropDownItem> che funziona con <xref:System.Windows.Forms.ToolStripDropDownMenu> e <xref:System.Windows.Forms.ContextMenuStrip> per gestire la disposizione di evidenziazione, layout e colonna speciale per i menu.  
  
### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton  
 <xref:System.Windows.Forms.ToolStripDropDownButton>aspetto <xref:System.Windows.Forms.ToolStripButton>, ma visualizza un'area di riepilogo a discesa quando l'utente fa clic. Visualizzare o nascondere la freccia a discesa impostando il <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> proprietà. <xref:System.Windows.Forms.ToolStripDropDownButton>ospita un <xref:System.Windows.Forms.ToolStripOverflowButton> che visualizza gli elementi che superano il <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="toolstripsplitbutton"></a>Controllo ToolStripSplitButton  
 <xref:System.Windows.Forms.ToolStripSplitButton>Combina le funzionalità di pulsante e pulsante di menu a discesa.  
  
 Utilizzare il <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> proprietà per sincronizzare il <xref:System.Windows.Forms.Control.Click> evento della voce di menu a discesa scelta con l'elemento visualizzato sul pulsante.  
  
### <a name="toolstripitem-generic-features"></a>Funzionalità generiche di ToolStripItem  
 <xref:System.Windows.Forms.ToolStripItem>fornisce le seguenti funzionalità generiche e le opzioni per i controlli che ereditano:  
  
-   Eventi di base  
  
-   Gestione delle immagini  
  
-   Allineamento  
  
-   Relazione di tipo text e image  
  
-   Stile di visualizzazione  
  
#### <a name="core-events"></a>Eventi di base  
 <xref:System.Windows.Forms.ToolStripItem>controlli ricevano le proprie risorse, mouse e gli eventi di disegno fare clic su e possono eseguire alcuni tasti anche di pre-elaborazione.  
  
#### <a name="image-handling"></a>Gestione delle immagini  
 Il <xref:System.Windows.Forms.ToolStripItem.Image%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A>, <xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>, e <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> proprietà riguardano i vari aspetti della gestione di immagini. Utilizzare le immagini in <xref:System.Windows.Forms.ToolStrip> controlli impostando direttamente queste proprietà o impostando l'esecuzione solo in fase di <xref:System.Windows.Forms.ToolStrip.ImageList%2A> proprietà.  
  
 Il ridimensionamento dell'immagine è determinato dall'interazione delle proprietà in <xref:System.Windows.Forms.ToolStrip> e <xref:System.Windows.Forms.ToolStripItem>, come segue:  
  
-   <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A>rappresenta la scala dell'immagine finale, come determinato dalla combinazione dell'immagine <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> impostazione e il contenitore <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> impostazione.  
  
    -   Se <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> è `true` (predefinito) e <xref:System.Windows.Forms.ToolStripItemImageScaling> è <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>, si verifica alcun ridimensionamento di immagini e <xref:System.Windows.Forms.ToolStrip> dimensioni sono quello dell'elemento più grande o una dimensione minima prestabilita.  
  
    -   Se <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> è `false` e <xref:System.Windows.Forms.ToolStripItemImageScaling> è <xref:System.Windows.Forms.ToolStripItemImageScaling.None>, nessuna immagine né <xref:System.Windows.Forms.ToolStrip> si verifica il ridimensionamento.  
  
#### <a name="alignment"></a>Allineamento  
 Il valore di <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> proprietà determina la fine del <xref:System.Windows.Forms.ToolStrip> in cui viene visualizzato un elemento. Il <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> proprietà funziona solo quando lo stile di layout di <xref:System.Windows.Forms.ToolStrip> è impostata su uno dei valori di overflow dello stack.  
  
 Gli elementi vengono inseriti nel <xref:System.Windows.Forms.ToolStrip> nell'ordine in cui gli elementi vengono visualizzati nell'insieme di elementi. Per modificare a livello di codice in cui un elemento è disposto, utilizzare il <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> metodo per spostare l'elemento nella raccolta. Questo metodo consente di spostare l'elemento ma non duplicare.  
  
#### <a name="text-and-image-relationship"></a>Testo e immagine relazione  
 Il <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> proprietà definisce la posizione relativa dell'immagine rispetto al testo in un <xref:System.Windows.Forms.ToolStripItem>. Gli elementi che non dispongono di un'immagine, testo o entrambi sono considerati come casi speciali in modo che il <xref:System.Windows.Forms.ToolStripItem> non è presente uno spazio vuoto per gli elementi mancanti.  
  
#### <a name="display-style"></a>Stile di visualizzazione  
 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>Consente di impostare i valori delle proprietà di testo e immagine di un elemento durante la visualizzazione solo gli elementi desiderati. In genere, questo viene utilizzato per modificare lo stile di visualizzazione quando lo stesso elemento in un contesto diverso.  
  
## <a name="accessory-classes"></a>Classi degli accessori  
 Le classi che forniscono varie altre funzionalità includono:  
  
-   <xref:System.Windows.Forms.ToolStripManager>supporta <xref:System.Windows.Forms.ToolStrip>-attività per l'intera applicazione, ad esempio l'unione, le impostazioni e opzioni di rendering correlate.  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>Consente di applicare uno stile specifico o un tema da un <xref:System.Windows.Forms.ToolStrip> facilmente.  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer>crea penne e pennelli in base a una tabella dei colori sostituibile (<xref:System.Windows.Forms.ProfessionalColorTable>).  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer>Applica i colori di sistema e uno stile di visualizzazione bidimensionale <xref:System.Windows.Forms.ToolStrip> applicazioni.  
  
-   <xref:System.Windows.Forms.ToolStripContainer>è simile a <xref:System.Windows.Forms.SplitContainer>. Utilizza quattro pannelli laterali ancorati (istanze di <xref:System.Windows.Forms.ToolStripPanel>) e un pannello centrale (un'istanza di <xref:System.Windows.Forms.ToolStripContentPanel>) per creare una disposizione tipica. Non è possibile rimuovere i pannelli lato, ma è possibile nasconderle. Non è possibile rimuovere né nascondere il riquadro centrale. È possibile disporre di uno o più <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, o <xref:System.Windows.Forms.StatusStrip> controlli nei pannelli laterali ed è possano utilizzare il pannello centrale per altri controlli. Il <xref:System.Windows.Forms.ToolStripContentPanel> fornisce inoltre un modo per ottenere il supporto del renderer nel corpo del form per un aspetto coerenza. <xref:System.Windows.Forms.ToolStripContainer>non supporta l'interfaccia a documenti multipli (MDI).  
  
-   <xref:System.Windows.Forms.ToolStripPanel>fornisce lo spazio per lo spostamento e la disposizione <xref:System.Windows.Forms.ToolStrip> controlli. È possibile utilizzare solo un pannello se si sceglie, e <xref:System.Windows.Forms.ToolStripPanel> funziona bene in scenari MDI.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sul controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Riepilogo della tecnologia ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)  
 [Controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 [Controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [Controllo StatusStrip](../../../../docs/framework/winforms/controls/statusstrip-control.md)  
 [Controllo ContextMenuStrip](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)  
 [Controllo BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
