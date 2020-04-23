---
title: Panoramica del data binding
description: Informazioni sulle diverse origini dati che è possibile aggiungere al progetto in Windows Presentation Foundation per .NET Core. Le origini dati possono essere associati a elementi XAML per creare app dinamiche.
author: thraka
ms.date: 09/19/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
ms.openlocfilehash: 7f17ff094a35c04ba880c87c6966d7d249817516
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "82072011"
---
# <a name="data-binding-overview-in-wpf"></a>Cenni preliminari sul data binding in WPF

Il data binding in Windows Presentation Foundation (WPF) offre un modo semplice e coerente per le app di presentare e interagire con i dati. Gli elementi possono essere associati a dati da un'ampia gamma di origini dati sotto forma di oggetti .NET e XML. Qualsiasi <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.Controls.ItemsControl>, <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ListView>ad <xref:System.Windows.Controls.Button> esempio e, dispone di funzionalità incorporate per consentire lo stile flessibile di singoli elementi di dati o raccolte di elementi di dati. In cima ai dati è possibile generare visualizzazioni di ordinamento, filtro e raggruppamento.

La funzionalità data binding di WPF presenta diversi vantaggi rispetto ai modelli tradizionali, incluso il supporto intrinseco per data binding da un'ampia gamma di proprietà, la rappresentazione flessibile dei dati e la separazione pulita della logica di business dall'interfaccia utente.

Questo articolo illustra prima di tutto i concetti fondamentali per WPF data binding e quindi illustra l' <xref:System.Windows.Data.Binding> uso della classe e altre funzionalità di data binding.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-data-binding"></a>Che cos'è il data binding?

Il data binding è il processo che stabilisce una connessione tra l'interfaccia utente dell'app e i dati visualizzati. Se l'associazione è impostata correttamente e i dati forniscono le notifiche appropriate, quando il valore dei dati cambia la modifica si riflette automaticamente negli elementi associati ai dati. Il data binding prevede anche che, se una rappresentazione esterna dei dati in un elemento viene modificata, i dati sottostanti possono essere automaticamente aggiornati in modo da riflettere la modifica. Se, ad esempio, l'utente modifica il valore in un `TextBox` elemento, il valore dei dati sottostanti verrà aggiornato automaticamente per riflettere la modifica.

Un uso tipico di data binding consiste nel posizionare i dati di configurazione del server o locali in moduli o altri controlli dell'interfaccia utente. In WPF, questo concetto viene ampliato per includere un'ampia gamma di proprietà a una varietà di origini dati. In WPF, le proprietà di dipendenza degli elementi possono essere associate a oggetti .NET (inclusi gli oggetti ADO.NET o gli oggetti associati a servizi Web e proprietà Web) e i dati XML.

Per un esempio di data binding, vedere l'interfaccia utente dell'app seguente dalla demo di [Data Binding][data-binding-demo], che visualizza un elenco di elementi dell'asta.

![Schermata di esempio di data binding](./media/data-binding-overview/demo.png "DataBinding_DataBindingDemo")

L'app illustra le seguenti funzionalità di data binding:

- Il contenuto della casella di riepilogo è associato a una raccolta di oggetti *AuctionItem* . Un oggetto *AuctionItem* dispone di proprietà quali *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures*e così via.

- I dati (oggetti*AuctionItem* ) visualizzati in `ListBox` sono basati su modelli in modo da visualizzare la descrizione e il prezzo corrente per ogni elemento. Il modello viene creato tramite un oggetto <xref:System.Windows.DataTemplate>. L'aspetto di ogni articolo dipende inoltre dal valore di *SpecialFeatures* dell'oggetto *AuctionItem* visualizzato. Se il valore di *SpecialFeatures* dell'oggetto *AuctionItem* è *Color*, l'articolo avrà un bordo blu. Se il valore è *Highlight*, l'articolo sarà dotato di un bordo arancione e di una stella. La sezione [Modelli di dati](#data-templating) include informazioni sull'applicazione di modelli ai dati.

