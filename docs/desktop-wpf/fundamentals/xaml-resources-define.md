---
title: Definire le risorse XAMLDefine XAML resources
description: Informazioni sulle risorse XAML in WPF per .NET Core.Learn about XAML resources in WPF for .NET Core. Comprendere i tipi di risorse XAML e informazioni su come definire le risorse XAML.
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

Una risorsa è un oggetto che può essere riutilizzato in posizioni diverse dell'app. Sono esempi di risorse pennelli e stili. Questa panoramica descrive come usare le risorse in XAML (Extensible Application Markup Language). È inoltre possibile creare e accedere alle risorse tramite codice.

> [!NOTE]
> Le risorse XAML descritte in questo articolo sono diverse dalle *risorse dell'app* che in genere vengono aggiunte a un'app, ad esempio contenuto, dati o file incorporati.

<!-- TODO: File redirect from docs\framework\wpf\advanced\xaml-resources.md -->

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="using-resources-in-xaml"></a>Uso delle risorse in XAMLUsing resources in XAML

Nell'esempio seguente <xref:System.Windows.Media.SolidColorBrush> viene definita una risorsa nell'elemento radice di una pagina. Nell'esempio viene quindi fatto riferimento alla risorsa e viene <xref:System.Windows.Shapes.Ellipse>utilizzata <xref:System.Windows.Controls.TextBlock>per <xref:System.Windows.Controls.Button>impostare le proprietà di diversi elementi figlio, tra cui un oggetto , un , e un oggetto .

[!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]

Ogni elemento a<xref:System.Windows.FrameworkElement> livello <xref:System.Windows.FrameworkContentElement>di <xref:System.Windows.FrameworkElement.Resources%2A> framework ( o <xref:System.Windows.ResourceDictionary> ) dispone di una proprietà, ovvero un tipo che contiene risorse definite. È possibile definire le risorse su <xref:System.Windows.Controls.Button>qualsiasi elemento, ad esempio un oggetto . Tuttavia, le risorse sono più spesso <xref:System.Windows.Controls.Page> definite nell'elemento radice, che è nell'esempio.

Ogni risorsa in un dizionario risorse deve avere una chiave univoca. Quando si definiscono le risorse nel markup, si assegna la chiave univoca tramite la [direttiva x:Key](../xaml-services/xkey-directive.md). In genere, la chiave è una stringa. È tuttavia possibile impostare la chiave su altri tipi di oggetto tramite le estensioni di markup appropriate. Le chiavi non stringa per le risorse vengono usate da determinate aree di funzionalità in WPFWPF, in particolare per gli stili, le risorse dei componenti e l'applicazione di stili ai dati.

È possibile usare una risorsa definita con la sintassi dell'estensione di markup della risorsa che specifica il nome della chiave della risorsa. Ad esempio, utilizzare la risorsa come valore di una proprietà in un altro elemento.

[!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]

Nell'esempio precedente, quando il caricatore XAML `{StaticResource MyBrush}` elabora <xref:System.Windows.Controls.Control.Background%2A> il <xref:System.Windows.Controls.Button>valore della proprietà in , la <xref:System.Windows.Controls.Button> logica di ricerca delle risorse controlla innanzitutto il dizionario risorse per l'elemento. Se <xref:System.Windows.Controls.Button> non dispone di una definizione della chiave `MyBrush` di risorsa (in questo esempio no; la relativa <xref:System.Windows.Controls.Button>raccolta <xref:System.Windows.Controls.Page>di risorse è vuota), la ricerca controlla l'elemento padre di , ovvero . Se si definisce <xref:System.Windows.Controls.Page> una risorsa nell'elemento radice, tutti <xref:System.Windows.Controls.Page> gli elementi nell'albero logico dell'oggetto possono accedervi. È inoltre possibile riutilizzare la stessa risorsa per impostare il valore di qualsiasi proprietà che accetta lo stesso tipo rappresentato dalla risorsa. Nell'esempio precedente la `MyBrush` stessa risorsa imposta <xref:System.Windows.Controls.Control.Background%2A> due <xref:System.Windows.Controls.Button>proprietà diverse: la di un oggetto , e la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà di . <xref:System.Windows.Shapes.Rectangle>

