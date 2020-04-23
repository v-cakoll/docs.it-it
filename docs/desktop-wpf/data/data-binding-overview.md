---
title: Panoramica del data binding
description: Informazioni sulle diverse origini dati che è possibile aggiungere al progetto in Windows Presentation Foundation per .NET Core.Learn about the different data sources you can add to your project in Windows Presentation Foundation for .NET Core. Le origini dati possono essere associate a elementi XAML per creare app dinamiche.
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
# <a name="data-binding-overview-in-wpf"></a>Panoramica dell'associazione dati in WPFData binding overview in WPF

L'associazione dati in Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF)Windows Presentation Gli elementi possono essere associati ai dati da un'ampia gamma di origini dati sotto forma di oggetti .NET e XML. Qualsiasi, <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.Controls.Button> ad <xref:System.Windows.Controls.ItemsControl>esempio, <xref:System.Windows.Controls.ListBox> e <xref:System.Windows.Controls.ListView>qualsiasi , quali e , dispongono di funzionalità incorporate per consentire lo stile flessibile di singoli elementi di dati o raccolte di elementi di dati. In cima ai dati è possibile generare visualizzazioni di ordinamento, filtro e raggruppamento.

La funzionalità di associazione dati in WPFWPF presenta diversi vantaggi rispetto ai modelli tradizionali, tra cui il supporto intrinseco per l'associazione dati da parte di un'ampia gamma di proprietà, una rappresentazione flessibile dell'interfaccia utente dei dati e una netta separazione della logica di business dall'interfaccia utente.

In questo articolo vengono illustrati in primo luogo i <xref:System.Windows.Data.Binding> concetti fondamentali per l'associazione dati WPFWPF e quindi viene illustrato l'utilizzo della classe e di altre funzionalità dell'associazione dati.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-data-binding"></a>Che cos'è il data binding?

L'associazione dati è il processo che stabilisce una connessione tra l'interfaccia utente dell'app e i dati visualizzati. Se l'associazione è impostata correttamente e i dati forniscono le notifiche appropriate, quando il valore dei dati cambia la modifica si riflette automaticamente negli elementi associati ai dati. Il data binding prevede anche che, se una rappresentazione esterna dei dati in un elemento viene modificata, i dati sottostanti possono essere automaticamente aggiornati in modo da riflettere la modifica. Ad esempio, se l'utente modifica `TextBox` il valore in un elemento, il valore dei dati sottostante viene aggiornato automaticamente per riflettere tale modifica.

Un utilizzo tipico dell'associazione dati consiste nell'inserire i dati di configurazione locali o del server in form o altri controlli dell'interfaccia utente. In WPFWPF, questo concetto viene espanso per includere l'associazione di un'ampia gamma di proprietà a un'ampia gamma di origini dati. In WPFWPF, le proprietà di dipendenza degli elementi possono essere associate a oggetti .NET (inclusi oggetti ADO.NET o oggetti associati a servizi Web e proprietà Web) e dati XML.

