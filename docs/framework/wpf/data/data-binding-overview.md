---
title: Panoramica sul data binding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data conversion for binding [WPF]
- binding data [WPF], about data binding
- data binding [WPF], about data binding
- conversion for data binding [WPF]
ms.assetid: c707c95f-7811-401d-956e-2fffd019a211
ms.openlocfilehash: ad86577aa4a66d9296c3c1844c9f8fa8c2b89d24
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364827"
---
# <a name="data-binding-overview"></a>Panoramica sul data binding
Il data binding [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] rappresenta per le applicazioni un modo semplice e coerente di presentare i dati e di interagire con essi. È possibile eseguire il data binding degli elementi a diverse origini dati sotto forma di oggetti [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] e [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]. <xref:System.Windows.Controls.ContentControl>s, ad esempio <xref:System.Windows.Controls.Button> e <xref:System.Windows.Controls.ItemsControl>s, ad esempio <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.ListView> dispongono di funzionalità incorporate per abilitare lo stile flessibile dei singoli elementi di dati o raccolte di elementi di dati. In cima ai dati è possibile generare visualizzazioni di ordinamento, filtro e raggruppamento.  
  
 La funzionalità di data binding in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presenta molti vantaggi rispetto ai modelli tradizionali, tra cui un'ampia gamma di proprietà che supportano implicitamente il data binding, una rappresentazione dei dati mediante [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] flessibile e una netta separazione tra logica di business e [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 In questo argomento illustra prima di tutto i concetti fondamentali [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding e successivamente passa ad analizzare l'utilizzo del <xref:System.Windows.Data.Binding> classe e altre funzionalità di data binding.  
  
  