## <a name="static-and-dynamic-resources"></a>Risorse statiche e dinamiche

È possibile fare riferimento a una risorsa come statica o dinamica. I riferimenti vengono creati utilizzando l'estensione di [markup StaticResource](../../framework/wpf/advanced/staticresource-markup-extension.md) o [DynamicResource Markup Extension](../../framework/wpf/advanced/dynamicresource-markup-extension.md). Un'estensione di markup è una funzionalità XAML che consente di specificare un riferimento a un oggetto facendo in modo che l'estensione di markup elabori la stringa dell'attributo e restituisca l'oggetto a un caricatore XAML. Per altre informazioni sul comportamento dell'estensione di markup, vedere [Estensioni di markup e XAML WPF.](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)

Quando si utilizza un'estensione di markup, in genere si forniscono uno o più parametri in formato stringa elaborati da quella particolare estensione di markup. StaticResource [Markup Extension](../../framework/wpf/advanced/staticresource-markup-extension.md) elabora una chiave cercando il valore di tale chiave in tutti i dizionari risorse disponibili. L'elaborazione avviene durante il caricamento, ovvero quando il processo di caricamento deve assegnare il valore della proprietà. L'estensione di [markup DynamicResource](../../framework/wpf/advanced/dynamicresource-markup-extension.md) elabora invece una chiave creando un'espressione e tale espressione rimane non valutata fino all'esecuzione dell'app, al momento in cui l'espressione viene valutata e fornisce un valore.

Quando si fa riferimento a una risorsa, la decisione di usare un riferimento di risorsa statica o un riferimento di risorsa dinamica può essere influenzata dalle considerazioni seguenti:

- Quando determini la progettazione complessiva della modalità di creazione delle risorse per l'app (per pagina, nell'app, in XAML separato o in un assembly di sole risorse), tieni presente quanto segue:

- Funzionalità dell'app. L'aggiornamento delle risorse in tempo reale fa parte dei requisiti dell'app?
- Il comportamento di ricerca specifico del tipo di riferimento di risorsa.
- La proprietà o il tipo di risorsa specifico e il comportamento nativo di tale tipo.

## <a name="static-resources"></a>Risorse statiche

I riferimenti di risorse statiche sono ideali nelle circostanze seguenti:

- La progettazione dell'app concentra la maggior parte delle risorse in dizionari risorse a livello di pagina o di applicazione. I riferimenti alle risorse statiche non vengono rivalutati in base ai comportamenti di runtime, ad esempio il ricaricamento di una pagina. Pertanto, possono essere disponibili alcuni vantaggi in termini di prestazioni per evitare un numero elevato di riferimenti a risorse dinamiche quando non sono necessari in base alla progettazione della risorsa e dell'app.

- Si sta impostando il valore di una proprietà <xref:System.Windows.DependencyObject> che <xref:System.Windows.Freezable>non si trovi su un oggetto o un oggetto .

- Si sta creando un dizionario risorse che verrà compilato in una DLL e incluso nel pacchetto come parte dell'app o condiviso tra le app.

- Si sta creando un tema per un controllo personalizzato e si definiscono le risorse utilizzate all'interno dei temi. In questo caso, in genere non si desidera il comportamento di ricerca dei riferimenti alle risorse dinamiche. si desidera invece il comportamento di riferimento di risorsa statica in modo che la ricerca sia prevedibile e indipendente al tema. Con un riferimento di risorsa dinamica, anche un riferimento all'interno di un tema viene lasciato non valutato fino alla fase di esecuzione. e c'è la possibilità che quando il tema viene applicato, qualche elemento locale ridefinirà una chiave che il tema sta tentando di fare riferimento, e l'elemento locale cadrà prima del tema stesso nella ricerca. In questo caso, il tema non si comporterà come previsto.

