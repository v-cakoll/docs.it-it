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
ms.openlocfilehash: e1fbb46c76fbc729818b6ff24b55c0d18f6b05df
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400704"
---
# <a name="data-binding-overview"></a>Panoramica sul data binding
Il data binding di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] rappresenta per le applicazioni un modo semplice e coerente di presentare i dati e interagire con essi. Gli elementi possono essere associati a dati da un'ampia gamma di origini dati sotto forma di oggetti Common Language Runtime (CLR) [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]e. <xref:System.Windows.Controls.ContentControl>, ad esempio <xref:System.Windows.Controls.Button> e <xref:System.Windows.Controls.ItemsControl> <xref:System.Windows.Controls.ListView> , come e hanno una funzionalità incorporata per consentire lo stile flessibile di singoli elementi di dati o raccolte di elementi di dati. <xref:System.Windows.Controls.ListBox> In cima ai dati è possibile generare visualizzazioni di ordinamento, filtro e raggruppamento.  
  
 La funzionalità di data binding in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presenta molti vantaggi rispetto ai modelli tradizionali, tra cui un'ampia gamma di proprietà che supportano implicitamente il data binding, una rappresentazione dei dati mediante [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] flessibile e una netta separazione tra logica di business e [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 In questo argomento vengono illustrati in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] primo luogo i concetti fondamentali per data binding e quindi <xref:System.Windows.Data.Binding> viene illustrato l'utilizzo della classe e di altre funzionalità di data binding.  

<a name="what_is_data_binding"></a>   
## <a name="what-is-data-binding"></a>Definizione di data binding  
 Il data binding è il processo tramite cui viene stabilita una connessione tra l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione e la logica di business. Se le impostazioni del binding sono corrette e i dati forniscono le notifiche appropriate, quando il valore dei dati viene modificato, gli elementi a essi associati riflettono automaticamente le modifiche apportate. Il data binding prevede anche che, se una rappresentazione esterna dei dati in un elemento viene modificata, i dati sottostanti possono essere automaticamente aggiornati in modo da riflettere la modifica. Se, ad esempio, l'utente modifica il valore in un <xref:System.Windows.Controls.TextBox> elemento, il valore dei dati sottostanti verrà aggiornato automaticamente per riflettere la modifica.  
  
 Un utilizzo tipico del data binding consiste nell'inserimento di dati di configurazione locale o del server in moduli o in altri controlli [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] questo concetto viene esteso per includere il binding di un'ampia gamma di proprietà a varie origini dati. In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le proprietà di dipendenza degli elementi possono essere associate a oggetti CLR, inclusi oggetti ADO.NET o oggetti associati a servizi Web e proprietà Web, [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] e ai dati.  
  
 Per un esempio di data binding, osservare l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione seguente disponibile in [Demo di data binding](https://go.microsoft.com/fwlink/?LinkID=163703):  
  
 ![Schermata di esempio di data binding](./media/databinding-databindingdemo.png "DataBinding_DataBindingDemo")  
  
 La figura precedente mostra l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] di un'applicazione che visualizza un elenco di articoli da vendere all'asta. L'applicazione mostra le funzionalità di data binding seguenti:  
  
- Il contenuto di <xref:System.Windows.Controls.ListBox> è associato a una raccolta di oggetti *AuctionItem* . Un oggetto *AuctionItem* dispone di diverse proprietà, tra cui *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures* e così via.  
  
- I dati (oggetti*AuctionItem* ) visualizzati in <xref:System.Windows.Controls.ListBox> sono basati su modelli in modo da visualizzare la descrizione e il prezzo corrente per ogni elemento. Questa operazione viene eseguita tramite <xref:System.Windows.DataTemplate>un oggetto. L'aspetto di ogni articolo dipende inoltre dal valore di *SpecialFeatures* dell'oggetto *AuctionItem* visualizzato. Se il valore di *SpecialFeatures* dell'oggetto *AuctionItem* è *Color*, l'articolo avrà un bordo blu. Se il valore è *Highlight*, l'articolo sarà dotato di un bordo arancione e di una stella. La sezione [Modelli di dati](#data_templating) include informazioni sull'applicazione di modelli ai dati.  
  
