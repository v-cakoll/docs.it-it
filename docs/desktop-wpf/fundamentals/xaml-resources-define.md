---
title: Definire le risorse XAML
description: Informazioni sulle risorse XAML in WPF per .NET Core. Comprendere i tipi di risorse XAML e apprendere come definire le risorse XAML.
author: thraka
ms.author: adegeo
ms.date: 08/21/2019
ms.openlocfilehash: b278bb92afc308578d60e347871e0150b26a95db
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "82071283"
---
# <a name="overview-of-xaml-resources"></a>Panoramica delle risorse XAML

Una risorsa è un oggetto che può essere riutilizzato in posizioni diverse nell'app. Sono esempi di risorse pennelli e stili. In questa panoramica viene descritto come usare le risorse in Extensible Application Markup Language (XAML). È anche possibile creare e accedere alle risorse usando il codice.

> [!NOTE]
> Le risorse XAML descritte in questo articolo sono diverse dalle *risorse dell'app* , che sono in genere file aggiunti a un'app, ad esempio contenuto, dati o file incorporati.

<!-- TODO: File redirect from docs\framework\wpf\advanced\xaml-resources.md -->

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="using-resources-in-xaml"></a>Uso delle risorse in XAML

Nell'esempio seguente viene definito <xref:System.Windows.Media.SolidColorBrush> un come risorsa nell'elemento radice di una pagina. L'esempio fa quindi riferimento alla risorsa e la usa per impostare le proprietà di diversi elementi figlio, <xref:System.Windows.Shapes.Ellipse>inclusi un <xref:System.Windows.Controls.TextBlock>oggetto, un <xref:System.Windows.Controls.Button>oggetto e un oggetto.

[!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]

Ogni elemento a livello di Framework<xref:System.Windows.FrameworkElement> ( <xref:System.Windows.FrameworkContentElement>o) ha <xref:System.Windows.FrameworkElement.Resources%2A> una proprietà, che è <xref:System.Windows.ResourceDictionary> un tipo che contiene le risorse definite. È possibile definire le risorse per qualsiasi elemento, ad esempio <xref:System.Windows.Controls.Button>. Tuttavia, le risorse vengono spesso definite nell'elemento radice, che è <xref:System.Windows.Controls.Page> nell'esempio.

Ogni risorsa in un dizionario risorse deve avere una chiave univoca. Quando si definiscono le risorse nel markup, si assegna la chiave univoca tramite la [direttiva x:Key](../xaml-services/xkey-directive.md). In genere, la chiave è una stringa. È tuttavia possibile impostare la chiave su altri tipi di oggetto tramite le estensioni di markup appropriate. Le chiavi non di tipo stringa per le risorse vengono utilizzate da determinate aree di funzionalità in WPF, in particolare per gli stili, le risorse componenti e lo stile dei dati.

È possibile usare una risorsa definita con la sintassi dell'estensione di markup della risorsa che specifica il nome della chiave della risorsa. Ad esempio, usare la risorsa come valore di una proprietà in un altro elemento.

[!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]

Nell'esempio `{StaticResource MyBrush}` precedente, quando il caricatore XAML elabora il valore per la <xref:System.Windows.Controls.Control.Background%2A> proprietà in <xref:System.Windows.Controls.Button>, la logica di ricerca delle risorse verifica prima di tutto il dizionario <xref:System.Windows.Controls.Button> risorse per l'elemento. Se <xref:System.Windows.Controls.Button> non dispone di una definizione della chiave `MyBrush` di risorsa (in questo esempio, la relativa raccolta di risorse è vuota), la ricerca successiva controlla l'elemento padre <xref:System.Windows.Controls.Button>di, ovvero <xref:System.Windows.Controls.Page>. Se si definisce una risorsa sull'elemento <xref:System.Windows.Controls.Page> radice, tutti gli elementi nell'albero logico di <xref:System.Windows.Controls.Page> possono accedervi. È anche possibile riutilizzare la stessa risorsa per impostare il valore di qualsiasi proprietà che accetti lo stesso tipo rappresentato dalla risorsa. Nell'esempio precedente, `MyBrush` la stessa risorsa imposta due proprietà diverse: la <xref:System.Windows.Controls.Control.Background%2A> proprietà di un <xref:System.Windows.Controls.Button>oggetto e la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà di <xref:System.Windows.Shapes.Rectangle>un oggetto.

## <a name="static-and-dynamic-resources"></a>Risorse statiche e dinamiche