- Si usano le risorse per impostare un numero elevato di proprietà di dipendenza. Le proprietà di dipendenza hanno un valore efficace nella cache come abilitato dal sistema di proprietà, pertanto se si fornisce un valore per una proprietà di dipendenza che può essere valutata in fase di caricamento, la proprietà di dipendenza non deve verificare la presenza di un'espressione rivalutata e può restituire l'ultimo valore effettivo. Questa tecnica può garantire un miglioramento delle prestazioni.

- Si desidera modificare la risorsa sottostante per tutti i consumer oppure si desidera mantenere istanze scrivibili separate per ogni consumer utilizzando [l'attributo x:Shared](../xaml-services/xshared-attribute.md).

### <a name="static-resource-lookup-behavior"></a>Comportamento di ricerca delle risorse statiche

Di seguito viene descritto il processo di ricerca che si verifica automaticamente quando una risorsa statica fa riferimento a una proprietà o un elemento:The following describes the lookup process that happens automatically when a static resource is referenced by a property or element:

01. Il processo di ricerca controlla la presenza della chiave richiesta all'interno del dizionario risorse definito dall'elemento che imposta la proprietà.

01. Il processo di ricerca attraversa quindi l'albero logico verso l'alto fino all'elemento padre e al relativo dizionario risorse. Questo processo continua fino a quando non viene raggiunto l'elemento radice.

01. Le risorse dell'app vengono controllate. Le risorse dell'app sono quelle risorse <xref:System.Windows.Application> all'interno del dizionario risorse definito dall'oggetto per l'app WPF.

I riferimenti di risorse statiche all'interno di un dizionario risorse devono fare riferimento a una risorsa già definita lessicalmente prima del riferimento. I riferimenti di risorse statiche non sono in grado di risolvere riferimenti in avanti. Per questo motivo, progettare la struttura del dizionario risorse in modo che le risorse siano definite all'inizio o vicino all'inizio di ogni rispettivo dizionario risorse.

La ricerca di risorse statiche può estendersi nei temi o nelle risorse di sistema, ma questa ricerca è supportata solo perché il caricatore XAML rinvia la richiesta. Il rinvio è necessario in modo che il tema di runtime al momento del caricamento della pagina venga applicato correttamente all'app. Tuttavia, i riferimenti alle risorse statiche alle chiavi che sono noti per esistere solo nei temi o come risorse di sistema non sono consigliati, perché tali riferimenti non vengono rivalutati se il tema viene modificato dall'utente in tempo reale. Un riferimento di risorsa dinamica è più affidabile se si richiedono risorse di tema o di sistema. Fa eccezione il caso in cui un elemento tema stesso richieda un'altra risorsa. Per i motivi descritti in precedenza, questi riferimenti devono essere riferimenti di risorse statiche.

Il comportamento dell'eccezione se non viene trovato un riferimento a una risorsa statica varia. Se la risorsa è stata rinviata, l'eccezione si verifica in runtime. Se la risorsa non è stata rinviata, l'eccezione si verifica al momento del caricamento.

## <a name="dynamic-resources"></a>Risorse dinamiche

Le risorse dinamiche funzionano meglio quando:Dynamic resources work best when:

- Il valore della risorsa, incluse le risorse di sistema o le risorse che sono altrimenti impostabili dall'utente, dipende da condizioni che non sono note fino al runtime. Ad esempio, è possibile creare valori setter che <xref:System.Windows.SystemColors> <xref:System.Windows.SystemFonts>fanno <xref:System.Windows.SystemParameters>riferimento alle proprietà di sistema esposte da , , o . Questi valori sono realmente dinamici perché in ultima analisi derivano dall'ambiente di runtime dell'utente e dal sistema operativo. È anche possibile che eventuali temi a livello di applicazione siano soggetti a modifica e che l'accesso alle risorse a livello di pagina debba anche acquisire la modifica.

- Si stanno creando o facendo riferimento agli stili del tema per un controllo personalizzato.

- Si intende regolare il <xref:System.Windows.ResourceDictionary> contenuto di un oggetto durante la durata di un'app.

- La struttura delle risorse è complessa e con interdipendenze e potrebbe richiedere riferimenti in avanti. I riferimenti alle risorse statiche non supportano i riferimenti in avanti, ma i riferimenti alle risorse dinamiche li supportano perché la risorsa non deve essere valutata fino al runtime e i riferimenti in avanti non sono pertanto un concetto rilevante.

- Si fa riferimento a una risorsa di grandi dimensioni dal punto di vista di una compilazione o di un working set e la risorsa potrebbe non essere utilizzata immediatamente al caricamento della pagina. I riferimenti alle risorse statiche vengono sempre caricati da XAML al caricamento della pagina. Tuttavia, un riferimento di risorsa dinamica non viene caricato fino a quando non viene utilizzato.

- Stai creando uno stile in cui i valori di setter potrebbero provenire da altri valori che sono influenzati da temi o altre impostazioni utente.

- Si stanno applicando risorse a elementi che potrebbero essere riassociati nell'albero logico durante la durata dell'app. La modifica dell'elemento padre cambia potenzialmente anche l'ambito di ricerca. Se quindi si vuole che la risorsa per un elemento associato a un nuovo elemento padre sia rivalutata in base al nuovo ambito, usare sempre un riferimento di risorsa dinamica.

### <a name="dynamic-resource-lookup-behavior"></a>Comportamento di ricerca delle risorse dinamiche

Il comportamento di ricerca delle risorse per un riferimento a <xref:System.Windows.FrameworkElement.FindResource%2A> <xref:System.Windows.FrameworkElement.SetResourceReference%2A>una risorsa dinamica è parallelo al comportamento di ricerca nel codice se si chiama o :

01. La ricerca verifica la chiave richiesta all'interno del dizionario risorse definito dall'elemento che imposta la proprietà:The lookup checks for the requested key within the resource dictionary defined by the element that sets the property:

    - Se l'elemento <xref:System.Windows.FrameworkElement.Style%2A> definisce <xref:System.Windows.FrameworkElement.Style?displayProperty=fullName> una proprietà, <xref:System.Windows.Style.Resources> l'elemento ha il dizionario controllato.

    - Se l'elemento <xref:System.Windows.Controls.Control.Template%2A> definisce <xref:System.Windows.FrameworkTemplate.Resources?displayProperty=fullName> una proprietà, il dizionario dell'elemento viene controllato.

01. La ricerca attraversa l'albero logico verso l'alto fino all'elemento padre e al relativo dizionario risorse. Questo processo continua fino a quando non viene raggiunto l'elemento radice.

01. Le risorse dell'app vengono controllate. Le risorse dell'app sono quelle risorse <xref:System.Windows.Application> all'interno del dizionario risorse definite dall'oggetto per l'app WPF.

01. Il dizionario risorse del tema viene controllato per il tema attualmente attivo. Se il tema viene modificato in runtime, il valore viene rivalutato.

01. Vengono controllate le risorse di sistema.

Il comportamento di eventuali eccezioni varia:

- Se una risorsa è <xref:System.Windows.FrameworkElement.FindResource%2A> stata richiesta da una chiamata e non è stata trovata, viene generata un'eccezione.

- Se una risorsa è <xref:System.Windows.FrameworkElement.TryFindResource%2A> stata richiesta da una chiamata e non è `null`stata trovata, non viene generata alcuna eccezione e il valore restituito è . Se la proprietà impostata `null`non accetta , è comunque possibile che venga generata un'eccezione più profonda, a seconda della singola proprietà impostata.

- Se una risorsa è stata richiesta da un riferimento di risorsa dinamica in XAML e non è stata trovata, il comportamento dipende dal sistema di proprietà generale. Il comportamento generale è come se non si è verificata alcuna operazione di impostazione della proprietà al livello in cui è presente la risorsa. Ad esempio, se si tenta di impostare lo sfondo su un singolo elemento pulsante utilizzando una risorsa che non può essere valutata, non è stato possibile immettere alcun valore, ma il valore effettivo può comunque provenire da altri partecipanti al sistema di proprietà e dalla precedenza dei valori. Ad esempio, il valore di sfondo potrebbe ancora provenire da uno stile di pulsante definito localmente o dallo stile del tema. Per le proprietà che non sono definite dagli stili del tema, il valore effettivo dopo una valutazione della risorsa non riuscita potrebbe provenire dal valore predefinito nei metadati della proprietà.

### <a name="restrictions"></a>Restrizioni

I riferimenti di risorse dinamiche presentano alcune restrizioni rilevanti. Almeno una delle seguenti condizioni deve essere vera:

- La proprietà da impostare deve <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>essere una proprietà in un oggetto o . Tale proprietà deve essere <xref:System.Windows.DependencyProperty>supportata da un oggetto .

- Il riferimento è per `StyleSetter`un valore all'interno di un oggetto .

- La proprietà da impostare deve <xref:System.Windows.Freezable> essere una proprietà in <xref:System.Windows.FrameworkElement> un <xref:System.Windows.FrameworkContentElement> oggetto fornito <xref:System.Windows.Setter> come valore di una proprietà o o di proprietà o un valore.

Poiché la proprietà da <xref:System.Windows.DependencyProperty> <xref:System.Windows.Freezable> impostare deve essere una proprietà o , la maggior parte delle modifiche alle proprietà può propagarsi all'interfaccia utente perché una modifica della proprietà (il valore della risorsa dinamica modificata) viene riconosciuta dal sistema di proprietà. La maggior parte dei controlli include la <xref:System.Windows.DependencyProperty> logica che forzerà un altro layout di un controllo se una modifica e tale proprietà potrebbe influire sul layout. Tuttavia, non tutte le proprietà che hanno un [DynamicResource Markup Extension](../../framework/wpf/advanced/dynamicresource-markup-extension.md) come valore sono garantiti per fornire aggiornamenti in tempo reale nell'interfaccia utente. Tale funzionalità può comunque variare a seconda della proprietà, nonché a seconda del tipo che possiede la proprietà o anche la struttura logica dell'app.

## <a name="styles-datatemplates-and-implicit-keys"></a>Stili, DataTemplates e chiavi implicite

Anche se tutti <xref:System.Windows.ResourceDictionary> gli elementi in un oggetto deve avere una `x:Key`chiave, ciò non significa che tutte le risorse debbano avere un'esplicita . Diversi tipi di oggetto supportano una chiave implicita quando sono definiti come risorsa in cui il valore della chiave è associato al valore di un'altra proprietà. Questo tipo di chiave è noto `x:Key` come chiave implicita, mentre un attributo è una chiave esplicita. È possibile sovrascrivere qualsiasi chiave implicita specificando una chiave esplicita.

Uno scenario importante per le <xref:System.Windows.Style>risorse è quando si definisce un file . Infatti, <xref:System.Windows.Style> un oggetto è quasi sempre definito come una voce in un dizionario risorse, perché gli stili sono intrinsecamente destinati al riutilizzo. Per ulteriori informazioni sugli stili, consultate [Applicazione di stili e modelli.](styles-templates-overview.md)

Una chiave implicita consente sia di creare stili per controlli che di fare riferimento ad essi. Gli stili di tema che definiscono l'aspetto predefinito di un controllo si basano sulla chiave implicita. Dal punto di vista della richiesta, la <xref:System.Type> chiave implicita è il controllo stesso. Dal punto di vista della definizione delle <xref:System.Windows.Style.TargetType%2A> risorse, la chiave implicita è lo stile. Pertanto, se si creano temi per i controlli personalizzati o si creano stili che interagiscono con <xref:System.Windows.Style>gli stili del tema esistenti, non è necessario specificare una [direttiva x:Key](../xaml-services/xkey-directive.md) per tale . E se si vogliono usare stili con tema, non è necessario specificare alcuno stile. Ad esempio, la definizione di <xref:System.Windows.Style> stile seguente funziona, anche se la risorsa non sembra avere una chiave:For instance, the following style definition works, even though the resource doesn't appear to have a key:

[!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]

Quello stile ha davvero una chiave: la chiave implicita `typeof(System.Windows.Controls.Button)`. Nel markup, è <xref:System.Windows.Style.TargetType%2A> possibile specificare direttamente un nome di tipo (oppure è possibile utilizzare facoltativamente il nome del [tipo...](../xaml-services/xtype-markup-extension.md) per restituire <xref:System.Type>un file .

Tramite i meccanismi di stile del tema predefinito utilizzati da <xref:System.Windows.Controls.Button> WPFWPF, tale <xref:System.Windows.Controls.Button> stile viene applicato come <xref:System.Windows.FrameworkElement.Style%2A> stile di runtime di un nella pagina, anche se il sé non tenta di specificare la proprietà o un riferimento di risorsa specifico allo stile. Lo stile definito nella pagina si trova in precedenza nella sequenza di ricerca rispetto allo stile del dizionario dei temi, utilizzando la stessa chiave dello stile del dizionario dei temi. È possibile `<Button>Hello</Button>` specificare in qualsiasi punto della <xref:System.Windows.Style.TargetType%2A> pagina `Button` e lo stile definito da verrà applicato a tale pulsante. Se si desidera, è comunque possibile digitare <xref:System.Windows.Style.TargetType%2A> in modo esplicito lo stile con lo stesso valore di tipo come per chiarezza nel markup, ma che è facoltativo.

I tasti impliciti per gli <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> stili `true`non si applicano a un controllo se è . Si noti <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> inoltre che potrebbe essere impostato come parte del comportamento nativo per la classe del controllo, anziché in modo esplicito in un'istanza del controllo. Inoltre, per supportare le chiavi implicite per <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> gli scenari di classi derivate, il controllo deve eseguire l'override (tutti i controlli esistenti forniti come parte di WPFWPF includono questo override). Per ulteriori informazioni su stili, temi e progettazione di controlli, vedere Linee guida per la progettazione di [controlli stilizzati](../../framework/wpf/controls/guidelines-for-designing-stylable-controls.md).

<xref:System.Windows.DataTemplate>ha anche una chiave implicita. La chiave implicita per un <xref:System.Windows.DataTemplate> è il valore della <xref:System.Windows.DataTemplate.DataType%2A> proprietà. <xref:System.Windows.DataTemplate.DataType%2A>può anche essere specificato come nome del tipo anziché utilizzare in modo esplicito [l'utilizzo di x:Type...](../xaml-services/xtype-markup-extension.md). Per informazioni dettagliate, vedere [Cenni](../../framework/wpf/data/data-templating-overview.md)preliminari sui modelli di dati .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.ResourceDictionary>
- [Risorse dell'applicazione](../../framework/wpf/advanced/optimizing-performance-application-resources.md)
- [Risorse e codice](../../framework/wpf/advanced/resources-and-code.md)
- [Definire e fare riferimento a una risorsaDefine and reference a resource](../../framework/wpf/advanced/how-to-define-and-reference-a-resource.md)
- [Panoramica sulla gestione delle applicazioni](../../framework/wpf/app-development/application-management-overview.md)
- [estensione di markup x:Type](../xaml-services/xtype-markup-extension.md)
- [Estensione di markup StaticResourceStaticResource markup extension](../../framework/wpf/advanced/staticresource-markup-extension.md)
- [Estensione di markup DynamicResourceDynamicResource markup extension](../../framework/wpf/advanced/dynamicresource-markup-extension.md)
