---
title: Architettura del controllo ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], architecture
ms.assetid: 71df2d18-862e-4701-9ff9-c1fe606f94f2
ms.openlocfilehash: d0a1441e9bae8d2c1f938e7399c11e736708da4d
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68363833"
---
# <a name="toolstrip-control-architecture"></a>Architettura del controllo ToolStrip

Le <xref:System.Windows.Forms.ToolStrip> classi <xref:System.Windows.Forms.ToolStripItem> e forniscono un sistema flessibile ed estendibile per la visualizzazione della barra degli strumenti, dello stato e delle voci di menu. Queste classi sono tutte contenute nello <xref:System.Windows.Forms> spazio dei nomi e vengono in genere denominate con il prefisso "ToolStrip" ( <xref:System.Windows.Forms.ToolStripOverflow>ad esempio) o con il suffisso "Strip <xref:System.Windows.Forms.MenuStrip>" (ad esempio).

## <a name="toolstrip"></a>ToolStrip

Gli argomenti seguenti descrivono <xref:System.Windows.Forms.ToolStrip> e i controlli che derivano da esso.

<xref:System.Windows.Forms.ToolStrip>è la classe di base astratta <xref:System.Windows.Forms.MenuStrip>per <xref:System.Windows.Forms.StatusStrip>, e <xref:System.Windows.Forms.ContextMenuStrip>. Il modello a oggetti seguente mostra <xref:System.Windows.Forms.ToolStrip> la gerarchia di ereditarietà.

![Diagramma che mostra il modello a oggetti ToolStrip.](./media/toolstrip-control-architecture/toolstrip-object-model.gif)

È possibile accedere a tutti gli elementi di <xref:System.Windows.Forms.ToolStrip> un oggetto <xref:System.Windows.Forms.ToolStrip.Items%2A> tramite la raccolta. È possibile accedere a tutti gli elementi di <xref:System.Windows.Forms.ToolStripDropDownItem> un oggetto <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> tramite la raccolta. In una classe derivata da <xref:System.Windows.Forms.ToolStrip>, è anche possibile usare la <xref:System.Windows.Forms.ToolStrip.DisplayedItems%2A> proprietà per accedere solo agli elementi attualmente visualizzati. Si tratta degli elementi che attualmente non si trovano in un menu di overflow.

Gli elementi seguenti sono appositamente progettati per funzionare senza interruzioni <xref:System.Windows.Forms.ToolStripSystemRenderer> con <xref:System.Windows.Forms.ToolStripProfessionalRenderer> e in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per <xref:System.Windows.Forms.ToolStrip> il controllo:

- <xref:System.Windows.Forms.ToolStripButton>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="menustrip"></a>MenuStrip

<xref:System.Windows.Forms.MenuStrip>è il contenitore di livello superiore che sostituisce <xref:System.Windows.Forms.MainMenu>. Fornisce inoltre funzionalità di gestione delle chiavi e di interfaccia a documenti multipli (MDI). Dal punto di vista <xref:System.Windows.Forms.ToolStripMenuItem> funzionale <xref:System.Windows.Forms.MenuStrip> efunzionano<xref:System.Windows.Forms.ToolStripItem>insieme a, anche se sono derivati da. <xref:System.Windows.Forms.ToolStripDropDownItem>

Gli elementi seguenti sono appositamente progettati per funzionare senza interruzioni <xref:System.Windows.Forms.ToolStripSystemRenderer> con <xref:System.Windows.Forms.ToolStripProfessionalRenderer> e in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per <xref:System.Windows.Forms.MenuStrip> il controllo:

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="statusstrip"></a>StatusStrip

<xref:System.Windows.Forms.StatusStrip>sostituisce il <xref:System.Windows.Forms.StatusBar> controllo. Le funzionalità speciali <xref:System.Windows.Forms.StatusStrip> di includono un layout di tabella personalizzato, il supporto per i grip di ridimensionamento e di movimentazione `Spring` del modulo e la proprietà <xref:System.Windows.Forms.ToolStripStatusLabel> , che consente a un di riempire lo spazio disponibile automaticamente.

Gli elementi seguenti sono appositamente progettati per funzionare senza interruzioni <xref:System.Windows.Forms.ToolStripSystemRenderer> con <xref:System.Windows.Forms.ToolStripProfessionalRenderer> e in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per <xref:System.Windows.Forms.StatusStrip> il controllo:

- <xref:System.Windows.Forms.ToolStripStatusLabel>

- <xref:System.Windows.Forms.ToolStripDropDownButton>

- <xref:System.Windows.Forms.ToolStripSplitButton>

- <xref:System.Windows.Forms.ToolStripProgressBar>

### <a name="contextmenustrip"></a>ContextMenuStrip

<xref:System.Windows.Forms.ContextMenuStrip> sostituisce <xref:System.Windows.Forms.ContextMenu>. È possibile associare un <xref:System.Windows.Forms.ContextMenuStrip> oggetto a qualsiasi controllo e fare clic con il pulsante destro del mouse su Visualizza automaticamente il menu di scelta rapida o il menu di scelta rapida. È possibile visualizzare un <xref:System.Windows.Forms.ContextMenuStrip> oggetto a livello di codice <xref:System.Windows.Forms.ToolStripDropDown.Show%2A> usando il metodo. <xref:System.Windows.Forms.ContextMenuStrip>supporta gli eventi <xref:System.Windows.Forms.ToolStripDropDown.Opening> annullabili e <xref:System.Windows.Forms.ToolStripDropDown.Closing> per gestire il popolamento dinamico e scenari con più clic. <xref:System.Windows.Forms.ContextMenuStrip>supporta immagini, stato di controllo delle voci di menu, testo, chiavi di accesso, scelte rapide e menu a cascata.