È possibile fare riferimento a una risorsa come statica o dinamica. I riferimenti vengono creati usando l' [estensione di markup StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md) o l' [estensione di markup DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md). Un'estensione di markup è una funzionalità XAML che consente di specificare un riferimento a un oggetto mediante l'estensione di markup che elabora la stringa dell'attributo e restituisce l'oggetto a un caricatore XAML. Per altre informazioni sul comportamento dell'estensione di markup, vedere [estensioni di markup e XAML WPF](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

Quando si usa un'estensione di markup, in genere si forniscono uno o più parametri in formato stringa elaborati da un'estensione di markup particolare. L' [estensione di markup StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md) elabora una chiave cercando il valore della chiave in tutti i dizionari risorse disponibili. L'elaborazione viene eseguita durante il caricamento, ovvero quando il processo di caricamento deve assegnare il valore della proprietà. L' [estensione di markup DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md) elabora invece una chiave creando un'espressione e tale espressione rimane non valutata fino a quando l'app non viene eseguita, a quel punto l'espressione viene valutata e fornisce un valore.

Quando si fa riferimento a una risorsa, la decisione di usare un riferimento di risorsa statica o un riferimento di risorsa dinamica può essere influenzata dalle considerazioni seguenti:

- Quando si determina la progettazione complessiva della modalità di creazione delle risorse per l'app (per pagina, nell'app, in XAML separato o in un assembly di sole risorse), tenere presente quanto segue:

- Funzionalità dell'app. Sono in corso l'aggiornamento delle risorse in tempo reale nei requisiti dell'app?
- Il comportamento di ricerca specifico del tipo di riferimento di risorsa.
- La proprietà o il tipo di risorsa specifico e il comportamento nativo di tale tipo.

## <a name="static-resources"></a>Risorse statiche

I riferimenti di risorse statiche sono ideali nelle circostanze seguenti:

- La progettazione dell'app concentra la maggior parte delle risorse nei dizionari risorse a livello di pagina o di applicazione. I riferimenti alle risorse statiche non vengono rivalutati in base ai comportamenti di runtime, ad esempio il ricaricamento di una pagina. Pertanto, è possibile che si verifichi un vantaggio in merito alle prestazioni per evitare un numero elevato di riferimenti a risorse dinamiche quando questi non sono necessari in base alla progettazione delle risorse e delle app.

- Si sta impostando il valore di una proprietà che non si <xref:System.Windows.DependencyObject> trova in <xref:System.Windows.Freezable>un oggetto o.

- Si sta creando un dizionario risorse che verrà compilato in una DLL e incluso in un pacchetto come parte dell'app o condiviso tra le app.

- Si sta creando un tema per un controllo personalizzato e si definiscono le risorse usate nei temi. In questo caso, non si desidera in genere il comportamento di ricerca dei riferimenti alle risorse dinamiche. si desidera invece il comportamento del riferimento a una risorsa statica in modo che la ricerca sia prevedibile e autonoma al tema. Con un riferimento a una risorsa dinamica, anche un riferimento all'interno di un tema viene lasciato non valutato fino alla fase di esecuzione. e c'è la possibilità che, quando il tema viene applicato, alcuni elementi locali ridefiniranno una chiave a cui il tema sta provando a fare riferimento e l'elemento locale rientrerà prima del tema stesso nella ricerca. In tal caso, il tema non si comporta come previsto.

- Si stanno usando risorse per impostare un numero elevato di proprietà di dipendenza. Le proprietà di dipendenza hanno una memorizzazione nella cache dei valori effettiva abilitata dal sistema di proprietà, pertanto se si fornisce un valore per una proprietà di dipendenza che può essere valutata in fase di caricamento, la proprietà di dipendenza non deve verificare la presenza di un'espressione rivalutata e può restituire l'ultimo valore effettivo. Questa tecnica può garantire un miglioramento delle prestazioni.

- Si desidera modificare la risorsa sottostante per tutti i consumer oppure si desidera mantenere istanze scrivibili separate per ogni consumer utilizzando l' [attributo x:Shared](../xaml-services/xshared-attribute.md).

### <a name="static-resource-lookup-behavior"></a>Comportamento di ricerca delle risorse statiche

Di seguito viene descritto il processo di ricerca che si verifica automaticamente quando una proprietà o un elemento fa riferimento a una risorsa statica:

01. Il processo di ricerca controlla la presenza della chiave richiesta all'interno del dizionario risorse definito dall'elemento che imposta la proprietà.

01. Il processo di ricerca attraversa quindi l'albero logico verso l'alto all'elemento padre e al relativo dizionario risorse. Questo processo continua fino a quando non viene raggiunto l'elemento radice.