- L'utente può raggruppare, filtrare o ordinare i dati usando gli <xref:System.Windows.Controls.CheckBox>es forniti. Nell'immagine precedente sono selezionate le caselle "Raggruppa per categoria" e "Ordina per categoria e data <xref:System.Windows.Controls.CheckBox>". I dati sono raggruppati in base alla categoria del prodotto e i nomi delle categorie seguono l'ordine alfabetico. Benché non risulti evidente dalla figura, gli articoli sono anche ordinati in base alla data di inizio all'interno di ogni categoria. Questa operazione viene eseguita usando una *visualizzazione di raccolta*. La sezione [Binding alle raccolte](#binding_to_collections) descrive le visualizzazioni di raccolta.  
  
- Quando l'utente seleziona un elemento, <xref:System.Windows.Controls.ContentControl> Visualizza i dettagli dell'elemento selezionato. Si parla in questo caso di *scenario master-dettagli*. La sezione [Scenario master-dettagli](#master_detail_scenario) include informazioni su questo tipo di scenario di binding.  
  
- Il tipo della proprietà *StartDate* è <xref:System.DateTime>, che restituisce una data che include l'ora del millisecondo. In questa applicazione è stato usato un convertitore personalizzato per visualizzare una stringa di data più breve. La sezione [Conversione dei dati](#data_conversion) include informazioni sui convertitori.  
  
 Quando l'utente fa clic sul pulsante *Add Product* (Aggiungi prodotto), viene visualizzato il modulo seguente:  
  
 ![Pagina Add Product Listing](./media/databinding-demo-addproductlisting.png "DataBinding_Demo_AddProductListing")  
  
 L'utente può modificare i campi del modulo, visualizzare in anteprima il prodotto usando i riquadri di anteprima rapida e di anteprima più dettagliata e quindi fare clic su *Submit* (Inoltra) per aggiungere il nuovo prodotto. Le funzionalità di raggruppamento, filtro e ordinamento esistenti verranno applicate alla nuova voce. In questo caso specifico, l'articolo immesso nella figura precedente verrà visualizzato come secondo articolo della categoria *Computer*.  
  
 Non mostrata in questa immagine è la logica di convalida fornita nella *Data* <xref:System.Windows.Controls.TextBox>di inizio. Se l'utente immette una data non valida (formattazione non valida o data precedente), l'utente riceverà una notifica <xref:System.Windows.Controls.ToolTip> con un e un punto esclamativo rosso <xref:System.Windows.Controls.TextBox>accanto a. La sezione [Convalida dei dati](#data_validation) descrive come creare la logica di convalida.  
  
 Prima di approfondire le diverse funzionalità di data binding delineate finora, verranno trattati nella sezione successiva i concetti fondamentali necessari a comprendere il data binding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## <a name="basic-data-binding-concepts"></a>Concetti di base sul data binding  
  
 Indipendentemente dall'elemento che si intende associare e dalla natura dell'origine dati, ogni binding si basa sempre sul modello illustrato nella figura seguente:  
  
 ![Diagramma che mostra il modello di data binding di base.](./media/data-binding-overview/basic-data-binding-diagram.png)  
  
 Come illustrato nella figura precedente, il data binding funge essenzialmente da ponte tra la destinazione e l'origine del binding. La figura illustra i concetti fondamentali seguenti relativi al data binding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
- Ogni binding possiede in genere quattro componenti: un oggetto di destinazione del binding, una proprietà di destinazione, un'origine del binding e un percorso al valore nell'origine del binding da usare. Se ad esempio si vuole associare il contenuto di <xref:System.Windows.Controls.TextBox> un oggetto alla proprietà *Name* di un oggetto *Employee* <xref:System.Windows.Controls.TextBox>, l'oggetto di destinazione è, la proprietà di destinazione è la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà, il valore da usare è *Name*e il valore di l'oggetto di origine è l'oggetto *dipendente* .  
  
- La proprietà di destinazione deve essere una proprietà di dipendenza. La <xref:System.Windows.UIElement> maggior parte delle proprietà sono proprietà di dipendenza e la maggior parte delle proprietà di dipendenza, tranne quelle di sola lettura, supportano data binding per impostazione predefinita. (Solo <xref:System.Windows.DependencyObject> i tipi possono definire le proprietà di <xref:System.Windows.UIElement>dipendenza e tutti i <xref:System.Windows.DependencyObject>derivati da).  
  
- Sebbene non sia specificato nella figura, è opportuno notare che l'oggetto di origine del binding non è limitato a essere un oggetto CLR personalizzato. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]data binding supporta i dati sotto forma di oggetti CLR e [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Per fornire alcuni esempi, l'origine del binding può essere <xref:System.Windows.UIElement>un, qualsiasi oggetto elenco, un oggetto CLR associato a dati ADO.NET o servizi Web o un XmlNode che contiene i [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati. Per altre informazioni, vedere [Cenni preliminari sulle origini del binding](binding-sources-overview.md).  
  
 Come detto in altri argomenti concernenti [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)], è importante ricordare che quando si stabilisce un binding, si associa una destinazione del binding *a* un'origine del binding. Se, ad esempio, si visualizzano alcuni [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati sottostanti <xref:System.Windows.Controls.ListBox> in un oggetto utilizzando Data Binding <xref:System.Windows.Controls.ListBox> , si associa ai [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati.  
  
 Per stabilire un'associazione, utilizzare l' <xref:System.Windows.Data.Binding> oggetto. Nella parte restante di questo argomento vengono illustrati molti dei concetti associati a e alcune delle proprietà e l' <xref:System.Windows.Data.Binding> utilizzo dell'oggetto.  
  
<a name="direction_of_data_flow"></a>   
### <a name="direction-of-the-data-flow"></a>Direzione del flusso di dati  
 Come accennato in precedenza e come indicato dalla freccia nella figura precedente, il flusso di dati di un'associazione può passare dalla destinazione del binding all'origine del binding (ad esempio, il valore di origine cambia quando un utente modifica il valore di a <xref:System.Windows.Controls.TextBox>) e/o dall'origine dell'associazione alla destinazione del binding (ad esempio, il <xref:System.Windows.Controls.TextBox> contenuto viene aggiornato con le modifiche nell'origine del binding) se l'origine di associazione fornisce le notifiche appropriate.  
  
 È possibile fare in modo che l'applicazione consenta agli utenti di modificare i dati e di propagarli all'oggetto di origine oppure è possibile fare in modo che gli utenti non possano aggiornare i dati di origine. È possibile controllare questa impostazione impostando <xref:System.Windows.Data.Binding.Mode%2A> la proprietà <xref:System.Windows.Data.Binding> dell'oggetto. La figura seguente illustra i diversi tipi di flusso di dati:  
  
 ![Flusso di dati nel data binding](./media/databinding-dataflow.png "DataBinding_DataFlow")  
  
- <xref:System.Windows.Data.BindingMode.OneWay>l'associazione determina l'aggiornamento automatico della proprietà di destinazione delle modifiche apportate alla proprietà di origine, ma le modifiche apportate alla proprietà di destinazione non vengono propagate alla proprietà di origine. Questo tipo di binding è appropriato se il controllo da associare è implicitamente di sola lettura. Può accadere ad esempio che si effettui un binding a un'origine quale un controllo Stock Ticker oppure che la proprietà di destinazione non possieda un'interfaccia di controllo tramite la quale apportare modifiche, come nel caso di un colore di sfondo con binding a dati di una tabella. Se non è necessario monitorare le modifiche delle proprietà di destinazione, l'uso della modalità di associazione <xref:System.Windows.Data.BindingMode.OneWay> consente di evitare il sovraccarico della modalità di binding <xref:System.Windows.Data.BindingMode.TwoWay>.  
  
- <xref:System.Windows.Data.BindingMode.TwoWay>l'associazione causa modifiche alla proprietà di origine o alla proprietà di destinazione per aggiornare automaticamente l'altra. Questo tipo di binding è adatto a moduli modificabili o ad altri scenari [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] completamente interattivi. <xref:System.Windows.Data.BindingMode.OneWay> Per impostazione predefinita, la maggior parte delle proprietà è vincolante, ma alcune proprietà di dipendenza, in genere proprietà di <xref:System.Windows.Controls.TextBox> controlli modificabili dall'utente, ad esempio la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà di e la <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> proprietà di <xref:System.Windows.Controls.CheckBox>, per impostazionepredefinitasono<xref:System.Windows.Data.BindingMode.TwoWay> associazione. Un modo programmatico per determinare se l'associazione di una proprietà di dipendenza è unidirezionale o bidirezionale per impostazione predefinita, consiste nell'ottenere i metadati della proprietà con <xref:System.Windows.DependencyProperty.GetMetadata%2A> e quindi controllare il valore booleano della proprietà <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource>è il contrario dell' <xref:System.Windows.Data.BindingMode.OneWay> associazione; aggiorna la proprietà di origine quando viene modificata la proprietà di destinazione. Può essere usata, ad esempio, nel caso in cui si debba semplicemente rivalutare il valore di origine dall'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
- Non illustrato nella figura è <xref:System.Windows.Data.BindingMode.OneTime> l'associazione, che fa in modo che la proprietà di origine Inizializza la proprietà di destinazione, ma le modifiche successive non vengono propagate. Ciò significa che se il contesto dati subisce una modifica o l'oggetto nel contesto dati viene modificato, la modifica non si riflette nella proprietà di destinazione. Questo tipo di binding è appropriato per dati in cui è opportuno usare uno snapshot dello stato corrente o che sono realmente statici. Questo tipo di binding è utile anche se si vuole inizializzare la proprietà di destinazione con un valore ricavato da una proprietà di origine e il contesto dei dati non è noto in anticipo. Si tratta essenzialmente di una forma più semplice di binding <xref:System.Windows.Data.BindingMode.OneWay> che offre prestazioni migliori nei casi in cui il valore di origine non cambia.  
  
 Si noti che per rilevare le modifiche dell'origine <xref:System.Windows.Data.BindingMode.OneWay> ( <xref:System.Windows.Data.BindingMode.TwoWay> applicabili alle associazioni e), l'origine deve implementare un meccanismo di notifica delle <xref:System.ComponentModel.INotifyPropertyChanged>modifiche di proprietà appropriato, ad esempio. Per [](how-to-implement-property-change-notification.md) un esempio di <xref:System.ComponentModel.INotifyPropertyChanged> implementazione, vedere implementare una notifica di modifica delle proprietà.  
  
 Nella <xref:System.Windows.Data.Binding.Mode%2A> pagina delle proprietà sono disponibili ulteriori informazioni sulle modalità di associazione e un esempio di come specificare la direzione di un'associazione.  
  
<a name="what_triggers_source_updates"></a>   
### <a name="what-triggers-source-updates"></a>Eventi che generano gli aggiornamenti dell'origine  
 Binding che sono <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> restano in ascolto delle modifiche nella proprietà di destinazione e li propagano all'origine. Questo processo è noto come aggiornamento dell'origine. Può accadere ad esempio che si modifichi il testo di un oggetto TextBox per modificare il valore di origine sottostante. Come descritto nella sezione precedente, la direzione del flusso di dati è determinata dal valore della <xref:System.Windows.Data.Binding.Mode%2A> proprietà dell'associazione.  
  
 Il valore di origine viene aggiornato durante la modifica del testo o dopo aver apportato le modifiche del testo e aver spostato il mouse da TextBox? La <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà dell'associazione determina l'attivazione dell'aggiornamento dell'origine. I punti delle frecce a destra nella figura seguente illustrano il ruolo della <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà:  
  
 ![Diagramma che mostra il ruolo della proprietà UpdateSourceTrigger.](./media/data-binding-overview/data-binding-updatesource-trigger.png)  
  
 Se il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore è <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, il valore a cui punta la freccia destra di <xref:System.Windows.Data.BindingMode.TwoWay> o i <xref:System.Windows.Data.BindingMode.OneWayToSource> binding vengono aggiornati non appena viene modificata la proprietà di destinazione. Tuttavia, se il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore è <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>, il valore viene aggiornato solo con il nuovo valore quando la proprietà di destinazione perde lo stato attivo.  
  
 Analogamente alla <xref:System.Windows.Data.Binding.Mode%2A> proprietà, diverse proprietà di dipendenza hanno valori <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> predefiniti diversi. Il valore predefinito per la maggior parte delle proprietà di dipendenza è <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, mentre la proprietà <xref:System.Windows.Controls.TextBox.Text%2A> ha il valore predefinito <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Questo significa che gli aggiornamenti di origine vengono in genere eseguiti ogni volta che la proprietà di <xref:System.Windows.Controls.CheckBox>destinazione viene modificata, che è ottimale per es e altri controlli semplici. Nel caso dei campi di testo, tuttavia, l'esecuzione di un aggiornamento a ogni pressione di tasto può comportare un calo di prestazioni nonché negare all'utente la possibilità di tornare indietro e correggere eventuali errori di digitazione prima di confermare il nuovo valore. Per questo motivo <xref:System.Windows.Controls.TextBox.Text%2A> <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, il <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> valore predefinito della proprietà è anziché.  
  
 Per informazioni <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> su come trovare il valore predefinito <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> di una proprietà di dipendenza, vedere la pagina delle proprietà.  
  
 Nella tabella seguente viene fornito uno scenario di esempio <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> per ogni valore <xref:System.Windows.Controls.TextBox> utilizzando come esempio:  
  
|Valore di UpdateSourceTrigger|Quando il valore di origine viene aggiornato|Scenario di esempio per TextBox|  
|-------------------------------|----------------------------------------|----------------------------------|  
|LostFocus (impostazione predefinita <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>per)|Quando il controllo TextBox perde lo stato attivo|Oggetto <xref:System.Windows.Controls.TextBox> associato alla logica di convalida. vedere la sezione relativa alla convalida dei dati|  
|PropertyChanged|Durante la digitazione nel<xref:System.Windows.Controls.TextBox>|<xref:System.Windows.Controls.TextBox>controlli in una finestra di chat room|  
|Explicit|Quando l'applicazione chiama<xref:System.Windows.Data.BindingExpression.UpdateSource%2A>|<xref:System.Windows.Controls.TextBox>controlli in un modulo modificabile (Aggiorna i valori di origine solo quando l'utente fa clic sul pulsante Invia)|  
  
 Per un esempio, vedere [Procedura: Controllare il momento in cui il database di origine viene aggiornato dal testo di TextBox](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
<a name="creating_a_binding"></a>   
## <a name="creating-a-binding"></a>Creazione di un'associazione  
  
 Per ricapitolare alcuni dei concetti illustrati nelle sezioni precedenti, è necessario stabilire un'associazione usando l' <xref:System.Windows.Data.Binding> oggetto e ogni binding in genere ha quattro componenti: destinazione del binding, proprietà di destinazione, origine del binding e un percorso del valore di origine da usare. Questa sezione illustra come impostare un binding.  
  
 Si consideri l'esempio seguente, in cui l'oggetto origine del binding è una classe denominata *MyData* definita nello spazio dei nomi *SDKSample*. A scopo dimostrativo, la classe *MyData* dispone di una proprietà stringa denominata *ColorName*, il cui valore è impostato su "Red". L'esempio genera quindi un pulsante con uno sfondo rosso.  
  
 [!code-xaml[BindNonTextProperty#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page1.xaml#1)]  
  
 Per altre informazioni sulla sintassi della dichiarazione di binding e per esempi su come impostare un binding nel codice, vedere [Cenni preliminari sulle dichiarazioni di binding](binding-declarations-overview.md).  
  
 Se si applica questo esempio al diagramma di base, la figura risultante sarà simile alla seguente. Si tratta di <xref:System.Windows.Data.BindingMode.OneWay> un'associazione perché la proprietà background <xref:System.Windows.Data.BindingMode.OneWay> supporta l'associazione per impostazione predefinita.  
  
 ![Diagramma che mostra la proprietà data binding background.](./media/data-binding-overview/data-binding-button-background-example.png)  
  
 Ci si potrebbe chiedere perché funziona anche se la  proprietà ColorName è di tipo stringa, mentre <xref:System.Windows.Controls.Control.Background%2A> la proprietà è di <xref:System.Windows.Media.Brush>tipo. In questo caso viene usata la conversione di tipi predefinita, descritta nella sezione [Conversione dei dati](#data_conversion).  
  
<a name="specifying_the_binding_source"></a>   
### <a name="specifying-the-binding-source"></a>Specifica dell'origine del binding  
 Si noti che nell'esempio precedente, l'origine del binding viene specificata impostando <xref:System.Windows.FrameworkElement.DataContext%2A> la proprietà <xref:System.Windows.Controls.DockPanel> sull'elemento. Eredita quindi il <xref:System.Windows.FrameworkElement.DataContext%2A> valore da <xref:System.Windows.Controls.DockPanel>, che è il relativo elemento padre. <xref:System.Windows.Controls.Button> Come già detto, l'oggetto origine del binding è uno dei quattro componenti necessari di un binding. Se quindi non si specifica l'oggetto origine del binding, questa non viene creata.  
  
 Esistono diversi modi per specificare l'oggetto origine del binding. L'utilizzo <xref:System.Windows.FrameworkElement.DataContext%2A> della proprietà in un elemento padre è utile quando si associano più proprietà alla stessa origine. In alcuni casi, tuttavia, è preferibile specificare l'origine del binding in singole dichiarazioni di binding. Per l'esempio precedente, invece di usare la <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà, è possibile specificare l'origine del binding impostando <xref:System.Windows.Data.Binding.Source%2A> la proprietà direttamente nella dichiarazione di binding del pulsante, come nell'esempio seguente:  
  
 [!code-xaml[BindNonTextProperty#BackgroundBindingCompact](~/samples/snippets/csharp/VS_Snippets_Wpf/BindNonTextProperty/CS/Page2.xaml#backgroundbindingcompact)]  
  
 Oltre a impostare direttamente <xref:System.Windows.FrameworkElement.DataContext%2A> la proprietà su un elemento, ereditando il <xref:System.Windows.FrameworkElement.DataContext%2A> valore da un predecessore, ad esempio il pulsante nel primo esempio, e specificando in modo esplicito l'origine del binding <xref:System.Windows.Data.Binding.Source%2A> impostando la proprietà nel parametro<xref:System.Windows.Data.Binding> (ad esempio il pulsante nell'ultimo esempio), è anche possibile usare la <xref:System.Windows.Data.Binding.ElementName%2A> proprietà o la <xref:System.Windows.Data.Binding.RelativeSource%2A> proprietà per specificare l'origine del binding. La <xref:System.Windows.Data.Binding.ElementName%2A> proprietà è utile quando si esegue il binding ad altri elementi nell'applicazione, ad esempio quando si usa un dispositivo di scorrimento per regolare la larghezza di un pulsante. La <xref:System.Windows.Data.Binding.RelativeSource%2A> proprietà è utile quando l'associazione viene specificata in un <xref:System.Windows.Controls.ControlTemplate> oggetto o <xref:System.Windows.Style>. Per altre informazioni, vedere [Procedura: Specificare l'origine del binding](how-to-specify-the-binding-source.md).  
  
<a name="specifying_the_path_to_the_value"></a>   
### <a name="specifying-the-path-to-the-value"></a>Specifica del percorso al valore  
 Se l'origine del binding è un oggetto, usare la <xref:System.Windows.Data.Binding.Path%2A> proprietà per specificare il valore da usare per l'associazione. Se si esegue il binding [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ai dati, utilizzare la <xref:System.Windows.Data.Binding.XPath%2A> proprietà per specificare il valore. In alcuni casi, può essere applicabile per utilizzare la <xref:System.Windows.Data.Binding.Path%2A> proprietà anche quando i dati sono. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Se ad esempio si desidera accedere alla proprietà Name di un oggetto XmlNode restituito (in seguito a una query XPath), è necessario utilizzare la <xref:System.Windows.Data.Binding.Path%2A> proprietà oltre <xref:System.Windows.Data.Binding.XPath%2A> alla proprietà.  
  
 Per informazioni sulla sintassi ed esempi, vedere <xref:System.Windows.Data.Binding.Path%2A> le <xref:System.Windows.Data.Binding.XPath%2A> pagine delle proprietà e.  
  
 Si noti che, anche se è stato evidenziato che il <xref:System.Windows.Data.Binding.Path%2A> valore di per usare è uno dei quattro componenti necessari di un'associazione, negli scenari che si desidera associare a un intero oggetto, il valore da utilizzare corrisponde all'oggetto di origine dell'associazione. In questi casi, è applicabile non specificare un oggetto <xref:System.Windows.Data.Binding.Path%2A>. Si consideri l'esempio seguente:  
  
 [!code-xaml[MasterDetail#EmptyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetail/CSharp/Page1.xaml#emptybinding)]  
  
 L'esempio precedente usa la sintassi di binding vuota: {Binding}. In questo caso, <xref:System.Windows.Controls.ListBox> eredita l'oggetto DataContext da un elemento DockPanel padre (non illustrato in questo esempio). Quando il percorso non viene specificato, per impostazione predefinita si esegue un binding all'intero oggetto. In altre parole, in questo esempio il percorso è stato escluso perché è in corso il binding <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> della proprietà all'intero oggetto. Per informazioni più dettagliate, vedere la sezione [Binding alle raccolte](#binding_to_collections).  
  
 Oltre al binding a una raccolta, questo scenario è utile anche in caso di binding a un intero oggetto anziché a una singola proprietà di un oggetto. Si consideri ad esempio un oggetto origine di tipo stringa con un binding alla stringa stessa. Un altro scenario comune riguarda il binding di un elemento a un oggetto con numerose proprietà.  
  
 Affinché i dati siano significativi per la proprietà di destinazione associata, può essere necessario applicare logica personalizzata. Tale logica potrebbe essere un convertitore personalizzato, in assenza della conversione di tipi predefinita. Per informazioni sui convertitori, vedere [Conversione dei dati](#data_conversion).  
  
<a name="binding_bindingexpression"></a>   
### <a name="binding-and-bindingexpression"></a>Binding e BindingExpression  
 Prima di accedere ad altre funzionalità e utilizzi di data binding, sarebbe utile introdurre la <xref:System.Windows.Data.BindingExpression> classe. Come illustrato nelle sezioni precedenti, la <xref:System.Windows.Data.Binding> classe è la classe di alto livello per la dichiarazione di un'associazione. la <xref:System.Windows.Data.Binding> classe fornisce molte proprietà che consentono di specificare le caratteristiche di un'associazione. Una classe correlata <xref:System.Windows.Data.BindingExpression>,, è l'oggetto sottostante che mantiene la connessione tra l'origine e la destinazione. Un binding contiene tutte le informazioni condivisibili tra diverse espressioni di binding. Un <xref:System.Windows.Data.BindingExpression> oggetto è un'espressione <xref:System.Windows.Data.Binding>di istanza che non può essere condivisa e contiene tutte le informazioni sull'istanza di.  
  
 Si consideri, ad esempio, quanto segue, dove *DataObject* è un'istanza della classe di *dati* , il *Binding* è l'oggetto di origine <xref:System.Windows.Data.Binding> e la classe di *dati* è una classe definita che contiene una proprietà di stringa denominata  *MyDataProperty*. In questo esempio il contenuto di testo di un *testo*, un'istanza di <xref:System.Windows.Controls.TextBlock>, viene associato a *MyDataProperty*.  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 È possibile usare lo stesso oggetto *myBinding* per creare altri binding. È ad esempio possibile usare l'oggetto *myBinding* per associare il contenuto di testo di una casella di controllo di testo a *MyDataProperty*. In questo scenario saranno presenti due istanze di condivisione dell' <xref:System.Windows.Data.BindingExpression> oggetto di *associazione* .  
  
 Un <xref:System.Windows.Data.BindingExpression> oggetto può essere ottenuto tramite il valore restituito dalla chiamata <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> a su un oggetto con associazione a dati. Negli argomenti seguenti vengono illustrati alcuni degli utilizzi della <xref:System.Windows.Data.BindingExpression> classe:  
  
- [Procedura: ottenere l'oggetto di binding da una proprietà di destinazione associata](how-to-get-the-binding-object-from-a-bound-target-property.md)  
  
- [Procedura: Controllare il momento in cui il database di origine viene aggiornata dal testo di TextBox](how-to-control-when-the-textbox-text-updates-the-source.md)  
  
<a name="data_conversion"></a>   
## <a name="data-conversion"></a>Conversione dei dati  
 Nell'esempio precedente il pulsante è rosso perché la relativa <xref:System.Windows.Controls.Control.Background%2A> proprietà è associata a una proprietà di stringa con il valore "Red". Questa operazione funziona perché nel <xref:System.Windows.Media.Brush> tipo è presente un convertitore di tipi per convertire il valore stringa in un oggetto. <xref:System.Windows.Media.Brush>  
  
 Se si aggiungono queste informazioni alla figura nella sezione [Creazione di un binding](#creating_a_binding), si ottiene un diagramma analogo al seguente:  
  
 ![Diagramma che mostra il data binding proprietà predefinita.](./media/data-binding-overview/data-binding-button-default-conversion.png)  
  
 Tuttavia, cosa accade se invece di avere una proprietà di tipo stringa l'oggetto di origine del  binding ha una proprietà <xref:System.Windows.Media.Color>color di tipo? In tal caso, per consentire il funzionamento dell'associazione, è necessario innanzitutto trasformare il valore della proprietà *color* in un elemento accettato dalla <xref:System.Windows.Controls.Control.Background%2A> proprietà. È necessario creare un convertitore personalizzato implementando l' <xref:System.Windows.Data.IValueConverter> interfaccia, come nell'esempio seguente:  
  
 [!code-csharp[ColorPicker_snip#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ColorPicker_snip/CSharp/ColorPickerLib/ColorPicker.cs#16)]
 [!code-vb[ColorPicker_snip#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ColorPicker_snip/visualbasic/colorpickerlib/colorpicker.vb#16)]  
  
 Ulteriori <xref:System.Windows.Data.IValueConverter> informazioni sono disponibili nella pagina di riferimento.  
  
 Il convertitore personalizzato viene ora usato al posto della conversione predefinita e il diagramma si presenta come segue:  
  
 ![Diagramma che mostra il convertitore data binding personalizzato.](./media/data-binding-overview/data-binding-converter-color-example.png)  
  
 Come già detto, le conversioni predefinite possono essere disponibili o meno a seconda dei convertitori presenti nel tipo a cui si esegue il binding. Questo comportamento dipenderà dai convertitori di tipi disponibili nella destinazione. In caso di dubbio, creare un convertitore personalizzato.  
  
 Vengono riportati di seguito alcuni scenari tipici in cui è opportuno implementare un convertitore di dati:  
  
- I dati devono essere visualizzati in modo diverso, a seconda delle impostazioni cultura. È ad esempio possibile implementare un convertitore di valuta o un convertitore di data/ora nel calendario in base ai valori o agli standard usati in specifiche impostazioni cultura.  
  
- I dati usati non devono necessariamente modificare il valore di testo di una proprietà quanto piuttosto altri valori, ad esempio l'origine di un'immagine oppure il colore o lo stile del testo visualizzato. I convertitori possono essere usati in questo caso per convertire il binding di una proprietà considerata poco appropriata, ad esempio il binding di un campo di testo alla proprietà Background della cella di una tabella.  
  
- Più controlli o più proprietà dei controlli sono associati agli stessi dati. In questo caso, il binding primario potrebbe semplicemente visualizzare il testo, mentre gli altri binding gestiscono problemi di visualizzazione specifici, usando comunque lo stesso binding come informazione di origine.  
  
- Finora non è ancora stato discusso <xref:System.Windows.Data.MultiBinding>, in cui una proprietà di destinazione ha una raccolta di associazioni. Nel caso di un <xref:System.Windows.Data.MultiBinding>, si usa un oggetto personalizzato <xref:System.Windows.Data.IMultiValueConverter> per produrre un valore finale dai valori delle associazioni. È possibile ad esempio calcolare il colore dai valori rosso, blu e verde, ovvero valori che possono provenire da oggetti origine del binding identici o diversi. Per esempi <xref:System.Windows.Data.MultiBinding> e informazioni, vedere la pagina relativa alla classe.  
  
<a name="binding_to_collections"></a>   
## <a name="binding-to-collections"></a>Binding alle raccolte  
  
 Un oggetto origine del binding può essere considerato come un unico oggetto le cui proprietà contengono dati oppure come una raccolta di dati di oggetti polimorfici che spesso vengono raggruppati. Un esempio può essere il risultato di una query in un database. È stato finora illustrato solo il binding a singoli oggetti. Esiste tuttavia un altro scenario comune che è il binding a una raccolta di dati. Uno scenario comune, ad esempio, consiste nell'usare <xref:System.Windows.Controls.ItemsControl> un oggetto <xref:System.Windows.Controls.ListBox>, ad <xref:System.Windows.Controls.ListView>esempio, <xref:System.Windows.Controls.TreeView> o per visualizzare una raccolta di dati, ad esempio nell'applicazione illustrata nella sezione [informazioni sul data binding](#what_is_data_binding) .  
  
 Anche in questo caso è possibile applicare il diagramma di base. Se si associa un oggetto <xref:System.Windows.Controls.ItemsControl> a una raccolta, il diagramma ha un aspetto simile al seguente:  
  
 ![Diagramma che mostra il data binding oggetto ItemsControl.](./media/data-binding-overview/data-binding-itemscontrol.png)  
  
 Come illustrato in questo diagramma, per associare un <xref:System.Windows.Controls.ItemsControl> oggetto a un oggetto raccolta <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> , Property è la proprietà da usare. È possibile considerare <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> la proprietà come il contenuto <xref:System.Windows.Controls.ItemsControl>di. Si noti che l'associazione <xref:System.Windows.Data.BindingMode.OneWay> è perché <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> la proprietà <xref:System.Windows.Data.BindingMode.OneWay> supporta l'associazione per impostazione predefinita.  
  
<a name="how_to_implement_collections"></a>   
### <a name="how-to-implement-collections"></a>Come implementare le raccolte  
 È possibile enumerare qualsiasi raccolta che implementi <xref:System.Collections.IEnumerable> l'interfaccia. Tuttavia, per configurare i binding dinamici in modo che gli inserimenti o le eliminazioni nella raccolta [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aggiornino automaticamente l'oggetto, la <xref:System.Collections.Specialized.INotifyCollectionChanged> raccolta deve implementare l'interfaccia. Questa interfaccia espone un evento che deve essere generato a ogni modifica della raccolta sottostante.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]fornisce la <xref:System.Collections.ObjectModel.ObservableCollection%601> classe, che è un'implementazione incorporata di una raccolta di dati che espone l' <xref:System.Collections.Specialized.INotifyCollectionChanged> interfaccia. Si noti che per supportare completamente il trasferimento dei valori di dati dagli oggetti di origine alle destinazioni, ogni oggetto della raccolta che supporta le proprietà <xref:System.ComponentModel.INotifyPropertyChanged> associabili deve implementare anche l'interfaccia. Per altre informazioni, vedere [Cenni preliminari sulle origini del binding](binding-sources-overview.md).  
  
 Prima di implementare una raccolta personalizzata, prendere <xref:System.Collections.ObjectModel.ObservableCollection%601> in <xref:System.Collections.Generic.List%601>considerazione l'uso di o di una delle classi di <xref:System.Collections.ObjectModel.Collection%601>raccolte esistenti <xref:System.ComponentModel.BindingList%601>, ad esempio, e, tra molte altre. Se si dispone di uno scenario avanzato e si desidera implementare una raccolta personalizzata, è <xref:System.Collections.IList>consigliabile utilizzare, che fornisce una raccolta non generica di oggetti a cui è possibile accedere singolarmente in base all'indice e pertanto le prestazioni migliori.  
  
<a name="collection_views"></a>   
### <a name="collection-views"></a>Visualizzazioni di raccolte  
 <xref:System.Windows.Controls.ItemsControl> Una volta associato a una raccolta di dati, è possibile ordinare, filtrare o raggruppare i dati. A tale scopo, usare le visualizzazioni di raccolta, che sono classi che implementano l' <xref:System.ComponentModel.ICollectionView> interfaccia.  

#### <a name="what-are-collection-views"></a>Definizione di visualizzazione di raccolta  
 Una visualizzazione di raccolta rappresenta il livello superiore di una raccolta di origine di binding che consente di esplorare e visualizzare la raccolta di origine in base a query di ordinamento, filtro e raggruppamento, il tutto senza modificare la raccolta di origine sottostante. Una visualizzazione di raccolta mantiene inoltre un puntatore all'elemento corrente nella raccolta. Se la raccolta <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> di origine implementa <xref:System.Collections.Specialized.INotifyCollectionChanged> l'interfaccia, le modifiche generate dall'evento vengono propagate alle viste.  
  
 Poiché le visualizzazioni non modificano le raccolte di origine sottostanti, ogni raccolta di origine può avere più visualizzazioni associate. Si consideri ad esempio una raccolta di oggetti *Task*. Grazie alle visualizzazioni è possibile visualizzare gli stessi dati in modi diversi. È possibile ad esempio visualizzare le attività ordinate in base alla priorità nella parte sinistra della pagina e, contemporaneamente nella parte destra, visualizzare le stesse attività raggruppate in base all'area.  
  
<a name="how_to_create_a_view"></a>   
#### <a name="how-to-create-a-view"></a>Come creare una visualizzazione  
 Per creare e usare una visualizzazione, è possibile creare direttamente un'istanza dell'oggetto visualizzazione e usare tale istanza come origine del binding. Si consideri ad esempio l'applicazione [Demo di data binding](https://go.microsoft.com/fwlink/?LinkID=163703) mostrata nella sezione [Definizione di data binding](#what_is_data_binding). L'applicazione viene implementata in modo <xref:System.Windows.Controls.ListBox> che il associ a una visualizzazione sulla raccolta dati invece che direttamente sulla raccolta di dati. L'esempio seguente è stato estratto dall'applicazione [Demo di data binding](https://go.microsoft.com/fwlink/?LinkID=163703). La <xref:System.Windows.Data.CollectionViewSource> classe è il [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] proxy di una classe che eredita da <xref:System.Windows.Data.CollectionView>. In questo particolare esempio, l' <xref:System.Windows.Data.CollectionViewSource.Source%2A> oggetto della vista è associato alla raccolta *AuctionItems* (di tipo <xref:System.Collections.ObjectModel.ObservableCollection%601>) dell'oggetto applicazione corrente.  
  
 [!code-xaml[DataBindingLab#WindowResources1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources1)]  
[!code-xaml[DataBindingLab#CollectionViewSource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#collectionviewsource)]  
[!code-xaml[DataBindingLab#WindowResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#windowresources2)]  
  
 La risorsa *listingDataView* funge quindi da origine dell'associazione per gli elementi dell'applicazione, ad esempio <xref:System.Windows.Controls.ListBox>:  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
  
 Per creare un'altra visualizzazione per la stessa raccolta, è possibile creare <xref:System.Windows.Data.CollectionViewSource> un'altra istanza e assegnarle `x:Key` un nome diverso.  
  
 Nella tabella seguente vengono illustrati i tipi di dati di visualizzazione creati come visualizzazione di raccolta <xref:System.Windows.Data.CollectionViewSource> predefinita o in base al tipo di raccolta di origine.  
  
|Tipo di raccolta di origine|Tipo di visualizzazione di raccolta|Note|  
|----------------------------|--------------------------|-----------|  
|<xref:System.Collections.IEnumerable>|Tipo interno basato su<xref:System.Windows.Data.CollectionView>|Non è possibile raggruppare gli elementi.|  
|<xref:System.Collections.IList>|<xref:System.Windows.Data.ListCollectionView>|Il più veloce.|  
|<xref:System.ComponentModel.IBindingList>|<xref:System.Windows.Data.BindingListCollectionView>||  
  
##### <a name="using-a-default-view"></a>Utilizzo di una visualizzazione predefinita  
 Specificare una visualizzazione di raccolta come origine di binding rappresenta un modo per creare e usare una visualizzazione di raccolta. WPF crea inoltre una visualizzazione di raccolta predefinita per ogni raccolta usata come origine di binding. Se si esegue il binding direttamente a una raccolta, WPF esegue il binding alla relativa visualizzazione predefinita. Questa visualizzazione predefinita è condivisa da tutti i binding alla stessa raccolta, pertanto una modifica apportata a una visualizzazione predefinita da un controllo associato o dal codice, ad esempio l'ordinamento o una modifica al puntatore dell'elemento corrente illustrati più avanti, viene riflessa in tutti gli altri binding alla stessa raccolta.  
  
 Per ottenere la visualizzazione predefinita, usare il <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> metodo. Per un esempio, vedere [Procedura: ottenere la visualizzazione predefinita di una raccolta di dati](how-to-get-the-default-view-of-a-data-collection.md).  
  
##### <a name="collection-views-with-adonet-datatables"></a>Visualizzazioni di raccolta con ADO.NET DataTable  
 Per migliorare le prestazioni, le visualizzazioni di <xref:System.Data.DataTable> raccolta <xref:System.Data.DataView> per ADO.NET o gli oggetti delegano <xref:System.Data.DataView>l'ordinamento e il filtro a. L'ordinamento e il filtro vengono in tal modo condivisi in tutte le visualizzazioni di raccolta dell'origine dati. Per consentire a ogni visualizzazione della raccolta di ordinare e filtrare in modo indipendente, inizializzare ogni visualizzazione <xref:System.Data.DataView> di raccolta con il relativo oggetto.  
  
#### <a name="sorting"></a>Ordinamento  
 Come detto in precedenza, le visualizzazioni possono applicare un ordinamento a una raccolta. Poiché esistono nella raccolta sottostante, i dati possono avere o non avere un ordine intrinseco. La visualizzazione della raccolta consente di imporre un ordine o di modificare l'ordine predefinito in base ai criteri di confronto che si forniscono. Trattandosi di una visualizzazione dei dati basata su client, uno scenario comune prevede che l'utente possa ordinare le colonne di dati tabulari in base al valore al quale corrisponde la colonna. Grazie alle visualizzazioni, è possibile applicare questo ordinamento gestito dall'utente senza apportare alcuna modifica alla raccolta sottostante né dover ripetere la query nel contenuto della raccolta. Per un esempio, vedere [Procedura: Ordinare una colonna GridView quando si fa clic su un'intestazione](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  
  
 Nell'esempio seguente viene illustrata la logica di ordinamento della sezione "Sort by category and <xref:System.Windows.Controls.CheckBox> date" dell' [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] applicazione nella sezione [What is data binding?](#what_is_data_binding) :  
  
 [!code-csharp[DataBindingLab#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#8)]
 [!code-vb[DataBindingLab#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#8)]  
  
#### <a name="filtering"></a>Filtro  
 Le visualizzazioni possono anche applicare un filtro a una raccolta. In altre parole, anche se una raccolta può includere un elemento, questa specifica visualizzazione è progettata per visualizzare solo un determinato subset di una raccolta completa. I dati possono essere filtrati in base a una condizione. Ad esempio, come avviene nell'applicazione nella sezione [What is data binding?](#what_is_data_binding) , la "Show only bargains" <xref:System.Windows.Controls.CheckBox> contiene la logica per filtrare gli elementi che costano $25 o più. Il codice seguente viene eseguito per impostare *ShowOnlyBargainsFilter* come <xref:System.Windows.Data.CollectionViewSource.Filter> gestore <xref:System.Windows.Controls.CheckBox> eventi quando è selezionato:  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 L'implementazione dell'evento *ShowOnlyBargainsFilter* è la seguente:  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
 Se si utilizza direttamente una delle <xref:System.Windows.Data.CollectionView> classi <xref:System.Windows.Data.CollectionViewSource>anziché, utilizzare la <xref:System.Windows.Data.CollectionView.Filter%2A> proprietà per specificare un callback. Per un esempio, vedere [Procedura: Filtrare i dati in una visualizzazione](how-to-filter-data-in-a-view.md).  
  
#### <a name="grouping"></a>Raggruppamento  
 Ad eccezione della classe interna che visualizza una <xref:System.Collections.IEnumerable> raccolta, tutte le visualizzazioni di raccolta supportano la funzionalità di raggruppamento, che consente all'utente di partizionare la raccolta nella visualizzazione raccolta in gruppi logici. Se l'utente fornisce un elenco di gruppi, questi saranno espliciti. Se invece i gruppi vengono generati in modo dinamico in base ai dati, si avranno gruppi impliciti.  
  
 Nell'esempio seguente viene illustrata la logica della categoria "Group by <xref:System.Windows.Controls.CheckBox>":  
  
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
 La nozione di elemento corrente è utile non solo per l'esplorazione degli elementi in una raccolta, bensì anche per lo scenario di binding master-dettagli. Si consideri nuovamente l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione presentata nella sezione [Definizione di data binding](#what_is_data_binding). In tale applicazione, la selezione all'interno <xref:System.Windows.Controls.ListBox> di determina il contenuto visualizzato nell' <xref:System.Windows.Controls.ContentControl>oggetto. Per inserirla in un altro modo, <xref:System.Windows.Controls.ListBox> quando viene selezionato un elemento <xref:System.Windows.Controls.ContentControl> , Visualizza i dettagli dell'elemento selezionato.  
  
 Per implementare lo scenario master-dettagli, occorre semplicemente avere due o più controlli associati alla stessa visualizzazione. Nell'esempio seguente della [demo di data binding](https://go.microsoft.com/fwlink/?LinkID=163703) viene mostrato il markup di <xref:System.Windows.Controls.ListBox> e l' <xref:System.Windows.Controls.ContentControl> oggetto visualizzato nell'applicazione [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] nella sezione [What is data binding?](#what_is_data_binding) :  
  
 [!code-xaml[DataBindingLab#Master1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master1)]  
[!code-xaml[DataBindingLab#Master2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#master2)]  
[!code-xaml[DataBindingLab#Detail](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml#detail)]  
  
 Si noti che entrambi i controlli sono associati alla stessa origine, vale a dire la risorsa statica *listingDataView*. Vedere a tale proposito la definizione di questa risorsa nella sezione [Come creare una visualizzazione](#how_to_create_a_view). Questa operazione funziona perché quando un oggetto Singleton ( <xref:System.Windows.Controls.ContentControl> in questo caso) è associato a una visualizzazione <xref:System.Windows.Data.CollectionView.CurrentItem%2A> di raccolta, viene automaticamente associato alla della visualizzazione. Si noti <xref:System.Windows.Data.CollectionViewSource> che gli oggetti sincronizzano automaticamente valuta e selezione. Se il controllo elenco non è associato a un <xref:System.Windows.Data.CollectionViewSource> oggetto come in questo esempio, è necessario impostare la relativa <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà su `true` affinché funzioni.  
  
 Per altri esempi, vedere [Procedura: Eseguire il binding di una raccolta e visualizzare informazioni in base alla selezione effettuata](how-to-bind-to-a-collection-and-display-information-based-on-selection.md) e [Procedura: Utilizzare il modello master-dettagli con dati gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Come si può notare, l'esempio precedente usa un modello. Infatti, i dati non vengono visualizzati nel modo desiderato senza l'uso di modelli (quello usato in modo esplicito da <xref:System.Windows.Controls.ContentControl> e quello usato <xref:System.Windows.Controls.ListBox>in modo implicito da). Le sezione seguente illustra i modelli di dati.  
  
<a name="data_templating"></a>   
## <a name="data-templating"></a>Modelli di dati  
 Senza l'utilizzo di modelli di dati, l'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione illustrata nella sezione [Definizione di data binding](#what_is_data_binding) avrebbe un aspetto simile al seguente:  
  
 ![Data Binding Demo senza Data Templates](./media/data-binding-overview/data-binding-demo-templates.png)  
  
 Come illustrato nell'esempio della sezione precedente, sia il <xref:System.Windows.Controls.ListBox> controllo che l' <xref:System.Windows.Controls.ContentControl> oggetto sono associati all'intero oggetto Collection (o, più specificamente, alla vista sull'oggetto Collection) di *AuctionItem*s. Senza istruzioni specifiche sulla visualizzazione della raccolta di dati, <xref:System.Windows.Controls.ListBox> in viene visualizzata una rappresentazione di stringa di ogni oggetto nella raccolta sottostante <xref:System.Windows.Controls.ContentControl> e viene visualizzata una rappresentazione di stringa dell'oggetto a cui è associato.  
  
 Per risolvere il problema, l'applicazione definisce <xref:System.Windows.DataTemplate>i. Come illustrato nell'esempio nella sezione precedente, <xref:System.Windows.Controls.ContentControl> USA in modo esplicito *detailsProductListingTemplate*<xref:System.Windows.DataTemplate>. Il <xref:System.Windows.Controls.ListBox> controllo utilizza in modo implicito <xref:System.Windows.DataTemplate> quanto segue per la visualizzazione degli oggetti *AuctionItem* nella raccolta:  
  
 [!code-xaml[DataBindingLab#AuctionItemDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#auctionitemdatatemplate)]  
  
 Con l'uso di questi due <xref:System.Windows.DataTemplate>, l'interfaccia utente risultante è quella illustrata nella sezione [What is data binding?](#what_is_data_binding) . Come si può notare dallo screenshot, oltre a consentire di inserire i dati nei controlli, <xref:System.Windows.DataTemplate>i consentono di definire oggetti visivi accattivanti per i dati. Ad esempio, <xref:System.Windows.DataTrigger>le istanze di vengono usate in <xref:System.Windows.DataTemplate> precedenza in modo che *AuctionItem*s con il valore *SpecialFeatures* di *Highlight* venga visualizzato con un bordo arancione e una stella.  
  
 Per altre informazioni sui modelli di dati, vedere [Cenni preliminari sui modelli di dati](data-templating-overview.md).  
  
<a name="data_validation"></a>   
## <a name="data-validation"></a>Convalida dei dati  
  
 La maggior parte delle applicazioni che accettano input dell'utente deve avere una logica di convalida per garantire che l'utente immetta le informazioni previste. I controlli di convalida possono basarsi sul tipo, l'intervallo, il formato o altri requisiti specifici dell'applicazione. Questa sezione illustra il funzionamento della convalida dei dati in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="associating-validation-rules-with-a-binding"></a>Associazione di regole di convalida a un binding  
 Il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modello di data binding consente di associarlo <xref:System.Windows.Data.Binding.ValidationRules%2A> <xref:System.Windows.Data.Binding> all'oggetto. Nell'esempio seguente, ad esempio, viene associato <xref:System.Windows.Controls.TextBox> un oggetto a una `StartPrice` proprietà denominata e <xref:System.Windows.Controls.ExceptionValidationRule> <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> viene aggiunto un oggetto alla proprietà.  
  
 [!code-xaml[DataBindingLab#DefaultValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#defaultvalidation)]  
  
 <xref:System.Windows.Controls.ValidationRule> Oggetto che controlla se il valore di una proprietà è valido. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]include i due tipi di <xref:System.Windows.Controls.ValidationRule> oggetti predefiniti seguenti:  
  
- Un <xref:System.Windows.Controls.ExceptionValidationRule> controllo per le eccezioni generate durante l'aggiornamento della proprietà di origine dell'associazione. Nell'esempio precedente `StartPrice` è di tipo intero. Quando l'utente immette un valore che non può essere convertito in un intero, viene generata un'eccezione e il binding viene contrassegnato come non valido. Una sintassi alternativa per impostare in <xref:System.Windows.Controls.ExceptionValidationRule> modo esplicito è l'impostazione <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> della proprietà `true` su sull' <xref:System.Windows.Data.Binding> oggetto <xref:System.Windows.Data.MultiBinding> o.  
  
- Un <xref:System.Windows.Controls.DataErrorValidationRule> oggetto verifica la presenza di errori generati da oggetti che implementano <xref:System.ComponentModel.IDataErrorInfo> l'interfaccia. Per un esempio di utilizzo di questa regola di convalida <xref:System.Windows.Controls.DataErrorValidationRule>, vedere. Una sintassi alternativa per impostare in <xref:System.Windows.Controls.DataErrorValidationRule> modo esplicito è l'impostazione <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> della proprietà `true` su sull' <xref:System.Windows.Data.Binding> oggetto <xref:System.Windows.Data.MultiBinding> o.  
  
 È anche possibile creare una regola di convalida personalizzata derivando dalla <xref:System.Windows.Controls.ValidationRule> classe e implementando <xref:System.Windows.Controls.ValidationRule.Validate%2A> il metodo. Nell'esempio seguente viene illustrata la regola utilizzata dall'aggiunta di un *elenco* di prodotti <xref:System.Windows.Controls.TextBox> "data di inizio" dalla sezione [informazioni sul data binding](#what_is_data_binding) :  
  
 [!code-csharp[DataBindingLab#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/FutureDateRule.cs#2)]
 [!code-vb[DataBindingLab#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/FutureDateRule.vb#2)]  
  
 Oggetto<xref:System.Windows.Controls.TextBox> usa questo *FutureDateRule*, come illustrato nell'esempio seguente:  
  
 [!code-xaml[DataBindingLab#CustomValidation](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#customvalidation)]  
  
 Si noti che poiché <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> il valore <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>è, il motore di associazione aggiorna il valore di origine per ogni pressione di tasto, ovvero <xref:System.Windows.Data.Binding.ValidationRules%2A> controlla anche ogni regola della raccolta in ogni sequenza di tasti. L'argomento verrà ulteriormente trattato nella sezione Processo di convalida.  
  
<a name="invalidation_feedback"></a>   
### <a name="providing-visual-feedback"></a>Visualizzazione di un feedback  
 Se l'utente immette un valore non valido, è possibile fornire un feedback relativo all'errore nell'[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dell'applicazione. Un modo per fornire un feedback di questo tipo consiste <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> nell'impostare la proprietà associata <xref:System.Windows.Controls.ControlTemplate>su un oggetto personalizzato. Come illustrato nella sottosezione precedente, *oggetto* <xref:System.Windows.Controls.TextBox> usa un oggetto <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> denominato *validationTemplate*. L'esempio seguente illustra la definizione di *validationTemplate*:  
  
 [!code-xaml[DataBindingLab#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/AddProductWindow.xaml#1)]  
  
 L' <xref:System.Windows.Controls.AdornedElementPlaceholder> elemento specifica la posizione in cui deve essere inserito il controllo da decorare.  
  
 Inoltre, è possibile utilizzare un oggetto <xref:System.Windows.Controls.ToolTip> per visualizzare il messaggio di errore. Sia *oggetto* che *StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>es utilizzano lo stile *textStyleTextBox*, che consente di creare un <xref:System.Windows.Controls.ToolTip> oggetto in cui viene visualizzato il messaggio di errore. L'esempio seguente illustra la definizione di *textStyleTextBox*. La proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `true` quando uno o più binding nelle proprietà dell'elemento associato sono in errore.  
  
 [!code-xaml[DataBindingLab#14](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#14)]  
  
 Con l'oggetto <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> personalizzato e <xref:System.Windows.Controls.ToolTip>l'oggetto, *oggetto* <xref:System.Windows.Controls.TextBox> è simile al seguente quando si verifica un errore di convalida:  
  
 ![Errore di convalida di data binding](./media/databindingdemo-validation.PNG "DataBindingDemo_Validation")  
  
 Se il <xref:System.Windows.Data.Binding> dispone di regole di convalida associate ma non si specifica <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> un oggetto sul controllo associato, verrà <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> utilizzato un valore predefinito per notificare agli utenti quando si verifica un errore di convalida. Il valore <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> predefinito è un modello di controllo che definisce un bordo rosso nel livello dello strumento decorativo. Con le impostazioni <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> predefinite <xref:System.Windows.Controls.ToolTip>e, il [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] valore di *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> è simile al seguente quando si verifica un errore di convalida:  
  
 ![Errore di convalida di data binding](./media/databindingdemo-validationdefault.PNG "DataBindingDemo_ValidationDefault")  
  
 Per un esempio di come fornire una logica di convalida per tutti i controlli in una finestra di dialogo, vedere la sezione Finestre di dialogo personalizzate contenuta in [Cenni preliminari sulle finestre di dialogo](../app-development/dialog-boxes-overview.md).  
  
### <a name="validation-process"></a>Processo di convalida  
 La convalida avviene solitamente quando si trasferisce un valore di destinazione alla proprietà di origine del binding. Questo problema si <xref:System.Windows.Data.BindingMode.TwoWay> verifica <xref:System.Windows.Data.BindingMode.OneWayToSource> sulle associazioni e. Per ripetere, cosa causa un aggiornamento di origine in base al valore della <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà, come descritto nella sezione [What Triggers Source Updates](#what_triggers_source_updates) .  
  
 Viene di seguito descritto il processo di *convalida*. Si noti che se in qualsiasi momento durante questo processo si verifica un errore di convalida o un altro tipo di errore, il processo viene interrotto.  
  
1. Il motore di associazione controlla se sono presenti oggetti <xref:System.Windows.Controls.ValidationRule> personalizzati definiti la <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> cui <xref:System.Windows.Data.Binding>proprietà è <xref:System.Windows.Controls.ValidationStep.RawProposedValue> impostata su, nel qual caso chiama il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo su ogni <xref:System.Windows.Controls.ValidationRule> oggetto fino a quando uno di essi non viene eseguito in un errore o fino a quando tutti i passaggi sono stati superati.  
  
2. Il motore di binding chiama quindi il convertitore, se presente.  
  
3. Se il convertitore ha esito positivo, il motore di associazione controlla se sono <xref:System.Windows.Controls.ValidationRule> presenti oggetti personalizzati <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> definiti la cui <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> proprietà <xref:System.Windows.Data.Binding>è impostata su, nel qual caso viene <xref:System.Windows.Controls.ValidationRule.Validate%2A> chiamato il metodo <xref:System.Windows.Controls.ValidationRule> su ogni oggetto con <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostare su<xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> fino a quando uno di essi non viene eseguito in un errore o fino a quando non vengono superati tutti.  
  
4. Il motore di binding imposta la proprietà di origine.  
  
5. Il motore di associazione controlla se sono presenti oggetti <xref:System.Windows.Controls.ValidationRule> personalizzati definiti la <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> cui <xref:System.Windows.Data.Binding>proprietà è <xref:System.Windows.Controls.ValidationStep.UpdatedValue> impostata su, nel qual caso chiama il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo su ogni <xref:System.Windows.Controls.ValidationRule> oggetto che ha <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostato su <xref:System.Windows.Controls.ValidationStep.UpdatedValue> fino a quando uno di essi non viene eseguito in un errore o fino a quando non vengono superati tutti. Se un <xref:System.Windows.Controls.DataErrorValidationRule> oggetto è associato a un'associazione e <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> la relativa proprietà è impostata <xref:System.Windows.Controls.DataErrorValidationRule> sul <xref:System.Windows.Controls.ValidationStep.UpdatedValue>valore predefinito,, a questo punto viene verificato. Si tratta anche del punto in cui vengono verificate le <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> associazioni con `true` impostato su.  
  
6. Il motore di associazione controlla se sono presenti oggetti <xref:System.Windows.Controls.ValidationRule> personalizzati definiti la <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> cui <xref:System.Windows.Data.Binding>proprietà è <xref:System.Windows.Controls.ValidationStep.CommittedValue> impostata su, nel qual caso chiama il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo su ogni <xref:System.Windows.Controls.ValidationRule> oggetto che ha <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostato su <xref:System.Windows.Controls.ValidationStep.CommittedValue> fino a quando uno di essi non viene eseguito in un errore o fino a quando non vengono superati tutti.  
  
 Se un <xref:System.Windows.Controls.ValidationRule> non passa in qualsiasi momento durante questo processo, il motore di binding crea un <xref:System.Windows.Controls.ValidationError> oggetto <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> e lo aggiunge alla raccolta dell'elemento associato. Prima che il motore di associazione <xref:System.Windows.Controls.ValidationRule> esegua gli oggetti in un determinato passaggio, <xref:System.Windows.Controls.ValidationError> rimuove tutti gli elementi aggiunti <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> alla proprietà associata dell'elemento associato durante tale passaggio. Se, ad esempio, <xref:System.Windows.Controls.ValidationRule> un <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> oggetto il cui <xref:System.Windows.Controls.ValidationStep.UpdatedValue> è impostato su failed, alla successiva esecuzione del <xref:System.Windows.Controls.ValidationError> processo di convalida, il motore di binding lo rimuove immediatamente <xref:System.Windows.Controls.ValidationRule> prima che <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> chiami any con impostato su <xref:System.Windows.Controls.ValidationStep.UpdatedValue>.  
  
 Quando <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> non è vuoto, la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata dell'elemento viene impostata su `true`. Inoltre, se la <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> proprietà <xref:System.Windows.Data.Binding> di è impostata `true`su, il motore di binding genera l' <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> evento associato sull'elemento.  
  
 Si noti anche che un trasferimento di valore valido in entrambe le direzioni (da destinazione a origine o origine a destinazione <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> ) cancella la proprietà associata.  
  
 Se al binding è associato un <xref:System.Windows.Controls.ExceptionValidationRule> oggetto o <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> se la proprietà è impostata su `true` e viene generata un'eccezione quando il motore di binding imposta l'origine, il motore di associazione verifica se è presente un <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>. È possibile usare il <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> callback per fornire un gestore personalizzato per la gestione delle eccezioni. Se un <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> oggetto non è specificato <xref:System.Windows.Data.Binding>in, il motore di associazione crea <xref:System.Windows.Controls.ValidationError> un oggetto <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> con l'eccezione e lo aggiunge alla raccolta dell'elemento associato.  
  
## <a name="debugging-mechanism"></a>Meccanismo di debug  
 È possibile impostare la proprietà <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> associata su un oggetto correlato all'associazione per ricevere informazioni sullo stato di un'associazione specifica.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Novità di WPF versione 4.5](../getting-started/whats-new.md)
- [Eseguire l'associazione dei risultati di una query LINQ](how-to-bind-to-the-results-of-a-linq-query.md)
- [Data binding](../advanced/optimizing-performance-data-binding.md)
- [Demo di data binding](https://go.microsoft.com/fwlink/?LinkID=163703)
- [Procedure relative alle proprietà](data-binding-how-to-topics.md)
- [Procedura: Eseguire l'associazione a un'origine dati ADO.NET](how-to-bind-to-an-ado-net-data-source.md)