Gli elementi seguenti sono appositamente progettati per funzionare senza interruzioni <xref:System.Windows.Forms.ToolStripSystemRenderer> con <xref:System.Windows.Forms.ToolStripProfessionalRenderer> e in tutti gli orientamenti. Sono disponibili per impostazione predefinita in fase di progettazione per <xref:System.Windows.Forms.ContextMenuStrip> il controllo:

- <xref:System.Windows.Forms.ToolStripMenuItem>

- <xref:System.Windows.Forms.ToolStripSeparator>

- <xref:System.Windows.Forms.ToolStripTextBox>

- <xref:System.Windows.Forms.ToolStripComboBox>

### <a name="toolstrip-generic-features"></a>Funzionalità generiche di ToolStrip

Negli argomenti seguenti vengono descritte le funzionalità e il comportamento generici <xref:System.Windows.Forms.ToolStrip> per i controlli derivati e.

#### <a name="painting"></a>Disegno

È possibile eseguire il disegno personalizzato <xref:System.Windows.Forms.ToolStrip> nei controlli in diversi modi. Come per gli <xref:System.Windows.Forms.ToolStrip> altri controlli Windows Forms, ed <xref:System.Windows.Forms.ToolStripItem> entrambi hanno metodi ed `OnPaint` `Paint` eventi sottoponibili a override. Come nel caso del disegno normale, il sistema di coordinate è relativo all'area client del controllo; ovvero l'angolo superiore sinistro del controllo è 0, 0. L' `Paint` evento e `OnPaint` il metodo per <xref:System.Windows.Forms.ToolStripItem> un si comportano come altri eventi di disegno del controllo.

I <xref:System.Windows.Forms.ToolStrip> controlli forniscono anche un accesso più preciso al rendering degli elementi e del contenitore tramite <xref:System.Windows.Forms.ToolStripRenderer> la classe, che dispone di metodi sottoponibili a override per disegnare lo sfondo, lo sfondo dell'elemento, l'immagine dell'elemento, la freccia dell'elemento, il testo dell'elemento e il bordo del <xref:System.Windows.Forms.ToolStrip>. Gli argomenti dell'evento per questi metodi espongono diverse proprietà, ad esempio rettangoli, colori e formati di testo che è possibile modificare secondo le esigenze.

Per modificare solo alcuni aspetti della modalità di disegno di un elemento, in genere si esegue <xref:System.Windows.Forms.ToolStripRenderer>l'override di.

Se si sta scrivendo un nuovo elemento e si desidera controllare tutti gli aspetti del disegno, eseguire l' `OnPaint` override del metodo. Dall'interno `OnPaint`di è possibile utilizzare i <xref:System.Windows.Forms.ToolStripRenderer>metodi di.

Per impostazione predefinita, <xref:System.Windows.Forms.ToolStrip> l'oggetto è con doppio buffer, sfruttando <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> l'impostazione.

#### <a name="parenting"></a>Padre

Il concetto di proprietà e genitorialità del contenitore è più complesso <xref:System.Windows.Forms.ToolStrip> nei controlli che in altri Windows Forms controlli contenitore. Ciò è necessario per supportare scenari dinamici come l'overflow, la condivisione di elementi a discesa tra <xref:System.Windows.Forms.ToolStrip> più elementi e per supportare la generazione di un <xref:System.Windows.Forms.ContextMenuStrip> da un controllo.

Nell'elenco seguente vengono descritti i membri correlati all'elemento padre e ne viene illustrato l'utilizzo.

- <xref:System.Windows.Forms.ToolStripDropDown.OwnerItem%2A>accede all'elemento che rappresenta l'origine dell'elemento a discesa. Questa operazione è simile <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>a, ma anziché restituire un controllo, <xref:System.Windows.Forms.ToolStripItem>restituisce.

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A>determina il controllo che rappresenta l'origine di <xref:System.Windows.Forms.ContextMenuStrip> quando più controlli condividono lo stesso <xref:System.Windows.Forms.ContextMenuStrip>oggetto.

- <xref:System.Windows.Forms.ToolStripItem.GetCurrentParent%2A>è una funzione di accesso di sola lettura <xref:System.Windows.Forms.ToolStripItem.Parent%2A> alla proprietà. Un padre è diverso da un proprietario in quanto un elemento padre denota l'oggetto corrente <xref:System.Windows.Forms.ToolStrip> restituito in cui viene visualizzato l'elemento, che potrebbe trovarsi nell'area di overflow.

- <xref:System.Windows.Forms.ToolStripItem.Owner%2A>Restituisce l' <xref:System.Windows.Forms.ToolStrip> oggetto la cui raccolta Items <xref:System.Windows.Forms.ToolStripItem>contiene l'oggetto corrente. Questo è il modo migliore per fare <xref:System.Windows.Forms.ToolStrip.ImageList%2A> riferimento a o ad altre proprietà nel livello <xref:System.Windows.Forms.ToolStrip> superiore senza scrivere codice speciale per gestire l'overflow.

#### <a name="behavior-of-inherited-controls"></a>Comportamento dei controlli ereditati

I controlli seguenti sono bloccati ogni volta che vengono usati nell'ereditarietà:

- <xref:System.Windows.Forms.ToolStrip>

- <xref:System.Windows.Forms.MenuStrip>

- <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.StatusStrip>

- <xref:System.Windows.Forms.ToolStripPanel>che include i pannelli in un <xref:System.Windows.Forms.ToolStripContainer> oggetto e anche <xref:System.Windows.Forms.ToolStripPanel> i singoli controlli.