01. Le risorse dell'app vengono controllate. Le risorse dell'app sono le risorse all'interno del dizionario risorse definito dall' <xref:System.Windows.Application> oggetto per l'app WPF.

I riferimenti di risorse statiche all'interno di un dizionario risorse devono fare riferimento a una risorsa già definita lessicalmente prima del riferimento. I riferimenti di risorse statiche non sono in grado di risolvere riferimenti in avanti. Per questo motivo, progettare la struttura del dizionario risorse in modo che le risorse vengano definite in corrispondenza o in prossimità dell'inizio di ogni rispettivo dizionario risorse.

La ricerca di risorse statiche può estendersi nei temi o nelle risorse di sistema, ma questa ricerca è supportata solo perché il caricatore XAML rinvia la richiesta. Il rinvio è necessario in modo che il tema del runtime al momento del caricamento della pagina venga applicato correttamente all'app. Tuttavia, i riferimenti a risorse statiche a chiavi note a esistere solo nei temi o come risorse di sistema non sono consigliate, perché tali riferimenti non vengono rivalutati se il tema viene modificato dall'utente in tempo reale. Un riferimento di risorsa dinamica è più affidabile se si richiedono risorse di tema o di sistema. Fa eccezione il caso in cui un elemento tema stesso richieda un'altra risorsa. Per i motivi descritti in precedenza, questi riferimenti devono essere riferimenti di risorse statiche.

Il comportamento dell'eccezione se non viene trovato un riferimento a una risorsa statica varia. Se la risorsa è stata rinviata, l'eccezione si verifica in runtime. Se la risorsa non è stata rinviata, l'eccezione si verifica al momento del caricamento.

## <a name="dynamic-resources"></a>Risorse dinamiche

Le risorse dinamiche funzionano meglio nei casi seguenti:

- Il valore della risorsa, incluse le risorse di sistema o le risorse che sono altrimenti impostabili dall'utente, dipende dalle condizioni che non sono note fino al runtime. È ad esempio possibile creare valori Setter che fanno riferimento alle proprietà di sistema <xref:System.Windows.SystemColors>esposte <xref:System.Windows.SystemFonts>da, <xref:System.Windows.SystemParameters>o. Questi valori sono realmente dinamici perché in ultima analisi derivano dall'ambiente di runtime dell'utente e dal sistema operativo. È anche possibile che eventuali temi a livello di applicazione siano soggetti a modifica e che l'accesso alle risorse a livello di pagina debba anche acquisire la modifica.

- Si stanno creando o facendo riferimento a stili di tema per un controllo personalizzato.

- Si intende modificare il contenuto di un <xref:System.Windows.ResourceDictionary> durante la durata di un'app.

- La struttura delle risorse è complessa e con interdipendenze e potrebbe richiedere riferimenti in avanti. I riferimenti alle risorse statiche non supportano i riferimenti in diretta, ma i riferimenti alle risorse dinamiche le supportano perché la risorsa non deve essere valutata fino al runtime e i riferimenti in diretta non sono pertanto un concetto pertinente.

- Si fa riferimento a una risorsa di grandi dimensioni dal punto di vista di una compilazione o di una working set e la risorsa potrebbe non essere utilizzata immediatamente quando viene caricata la pagina. I riferimenti a risorse statiche vengono sempre caricati da XAML quando viene caricata la pagina. Tuttavia, un riferimento a una risorsa dinamica non viene caricato fino a quando non viene utilizzato.

- Si sta creando uno stile in cui i valori Setter possono provenire da altri valori influenzati da temi o altre impostazioni utente.

- Si applicano risorse a elementi che possono essere associati a un nuovo elemento padre nell'albero logico durante la durata dell'app. La modifica dell'elemento padre cambia potenzialmente anche l'ambito di ricerca. Se quindi si vuole che la risorsa per un elemento associato a un nuovo elemento padre sia rivalutata in base al nuovo ambito, usare sempre un riferimento di risorsa dinamica.

### <a name="dynamic-resource-lookup-behavior"></a>Comportamento di ricerca delle risorse dinamiche

Il comportamento di ricerca delle risorse per un riferimento a una risorsa dinamica è parallelo al comportamento di ricerca <xref:System.Windows.FrameworkElement.FindResource%2A> nel <xref:System.Windows.FrameworkElement.SetResourceReference%2A>codice se si chiama o:

01. La ricerca controlla la chiave richiesta all'interno del dizionario risorse definito dall'elemento che imposta la proprietà:

    - Se l'elemento definisce una <xref:System.Windows.FrameworkElement.Style%2A> proprietà, l' <xref:System.Windows.FrameworkElement.Style?displayProperty=fullName> oggetto dell'elemento ha il <xref:System.Windows.Style.Resources> relativo dizionario selezionato.

    - Se l'elemento definisce una <xref:System.Windows.Controls.Control.Template%2A> proprietà, il <xref:System.Windows.FrameworkTemplate.Resources?displayProperty=fullName> dizionario dell'elemento viene selezionato.

01. La ricerca attraversa l'albero logico verso l'alto all'elemento padre e al relativo dizionario risorse. Questo processo continua fino a quando non viene raggiunto l'elemento radice.

01. Le risorse dell'app vengono controllate. Le risorse dell'app sono le risorse all'interno del dizionario risorse definite dall' <xref:System.Windows.Application> oggetto per l'app WPF.

01. Il tema del dizionario risorse del tema è selezionato per il tema attualmente attivo. Se il tema viene modificato in runtime, il valore viene rivalutato.

01. Vengono controllate le risorse di sistema.

Il comportamento di eventuali eccezioni varia:

- Se una risorsa è stata richiesta da <xref:System.Windows.FrameworkElement.FindResource%2A> una chiamata e non è stata trovata, viene generata un'eccezione.

- Se una risorsa è stata richiesta da <xref:System.Windows.FrameworkElement.TryFindResource%2A> una chiamata e non è stata trovata, non viene generata alcuna eccezione e il valore `null`restituito è. Se la proprietà impostata non accetta `null`, è comunque possibile che venga generata un'eccezione più profonda, a seconda della singola proprietà da impostare.

- Se una risorsa è stata richiesta da un riferimento a una risorsa dinamica in XAML e non è stata trovata, il comportamento dipende dal sistema di proprietà generale. Il comportamento generale è come se non fosse stata eseguita un'operazione di impostazione delle proprietà a livello di risorsa. Se, ad esempio, si tenta di impostare lo sfondo di un singolo elemento Button usando una risorsa che non è stato possibile valutare, non viene restituito alcun valore, ma il valore effettivo può comunque provenire da altri partecipanti nel sistema di proprietà e nella precedenza dei valori. Il valore dello sfondo, ad esempio, può provenire da uno stile di pulsante definito localmente o dallo stile del tema. Per le proprietà che non sono definite dagli stili del tema, il valore effettivo dopo una valutazione di risorse non riuscite potrebbe derivare dal valore predefinito nei metadati della proprietà.

### <a name="restrictions"></a>Restrizioni

I riferimenti di risorse dinamiche presentano alcune restrizioni rilevanti. È necessario che sia soddisfatta almeno una delle condizioni seguenti:

- La proprietà impostata deve essere una proprietà di un oggetto <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Tale proprietà deve essere supportata da un oggetto <xref:System.Windows.DependencyProperty>.

- Il riferimento è relativo a un valore all' `StyleSetter`interno di un oggetto.

- La proprietà impostata deve essere una proprietà di un oggetto <xref:System.Windows.Freezable> fornito come valore di una <xref:System.Windows.FrameworkElement> proprietà o <xref:System.Windows.FrameworkContentElement> oppure di un <xref:System.Windows.Setter> valore.

Poiché la proprietà impostata deve essere una <xref:System.Windows.DependencyProperty> proprietà o <xref:System.Windows.Freezable> , la maggior parte delle modifiche alle proprietà può propagarsi all'interfaccia utente perché una modifica di proprietà (il valore della risorsa dinamica modificata) viene riconosciuta dal sistema di proprietà. La maggior parte dei controlli include la logica che forza un altro layout di <xref:System.Windows.DependencyProperty> un controllo se una modifica e tale proprietà potrebbe influire sul layout. Tuttavia, non tutte le proprietà che dispongono di un' [estensione di markup DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md) come valore sono garantite per fornire aggiornamenti in tempo reale nell'interfaccia utente. Tale funzionalità può comunque variare a seconda della proprietà, nonché a seconda del tipo proprietario della proprietà o anche della struttura logica dell'app.

## <a name="styles-datatemplates-and-implicit-keys"></a>Stili, DataTemplate e chiavi implicite

Sebbene tutti gli elementi in <xref:System.Windows.ResourceDictionary> un oggetto debbano avere una chiave, questo non significa che tutte le risorse `x:Key`devono avere un oggetto esplicito. Diversi tipi di oggetto supportano una chiave implicita quando sono definiti come risorsa in cui il valore della chiave è associato al valore di un'altra proprietà. Questo tipo di chiave è noto come chiave implicita, mentre un `x:Key` attributo è una chiave esplicita. È possibile sovrascrivere qualsiasi chiave implicita specificando una chiave esplicita.

