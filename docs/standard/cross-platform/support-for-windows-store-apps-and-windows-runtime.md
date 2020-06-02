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
ms.openlocfilehash: 7ca5a1259f970f2db5400837eb7d20998dd824cb
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288862"
---
# <a name="net-framework-support-for-windows-store-apps-and-windows-runtime"></a>Supporto .NET Framework per applicazioni Windows Store e Windows Runtime

Il .NET Framework 4,5 supporta diversi scenari di sviluppo software con la Windows Runtime. Questi scenari sono suddivisi in tre categorie:

- Sviluppo di app di Windows 8. x Store con controlli XAML, come descritto in Guida [di orientamento per app di Windows Store con C# o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10)), procedure per le procedure di base [(XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))e [.NET per le app di Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)).

- Sviluppo di librerie di classi da usare nelle app di Windows 8. x Store create con il .NET Framework.

- Sviluppo di componenti di Windows Runtime, inclusi in un pacchetto. File WinMD, che possono essere usati da qualsiasi linguaggio di programmazione che supporta il Windows Runtime. Ad esempio, vedere [creazione di componenti Windows Runtime in C# e Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

In questo argomento viene illustrato il supporto fornito dal .NET Framework per tutte e tre le categorie e vengono descritti gli scenari per i componenti di Windows Runtime. Nella prima sezione sono incluse informazioni di base sulla relazione tra il .NET Framework e il Windows Runtime e vengono illustrate alcune stranezze che possono verificarsi nel sistema della guida e nell'IDE. La [seconda sezione](#WindowsRuntimeComponents) illustra gli scenari per lo sviluppo di componenti Windows Runtime.

## <a name="the-basics"></a>Nozioni di base

Il .NET Framework supporta i tre scenari di sviluppo elencati in precedenza fornendo .NET per le app di Windows 8. x Store e supportando il Windows Runtime stesso.

- Gli [spazi dei nomi .NET Framework e Windows Runtime](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)#net-framework-and-windows-runtime-namespaces) offrono una visualizzazione semplificata delle librerie di classi .NET Framework e includono solo i tipi e i membri che è possibile usare per creare app di Windows 8. x Store e componenti Windows Runtime.

  - Quando si usa Visual Studio (Visual Studio 2012 o versione successiva) per sviluppare un'app di Windows 8. x Store o un componente Windows Runtime, un set di assembly di riferimento garantisce che vengano visualizzati solo i tipi e i membri pertinenti.

  - Questo set di API semplificato viene ulteriormente semplificato dalla rimozione di funzionalità duplicate all'interno del .NET Framework o che duplicano Windows Runtime funzionalità. Contiene, ad esempio, solo le versioni generiche dei tipi di raccolta e il modello a oggetti documento XML viene eliminato a favore del Windows Runtime set di API XML.

  - Vengono rimosse anche le funzionalità che eseguono semplicemente il wrapping dell'API del sistema operativo, perché il Windows Runtime è facile da chiamare dal codice gestito.

  Per altre informazioni su .NET per le app di Windows 8. x Store, vedere la [Panoramica di .NET per le app di Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Per informazioni sul processo di selezione delle API, vedere la voce [.NET per le app in stile Metro](https://devblogs.microsoft.com/dotnet/net-for-metro-style-apps/) nel Blog di .NET.

- Il [Windows Runtime](/uwp/api/) fornisce gli elementi dell'interfaccia utente per la compilazione di app di Windows 8. x Store e fornisce l'accesso alle funzionalità del sistema operativo. Analogamente al .NET Framework, il Windows Runtime dispone di metadati che consentono ai compilatori C# e Visual Basic di utilizzare il Windows Runtime il modo in cui utilizzano le librerie di classi .NET Framework. Il .NET Framework facilita l'uso del Windows Runtime nascondendo alcune differenze:

  - Sono nascoste alcune differenze nei modelli di programmazione tra il .NET Framework e il Windows Runtime, ad esempio il modello per l'aggiunta e la rimozione di gestori eventi. È sufficiente usare il modello di .NET Framework.

  - Vengono celate alcune differenze nei tipi comunemente utilizzati, ad esempio i tipi primitivi e le raccolte. È sufficiente usare il tipo di .NET Framework, come descritto in [differenze visibili nell'IDE](#DifferencesVisibleInIDE), più avanti in questo articolo.

Nella maggior parte dei casi, il supporto .NET Framework per il Windows Runtime è trasparente. Nella sezione successiva vengono illustrate alcune delle differenze evidenti tra il codice gestito e il Windows Runtime.

<a name="AboutReferenceDocumentation"></a>

### <a name="the-net-framework-and-the-windows-runtime-reference-documentation"></a>La .NET Framework e la documentazione di riferimento Windows Runtime

I set di documentazione di Windows Runtime e .NET Framework sono distinti. Se si preme F1 per visualizzare la Guida su un tipo o un membro, viene visualizzata la documentazione di riferimento del set appropriato. Tuttavia, se si esplorano i [riferimenti Windows Runtime](/uwp/api/) è possibile che si verifichino esempi che sembrano sconcertanti:

- Gli argomenti come l' <xref:Windows.Foundation.Collections.IIterable%601> interfaccia non hanno la sintassi di dichiarazione per Visual Basic o C#. Viene invece visualizzata una nota sopra la sezione della sintassi (in questo caso, ".NET: questa interfaccia viene visualizzata come System. Collections. Generic. IEnumerable \<T> "). Ciò è dovuto al fatto che le .NET Framework e le Windows Runtime forniscono funzionalità simili con interfacce diverse. Inoltre, vi sono differenze di comportamento: `IIterable` dispone di un metodo `First` anziché di un metodo <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> per restituire l'enumeratore. Invece di imporre all'utente di apprendere un modo diverso per eseguire un'attività comune, il .NET Framework supporta il Windows Runtime rendendo il codice gestito visualizzato per l'uso del tipo con cui si ha familiarità. L'interfaccia non verrà visualizzata `IIterable` nell'IDE e pertanto l'unico modo in cui verrà rilevata nella documentazione di riferimento Windows Runtime consiste nell'esplorare direttamente la documentazione.

- Nella <xref:Windows.Web.Syndication.SyndicationFeed.%23ctor(System.String,System.String,Windows.Foundation.Uri)> documentazione viene illustrato un problema strettamente correlato: i relativi tipi di parametro sembrano diversi per le diverse lingue. Per C# e Visual Basic, i tipi di parametro sono <xref:System.String?displayProperty=nameWithType> e <xref:System.Uri?displayProperty=nameWithType>. Inoltre, questa situazione si verifica in quanto .NET Framework dispone di propri tipi `String` e `Uri` e, per questi tipi comunemente utilizzati, non ha senso imporre agli utenti di .NET Framework di apprendere un modo diverso per eseguire le operazioni. Nell'IDE, il .NET Framework nasconde i tipi di Windows Runtime corrispondenti.

- In alcuni casi, ad esempio la <xref:Windows.UI.Xaml.GridLength> struttura, il .NET Framework fornisce un tipo con lo stesso nome ma con più funzionalità. Ad esempio, un set di argomenti su costruttori e proprietà è associato a `GridLength`, ma con blocchi di sintassi solo per Visual Basic e C# perché i membri sono disponibili solo nel codice gestito. Nel Windows Runtime le strutture hanno solo campi. La struttura Windows Runtime richiede una classe helper, <xref:Windows.UI.Xaml.GridLengthHelper> , per fornire funzionalità equivalenti. Non verrà visualizzata la classe di supporto nell'IDE quando si scrive il codice gestito.

- Nell'IDE i tipi di Windows Runtime sembrano derivare da <xref:System.Object?displayProperty=nameWithType> . Sembrano disporre di membri ereditati da <xref:System.Object>, ad esempio <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Questi membri operano come se fossero effettivamente ereditati da <xref:System.Object> ed è possibile eseguire il cast dei tipi Windows Runtime a <xref:System.Object> . Questa funzionalità fa parte del supporto fornito dal .NET Framework per l'Windows Runtime. Tuttavia, se si visualizzano i tipi nella documentazione di riferimento Windows Runtime, non vengono visualizzati tali membri. La documentazione per questi membri apparentemente ereditati viene fornita dalla documentazione di riferimento a <xref:System.Object?displayProperty=nameWithType>.

<a name="DifferencesVisibleInIDE"></a>

### <a name="differences-that-are-visible-in-the-ide"></a>Differenze visibili nell'IDE

Negli scenari di programmazione più avanzati, ad esempio l'uso di un componente Windows Runtime scritto in C# per fornire la logica dell'applicazione per un'app di Windows 8. x Store compilata per Windows usando JavaScript, queste differenze sono evidenti nell'IDE e nella documentazione. Quando il componente restituisce un oggetto `IDictionary<int, string>` a JavaScript e lo si esamina nel debugger JavaScript, verranno visualizzati i metodi di `IMap<int, string>` perché JavaScript usa il tipo di Windows Runtime. Alcuni tipi di raccolte comunemente utilizzati che vengono visualizzati in modo diverso nei due linguaggi sono riportati nella tabella seguente:

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

Nell'Windows Runtime `IMap<K, V>` e `IMapView<K, V>` vengono iterati con `IKeyValuePair` . Quando vengono passate al codice gestito, vengono visualizzate come `IDictionary<TKey, TValue>` e `IReadOnlyDictionary<TKey, TValue>`, ed è quindi naturale utilizzare `System.Collections.Generic.KeyValuePair<TKey, TValue>` per enumerarle.

Il modo in cui le interfacce vengono visualizzate nel codice gestito influisce sul modo in cui vengono visualizzati i tipi tramite cui vengono implementate queste interfacce. Ad esempio, tramite la classe `PropertySet` viene implementata l'interfaccia `IMap<K, V>`, che nel codice gestito viene visualizzata come `IDictionary<TKey, TValue>`. `PropertySet` compare come se avesse implementato `IDictionary<TKey, TValue>` anziché `IMap<K, V>`, dunque nel codice gestito risulta avere un metodo `Add` che si comporta come il metodo `Add` nei dizionari di .NET Framework. Non risulta avere un metodo `Insert`.

Per ulteriori informazioni sull'utilizzo del .NET Framework per creare un componente Windows Runtime e una procedura dettagliata che illustra come utilizzare tale componente con JavaScript, vedere Creazione di [componenti di Windows Runtime in C# e Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).

### <a name="primitive-types"></a>Tipi primitivi

Per abilitare l'utilizzo naturale della Windows Runtime nel codice gestito, vengono visualizzati .NET Framework tipi primitivi anziché Windows Runtime tipi primitivi nel codice. In .NET Framework i tipi primitivi quali la struttura `Int32` presentano numerosi metodi e proprietà utili, ad esempio il metodo `Int32.TryParse`. Al contrario, i tipi primitivi e le strutture nel Windows Runtime hanno solo campi. Quando si utilizzano le primitive nel codice gestito, sembrano essere tipi .NET Framework e si possono utilizzare le proprietà e i metodi dei tipi .NET Framework normalmente. Nell'elenco seguente viene fornito un riepilogo:

- Per le primitive Windows Runtime `Int32` ,,, `Int64` `Single` `Double` , `Boolean` , `String` (una raccolta non modificabile di caratteri Unicode),,, `Enum` `UInt32` `UInt64` e `Guid` , usare il tipo con lo stesso nome nello `System` spazio dei nomi.

- Per `UInt8`, usare `System.Byte`.

- Per `Char16`, usare `System.Char`.

- Per l'interfaccia `IInspectable`, utilizzare `System.Object`.

- Per `HRESULT`, utilizzare una struttura con un membro `System.Int32`.

Come per i tipi di interfaccia, l'unica volta in cui è possibile visualizzare l'evidenza di questa rappresentazione è quando il progetto .NET Framework è un componente Windows Runtime usato da un'app di Windows 8. x Store compilata con JavaScript.

Altri tipi di Windows Runtime di base, usati comunemente, che vengono visualizzati nel codice gestito come .NET Framework equivalenti includono la `Windows.Foundation.DateTime` struttura, che viene visualizzata nel codice gestito come <xref:System.DateTimeOffset?displayProperty=nameWithType> struttura e la `Windows.Foundation.TimeSpan` struttura, visualizzata come <xref:System.TimeSpan?displayProperty=nameWithType> struttura.

### <a name="other-differences"></a>Altre differenze

In alcuni casi, il fatto che i tipi di .NET Framework siano visualizzati nel codice anziché Windows Runtime tipi richiedono un'azione da parte dell'utente. Ad esempio, la <xref:Windows.Foundation.Uri?displayProperty=nameWithType> classe viene visualizzata come <xref:System.Uri?displayProperty=nameWithType> in .NET Framework codice. <xref:System.Uri?displayProperty=nameWithType>consente un URI relativo, ma <xref:Windows.Foundation.Uri?displayProperty=nameWithType> richiede un URI assoluto. Pertanto, quando si passa un URI a un metodo di Windows Runtime, è necessario assicurarsi che sia assoluto. Vedi [Passaggio di un URI a Windows Runtime](passing-a-uri-to-the-windows-runtime.md).

<a name="WindowsRuntimeComponents"></a>

## <a name="scenarios-for-developing-windows-runtime-components"></a>Scenari per lo sviluppo di componenti Windows Runtime

Gli scenari supportati per i componenti Windows Runtime gestiti dipendono dai principi generali seguenti:

- Windows Runtime componenti compilati utilizzando l'.NET Framework non presentano differenze evidenti rispetto ad altri Runtimelibraries Windows. Se, ad esempio, si implementa di nuovo un componente di Windows Runtime nativo utilizzando codice gestito, i due componenti non sono distinguibili. Il fatto che il componente sia scritto in codice gestito non è visibile al codice in cui viene utilizzato, anche se il codice è esso stesso codice gestito. Tuttavia, internamente, il componente è realmente codice gestito e viene eseguito in Common Language Runtime (CLR).

- I componenti possono contenere tipi che implementano la logica dell'applicazione, i controlli dell'interfaccia utente di Windows 8. x Store o entrambi.

  > [!NOTE]
  > È consigliabile separare gli elementi dell'interfaccia utente dalla logica dell'applicazione. Inoltre, non è possibile usare i controlli dell'interfaccia utente di Windows 8. x Store in un'app di Windows 8. x Store compilata per Windows usando JavaScript e HTML.

- Un componente può essere un progetto all'interno di una soluzione di Visual Studio per un'app di Windows 8. x Store o un componente riutilizzabile che è possibile aggiungere a più soluzioni.

  > [!NOTE]
  > Se il componente verrà usato solo con C# o Visual Basic, non c'è motivo di renderlo Windows Runtime componente. Se invece si imposta una libreria di classi di .NET Framework ordinaria, non è necessario limitare la superficie dell'API pubblica ai tipi di Windows Runtime.

- È possibile rilasciare versioni di componenti riutilizzabili usando l' <xref:Windows.Foundation.Metadata.VersionAttribute> attributo Windows Runtime per identificare i tipi (e i membri all'interno di un tipo) aggiunti in versioni diverse.

- I tipi nel componente possono derivare da tipi di Windows Runtime. I controlli possono derivare dai tipi di controllo primitivi nello <xref:Windows.UI.Xaml.Controls.Primitives> spazio dei nomi o da controlli più finiti, ad esempio <xref:Windows.UI.Xaml.Controls.Button> .

  > [!IMPORTANT]
  > A partire da Windows 8 e dal .NET Framework 4,5, tutti i tipi pubblici in un componente Windows Runtime gestito devono essere sealed. Un tipo in un altro componente Windows Runtime non può derivare da essi. Se si desidera fornire il comportamento polimorfico nel componente, è possibile creare un'interfaccia e implementarla nei tipi polimorfici.

- Tutti i tipi di parametro e i tipi restituiti sui tipi pubblici nel componente devono essere Windows Runtime tipi (inclusi i tipi di Windows Runtime definiti dal componente).

Nelle sezioni seguenti vengono forniti esempi di scenari comuni.

### <a name="application-logic-for-a-windows-8x-store-app-with-javascript"></a>Logica dell'applicazione per un'app di Windows 8. x Store con JavaScript

Quando si sviluppa un'app di Windows 8. x Store per Windows usando JavaScript, è possibile che alcune parti della logica dell'applicazione migliorino nel codice gestito o siano più facili da sviluppare. Con JavaScript non è possibile utilizzare direttamente le librerie di classi .NET Framework, ma si può rendere la libreria di classi un file con estensione WinMD. In questo scenario, il componente Windows Runtime è parte integrante dell'app, pertanto non ha senso fornire attributi di versione.

### <a name="reusable-windows-8x-store-ui-controls"></a>Controlli dell'interfaccia utente di Windows 8. x Store riutilizzabili

È possibile creare un pacchetto di un set di controlli dell'interfaccia utente correlati in un componente Windows Runtime riutilizzabile. Il componente può essere commercializzato da solo o utilizzato come elemento nelle applicazioni create. In questo scenario, è opportuno utilizzare l' <xref:Windows.Foundation.Metadata.VersionAttribute> attributo Windows Runtime per migliorare la compatibilità.

### <a name="reusable-application-logic-from-existing-net-framework-apps"></a>Logica di un'applicazione riutilizzabile da applicazioni .NET Framework esistenti

È possibile creare un pacchetto di codice gestito dalle applicazioni desktop esistenti come componente Windows Runtime autonomo. In questo modo è possibile usare il componente nelle app di Windows 8. x Store compilate con C++ o JavaScript, nonché nelle app di Windows 8. x Store compilate con C# o Visual Basic. Il controllo delle versioni rappresenta un'opzione in caso di più scenari di riutilizzo del codice.

## <a name="related-topics"></a>Argomenti correlati

|Titolo|Descrizione|
|-----------|-----------------|
|[Panoramica di .NET per le app di Windows Store](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140))|Vengono descritti i tipi di .NET Framework e i membri che è possibile usare per creare app di Windows 8. x Store e Windows RuntimeComponents. In Dev Center di Windows.|
|[Guida di orientamento per app di Windows Store in C# o Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/br229583(v=win.10))|Fornisce le risorse principali per iniziare a sviluppare app di Windows 8. x Store usando C# o Visual Basic, inclusi molti argomenti, linee guida e procedure consigliate per la Guida introduttiva. In Dev Center di Windows.|
|[Procedure (XAML)](https://docs.microsoft.com/previous-versions/windows/apps/br229566(v=win.10))|Fornisce le risorse principali per iniziare a sviluppare app di Windows 8. x Store usando C# o Visual Basic, inclusi molti argomenti, linee guida e procedure consigliate per la Guida introduttiva. In Dev Center di Windows.|
|[Creazione di componenti Windows Runtime in C# e Visual Basic](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic)|Viene descritto come creare un componente Windows Runtime usando il .NET Framework, spiega come usarlo come parte di un'app di Windows 8. x Store compilata per Windows usando JavaScript e viene descritto come eseguire il debug della combinazione con Visual Studio. In Dev Center di Windows.|
|[Informazioni di riferimento su Windows Runtime](/uwp/api/)|Documentazione di riferimento per la Windows Runtime. In Dev Center di Windows.|
|[Passaggio di un URI a Windows Runtime](passing-a-uri-to-the-windows-runtime.md)|Descrive un problema che può verificarsi quando si passa un URI dal codice gestito al Windows Runtime e come evitarlo.|