Ad esempio, creare una nuova Windows Forms Application usando uno o più controlli nell'elenco precedente. Impostare il modificatore di accesso di uno o più `public` controlli `protected`su o, quindi compilare il progetto. Aggiungere un modulo che eredita dal primo form e quindi selezionare un controllo ereditato. Il controllo appare bloccato e si comporta come se fosse `private`il relativo modificatore di accesso.

#### <a name="toolstripcontainer-support-of-inheritance"></a>Supporto di ToolStripContainer dell'ereditarietà

Il <xref:System.Windows.Forms.ToolStripContainer> controllo supporta scenari ereditati limitati, in modo analogo all'esempio seguente:

1. Creare una nuova applicazione Windows Forms.

2. Aggiungere un tipo <xref:System.Windows.Forms.ToolStripContainer> al form.

3. Impostare il modificatore di accesso <xref:System.Windows.Forms.ToolStripContainer> di `public` su `protected`o.

4. Aggiungere qualsiasi combinazione di <xref:System.Windows.Forms.ToolStrip>controlli <xref:System.Windows.Forms.MenuStrip>, e <xref:System.Windows.Forms.ContextMenuStrip> alle <xref:System.Windows.Forms.ToolStripPanel> aree della <xref:System.Windows.Forms.ToolStripContainer>.

5. Compilare il progetto.

6. Aggiungere un modulo che eredita dal primo form.

7. Selezionare ereditato <xref:System.Windows.Forms.ToolStripContainer> nel form.

#### <a name="inherited-behavior-of-child-controls"></a>Comportamento ereditato dei controlli figlio

Dopo aver completato i passaggi precedenti, si verifica il comportamento ereditato seguente:

- Nella finestra di progettazione il controllo viene visualizzato con un'icona ereditata.

- I <xref:System.Windows.Forms.ToolStripPanel> controlli sono bloccati. non è possibile selezionare o riorganizzare il contenuto.

- È possibile aggiungere controlli a <xref:System.Windows.Forms.ToolStripContentPanel>, spostare i controlli e impostarli come controlli figlio dell'oggetto. <xref:System.Windows.Forms.ToolStripContentPanel>

- Le modifiche vengono mantenute dopo aver compilato il modulo.

  > [!NOTE]
  > Rimuovere i modificatori di accesso da <xref:System.Windows.Forms.ToolStripPanel> tutti i controlli che fanno parte <xref:System.Windows.Forms.ToolStripContainer>di un oggetto. Il modificatore di accesso <xref:System.Windows.Forms.ToolStripContainer> di regola l'intero controllo.

#### <a name="partial-trust"></a>Attendibilità parziale

Le limitazioni di `ToolStrip`s con attendibilità parziale sono progettate per impedire l'immissione accidentale di informazioni personali che potrebbero essere usate da persone o servizi non autorizzati. Le misure protettive sono le seguenti:

- `ToolStripDropDown`i controlli <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> richiedono la visualizzazione di elementi <xref:System.Windows.Forms.ToolStripControlHost>in un oggetto. Questo vale per entrambi i controlli intrinseci <xref:System.Windows.Forms.ToolStripTextBox>, <xref:System.Windows.Forms.ToolStripComboBox>ad esempio <xref:System.Windows.Forms.ToolStripProgressBar> , e, nonché per i controlli creati dall'utente. Se questo requisito non viene soddisfatto, questi elementi non vengono visualizzati. Non viene generata alcuna eccezione.

- L'impostazione <xref:System.Windows.Forms.ToolStripDropDown.AutoClose%2A> della proprietà `false` su non è consentita e il <xref:System.Windows.Forms.ToolStripDropDown.Closing> parametro dell'evento annullabile viene ignorato. In questo modo è Impossibile immettere più di una sequenza di tasti senza chiudere l'elemento a discesa. Se questo requisito non viene soddisfatto, tali elementi non vengono visualizzati. Non viene generata alcuna eccezione.

- Molti eventi di gestione della sequenza di tasti non verranno generati se si verificano in contesti di <xref:System.Security.Permissions.UIPermissionWindow.AllWindows>attendibilità parziale diversi da.

- Le chiavi di accesso non vengono <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> elaborate quando non viene concesso.

#### <a name="usage"></a>Utilizzo

I modelli di utilizzo seguenti presentano un impatto <xref:System.Windows.Forms.ToolStrip> sul layout, sull'interazione della tastiera e sul comportamento dell'utente finale:

- Unita in join<xref:System.Windows.Forms.ToolStripPanel>

  È <xref:System.Windows.Forms.ToolStrip> possibile riposizionare l'oggetto <xref:System.Windows.Forms.ToolStripPanel> all'interno di e <xref:System.Windows.Forms.ToolStripPanel>in. La `Dock` proprietà viene ignorata e se la <xref:System.Windows.Forms.ToolStrip.Stretch%2A> proprietà è `false`, le dimensioni di <xref:System.Windows.Forms.ToolStrip> aumentano man mano che gli elementi vengono <xref:System.Windows.Forms.ToolStripPanel>aggiunti all'oggetto. In genere, <xref:System.Windows.Forms.ToolStrip> non fa parte dell'ordine di tabulazione.

- Ancorato

  L' <xref:System.Windows.Forms.ToolStrip> oggetto viene posizionato su un lato di un contenitore in una posizione fissa e la relativa dimensione si espande sull'intero bordo a cui è ancorato. In genere, <xref:System.Windows.Forms.ToolStrip> non fa parte dell'ordine di tabulazione.