Uno scenario importante per le risorse è quando si definisce <xref:System.Windows.Style>un. In realtà, un <xref:System.Windows.Style> è quasi sempre definito come una voce in un dizionario risorse, perché gli stili sono intrinsecamente progettati per il riutilizzo. Per altre informazioni sugli stili, vedere applicazione di stili [e modelli](styles-templates-overview.md).

Una chiave implicita consente sia di creare stili per controlli che di fare riferimento ad essi. Gli stili di tema che definiscono l'aspetto predefinito di un controllo si basano sulla chiave implicita. Dal punto di vista della richiesta, la chiave implicita è la <xref:System.Type> del controllo stesso. Dal punto di vista della definizione delle risorse, la chiave implicita <xref:System.Windows.Style.TargetType%2A> è il dello stile. Di conseguenza, se si creano temi per i controlli personalizzati o si creano stili che interagiscono con gli stili del tema esistenti, non è necessario specificare una [direttiva x:Key](../xaml-services/xkey-directive.md) <xref:System.Windows.Style>. E se si vogliono usare stili con tema, non è necessario specificare alcuno stile. Ad esempio, la definizione di stile seguente funziona anche se la <xref:System.Windows.Style> risorsa non presenta una chiave:

[!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]

Lo stile ha effettivamente una chiave, ovvero la chiave `typeof(System.Windows.Controls.Button)`implicita. Nel markup è possibile specificare <xref:System.Windows.Style.TargetType%2A> direttamente come nome del tipo (oppure è possibile usare facoltativamente [{x:Type...}](../xaml-services/xtype-markup-extension.md) per restituire un <xref:System.Type>oggetto.

Attraverso i meccanismi di stile del tema predefiniti usati da WPF, lo stile viene applicato come stile di runtime <xref:System.Windows.Controls.Button> di un oggetto nella pagina, anche <xref:System.Windows.Controls.Button> se non tenta di specificare la <xref:System.Windows.FrameworkElement.Style%2A> proprietà o un riferimento a una risorsa specifica nello stile. Lo stile definito nella pagina viene trovato in precedenza nella sequenza di ricerca rispetto allo stile del dizionario dei temi, usando la stessa chiave dello stile del dizionario del tema. È possibile specificare `<Button>Hello</Button>` semplicemente un punto qualsiasi della pagina e lo stile definito con <xref:System.Windows.Style.TargetType%2A> `Button` si applica a tale pulsante. Se lo si desidera, è comunque possibile impostare in modo esplicito come <xref:System.Windows.Style.TargetType%2A> chiave lo stile con lo stesso valore di tipo di per chiarezza nel markup, ma questo è facoltativo.

Le chiavi implicite per gli stili non si applicano <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> a `true`un controllo se è. Si noti anche che <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> può essere impostato come parte del comportamento nativo per la classe del controllo, anziché in modo esplicito in un'istanza del controllo. Inoltre, per supportare le chiavi implicite per gli scenari di classi derivate, <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> il controllo deve eseguire l'override di (tutti i controlli esistenti forniti come parte di WPF includono questo override). Per ulteriori informazioni su stili, temi e progettazione di controlli, vedere [linee guida per la progettazione di controlli Stylable](../../framework/wpf/controls/guidelines-for-designing-stylable-controls.md).

<xref:System.Windows.DataTemplate>dispone inoltre di una chiave implicita. La chiave implicita per <xref:System.Windows.DataTemplate> un oggetto <xref:System.Windows.DataTemplate.DataType%2A> è il valore della proprietà. <xref:System.Windows.DataTemplate.DataType%2A>può anche essere specificato come nome del tipo anziché usare in modo esplicito [{x:Type...}](../xaml-services/xtype-markup-extension.md). Per informazioni dettagliate, vedere [Cenni preliminari sui modelli di dati](../../framework/wpf/data/data-templating-overview.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.ResourceDictionary>
- [Risorse dell'applicazione](../../framework/wpf/advanced/optimizing-performance-application-resources.md)
- [Risorse e codice](../../framework/wpf/advanced/resources-and-code.md)
- [Definire e fare riferimento a una risorsa](../../framework/wpf/advanced/how-to-define-and-reference-a-resource.md)
- [Panoramica sulla gestione delle applicazioni](../../framework/wpf/app-development/application-management-overview.md)
- [estensione di markup x:Type](../xaml-services/xtype-markup-extension.md)
- [Estensione di markup StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md)
- [Estensione di markup DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md)