- L'utente può raggruppare, filtrare o ordinare i dati utilizzando l' `CheckBoxes` oggetto fornito. Nell'immagine precedente vengono selezionate la **categoria raggruppa per** e **Ordina per categoria e data** `CheckBoxes` . I dati sono raggruppati in base alla categoria del prodotto e i nomi delle categorie seguono l'ordine alfabetico. Benché non risulti evidente dalla figura, gli articoli sono anche ordinati in base alla data di inizio all'interno di ogni categoria. L'ordinamento viene eseguito tramite una *visualizzazione di raccolta*. La sezione [binding alle raccolte](#binding-to-collections) illustra le visualizzazioni di raccolta.

- Quando l'utente seleziona un elemento, <xref:System.Windows.Controls.ContentControl> Visualizza i dettagli dell'elemento selezionato. Questa esperienza è detta *scenario Master-Details*. Nella sezione [scenario Master-Details](#master-detail-binding-scenario) sono disponibili informazioni su questo tipo di associazione.

- Il tipo della proprietà *StartDate* è <xref:System.DateTime>, che restituisce una data che include l'ora del millisecondo. In questa app è stato usato un convertitore personalizzato in modo da visualizzare una stringa di data più breve. La sezione [conversione dei dati](#data-conversion) fornisce informazioni sui convertitori.

Quando l'utente seleziona il pulsante *Aggiungi prodotto* , viene visualizzato il seguente modulo.

![Pagina Add Product Listing](./media/data-binding-overview/demo-addproductlisting.png "DataBinding_Demo_AddProductListing")

L'utente può modificare i campi nel modulo, visualizzare l'anteprima del prodotto utilizzando i riquadri di anteprima brevi o dettagliati e `Submit` selezionare questa voce per aggiungere il nuovo elenco di prodotti. Tutte le impostazioni di raggruppamento, filtro e ordinamento esistenti verranno applicate alla nuova voce. In questo caso specifico, l'articolo immesso nella figura precedente verrà visualizzato come secondo articolo della categoria *Computer*.

Non mostrata in questa immagine è la logica di convalida fornita nella *Data* <xref:System.Windows.Controls.TextBox>di inizio. Se l'utente immette una data non valida (formattazione non valida o data precedente), l'utente riceverà una notifica <xref:System.Windows.Controls.ToolTip> con un e un punto esclamativo rosso <xref:System.Windows.Controls.TextBox>accanto a. La sezione [Convalida dei dati](#data-validation) descrive come creare la logica di convalida.

Prima di approfondire le diverse funzionalità di data binding descritte in precedenza, verranno illustrati i concetti fondamentali essenziali per comprendere data binding WPF.

## <a name="basic-data-binding-concepts"></a>Concetti di base di data binding

Indipendentemente dall'elemento che si sta associando e dalla natura dell'origine dati, ogni binding segue sempre il modello illustrato nella figura seguente.

![Diagramma che mostra il modello di data binding di base.](./media/data-binding-overview/basic-data-binding-diagram.png)

Come illustrato nella figura, data binding è essenzialmente il ponte tra la destinazione del binding e l'origine del binding. Nella figura sono illustrati i concetti fondamentali data binding WPF seguenti:

- In genere, ogni binding è costituito da quattro componenti:

  - Oggetto di destinazione del binding.
  - Proprietà di destinazione.
  - Un'origine di binding.
  - Percorso del valore nell'origine di associazione da utilizzare.
  
  > `TextBox` Se ad esempio si vuole associare il contenuto di un oggetto alla `Employee.Name` proprietà, l'oggetto di destinazione è `TextBox`, la proprietà di destinazione è la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà, il valore da usare è *Name*e l'oggetto di origine è l'oggetto *Employee* .

- La proprietà di destinazione deve essere una proprietà di dipendenza. La <xref:System.Windows.UIElement> maggior parte delle proprietà sono proprietà di dipendenza e la maggior parte delle proprietà di dipendenza, ad eccezione di quelle di sola lettura, supportano data binding per impostazione predefinita. Solo i tipi derivati da <xref:System.Windows.DependencyObject> possono definire le proprietà di <xref:System.Windows.UIElement> dipendenza e tutti i `DependencyObject`tipi derivano da.

- Sebbene non sia illustrato nella figura, si noti che l'oggetto di origine del binding non è limitato a essere un oggetto .NET personalizzato. WPF data binding supporta dati sotto forma di oggetti .NET e XML. Per fornire alcuni esempi, l'origine del binding può essere <xref:System.Windows.UIElement>un oggetto, qualsiasi oggetto elenco, un oggetto ADO.NET o un oggetto servizio Web o un XmlNode che contiene i dati XML. Per altre informazioni, vedere [Cenni preliminari sulle origini di associazione](../../framework/wpf/data/binding-sources-overview.md).

È importante ricordare che quando si stabilisce un'associazione, si associa una destinazione di binding a un'origine *di* associazione. Se, ad esempio, si visualizzano alcuni dati XML sottostanti <xref:System.Windows.Controls.ListBox> in un oggetto utilizzando Data Binding, si `ListBox` associa ai dati XML.

Per stabilire un'associazione, utilizzare l' <xref:System.Windows.Data.Binding> oggetto. Nella parte restante di questo articolo vengono illustrati molti dei concetti associati a e alcune delle proprietà e dell' `Binding` utilizzo dell'oggetto.

### <a name="direction-of-the-data-flow"></a>Direzione del flusso di dati

Come indicato dalla freccia nella figura precedente, il flusso di dati di un'associazione può passare dalla destinazione dell'associazione all'origine dell'associazione, ad esempio quando un utente modifica il valore di un oggetto `TextBox`e/o dall'origine dell'associazione alla destinazione del binding (ad esempio, il `TextBox` contenuto viene aggiornato con le modifiche nell'origine del binding) se l'origine dell'associazione fornisce le notifiche appropriate.

È possibile che l'app consenta agli utenti di modificare i dati e di propagarli nuovamente all'oggetto di origine. oppure è possibile fare in modo che gli utenti non possano aggiornare i dati di origine. È possibile controllare il flusso di dati impostando <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>.

In questa figura vengono illustrati i diversi tipi di flusso di dati:

![Flusso di dati dell'associazione dati](./media/data-binding-overview/databinding-dataflow.png "DataBinding_DataFlow")

- <xref:System.Windows.Data.BindingMode.OneWay>l'associazione determina l'aggiornamento automatico della proprietà di destinazione delle modifiche apportate alla proprietà di origine, ma le modifiche apportate alla proprietà di destinazione non vengono propagate alla proprietà di origine. Questo tipo di binding è appropriato se il controllo da associare è implicitamente di sola lettura. Ad esempio, è possibile eseguire l'associazione a un'origine, ad esempio un titolo di borsa, oppure la proprietà di destinazione non dispone di un'interfaccia di controllo fornita per apportare modifiche, ad esempio un colore di sfondo associato a dati di una tabella. Se non è necessario monitorare le modifiche delle proprietà di destinazione, l'uso della modalità di associazione <xref:System.Windows.Data.BindingMode.OneWay> consente di evitare il sovraccarico della modalità di binding <xref:System.Windows.Data.BindingMode.TwoWay>.

- <xref:System.Windows.Data.BindingMode.TwoWay>l'associazione causa modifiche alla proprietà di origine o alla proprietà di destinazione per aggiornare automaticamente l'altra. Questo tipo di associazione è adatto ai moduli modificabili o ad altri scenari di interfaccia utente completamente interattivi. Per <xref:System.Windows.Data.BindingMode.OneWay> impostazione predefinita, la maggior parte delle proprietà è vincolante, ma alcune proprietà di dipendenza, in genere <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType> le proprietà dei controlli modificabili dall'utente <xref:System.Windows.Data.BindingMode.TwoWay> , ad esempio e [CheckBox. Unchecked](xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked) default to binding. Un modo programmatico per determinare se una proprietà di dipendenza esegue l'associazione unidirezionale o bidirezionale per impostazione predefinita consiste nell'ottenere i metadati <xref:System.Windows.DependencyProperty.GetMetadata%2A?displayProperty=nameWithType> della proprietà con e quindi controllare il valore <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A?displayProperty=nameWithType> booleano della proprietà.

- <xref:System.Windows.Data.BindingMode.OneWayToSource>è il contrario dell' <xref:System.Windows.Data.BindingMode.OneWay> associazione; Aggiorna la proprietà di origine quando viene modificata la proprietà di destinazione. Uno scenario di esempio è se è necessario rivalutare solo il valore di origine dall'interfaccia utente.

- Non illustrato nella figura è <xref:System.Windows.Data.BindingMode.OneTime> l'associazione, che fa in modo che la proprietà di origine Inizializza la proprietà di destinazione, ma non propaga le modifiche successive. Se il contesto dei dati cambia o l'oggetto nel contesto dei dati cambia, la modifica *non* viene riflessa nella proprietà di destinazione. Questo tipo di binding è appropriato se uno snapshot dello stato corrente è appropriato o se i dati sono realmente statici. Questo tipo di binding è utile anche se si vuole inizializzare la proprietà di destinazione con un valore ricavato da una proprietà di origine e il contesto dei dati non è noto in anticipo. Questa modalità è essenzialmente una forma più semplice di <xref:System.Windows.Data.BindingMode.OneWay> binding che offre prestazioni migliori nei casi in cui il valore di origine non cambia.

Per rilevare le modifiche apportate <xref:System.Windows.Data.BindingMode.OneWay> all' <xref:System.Windows.Data.BindingMode.TwoWay> origine (applicabili alle associazioni e), l'origine deve implementare un meccanismo appropriato di <xref:System.ComponentModel.INotifyPropertyChanged>notifica delle modifiche alle proprietà, ad esempio. Vedere [procedura: implementare una notifica di modifica delle proprietà](../../framework/wpf/data/how-to-implement-property-change-notification.md) per un esempio <xref:System.ComponentModel.INotifyPropertyChanged> di implementazione.

La <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType> proprietà fornisce ulteriori informazioni sulle modalità di associazione e un esempio di come specificare la direzione di un'associazione.

### <a name="what-triggers-source-updates"></a>Cosa attiva gli aggiornamenti dell'origine

Binding che sono <xref:System.Windows.Data.BindingMode.TwoWay> o <xref:System.Windows.Data.BindingMode.OneWayToSource> restano in ascolto delle modifiche nella proprietà di destinazione e li propagano all'origine, noto come aggiornamento dell'origine. Può accadere ad esempio che si modifichi il testo di un oggetto TextBox per modificare il valore di origine sottostante.

Tuttavia, il valore di origine viene aggiornato durante la modifica del testo o dopo aver completato la modifica del testo e il controllo perde lo stato attivo? La <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> proprietà determina che cosa attiva l'aggiornamento dell'origine. I punti delle frecce a destra nella figura seguente illustrano il ruolo della <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> proprietà.

![Diagramma che mostra il ruolo della proprietà UpdateSourceTrigger.](./media/data-binding-overview/data-binding-updatesource-trigger.png)

Se il `UpdateSourceTrigger` valore è <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged?displayProperty=nameWithType>, il valore a cui punta la freccia destra di <xref:System.Windows.Data.BindingMode.TwoWay> o i <xref:System.Windows.Data.BindingMode.OneWayToSource> binding vengono aggiornati non appena viene modificata la proprietà di destinazione. Tuttavia, se il `UpdateSourceTrigger` valore è <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>, il valore viene aggiornato solo con il nuovo valore quando la proprietà di destinazione perde lo stato attivo.

Analogamente alla <xref:System.Windows.Data.Binding.Mode%2A> proprietà, diverse proprietà di dipendenza hanno valori <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> predefiniti diversi. Il valore predefinito per la maggior parte delle proprietà di dipendenza è <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, mentre la proprietà `TextBox.Text` ha il valore predefinito <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. `PropertyChanged`indica che gli aggiornamenti di origine vengono in genere eseguiti ogni volta che la proprietà di destinazione cambia. Le modifiche immediate sono belle per le caselle di controllo e altri semplici controlli. Per i campi di testo, tuttavia, l'aggiornamento dopo ogni pressione di tasto può ridurre le prestazioni e nega all'utente la consueta opportunità di BACKSPACE e correggere gli errori di digitazione prima di eseguire il commit nel nuovo valore.

Per informazioni <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> su come trovare il valore predefinito di una proprietà di dipendenza, vedere la pagina delle proprietà.

Nella tabella seguente viene fornito uno scenario di esempio <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> per ogni valore <xref:System.Windows.Controls.TextBox> utilizzando come esempio.

| Valore di UpdateSourceTrigger | Quando viene aggiornato il valore di origine | Scenario di esempio per TextBox |
| ------------------------- | ---------------------------------- | ---------------------------- |
| `LostFocus`(impostazione predefinita <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>per) | Quando il controllo TextBox perde lo stato attivo. | Casella di testo associata alla logica di convalida (vedere la [convalida dei dati](#data-validation) riportata di seguito). |
| `PropertyChanged` | Durante la <xref:System.Windows.Controls.TextBox>digitazione in. | Controlli TextBox in una finestra della chat room. |
| `Explicit` | Quando l'app chiama <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>. | Controlli TextBox in un modulo modificabile (Aggiorna i valori di origine solo quando l'utente fa clic sul pulsante Invia). |

Per un esempio, vedere [procedura: controllare quando il testo della casella di testo aggiorna l'origine](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).

## <a name="creating-a-binding"></a>Creazione di un'associazione

Per ridefinire alcuni dei concetti illustrati nelle sezioni precedenti, è necessario stabilire un'associazione utilizzando l' <xref:System.Windows.Data.Binding> oggetto e ogni Binding dispone in genere di quattro componenti: una destinazione del binding, una proprietà di destinazione, un'origine di binding e un percorso del valore di origine da utilizzare. Questa sezione illustra come impostare un binding.

Si consideri l'esempio seguente, in cui l'oggetto origine del binding è una classe denominata *MyData* definita nello spazio dei nomi *SDKSample*. A scopo dimostrativo, *i dati* hanno una proprietà stringa denominata *ColorName* il cui valore è impostato su "Red". L'esempio genera quindi un pulsante con uno sfondo rosso.

[!code-xaml[BindNonTextProperty](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColor)]

Per ulteriori informazioni sulla sintassi di dichiarazione dell'associazione ed esempi di come configurare un'associazione nel codice, vedere [Cenni preliminari sulle dichiarazioni](../../framework/wpf/data/binding-declarations-overview.md)di associazione.

Se si applica questo esempio al diagramma di base, la figura risultante sarà simile alla seguente. In questa figura viene <xref:System.Windows.Data.BindingMode.OneWay> descritta un'associazione perché la proprietà <xref:System.Windows.Data.BindingMode.OneWay> background supporta l'associazione per impostazione predefinita.

![Diagramma che mostra la proprietà data binding background.](./media/data-binding-overview/data-binding-button-background-example.png)

Ci si potrebbe chiedere perché questa associazione funzioni anche se la proprietà *ColorName* è di tipo stringa, <xref:System.Windows.Controls.Control.Background%2A> mentre la proprietà è <xref:System.Windows.Media.Brush>di tipo. Questa associazione usa la conversione di tipi predefinita, descritta nella sezione relativa alla [conversione dei dati](#data-conversion) .

### <a name="specifying-the-binding-source"></a>Specifica dell'origine del binding

Si noti che nell'esempio precedente, l'origine del binding viene specificata impostando la proprietà [DockPanel. DataContext](xref:System.Windows.FrameworkElement.DataContext) . Eredita <xref:System.Windows.Controls.Button> quindi il <xref:System.Windows.FrameworkElement.DataContext%2A> valore da <xref:System.Windows.Controls.DockPanel>, che è il relativo elemento padre. Come già detto, l'oggetto origine del binding è uno dei quattro componenti necessari di un binding. Se quindi non si specifica l'oggetto origine del binding, questa non viene creata.

Esistono diversi modi per specificare l'oggetto origine del binding. L'utilizzo <xref:System.Windows.FrameworkElement.DataContext%2A> della proprietà in un elemento padre è utile quando si associano più proprietà alla stessa origine. In alcuni casi, tuttavia, è preferibile specificare l'origine del binding in singole dichiarazioni di binding. Per l'esempio precedente, invece di usare la <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà, è possibile specificare l'origine del binding impostando <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> la proprietà direttamente nella dichiarazione di binding del pulsante, come nell'esempio seguente.

[!code-xaml[BindNonTextPropertyCompactBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColorCompactBinding)]

Oltre a impostare direttamente <xref:System.Windows.FrameworkElement.DataContext%2A> la proprietà su un elemento, ereditando il <xref:System.Windows.FrameworkElement.DataContext%2A> valore da un predecessore, ad esempio il pulsante nel primo esempio, e specificando in modo esplicito l'origine del binding <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> impostando la proprietà sull'associazione, ad esempio il pulsante nell'ultimo esempio, è possibile utilizzare anche <xref:System.Windows.Data.Binding.ElementName?displayProperty=nameWithType> la proprietà o <xref:System.Windows.Data.Binding.RelativeSource?displayProperty=nameWithType> la proprietà per specificare l'origine del binding. La <xref:System.Windows.Data.Binding.ElementName%2A> proprietà è utile quando si esegue il binding ad altri elementi nell'app, ad esempio quando si usa un dispositivo di scorrimento per regolare la larghezza di un pulsante. La <xref:System.Windows.Data.Binding.RelativeSource%2A> proprietà è utile quando l'associazione viene specificata in un <xref:System.Windows.Controls.ControlTemplate> oggetto o <xref:System.Windows.Style>. Per altre informazioni, vedere [procedura: specificare l'origine del binding](../../framework/wpf/data/how-to-specify-the-binding-source.md).

### <a name="specifying-the-path-to-the-value"></a>Specifica del percorso del valore

Se l'origine del binding è un oggetto, usare la <xref:System.Windows.Data.Binding.Path?displayProperty=nameWithType> proprietà per specificare il valore da usare per l'associazione. Se si esegue il binding ai dati XML, utilizzare la <xref:System.Windows.Data.Binding.XPath?displayProperty=nameWithType> proprietà per specificare il valore. In alcuni casi, può essere applicabile per utilizzare la <xref:System.Windows.Data.Binding.Path%2A> proprietà anche quando i dati sono XML. Se ad esempio si desidera accedere alla proprietà Name di un oggetto XmlNode restituito (in seguito a una query XPath), è necessario utilizzare la <xref:System.Windows.Data.Binding.Path%2A> proprietà oltre alla <xref:System.Windows.Data.Binding.XPath%2A> proprietà.

Per ulteriori informazioni, vedere le <xref:System.Windows.Data.Binding.Path%2A> proprietà <xref:System.Windows.Data.Binding.XPath%2A> e.

Sebbene sia stato evidenziato che il <xref:System.Windows.Data.Binding.Path%2A> valore di per utilizzare è uno dei quattro componenti necessari di un'associazione, negli scenari in cui si desidera eseguire l'associazione a un intero oggetto, il valore da utilizzare corrisponde all'oggetto di origine dell'associazione. In questi casi, è applicabile non specificare un oggetto <xref:System.Windows.Data.Binding.Path%2A>. Si consideri l'esempio seguente.

[!code-xaml[EmptyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/EmptyBinding.xaml#EmptyBinding)]

L'esempio precedente usa la sintassi di binding vuota: {Binding}. In questo caso, <xref:System.Windows.Controls.ListBox> eredita l'oggetto DataContext da un elemento DockPanel padre (non illustrato in questo esempio). Quando il percorso non viene specificato, per impostazione predefinita si esegue un binding all'intero oggetto. In altre parole, in questo esempio il percorso è stato escluso perché è in corso il binding <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> della proprietà all'intero oggetto. Per una discussione approfondita, vedere la sezione [associazione alla raccolta](#binding-to-collections) .

Oltre al binding a una raccolta, questo scenario è utile anche in caso di binding a un intero oggetto anziché a una singola proprietà di un oggetto. Se, ad esempio, l'oggetto di origine è <xref:System.String>di tipo, è possibile eseguire l'associazione solo alla stringa stessa. Un altro scenario comune riguarda il binding di un elemento a un oggetto con numerose proprietà.

Potrebbe essere necessario applicare la logica personalizzata in modo che i dati siano significativi per la proprietà di destinazione associata. Se la conversione del tipo predefinito non esiste, la logica personalizzata potrebbe essere sotto forma di convertitore personalizzato. Per informazioni sui convertitori, vedere [conversione dei dati](#data-conversion) .

### <a name="binding-and-bindingexpression"></a>Binding e BindingExpression

Prima di accedere ad altre funzionalità e utilizzi di data binding, è utile introdurre la <xref:System.Windows.Data.BindingExpression> classe. Come illustrato nelle sezioni precedenti, la <xref:System.Windows.Data.Binding> classe è la classe di alto livello per la dichiarazione di un'associazione. fornisce molte proprietà che consentono di specificare le caratteristiche di un'associazione. Una classe correlata <xref:System.Windows.Data.BindingExpression>,, è l'oggetto sottostante che mantiene la connessione tra l'origine e la destinazione. Un binding contiene tutte le informazioni condivisibili tra diverse espressioni di binding. Un <xref:System.Windows.Data.BindingExpression> oggetto è un'espressione di istanza che non può essere condivisa e contiene tutte le informazioni <xref:System.Windows.Data.Binding>sull'istanza di.

Si consideri l'esempio `myDataObject` seguente, in cui è `MyData` un'istanza `myBinding` della classe, <xref:System.Windows.Data.Binding> è l'oggetto `MyData` di origine e è una classe definita che contiene una `MyDataProperty`proprietà di stringa denominata. In questo esempio viene associato il contenuto di `myText`testo di, un' <xref:System.Windows.Controls.TextBlock>istanza di `MyDataProperty`a.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ManualBinding.cs#CodeOnlyBinding)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ManualBinding.vb#CodeOnlyBinding)]

È possibile usare lo stesso oggetto *myBinding* per creare altri binding. Ad esempio, è possibile usare l'oggetto *SetBinding* per associare il contenuto di testo di una casella di controllo a *MyDataProperty*. In questo scenario saranno presenti due istanze di condivisione dell' <xref:System.Windows.Data.BindingExpression> oggetto di *associazione* .

Un <xref:System.Windows.Data.BindingExpression> oggetto viene restituito chiamando <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> su un oggetto con associazione a dati. Gli articoli seguenti illustrano alcuni degli usi della <xref:System.Windows.Data.BindingExpression> classe:

- [Ottenere l'oggetto di binding da una proprietà di destinazione associata](../../framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)

- [Controllare quando il testo della casella di testo aggiorna l'origine](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)

## <a name="data-conversion"></a>Conversione di dati

Nella sezione [creazione di un'associazione](#creating-a-binding) il pulsante è rosso perché la relativa <xref:System.Windows.Controls.Control.Background%2A> proprietà è associata a una proprietà di stringa con il valore "Red". Questo valore di stringa funziona perché nel <xref:System.Windows.Media.Brush> tipo è presente un convertitore di tipi per convertire il valore stringa in <xref:System.Windows.Media.Brush>un oggetto.

Aggiungendo queste informazioni alla figura la sezione [creazione di un'associazione ha un](#creating-a-binding) aspetto simile al seguente.

![Diagramma che mostra il data binding proprietà predefinita.](./media/data-binding-overview/data-binding-button-default-conversion.png)

Tuttavia, cosa accade se invece di avere una proprietà di tipo stringa l'oggetto di origine del *Color* binding ha una proprietà <xref:System.Windows.Media.Color>color di tipo? In tal caso, per consentire il funzionamento dell'associazione, è necessario innanzitutto trasformare il valore della proprietà *color* in un elemento accettato dalla <xref:System.Windows.Controls.Control.Background%2A> proprietà. È necessario creare un convertitore personalizzato implementando l' <xref:System.Windows.Data.IValueConverter> interfaccia, come nell'esempio seguente.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ColorBrushConverter.cs#ColorBrushConverter)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ColorBrushConverter.vb#ColorBrushConverter)]

Per altre informazioni, vedere <xref:System.Windows.Data.IValueConverter>.

Il convertitore personalizzato viene ora usato al posto della conversione predefinita e il diagramma ha un aspetto simile al seguente.

![Diagramma che mostra il convertitore data binding personalizzato.](./media/data-binding-overview/data-binding-converter-color-example.png)

Come già detto, le conversioni predefinite possono essere disponibili o meno a seconda dei convertitori presenti nel tipo a cui si esegue il binding. Questo comportamento dipenderà dai convertitori di tipi disponibili nella destinazione. In caso di dubbio, creare un convertitore personalizzato.

Di seguito sono riportati alcuni scenari tipici in cui è opportuno implementare un convertitore di dati:

- I dati devono essere visualizzati in modo diverso, a seconda delle impostazioni cultura. È ad esempio possibile implementare un convertitore di valuta o un convertitore di data/ora di calendario basato sulle convenzioni utilizzate in determinate impostazioni cultura.

- I dati usati non devono necessariamente modificare il valore di testo di una proprietà quanto piuttosto altri valori, ad esempio l'origine di un'immagine oppure il colore o lo stile del testo visualizzato. I convertitori possono essere usati in questo caso per convertire il binding di una proprietà considerata poco appropriata, ad esempio il binding di un campo di testo alla proprietà Background della cella di una tabella.

- Più di un controllo o più proprietà dei controlli sono associati agli stessi dati. In questo caso, il binding primario potrebbe semplicemente visualizzare il testo, mentre gli altri binding gestiscono problemi di visualizzazione specifici, usando comunque lo stesso binding come informazione di origine.

- Una proprietà di destinazione ha una raccolta di associazioni, che viene definita <xref:System.Windows.Data.MultiBinding>. Per <xref:System.Windows.Data.MultiBinding>, è possibile utilizzare un <xref:System.Windows.Data.IMultiValueConverter> oggetto personalizzato per produrre un valore finale dai valori dei binding. È possibile ad esempio calcolare il colore dai valori rosso, blu e verde, ovvero valori che possono provenire da oggetti origine del binding identici o diversi. Per <xref:System.Windows.Data.MultiBinding> esempi e informazioni, vedere.

## <a name="binding-to-collections"></a>Associazione alle raccolte

Un oggetto di origine di associazione può essere considerato come un singolo oggetto le cui proprietà contengono dati o come raccolta di dati di oggetti polimorfici spesso raggruppati, ad esempio il risultato di una query in un database. Finora è stata discussa solo l'associazione a singoli oggetti. Tuttavia, l'associazione a una raccolta dati è uno scenario comune. Uno scenario comune, ad esempio, consiste nell'usare <xref:System.Windows.Controls.ItemsControl> un tipo <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.ListView>o <xref:System.Windows.Controls.TreeView> per visualizzare una raccolta di dati, ad esempio nell'app mostrata nella sezione [What is data binding](#what-is-data-binding) .

Anche in questo caso è possibile applicare il diagramma di base. Se si associa un oggetto <xref:System.Windows.Controls.ItemsControl> a una raccolta, il diagramma ha un aspetto simile al seguente.

![Diagramma che mostra il data binding oggetto ItemsControl.](./media/data-binding-overview/data-binding-itemscontrol.png)

Come illustrato in questo diagramma, per associare un <xref:System.Windows.Controls.ItemsControl> oggetto a un oggetto raccolta <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A?displayProperty=nameWithType> , Property è la proprietà da usare. È possibile considerare `ItemsSource` come il contenuto di <xref:System.Windows.Controls.ItemsControl>. L'associazione è <xref:System.Windows.Data.BindingMode.OneWay> perché la `ItemsSource` proprietà supporta `OneWay` l'associazione per impostazione predefinita.

### <a name="how-to-implement-collections"></a>Come implementare le raccolte

È possibile enumerare qualsiasi raccolta che implementi <xref:System.Collections.IEnumerable> l'interfaccia. Tuttavia, per configurare i binding dinamici in modo che gli inserimenti o le eliminazioni nella raccolta aggiornino automaticamente l'interfaccia utente, la <xref:System.Collections.Specialized.INotifyCollectionChanged> raccolta deve implementare l'interfaccia. Questa interfaccia espone un evento che deve essere generato a ogni modifica della raccolta sottostante.

WPF fornisce la <xref:System.Collections.ObjectModel.ObservableCollection%601> classe, che è un'implementazione incorporata di una raccolta di dati che espone l' <xref:System.Collections.Specialized.INotifyCollectionChanged> interfaccia. Per supportare completamente il trasferimento dei valori di dati dagli oggetti di origine alle destinazioni, ogni oggetto della raccolta che supporta le proprietà associabili deve implementare anche l' <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia. Per altre informazioni, vedere [Cenni preliminari sulle origini di associazione](../../framework/wpf/data/binding-sources-overview.md).

Prima di implementare una raccolta personalizzata, prendere <xref:System.Collections.ObjectModel.ObservableCollection%601> in <xref:System.Collections.Generic.List%601>considerazione l'uso di o di una delle classi di <xref:System.Collections.ObjectModel.Collection%601>raccolte esistenti <xref:System.ComponentModel.BindingList%601>, ad esempio, e, tra molte altre. Se si dispone di uno scenario avanzato e si desidera implementare una raccolta personalizzata, considerare <xref:System.Collections.IList>l'utilizzo di, che fornisce una raccolta non generica di oggetti a cui è possibile accedere singolarmente dall'indice e fornisce pertanto le prestazioni migliori.

### <a name="collection-views"></a>Visualizzazioni raccolta

<xref:System.Windows.Controls.ItemsControl> Una volta associato a una raccolta di dati, è possibile ordinare, filtrare o raggruppare i dati. A tale scopo, usare le visualizzazioni di raccolta, che sono classi che implementano l' <xref:System.ComponentModel.ICollectionView> interfaccia.

#### <a name="what-are-collection-views"></a>Che cosa sono le visualizzazioni di raccolta?

Una visualizzazione di raccolta rappresenta il livello superiore di una raccolta di origine di binding che consente di esplorare e visualizzare la raccolta di origine in base a query di ordinamento, filtro e raggruppamento, il tutto senza modificare la raccolta di origine sottostante. Una visualizzazione di raccolta mantiene inoltre un puntatore all'elemento corrente nella raccolta. Se la raccolta di origine implementa <xref:System.Collections.Specialized.INotifyCollectionChanged> l'interfaccia, le modifiche generate <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> dall'evento vengono propagate alle viste.

Poiché le visualizzazioni non modificano le raccolte di origine sottostanti, ogni raccolta di origine può avere più visualizzazioni associate. Si consideri ad esempio una raccolta di oggetti *Task*. Grazie alle visualizzazioni è possibile visualizzare gli stessi dati in modi diversi. È possibile ad esempio visualizzare le attività ordinate in base alla priorità nella parte sinistra della pagina e, contemporaneamente nella parte destra, visualizzare le stesse attività raggruppate in base all'area.

#### <a name="how-to-create-a-view"></a>Come creare una visualizzazione

Per creare e usare una visualizzazione, è possibile creare direttamente un'istanza dell'oggetto visualizzazione e usare tale istanza come origine del binding. Si consideri, ad esempio, l'app [demo di data binding][data-binding-demo] mostrata nella sezione [What is data binding](#what-is-data-binding) . L'app viene implementata in modo <xref:System.Windows.Controls.ListBox> che il associ a una visualizzazione sulla raccolta dati invece che direttamente sulla raccolta di dati. L'esempio seguente viene estratto dall'app [demo di data binding][data-binding-demo] . La <xref:System.Windows.Data.CollectionViewSource> classe è il proxy XAML di una classe che eredita da <xref:System.Windows.Data.CollectionView>. In questo particolare esempio, l' <xref:System.Windows.Data.CollectionViewSource.Source%2A> oggetto della vista è associato alla raccolta *AuctionItems* (di tipo <xref:System.Collections.ObjectModel.ObservableCollection%601>) dell'oggetto app corrente.

[!code-xaml[CollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#CollectionView)]

La risorsa *listingDataView* funge quindi da origine dell'associazione per gli elementi nell'app, ad esempio <xref:System.Windows.Controls.ListBox>.

[!code-xaml[ListBoxCollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxCollectionView)]

Per creare un'altra visualizzazione per la stessa raccolta, è possibile creare <xref:System.Windows.Data.CollectionViewSource> un'altra istanza e assegnarle `x:Key` un nome diverso.

Nella tabella seguente vengono illustrati i tipi di dati di visualizzazione creati come visualizzazione di raccolta <xref:System.Windows.Data.CollectionViewSource> predefinita o in base al tipo di raccolta di origine.

| Tipo di raccolta di origine                    | Tipo di visualizzazione di raccolta | Note |
| ----------------------------------------- | -------------------- | ----- |
| <xref:System.Collections.IEnumerable>     | Tipo interno basato su<xref:System.Windows.Data.CollectionView> | Non è possibile raggruppare gli elementi. |
| <xref:System.Collections.IList>           | <xref:System.Windows.Data.ListCollectionView> | Il più veloce. |
| <xref:System.ComponentModel.IBindingList> | <xref:System.Windows.Data.BindingListCollectionView> | |

#### <a name="using-a-default-view"></a>Utilizzo di una visualizzazione predefinita

Specificare una visualizzazione di raccolta come origine di binding rappresenta un modo per creare e usare una visualizzazione di raccolta. WPF crea inoltre una visualizzazione di raccolta predefinita per ogni raccolta usata come origine di binding. Se si esegue il binding direttamente a una raccolta, WPF esegue il binding alla relativa visualizzazione predefinita. Questa visualizzazione predefinita è condivisa da tutti i binding alla stessa raccolta, quindi una modifica apportata a una visualizzazione predefinita da un controllo o da un codice associato, ad esempio l'ordinamento o una modifica al puntatore dell'elemento corrente, descritta più avanti, viene riflessa in tutte le altre associazioni alla stessa raccolta.

Per ottenere la visualizzazione predefinita, usare il <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> metodo. Per un esempio, vedere [ottenere la visualizzazione predefinita di una raccolta di dati](../../framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).

#### <a name="collection-views-with-adonet-datatables"></a>Viste di raccolta con DataTables ADO.NET

Per migliorare le prestazioni, le visualizzazioni di <xref:System.Data.DataTable> raccolta <xref:System.Data.DataView> per ADO.NET o gli oggetti delegano <xref:System.Data.DataView>l'ordinamento e il filtro a, che determina la condivisione dell'ordinamento e del filtro tra tutte le visualizzazioni di raccolta dell'origine dati. Per consentire a ogni visualizzazione della raccolta di ordinare e filtrare in modo indipendente, inizializzare ogni visualizzazione <xref:System.Data.DataView> di raccolta con il relativo oggetto.

#### <a name="sorting"></a>Ordinamento

Come detto in precedenza, le visualizzazioni possono applicare un ordinamento a una raccolta. Poiché esistono nella raccolta sottostante, i dati possono avere o non avere un ordine intrinseco. La visualizzazione della raccolta consente di imporre un ordine o di modificare l'ordine predefinito in base ai criteri di confronto che si forniscono. Trattandosi di una visualizzazione dei dati basata su client, uno scenario comune prevede che l'utente possa ordinare le colonne di dati tabulari in base al valore al quale corrisponde la colonna. Grazie alle visualizzazioni, è possibile applicare questo ordinamento gestito dall'utente senza apportare alcuna modifica alla raccolta sottostante né dover ripetere la query nel contenuto della raccolta. Per un esempio, vedere [ordinare una colonna GridView quando si fa clic su un'intestazione](../../framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).

Nell'esempio seguente viene illustrata la logica di ordinamento di "Ordina per categoria e data <xref:System.Windows.Controls.CheckBox> " dell'interfaccia utente dell'app nella sezione [What is data binding](#what-is-data-binding) .

[!code-csharp[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#AddSortChecked)]
[!code-vb[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#AddSortChecked)]

#### <a name="filtering"></a>Filtri

Le visualizzazioni possono inoltre applicare un filtro a una raccolta, in modo che la visualizzazione mostri solo un determinato subset della raccolta completa. I dati possono essere filtrati in base a una condizione. Ad esempio, come avviene con l'app nella sezione [che cosa è data binding](#what-is-data-binding) , la "Mostra solo le occasioni" <xref:System.Windows.Controls.CheckBox> contiene la logica per filtrare gli elementi che costano $25 o più. Il codice seguente viene eseguito per impostare *ShowOnlyBargainsFilter* come gestore <xref:System.Windows.Data.CollectionViewSource.Filter> eventi quando <xref:System.Windows.Controls.CheckBox> viene selezionato.

[!code-csharp[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingViewFilter)]
[!code-vb[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingViewFilter)]

Il gestore dell'evento *ShowOnlyBargainsFilter* presenta l'implementazione seguente.

[!code-csharp[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#FilterEvent)]
[!code-vb[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#FilterEvent)]

Se si utilizza direttamente una delle <xref:System.Windows.Data.CollectionView> classi anziché <xref:System.Windows.Data.CollectionViewSource>, utilizzare la <xref:System.Windows.Data.CollectionView.Filter%2A> proprietà per specificare un callback. Per un esempio, vedere [Procedura: Filtrare i dati in una visualizzazione](../../framework/wpf/data/how-to-filter-data-in-a-view.md).

#### <a name="grouping"></a>Raggruppamento

Ad eccezione della classe interna che visualizza una <xref:System.Collections.IEnumerable> raccolta, tutte le visualizzazioni di raccolta supportano il *raggruppamento*, che consente all'utente di partizionare la raccolta nella visualizzazione raccolta in gruppi logici. Se l'utente fornisce un elenco di gruppi, questi saranno espliciti. Se invece i gruppi vengono generati in modo dinamico in base ai dati, si avranno gruppi impliciti.

Nell'esempio seguente viene illustrata la logica della categoria "Group by <xref:System.Windows.Controls.CheckBox>".

[!code-csharp[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingGroupCheck)]
[!code-vb[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingGroupCheck)]

Per un altro esempio di raggruppamento, vedere [Procedura: Raggruppare gli elementi di un controllo ListView che implementa una GridView](../../framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md).

#### <a name="current-item-pointers"></a>Puntatori elemento corrente

Le visualizzazioni supportano anche la nozione di elemento corrente. In una visualizzazione di raccolta è possibile spostarsi da un oggetto all'altro. Durante lo spostamento viene spostato un puntatore dell'elemento che consente di recuperare l'oggetto presente in un percorso specifico nella raccolta. Per un esempio, vedere [spostarsi tra gli oggetti in una data CollectionView](../../framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).

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

Il puntatore dell'elemento corrente può essere influenzato da un'operazione di ordinamento o filtro applicata alla raccolta. L'ordinamento mantiene il puntatore dell'elemento corrente sull'ultimo elemento selezionato, ma la visualizzazione di raccolta viene ristrutturata in base a tale elemento. (Probabilmente l'elemento selezionato si trovava all'inizio dell'elenco prima, ma ora l'elemento selezionato potrebbe trovarsi in un punto al centro). Il filtro mantiene l'elemento selezionato se tale selezione rimane visualizzata dopo il filtro. Il puntatore dell'elemento corrente viene altrimenti impostato sul primo elemento della visualizzazione di raccolta filtrata.

#### <a name="master-detail-binding-scenario"></a>Scenario di associazione master-dettagli

La nozione di elemento corrente è utile non solo per l'esplorazione degli elementi in una raccolta, bensì anche per lo scenario di binding master-dettagli. Prendere in considerazione l'interfaccia utente dell'app nella sezione [What is data binding](#what-is-data-binding) . In tale app la selezione all'interno di <xref:System.Windows.Controls.ListBox> determina il contenuto visualizzato nell'oggetto <xref:System.Windows.Controls.ContentControl>. Per inserirla in un altro modo, <xref:System.Windows.Controls.ListBox> quando viene selezionato un elemento <xref:System.Windows.Controls.ContentControl> , Visualizza i dettagli dell'elemento selezionato.

Per implementare lo scenario master-dettagli, occorre semplicemente avere due o più controlli associati alla stessa visualizzazione. L'esempio seguente dalla [demo di data binding][data-binding-demo] Mostra il markup di <xref:System.Windows.Controls.ListBox> e l'oggetto <xref:System.Windows.Controls.ContentControl> visualizzato nell'interfaccia utente dell'app nella sezione [What is data binding](#what-is-data-binding) .

[!code-xaml[ListBoxContentControl](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxContentControl)]

Si noti che entrambi i controlli sono associati alla stessa origine, ovvero la risorsa statica *listingDataView* (vedere la definizione di questa risorsa nella [sezione How to create a View](#how-to-create-a-view)). Questa associazione funziona perché quando un oggetto Singleton ( <xref:System.Windows.Controls.ContentControl> in questo caso) è associato a una visualizzazione <xref:System.Windows.Data.CollectionView.CurrentItem%2A> di raccolta, viene automaticamente associato all'oggetto della visualizzazione. Gli <xref:System.Windows.Data.CollectionViewSource> oggetti sincronizzano automaticamente valuta e selezione. Se il controllo elenco non è associato a un <xref:System.Windows.Data.CollectionViewSource> oggetto come in questo esempio, è necessario impostare la relativa <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà su `true` affinché funzioni.

Per altri esempi, vedere [eseguire l'associazione a una raccolta e visualizzare informazioni in base alla selezione](../../framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) e [usare il modello Master-Details con dati gerarchici](../../framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md).

Come si può notare, l'esempio precedente usa un modello. Infatti, i dati non vengono visualizzati nel modo desiderato senza l'uso di modelli (quello usato in modo esplicito da <xref:System.Windows.Controls.ContentControl> e quello usato in modo implicito da <xref:System.Windows.Controls.ListBox>). Le sezione seguente illustra i modelli di dati.

## <a name="data-templating"></a>Modelli di dati

Senza l'uso di modelli di dati, l'interfaccia utente dell'app nella sezione [What is data binding](#what-is-data-binding) avrà un aspetto simile al seguente.

![Data Binding Demo senza Data Templates](./media/data-binding-overview/demo-no-template.png)

Come illustrato nell'esempio della sezione precedente, sia il <xref:System.Windows.Controls.ListBox> controllo che l' <xref:System.Windows.Controls.ContentControl> oggetto sono associati all'intero oggetto Collection (o, più specificamente, alla vista sull'oggetto Collection) di *AuctionItem*s. Senza istruzioni specifiche sulla visualizzazione della raccolta di dati, <xref:System.Windows.Controls.ListBox> Visualizza la rappresentazione di stringa di ogni oggetto nella raccolta sottostante e <xref:System.Windows.Controls.ContentControl> Visualizza la rappresentazione di stringa dell'oggetto a cui è associato.

Per risolvere il problema, l'app definisce <xref:System.Windows.DataTemplate?text=DataTemplates>. Come illustrato nell'esempio della sezione precedente, USA in <xref:System.Windows.Controls.ContentControl> modo esplicito il modello di dati *detailsProductListingTemplate* . Il <xref:System.Windows.Controls.ListBox> controllo utilizza in modo implicito il modello di dati seguente quando vengono visualizzati gli oggetti *AuctionItem* nella raccolta.

[!code-xaml[AuctionItemDataTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#AuctionItemDataTemplate)]

Con l'uso di questi due DataTemplate, l'interfaccia utente risultante è quella illustrata nella sezione [What is data binding](#what-is-data-binding) . Come si può notare dallo screenshot, oltre a consentire di inserire i dati nei controlli, DataTemplates consente di definire oggetti visivi accattivanti per i dati. Ad esempio, <xref:System.Windows.DataTrigger>le istanze di vengono usate in <xref:System.Windows.DataTemplate> precedenza in modo che *AuctionItem*s con il valore *SpecialFeatures* di *Highlight* venga visualizzato con un bordo arancione e una stella.

Per ulteriori informazioni sui modelli di dati, vedere [Cenni preliminari](../../framework/wpf/data/data-templating-overview.md)sui modelli di dati.

## <a name="data-validation"></a>Convalida dei dati

La maggior parte dell'app che accetta input utente deve avere la logica di convalida per assicurarsi che l'utente abbia immesso le informazioni previste. I controlli di convalida possono essere basati su tipo, intervallo, formato o altri requisiti specifici dell'app. In questa sezione viene illustrato il funzionamento della convalida dei dati in WPF.

### <a name="associating-validation-rules-with-a-binding"></a>Associazione delle regole di convalida a un'associazione

Il modello di data binding WPF consente di associarlo <xref:System.Windows.Data.Binding.ValidationRules%2A> all' <xref:System.Windows.Data.Binding> oggetto. Nell'esempio seguente, ad esempio, viene associato <xref:System.Windows.Controls.TextBox> un oggetto a una `StartPrice` proprietà denominata e <xref:System.Windows.Controls.ExceptionValidationRule> viene aggiunto un <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> oggetto alla proprietà.

[!code-xaml[TextboxStartPrice](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartPrice)]

<xref:System.Windows.Controls.ValidationRule> Oggetto che controlla se il valore di una proprietà è valido. WPF include due tipi di <xref:System.Windows.Controls.ValidationRule> oggetti incorporati:

- Un <xref:System.Windows.Controls.ExceptionValidationRule> controllo per le eccezioni generate durante l'aggiornamento della proprietà di origine dell'associazione. Nell'esempio precedente `StartPrice` è di tipo intero. Quando l'utente immette un valore che non può essere convertito in un intero, viene generata un'eccezione e il binding viene contrassegnato come non valido. Una sintassi alternativa per impostare in <xref:System.Windows.Controls.ExceptionValidationRule> modo esplicito è l'impostazione <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> della proprietà `true` su sull' <xref:System.Windows.Data.Binding> oggetto <xref:System.Windows.Data.MultiBinding> o.

- Un <xref:System.Windows.Controls.DataErrorValidationRule> oggetto verifica la presenza di errori generati da oggetti che implementano <xref:System.ComponentModel.IDataErrorInfo> l'interfaccia. Per un esempio di utilizzo di questa regola di convalida <xref:System.Windows.Controls.DataErrorValidationRule>, vedere. Una sintassi alternativa per impostare in <xref:System.Windows.Controls.DataErrorValidationRule> modo esplicito è l'impostazione <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> della proprietà `true` su sull' <xref:System.Windows.Data.Binding> oggetto <xref:System.Windows.Data.MultiBinding> o.

È anche possibile creare una regola di convalida personalizzata derivando dalla <xref:System.Windows.Controls.ValidationRule> classe e implementando <xref:System.Windows.Controls.ValidationRule.Validate%2A> il metodo. Nell'esempio seguente viene illustrata la regola utilizzata dall' *aggiunta del prodotto* "data di <xref:System.Windows.Controls.TextBox> inizio" dalla sezione informazioni sul [Data Binding](#what-is-data-binding) .

[!code-csharp[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/FutureDateRule.cs#FutureDateRule)]
[!code-vb[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/FutureDateRule.vb#FutureDateRule)]

*Oggetto* <xref:System.Windows.Controls.TextBox> usa questo *FutureDateRule*, come illustrato nell'esempio seguente.

[!code-xaml[TextboxStartDate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartDate)]

Poiché il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> valore è <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, il motore di associazione aggiorna il valore di origine per ogni sequenza di tasti, il che significa che controlla anche <xref:System.Windows.Data.Binding.ValidationRules%2A> ogni regola nella raccolta per ogni sequenza di tasti. L'argomento verrà ulteriormente trattato nella sezione Processo di convalida.

### <a name="providing-visual-feedback"></a>Fornire feedback visivo

Se l'utente immette un valore non valido, potrebbe essere necessario fornire un feedback sull'errore nell'interfaccia utente dell'app. Un modo per fornire un feedback di questo tipo consiste <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> nell'impostare la proprietà associata <xref:System.Windows.Controls.ControlTemplate>su un oggetto personalizzato. Come illustrato nella sottosezione precedente, *oggetto* <xref:System.Windows.Controls.TextBox> usa un oggetto <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> denominato *validationTemplate*. Nell'esempio seguente viene illustrata la definizione di *validationTemplate*.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#ControlTemplate)]

L' <xref:System.Windows.Controls.AdornedElementPlaceholder> elemento specifica la posizione in cui deve essere inserito il controllo da decorare.

Inoltre, è possibile utilizzare un oggetto <xref:System.Windows.Controls.ToolTip> per visualizzare il messaggio di errore. Sia *oggetto* che *StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>es utilizzano lo stile *textStyleTextBox*, che consente di creare un <xref:System.Windows.Controls.ToolTip> oggetto in cui viene visualizzato il messaggio di errore. L'esempio seguente illustra la definizione di *textStyleTextBox*. La proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata è `true` quando uno o più binding nelle proprietà dell'elemento associato sono in errore.

[!code-xaml[TextBoxStyle](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextBoxStyle)]

Con l'oggetto <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> personalizzato e <xref:System.Windows.Controls.ToolTip>l'oggetto, *oggetto* <xref:System.Windows.Controls.TextBox> è simile al seguente quando si verifica un errore di convalida.

![Errore di convalida del data binding](./media/data-binding-overview/demo-validation-date.png "DataBindingDemo_Validation")

Se il <xref:System.Windows.Data.Binding> dispone di regole di convalida associate ma non si specifica <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> un oggetto sul controllo associato, verrà <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> utilizzato un valore predefinito per notificare agli utenti quando si verifica un errore di convalida. Il valore <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> predefinito è un modello di controllo che definisce un bordo rosso nel livello dello strumento decorativo. Con le impostazioni <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> predefinite e <xref:System.Windows.Controls.ToolTip>, l'interfaccia utente di *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> ha un aspetto simile al seguente quando si verifica un errore di convalida.

![Errore di convalida del data binding](./media/data-binding-overview/demo-validation-price.png "DataBindingDemo_ValidationDefault")

Per un esempio di come fornire la logica per la convalida di tutti i controlli in una finestra di dialogo, vedere la sezione finestre di dialogo personalizzate nelle [finestre di dialogo Panoramica](../../framework/wpf/app-development/dialog-boxes-overview.md).

### <a name="validation-process"></a>Processo di convalida

La convalida avviene solitamente quando si trasferisce un valore di destinazione alla proprietà di origine del binding. Questo trasferimento si verifica <xref:System.Windows.Data.BindingMode.TwoWay> sulle <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni e. Per ripetere, cosa causa un aggiornamento di origine in base al valore della <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> proprietà, come descritto nella sezione [What Triggers Source Updates](#what-triggers-source-updates) .

Gli elementi seguenti descrivono il processo di *convalida* . Se in qualsiasi momento durante questo processo si verifica un errore di convalida o un altro tipo di errore, il processo viene interrotto:

1. Il motore di associazione controlla se sono presenti oggetti <xref:System.Windows.Controls.ValidationRule> personalizzati definiti la <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> cui proprietà è <xref:System.Windows.Controls.ValidationStep.RawProposedValue> impostata su <xref:System.Windows.Data.Binding>, nel qual caso viene chiamato il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo su ogni <xref:System.Windows.Controls.ValidationRule> oggetto fino a quando uno di essi non viene eseguito in un errore o fino a quando non vengono superati tutti.

2. Il motore di binding chiama quindi il convertitore, se presente.

3. Se il convertitore ha esito positivo, il motore di associazione controlla se sono <xref:System.Windows.Controls.ValidationRule> presenti oggetti personalizzati <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> definiti la cui <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> proprietà è <xref:System.Windows.Data.Binding>impostata su, nel qual caso chiama <xref:System.Windows.Controls.ValidationRule.Validate%2A> il metodo su <xref:System.Windows.Controls.ValidationRule> ogni che <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> ha impostato <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> su fino a quando uno di essi non viene eseguito in un errore o fino a quando non vengono superati tutti.

4. Il motore di binding imposta la proprietà di origine.

5. Il motore di associazione controlla se sono presenti oggetti <xref:System.Windows.Controls.ValidationRule> personalizzati definiti la <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> cui proprietà è <xref:System.Windows.Controls.ValidationStep.UpdatedValue> impostata su <xref:System.Windows.Data.Binding>, nel qual caso viene chiamato il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo su ogni <xref:System.Windows.Controls.ValidationRule> oggetto <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostato su <xref:System.Windows.Controls.ValidationStep.UpdatedValue> fino a quando uno di essi non viene eseguito in un errore o fino a quando non vengono superati tutti. Se un <xref:System.Windows.Controls.DataErrorValidationRule> oggetto è associato a un'associazione e <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> la relativa proprietà è impostata sul <xref:System.Windows.Controls.ValidationStep.UpdatedValue>valore predefinito <xref:System.Windows.Controls.DataErrorValidationRule> ,, a questo punto viene verificato. A questo punto, viene controllata qualsiasi binding <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> con impostato `true` su.

6. Il motore di associazione controlla se sono presenti oggetti <xref:System.Windows.Controls.ValidationRule> personalizzati definiti la <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> cui proprietà è <xref:System.Windows.Controls.ValidationStep.CommittedValue> impostata su <xref:System.Windows.Data.Binding>, nel qual caso viene chiamato il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo su ogni <xref:System.Windows.Controls.ValidationRule> oggetto <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostato su <xref:System.Windows.Controls.ValidationStep.CommittedValue> fino a quando uno di essi non viene eseguito in un errore o fino a quando non vengono superati tutti.

Se un <xref:System.Windows.Controls.ValidationRule> non passa in qualsiasi momento durante questo processo, il motore di binding crea un <xref:System.Windows.Controls.ValidationError> oggetto e lo aggiunge alla <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> raccolta dell'elemento associato. Prima che il motore di associazione <xref:System.Windows.Controls.ValidationRule> esegua gli oggetti in un determinato passaggio, <xref:System.Windows.Controls.ValidationError> rimuove tutti gli elementi aggiunti <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> alla proprietà associata dell'elemento associato durante tale passaggio. Se, ad esempio, <xref:System.Windows.Controls.ValidationRule> un <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> oggetto il cui <xref:System.Windows.Controls.ValidationStep.UpdatedValue> è impostato su failed, alla successiva esecuzione del processo di convalida, il motore <xref:System.Windows.Controls.ValidationError> di binding lo rimuove immediatamente <xref:System.Windows.Controls.ValidationRule> prima di <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> chiamare qualsiasi <xref:System.Windows.Controls.ValidationStep.UpdatedValue>oggetto con impostato su.

Quando <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> non è vuoto, la <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> proprietà associata dell'elemento viene impostata su `true`. Inoltre, se la <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> proprietà di <xref:System.Windows.Data.Binding> è impostata su `true`, il motore di binding genera l' <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> evento associato sull'elemento.

Si noti anche che un trasferimento di valore valido in entrambe le direzioni (da destinazione a origine o origine a destinazione <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> ) cancella la proprietà associata.

Se al binding è associato un <xref:System.Windows.Controls.ExceptionValidationRule> oggetto o se la <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> proprietà è impostata su `true` e viene generata un'eccezione quando il motore di binding imposta l'origine, il motore di associazione verifica se è presente un. <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> È possibile usare il <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> callback per fornire un gestore personalizzato per la gestione delle eccezioni. Se un <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> oggetto non è specificato in <xref:System.Windows.Data.Binding>, il motore di associazione crea <xref:System.Windows.Controls.ValidationError> un oggetto con l'eccezione e lo aggiunge <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> alla raccolta dell'elemento associato.

## <a name="debugging-mechanism"></a>Meccanismo di debug

È possibile impostare la proprietà <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> associata su un oggetto correlato all'associazione per ricevere informazioni sullo stato di un'associazione specifica.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Eseguire l'associazione ai risultati di una query LINQ](../../framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)
- [Associazione dati](../../framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Demo di data binding][data-binding-demo]
- [Articoli sulle procedure](../../framework/wpf/data/data-binding-how-to-topics.md)
- [Eseguire il binding a un'origine dati ADO.NET](../../framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)

[data-binding-demo]: https://github.com/microsoft/WPF-Samples/tree/master/Sample%20Applications/DataBindingDemo "app demo data binding"