- Posizionato in modo assoluto

  È <xref:System.Windows.Forms.ToolStrip> come gli altri controlli, in quanto viene inserito <xref:System.Windows.Forms.Control.Location%2A> dalla proprietà, ha una dimensione fissa e in genere partecipa all'ordine di tabulazione.

#### <a name="keyboard-interaction"></a>Interazione con la tastiera

##### <a name="access-keys"></a>Chiavi di accesso

In combinazione con o dopo il tasto ALT, le chiavi di accesso sono un modo per attivare un controllo usando la tastiera. <xref:System.Windows.Forms.ToolStrip>supporta chiavi di accesso esplicite e implicite. La definizione esplicita usa un carattere e commerciale (&) che precede la lettera. La definizione implicita usa un algoritmo che tenta di trovare un elemento corrispondente in base all'ordine dei caratteri di `Text` una determinata proprietà.

##### <a name="shortcut-keys"></a>Tasti di scelta rapida

I tasti di scelta rapida usati <xref:System.Windows.Forms.MenuStrip> da un oggetto usano una <xref:System.Windows.Forms.Keys> combinazione dell'enumerazione (che non è specifica dell'ordine) per definire il tasto di scelta rapida. È anche possibile usare la <xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeyDisplayString%2A> proprietà per visualizzare un tasto di scelta rapida solo con testo, ad esempio la visualizzazione di "CANC" invece di "Delete".

##### <a name="navigation"></a>Navigazione

Il tasto ALT attiva l'oggetto <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.Form.MainMenuStrip%2A>a cui punta. Da qui, CTRL + TAB passa tra <xref:System.Windows.Forms.ToolStrip> i controlli all'interno `ToolStripPanel`di s. Il tasto TAB e i tasti di direzione sul tastierino numerico passano tra gli elementi <xref:System.Windows.Forms.ToolStrip>di un oggetto. Un algoritmo speciale gestisce la navigazione nell'area di overflow. Barra spaziatrice <xref:System.Windows.Forms.ToolStripButton>consente <xref:System.Windows.Forms.ToolStripDropDownButton>di selezionare <xref:System.Windows.Forms.ToolStripSplitButton>, o.

##### <a name="focus-and-validation"></a>Messa a fuoco e convalida

Quando viene attivato dal tasto ALT, <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ToolStrip> in genere non è necessario né rimuovere lo stato attivo dal controllo che ha attualmente lo stato attivo. Se è presente un controllo ospitato all'interno <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.MenuStrip>di o di un elenco a discesa di, il controllo ottiene lo stato attivo quando l'utente preme il tasto TAB. In generale, gli <xref:System.Windows.Forms.Control.GotFocus>eventi <xref:System.Windows.Forms.Control.LostFocus>, <xref:System.Windows.Forms.Control.Enter>, e <xref:System.Windows.Forms.Control.Leave> di <xref:System.Windows.Forms.MenuStrip> potrebbero non essere generati quando vengono attivati dalla tastiera. In questi casi, usare invece <xref:System.Windows.Forms.MenuStrip.MenuActivate> gli <xref:System.Windows.Forms.MenuStrip.MenuDeactivate> eventi e.

Per impostazione predefinita <xref:System.Windows.Forms.ToolStrip.CausesValidation%2A> , `false`è. Chiamare <xref:System.Windows.Forms.ContainerControl.Validate%2A> in modo esplicito sul form per eseguire la convalida.

#### <a name="layout"></a>Layout

È possibile <xref:System.Windows.Forms.ToolStrip> controllare il layout scegliendo uno dei <xref:System.Windows.Forms.ToolStripLayoutStyle> membri di <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> con la proprietà.

##### <a name="stack-layouts"></a>Layout dello stack

Lo stacking è la disposizione di elementi accanto a entrambe le estremità di <xref:System.Windows.Forms.ToolStrip>. Nell'elenco seguente vengono descritti i layout dello stack.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.StackWithOverflow>è il valore predefinito. Questa impostazione fa in <xref:System.Windows.Forms.ToolStrip> modo che l'oggetto modifichi automaticamente il layout in <xref:System.Windows.Forms.ToolStrip.Orientation%2A> base alla proprietà per gestire gli scenari di trascinamento e ancoraggio.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>esegue il rendering <xref:System.Windows.Forms.ToolStrip> degli elementi uno accanto all'altro verticalmente.

- <xref:System.Windows.Forms.ToolStripLayoutStyle.HorizontalStackWithOverflow>esegue il rendering <xref:System.Windows.Forms.ToolStrip> degli elementi uno accanto all'altro orizzontalmente.

##### <a name="other-features-of-stack-layouts"></a>Altre funzionalità dei layout dello stack

<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>determina la fine dell' <xref:System.Windows.Forms.ToolStrip> oggetto a cui l'elemento è allineato.

Quando gli elementi non rientrano <xref:System.Windows.Forms.ToolStrip>in, viene visualizzato automaticamente un pulsante di overflow. L' <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> impostazione della proprietà determina se un elemento viene visualizzato nell'area di overflow sempre, in base alle esigenze o mai.

Nell'evento, è possibile esaminare la <xref:System.Windows.Forms.ToolStripItem.Placement%2A> proprietà per determinare se un elemento è stato inserito nella principale <xref:System.Windows.Forms.ToolStrip>, nell'overflow <xref:System.Windows.Forms.ToolStrip>o se non è visualizzato. <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> I motivi tipici per <xref:System.Windows.Forms.ToolStrip> <xref:System.Windows.Forms.ToolStripItemOverflow.Never>cui non viene visualizzato un elemento sono che l'elemento non è stato adattato al principale <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> e la relativa proprietà è stata impostata su.

