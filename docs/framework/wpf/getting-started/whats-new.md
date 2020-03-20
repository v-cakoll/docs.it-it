---
title: Novità di WPF versione 4.5
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 708b2fc231bfe7a9bc1f52872a0ec41c91931f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174706"
---
# <a name="whats-new-in-wpf-version-45"></a>Novità di WPF versione 4.5
<a name="introduction"></a>Questo argomento contiene informazioni sulle funzionalità [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] nuove e migliorate della versione 4.5.  
  
 In questo argomento sono incluse le sezioni seguenti:  
  
- [Controllo della barra multifunzione](#ribbon_control)  
  
- [Miglioramento delle prestazioni durante la visualizzazione di grandi set di dati raggruppati](#grouped_virtualization)  
  
- [Nuove funzionalità per il VirtualizingPanel](#VirtualizingPanel)  
  
- [Associazione alle proprietà statiche](#static_properties)  
  
- [Accesso alle raccolte su thread non di interfaccia utente](#xthread_access)  
  
- [Convalida dei dati in modo sincrono e asincrono](#INotifyDataErrorInfo)  
  
- [Aggiornamento automatico dell'origine di un data binding](#delay)  
  
- [Associazione a tipi che implementano ICustomTypeProvider](#ICustomTypeProvider)  
  
- [Recupero delle informazioni del data binding da un'espressione di associazione](#binding_state)  
  
- [Verifica di un oggetto DataContext valido](#DisconnectedSource)  
  
- [Riposizionamento di dati contestuale alla modifica dei valori (shaping attivo)](#live_shaping)  
  
- [Supporto migliorato per stabilire un riferimento debole a un evento](#weak_event_pattern)  
  
- [Nuovi metodi per la classe Dispatcher](#async)  
  
- [Estensioni di markup per gli eventi](#events_markup_extenions)  
  
<a name="ribbon_control"></a>
## <a name="ribbon-control"></a>Controllo della barra multifunzione  
 WPF 4.5WPF <xref:System.Windows.Controls.Ribbon.Ribbon> 4.5 viene fornito con un controllo che ospita una barra di accesso rapido, menu dell'applicazione e schede.  Per altre informazioni, vedere [Cenni preliminari sulla barra multifunzione](/visualstudio/vsto/ribbon-overview).  
  
<a name="grouped_virtualization"></a>
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>Miglioramento delle prestazioni durante la visualizzazione di grandi set di dati raggruppati  
 La virtualizzazione dell'interfaccia utente viene eseguita quando si genera un subset di elementi dell'interfaccia utente da un numero maggiore di elementi dati visibili sullo schermo. L'oggetto <xref:System.Windows.Controls.VirtualizingPanel> <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> definisce la proprietà associata che abilita la virtualizzazione dell'interfaccia utente per i dati raggruppati.  Per ulteriori informazioni sul raggruppamento dei dati, vedere Procedura: ordinare e raggruppare i dati tramite una visualizzazione di XAML.  Per altre informazioni sulla virtualizzazione dei <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> dati raggruppati, vedere la proprietà associata.  
  
<a name="VirtualizingPanel"></a>
## <a name="new-features-for-the-virtualizingpanel"></a>Nuove funzionalità per il VirtualizingPanel  
  
1. È possibile specificare se <xref:System.Windows.Controls.VirtualizingPanel> <xref:System.Windows.Controls.VirtualizingStackPanel>un oggetto , ad <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> esempio , deve visualizzare elementi parziali utilizzando la proprietà associata. Se <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> è <xref:System.Windows.Controls.ScrollUnit.Item>impostato <xref:System.Windows.Controls.VirtualizingPanel> su , verranno visualizzati solo gli elementi completamente visibili. Se <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> è <xref:System.Windows.Controls.ScrollUnit.Pixel>impostato <xref:System.Windows.Controls.VirtualizingPanel> su , è possibile visualizzare gli elementi parzialmente visibili.  
  
2. È possibile specificare la dimensione della cache prima <xref:System.Windows.Controls.VirtualizingPanel> e dopo il <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> riquadro di visualizzazione durante la virtualizzazione dell'oggetto utilizzando la proprietà associata.  La cache è la quantità di spazio sopra o sotto il viewport in cui gli elementi non sono virtualizzati.  È possibile migliorare le prestazioni usando una cache per evitare che vengano generati elementi dell'interfaccia utente quando ne viene eseguito lo scorrimento nella visualizzazione. La cache viene popolata con una priorità inferiore in modo che l'applicazione rimanga reattiva durante l'operazione. La <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> proprietà determina l'unità di <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>misura utilizzata da .  
  
<a name="static_properties"></a>
## <a name="binding-to-static-properties"></a>Associazione alle proprietà statiche  
 È possibile utilizzare proprietà statiche come origine di un data binding. Il motore di data binding riconosce quando cambia il valore della proprietà, se viene generato un evento statico.  Ad esempio, se la classe `SomeClass` definisce una proprietà statica denominata `MyProperty`, `SomeClass` può definire un evento statico generato quando cambia il valore di `MyProperty`.  L'evento statico può utilizzare una delle firme seguenti.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 Si noti che nel primo caso, la classe espone <xref:System.EventArgs> un evento statico denominato *PropertyName* `Changed` che passa al gestore eventi.  Nel secondo caso, la classe espone `StaticPropertyChanged` un <xref:System.ComponentModel.PropertyChangedEventArgs> evento statico denominato che passa al gestore eventi. Una classe che implementa la proprietà statica può scegliere di generare notifiche delle modifiche delle proprietà utilizzando uno dei metodi.  
  
<a name="xthread_access"></a>
## <a name="accessing-collections-on-non-ui-threads"></a>Accesso alle raccolte su thread non di interfaccia utente  
 WPF permette di accedere e modificare le raccolte di dati su thread diversi da quello che ha creato la raccolta.  In questo modo è possibile utilizzare un thread in background per ricevere dati da un'origine esterna, ad esempio un database, e visualizzare i dati sul thread dell'interfaccia utente.  Utilizzando un altro thread per modificare la raccolta, l'interfaccia utente rimane reattiva all'interazione dell'utente.  
  
<a name="INotifyDataErrorInfo"></a>
## <a name="synchronously-and-asynchronously-validating-data"></a>Convalida dei dati in modo sincrono e asincrono  
 L'interfaccia <xref:System.ComponentModel.INotifyDataErrorInfo> consente alle classi di entità di dati di implementare regole di convalida personalizzate ed esporre i risultati della convalida in modo asincrono. Questa interfaccia supporta anche gli oggetti di errori personalizzati, più errori per ogni proprietà, gli errori tra le proprietà e gli errori a livello di entità.  Per altre informazioni, vedere <xref:System.ComponentModel.INotifyDataErrorInfo>.  
  
<a name="delay"></a>
## <a name="automatically-updating-the-source-of-a-data-binding"></a>Aggiornamento automatico dell'origine di un data binding  
 Se si utilizza un'associazione dati per aggiornare un'origine dati, è possibile utilizzare la <xref:System.Windows.Data.BindingBase.Delay%2A> proprietà per specificare un periodo di tempo da passare dopo le modifiche della proprietà nella destinazione prima dell'aggiornamento dell'origine.  Si supponga, ad esempio, <xref:System.Windows.Controls.Slider> di <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> disporre di un oggetto che dispone dei <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> relativi dati <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>di proprietà associati bidirezionalmente a una proprietà di un oggetto dati e che la proprietà sia impostata su .  In questo esempio, quando <xref:System.Windows.Controls.Slider>l'utente sposta l'oggetto <xref:System.Windows.Controls.Slider> , l'origine viene aggiornata per ogni pixel spostato.  L'oggetto di origine richiede in genere il <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> valore del dispositivo di scorrimento solo quando il dispositivo di scorrimento smette di cambiare.  Per evitare l'aggiornamento troppo <xref:System.Windows.Data.BindingBase.Delay%2A> spesso dell'origine, utilizzare per specificare che l'origine non deve essere aggiornata fino a quando non trascorre un determinato periodo di tempo dopo che la casella di scorrimento si smette di muoversi.  
  
<a name="ICustomTypeProvider"></a>
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>Associazione a tipi che implementano ICustomTypeProvider  
 WPFWPF supporta l'associazione <xref:System.Reflection.ICustomTypeProvider>dati a oggetti che implementano , noti anche come tipi personalizzati.  È possibile utilizzare tipi personalizzati nei casi seguenti.  
  
1. Come <xref:System.Windows.PropertyPath> un in un'associazione dati. Ad esempio, <xref:System.Windows.Data.Binding.Path%2A> la <xref:System.Windows.Data.Binding> proprietà di un oggetto può fare riferimento a una proprietà di un tipo personalizzato.  
  
2. Come valore della <xref:System.Windows.DataTemplate.DataType%2A> proprietà.  
  
3. Come tipo che determina le colonne <xref:System.Windows.Controls.DataGrid>generate automaticamente in un oggetto .  
  
<a name="binding_state"></a>
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>Recupero delle informazioni di data binding da un'espressione di associazione  
 In alcuni casi, è <xref:System.Windows.Data.BindingExpression> possibile <xref:System.Windows.Data.Binding> ottenere il di un e hanno bisogno di informazioni sugli oggetti di origine e di destinazione dell'associazione.  Sono state aggiunte nuove API che consentono di ottenere l'oggetto di origine e di destinazione o la proprietà associata.  Quando si <xref:System.Windows.Data.BindingExpression>dispone di un oggetto , utilizzare le API seguenti per ottenere informazioni sulla destinazione e sull'origine.  
  
|Per trovare questo valore dell'associazione|Utilizzare questa API|  
|---------------------------------------|------------------|  
|L'oggetto di destinazione|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|La proprietà di destinazione|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|Oggetto di origine|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|La proprietà di origine|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|Se <xref:System.Windows.Data.BindingExpression> l'oggetto appartiene a un<xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|Il proprietario di un<xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>
## <a name="checking-for-a-valid-datacontext-object"></a>Verifica di un oggetto DataContext valido  
 In alcuni casi <xref:System.Windows.FrameworkElement.DataContext%2A> l'oggetto di <xref:System.Windows.Controls.ItemsControl> un contenitore di elementi in un oggetto viene disconnesso.  Un contenitore di elementi è l'elemento dell'interfaccia utente che visualizza un elemento in un oggetto <xref:System.Windows.Controls.ItemsControl>.  Quando <xref:System.Windows.Controls.ItemsControl> un oggetto è associato a dati a una raccolta, viene generato un contenitore di elementi per ogni elemento. In alcuni casi, i contenitori di elementi vengono rimossi dalla struttura ad albero visuale. I due casi tipici in cui viene rimosso un contenitore di elementi sono <xref:System.Windows.Controls.ItemsControl>quando un elemento viene rimosso dalla raccolta sottostante e quando la virtualizzazione è abilitata nell'oggetto . In questi casi, la <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà del contenitore di elementi verrà impostata <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> sull'oggetto sentinel restituito dalla proprietà statica.  È necessario verificare se <xref:System.Windows.FrameworkElement.DataContext%2A> <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> l'oggetto è <xref:System.Windows.FrameworkElement.DataContext%2A> uguale all'oggetto prima di accedere a un contenitore di elementi.  
  
<a name="live_shaping"></a>
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>Riposizionamento di dati contestuale alla modifica dei valori (shaping attivo)  
 Una raccolta di dati può essere raggruppata, ordinata o filtrata. WPF 4.5 consente di riordinare i dati quando questi vengono modificati. Si supponga, ad esempio, <xref:System.Windows.Controls.DataGrid> che un'applicazione utilizzi un oggetto per elencare le azioni in un mercato azionario e che le azioni siano ordinate in base al valore delle scorte. Se lo smistamento live <xref:System.Windows.Data.CollectionView>è abilitato sulle azioni', la <xref:System.Windows.Controls.DataGrid> posizione di un'azione nei movimenti quando il valore dello stock diventa maggiore o minore del valore di un altro titolo.   Per altre informazioni, <xref:System.ComponentModel.ICollectionViewLiveShaping> vedere l'interfaccia.  
  
<a name="weak_event_pattern"></a>
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>Supporto migliorato per stabilire un riferimento debole a un evento  
 L'implementazione del modello con riferimenti deboli agli eventi è ora più semplice perché i sottoscrittori di eventi possono parteciparvi senza implementare un'interfaccia aggiuntiva.  La <xref:System.Windows.WeakEventManager> classe generica consente inoltre ai sottoscrittori <xref:System.Windows.WeakEventManager> di partecipare al modello di eventi deboli se non esiste un elemento dedicato per un determinato evento.  Per ulteriori informazioni, vedere [Modelli di eventi deboli](../advanced/weak-event-patterns.md).  
  
<a name="async"></a>
## <a name="new-methods-for-the-dispatcher-class"></a>Nuovi metodi per la classe Dispatcher  
 La classe Dispatcher definisce nuovi metodi per le operazioni sincrone e asincrone.  Il <xref:System.Windows.Threading.Dispatcher.Invoke%2A> metodo sincrono definisce <xref:System.Action> gli <xref:System.Func%601> overload che accettano un parametro o . Il nuovo metodo <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>asincrono, <xref:System.Action> <xref:System.Func%601> , accetta anche un <xref:System.Windows.Threading.DispatcherOperation> <xref:System.Windows.Threading.DispatcherOperation%601>o come parametro di callback e restituisce un oggetto o .   Le <xref:System.Windows.Threading.DispatcherOperation> <xref:System.Windows.Threading.DispatcherOperation%601> classi e <xref:System.Threading.Tasks.Task> definiscono una proprietà.  Quando si <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>chiama , `await` è possibile <xref:System.Windows.Threading.DispatcherOperation> utilizzare la <xref:System.Threading.Tasks.Task>parola chiave con l'oggetto o associato. Se è necessario attendere in <xref:System.Threading.Tasks.Task> modo sincrono <xref:System.Windows.Threading.DispatcherOperation> per <xref:System.Windows.Threading.DispatcherOperation%601>il <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> che viene restituito da o , chiamare il metodo di estensione. La <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> chiamata genererà un deadlock se l'operazione viene accodata in un thread chiamante. Per ulteriori informazioni <xref:System.Threading.Tasks.Task> sull'utilizzo di un per eseguire operazioni asincrone, vedere [Parallelismo delle attività (Task Parallel Library)](../../../standard/parallel-programming/task-based-asynchronous-programming.md).  
  
<a name="events_markup_extenions"></a>
## <a name="markup-extensions-for-events"></a>Estensioni di markup per gli eventi  
 WPF 4.5 supporta le estensioni di markup per gli eventi.  Mentre WPF non definisce un'estensione di markup da utilizzare per gli eventi, le terze parti sono in grado di creare un'estensione di markup che può essere utilizzata con gli eventi.  
  
## <a name="see-also"></a>Vedere anche

- [Novità di .NET Framework](../../whats-new/index.md)
