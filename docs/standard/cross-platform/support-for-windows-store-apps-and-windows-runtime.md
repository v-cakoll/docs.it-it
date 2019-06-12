---
title: Supporto .NET Framework per applicazioni Windows Store e Windows Runtime
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Windows Store apps, .NET Framework support for
- Windows Runtime, .NET Framework support for
- .NET for Windows Store apps
- .NET Framework, and Windows Store apps
- .NET Framework, and Windows Runtime
ms.assetid: 6fa7d044-ae12-4c54-b8ee-50915607a565
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a51d8d77318685e4a4c8b90a793f2946de4a792b
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025544"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>Supporto .NET Framework per applicazioni Windows Store e Windows Runtime
.NET Framework 4.5 supporta una serie di scenari di sviluppo software con il Runtime di Windows. Questi scenari sono suddivisi in tre categorie:

- Sviluppare [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] le app con controlli XAML, come descritto in [app di Guida di orientamento per Windows Store scritte in c# o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), [come procedure (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10)), e [panoramica delle app .NET per Windows Store ](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

- Sviluppo di librerie di classi da utilizzare nelle applicazioni [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] create con .NET Framework.

- Sviluppo di componenti Windows Runtime, inseriti nel pacchetto. File WinMD, che possono essere usati da qualsiasi linguaggio di programmazione che supporta il Runtime di Windows. Ad esempio, vedere [creazione di componenti Windows Runtime in c# e Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

 In questo argomento viene descritto il supporto che .NET Framework fornisce per tutte e tre le categorie e vengono descritti gli scenari per i componenti di Windows Runtime. La prima sezione include informazioni di base sulla relazione tra il Runtime di Windows e .NET Framework e spiega spiegate alcune singolarità che si possono verificare nel sistema della Guida e l'IDE. Il [seconda sezione](#WindowsRuntimeComponents) vengono illustrati gli scenari per lo sviluppo di componenti Windows Runtime.

## <a name="the-basics"></a>Nozioni di base
 .NET Framework supporta i tre scenari di sviluppo elencati in precedenza fornendo [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]e grazie al supporto per il Windows Runtime.

- [Gli spazi dei nomi .NET framework e Windows Runtime](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) fornisce una visualizzazione semplice delle librerie di classi .NET Framework e includono solo i tipi e membri che è possibile utilizzare per creare [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] App e componenti di Windows Runtime.

    - Quando si usa Visual Studio (Visual Studio 2012 o versione successiva) per sviluppare un [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app o un componente Windows Runtime, un set di assembly di riferimento modo si garantisce che si vedano solo i tipi pertinenti e i membri.

    - Questo set di API efficace viene semplificato ulteriormente le funzionalità per la rimozione di funzionalità che sono duplicati all'interno di .NET Framework o che duplica il Runtime di Windows. Ad esempio, contiene solo le versioni generiche di tipi di raccolta e il modello a oggetti documento XML è stato eliminato a favore dell'API di Windows Runtime XML impostato.

    - Vengono rimosse anche le funzionalità che è sufficiente eseguire il wrapping di API del sistema operativo, perché il Runtime di Windows è semplice da chiamare dal codice gestito.

     Per altre informazioni, vedere la [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], vedere la [panoramica delle app .NET per Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Per informazioni sul processo di selezione di API, vedere la [.NET per App in stile Metro](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) nel blog di .NET.

- Il [Windows Runtime](/uwp/api/) fornisce all'utente gli elementi dell'interfaccia per la compilazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] le App e fornisce l'accesso alle funzionalità del sistema operativo. Ad esempio .NET Framework, il Runtime di Windows dispone di metadati che permettono di C# e librerie di classi di compilatori di Visual Basic per usare il Runtime di Windows il modo in cui utilizzano .NET Framework. .NET Framework rende più semplice usare il Runtime di Windows, nascondendo alcune differenze:

    - Alcune differenze in modelli di programmazione tra .NET Framework e il Runtime di Windows, ad esempio il modello per l'aggiunta e rimozione di gestori eventi, sono nascosti. È sufficiente usare il modello di .NET Framework.

    - Vengono celate alcune differenze nei tipi comunemente utilizzati, ad esempio i tipi primitivi e le raccolte. Utilizzare semplicemente il tipo di .NET Framework, come descritto nella [differenze visibili nell'IDE](#DifferencesVisibleInIDE), più avanti in questo articolo.

 La maggior parte dei casi, il supporto di .NET Framework per il Runtime di Windows è trasparente. Nella sezione successiva illustra alcune delle differenze evidenti tra codice gestito e il Runtime di Windows.

<a name="AboutReferenceDocumentation"></a>
### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>.NET Framework e la documentazione di riferimento del Runtime di Windows
 Il Runtime di Windows e i set di documentazione di .NET Framework sono separati. Se si preme F1 per visualizzare la Guida su un tipo o un membro, viene visualizzata la documentazione di riferimento del set appropriato. Tuttavia, se si scorre la [riferimento a Windows Runtime](/uwp/api/) è possibile riscontrare esempi dubbi:

- Argomenti come quello di <xref:Windows.Foundation.Collections.IIterable%601> interfaccia non dispongono di sintassi di dichiarazione per Visual Basic o c#. Al contrario, viene visualizzata una nota sopra la sezione sintassi (in questo caso, ".NET: Questa interfaccia viene visualizzato come IEnumerable\<T > "). Questo avviene perché il Runtime di Windows e .NET Framework offrono funzionalità simili con interfacce differenti. Inoltre, vi sono differenze di comportamento: `IIterable` dispone di un metodo `First` anziché di un metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> per restituire l'enumeratore. Anziché dover apprendere un modo diverso di eseguire un'attività comune, .NET Framework supporta il Runtime di Windows, rendendo il codice gestito vengono visualizzati come utilizzare il tipo a cui che si ha familiarità con. Non verrà visualizzato il `IIterable` interfaccia nell'IDE e pertanto l'unico modo per riscontrarla nella documentazione di riferimento di Windows Runtime da esplorare tale documentazione direttamente.

- Il <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> documentazione viene illustrato un problema strettamente correlato: I tipi di parametro sembrano essere differenti per le diverse lingue. Per C# e Visual Basic, i tipi di parametro sono <xref:System.String?displayProperty=nameWithType> e <xref:System.Uri?displayProperty=nameWithType>. Inoltre, questa situazione si verifica in quanto .NET Framework dispone di propri tipi `String` e `Uri` e, per questi tipi comunemente utilizzati, non ha senso imporre agli utenti di .NET Framework di apprendere un modo diverso per eseguire le operazioni. Nell'IDE di .NET Framework nasconde i corrispondenti tipi Windows Runtime.

- In alcuni casi, ad esempio il <xref:Windows.UI.Xaml.GridLength> struttura, .NET Framework fornisce un tipo con lo stesso nome ma con più funzionalità. Ad esempio, un set di argomenti su costruttori e proprietà è associato a `GridLength`, ma con blocchi di sintassi solo per Visual Basic e C# perché i membri sono disponibili solo nel codice gestito. Nel Runtime di Windows, le strutture dispongono solo di campi. La struttura di Windows Runtime richiede una classe helper, <xref:Windows.UI.Xaml.GridLengthHelper>, per offrire funzionalità equivalenti. Non verrà visualizzata la classe di supporto nell'IDE quando si scrive il codice gestito.

- Nell'IDE, sembrano derivare da tipi Windows Runtime <xref:System.Object?displayProperty=nameWithType>. Sembrano disporre di membri ereditati da <xref:System.Object>, ad esempio <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Questi membri funzionano come se i tipi ereditassero effettivamente da <xref:System.Object>, e i tipi Windows Runtime possono essere convertiti in <xref:System.Object>. Questa funzionalità fa parte del supporto che .NET Framework fornisce per il Runtime di Windows. Tuttavia, se si visualizzano i tipi nella documentazione di riferimento di Windows Runtime, verrà visualizzato alcun membro. La documentazione per questi membri apparentemente ereditati viene fornita dalla documentazione di riferimento a <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>
### <a name="differences-that-are-visible-in-the-ide"></a>Differenze visibili nell'IDE
 In più avanzati scenari di programmazione, ad esempio usando un componente Windows Runtime scritto in C# per fornire la logica dell'applicazione per un [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app compilata per Windows utilizzando JavaScript, queste differenze sono evidenti nell'IDE, nonché come mostrato di documentazione. Quando il componente restituisce un `IDictionary<int, string>` JavaScript e si esamina nel debugger JavaScript, si noterà i metodi di `IMap<int, string>` dato che JavaScript Usa il tipo Windows Runtime. Alcuni tipi di raccolte comunemente utilizzati che vengono visualizzati in modo diverso nei due linguaggi sono riportati nella tabella seguente:

|Tipo di Windows Runtime|Tipo .NET Framework corrispondente|
|--------------------------------------------------------------|---------------------------------------|
|`IIterable<T>`|`IEnumerable<T>`|
|`IIterator<T>`|`IEnumerator<T>`|
|`IVector<T>`|`IList<T>`|
|`IVectorView<T>`|`IReadOnlyList<T>`|
|`IMap<K, V>`|`IDictionary<TKey, TValue>`|
|`IMapView<K, V>`|`IReadOnlyDictionary<TKey, TValue>`|
|`IBindableIterable`|`IEnumerable`|
|`IBindableVector`|`IList`|
|`Windows.UI.Xaml.Data.INotifyPropertyChanged`|`System.ComponentModel.INotifyPropertyChanged`|
|`Windows.UI.Xaml.Data.PropertyChangedEventHandler`|`System.ComponentModel.PropertyChangedEventHandler`|
|`Windows.UI.Xaml.Data.PropertyChangedEventArgs`|`System.ComponentModel.PropertyChangedEventArgs`|

 Nel Runtime di Windows, `IMap<K, V>` e `IMapView<K, V>` vengono Iterate utilizzando `IKeyValuePair`. Quando vengono passate al codice gestito, vengono visualizzate come `IDictionary<TKey, TValue>` e `IReadOnlyDictionary<TKey, TValue>`, ed è quindi naturale utilizzare `System.Collections.Generic.KeyValuePair<TKey, TValue>` per enumerarle.

 Il modo in cui le interfacce vengono visualizzate nel codice gestito influisce sul modo in cui vengono visualizzati i tipi tramite cui vengono implementate queste interfacce. Ad esempio, tramite la classe `PropertySet` viene implementata l'interfaccia `IMap<K, V>`, che nel codice gestito viene visualizzata come `IDictionary<TKey, TValue>`. L'oggetto `PropertySet` viene visualizzato come se fosse implementata l'interfaccia `IDictionary<TKey, TValue>` anziché `IMap<K, V>`, pertanto nel codice gestito disporrà apparentemente di un metodo `Add`, il cui comportamento è simile al metodo `Add` nei dizionari di .NET Framework. Non risulta avere un metodo `Insert`.

 Per altre informazioni sull'uso di .NET Framework per creare un componente Windows Runtime e una procedura dettagliata che illustra come usare un componente di questo tipo con JavaScript, vedere [Creating Windows Runtime Components in C# e Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Tipi primitivi
 Per abilitare l'utilizzo naturale di Windows Runtime nel codice gestito, vengono visualizzati i tipi primitivi di .NET Framework anziché dei tipi primitivi di Windows Runtime nel codice. In .NET Framework i tipi primitivi quali la struttura `Int32` presentano numerosi metodi e proprietà utili, ad esempio il metodo `Int32.TryParse`. Al contrario, i tipi primitivi e le strutture di runtime di Windows dispongono solo di campi. Quando si utilizzano le primitive nel codice gestito, sembrano essere tipi .NET Framework e si possono utilizzare le proprietà e i metodi dei tipi .NET Framework normalmente. Nell'elenco seguente viene fornito un riepilogo:

- Per le primitive di Windows Runtime `Int32`, `Int64`, `Single`, `Double`, `Boolean`, `String` (una raccolta non modificabile di caratteri Unicode), `Enum`, `UInt32`, `UInt64`, e `Guid`, usare il tipo con lo stesso nome nel `System` dello spazio dei nomi.

- Per `UInt8`, utilizzare `System.Byte`.

- Per `Char16`, utilizzare `System.Char`.

- Per l'interfaccia `IInspectable`, utilizzare `System.Object`.

- Per `HRESULT`, utilizzare una struttura con un membro `System.Int32`.

 Come con i tipi di interfaccia, l'unica volta è possibile visualizzare la prova di questa rappresentazione è quando il progetto di .NET Framework è un componente Windows Runtime che viene utilizzato da un [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app compilata con JavaScript.

 Altri tipi Windows Runtime di base, di uso comune visualizzati nel codice gestito come equivalenti di .NET Framework sono inclusi i `Windows.Foundation.DateTime` struttura, che viene visualizzata nel codice gestito come i <xref:System.DateTimeOffset?displayProperty=nameWithType> struttura e il `Windows.Foundation.TimeSpan` struttura, che viene visualizzato come il <xref:System.TimeSpan?displayProperty=nameWithType> struttura.

### <a name="other-differences"></a>Altre differenze
 In alcuni casi, il fatto che i tipi .NET Framework vengono visualizzati nel codice anziché tipi Windows Runtime necessita dell'intervento da parte dell'utente. Ad esempio, il <xref:Windows.Foundation.Uri?displayProperty=nameWithType> classe viene visualizzata come <xref:System.Uri?displayProperty=nameWithType> nel codice .NET Framework. <xref:System.Uri?displayProperty=nameWithType> consente un URI relativo, ma <xref:Windows.Foundation.Uri?displayProperty=nameWithType> richiede un URI assoluto. Pertanto, quando si passa un URI a un metodo di Windows Runtime, è necessario assicurarsi che sia assoluto. (Vedere [passaggio di un URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md).)

<a name="WindowsRuntimeComponents"></a>
## <a name="scenarios-for-developing-windows-runtime-components"></a>Scenari per lo sviluppo di componenti Windows Runtime
 Gli scenari supportati per i componenti di Runtime gestiti di Windows dipendono i principi generali seguenti:

- Componenti di Runtime di Windows che vengono compilati mediante .NET Framework non presentano differenze evidenti da altri Runtimelibraries Windows. Ad esempio, se si implementa nuovamente un componente Windows Runtime nativo con codice gestito, i due componenti sono apparentemente indistinguibili. Il fatto che il componente sia scritto in codice gestito non è visibile al codice in cui viene utilizzato, anche se il codice è esso stesso codice gestito. Tuttavia, internamente, il componente è realmente codice gestito e viene eseguito in Common Language Runtime (CLR).

- Nei componenti possono essere contenuti tipi tramite cui viene implementata la logica dell'applicazione, i controlli dell'interfaccia utente di [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] o entrambi.

    > [!NOTE]
    >  È consigliabile separare gli elementi dell'interfaccia utente dalla logica dell'applicazione. Inoltre, non è possibile utilizzare i controlli dell'interfaccia utente di [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] in un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] compilata per Windows utilizzando JavaScript e HTML.

- Un componente può essere un progetto all'interno di una soluzione Visual Studio per un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] oppure un componente riutilizzabile che è possibile aggiungere a più soluzioni.

    > [!NOTE]
    >  Se il componente verrà usato solo con C# o Visual Basic, non vi è alcun motivo di convertirlo in un componente Windows Runtime. Se si imposta una libreria di classi .NET Framework ordinaria invece, non devi limitare la superficie dell'API pubblica a tipi Windows Runtime.

- È possibile rilasciare versioni di componenti riusabili tramite il Runtime Windows <xref:Windows.Foundation.Metadata.VersionAttribute> attributo per identificare i tipi (e i membri all'interno di un tipo) sono stati aggiunti nelle differenti versioni.

- I tipi nel componente possono derivare da tipi Windows Runtime. I controlli possono derivare da tipi di controllo primitivi nel <xref:Windows.UI.Xaml.Controls.Primitives> dello spazio dei nomi o da controlli più avanzati, ad esempio <xref:Windows.UI.Xaml.Controls.Button>.

    > [!IMPORTANT]
    >  A partire da [!INCLUDE[win8](../../../includes/win8-md.md)] e .NET Framework 4.5, tutti i tipi pubblici in un componente Windows Runtime gestito deve essere bloccato. Un tipo in un altro componente Windows Runtime non può derivare da esse. Se si desidera fornire il comportamento polimorfico nel componente, è possibile creare un'interfaccia e implementarla nei tipi polimorfici.

- Tutti i parametri e tipi restituiti nei tipi pubblici nel componente devono essere tipi Windows Runtime (inclusi i tipi Windows Runtime che definisce il componente).

 Nelle sezioni seguenti vengono forniti esempi di scenari comuni.

### <a name="application-logic-for-a-includewin8appnamelongincludeswin8-appname-long-mdmd-app-with-javascript"></a>Logica di un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] con JavaScript
 Quando si sviluppa un'applicazione [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] per Windows utilizzando JavaScript, è possibile che alcune parti della logica dell'applicazione vengano eseguite in maniera ottimale nel codice gestito o risultino più semplici da sviluppare. Con JavaScript non è possibile utilizzare direttamente le librerie di classi .NET Framework, ma si può rendere la libreria di classi un file con estensione WinMD. In questo scenario, il componente Windows Runtime è parte integrante dell'app, in modo che non ha senso per fornire gli attributi version.

### <a name="reusable-includewin8appnamelongincludeswin8-appname-long-mdmd-ui-controls"></a>Controlli riutilizzabili dell'interfaccia utente di [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]
 È possibile creare un pacchetto un set di controlli dell'interfaccia utente correlati in un componente Windows Runtime riutilizzabile. Il componente può essere commercializzato da solo o utilizzato come elemento nelle applicazioni create. In questo scenario, è opportuno usare il Runtime Windows <xref:Windows.Foundation.Metadata.VersionAttribute> attributi per migliorare la compatibilità.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Logica di un'applicazione riutilizzabile da applicazioni .NET Framework esistenti
 È possibile comprimere il codice gestito da applicazioni desktop esistenti come componente Windows Runtime autonomo. In questo modo è possibile utilizzare il componente in applicazioni [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] compilate con C++ o JavaScript, nonché in applicazioni [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] compilate con C# o Visual Basic. Il controllo delle versioni rappresenta un'opzione in caso di più scenari di riutilizzo del codice.

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Panoramica di .NET per le app di Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|Vengono descritti i tipi di .NET Framework e i membri che è possibile usare per creare [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] RuntimeComponents Windows e App. In Dev Center di Windows.|
|[Roadmap per App di Windows Store utilizzando c# o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|Fornisce risorse chiave per iniziare a sviluppare applicazioni [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] utilizzando C# o Visual Basic, inclusi molti argomenti della guida rapida, linee guida e procedure consigliate. In Dev Center di Windows.|
|[Come procedure (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|Fornisce risorse chiave per iniziare a sviluppare applicazioni [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] utilizzando C# o Visual Basic, inclusi molti argomenti della guida rapida, linee guida e procedure consigliate. In Dev Center di Windows.|
|[Creazione di componenti Windows Runtime in C# e Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|Viene descritto come creare un componente Windows Runtime usando .NET Framework, viene spiegato come usarlo come parte di un [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app compilata per Windows utilizzando JavaScript e viene descritto come eseguire il debug della combinazione con Visual Studio. In Dev Center di Windows.|
|[Riferimento di Windows Runtime](/uwp/api/)|La documentazione di riferimento per il Runtime di Windows. In Dev Center di Windows.|
|[Passaggio di un URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md)|Descrive un problema che può verificarsi quando si passa un URI dal codice gestito per il Runtime di Windows e come evitarli.|