<a name="what_is_data_binding"></a>   
## <a name="what-is-data-binding"></a>Definizione di data binding  
 Il data binding è il processo tramite cui viene stabilita una connessione tra l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione e la logica di business. Se le impostazioni del binding sono corrette e i dati forniscono le notifiche appropriate, quando il valore dei dati viene modificato, gli elementi a essi associati riflettono automaticamente le modifiche apportate. Il data binding prevede anche che, se una rappresentazione esterna dei dati in un elemento viene modificata, i dati sottostanti possono essere automaticamente aggiornati in modo da riflettere la modifica. Ad esempio, se l'utente modifica il valore in un <xref:System.Windows.Controls.TextBox> elemento, il valore di dati sottostante viene aggiornata automaticamente per riflettere tale modifica.  
  
 Un utilizzo tipico del data binding consiste nell'inserimento di dati di configurazione locale o del server in moduli o in altri controlli [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] questo concetto viene esteso per includere il binding di un'ampia gamma di proprietà a varie origini dati. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le proprietà di dipendenza degli elementi possono essere associate a oggetti [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] (inclusi gli oggetti [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] o gli oggetti associati a servizi Web e a proprietà Web) e a dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)].  
  
 Per un esempio di data binding, osservare l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione seguente disponibile in [Demo di data binding](https://go.microsoft.com/fwlink/?LinkID=163703):  
  
 ![Screenshot di esempio di data binding](./media/databinding-databindingdemo.png "DataBinding_DataBindingDemo")  
  
 La figura precedente mostra l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di un'applicazione che visualizza un elenco di articoli da vendere all'asta. L'applicazione mostra le funzionalità di data binding seguenti:  
  
-   Il contenuto di <xref:System.Windows.Controls.ListBox> è associato a una raccolta di *AuctionItem* oggetti. Un oggetto *AuctionItem* dispone di diverse proprietà, tra cui *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures* e così via.  
  
-   I dati (*AuctionItem* oggetti) visualizzati nei <xref:System.Windows.Controls.ListBox> è basato su modelli in modo che la descrizione e il prezzo corrente vengono visualizzati per ogni elemento. Questa operazione viene eseguita usando un <xref:System.Windows.DataTemplate>. L'aspetto di ogni articolo dipende inoltre dal valore di *SpecialFeatures* dell'oggetto *AuctionItem* visualizzato. Se il valore di *SpecialFeatures* dell'oggetto *AuctionItem* è *Color*, l'articolo avrà un bordo blu. Se il valore è *Highlight*, l'articolo sarà dotato di un bordo arancione e di una stella. La sezione [Modelli di dati](#data_templating) include informazioni sull'applicazione di modelli ai dati.  
  
-   L'utente può raggruppare, filtrare o ordinare i dati utilizzando il <xref:System.Windows.Controls.CheckBox>es fornito. Nell'immagine precedente, "Group by category" e "Sort by category and date" <xref:System.Windows.Controls.CheckBox>sono stati selezionati. I dati sono raggruppati in base alla categoria del prodotto e i nomi delle categorie seguono l'ordine alfabetico. Benché non risulti evidente dalla figura, gli articoli sono anche ordinati in base alla data di inizio all'interno di ogni categoria. Questa operazione viene eseguita usando una *visualizzazione di raccolta*. La sezione [Binding alle raccolte](#binding_to_collections) descrive le visualizzazioni di raccolta.  
  
-   Quando l'utente seleziona un elemento, il <xref:System.Windows.Controls.ContentControl> vengono visualizzati i dettagli dell'elemento selezionato. Si parla in questo caso di *scenario master-dettagli*. La sezione [Scenario master-dettagli](#master_detail_scenario) include informazioni su questo tipo di scenario di binding.  
  
-   Il tipo dei *StartDate* è di proprietà <xref:System.DateTime>, che restituisce una data che include l'ora fino al millisecondo. In questa applicazione è stato usato un convertitore personalizzato per visualizzare una stringa di data più breve. La sezione [Conversione dei dati](#data_conversion) include informazioni sui convertitori.  
  
 Quando l'utente fa clic sul pulsante *Add Product* (Aggiungi prodotto), viene visualizzato il modulo seguente:  
  
 ![Pagina Add Product Listing](./media/databinding-demo-addproductlisting.png "DataBinding_Demo_AddProductListing")  
  
 L'utente può modificare i campi del modulo, visualizzare in anteprima il prodotto usando i riquadri di anteprima rapida e di anteprima più dettagliata e quindi fare clic su *Submit* (Inoltra) per aggiungere il nuovo prodotto. Le funzionalità di raggruppamento, filtro e ordinamento esistenti verranno applicate alla nuova voce. In questo caso specifico, l'articolo immesso nella figura precedente verrà visualizzato come secondo articolo della categoria *Computer*.  
  
 Non visualizzato in questa immagine è la logica di convalida fornita nel *data di inizio* <xref:System.Windows.Controls.TextBox>. Se l'utente immette un valore non valido date (formattazione non validi o una data già trascorsa), l'utente riceverà una notifica con un <xref:System.Windows.Controls.ToolTip> e un punto esclamativo rosso accanto al <xref:System.Windows.Controls.TextBox>. La sezione [Convalida dei dati](#data_validation) descrive come creare la logica di convalida.  
  
 Prima di approfondire le diverse funzionalità di data binding delineate finora, verranno trattati nella sezione successiva i concetti fondamentali necessari a comprendere il data binding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="basic-data-binding-concepts"></a>Concetti di base sul data binding  
  
 Indipendentemente dall'elemento che si intende associare e dalla natura dell'origine dati, ogni binding si basa sempre sul modello illustrato nella figura seguente:  
  
 ![Diagramma di data binding di base](./media/databindingmostbasic.png "DataBindingMostBasic")  
  
 Come illustrato nella figura precedente, il data binding funge essenzialmente da ponte tra la destinazione e l'origine del binding. La figura illustra i concetti fondamentali seguenti relativi al data binding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   Ogni binding possiede in genere quattro componenti: un oggetto di destinazione del binding, una proprietà di destinazione, un'origine del binding e un percorso al valore nell'origine del binding da usare. Ad esempio, se si desidera associare il contenuto di un <xref:System.Windows.Controls.TextBox> per il *nome* proprietà di un *dipendente* dell'oggetto, l'oggetto di destinazione è il <xref:System.Windows.Controls.TextBox>, la proprietà di destinazione è il <xref:System.Windows.Controls.TextBox.Text%2A> proprietà, è il valore da usare *Name*, e l'oggetto di origine è la *dipendente* oggetto.  
  
-   La proprietà di destinazione deve essere una proprietà di dipendenza. La maggior parte delle <xref:System.Windows.UIElement> proprietà sono proprietà di dipendenza e la maggior parte delle proprietà di dipendenza, ad eccezione di quelli di sola lettura, supportano il data binding per impostazione predefinita. (Solo <xref:System.Windows.DependencyObject> tipi possono definire le proprietà di dipendenza e tutti i <xref:System.Windows.UIElement>derivano da <xref:System.Windows.DependencyObject>.)  
  
-   Sebbene non sia specificato nella figura, è importante notare che l'oggetto di origine del binding non è necessariamente costituito da un oggetto [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] personalizzato. Il data binding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta dati nel formato di oggetti [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] e [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Per fornire alcuni esempi, l'origine del binding può essere un <xref:System.Windows.UIElement>, qualsiasi oggetto elenco, una [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] oggetto associato [!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)] dati o servizi Web o un oggetto XmlNode che contiene il [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati. Per altre informazioni, vedere [Cenni preliminari sulle origini del binding](binding-sources-overview.md).  
  
 Come detto in altri argomenti concernenti [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)], è importante ricordare che quando si stabilisce un binding, si associa una destinazione del binding *a* un'origine del binding. Ad esempio, se si visualizzano alcuni sottostante [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] i dati in un <xref:System.Windows.Controls.ListBox> tramite data binding, si esegue il binding i <xref:System.Windows.Controls.ListBox> per il [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati.  
  
 Per stabilire un'associazione, si utilizza il <xref:System.Windows.Data.Binding> oggetto. Il resto di questo argomento vengono descritti molti dei concetti associati e alcune delle proprietà e l'utilizzo del <xref:System.Windows.Data.Binding> oggetto.  
  
<a name="direction_of_data_flow"></a>   
### <a name="direction-of-the-data-flow"></a>Direzione del flusso di dati  
 Come indicato in precedenza e come indicato dalla freccia nella figura precedente, il flusso di dati di un binding può andare dalla destinazione del binding all'origine del binding (ad esempio, il valore di origine cambia quando un utente modifica il valore di un <xref:System.Windows.Controls.TextBox>) e/o dall'origine dell'associazione per la destinazione del binding (ad esempio, il <xref:System.Windows.Controls.TextBox> contenuto viene aggiornato con le modifiche nell'origine del binding) se l'origine del binding fornisce le notifiche appropriate.  
  
 È possibile fare in modo che l'applicazione consenta agli utenti di modificare i dati e di propagarli all'oggetto di origine oppure è possibile fare in modo che gli utenti non possano aggiornare i dati di origine. È possibile controllare questo impostando il <xref:System.Windows.Data.Binding.Mode%2A> proprietà del <xref:System.Windows.Data.Binding> oggetto. La figura seguente illustra i diversi tipi di flusso di dati:  
  
 ![Flusso di dati nel data binding](./media/databinding-dataflow.png "DataBinding_DataFlow")  
  
-   <xref:System.Windows.Data.BindingMode.OneWay> Binding fa sì che le modifiche apportate alla proprietà di origine per aggiornare automaticamente la proprietà di destinazione, ma le modifiche apportate alla proprietà di destinazione non vengono propagate alla proprietà di origine. Questo tipo di binding è appropriato se il controllo da associare è implicitamente di sola lettura. Può accadere ad esempio che si effettui un binding a un'origine quale un controllo Stock Ticker oppure che la proprietà di destinazione non possieda un'interfaccia di controllo tramite la quale apportare modifiche, come nel caso di un colore di sfondo con binding a dati di una tabella. Se non è necessario monitorare le modifiche delle proprietà di destinazione, l'uso della modalità di associazione <xref:System.Windows.Data.BindingMode.OneWay> consente di evitare il sovraccarico della modalità di binding <xref:System.Windows.Data.BindingMode.TwoWay>.  
  
-   <xref:System.Windows.Data.BindingMode.TwoWay> Binding fa sì che le modifiche alla proprietà di origine o la proprietà di destinazione per aggiornare automaticamente l'altra. Questo tipo di binding è adatto a moduli modificabili o ad altri scenari [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] completamente interattivi. Per impostazione predefinita la maggior parte delle proprietà <xref:System.Windows.Data.BindingMode.OneWay> binding, ma alcune proprietà di dipendenza (in genere le proprietà dei controlli modificabili dall'utente, ad esempio il <xref:System.Windows.Controls.TextBox.Text%2A> proprietà di <xref:System.Windows.Controls.TextBox> e il <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> proprietà di <xref:System.Windows.Controls.CheckBox>) predefinito per <xref:System.Windows.Data.BindingMode.TwoWay> dell'associazione. Un modo programmatico per determinare se l'associazione di una proprietà di dipendenza è unidirezionale o bidirezionale per impostazione predefinita, consiste nell'ottenere i metadati della proprietà con <xref:System.Windows.DependencyProperty.GetMetadata%2A> e quindi controllare il valore booleano della proprietà <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>.  
  
-   <xref:System.Windows.Data.BindingMode.OneWayToSource> è l'opposto di <xref:System.Windows.Data.BindingMode.OneWay> binding; Aggiorna la proprietà di origine quando cambia la proprietà di destinazione. Può essere usata, ad esempio, nel caso in cui si debba semplicemente rivalutare il valore di origine dall'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
-   Non è illustrata nella figura è <xref:System.Windows.Data.BindingMode.OneTime> associazione, in modo che la proprietà di origine inizializzare la proprietà di destinazione, ma non vengono propagate le modifiche successive. Ciò significa che se il contesto dati subisce una modifica o l'oggetto nel contesto dati viene modificato, la modifica non si riflette nella proprietà di destinazione. Questo tipo di binding è appropriato per dati in cui è opportuno usare uno snapshot dello stato corrente o che sono realmente statici. Questo tipo di binding è utile anche se si vuole inizializzare la proprietà di destinazione con un valore ricavato da una proprietà di origine e il contesto dei dati non è noto in anticipo. Si tratta essenzialmente di una forma più semplice di binding <xref:System.Windows.Data.BindingMode.OneWay> che offre prestazioni migliori nei casi in cui il valore di origine non cambia.  
  
 Si noti che per rilevare le modifiche di origine (applicabile per <xref:System.Windows.Data.BindingMode.OneWay> e <xref:System.Windows.Data.BindingMode.TwoWay> associazioni), l'origine deve implementare un meccanismo di notifica di modifica proprietà appropriato, ad esempio <xref:System.ComponentModel.INotifyPropertyChanged>. Visualizzare [implementare la notifica di modifica proprietà](how-to-implement-property-change-notification.md) per un esempio di un <xref:System.ComponentModel.INotifyPropertyChanged> implementazione.  
  
 Il <xref:System.Windows.Data.Binding.Mode%2A> pagina delle proprietà fornisce altre informazioni sulle modalità di associazione e un esempio di come specificare la direzione di un'associazione.  
  
<a name="what_triggers_source_updates"></a>   
### <a name="what-triggers-source-updates"></a>Eventi che generano gli aggiornamenti dell'origine  
 Le associazioni di tipo <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> ascoltare le modifiche alla proprietà di destinazione e quindi propagarli all'origine. Questo processo è noto come aggiornamento dell'origine. Può accadere ad esempio che si modifichi il testo di un oggetto TextBox per modificare il valore di origine sottostante. Come descritto nella sezione precedente, la direzione del flusso di dati è determinata dal valore della <xref:System.Windows.Data.Binding.Mode%2A> proprietà dell'associazione.  
  
 Il valore di origine viene aggiornato durante la modifica del testo o dopo aver apportato le modifiche del testo e aver spostato il mouse da TextBox? Il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà dell'associazione determina ciò che attiva l'aggiornamento dell'origine. I puntini delle frecce a destra nella figura seguente viene illustrato il ruolo del <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà:  
  
 ![Diagramma di UpdateSourceTrigger](./media/databindingupdatesourcetrigger.png "DataBindingUpdateSourceTrigger")  
  
 Se il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore è <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, quindi il valore a cui punta di freccia a destra <xref:System.Windows.Data.BindingMode.TwoWay> o il <xref:System.Windows.Data.BindingMode.OneWayToSource> binding viene aggiornato non appena le modifiche alle proprietà di destinazione. Tuttavia, se il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore è <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>, quindi tale valore viene aggiornato soltanto con il nuovo valore quando la proprietà di destinazione perde lo stato attivo.  
  
 Simile al <xref:System.Windows.Data.Binding.Mode%2A> proprietà, proprietà di dipendenza diverse possiedono predefinite diverse <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valori. Il valore predefinito per la maggior parte delle proprietà di dipendenza è <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, mentre la proprietà <xref:System.Windows.Controls.TextBox.Text%2A> ha il valore predefinito <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Ciò significa che gli aggiornamenti dell'origine avvengono in genere ogni volta che le modifiche alle proprietà di destinazione, che va bene per <xref:System.Windows.Controls.CheckBox>es e altri controlli semplici. Nel caso dei campi di testo, tuttavia, l'esecuzione di un aggiornamento a ogni pressione di tasto può comportare un calo di prestazioni nonché negare all'utente la possibilità di tornare indietro e correggere eventuali errori di digitazione prima di confermare il nuovo valore. Ecco perché il <xref:System.Windows.Controls.TextBox.Text%2A> proprietà ha un valore predefinito di <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> invece di <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  
  
 Vedere le <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> pagina delle proprietà per informazioni su come trovare il valore predefinito <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore di una proprietà di dipendenza.  
  
 Nella tabella seguente fornisce uno scenario di esempio per ognuno <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore utilizzando il <xref:System.Windows.Controls.TextBox> ad esempio:  
  
|Valore di UpdateSourceTrigger|Quando il valore di origine viene aggiornato|Scenario di esempio per TextBox|  
|-------------------------------|----------------------------------------|----------------------------------|  
|LostFocus (valore predefinito per <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>)|Quando il controllo TextBox perde lo stato attivo|Oggetto <xref:System.Windows.Controls.TextBox> associata con la logica di convalida (vedere la sezione convalida dei dati)|  
|PropertyChanged|Durante la digitazione di <xref:System.Windows.Controls.TextBox>|<xref:System.Windows.Controls.TextBox> controlli in una finestra della chat|  
|Explicit|Quando l'applicazione chiama <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|<xref:System.Windows.Controls.TextBox> controlli in un modulo modificabile (Aggiorna i valori di origine solo quando l'utente fa clic sul pulsante Invia)|  
  
 Per un esempio, vedere [Procedura: Controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
<a name="creating_a_binding"></a>   
## <a name="creating-a-binding"></a>Creazione di un'associazione  
  
 Per riepilogare alcuni dei concetti illustrati nelle sezioni precedenti, si stabilisce un'associazione utilizzando il <xref:System.Windows.Data.Binding> oggetto e ogni associazione è in genere include quattro componenti: associazione di destinazione, la proprietà di destinazione, origine dell'associazione e un percorso per il valore di origine da utilizzare. Questa sezione illustra come impostare un binding.  
  
 Si consideri l'esempio seguente, in cui l'oggetto origine del binding è una classe denominata *MyData* definita nello spazio dei nomi *SDKSample*. A scopo dimostrativo, la classe *MyData* dispone di una proprietà stringa denominata *ColorName*, il cui valore è impostato su "Red". L'esempio genera quindi un pulsante con uno sfondo rosso.  
  
 [!code-xaml[BindNonTextProperty#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 Per altre informazioni sulla sintassi della dichiarazione di binding e per esempi su come impostare un binding nel codice, vedere [Cenni preliminari sulle dichiarazioni di binding](binding-declarations-overview.md).  
  
 Se si applica questo esempio al diagramma di base, la figura risultante sarà simile alla seguente. Si tratta di un <xref:System.Windows.Data.BindingMode.OneWay> associazione perché la proprietà Background supporta <xref:System.Windows.Data.BindingMode.OneWay> binding per impostazione predefinita.  
  
 ![Diagramma di data binding](./media/databindingbuttonbackgroundexample.png "DataBindingButtonBackgroundExample")  
  
 È lecito chiedersi perché ciò funziona anche se il *ColorName* proprietà è di tipo stringa mentre la <xref:System.Windows.Controls.Control.Background%2A> proprietà è di tipo <xref:System.Windows.Media.Brush>. In questo caso viene usata la conversione di tipi predefinita, descritta nella sezione [Conversione dei dati](#data_conversion).  
  
<a name="specifying_the_binding_source"></a>   
### <a name="specifying-the-binding-source"></a>Specifica dell'origine del binding  
 Si noti che nell'esempio precedente, l'origine del binding viene specificato impostando il <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà di <xref:System.Windows.Controls.DockPanel> elemento. Il <xref:System.Windows.Controls.Button> eredita quindi il <xref:System.Windows.FrameworkElement.DataContext%2A> valore il <xref:System.Windows.Controls.DockPanel>, che costituisce l'elemento padre. Come già detto, l'oggetto origine del binding è uno dei quattro componenti necessari di un binding. Se quindi non si specifica l'oggetto origine del binding, questa non viene creata.  
  
 Esistono diversi modi per specificare l'oggetto origine del binding. Uso di <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà su un elemento padre è utile quando si associano più proprietà alla stessa origine. In alcuni casi, tuttavia, è preferibile specificare l'origine del binding in singole dichiarazioni di binding. Per l'esempio precedente, invece di usare la <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà, è possibile specificare l'origine del binding impostando la <xref:System.Windows.Data.Binding.Source%2A> proprietà direttamente nella dichiarazione di binding del pulsante, come nell'esempio seguente:  
  
 [!code-xaml[BindNonTextProperty#BackgroundBindingCompact](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 Diverso da impostare il <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà su un elemento direttamente, che eredita le <xref:System.Windows.FrameworkElement.DataContext%2A> valore da un predecessore (ad esempio, il pulsante nel primo esempio) e specificare in modo esplicito l'origine del binding impostando il <xref:System.Windows.Data.Binding.Source%2A> proprietà il <xref:System.Windows.Data.Binding> (ad esempio, il pulsante nell'ultimo esempio), è anche possibile usare la <xref:System.Windows.Data.Binding.ElementName%2A> proprietà o il <xref:System.Windows.Data.Binding.RelativeSource%2A> proprietà per specificare l'origine del binding. Il <xref:System.Windows.Data.Binding.ElementName%2A> proprietà è utile quando si associa agli altri elementi dell'applicazione, ad esempio quando si utilizza un dispositivo di scorrimento per regolare la larghezza di un pulsante. Il <xref:System.Windows.Data.Binding.RelativeSource%2A> proprietà è utile quando è specificata l'associazione un <xref:System.Windows.Controls.ControlTemplate> o un <xref:System.Windows.Style>. Per altre informazioni, vedere [Procedura: Specificare l'origine del binding](how-to-specify-the-binding-source.md).  
  
<a name="specifying_the_path_to_the_value"></a>   
### <a name="specifying-the-path-to-the-value"></a>Specifica del percorso al valore  
 Se l'origine del binding è un oggetto, si utilizza il <xref:System.Windows.Data.Binding.Path%2A> proprietà per specificare il valore da usare per l'associazione. Se si esegue l'associazione [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dei dati, utilizzare il <xref:System.Windows.Data.Binding.XPath%2A> proprietà per specificare il valore. In alcuni casi, potrebbe essere applicabile all'utilizzo di <xref:System.Windows.Data.Binding.Path%2A> anche quando i dati sono di proprietà [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Ad esempio, se si vuole accedere alla proprietà Name di un XmlNode restituito (in seguito a una query XPath), è consigliabile usare la <xref:System.Windows.Data.Binding.Path%2A> oltre alla proprietà di <xref:System.Windows.Data.Binding.XPath%2A> proprietà.  
  
 Per informazioni sulla sintassi ed esempi, vedere la <xref:System.Windows.Data.Binding.Path%2A> e <xref:System.Windows.Data.Binding.XPath%2A> pagine delle proprietà.  
  
 Si noti che, sebbene sia stato sottolineato che il <xref:System.Windows.Data.Binding.Path%2A> al valore da usare è uno dei quattro componenti necessari di un binding, negli scenari che si desidera associare a un oggetto intero, il valore da usare sarebbe lo stesso dell'oggetto di origine di associazione. In questi casi, è possibile non specificare un <xref:System.Windows.Data.Binding.Path%2A>. Si consideri l'esempio seguente:  
  
 [!code-xaml[MasterDetail#EmptyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 L'esempio precedente usa la sintassi di binding vuota: {Binding}. In questo caso, il <xref:System.Windows.Controls.ListBox> eredita DataContext da un elemento DockPanel padre (non illustrato in questo esempio). Quando il percorso non viene specificato, per impostazione predefinita si esegue un binding all'intero oggetto. In altre parole, in questo esempio, il percorso è stato tralasciato poiché la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà per l'intero oggetto. Per informazioni più dettagliate, vedere la sezione [Binding alle raccolte](#binding_to_collections).  
  
 Oltre al binding a una raccolta, questo scenario è utile anche in caso di binding a un intero oggetto anziché a una singola proprietà di un oggetto. Si consideri ad esempio un oggetto origine di tipo stringa con un binding alla stringa stessa. Un altro scenario comune riguarda il binding di un elemento a un oggetto con numerose proprietà.  
  
 Affinché i dati siano significativi per la proprietà di destinazione associata, può essere necessario applicare logica personalizzata. Tale logica potrebbe essere un convertitore personalizzato, in assenza della conversione di tipi predefinita. Per informazioni sui convertitori, vedere [Conversione dei dati](#data_conversion).  
  
<a name="binding_bindingexpression"></a>   
### <a name="binding-and-bindingexpression"></a>Binding e BindingExpression  
 Prima di approfondire altri utilizzi del data binding e funzionalità, potrebbe essere utile per introdurre il <xref:System.Windows.Data.BindingExpression> classe. Come si è visto nelle sezioni precedenti, il <xref:System.Windows.Data.Binding> è la classe generale per la dichiarazione di un'associazione; il <xref:System.Windows.Data.Binding> classe include diverse proprietà che consentono di specificare le caratteristiche di un'associazione. Una classe correlata, <xref:System.Windows.Data.BindingExpression>, corrisponde all'oggetto sottostante che gestisce la connessione tra l'origine e destinazione. Un binding contiene tutte le informazioni condivisibili tra diverse espressioni di binding. Oggetto <xref:System.Windows.Data.BindingExpression> è un'espressione dell'istanza condivisibile e contiene tutte le informazioni sull'istanza del <xref:System.Windows.Data.Binding>.  
  
 Ad esempio, tenere presente quanto segue, dove *myDataObject* è un'istanza di *MyData* (classe), *myBinding* è l'origine <xref:System.Windows.Data.Binding> oggetto ed *MyData* classe è una classe definita contenente una proprietà stringa denominata *MyDataProperty*. Questo esempio associa il contenuto di testo *mytext*, un'istanza di <xref:System.Windows.Controls.TextBlock>, al *MyDataProperty*.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 È possibile usare lo stesso oggetto *myBinding* per creare altri binding. È ad esempio possibile usare l'oggetto *myBinding* per associare il contenuto di testo di una casella di controllo di testo a *MyDataProperty*. In questo scenario, saranno presenti due istanze del <xref:System.Windows.Data.BindingExpression> condividere la *myBinding* oggetto.  
  
 Oggetto <xref:System.Windows.Data.BindingExpression> oggetto può essere ottenuto tramite il valore restituito della chiamata al metodo <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> su un oggetto con associazione a dati. Gli argomenti seguenti vengono illustrati alcuni degli utilizzi del <xref:System.Windows.Data.BindingExpression> classe:  
  
-   [Procedura: ottenere l'oggetto di binding da una proprietà di destinazione associata](how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
-   [Procedura: Controllare il momento in cui il database di origine viene aggiornata dal testo di TextBox](how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## <a name="data-conversion"></a>Conversione dei dati  
 Nell'esempio precedente, il pulsante è rosso perché relativo <xref:System.Windows.Controls.Control.Background%2A> proprietà è associata a una proprietà di stringa con il valore "Red". Questo procedimento funziona perché è presente in un convertitore di tipi di <xref:System.Windows.Media.Brush> tipo in cui convertire il valore della stringa un <xref:System.Windows.Media.Brush>.  
  
 Se si aggiungono queste informazioni alla figura nella sezione [Creazione di un binding](#creating_a_binding), si ottiene un diagramma analogo al seguente:  
  
 ![Diagramma di data binding](./media/databindingbuttondefaultconversion.png "DataBindingButtonDefaultConversion")  
  
 Cosa accade però se anziché una proprietà di stringa del tipo di oggetto origine del binding è un *colore* vlastnosti typu <xref:System.Windows.Media.Color>? In tal caso, affinché l'associazione da usare è necessario prima disattivare la *colore* valore della proprietà in un elemento che il <xref:System.Windows.Controls.Control.Background%2A> proprietà accetta. È necessario creare un convertitore personalizzato implementando il <xref:System.Windows.Data.IValueConverter> interfaccia, come nell'esempio seguente:  
  
 [!code-csharp[ColorPicker_snip#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 Il <xref:System.Windows.Data.IValueConverter> pagina di riferimento vengono fornite ulteriori informazioni.  
  
 Il convertitore personalizzato viene ora usato al posto della conversione predefinita e il diagramma si presenta come segue:  
  
 ![Diagramma di data binding](./media/databindingconvertercolorexample.png "DataBindingConverterColorExample")  
  
 Come già detto, le conversioni predefinite possono essere disponibili o meno a seconda dei convertitori presenti nel tipo a cui si esegue il binding. Questo comportamento dipenderà dai convertitori di tipi disponibili nella destinazione. In caso di dubbio, creare un convertitore personalizzato.  
  
 Vengono riportati di seguito alcuni scenari tipici in cui è opportuno implementare un convertitore di dati:  
  
-   I dati devono essere visualizzati in modo diverso, a seconda delle impostazioni cultura. È ad esempio possibile implementare un convertitore di valuta o un convertitore di data/ora nel calendario in base ai valori o agli standard usati in specifiche impostazioni cultura.  
  
-   I dati usati non devono necessariamente modificare il valore di testo di una proprietà quanto piuttosto altri valori, ad esempio l'origine di un'immagine oppure il colore o lo stile del testo visualizzato. I convertitori possono essere usati in questo caso per convertire il binding di una proprietà considerata poco appropriata, ad esempio il binding di un campo di testo alla proprietà Background della cella di una tabella.  
  
-   Più controlli o più proprietà dei controlli sono associati agli stessi dati. In questo caso, il binding primario potrebbe semplicemente visualizzare il testo, mentre gli altri binding gestiscono problemi di visualizzazione specifici, usando comunque lo stesso binding come informazione di origine.  
  
-   Finora abbiamo non ancora analizzato <xref:System.Windows.Data.MultiBinding>, in una proprietà di destinazione è una raccolta di associazioni. Nel caso di un <xref:System.Windows.Data.MultiBinding>, si utilizza un oggetto personalizzato <xref:System.Windows.Data.IMultiValueConverter> per produrre un valore finale dai valori delle associazioni. È possibile ad esempio calcolare il colore dai valori rosso, blu e verde, ovvero valori che possono provenire da oggetti origine del binding identici o diversi. Vedere il <xref:System.Windows.Data.MultiBinding> pagina relativa alla classe per informazioni ed esempi.  
  
<a name="binding_to_collections"></a>   
## <a name="binding-to-collections"></a>Binding alle raccolte  
  
 Un oggetto origine del binding può essere considerato come un unico oggetto le cui proprietà contengono dati oppure come una raccolta di dati di oggetti polimorfici che spesso vengono raggruppati. Un esempio può essere il risultato di una query in un database. È stato finora illustrato solo il binding a singoli oggetti. Esiste tuttavia un altro scenario comune che è il binding a una raccolta di dati. Ad esempio, uno scenario comune consiste nell'usare un <xref:System.Windows.Controls.ItemsControl> , ad esempio un <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView>, o <xref:System.Windows.Controls.TreeView> per visualizzare una raccolta di dati, come avviene nell'applicazione illustrata nella [What ' s Data Binding?](#what_is_data_binding) sezione.  
  
 Anche in questo caso è possibile applicare il diagramma di base. Quando si associa un <xref:System.Windows.Controls.ItemsControl> a una raccolta, il diagramma appare come segue:  
  
 ![Diagramma di data binding di ItemsControl](./media/databindingitemscontrol.png "DataBindingItemsControl")  
  
 Come illustrato nella figura seguente, per associare un' <xref:System.Windows.Controls.ItemsControl> a un oggetto collection, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> è la proprietà da utilizzare. È possibile pensare <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> come contenuto della proprietà di <xref:System.Windows.Controls.ItemsControl>. Si noti che è l'associazione <xref:System.Windows.Data.BindingMode.OneWay> perché il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> supporta proprietà <xref:System.Windows.Data.BindingMode.OneWay> binding per impostazione predefinita.  
  
<a name="how_to_implement_collections"></a>   
### <a name="how-to-implement-collections"></a>Come implementare le raccolte  
 È possibile enumerare in qualsiasi raccolta che implementa il <xref:System.Collections.IEnumerable> interfaccia. Tuttavia, per impostare i binding dinamici in modo che gli inserimenti o eliminazioni nella raccolta di aggiornino il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] automaticamente, la raccolta deve implementare il <xref:System.Collections.Specialized.INotifyCollectionChanged> interfaccia. Questa interfaccia espone un evento che deve essere generato a ogni modifica della raccolta sottostante.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] fornisce il <xref:System.Collections.ObjectModel.ObservableCollection%601> classe, ovvero un'implementazione incorporata di una raccolta di dati che espone il <xref:System.Collections.Specialized.INotifyCollectionChanged> interfaccia. Si noti che per supportare pienamente il trasferimento dei valori dei dati dagli oggetti di origine alle destinazioni, ogni oggetto nella raccolta che supporta proprietà associabili deve implementare anche il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia. Per altre informazioni, vedere [Cenni preliminari sulle origini del binding](binding-sources-overview.md).  
  
 Prima di implementare una raccolta personalizzata, è consigliabile usare <xref:System.Collections.ObjectModel.ObservableCollection%601> o una delle raccolte esistenti classi, ad esempio <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>, e <xref:System.ComponentModel.BindingList%601>, tra le molte altre. Se si dispone di uno scenario avanzato e si vuole implementare una raccolta personalizzata, è consigliabile usare <xref:System.Collections.IList>, che fornisce una raccolta non generica di oggetti che è possibile accedere singolarmente tramite indice e garantisce prestazioni ottimali.  
  
<a name="collection_views"></a>   
### <a name="collection-views"></a>Visualizzazioni di raccolte  
 Una volta il <xref:System.Windows.Controls.ItemsControl> è associato a una raccolta di dati, è possibile ordinare, filtrare o raggruppare i dati. A tale scopo, si usano le visualizzazioni di raccolta, che sono classi che implementano il <xref:System.ComponentModel.ICollectionView> interfaccia.  
  
  
#### <a name="what-are-collection-views"></a>Definizione di visualizzazione di raccolta  
 Una visualizzazione di raccolta rappresenta il livello superiore di una raccolta di origine di binding che consente di esplorare e visualizzare la raccolta di origine in base a query di ordinamento, filtro e raggruppamento, il tutto senza modificare la raccolta di origine sottostante. Una visualizzazione di raccolta mantiene inoltre un puntatore all'elemento corrente nella raccolta. Se la raccolta di origine implementa il <xref:System.Collections.Specialized.INotifyCollectionChanged> dell'interfaccia, le modifiche generate dalla <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> evento vengono propagate alle visualizzazioni.  
  
 Poiché le visualizzazioni non modificano le raccolte di origine sottostanti, ogni raccolta di origine può avere più visualizzazioni associate. Si consideri ad esempio una raccolta di oggetti *Task*. Grazie alle visualizzazioni è possibile visualizzare gli stessi dati in modi diversi. È possibile ad esempio visualizzare le attività ordinate in base alla priorità nella parte sinistra della pagina e, contemporaneamente nella parte destra, visualizzare le stesse attività raggruppate in base all'area.  
  
<a name="how_to_create_a_view"></a>   
#### <a name="how-to-create-a-view"></a>Come creare una visualizzazione  
 Per creare e usare una visualizzazione, è possibile creare direttamente un'istanza dell'oggetto visualizzazione e usare tale istanza come origine del binding. Si consideri ad esempio l'applicazione [Demo di data binding](https://go.microsoft.com/fwlink/?LinkID=163703) mostrata nella sezione [Definizione di data binding](#what_is_data_binding). L'applicazione viene implementata in modo che il <xref:System.Windows.Controls.ListBox> associa direttamente a una visualizzazione della raccolta di dati anziché la raccolta dei dati. L'esempio seguente è stato estratto dall'applicazione [Demo di data binding](https://go.microsoft.com/fwlink/?LinkID=163703). Il <xref:System.Windows.Data.CollectionViewSource> classe è il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] proxy di una classe che eredita da <xref:System.Windows.Data.CollectionView>. In questo particolare esempio, il <xref:System.Windows.Data.CollectionViewSource.Source%2A> della visualizzazione è associata ai *AuctionItems* raccolta (di tipo <xref:System.Collections.ObjectModel.ObservableCollection%601>) dell'oggetto applicazione corrente.  
  
 [!code-xaml[DataBindingLab#WindowResources1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xaml[DataBindingLab#CollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xaml[DataBindingLab#WindowResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 La risorsa *listingDataView* viene quindi usato come origine del binding per gli elementi nell'applicazione, ad esempio il <xref:System.Windows.Controls.ListBox>:  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 Per creare un'altra visualizzazione per la stessa raccolta, è possibile creare un'altra <xref:System.Windows.Data.CollectionViewSource> dell'istanza e assegnargli un diverso `x:Key` nome.  
  
 La tabella seguente illustra i tipi di dati di visualizzazione vengono creati come visualizzazione raccolta predefinita o tramite <xref:System.Windows.Data.CollectionViewSource> in base al tipo di raccolta di origine.  
  
|Tipo di raccolta di origine|Tipo di visualizzazione di raccolta|Note|  
|----------------------------|--------------------------|-----------|  
|<xref:System.Collections.IEnumerable>|Un tipo interno basato sul <xref:System.Windows.Data.CollectionView>|Non è possibile raggruppare gli elementi.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|Il più veloce.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### <a name="using-a-default-view"></a>Utilizzo di una visualizzazione predefinita  
 Specificare una visualizzazione di raccolta come origine di binding rappresenta un modo per creare e usare una visualizzazione di raccolta. WPF crea inoltre una visualizzazione di raccolta predefinita per ogni raccolta usata come origine di binding. Se si esegue il binding direttamente a una raccolta, WPF esegue il binding alla relativa visualizzazione predefinita. Questa visualizzazione predefinita è condivisa da tutti i binding alla stessa raccolta, pertanto una modifica apportata a una visualizzazione predefinita da un controllo associato o dal codice, ad esempio l'ordinamento o una modifica al puntatore dell'elemento corrente illustrati più avanti, viene riflessa in tutti gli altri binding alla stessa raccolta.  
  
 Per ottenere la visualizzazione predefinita, si utilizza il <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> (metodo). Per un esempio, vedere [Procedura: ottenere la visualizzazione predefinita di una raccolta di dati](how-to-get-the-default-view-of-a-data-collection.md).  
  
##### <a name="collection-views-with-adonet-datatables"></a>Visualizzazioni di raccolta con ADO.NET DataTable  
 Per migliorare le prestazioni, le visualizzazioni di raccolta per ADO.NET <xref:System.Data.DataTable> oppure <xref:System.Data.DataView> oggetti delegano l'ordinamento e filtraggio del contenuto per il <xref:System.Data.DataView>. L'ordinamento e il filtro vengono in tal modo condivisi in tutte le visualizzazioni di raccolta dell'origine dati. Per consentire a ogni vista di raccolta ordinare e filtrare in modo indipendente, inizializzare ogni visualizzazione di raccolta con il proprio <xref:System.Data.DataView> oggetto.  
  
#### <a name="sorting"></a>Ordinamento  
 Come detto in precedenza, le visualizzazioni possono applicare un ordinamento a una raccolta. Poiché esistono nella raccolta sottostante, i dati possono avere o non avere un ordine intrinseco. La visualizzazione della raccolta consente di imporre un ordine o di modificare l'ordine predefinito in base ai criteri di confronto che si forniscono. Trattandosi di una visualizzazione dei dati basata su client, uno scenario comune prevede che l'utente possa ordinare le colonne di dati tabulari in base al valore al quale corrisponde la colonna. Grazie alle visualizzazioni, è possibile applicare questo ordinamento gestito dall'utente senza apportare alcuna modifica alla raccolta sottostante né dover ripetere la query nel contenuto della raccolta. Per un esempio, vedere [Procedura: Ordinare una colonna GridView quando si fa clic su un'intestazione](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  
  
 L'esempio seguente illustra la logica di ordinamento di "Sort by category and date" <xref:System.Windows.Controls.CheckBox> dell'applicazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nel [What ' s Data Binding?](#what_is_data_binding) sezione:  
  
 [!code-csharp[DataBindingLab#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
#### <a name="filtering"></a>Filtro  
 Le visualizzazioni possono anche applicare un filtro a una raccolta. In altre parole, anche se una raccolta può includere un elemento, questa specifica visualizzazione è progettata per visualizzare solo un determinato subset di una raccolta completa. I dati possono essere filtrati in base a una condizione. Ad esempio, come avviene per l'applicazione nel [What ' s Data Binding?](#what_is_data_binding) sezione, "Mostra solo bargains" <xref:System.Windows.Controls.CheckBox> contiene la logica per filtrare gli elementi con un costo di $25 o più. Viene eseguito il codice seguente per impostare *ShowOnlyBargainsFilter* come la <xref:System.Windows.Data.CollectionViewSource.Filter> gestore evento quando che <xref:System.Windows.Controls.CheckBox> è selezionato:  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 L'implementazione dell'evento *ShowOnlyBargainsFilter* è la seguente:  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 Se si usa uno dei <xref:System.Windows.Data.CollectionView> classi direttamente anziché <xref:System.Windows.Data.CollectionViewSource>, si utilizzerebbe il <xref:System.Windows.Data.CollectionView.Filter%2A> proprietà per specificare un callback. Per un esempio, vedere [Procedura: Filtrare i dati in una visualizzazione](how-to-filter-data-in-a-view.md).  
  
#### <a name="grouping"></a>Raggruppamento  
 Fatta eccezione per la classe interna che visualizza un <xref:System.Collections.IEnumerable> raccolta, tutte le visualizzazioni di raccolta supportano la funzionalità di raggruppamento, che consente all'utente di suddividere la raccolta nella visualizzazione dell'insieme in gruppi logici. Se l'utente fornisce un elenco di gruppi, questi saranno espliciti. Se invece i gruppi vengono generati in modo dinamico in base ai dati, si avranno gruppi impliciti.  
  
 L'esempio seguente illustra la logica di "Group by category" <xref:System.Windows.Controls.CheckBox>:  
  
 [!code-csharp[DataBindingLab#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#6)]
 [!code-vb[DataBindingLab#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#6)]  
  
 Per un altro esempio di raggruppamento, vedere [Procedura: Raggruppare gli elementi di un controllo ListView che implementa una GridView](../controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md).  
  
#### <a name="current-item-pointers"></a>Puntatori dell'elemento corrente  
 Le visualizzazioni supportano anche la nozione di elemento corrente. In una visualizzazione di raccolta è possibile spostarsi da un oggetto all'altro. Durante lo spostamento viene spostato un puntatore dell'elemento che consente di recuperare l'oggetto presente in un percorso specifico nella raccolta. Per un esempio, vedere [Procedura: Navigare tra gli oggetti nella visualizzazione di una raccolta dati](how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
 Poiché WPF esegue il binding a una raccolta solo tramite una visualizzazione, che può essere sia una visualizzazione specificata dall'utente che la visualizzazione predefinita della raccolta, tutti i binding alle raccolte contengono un puntatore dell'elemento corrente. Quando si esegue il binding a una visualizzazione, il carattere barra ("/") in un valore di `Path` definisce l'elemento corrente della visualizzazione. Nell'esempio seguente il contesto di dati è una visualizzazione di raccolta. La prima riga viene associata alla raccolta. La seconda riga viene associata all'elemento corrente della raccolta. La terza riga viene associata alla proprietà `Description` dell'elemento corrente nella raccolta.  
  
```xaml  
<Button Content="{Binding }" />  
<Button Content="{Binding Path=/}" />  
<Button Content="{Binding Path=/Description}" />   
```  
  
 La barra e la sintassi della proprietà possono inoltre essere sovrapposte per attraversare una gerarchia di raccolte. Nell'esempio seguente viene eseguito il binding all'elemento corrente di una raccolta denominata `Offices`, che è una proprietà dell'elemento corrente della raccolta di origine.  
  
```xaml  
<Button Content="{Binding /Offices/}" />  
```  
  
 Il puntatore dell'elemento corrente può essere influenzato da un'operazione di ordinamento o filtro applicata alla raccolta. L'ordinamento mantiene il puntatore dell'elemento corrente sull'ultimo elemento selezionato, ma la visualizzazione di raccolta viene ristrutturata in base a tale elemento. Se in precedenza l'elemento selezionato si trovava all'inizio dell'elenco, ora è possibile che si trovi in posizione centrale. Il filtro mantiene l'elemento selezionato se la selezione rimane nella visualizzazione dopo l'applicazione del filtro. Il puntatore dell'elemento corrente viene altrimenti impostato sul primo elemento della visualizzazione di raccolta filtrata.  
  
<a name="master_detail_scenario"></a>   
#### <a name="master-detail-binding-scenario"></a>Scenario di binding master-dettagli  
 La nozione di elemento corrente è utile non solo per l'esplorazione degli elementi in una raccolta, bensì anche per lo scenario di binding master-dettagli. Si consideri nuovamente l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione presentata nella sezione [Definizione di data binding](#what_is_data_binding). In tale applicazione, la selezione all'interno di <xref:System.Windows.Controls.ListBox> determina il contenuto visualizzato nel <xref:System.Windows.Controls.ContentControl>. Inserirlo in un altro modo, quando un <xref:System.Windows.Controls.ListBox> elemento è selezionato, il <xref:System.Windows.Controls.ContentControl> Mostra i dettagli dell'elemento selezionato.  
  
 Per implementare lo scenario master-dettagli, occorre semplicemente avere due o più controlli associati alla stessa visualizzazione. Nell'esempio seguente il [Demo di Data Binding](https://go.microsoft.com/fwlink/?LinkID=163703) viene illustrato il markup delle <xref:System.Windows.Controls.ListBox> e il <xref:System.Windows.Controls.ContentControl> viene visualizzato nell'applicazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nel [What ' s Data Binding?](#what_is_data_binding) sezione:  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xaml[DataBindingLab#Detail](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 Si noti che entrambi i controlli sono associati alla stessa origine, vale a dire la risorsa statica *listingDataView*. Vedere a tale proposito la definizione di questa risorsa nella sezione [Come creare una visualizzazione](#how_to_create_a_view). Questo procedimento funziona perché quando un oggetto singleton (il <xref:System.Windows.Controls.ContentControl> in questo caso) è associato a una vista di raccolta, viene automaticamente associato ai <xref:System.Windows.Data.CollectionView.CurrentItem%2A> della visualizzazione. Si noti che <xref:System.Windows.Data.CollectionViewSource> oggetti sincronizzano automaticamente valuta e selezione. Se l'elenco non è associato a un <xref:System.Windows.Data.CollectionViewSource> dell'oggetto come in questo esempio, è necessario impostare relativi <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà `true` per il corretto funzionamento.  
  
 Per altri esempi, vedere [Procedura: Eseguire il binding di una raccolta e visualizzare informazioni in base alla selezione effettuata](how-to-bind-to-a-collection-and-display-information-based-on-selection.md) e [Procedura: Utilizzare il modello master-dettagli con dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Come si può notare, l'esempio precedente usa un modello. In effetti, i dati potrebbero non essere visualizzati come desiderato senza l'uso dei modelli (quello usato in modo esplicito dal <xref:System.Windows.Controls.ContentControl> e quella usata in modo implicito dal <xref:System.Windows.Controls.ListBox>). Le sezione seguente illustra i modelli di dati.  
  
<a name="data_templating"></a>   
## <a name="data-templating"></a>Modelli di dati  
 Senza l'utilizzo di modelli di dati, l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione illustrata nella sezione [Definizione di data binding](#what_is_data_binding) avrebbe un aspetto simile al seguente:  
  
 ![Demo di data binding senza modelli di dati](./media/databindingdemotemplates.png "DataBindingDemoTemplates")  
  
 Come illustrato nell'esempio nella sezione precedente, sia la <xref:System.Windows.Controls.ListBox> controllo e il <xref:System.Windows.Controls.ContentControl> associati all'intero oggetto collection (o più in particolare, la visualizzazione sull'oggetto collection) di *AuctionItem*s. Senza istruzioni specifiche visualizzare la raccolta dei dati, il <xref:System.Windows.Controls.ListBox> Visualizza una rappresentazione di stringa di ogni oggetto nella raccolta sottostante e <xref:System.Windows.Controls.ContentControl> Visualizza una rappresentazione di stringa dell'oggetto è associato a.  
  
 Per risolvere il problema, l'applicazione definisce <xref:System.Windows.DataTemplate>s. Come illustrato nell'esempio nella sezione precedente, il <xref:System.Windows.Controls.ContentControl> utilizza in modo esplicito il *detailsProductListingTemplate*<xref:System.Windows.DataTemplate>. Il <xref:System.Windows.Controls.ListBox> controllo utilizza in modo implicito le seguenti <xref:System.Windows.DataTemplate> quando si visualizzano le *AuctionItem* oggetti nella raccolta:  
  
 [!code-xaml[DataBindingLab#AuctionItemDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 Grazie all'uso di questi due <xref:System.Windows.DataTemplate>s, l'interfaccia utente risultante è quella illustrata nella [What ' s Data Binding?](#what_is_data_binding) sezione. Come può notare dallo screenshot, oltre a consentendo agli sviluppatori di inserimento di dati all'interno dei controlli, <xref:System.Windows.DataTemplate>s consentono di definire gli oggetti visivi accattivanti per i dati. Ad esempio, <xref:System.Windows.DataTrigger>vengono usati nell'esempio precedente <xref:System.Windows.DataTemplate> in modo che *AuctionItem*s con *SpecialFeatures* pari *evidenziare* verrebbe visualizzato con un bordo arancione e una stella.  
  
 Per altre informazioni sui modelli di dati, vedere [Cenni preliminari sui modelli di dati](data-templating-overview.md).  
  
<a name="data_validation"></a>   
## <a name="data-validation"></a>Convalida dei dati  
  
 La maggior parte delle applicazioni che accettano input dell'utente deve avere una logica di convalida per garantire che l'utente immetta le informazioni previste. I controlli di convalida possono basarsi sul tipo, l'intervallo, il formato o altri requisiti specifici dell'applicazione. Questa sezione illustra il funzionamento della convalida dei dati in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="associating-validation-rules-with-a-binding"></a>Associazione di regole di convalida a un binding  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modello di data binding, è possibile associare <xref:System.Windows.Data.Binding.ValidationRules%2A> con il <xref:System.Windows.Data.Binding> oggetto. Ad esempio, l'esempio seguente associa un <xref:System.Windows.Controls.TextBox> a una proprietà denominata `StartPrice` e aggiunge un <xref:System.Windows.Controls.ExceptionValidationRule> dell'oggetto per il <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> proprietà.  
  
 [!code-xaml[DataBindingLab#DefaultValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 Oggetto <xref:System.Windows.Controls.ValidationRule> oggetto controlla se il valore di una proprietà è valido. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contiene i due tipi seguenti incorporati <xref:System.Windows.Controls.ValidationRule> oggetti:  
  
-   Oggetto <xref:System.Windows.Controls.ExceptionValidationRule> controlla le eccezioni generate durante l'aggiornamento della proprietà di origine del binding. Nell'esempio precedente `StartPrice` è di tipo intero. Quando l'utente immette un valore che non può essere convertito in un intero, viene generata un'eccezione e il binding viene contrassegnato come non valido. Una sintassi alternativa all'impostazione il <xref:System.Windows.Controls.ExceptionValidationRule> in modo esplicito consiste nell'impostare il <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> proprietà `true` sul <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.MultiBinding> oggetto.  
  
-   Oggetto <xref:System.Windows.Controls.DataErrorValidationRule> verifica la presenza di errori generati dagli oggetti che implementano il <xref:System.ComponentModel.IDataErrorInfo> interfaccia. Per un esempio dell'uso di questa regola di convalida, vedere <xref:System.Windows.Controls.DataErrorValidationRule>. Una sintassi alternativa all'impostazione il <xref:System.Windows.Controls.DataErrorValidationRule> in modo esplicito consiste nell'impostare il <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> proprietà `true` sul <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.MultiBinding> oggetto.  
  
 È anche possibile creare la regola di convalida derivando dal <xref:System.Windows.Controls.ValidationRule> classe e l'implementazione di <xref:System.Windows.Controls.ValidationRule.Validate%2A> (metodo). L'esempio seguente mostra la regola usata dal *Add Product Listing* "Start Date" <xref:System.Windows.Controls.TextBox> dal [What ' s Data Binding?](#what_is_data_binding) sezione:  
  
 [!code-csharp[DataBindingLab#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 Il *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> utilizza questo *FutureDateRule*, come illustrato nell'esempio seguente:  
  
 [!code-xaml[DataBindingLab#CustomValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 Si noti che poiché il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore è <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, il motore di binding aggiorna il valore di origine a ogni pressione di tasto, il che significa che anche controlli di ogni regola nella <xref:System.Windows.Data.Binding.ValidationRules%2A> insieme a ogni pressione di tasto. L'argomento verrà ulteriormente trattato nella sezione Processo di convalida.  
  
<a name="invalidation_feedback"></a>   
### <a name="providing-visual-feedback"></a>Visualizzazione di un feedback  
 Se l'utente immette un valore non valido, è possibile fornire un feedback relativo all'errore nell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione. Un modo per fornire tale feedback consiste nell'impostare il <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> proprietà associata a un oggetto personalizzato <xref:System.Windows.Controls.ControlTemplate>. Come illustrato nella sottosezione precedente, il *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> utilizza una <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> chiamato *validationTemplate*. L'esempio seguente illustra la definizione di *validationTemplate*:  
  
 [!code-xaml[DataBindingLab#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 Il <xref:System.Windows.Controls.AdornedElementPlaceholder> elemento specifica dove deve essere posizionato il controllo decorato.  
  
 Inoltre, è anche possibile usare un <xref:System.Windows.Controls.ToolTip> per visualizzare il messaggio di errore. Entrambi i *StartDateEntryForm* e il *StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>usano lo stile *textStyleTextBox*, che consente di creare un <xref:System.Windows.Controls.ToolTip> che Visualizza il messaggio di errore. L'esempio seguente illustra la definizione di *textStyleTextBox*. La proprietà associata <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> è `true` quando uno o più binding nelle proprietà dell'elemento associato sono in errore.  
  
 [!code-xaml[DataBindingLab#14](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 Con l'oggetto personalizzato <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> e il <xref:System.Windows.Controls.ToolTip>, il *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> simile al seguente quando si verifica un errore di convalida:  
  
 ![Errore di convalida di data binding](./media/databindingdemo-validation.PNG "DataBindingDemo_Validation")  
  
 Se il <xref:System.Windows.Data.Binding> dispone di regole di convalida associate ma non si specifica un' <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> nel controllo associato, predefinito <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> verrà usato per inviare notifiche agli utenti quando si verifica un errore di convalida. Il valore predefinito <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> è un modello di controllo che definisce un bordo rosso nel livello dello strumento decorativo visuale. Con il valore predefinito <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> e il <xref:System.Windows.Controls.ToolTip>, il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] del *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> simile al seguente quando si verifica un errore di convalida:  
  
 ![Errore di convalida di data binding](./media/databindingdemo-validationdefault.PNG "DataBindingDemo_ValidationDefault")  
  
 Per un esempio di come fornire una logica di convalida per tutti i controlli in una finestra di dialogo, vedere la sezione Finestre di dialogo personalizzate contenuta in [Cenni preliminari sulle finestre di dialogo](../app-development/dialog-boxes-overview.md).  
  
### <a name="validation-process"></a>Processo di convalida  
 La convalida avviene solitamente quando si trasferisce un valore di destinazione alla proprietà di origine del binding. Ciò si verifica sul <xref:System.Windows.Data.BindingMode.TwoWay> e <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni. Come già detto, ciò che fa sì che un aggiornamento dell'origine dipende dal valore della <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà, come descritto nel [quali trigger origine aggiornamenti](#what_triggers_source_updates) sezione.  
  
 Viene di seguito descritto il processo di *convalida*. Si noti che se in qualsiasi momento durante questo processo si verifica un errore di convalida o un altro tipo di errore, il processo viene interrotto.  
  
1.  Il motore di binding controlla se esistono eventuali custom <xref:System.Windows.Controls.ValidationRule> definiti oggetti la cui proprietà <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> è impostata su <xref:System.Windows.Controls.ValidationStep.RawProposedValue> tale <xref:System.Windows.Data.Binding>, nel qual caso chiama il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo su ogni <xref:System.Windows.Controls.ValidationRule> fino a quando non uno di essi viene rilevato un errore o fino a quando tutti gli elementi passare.  
  
2.  Il motore di binding chiama quindi il convertitore, se presente.  
  
3.  Se il convertitore riesce, il motore di binding controlla se esistono eventuali personalizzato <xref:System.Windows.Controls.ValidationRule> definiti oggetti la cui proprietà <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> è impostata su <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> tale <xref:System.Windows.Data.Binding>, nel qual caso chiama il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo su ogni <xref:System.Windows.Controls.ValidationRule> con <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostato su <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> fino a quando non uno di essi viene rilevato un errore o fino a quando tutti gli elementi passare.  
  
4.  Il motore di binding imposta la proprietà di origine.  
  
5.  Il motore di binding controlla se esistono eventuali personalizzato <xref:System.Windows.Controls.ValidationRule> definiti oggetti la cui proprietà <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> è impostata su <xref:System.Windows.Controls.ValidationStep.UpdatedValue> tale <xref:System.Windows.Data.Binding>, nel qual caso chiama il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo su ogni <xref:System.Windows.Controls.ValidationRule> con <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostata su <xref:System.Windows.Controls.ValidationStep.UpdatedValue> fino a quando non uno di essi viene rilevato un errore o fino a quando tutti gli elementi passare. Se un <xref:System.Windows.Controls.DataErrorValidationRule> associata a un'associazione e la relativa <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> è impostata sul valore predefinito, <xref:System.Windows.Controls.ValidationStep.UpdatedValue>, il <xref:System.Windows.Controls.DataErrorValidationRule> viene controllato a questo punto. Questo è anche il punto quando le associazioni che hanno le <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> impostato su `true` vengono controllati.  
  
6.  Il motore di binding controlla se esistono eventuali personalizzato <xref:System.Windows.Controls.ValidationRule> definiti oggetti la cui proprietà <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> è impostata su <xref:System.Windows.Controls.ValidationStep.CommittedValue> tale <xref:System.Windows.Data.Binding>, nel qual caso chiama il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo su ogni <xref:System.Windows.Controls.ValidationRule> con <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostata su <xref:System.Windows.Controls.ValidationStep.CommittedValue> fino a quando non uno di essi viene rilevato un errore o fino a quando tutti gli elementi passare.  
  
 Se un <xref:System.Windows.Controls.ValidationRule> non supera in qualsiasi momento durante questo processo, il motore di binding crea un <xref:System.Windows.Controls.ValidationError> dell'oggetto e lo aggiunge al <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> raccolta dell'elemento associato. Viene eseguito prima dell'associazione motore il <xref:System.Windows.Controls.ValidationRule> oggetti in un determinato passaggio, consente di rimuovere qualsiasi <xref:System.Windows.Controls.ValidationError> che è stato aggiunto al <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> collegato proprietà dell'elemento associato durante quel passaggio. Ad esempio, se un <xref:System.Windows.Controls.ValidationRule> cui <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> è impostata su <xref:System.Windows.Controls.ValidationStep.UpdatedValue> non è riuscita, la volta successiva che si verifica il processo di convalida, il motore di binding rimuove l'oggetto <xref:System.Windows.Controls.ValidationError> immediatamente prima di chiamare <xref:System.Windows.Controls.ValidationRule> dotato <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostato su <xref:System.Windows.Controls.ValidationStep.UpdatedValue>.  
  
 Quando <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> non è vuota, il <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> collegati proprietà dell'elemento è impostata su `true`. Inoltre, se il <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> proprietà del <xref:System.Windows.Data.Binding> è impostata su `true`, quindi il motore di binding genera il <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> evento sull'elemento associato.  
  
 Si noti inoltre che un trasferimento di un valore valido in entrambe le direzioni (dalla destinazione all'origine o destinazione) Cancella il <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> proprietà associata.  
  
 Se il binding è un' <xref:System.Windows.Controls.ExceptionValidationRule> associata o se il <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> è impostata su `true` e viene generata un'eccezione quando il motore di binding imposta l'origine, il motore di binding controlla se è presente un <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>. È possibile usare il <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> callback per fornire un gestore personalizzato per la gestione delle eccezioni. Se un' <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> non viene specificato nella <xref:System.Windows.Data.Binding>, il motore di binding crea un <xref:System.Windows.Controls.ValidationError> con l'eccezione e lo aggiunge al <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> raccolta dell'elemento associato.  
  
## <a name="debugging-mechanism"></a>Meccanismo di debug  
 È possibile impostare la proprietà associata <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> su un oggetto correlato all'associazione per ricevere informazioni sullo stato di uno specifico binding.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Novità di WPF versione 4.5](../getting-started/whats-new.md)
- [Eseguire l'associazione dei risultati di una query LINQ](how-to-bind-to-the-results-of-a-linq-query.md)
- [Data binding](../advanced/optimizing-performance-data-binding.md)
- [Demo di Data Binding](https://go.microsoft.com/fwlink/?LinkID=163703)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
- [Procedura: Eseguire l'associazione a un'origine dati ADO.NET](how-to-bind-to-an-ado-net-data-source.md)