Rendere un <xref:System.Windows.Forms.ToolStrip> oggetto mobile inserendolo in un <xref:System.Windows.Forms.ToolStripPanel> oggetto e impostando <xref:System.Windows.Forms.ToolStripGripStyle.Visible> <xref:System.Windows.Forms.ToolStrip.GripStyle%2A> su.

##### <a name="other-layout-options"></a>Altre opzioni di layout

Le altre opzioni di layout <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> sono <xref:System.Windows.Forms.ToolStripLayoutStyle.Table>e.

##### <a name="flow-layout"></a>Layout di flusso

<xref:System.Windows.Forms.ToolStripLayoutStyle.Flow>layout è l'impostazione predefinita <xref:System.Windows.Forms.ContextMenuStrip>per <xref:System.Windows.Forms.ToolStripDropDownMenu>, e <xref:System.Windows.Forms.ToolStripOverflow>. È simile a <xref:System.Windows.Forms.FlowLayoutPanel>. Di seguito sono <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> riportate le funzionalità del layout:

- Tutte le funzionalità di <xref:System.Windows.Forms.FlowLayoutPanel> sono esposte <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> dalla proprietà. È necessario eseguire il <xref:System.Windows.Forms.LayoutSettings> cast della classe <xref:System.Windows.Forms.FlowLayoutSettings> a una classe.

- È possibile utilizzare le <xref:System.Windows.Forms.ToolStripItem.Dock%2A> proprietà <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> e nel codice per allineare gli elementi all'interno della riga.

- La proprietà <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> viene ignorata.

- Nell'evento, è possibile esaminare la <xref:System.Windows.Forms.ToolStripItem.Placement%2A> proprietà per determinare se un elemento è stato inserito nel Main <xref:System.Windows.Forms.ToolStrip> o non è adatto. <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>

- Il rendering del grip non viene eseguito e pertanto <xref:System.Windows.Forms.ToolStrip> non <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> è possibile spostare un <xref:System.Windows.Forms.ToolStripPanel> oggetto nello stile di layout in un oggetto.

- Il <xref:System.Windows.Forms.ToolStrip> pulsante di overflow non viene sottoposto <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> a rendering e viene ignorato.

##### <a name="table-layout"></a>Layout tabella

<xref:System.Windows.Forms.ToolStripLayoutStyle.Table>layout è l'impostazione predefinita <xref:System.Windows.Forms.StatusStrip>per. È simile a <xref:System.Windows.Forms.TableLayoutPanel>. Di seguito sono <xref:System.Windows.Forms.ToolStripLayoutStyle.Flow> riportate le funzionalità del layout:

- Tutte le funzionalità di <xref:System.Windows.Forms.TableLayoutPanel> sono esposte <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A> dalla proprietà. È necessario eseguire il <xref:System.Windows.Forms.LayoutSettings> cast della classe <xref:System.Windows.Forms.TableLayoutSettings> a una classe.

- È possibile utilizzare le <xref:System.Windows.Forms.ToolStripItem.Dock%2A> proprietà <xref:System.Windows.Forms.ToolStripItem.Anchor%2A> e nel codice per allineare gli elementi all'interno della cella della tabella.

- La proprietà <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> viene ignorata.

- Nell'evento, è possibile esaminare la <xref:System.Windows.Forms.ToolStripItem.Placement%2A> proprietà per determinare se un elemento è stato inserito nel Main <xref:System.Windows.Forms.ToolStrip> o non è adatto. <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>

- Il rendering del grip non viene eseguito e pertanto <xref:System.Windows.Forms.ToolStrip> non <xref:System.Windows.Forms.ToolStripLayoutStyle.Table> è possibile spostare un <xref:System.Windows.Forms.ToolStripPanel> oggetto nello stile di layout in un oggetto.

- Il <xref:System.Windows.Forms.ToolStrip> pulsante di overflow non viene sottoposto <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> a rendering e viene ignorato.

## <a name="toolstripitem"></a>ToolStripItem

Gli argomenti seguenti descrivono <xref:System.Windows.Forms.ToolStripItem> e i controlli che derivano da esso.

<xref:System.Windows.Forms.ToolStripItem>è la classe di base astratta per tutti gli elementi che vengono inseriti <xref:System.Windows.Forms.ToolStrip>in un oggetto. Il modello a oggetti seguente mostra <xref:System.Windows.Forms.ToolStripItem> la gerarchia di ereditarietà.

![Diagramma che mostra il modello a oggetti ToolStripItem.](./media/toolstrip-control-architecture/toolstripitem-object-model.gif)

<xref:System.Windows.Forms.ToolStripItem>le classi ereditano direttamente <xref:System.Windows.Forms.ToolStripItem>da o ereditano indirettamente da <xref:System.Windows.Forms.ToolStripItem> tramite <xref:System.Windows.Forms.ToolStripControlHost> o <xref:System.Windows.Forms.ToolStripDropDownItem>.

<xref:System.Windows.Forms.ToolStripItem>i controlli devono essere contenuti in <xref:System.Windows.Forms.ToolStrip>un <xref:System.Windows.Forms.MenuStrip>oggetto <xref:System.Windows.Forms.StatusStrip>,, <xref:System.Windows.Forms.ContextMenuStrip> o e non possono essere aggiunti direttamente a un form. Le varie classi di contenitori sono progettate per contenere un subset di <xref:System.Windows.Forms.ToolStripItem> controlli appropriato.