Per un esempio di associazione dati, dai un'occhiata alla seguente interfaccia utente dell'app dalla [demo sull'associazione dati][data-binding-demo], che visualizza un elenco di elementi dell'asta.

![Schermata di esempio di associazione dati](./media/data-binding-overview/demo.png "DataBinding_DataBindingDemo")

L'app illustra le seguenti funzionalità dell'associazione dati:

- Il contenuto di ListBox è associato a una raccolta di *AuctionItem* oggetti. Un oggetto *AuctionItem* dispone di proprietà quali *Description*, *StartPrice*, *StartDate*, *Category*, *SpecialFeatures*e così via.

- I dati ( oggetti*AuctionItem)* visualizzati nel `ListBox` oggetto sono basati su modelli in modo che la descrizione e il prezzo corrente vengano visualizzati per ogni articolo. Il modello viene creato <xref:System.Windows.DataTemplate>utilizzando un oggetto . L'aspetto di ogni articolo dipende inoltre dal valore di *SpecialFeatures* dell'oggetto *AuctionItem* visualizzato. Se il valore di *SpecialFeatures* dell'oggetto *AuctionItem* è *Color*, l'articolo avrà un bordo blu. Se il valore è *Highlight*, l'articolo sarà dotato di un bordo arancione e di una stella. La sezione [Modelli di dati](#data-templating) include informazioni sull'applicazione di modelli ai dati.

- L'utente può raggruppare, filtrare `CheckBoxes` o ordinare i dati utilizzando quelli forniti. Nell'immagine precedente vengono selezionate le opzioni **Raggruppa per categoria** e Ordina per categoria e **data.** `CheckBoxes` I dati sono raggruppati in base alla categoria del prodotto e i nomi delle categorie seguono l'ordine alfabetico. Benché non risulti evidente dalla figura, gli articoli sono anche ordinati in base alla data di inizio all'interno di ogni categoria. L'ordinamento viene eseguito utilizzando una *visualizzazione raccolta.* La sezione [Associazione alle raccolte](#binding-to-collections) illustra le visualizzazioni delle raccolte.

- Quando l'utente seleziona un <xref:System.Windows.Controls.ContentControl> elemento, visualizza i dettagli dell'elemento selezionato. Questa esperienza è *denominata scenario Master-dettagli*. Nella sezione [Scenario Master-dettagli](#master-detail-binding-scenario) vengono fornite informazioni su questo tipo di associazione.

- Il tipo della proprietà <xref:System.DateTime> *StartDate* è , che restituisce una data che include l'ora al millisecondo. In questa app è stato utilizzato un convertitore personalizzato in modo che venga visualizzata una stringa di data più breve. La sezione [Conversione dati](#data-conversion) fornisce informazioni sui convertitori.

Quando l'utente seleziona il pulsante *Aggiungi prodotto,* viene visualizzato il seguente modulo.

![Pagina Add Product Listing](./media/data-binding-overview/demo-addproductlisting.png "DataBinding_Demo_AddProductListing")

L'utente può modificare i campi nel modulo, visualizzare in anteprima l'elenco `Submit` dei prodotti utilizzando i riquadri di anteprima brevi o dettagliati e scegliere di aggiungere il nuovo elenco di prodotti. Tutte le impostazioni di raggruppamento, filtro e ordinamento esistenti verranno applicate alla nuova voce. In questo caso specifico, l'articolo immesso nella figura precedente verrà visualizzato come secondo articolo della categoria *Computer*.

Non viene visualizzata in questa immagine è la logica di convalida fornita nella *data* <xref:System.Windows.Controls.TextBox>di inizio . Se l'utente immette una data non valida (formattazione non valida <xref:System.Windows.Controls.ToolTip> o una data passata), <xref:System.Windows.Controls.TextBox>l'utente riceverà una notifica con un punto esclamativo rosso accanto al . La sezione [Convalida dei dati](#data-validation) descrive come creare la logica di convalida.

Prima di esaminare le diverse funzionalità dell'associazione dati descritte in precedenza, verranno illustrati i concetti fondamentali fondamentali fondamentali per comprendere l'associazione dati WPF.

## <a name="basic-data-binding-concepts"></a>Concetti di base sull'associazione dati

Indipendentemente dall'elemento da associare e dalla natura dell'origine dati, ogni associazione segue sempre il modello illustrato nella figura seguente.

![Diagramma che mostra il modello di associazione dati di base.](./media/data-binding-overview/basic-data-binding-diagram.png)

Come illustrato nella figura, l'associazione dati è essenzialmente il ponte tra la destinazione di associazione e l'origine di associazione. Nella figura vengono illustrati i concetti fondamentali di associazione dati WPF:The figure demonstrates the following fundamental WPF Data binding concepts:

- In genere, ogni associazione ha quattro componenti:Typically, each binding has four components:

  - Oggetto di destinazione dell'associazione.
  - Una proprietà di destinazione.
  - Un'origine di binding.
  - Percorso del valore nell'origine dell'associazione da utilizzare.
  
  > Ad esempio, se si desidera associare il contenuto `TextBox` di un oggetto alla proprietà , l'oggetto `Employee.Name` di destinazione è il `TextBox`, la proprietà di destinazione è la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà , il valore da utilizzare è *Name*e l'oggetto di origine è il *Employee* oggetto.

- La proprietà di destinazione deve essere una proprietà di dipendenza. La <xref:System.Windows.UIElement> maggior parte delle proprietà sono proprietà di dipendenza e la maggior parte delle proprietà di dipendenza, ad eccezione di quelle di sola lettura, supporta l'associazione dati per impostazione predefinita. Solo i tipi <xref:System.Windows.DependencyObject> derivati da possono <xref:System.Windows.UIElement> definire le `DependencyObject`proprietà di dipendenza e tutti i tipi derivano da .)

- Anche se non è illustrato nella figura, è necessario notare che l'oggetto origine dell'associazione non è limitato a essere un oggetto .NET personalizzato. L'associazione dati WPF supporta i dati sotto forma di oggetti .NET e XML. Per fornire alcuni esempi, l'origine dell'associazione può essere un oggetto , un <xref:System.Windows.UIElement>oggetto elenco, un oggetto ADO.NET o Servizi Web o un Oggetto XmlNode contenente i dati XML. Per ulteriori informazioni, vedere Panoramica delle origini di [associazione.](../../framework/wpf/data/binding-sources-overview.md)

È importante ricordare che quando si stabilisce un'associazione, si associa una destinazione di associazione *a* un'origine di associazione. Ad esempio, se si visualizzano alcuni <xref:System.Windows.Controls.ListBox> dati XML sottostanti in `ListBox` un'associazione dati di utilizzo, si sta associando l'elemento ai dati XML.

Per stabilire un'associazione, utilizzare l'oggetto <xref:System.Windows.Data.Binding> . Nella parte restante di questo articolo vengono illustrati molti dei `Binding` concetti associati e alcune delle proprietà e l'utilizzo dell'oggetto.

### <a name="direction-of-the-data-flow"></a>Direzione del flusso di dati

Come indicato dalla freccia nella figura precedente, il flusso di dati di un'associazione può passare dalla destinazione di associazione all'origine di associazione (ad esempio, il valore di origine cambia quando un utente modifica il valore di un `TextBox`) e/o dall'origine di associazione alla destinazione di associazione (ad esempio, il `TextBox` contenuto viene aggiornato con le modifiche nell'origine di associazione) se l'origine di associazione fornisce le notifiche appropriate.

Puoi consentire all'app di modificare i dati e propagarlo nuovamente all'oggetto di origine. oppure è possibile fare in modo che gli utenti non possano aggiornare i dati di origine. È possibile controllare il flusso <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType>di dati impostando il .

Figura che illustra i diversi tipi di flusso di dati:This figure illustrates the different types of data flow:

![Flusso di dati dell'associazione dati](./media/data-binding-overview/databinding-dataflow.png "DataBinding_DataFlow")

- <xref:System.Windows.Data.BindingMode.OneWay>L'associazione fa sì che le modifiche alla proprietà di origine aggiornino automaticamente la proprietà di destinazione, ma le modifiche alla proprietà di destinazione non vengono propagate alla proprietà di origine. Questo tipo di binding è appropriato se il controllo da associare è implicitamente di sola lettura. Ad esempio, è possibile eseguire l'associazione a un'origine, ad esempio un ticker azionario o forse la proprietà di destinazione non dispone di alcuna interfaccia di controllo fornita per apportare modifiche, ad esempio un colore di sfondo con associazione a dati di una tabella. Se non è necessario monitorare le modifiche delle proprietà di destinazione, l'uso della modalità di associazione <xref:System.Windows.Data.BindingMode.OneWay> consente di evitare il sovraccarico della modalità di binding <xref:System.Windows.Data.BindingMode.TwoWay>.

- <xref:System.Windows.Data.BindingMode.TwoWay>L'associazione fa sì che le modifiche alla proprietà di origine o alla proprietà di destinazione aggiornino automaticamente l'altra. Questo tipo di associazione è appropriato per i moduli modificabili o altri scenari dell'interfaccia utente completamente interattivi. La maggior <xref:System.Windows.Data.BindingMode.OneWay> parte delle proprietà per impostazione predefinita per l'associazione, <xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType> ma alcune proprietà di <xref:System.Windows.Data.BindingMode.TwoWay> dipendenza (in genere le proprietà dei controlli modificabili dall'utente, ad esempio il e [CheckBox.IsChecked](xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked) predefinito per l'associazione. Un modo a livello di codice per determinare se una proprietà di dipendenza viene associata unidirezionale o bidirezionale per impostazione predefinita consiste nell'ottenere i metadati della proprietà con <xref:System.Windows.DependencyProperty.GetMetadata%2A?displayProperty=nameWithType> e quindi controllare il valore booleano della <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A?displayProperty=nameWithType> proprietà.

- <xref:System.Windows.Data.BindingMode.OneWayToSource>è il <xref:System.Windows.Data.BindingMode.OneWay> contrario dell'associazione; aggiorna la proprietà di origine quando la proprietà di destinazione viene modificata. Uno scenario di esempio è se è necessario rivalutare solo il valore di origine dall'interfaccia utente.

- Non illustrato nella <xref:System.Windows.Data.BindingMode.OneTime> figura è l'associazione, che fa sì che la proprietà di origine per inizializzare la proprietà di destinazione, ma non propagare le modifiche successive. Se il contesto dati cambia o l'oggetto nel contesto dati viene modificato, la modifica *non* viene riflessa nella proprietà di destinazione. Questo tipo di associazione è appropriato se uno snapshot dello stato corrente è appropriato o se i dati sono veramente statici. Questo tipo di binding è utile anche se si vuole inizializzare la proprietà di destinazione con un valore ricavato da una proprietà di origine e il contesto dei dati non è noto in anticipo. Questa modalità è essenzialmente <xref:System.Windows.Data.BindingMode.OneWay> una forma più semplice di associazione che fornisce prestazioni migliori nei casi in cui il valore di origine non viene modificato.

Per rilevare le <xref:System.Windows.Data.BindingMode.OneWay> modifiche <xref:System.Windows.Data.BindingMode.TwoWay> di origine (applicabili a e associazioni), <xref:System.ComponentModel.INotifyPropertyChanged>l'origine deve implementare un meccanismo di notifica di modifica delle proprietà adatto, ad esempio . Vedere [Procedura: implementare la notifica](../../framework/wpf/data/how-to-implement-property-change-notification.md) di <xref:System.ComponentModel.INotifyPropertyChanged> modifica delle proprietà per un esempio di un'implementazione.

La <xref:System.Windows.Data.Binding.Mode?displayProperty=nameWithType> proprietà fornisce ulteriori informazioni sulle modalità di associazione e un esempio di come specificare la direzione di un'associazione.

### <a name="what-triggers-source-updates"></a>Elementi che attivano gli aggiornamenti dell'origineWhat triggers source updates

Associazioni che <xref:System.Windows.Data.BindingMode.TwoWay> sono <xref:System.Windows.Data.BindingMode.OneWayToSource> o ascoltano le modifiche nella proprietà di destinazione e le propagano nuovamente all'origine, nota come aggiornamento dell'origine. Può accadere ad esempio che si modifichi il testo di un oggetto TextBox per modificare il valore di origine sottostante.

Tuttavia, il valore di origine viene aggiornato durante la modifica del testo o dopo aver completato la modifica del testo e il controllo perde lo stato attivo? La <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> proprietà determina ciò che attiva l'aggiornamento dell'origine. I punti delle frecce a destra nella figura seguente <xref:System.Windows.Data.Binding.UpdateSourceTrigger?displayProperty=nameWithType> illustrano il ruolo della proprietà.

![Diagramma che mostra il ruolo della proprietà UpdateSourceTrigger.](./media/data-binding-overview/data-binding-updatesource-trigger.png)

Se `UpdateSourceTrigger` il <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged?displayProperty=nameWithType>valore è , il valore a <xref:System.Windows.Data.BindingMode.TwoWay> cui <xref:System.Windows.Data.BindingMode.OneWayToSource> fa riferimento la freccia destra o le associazioni vengono aggiornati non appena la proprietà di destinazione viene modificata. Tuttavia, `UpdateSourceTrigger` se <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>il valore è , tale valore viene aggiornato solo con il nuovo valore quando la proprietà di destinazione perde lo stato attivo.

Analogamente <xref:System.Windows.Data.Binding.Mode%2A> alla proprietà, proprietà di <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> dipendenza diverse hanno valori predefiniti diversi. Il valore predefinito per la maggior parte delle proprietà di dipendenza è <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>, mentre la proprietà `TextBox.Text` ha il valore predefinito <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. `PropertyChanged`significa che gli aggiornamenti di origine in genere si verificano ogni volta che la proprietà di destinazione viene modificata. Le modifiche istantanee vanno bene per le caselle di controllo e altri controlli semplici. Tuttavia, per i campi di testo, l'aggiornamento dopo ogni pressione di tasto può ridurre le prestazioni e nega all'utente la solita opportunità di backspace e correggere gli errori di digitazione prima di eseguire il commit del nuovo valore.

Vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> la pagina delle proprietà per informazioni su come trovare il valore predefinito di una proprietà di dipendenza.

Nella tabella seguente viene fornito <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> uno <xref:System.Windows.Controls.TextBox> scenario di esempio per ogni valore usando l'oggetto come esempio.

| Valore di UpdateSourceTrigger | Quando il valore di origine viene aggiornato | Scenario di esempio per TextBoxExample scenario for TextBox |
| ------------------------- | ---------------------------------- | ---------------------------- |
| `LostFocus`(impostazione <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>predefinita per ) | Quando il TextBox controllo perde lo stato attivo. | Oggetto TextBox associato alla logica di convalida (vedere [Convalida dei dati](#data-validation) di seguito). |
| `PropertyChanged` | Durante la digitazione nel <xref:System.Windows.Controls.TextBox>file . | Controlli TextBox in una finestra della chat room. |
| `Explicit` | Quando l'app chiama <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>. | Controlli TextBox in un modulo modificabile (aggiorna i valori di origine solo quando l'utente fa clic sul pulsante di invio). |

Per un esempio, vedere [Procedura: controllare quando il testo TextBox aggiorna l'origine](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).

## <a name="creating-a-binding"></a>Creazione di un'associazioneCreating a binding

Per riformulare alcuni dei concetti illustrati nelle sezioni precedenti, si stabilisce un'associazione usando l'oggetto <xref:System.Windows.Data.Binding> e ogni associazione include in genere quattro componenti: una destinazione di associazione, una proprietà di destinazione, un'origine di associazione e un percorso al valore di origine da utilizzare. Questa sezione illustra come impostare un binding.

Si consideri l'esempio seguente, in cui l'oggetto origine del binding è una classe denominata *MyData* definita nello spazio dei nomi *SDKSample*. A scopo dimostrativo, *MyData* ha una proprietà stringa denominata *ColorName* il cui valore è impostato su "Red". L'esempio genera quindi un pulsante con uno sfondo rosso.

[!code-xaml[BindNonTextProperty](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColor)]

Per ulteriori informazioni sulla sintassi della dichiarazione di associazione ed esempi su come impostare un'associazione nel codice, vedere [Cenni preliminari](../../framework/wpf/data/binding-declarations-overview.md)sulle dichiarazioni di associazione .

Se si applica questo esempio al diagramma di base, la figura risultante sarà simile alla seguente. Questa figura descrive <xref:System.Windows.Data.BindingMode.OneWay> un'associazione perché <xref:System.Windows.Data.BindingMode.OneWay> il Background proprietà supporta l'associazione per impostazione predefinita.

![Diagramma che mostra la proprietà Background di associazione dati.](./media/data-binding-overview/data-binding-button-background-example.png)

Ci si potrebbe chiedere perché questa associazione funziona anche <xref:System.Windows.Controls.Control.Background%2A> se il <xref:System.Windows.Media.Brush> *ColorName* proprietà è di tipo string mentre la proprietà è di tipo . Questa associazione usa la conversione dei tipi predefinita, descritta nella sezione [Conversione dati.](#data-conversion)

### <a name="specifying-the-binding-source"></a>Specifica dell'origine dell'associazioneSpecifying the binding source

Si noti che nell'esempio precedente, l'origine dell'associazione viene specificata impostando il [DockPanel.DataContext](xref:System.Windows.FrameworkElement.DataContext) proprietà. Il <xref:System.Windows.Controls.Button> quindi eredita <xref:System.Windows.FrameworkElement.DataContext%2A> il <xref:System.Windows.Controls.DockPanel>valore da , che è l'elemento padre. Come già detto, l'oggetto origine del binding è uno dei quattro componenti necessari di un binding. Se quindi non si specifica l'oggetto origine del binding, questa non viene creata.

Esistono diversi modi per specificare l'oggetto origine del binding. L'utilizzo della <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà su un elemento padre è utile quando si associano più proprietà alla stessa origine. In alcuni casi, tuttavia, è preferibile specificare l'origine del binding in singole dichiarazioni di binding. Per l'esempio precedente, <xref:System.Windows.FrameworkElement.DataContext%2A> anziché utilizzare la proprietà , <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> è possibile specificare l'origine dell'associazione impostando la proprietà direttamente nella dichiarazione di associazione del pulsante, come nell'esempio seguente.

[!code-xaml[BindNonTextPropertyCompactBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/AutoConvertPropertyToColor.xaml#BindAutoConvertColorCompactBinding)]

Oltre a <xref:System.Windows.FrameworkElement.DataContext%2A> impostare direttamente la proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> su un elemento, ereditando il valore da un predecessore (ad <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> esempio il pulsante nel primo esempio) e specificando <xref:System.Windows.Data.Binding.ElementName?displayProperty=nameWithType> in modo <xref:System.Windows.Data.Binding.RelativeSource?displayProperty=nameWithType> esplicito l'origine dell'associazione impostando la proprietà nell'associazione (ad esempio il pulsante nell'ultimo esempio), è anche possibile usare la proprietà o la proprietà per specificare l'origine dell'associazione. La <xref:System.Windows.Data.Binding.ElementName%2A> proprietà è utile quando si esegue l'associazione ad altri elementi dell'app, ad esempio quando si usa un dispositivo di scorrimento per regolare la larghezza di un pulsante. La <xref:System.Windows.Data.Binding.RelativeSource%2A> proprietà è utile quando l'associazione è specificata in un <xref:System.Windows.Controls.ControlTemplate> oggetto o in un <xref:System.Windows.Style>oggetto . Per ulteriori informazioni, vedere [Procedura: specificare l'origine dell'associazione](../../framework/wpf/data/how-to-specify-the-binding-source.md).

### <a name="specifying-the-path-to-the-value"></a>Specifica del percorso del valore

Se l'origine dell'associazione <xref:System.Windows.Data.Binding.Path?displayProperty=nameWithType> è un oggetto, utilizzare la proprietà per specificare il valore da utilizzare per l'associazione. Se si esegue l'associazione <xref:System.Windows.Data.Binding.XPath?displayProperty=nameWithType> a dati XML, utilizzare la proprietà per specificare il valore. In alcuni casi, può essere <xref:System.Windows.Data.Binding.Path%2A> applicabile per utilizzare la proprietà anche quando i dati sono XML. Ad esempio, se si desidera accedere al Name proprietà di un restituito XmlNode (come <xref:System.Windows.Data.Binding.Path%2A> risultato di <xref:System.Windows.Data.Binding.XPath%2A> una query XPath), è necessario utilizzare la proprietà oltre alla proprietà.

Per ulteriori informazioni, <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Data.Binding.XPath%2A> vedere le proprietà e .

Anche se abbiamo sottolineato <xref:System.Windows.Data.Binding.Path%2A> che il per il valore da utilizzare è uno dei quattro componenti necessari di un'associazione, negli scenari che si desidera associare a un intero oggetto, il valore da utilizzare sarebbe lo stesso dell'oggetto di origine dell'associazione. In questi casi, è applicabile <xref:System.Windows.Data.Binding.Path%2A>a non specificare un file . Si consideri l'esempio seguente.

[!code-xaml[EmptyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/EmptyBinding.xaml#EmptyBinding)]

L'esempio precedente usa la sintassi di binding vuota: {Binding}. In questo caso, eredita <xref:System.Windows.Controls.ListBox> il DataContext da un elemento DockPanel padre (non illustrato in questo esempio). Quando il percorso non viene specificato, per impostazione predefinita si esegue un binding all'intero oggetto. In altre parole, in questo esempio, il percorso è <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> stato tralasciato perché la proprietà viene riuneta all'intero oggetto. Per una discussione approfondita, vedere la sezione [Associazione alle raccolte.](#binding-to-collections)

Oltre al binding a una raccolta, questo scenario è utile anche in caso di binding a un intero oggetto anziché a una singola proprietà di un oggetto. Ad esempio, se l'oggetto <xref:System.String>di origine è di tipo , è possibile semplicemente eseguire l'associazione alla stringa stessa. Un altro scenario comune riguarda il binding di un elemento a un oggetto con numerose proprietà.

Potrebbe essere necessario applicare la logica personalizzata in modo che i dati sono significativi per la proprietà di destinazione associata. La logica personalizzata può essere sotto forma di un convertitore personalizzato se la conversione del tipo predefinito non esiste. Vedere [Conversione dei dati](#data-conversion) per informazioni sui convertitori.

### <a name="binding-and-bindingexpression"></a>Binding e BindingExpression

Prima di accedere ad altre funzionalità e utilizzi dell'associazione dati, è utile introdurre la <xref:System.Windows.Data.BindingExpression> classe . Come si è visto nelle <xref:System.Windows.Data.Binding> sezioni precedenti, la classe è la classe di alto livello per la dichiarazione di un'associazione; fornisce molte proprietà che consentono di specificare le caratteristiche di un'associazione. Una classe <xref:System.Windows.Data.BindingExpression>correlata, , è l'oggetto sottostante che mantiene la connessione tra l'origine e la destinazione. Un binding contiene tutte le informazioni condivisibili tra diverse espressioni di binding. Un <xref:System.Windows.Data.BindingExpression> è un'espressione di istanza che non può <xref:System.Windows.Data.Binding>essere condivisa e contiene tutte le informazioni sull'istanza dell'oggetto .

Si consideri l'esempio seguente, `myDataObject` where è un'istanza della `MyData` classe, `myBinding` è l'oggetto di origine <xref:System.Windows.Data.Binding> ed `MyData` è una classe definita che contiene una proprietà stringa denominata `MyDataProperty`. In questo esempio il `myText`contenuto di <xref:System.Windows.Controls.TextBlock>testo `MyDataProperty`di , un'istanza di , viene associato a .

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ManualBinding.cs#CodeOnlyBinding)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ManualBinding.vb#CodeOnlyBinding)]

È possibile usare lo stesso oggetto *myBinding* per creare altri binding. Ad esempio, è possibile utilizzare l'oggetto *myBinding* per associare il contenuto di testo di una casella di controllo a *MyDataProperty*. In questo scenario, ci saranno <xref:System.Windows.Data.BindingExpression> due istanze di condivisione del *myBinding* oggetto.

Un <xref:System.Windows.Data.BindingExpression> oggetto viene restituito <xref:System.Windows.Data.BindingOperations.GetBindingExpression%2A> chiamando su un oggetto con associazione a dati. Gli articoli seguenti illustrano alcuni <xref:System.Windows.Data.BindingExpression> degli utilizzi della classe:

- [Ottenere l'oggetto di binding da una proprietà di destinazione associata](../../framework/wpf/data/how-to-get-the-binding-object-from-a-bound-target-property.md)

- [Controllo quando il testo TextBox aggiorna l'origine](../../framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)

## <a name="data-conversion"></a>Conversione di dati

Nella [sezione Creazione di un'associazione,](#creating-a-binding) il pulsante è rosso perché la relativa <xref:System.Windows.Controls.Control.Background%2A> proprietà è associata a una proprietà stringa con il valore "Red". Questo valore stringa funziona perché un <xref:System.Windows.Media.Brush> convertitore di tipi è <xref:System.Windows.Media.Brush>presente nel tipo per convertire il valore stringa in un oggetto .

Aggiunta di queste informazioni alla figura la [creazione di un'associazione](#creating-a-binding) sezione è simile al seguente.

![Diagramma che mostra la proprietà Default di associazione dati.](./media/data-binding-overview/data-binding-button-default-conversion.png)

Tuttavia, cosa succede se invece di avere una *Color* proprietà di <xref:System.Windows.Media.Color>tipo stringa l'oggetto di origine dell'associazione ha un Color proprietà di tipo ? In tal caso, affinché l'associazione funzioni è *Color* necessario innanzitutto trasformare <xref:System.Windows.Controls.Control.Background%2A> il Color valore della proprietà in un elemento che la proprietà accetta. È necessario creare un convertitore <xref:System.Windows.Data.IValueConverter> personalizzato implementando l'interfaccia , come nell'esempio seguente.

[!code-csharp[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/ColorBrushConverter.cs#ColorBrushConverter)]
[!code-vb[CodeOnlyBinding](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/ColorBrushConverter.vb#ColorBrushConverter)]

Per altre informazioni, vedere <xref:System.Windows.Data.IValueConverter>.

Ora viene utilizzato il convertitore personalizzato anziché la conversione predefinita e il diagramma è simile al seguente.

![Diagramma che mostra il convertitore personalizzato di associazione dati.](./media/data-binding-overview/data-binding-converter-color-example.png)

Come già detto, le conversioni predefinite possono essere disponibili o meno a seconda dei convertitori presenti nel tipo a cui si esegue il binding. Questo comportamento dipenderà dai convertitori di tipi disponibili nella destinazione. In caso di dubbio, creare un convertitore personalizzato.

Di seguito sono riportati alcuni scenari tipici in cui è opportuno implementare un convertitore di dati:The following are some typical scenarios where it makes sense to implement a data converter:

- I dati devono essere visualizzati in modo diverso, a seconda delle impostazioni cultura. Ad esempio, è possibile implementare un convertitore di valuta o un convertitore di data/ora del calendario in base alle convenzioni utilizzate in determinate impostazioni cultura.

- I dati usati non devono necessariamente modificare il valore di testo di una proprietà quanto piuttosto altri valori, ad esempio l'origine di un'immagine oppure il colore o lo stile del testo visualizzato. I convertitori possono essere usati in questo caso per convertire il binding di una proprietà considerata poco appropriata, ad esempio il binding di un campo di testo alla proprietà Background della cella di una tabella.

- Più di un controllo o più proprietà dei controlli sono associati agli stessi dati. In questo caso, il binding primario potrebbe semplicemente visualizzare il testo, mentre gli altri binding gestiscono problemi di visualizzazione specifici, usando comunque lo stesso binding come informazione di origine.

- Una proprietà di destinazione dispone di una <xref:System.Windows.Data.MultiBinding>raccolta di associazioni, che viene definita . Per <xref:System.Windows.Data.MultiBinding>, si <xref:System.Windows.Data.IMultiValueConverter> utilizza un oggetto personalizzato per produrre un valore finale dai valori delle associazioni. È possibile ad esempio calcolare il colore dai valori rosso, blu e verde, ovvero valori che possono provenire da oggetti origine del binding identici o diversi. Vedere <xref:System.Windows.Data.MultiBinding> per esempi e informazioni.

## <a name="binding-to-collections"></a>Associazione alle raccolteBinding to collections

Un oggetto origine di associazione può essere considerato come un singolo oggetto le cui proprietà contengono dati o come una raccolta di dati di oggetti polimorfici spesso raggruppati (ad esempio il risultato di una query in un database). Finora abbiamo discusso solo l'associazione a singoli oggetti. Tuttavia, l'associazione a una raccolta dati è uno scenario comune. Ad esempio, uno scenario comune <xref:System.Windows.Controls.ItemsControl> consiste <xref:System.Windows.Controls.ListBox>nell'utilizzare un esempio, ad esempio <xref:System.Windows.Controls.ListView>, o <xref:System.Windows.Controls.TreeView> per visualizzare una raccolta di dati, ad esempio nell'app illustrata nella sezione Che [cos'è l'associazione dati.](#what-is-data-binding)

Anche in questo caso è possibile applicare il diagramma di base. Se si associa <xref:System.Windows.Controls.ItemsControl> un a una raccolta, il diagramma è simile al seguente.

![Diagramma che mostra l'oggetto ItemsControl di associazione dati.](./media/data-binding-overview/data-binding-itemscontrol.png)

Come illustrato in questo diagramma, per associare un <xref:System.Windows.Controls.ItemsControl> oggetto raccolta, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A?displayProperty=nameWithType> proprietà è la proprietà da utilizzare. Si può `ItemsSource` pensare come il <xref:System.Windows.Controls.ItemsControl>contenuto del . L'associazione <xref:System.Windows.Data.BindingMode.OneWay> `ItemsSource` è perché `OneWay` la proprietà supporta l'associazione per impostazione predefinita.

### <a name="how-to-implement-collections"></a>Come implementare le raccolte

È possibile enumerare su <xref:System.Collections.IEnumerable> qualsiasi raccolta che implementa l'interfaccia. Tuttavia, per impostare le associazioni dinamiche in modo che gli inserimenti o <xref:System.Collections.Specialized.INotifyCollectionChanged> le eliminazioni nella raccolta aggiornino automaticamente l'interfaccia utente, la raccolta deve implementare l'interfaccia. Questa interfaccia espone un evento che deve essere generato a ogni modifica della raccolta sottostante.

WPFWPF <xref:System.Collections.ObjectModel.ObservableCollection%601> fornisce la classe , che è un'implementazione <xref:System.Collections.Specialized.INotifyCollectionChanged> incorporata di una raccolta di dati che espone l'interfaccia. Per supportare completamente il trasferimento di valori di dati da oggetti di origine a <xref:System.ComponentModel.INotifyPropertyChanged> destinazioni, ogni oggetto nella raccolta che supporta le proprietà associabili deve implementare anche l'interfaccia. Per ulteriori informazioni, vedere Panoramica delle origini di [associazione.](../../framework/wpf/data/binding-sources-overview.md)

Prima di implementare un <xref:System.Collections.ObjectModel.ObservableCollection%601> insieme personalizzato, è consigliabile <xref:System.Collections.Generic.List%601> <xref:System.Collections.ObjectModel.Collection%601>utilizzare <xref:System.ComponentModel.BindingList%601>o una delle classi di raccolte esistenti, ad esempio , e , tra le altre. Se si dispone di uno scenario avanzato e <xref:System.Collections.IList>si desidera implementare un insieme personalizzato, è consigliabile utilizzare , che fornisce una raccolta non generica di oggetti a cui l'indice può accedere singolarmente e che fornisce pertanto le prestazioni migliori.

### <a name="collection-views"></a>Visualizzazioni raccolta

Una <xref:System.Windows.Controls.ItemsControl> volta che è associato a una raccolta di dati, è possibile ordinare, filtrare o raggruppare i dati. A tale scopo, utilizzare le visualizzazioni di <xref:System.ComponentModel.ICollectionView> raccolta, ovvero le classi che implementano l'interfaccia.

#### <a name="what-are-collection-views"></a>Che cosa sono le visualizzazioni di raccolta?

Una visualizzazione di raccolta rappresenta il livello superiore di una raccolta di origine di binding che consente di esplorare e visualizzare la raccolta di origine in base a query di ordinamento, filtro e raggruppamento, il tutto senza modificare la raccolta di origine sottostante. Una visualizzazione di raccolta mantiene inoltre un puntatore all'elemento corrente nella raccolta. Se la raccolta <xref:System.Collections.Specialized.INotifyCollectionChanged> di origine implementa l'interfaccia, le modifiche generate dall'evento <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged> vengono propagate alle visualizzazioni.

Poiché le visualizzazioni non modificano le raccolte di origine sottostanti, ogni raccolta di origine può avere più visualizzazioni associate. Si consideri ad esempio una raccolta di oggetti *Task*. Grazie alle visualizzazioni è possibile visualizzare gli stessi dati in modi diversi. È possibile ad esempio visualizzare le attività ordinate in base alla priorità nella parte sinistra della pagina e, contemporaneamente nella parte destra, visualizzare le stesse attività raggruppate in base all'area.

#### <a name="how-to-create-a-view"></a>Come creare una visualizzazione

Per creare e usare una visualizzazione, è possibile creare direttamente un'istanza dell'oggetto visualizzazione e usare tale istanza come origine del binding. Si consideri, ad esempio, l'app [dimostrativa per l'associazione dati][data-binding-demo] nella sezione [Che cos'è l'associazione dati.](#what-is-data-binding) L'app viene implementata in modo che l'associazione <xref:System.Windows.Controls.ListBox> a una visualizzazione sulla raccolta dati anziché direttamente la raccolta dati. L'esempio seguente viene estratto dall'app [demo di associazione dati.][data-binding-demo] La <xref:System.Windows.Data.CollectionViewSource> classe è il proxy XAML di <xref:System.Windows.Data.CollectionView>una classe che eredita da . In questo particolare <xref:System.Windows.Data.CollectionViewSource.Source%2A> esempio, l'oggetto della visualizzazione è <xref:System.Collections.ObjectModel.ObservableCollection%601>associato all'insieme *AuctionItems* (di tipo ) dell'oggetto app corrente.

[!code-xaml[CollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#CollectionView)]

La risorsa *listingDataView* funge quindi da origine di associazione <xref:System.Windows.Controls.ListBox>per gli elementi nell'app, ad esempio il file .

[!code-xaml[ListBoxCollectionView](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxCollectionView)]

Per creare un'altra visualizzazione per la <xref:System.Windows.Data.CollectionViewSource> stessa raccolta, `x:Key` è possibile creare un'altra istanza e assegnarle un nome diverso.

Nella tabella seguente vengono illustrati i tipi di dati <xref:System.Windows.Data.CollectionViewSource> della visualizzazione creati come visualizzazione di raccolta predefinita o in base al tipo di raccolta di origine.

| Tipo di raccolta di origine                    | Tipo di visualizzazione di raccolta | Note |
| ----------------------------------------- | -------------------- | ----- |
| <xref:System.Collections.IEnumerable>     | Un tipo interno basato su<xref:System.Windows.Data.CollectionView> | Non è possibile raggruppare gli elementi. |
| <xref:System.Collections.IList>           | <xref:System.Windows.Data.ListCollectionView> | Il più veloce. |
| <xref:System.ComponentModel.IBindingList> | <xref:System.Windows.Data.BindingListCollectionView> | |

#### <a name="using-a-default-view"></a>Utilizzo di una visualizzazione predefinita

Specificare una visualizzazione di raccolta come origine di binding rappresenta un modo per creare e usare una visualizzazione di raccolta. WPF crea inoltre una visualizzazione di raccolta predefinita per ogni raccolta usata come origine di binding. Se si esegue il binding direttamente a una raccolta, WPF esegue il binding alla relativa visualizzazione predefinita. Questa visualizzazione predefinita è condivisa da tutte le associazioni alla stessa raccolta, pertanto una modifica apportata a una visualizzazione predefinita da un controllo associato o codice (ad esempio l'ordinamento o una modifica al puntatore dell'elemento corrente, illustrato più avanti) si riflette in tutte le altre associazioni alla stessa raccolta.

Per ottenere la visualizzazione predefinita, utilizzare il <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> metodo . Per un esempio, vedere [Ottenere la visualizzazione predefinita di una raccolta dati.](../../framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)

#### <a name="collection-views-with-adonet-datatables"></a>Visualizzazioni di raccolta con ADO.NET DataTable

Per migliorare le prestazioni, <xref:System.Data.DataTable> <xref:System.Data.DataView> le visualizzazioni di <xref:System.Data.DataView>raccolta per ADO.NET o gli oggetti delegano l'ordinamento e il filtro a , che determina la condivisione dell'ordinamento e del filtro tra tutte le visualizzazioni di raccolta dell'origine dati. Per consentire a ogni visualizzazione di raccolta di ordinare <xref:System.Data.DataView> e filtrare in modo indipendente, inizializzare ogni visualizzazione della raccolta con il proprio oggetto.

#### <a name="sorting"></a>Ordinamento

Come detto in precedenza, le visualizzazioni possono applicare un ordinamento a una raccolta. Poiché esistono nella raccolta sottostante, i dati possono avere o non avere un ordine intrinseco. La visualizzazione della raccolta consente di imporre un ordine o di modificare l'ordine predefinito in base ai criteri di confronto che si forniscono. Trattandosi di una visualizzazione dei dati basata su client, uno scenario comune prevede che l'utente possa ordinare le colonne di dati tabulari in base al valore al quale corrisponde la colonna. Grazie alle visualizzazioni, è possibile applicare questo ordinamento gestito dall'utente senza apportare alcuna modifica alla raccolta sottostante né dover ripetere la query nel contenuto della raccolta. Per un esempio, vedere [Ordinare una colonna GridView quando si fa clic su un'intestazione](../../framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).

L'esempio seguente mostra la logica di ordinamento <xref:System.Windows.Controls.CheckBox> di "Ordina per categoria e data" dell'interfaccia utente dell'app nella sezione [Che cos'è l'associazione dati.](#what-is-data-binding)

[!code-csharp[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#AddSortChecked)]
[!code-vb[AddSortChecked](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#AddSortChecked)]

#### <a name="filtering"></a>Filtri

Le visualizzazioni possono anche applicare un filtro a una raccolta, in modo che la visualizzazione mostri solo un determinato subset della raccolta completa. I dati possono essere filtrati in base a una condizione. Ad esempio, come avviene dall'app nella sezione [Che cos'è l'associazione dati,](#what-is-data-binding) la "Mostra solo occasioni" <xref:System.Windows.Controls.CheckBox> contiene la logica per filtrare gli elementi che costano 25 dollari o più. Il codice seguente viene eseguito per impostare <xref:System.Windows.Data.CollectionViewSource.Filter> *ShowOnlyBargainsFilter* come gestore eventi quando <xref:System.Windows.Controls.CheckBox> viene selezionato.

[!code-csharp[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingViewFilter)]
[!code-vb[ListingViewFilter](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingViewFilter)]

Il *ShowOnlyBargainsFilter* gestore dell'evento ha l'implementazione seguente.

[!code-csharp[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#FilterEvent)]
[!code-vb[FilterEvent](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#FilterEvent)]

Se si utilizza una <xref:System.Windows.Data.CollectionView> delle classi <xref:System.Windows.Data.CollectionViewSource>direttamente anziché <xref:System.Windows.Data.CollectionView.Filter%2A> , è necessario utilizzare la proprietà per specificare un callback. Per un esempio, vedere [Procedura: Filtrare i dati in una visualizzazione](../../framework/wpf/data/how-to-filter-data-in-a-view.md).

#### <a name="grouping"></a>Raggruppamento

Ad eccezione della classe <xref:System.Collections.IEnumerable> interna che visualizza una raccolta, tutte le visualizzazioni dell'insieme supportano il *raggruppamento*, che consente all'utente di partizionare la raccolta nella visualizzazione raccolta in gruppi logici. Se l'utente fornisce un elenco di gruppi, questi saranno espliciti. Se invece i gruppi vengono generati in modo dinamico in base ai dati, si avranno gruppi impliciti.

Nell'esempio seguente viene illustrata la <xref:System.Windows.Controls.CheckBox>logica del "Gruppo per categoria".

[!code-csharp[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml.cs#ListingGroupCheck)]
[!code-vb[ListingGroupCheck](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/CollectionView.xaml.vb#ListingGroupCheck)]

Per un altro esempio di raggruppamento, vedere [Procedura: Raggruppare gli elementi di un controllo ListView che implementa una GridView](../../framework/wpf/controls/how-to-group-items-in-a-listview-that-implements-a-gridview.md).

#### <a name="current-item-pointers"></a>Puntatori all'elemento corrente

Le visualizzazioni supportano anche la nozione di elemento corrente. In una visualizzazione di raccolta è possibile spostarsi da un oggetto all'altro. Durante lo spostamento viene spostato un puntatore dell'elemento che consente di recuperare l'oggetto presente in un percorso specifico nella raccolta. Per un esempio, vedere [Spostarsi tra gli oggetti in un oggetto CollectionView di dati.](../../framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md)

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

Il puntatore dell'elemento corrente può essere influenzato da un'operazione di ordinamento o filtro applicata alla raccolta. L'ordinamento mantiene il puntatore dell'elemento corrente sull'ultimo elemento selezionato, ma la visualizzazione di raccolta viene ristrutturata in base a tale elemento. (Forse l'elemento selezionato era all'inizio dell'elenco prima, ma ora l'elemento selezionato potrebbe essere da qualche parte nel mezzo.) Il filtro mantiene l'elemento selezionato se tale selezione rimane in visualizzazione dopo il filtro. Il puntatore dell'elemento corrente viene altrimenti impostato sul primo elemento della visualizzazione di raccolta filtrata.

#### <a name="master-detail-binding-scenario"></a>Scenario di associazione master-dettagli

La nozione di elemento corrente è utile non solo per l'esplorazione degli elementi in una raccolta, bensì anche per lo scenario di binding master-dettagli. Considera di nuovo l'interfaccia utente dell'app nella sezione [Che cos'è l'associazione dati.](#what-is-data-binding) In tale app, la <xref:System.Windows.Controls.ListBox> selezione all'interno <xref:System.Windows.Controls.ContentControl>di determina il contenuto visualizzato nel file . Per dirla in un <xref:System.Windows.Controls.ListBox> altro modo, <xref:System.Windows.Controls.ContentControl> quando viene selezionato un elemento, mostra i dettagli dell'elemento selezionato.

Per implementare lo scenario master-dettagli, occorre semplicemente avere due o più controlli associati alla stessa visualizzazione. L'esempio seguente della [demo dell'associazione dati][data-binding-demo] mostra il markup dell'interfaccia <xref:System.Windows.Controls.ListBox> utente dell'app e <xref:System.Windows.Controls.ContentControl> viene visualizzato nella sezione Che [cos'è l'associazione dati.](#what-is-data-binding)

[!code-xaml[ListBoxContentControl](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#ListBoxContentControl)]

Si noti che entrambi i controlli sono associati alla stessa origine, la risorsa statica *listingDataView* (vedere la definizione di questa risorsa nella [sezione Come creare una visualizzazione](#how-to-create-a-view)). Questa associazione funziona perché quando un <xref:System.Windows.Controls.ContentControl> singleton oggetto (il in questo caso) <xref:System.Windows.Data.CollectionView.CurrentItem%2A> è associato a una visualizzazione di raccolta, viene associato automaticamente alla visualizzazione. Gli <xref:System.Windows.Data.CollectionViewSource> oggetti sincronizzano automaticamente la valuta e la selezione. Se il controllo elenco non <xref:System.Windows.Data.CollectionViewSource> è associato a un oggetto come <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> in `true` questo esempio, è necessario impostare la relativa proprietà su per il funzionamento.

Per altri esempi, vedere [Associare a una raccolta e visualizzare le informazioni in base alla selezione](../../framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md) e Usare il modello [master-dettagli con dati gerarchici.](../../framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)

Come si può notare, l'esempio precedente usa un modello. Infatti, i dati non verrebbero visualizzati nel modo che desideriamo senza <xref:System.Windows.Controls.ContentControl> l'uso di modelli <xref:System.Windows.Controls.ListBox>(quello esplicitamente utilizzato da e quello implicitamente utilizzato dal ). Le sezione seguente illustra i modelli di dati.

## <a name="data-templating"></a>Modelli di dati

Senza l'uso dei modelli di dati, l'interfaccia utente dell'app nella sezione [Che cos'è l'associazione dati](#what-is-data-binding) sarà simile alla seguente.

![Data Binding Demo senza Data Templates](./media/data-binding-overview/demo-no-template.png)

Come illustrato nell'esempio nella sezione <xref:System.Windows.Controls.ListBox> precedente, <xref:System.Windows.Controls.ContentControl> sia il controllo che l'oggetto sono associati all'intero oggetto raccolta (o, più specificamente, alla visualizzazione sull'oggetto raccolta) di *AuctionItem*s. Senza istruzioni specifiche su come visualizzare <xref:System.Windows.Controls.ListBox> la raccolta dei dati, viene visualizzata <xref:System.Windows.Controls.ContentControl> la rappresentazione di stringa di ogni oggetto nella raccolta sottostante e la rappresentazione di stringa dell'oggetto a cui è associato.

Per risolvere questo problema, <xref:System.Windows.DataTemplate?text=DataTemplates>l'applicazione definisce . Come illustrato nell'esempio nella sezione <xref:System.Windows.Controls.ContentControl> precedente, il utilizzo esplicito del modello di dati *detailsProductListingTemplate.As* shown in the example in the previous section, the explicitly uses the detailsProductListingTemplate data template. Il <xref:System.Windows.Controls.ListBox> controllo utilizza in modo implicito il modello di dati seguente quando si visualizzano gli oggetti *AuctionItem* nella raccolta.

[!code-xaml[AuctionItemDataTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/CollectionView.xaml#AuctionItemDataTemplate)]

Con l'uso di questi due DataTemplates, l'interfaccia utente risultante è quella illustrata nella sezione [Che cos'è l'associazione dati.](#what-is-data-binding) Come si può vedere da quella schermata, oltre a consentire di inserire dati nei controlli, DataTemplates consentono di definire oggetti visivi accattivanti per i dati. Ad <xref:System.Windows.DataTrigger>esempio, s vengono <xref:System.Windows.DataTemplate> utilizzati nell'esempio precedente in modo che *AuctionItem*s con *valore SpecialFeatures* di *HighLight* venga visualizzato con un bordo arancione e una stella.

Per ulteriori informazioni sui modelli di dati, vedere [Panoramica](../../framework/wpf/data/data-templating-overview.md)dei modelli di dati .

## <a name="data-validation"></a>Convalida dei dati

La maggior parte delle app che accettano l'input dell'utente devono disporre della logica di convalida per garantire che l'utente abbia immesso le informazioni previste. I controlli di convalida possono essere basati sul tipo, l'intervallo, il formato o altri requisiti specifici dell'app. In questa sezione viene illustrato il funzionamento della convalida dei dati in WPFWPF.

### <a name="associating-validation-rules-with-a-binding"></a>Associazione di regole di convalida a un'associazione

Il modello di associazione <xref:System.Windows.Data.Binding.ValidationRules%2A> dati <xref:System.Windows.Data.Binding> WPFWPF consente di eseguire l'associazione all'oggetto. Ad esempio, l'esempio <xref:System.Windows.Controls.TextBox> seguente associa `StartPrice` a una <xref:System.Windows.Controls.ExceptionValidationRule> proprietà <xref:System.Windows.Data.Binding.ValidationRules%2A?displayProperty=nameWithType> denominata e aggiunge un oggetto alla proprietà.

[!code-xaml[TextboxStartPrice](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartPrice)]

Un <xref:System.Windows.Controls.ValidationRule> oggetto verifica se il valore di una proprietà è valido. WPFWPF dispone di due <xref:System.Windows.Controls.ValidationRule> tipi di oggetti predefiniti:WPFWPF has two types of built-in objects:

- Un <xref:System.Windows.Controls.ExceptionValidationRule> controllo verifica la presenza di eccezioni generate durante l'aggiornamento della proprietà dell'origine di associazione. Nell'esempio precedente `StartPrice` è di tipo intero. Quando l'utente immette un valore che non può essere convertito in un intero, viene generata un'eccezione e il binding viene contrassegnato come non valido. Una sintassi alternativa <xref:System.Windows.Controls.ExceptionValidationRule> all'impostazione <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> esplicita di `true` consiste nell'impostare la proprietà su <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.MultiBinding> sull'oggetto .

- Un <xref:System.Windows.Controls.DataErrorValidationRule> oggetto verifica la presenza di errori <xref:System.ComponentModel.IDataErrorInfo> generati da oggetti che implementano l'interfaccia. Per un esempio di utilizzo <xref:System.Windows.Controls.DataErrorValidationRule>di questa regola di convalida, vedere . Una sintassi alternativa <xref:System.Windows.Controls.DataErrorValidationRule> all'impostazione <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> esplicita di `true` consiste nell'impostare la proprietà su <xref:System.Windows.Data.Binding> o <xref:System.Windows.Data.MultiBinding> sull'oggetto .

È inoltre possibile creare una regola di <xref:System.Windows.Controls.ValidationRule> convalida personalizzata derivandola dalla classe e implementando il <xref:System.Windows.Controls.ValidationRule.Validate%2A> metodo. Nell'esempio seguente viene illustrata la regola utilizzata <xref:System.Windows.Controls.TextBox> dalla sezione Aggiungi elenco *prodotti* "Data di inizio" dalla sezione Che [cos'è l'associazione dati.](#what-is-data-binding)

[!code-csharp[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/FutureDateRule.cs#FutureDateRule)]
[!code-vb[FutureDateRule](~/samples/snippets/desktop-guide/wpf/data-binding-overview/vb/FutureDateRule.vb#FutureDateRule)]

*StartDateEntryForm* <xref:System.Windows.Controls.TextBox> utilizza *FutureDateRule*, come illustrato nell'esempio seguente.

[!code-xaml[TextboxStartDate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextboxStartDate)]

Poiché <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> il <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>valore è , il motore di associazione aggiorna il valore <xref:System.Windows.Data.Binding.ValidationRules%2A> di origine a ogni sequenza di tasti, il che significa che controlla anche ogni regola nell'insieme a ogni sequenza di tasti. L'argomento verrà ulteriormente trattato nella sezione Processo di convalida.

### <a name="providing-visual-feedback"></a>Fornire feedback visivo

Se l'utente immette un valore non valido, è possibile fornire un feedback sull'errore nell'interfaccia utente dell'app. Un modo per fornire tale <xref:System.Windows.Controls.Validation.ErrorTemplate%2A?displayProperty=nameWithType> feedback consiste nell'impostare la proprietà associata su un oggetto personalizzato <xref:System.Windows.Controls.ControlTemplate>. Come illustrato nella sottosezione precedente, *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> utilizza un <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> oggetto *validationTemplate*denominato . Nell'esempio seguente viene illustrata la definizione di *validationTemplate*.

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#ControlTemplate)]

L'elemento <xref:System.Windows.Controls.AdornedElementPlaceholder> specifica dove deve essere posizionato il controllo da aggiungere.

Inoltre, è anche possibile <xref:System.Windows.Controls.ToolTip> utilizzare un per visualizzare il messaggio di errore. *StartDateEntryForm* e *StartPriceEntryForm*<xref:System.Windows.Controls.TextBox>utilizzano lo stile *textStyleTextBox*, <xref:System.Windows.Controls.ToolTip> che crea un che visualizza il messaggio di errore. L'esempio seguente illustra la definizione di *textStyleTextBox*. La proprietà <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> associata si verifica `true` quando una o più associazioni sulle proprietà dell'elemento associato sono in errore.

[!code-xaml[TextBoxStyle](~/samples/snippets/desktop-guide/wpf/data-binding-overview/csharp/DataValidation.xaml#TextBoxStyle)]

Con <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> l'aspetto <xref:System.Windows.Controls.ToolTip>personalizzato e l'oggetto , *StartDateEntryForm* <xref:System.Windows.Controls.TextBox> è simile al seguente quando si verifica un errore di convalida.

![Errore di convalida del data binding](./media/data-binding-overview/demo-validation-date.png "DataBindingDemo_Validation")

Se <xref:System.Windows.Data.Binding> sono associate regole di convalida <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> ma non si specifica <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> un controllo associato, verrà utilizzato un valore predefinito per notificare agli utenti quando si verifica un errore di convalida. L'impostazione predefinita <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> è un modello di controllo che definisce un bordo rosso nel livello dello strumento decorativo visuale. Con il <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> valore <xref:System.Windows.Controls.ToolTip>predefinito e l'interfaccia utente di *StartPriceEntryForm* <xref:System.Windows.Controls.TextBox> è simile al seguente quando si verifica un errore di convalida.

![Errore di convalida del data binding](./media/data-binding-overview/demo-validation-price.png "DataBindingDemo_ValidationDefault")

Per un esempio di come fornire la logica per convalidare tutti i controlli in una finestra di dialogo, vedere la sezione Finestre di dialogo personalizzate in [Panoramica delle finestre di dialogo](../../framework/wpf/app-development/dialog-boxes-overview.md).

### <a name="validation-process"></a>Processo di convalida

La convalida avviene solitamente quando si trasferisce un valore di destinazione alla proprietà di origine del binding. Questo trasferimento <xref:System.Windows.Data.BindingMode.TwoWay> avviene e <xref:System.Windows.Data.BindingMode.OneWayToSource> i binding. Per ribadire, ciò che causa un <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> aggiornamento di origine dipende dal valore della proprietà, come descritto nella sezione [Che cosa attiva](#what-triggers-source-updates) gli aggiornamenti di origine .

Negli elementi seguenti viene descritto il processo di *convalida.* Se si verifica un errore di convalida o un altro tipo di errore in qualsiasi momento durante questo processo, il processo viene interrotto:

1. Il motore di associazione <xref:System.Windows.Controls.ValidationRule> controlla se <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> sono <xref:System.Windows.Controls.ValidationStep.RawProposedValue> presenti <xref:System.Windows.Data.Binding>oggetti personalizzati definiti di <xref:System.Windows.Controls.ValidationRule.Validate%2A> cui <xref:System.Windows.Controls.ValidationRule> è impostato su per tale , nel qual caso chiama il metodo su ciascuno di essi fino a quando uno di essi non si verifica un errore o fino a quando tutti non passano.

2. Il motore di binding chiama quindi il convertitore, se presente.

3. Se il convertitore ha esito positivo, <xref:System.Windows.Controls.ValidationRule> il motore <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> di <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> associazione <xref:System.Windows.Data.Binding>verifica se sono <xref:System.Windows.Controls.ValidationRule.Validate%2A> presenti oggetti <xref:System.Windows.Controls.ValidationRule> personalizzati <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> definiti <xref:System.Windows.Controls.ValidationStep.ConvertedProposedValue> il cui è impostato su tale , nel qual caso chiama il metodo su ognuno che è stato impostato su ogni che è stato impostato su fino a quando uno di essi si verifica un errore o finché non vengono passati tutti.

4. Il motore di binding imposta la proprietà di origine.

5. Il motore di associazione <xref:System.Windows.Controls.ValidationRule> controlla se <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> sono <xref:System.Windows.Controls.ValidationStep.UpdatedValue> presenti <xref:System.Windows.Data.Binding>oggetti personalizzati definiti di <xref:System.Windows.Controls.ValidationRule.Validate%2A> cui <xref:System.Windows.Controls.ValidationRule> è <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostato <xref:System.Windows.Controls.ValidationStep.UpdatedValue> su per tale , nel qual caso chiama il metodo su ognuno che è impostato su ogni che è impostato su fino a quando uno di essi si verifica un errore o fino a quando tutti passano. Se <xref:System.Windows.Controls.DataErrorValidationRule> un oggetto è associato <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> a un'associazione e la relativa impostazione è impostata sul valore predefinito, <xref:System.Windows.Controls.ValidationStep.UpdatedValue>, a questo punto viene selezionata la casella <xref:System.Windows.Controls.DataErrorValidationRule> di controllo. A questo punto viene <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> controllata `true` qualsiasi associazione con l'opzione impostata su.

6. Il motore di associazione <xref:System.Windows.Controls.ValidationRule> controlla se <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> sono <xref:System.Windows.Controls.ValidationStep.CommittedValue> presenti <xref:System.Windows.Data.Binding>oggetti personalizzati definiti di <xref:System.Windows.Controls.ValidationRule.Validate%2A> cui <xref:System.Windows.Controls.ValidationRule> è <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> impostato <xref:System.Windows.Controls.ValidationStep.CommittedValue> su per tale , nel qual caso chiama il metodo su ognuno che è impostato su ogni che è impostato su fino a quando uno di essi si verifica un errore o fino a quando tutti passano.

Se <xref:System.Windows.Controls.ValidationRule> un oggetto non passa in qualsiasi momento durante <xref:System.Windows.Controls.ValidationError> questo processo, <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> il motore di associazione crea un oggetto e lo aggiunge alla raccolta dell'elemento associato. Prima che il <xref:System.Windows.Controls.ValidationRule> motore di associazione esegua gli oggetti in un determinato passaggio, rimuove quello <xref:System.Windows.Controls.ValidationError> aggiunto alla proprietà <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> associata dell'elemento associato durante tale passaggio. Ad esempio, <xref:System.Windows.Controls.ValidationRule> se <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> un <xref:System.Windows.Controls.ValidationStep.UpdatedValue> oggetto cui è impostato su non riuscito, <xref:System.Windows.Controls.ValidationError> la volta successiva <xref:System.Windows.Controls.ValidationRule> che <xref:System.Windows.Controls.ValidationRule.ValidationStep%2A> si <xref:System.Windows.Controls.ValidationStep.UpdatedValue>verifica il processo di convalida, il motore di associazione rimuove immediatamente tale operazione prima di chiamare qualsiasi che è impostato su .

Quando <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> non è <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> vuota, la proprietà associata `true`dell'elemento è impostata su . Inoltre, se <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A> la <xref:System.Windows.Data.Binding> proprietà di `true`è impostata su <xref:System.Windows.Controls.Validation.Error?displayProperty=nameWithType> , il motore di associazione genera l'evento associato sull'elemento.

Si noti inoltre che un trasferimento di valore valido in entrambe le direzioni (destinazione all'origine o di origine alla destinazione) cancella la <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> proprietà associata.

Se all'associazione <xref:System.Windows.Controls.ExceptionValidationRule> è associato un <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> oggetto o `true` se la proprietà è impostata su e viene generata un'eccezione quando il motore di associazione imposta l'origine, il motore di associazione verifica se è presente un <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>oggetto . È possibile utilizzare il <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> callback per fornire un gestore personalizzato per la gestione delle eccezioni. Se <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A> un oggetto non <xref:System.Windows.Data.Binding>è specificato in <xref:System.Windows.Controls.ValidationError> , il motore di <xref:System.Windows.Controls.Validation.Errors%2A?displayProperty=nameWithType> associazione crea un oggetto con l'eccezione e lo aggiunge all'insieme dell'elemento associato.

## <a name="debugging-mechanism"></a>Meccanismo di debug

È possibile impostare <xref:System.Diagnostics.PresentationTraceSources.TraceLevel%2A?displayProperty=nameWithType> la proprietà associata su un oggetto correlato all'associazione per ricevere informazioni sullo stato di un'associazione specifica.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataErrorValidationRule>
- [Eseguire l'associazione ai risultati di una query LINQBind to the results of a LINQ query](../../framework/wpf/data/how-to-bind-to-the-results-of-a-linq-query.md)
- [Associazione dati](../../framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Demo sull'associazione dati][data-binding-demo]
- [Articoli pratici](../../framework/wpf/data/data-binding-how-to-topics.md)
- [Eseguire il binding a un'origine dati ADO.NET](../../framework/wpf/data/how-to-bind-to-an-ado-net-data-source.md)

[data-binding-demo]: https://github.com/microsoft/WPF-Samples/tree/master/Sample%20Applications/DataBindingDemo "app demo per l'associazione dati"
