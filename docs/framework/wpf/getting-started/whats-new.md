---
title: Novità di WPF versione 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 03f785da018cacdec643fa196bdd0c6d5d7c7f70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325826"
---
# <a name="whats-new-in-wpf-version-45"></a>Novità di WPF versione 4.5
<a name="introduction"></a> In questo argomento contiene informazioni sulle funzionalità nuove e migliorate in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] versione 4.5.  
  
 Di seguito sono elencate le diverse sezioni di questo argomento:  
  
-   [Controllo della barra multifunzione](#ribbon_control)  
  
-   [Miglioramento delle prestazioni durante la visualizzazione di grandi set di dati raggruppati](#grouped_virtualization)  
  
-   [Nuove funzionalità per il VirtualizingPanel](#VirtualizingPanel)  
  
-   [Associazione alle proprietà statiche](#static_properties)  
  
-   [Accesso alle raccolte su thread non di interfaccia utente](#xthread_access)  
  
-   [Convalida dei dati in modo sincrono e asincrono](#INotifyDataErrorInfo)  
  
-   [Aggiornamento automatico dell'origine di un data binding](#delay)  
  
-   [Associazione a tipi che implementano ICustomTypeProvider](#ICustomTypeProvider)  
  
-   [Recupero delle informazioni del data binding da un'espressione di associazione](#binding_state)  
  
-   [Verifica di un oggetto DataContext valido](#DisconnectedSource)  
  
-   [Riposizionamento di dati contestuale alla modifica dei valori (shaping attivo)](#live_shaping)  
  
-   [Supporto migliorato per stabilire un riferimento debole a un evento](#weak_event_pattern)  
  
-   [Nuovi metodi per la classe Dispatcher](#async)  
  
-   [Estensioni di markup per gli eventi](#events_markup_extenions)  
  
<a name="ribbon_control"></a>   
## <a name="ribbon-control"></a>Controllo della barra multifunzione  
 WPF 4.5 è disponibile un <xref:System.Windows.Controls.Ribbon.Ribbon> controllo che ospita una barra di accesso rapido, Menu dell'applicazione e schede.  Per altre informazioni, vedere [Cenni preliminari sulla barra multifunzione](/visualstudio/vsto/ribbon-overview).  
  
<a name="grouped_virtualization"></a>   
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>Miglioramento delle prestazioni durante la visualizzazione di grandi set di dati raggruppati  
 La virtualizzazione dell'interfaccia utente viene eseguita quando si genera un subset di elementi dell'interfaccia utente da un numero maggiore di elementi dati visibili sullo schermo. Il <xref:System.Windows.Controls.VirtualizingPanel> definisce il <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> proprietà che consente la virtualizzazione dell'interfaccia utente per i dati raggruppati associata.  Per altre informazioni sul raggruppamento dei dati, vedere Procedura: Ordinare e raggruppare dati tramite una visualizzazione in XAML.  Per ulteriori informazioni sulla virtualizzazione dei dati raggruppati, vedere il <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> proprietà associata.  
  
<a name="VirtualizingPanel"></a>   
## <a name="new-features-for-the-virtualizingpanel"></a>Nuove funzionalità per il VirtualizingPanel  
  
1. È possibile specificare se un <xref:System.Windows.Controls.VirtualizingPanel>, ad esempio il <xref:System.Windows.Controls.VirtualizingStackPanel>, consente di visualizzare elementi parziali usando la <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> proprietà associata. Se <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> è impostata su <xref:System.Windows.Controls.ScrollUnit.Item>, il <xref:System.Windows.Controls.VirtualizingPanel> visualizzerà solo gli elementi che sono visibili in modo completo. Se <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> è impostata su <xref:System.Windows.Controls.ScrollUnit.Pixel>, il <xref:System.Windows.Controls.VirtualizingPanel> può visualizzare elementi parzialmente visibili.  
  
2. È possibile specificare le dimensioni della cache prima e dopo il viewport quando il <xref:System.Windows.Controls.VirtualizingPanel> esegue la virtualizzazione utilizzando la <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> proprietà associata.  La cache è la quantità di spazio sopra o sotto il viewport in cui gli elementi non sono virtualizzati.  È possibile migliorare le prestazioni usando una cache per evitare che vengano generati elementi dell'interfaccia utente quando ne viene eseguito lo scorrimento nella visualizzazione. La cache viene popolata con una priorità inferiore in modo che l'applicazione rimanga reattiva durante l'operazione. Il <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> proprietà determina l'unità di misura utilizzata da <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>.  
  
<a name="static_properties"></a>   
## <a name="binding-to-static-properties"></a>Associazione alle proprietà statiche  
 È possibile utilizzare proprietà statiche come origine di un data binding. Il motore di data binding riconosce quando cambia il valore della proprietà, se viene generato un evento statico.  Ad esempio, se la classe `SomeClass` definisce una proprietà statica denominata `MyProperty`, `SomeClass` può definire un evento statico generato quando cambia il valore di `MyProperty`.  L'evento statico può utilizzare una delle firme seguenti.  
  
-   `public static event EventHandler MyPropertyChanged;`  
  
-   `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Si noti che nel primo caso, la classe espone un evento statico denominato *PropertyName* `Changed` che passa <xref:System.EventArgs> al gestore dell'evento.  Nel secondo caso, la classe espone un evento statico denominato `StaticPropertyChanged` che passa <xref:System.ComponentModel.PropertyChangedEventArgs> al gestore dell'evento. Una classe che implementa la proprietà statica può scegliere di generare notifiche delle modifiche delle proprietà utilizzando uno dei metodi.  
  
<a name="xthread_access"></a>   
## <a name="accessing-collections-on-non-ui-threads"></a>Accesso alle raccolte su thread non di interfaccia utente  
 WPF permette di accedere e modificare le raccolte di dati su thread diversi da quello che ha creato la raccolta.  In questo modo è possibile utilizzare un thread in background per ricevere dati da un'origine esterna, ad esempio un database, e visualizzare i dati sul thread dell'interfaccia utente.  Utilizzando un altro thread per modificare la raccolta, l'interfaccia utente rimane reattiva all'interazione dell'utente.  
  
<a name="INotifyDataErrorInfo"></a>   
## <a name="synchronously-and-asynchronously-validating-data"></a>Convalida dei dati in modo sincrono e asincrono  
 Il <xref:System.ComponentModel.INotifyDataErrorInfo> interfaccia consente alle classi di entità dati implementare regole di convalida personalizzate ed esporre i risultati della convalida in modo asincrono. Questa interfaccia supporta anche gli oggetti di errori personalizzati, più errori per ogni proprietà, gli errori tra le proprietà e gli errori a livello di entità.  Per altre informazioni, vedere <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>   
## <a name="automatically-updating-the-source-of-a-data-binding"></a>Aggiornamento automatico dell'origine di un data binding  
 Se si usa un data binding per aggiornare un'origine dati, è possibile usare il <xref:System.Windows.Data.BindingBase.Delay%2A> proprietà per specificare un periodo di tempo deve trascorrere dopo le modifiche alle proprietà nella destinazione prima gli aggiornamenti di origine.  Ad esempio, si supponga di avere una <xref:System.Windows.Controls.Slider> con relativo <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> bidirezionale dei dati di proprietà associato a una proprietà di un oggetto dati e il <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> è impostata su <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.  In questo esempio, quando l'utente sposta il <xref:System.Windows.Controls.Slider>, gli aggiornamenti di origine per ogni pixel che il <xref:System.Windows.Controls.Slider> viene spostato.  L'oggetto di origine deve in genere il valore del dispositivo di scorrimento solo quando il dispositivo di scorrimento <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> interrompe le modifiche.  Per impedire l'aggiornamento dell'origine troppo spesso, usare <xref:System.Windows.Data.BindingBase.Delay%2A> per specificare che l'origine non deve essere aggiornata fino allo scadere di un determinato periodo di tempo dopo il controllo thumb cessa lo spostamento.  
  
<a name="ICustomTypeProvider"></a>   
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>Associazione a tipi che implementano ICustomTypeProvider  
 WPF supporta il data binding a oggetti che implementano <xref:System.Reflection.ICustomTypeProvider>, noto anche come tipi personalizzati.  È possibile utilizzare tipi personalizzati nei casi seguenti.  
  
1. Come un <xref:System.Windows.PropertyPath> in un data binding. Ad esempio, il <xref:System.Windows.Data.Binding.Path%2A> proprietà di un <xref:System.Windows.Data.Binding> può fare riferimento a una proprietà di un tipo personalizzato.  
  
2. Come valore del <xref:System.Windows.DataTemplate.DataType%2A> proprietà.  
  
3. Come un tipo che determina le colonne generate automaticamente in un <xref:System.Windows.Controls.DataGrid>.  
  
<a name="binding_state"></a>   
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>Recupero delle informazioni di data binding da un'espressione di associazione  
 In alcuni casi, è possibile ottenere il <xref:System.Windows.Data.BindingExpression> di un <xref:System.Windows.Data.Binding> e sono necessarie informazioni sugli oggetti di origine e destinazione dell'associazione.  Sono state aggiunte nuove API che consentono di ottenere l'oggetto di origine e di destinazione o la proprietà associata.  Quando si dispone di un <xref:System.Windows.Data.BindingExpression>, usare le API seguenti per ottenere informazioni sull'origine e destinazione.  
  
|Per trovare questo valore dell'associazione|Utilizzare questa API|  
|---------------------------------------|------------------|  
|L'oggetto di destinazione|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|La proprietà di destinazione|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|Oggetto di origine|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|La proprietà di origine|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|Se il <xref:System.Windows.Data.BindingExpression> appartiene a un <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|Il proprietario di un <xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## <a name="checking-for-a-valid-datacontext-object"></a>Verifica di un oggetto DataContext valido  
 Vi sono casi in cui il <xref:System.Windows.FrameworkElement.DataContext%2A> di un contenitore di elementi in un <xref:System.Windows.Controls.ItemsControl> viene disconnesso.  Un contenitore di elementi è l'elemento dell'interfaccia utente che visualizza un elemento in un <xref:System.Windows.Controls.ItemsControl>.  Quando un <xref:System.Windows.Controls.ItemsControl> dati associato a una raccolta, un contenitore di elementi viene generato per ogni elemento. In alcuni casi, i contenitori di elementi vengono rimossi dalla struttura ad albero visuale. Due casi comuni in cui un contenitore di elementi viene rimosso sono quando un elemento viene rimosso dalla raccolta sottostante e quando è abilitata la virtualizzazione nel <xref:System.Windows.Controls.ItemsControl>. In questi casi, il <xref:System.Windows.FrameworkElement.DataContext%2A> del contenitore di elementi verrà impostata sull'oggetto sentinel restituito dal <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> proprietà statica.  È necessario controllare se il <xref:System.Windows.FrameworkElement.DataContext%2A> è uguale al <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> oggetto prima di accedere al <xref:System.Windows.FrameworkElement.DataContext%2A> di un contenitore di elementi.  
  
<a name="live_shaping"></a>   
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>Riposizionamento di dati contestuale alla modifica dei valori (shaping attivo)  
 Una raccolta di dati può essere raggruppata, ordinata o filtrata. WPF 4.5 consente di riordinare i dati quando questi vengono modificati. Ad esempio, si supponga che un'applicazione utilizza un <xref:System.Windows.Controls.DataGrid> per elencare scorte in un mercato azionario e vengono ordinati dal valore predefinito. Se l'ordinamento in tempo reale è abilitato su stocks' <xref:System.Windows.Data.CollectionView>, posizione del titolo nel <xref:System.Windows.Controls.DataGrid> spostamenti quando il valore dell'azione supera il valore o valore minore di un'altra azione.   Per altre informazioni, vedere il <xref:System.ComponentModel.ICollectionViewLiveShaping> interfaccia.  
  
<a name="weak_event_pattern"></a>   
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>Supporto migliorato per stabilire un riferimento debole a un evento  
 L'implementazione del modello con riferimenti deboli agli eventi è ora più semplice perché i sottoscrittori di eventi possono parteciparvi senza implementare un'interfaccia aggiuntiva.  Il tipo generico <xref:System.Windows.WeakEventManager> classe consente inoltre ai sottoscrittori di partecipare al modello di eventi deboli se un oggetto dedicato <xref:System.Windows.WeakEventManager> non esiste per un determinato evento.  Per ulteriori informazioni, vedere [Modelli di eventi deboli](../advanced/weak-event-patterns.md).  
  
<a name="async"></a>   
## <a name="new-methods-for-the-dispatcher-class"></a>Nuovi metodi per la classe Dispatcher  
 La classe Dispatcher definisce nuovi metodi per le operazioni sincrone e asincrone.  Sincroni <xref:System.Windows.Threading.Dispatcher.Invoke%2A> metodo definisce gli overload che accettano un' <xref:System.Action> o <xref:System.Func%601> parametro. Il nuovo metodo asincrono <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, accetta inoltre un <xref:System.Action> oppure <xref:System.Func%601> come il parametro di callback e restituisce un <xref:System.Windows.Threading.DispatcherOperation> o <xref:System.Windows.Threading.DispatcherOperation%601>.   Il <xref:System.Windows.Threading.DispatcherOperation> e <xref:System.Windows.Threading.DispatcherOperation%601> classi definiscono un <xref:System.Threading.Tasks.Task> proprietà.  Quando si chiama <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>, è possibile usare il `await` parola chiave con il <xref:System.Windows.Threading.DispatcherOperation> o associato <xref:System.Threading.Tasks.Task>. Se è necessario attendere in modo sincrono il <xref:System.Threading.Tasks.Task> restituito da un <xref:System.Windows.Threading.DispatcherOperation> oppure <xref:System.Windows.Threading.DispatcherOperation%601>, chiamare il <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> metodo di estensione. La chiamata a <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> provoca un deadlock se l'operazione viene accodata in un thread di chiamata. Per altre informazioni sull'uso di un <xref:System.Threading.Tasks.Task> per eseguire operazioni asincrone, vedere [parallelismo fra attività (Task Parallel Library)](../../../standard/parallel-programming/task-based-asynchronous-programming.md).  
  
<a name="events_markup_extenions"></a>   
## <a name="markup-extensions-for-events"></a>Estensioni di markup per gli eventi  
 WPF 4.5 supporta le estensioni di markup per gli eventi.  Mentre WPF non definisce un'estensione di markup da utilizzare per gli eventi, le terze parti sono in grado di creare un'estensione di markup che può essere utilizzata con gli eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Novità di .NET Framework](../../whats-new/index.md)