La tabella seguente elenca i controlli <xref:System.Windows.Forms.ToolStripItem> azionari e i contenitori in cui sembrano migliori. Sebbene sia <xref:System.Windows.Forms.ToolStrip> possibile ospitare qualsiasi elemento in qualsiasi <xref:System.Windows.Forms.ToolStrip>contenitore derivato da, questi elementi sono stati progettati per un aspetto ottimale nei contenitori seguenti:

> [!NOTE]
> <xref:System.Windows.Forms.ToolStripDropDown>non viene visualizzato nella casella degli strumenti della finestra di progettazione.

|Elemento contenuto|ToolStrip|MenuStrip|ContextMenuStrip|StatusStrip|ToolStripDropDown|
|--------------------|---------------|---------------|----------------------|-----------------|-----------------------|
|<xref:System.Windows.Forms.ToolStripButton>|Sì|No|No|No|Yes|
|<xref:System.Windows.Forms.ToolStripComboBox>|Sì|Sì|Sì|No|Yes|
|<xref:System.Windows.Forms.ToolStripSplitButton>|Sì|No|No|Yes|Sì|
|<xref:System.Windows.Forms.ToolStripLabel>|Sì|No|No|Yes|Sì|
|<xref:System.Windows.Forms.ToolStripSeparator>|Sì|Sì|Sì|No|Yes|
|<xref:System.Windows.Forms.ToolStripDropDownButton>|Sì|No|No|Yes|Sì|
|<xref:System.Windows.Forms.ToolStripTextBox>|Sì|Sì|Sì|No|Sì|
|<xref:System.Windows.Forms.ToolStripMenuItem>|No|Yes|Sì|No|No|
|<xref:System.Windows.Forms.ToolStripStatusLabel>|No|No|No|Sì|No|
|<xref:System.Windows.Forms.ToolStripProgressBar>|Sì|No|No|Sì|No|
|<xref:System.Windows.Forms.ToolStripControlHost>|Yes|Sì|No|Yes|Sì|

### <a name="toolstripbutton"></a>ToolStripButton

<xref:System.Windows.Forms.ToolStripButton>è l'elemento del pulsante <xref:System.Windows.Forms.ToolStrip>per. È possibile visualizzarlo con diversi stili di bordo ed è possibile usarlo per rappresentare e attivare gli stati operativi. È anche possibile definirlo in modo che abbia lo stato attivo per impostazione predefinita.

### <a name="toolstriplabel"></a>ToolStripLabel

Fornisce <xref:System.Windows.Forms.ToolStripLabel> la funzionalità di etichetta <xref:System.Windows.Forms.ToolStrip> nei controlli. È <xref:System.Windows.Forms.ToolStripLabel> come un <xref:System.Windows.Forms.ToolStripButton> che non ottiene lo stato attivo per impostazione predefinita e che non esegue il rendering come push o evidenziato.

<xref:System.Windows.Forms.ToolStripLabel>Poiché un elemento ospitato supporta le chiavi di accesso.

Utilizzare le <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>proprietà <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>, e <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> su un <xref:System.Windows.Forms.ToolStripLabel> per supportare il controllo dei collegamenti in <xref:System.Windows.Forms.ToolStrip>un oggetto.

### <a name="toolstripstatuslabel"></a>ToolStripStatusLabel

<xref:System.Windows.Forms.ToolStripStatusLabel>è una versione di <xref:System.Windows.Forms.ToolStripLabel> progettata specificamente per l'utilizzo <xref:System.Windows.Forms.StatusStrip>in. Le funzionalità speciali includono <xref:System.Windows.Forms.ToolStripStatusLabel.BorderStyle%2A>, <xref:System.Windows.Forms.ToolStripStatusLabel.BorderSides%2A>e <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.

### <a name="toolstripseparator"></a>ToolStripSeparator

Il <xref:System.Windows.Forms.ToolStripSeparator> aggiunge una linea verticale o orizzontale a una barra degli strumenti o a un menu, a seconda dell'orientamento. Consente di raggruppare o distinguere gli elementi, ad esempio quelli presenti in un menu.

È possibile aggiungere un <xref:System.Windows.Forms.ToolStripSeparator> oggetto in fase di progettazione selezionandolo da un elenco a discesa. Tuttavia, è anche possibile creare automaticamente un <xref:System.Windows.Forms.ToolStripSeparator> oggetto digitando un trattino (-) nel nodo del modello della finestra <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> di progettazione o nel metodo.

### <a name="toolstripcontrolhost"></a>ToolStripControlHost

<xref:System.Windows.Forms.ToolStripControlHost>è la classe di base astratta <xref:System.Windows.Forms.ToolStripComboBox>per <xref:System.Windows.Forms.ToolStripTextBox>, e <xref:System.Windows.Forms.ToolStripProgressBar>. <xref:System.Windows.Forms.ToolStripControlHost>può ospitare altri controlli, inclusi i controlli personalizzati, in due modi:

- Costruire un <xref:System.Windows.Forms.ToolStripControlHost> oggetto con una classe che deriva da <xref:System.Windows.Forms.Control>. Per accedere completamente alle proprietà e al controllo ospitato, è necessario eseguire <xref:System.Windows.Forms.ToolStripControlHost.Control%2A> il cast della proprietà alla classe effettiva che rappresenta.

- Estendere <xref:System.Windows.Forms.ToolStripControlHost>e nel costruttore senza parametri della classe ereditata chiamare il costruttore della classe di base passando una classe che deriva da <xref:System.Windows.Forms.Control>. Questa opzione consente di eseguire il wrapping dei metodi e delle proprietà di controllo comuni <xref:System.Windows.Forms.ToolStrip>per semplificare l'accesso in un.

### <a name="toolstripcombobox"></a>ToolStripComboBox

<xref:System.Windows.Forms.ToolStripComboBox>è l' <xref:System.Windows.Forms.ComboBox> oggetto ottimizzato per l' <xref:System.Windows.Forms.ToolStrip>hosting in un oggetto. Un subset delle proprietà e degli eventi del controllo ospitato viene esposto a <xref:System.Windows.Forms.ToolStripComboBox> livello, ma il controllo sottostante <xref:System.Windows.Forms.ComboBox> è completamente accessibile tramite la <xref:System.Windows.Forms.ToolStripComboBox.ComboBox%2A> proprietà.

### <a name="toolstriptextbox"></a>ToolStripTextBox

<xref:System.Windows.Forms.ToolStripTextBox>è l' <xref:System.Windows.Forms.TextBox> oggetto ottimizzato per l' <xref:System.Windows.Forms.ToolStrip>hosting in un oggetto. Un subset delle proprietà e degli eventi del controllo ospitato viene esposto a <xref:System.Windows.Forms.ToolStripTextBox> livello, ma il controllo sottostante <xref:System.Windows.Forms.TextBox> è completamente accessibile tramite la <xref:System.Windows.Forms.ToolStripTextBox.TextBox%2A> proprietà.

### <a name="toolstripprogressbar"></a>ToolStripProgressBar

<xref:System.Windows.Forms.ToolStripProgressBar>è l' <xref:System.Windows.Forms.ProgressBar> oggetto ottimizzato per l' <xref:System.Windows.Forms.ToolStrip>hosting in un oggetto. Un subset delle proprietà e degli eventi del controllo ospitato viene esposto a <xref:System.Windows.Forms.ToolStripProgressBar> livello, ma il controllo sottostante <xref:System.Windows.Forms.ProgressBar> è completamente accessibile tramite la <xref:System.Windows.Forms.ToolStripProgressBar.ProgressBar%2A> proprietà.

### <a name="toolstripdropdownitem"></a>ToolStripDropDownItem

<xref:System.Windows.Forms.ToolStripDropDownItem>è la classe di base astratta <xref:System.Windows.Forms.ToolStripMenuItem>per <xref:System.Windows.Forms.ToolStripDropDownButton>, e <xref:System.Windows.Forms.ToolStripSplitButton>, che può ospitare direttamente gli elementi o ospitare elementi aggiuntivi in un contenitore a discesa. A tale scopo, impostare la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDown%2A> proprietà su un <xref:System.Windows.Forms.ToolStripDropDown> oggetto e impostare <xref:System.Windows.Forms.ToolStrip.Items%2A> la proprietà dell' <xref:System.Windows.Forms.ToolStripDropDown>oggetto. Accedere a questi elementi a discesa direttamente tramite la <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItems%2A> proprietà.

### <a name="toolstripmenuitem"></a>ToolStripMenuItem

<xref:System.Windows.Forms.ToolStripMenuItem>è un <xref:System.Windows.Forms.ToolStripDropDownItem> oggetto che funziona <xref:System.Windows.Forms.ToolStripDropDownMenu> con <xref:System.Windows.Forms.ContextMenuStrip> e per gestire la disposizione speciale di evidenziazione, layout e colonna per i menu.

### <a name="toolstripdropdownbutton"></a>ToolStripDropDownButton

<xref:System.Windows.Forms.ToolStripDropDownButton>ha un <xref:System.Windows.Forms.ToolStripButton>aspetto simile a, ma mostra un'area a discesa quando l'utente fa clic su di essa. Nascondere o visualizzare la freccia a discesa impostando la <xref:System.Windows.Forms.ToolStripDropDownButton.ShowDropDownArrow%2A> proprietà. <xref:System.Windows.Forms.ToolStripDropDownButton>ospita un <xref:System.Windows.Forms.ToolStripOverflowButton> oggetto che visualizza gli elementi che <xref:System.Windows.Forms.ToolStrip>hanno overflow.

### <a name="toolstripsplitbutton"></a>ToolStripSplitButton

<xref:System.Windows.Forms.ToolStripSplitButton>combina il pulsante e la funzionalità del pulsante a discesa.

Utilizzare la <xref:System.Windows.Forms.ToolStripSplitButton.DefaultItem%2A> proprietà per sincronizzare l' <xref:System.Windows.Forms.Control.Click> evento dell'elemento a discesa scelto con l'elemento visualizzato sul pulsante.

### <a name="toolstripitem-generic-features"></a>Funzionalità generiche di ToolStripItem

<xref:System.Windows.Forms.ToolStripItem>in sono disponibili le seguenti funzionalità e opzioni generiche per l'ereditarietà dei controlli:

- Eventi principali

- Gestione delle immagini

- Allineamento

- Relazione tra testo e immagine

- Stile di visualizzazione

#### <a name="core-events"></a>Eventi principali

<xref:System.Windows.Forms.ToolStripItem>i controlli ricevono i propri eventi click, mouse e Paint e possono anche eseguire alcune operazioni di pre-elaborazione della tastiera.

#### <a name="image-handling"></a>Gestione delle immagini

Le <xref:System.Windows.Forms.ToolStripItem.Image%2A>proprietà <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A>, ,<xref:System.Windows.Forms.ToolStripItem.ImageIndex%2A> ,<xref:System.Windows.Forms.ToolStripItem.ImageKey%2A>e riguardano<xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> vari aspetti della gestione delle immagini. Utilizzare le immagini <xref:System.Windows.Forms.ToolStrip> nei controlli impostando queste proprietà direttamente o impostando la proprietà solo <xref:System.Windows.Forms.ToolStrip.ImageList%2A> in fase di esecuzione.

Il ridimensionamento delle immagini è determinato dall'interazione delle proprietà <xref:System.Windows.Forms.ToolStrip> in <xref:System.Windows.Forms.ToolStripItem>e, come indicato di seguito:

- <xref:System.Windows.Forms.ToolStrip.ImageScalingSize%2A>scala dell'immagine finale determinata dalla combinazione dell' <xref:System.Windows.Forms.ToolStripItem.ImageScaling%2A> impostazione dell'immagine e dell' <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> impostazione del contenitore.

  - Se <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> <xref:System.Windows.Forms.ToolStripItemImageScaling> è `true` (impostazione predefinita) e è <xref:System.Windows.Forms.ToolStripItemImageScaling.SizeToFit>, non si verifica alcun ridimensionamento dell' <xref:System.Windows.Forms.ToolStrip> immagine e la dimensione corrisponde a quella dell'elemento più grande o a una dimensione minima prestabilita.

  - Se <xref:System.Windows.Forms.ToolStrip.AutoSize%2A> è `false` e è<xref:System.Windows.Forms.ToolStripItemImageScaling> <xref:System.Windows.Forms.ToolStrip> , non viene eseguita né l'immagine né il ridimensionamento. <xref:System.Windows.Forms.ToolStripItemImageScaling.None>

#### <a name="alignment"></a>Allineamento

Il valore della <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> proprietà determina la fine <xref:System.Windows.Forms.ToolStrip> di in corrispondenza della quale viene visualizzato un elemento. La <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> proprietà funziona solo quando lo stile <xref:System.Windows.Forms.ToolStrip> di layout di è impostato su uno dei valori di overflow dello stack.

Gli elementi vengono posizionati <xref:System.Windows.Forms.ToolStrip> in nell'ordine in cui gli elementi vengono visualizzati nella raccolta Items. Per modificare a livello di codice la posizione in cui un elemento è <xref:System.Windows.Forms.ToolStripItemCollection.Insert%2A> disposto, utilizzare il metodo per spostare l'elemento nella raccolta. Questo metodo sposta l'elemento senza duplicarlo.

#### <a name="text-and-image-relationship"></a>Relazione tra testo e immagine

La <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> proprietà definisce la posizione relativa dell'immagine rispetto al testo in un oggetto <xref:System.Windows.Forms.ToolStripItem>. Gli elementi che non dispongono di un'immagine, un testo o entrambi sono considerati casi speciali, <xref:System.Windows.Forms.ToolStripItem> in modo che non venga visualizzato un punto vuoto per l'elemento o gli elementi mancanti.

#### <a name="display-style"></a>Stile di visualizzazione

<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>consente di impostare i valori delle proprietà Text e image di un elemento visualizzando solo le informazioni desiderate. Viene in genere utilizzato per modificare solo lo stile di visualizzazione quando si visualizza lo stesso elemento in un contesto diverso.

## <a name="accessory-classes"></a>Classi accessorie

Le classi che forniscono diverse altre funzionalità includono:

- <xref:System.Windows.Forms.ToolStripManager>supporta <xref:System.Windows.Forms.ToolStrip>le attività correlate a per intere applicazioni, ad esempio l'Unione, le impostazioni e le opzioni renderer.

- <xref:System.Windows.Forms.ToolStripRenderer>consente di applicare un particolare stile o tema a un oggetto <xref:System.Windows.Forms.ToolStrip> in modo semplice.

- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>Crea le penne e i pennelli in base a una tabella<xref:System.Windows.Forms.ProfessionalColorTable>colori sostituibile ().

- <xref:System.Windows.Forms.ToolStripSystemRenderer>applica i colori di sistema e uno stile di <xref:System.Windows.Forms.ToolStrip> visualizzazione Flat alle applicazioni.

- <xref:System.Windows.Forms.ToolStripContainer>è simile a <xref:System.Windows.Forms.SplitContainer>. USA quattro pannelli laterali ancorati (istanze di <xref:System.Windows.Forms.ToolStripPanel>) e un pannello centrale (un'istanza di <xref:System.Windows.Forms.ToolStripContentPanel>) per creare una disposizione tipica. Non è possibile rimuovere i pannelli laterali, ma è possibile nasconderli. Non è possibile rimuovere né nascondere il pannello centrale. È possibile disporre uno o più <xref:System.Windows.Forms.ToolStrip>controlli <xref:System.Windows.Forms.MenuStrip>, o <xref:System.Windows.Forms.StatusStrip> nei pannelli laterali ed è possibile usare il pannello centrale per altri controlli. Fornisce <xref:System.Windows.Forms.ToolStripContentPanel> inoltre un modo per ottenere il supporto del renderer nel corpo del form per un aspetto coerente. <xref:System.Windows.Forms.ToolStripContainer>non supporta l'interfaccia a documenti multipli (MDI).

- <xref:System.Windows.Forms.ToolStripPanel>fornisce spazio per lo spostare e la <xref:System.Windows.Forms.ToolStrip> disposizione dei controlli. È possibile utilizzare un solo pannello se si sceglie e <xref:System.Windows.Forms.ToolStripPanel> funziona correttamente negli scenari MDI.

## <a name="see-also"></a>Vedere anche

- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)
- [Controllo ToolStrip](toolstrip-control-windows-forms.md)
- [Controllo MenuStrip](menustrip-control-windows-forms.md)
- [Controllo StatusStrip](statusstrip-control.md)
- [Controllo ContextMenuStrip](contextmenustrip-control.md)
- [Controllo BindingNavigator](bindingnavigator-control-windows-forms.md)
