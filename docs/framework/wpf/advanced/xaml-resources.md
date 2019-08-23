---
title: Risorse XAML
ms.date: 03/30/2017
helpviewer_keywords:
- reusing resources [WPF]
- resources [WPF], reusing
- reusing commonly defined objects [WPF]
- XAML [WPF], reusing resources
ms.assetid: 91580b89-a0a8-4889-aecb-fddf8e63175f
ms.openlocfilehash: 738a4f397b1677b867126c7bb439b027f951baa0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958810"
---
# <a name="xaml-resources"></a>Risorse XAML
Una risorsa è un oggetto che è possibile riusare in posizioni diverse all'interno dell'applicazione. Sono esempi di risorse pennelli e stili. In questa panoramica viene descritto come utilizzare le [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]risorse in. È anche possibile creare e accedere alle risorse tramite codice o interscambiabile tra codice e [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Per altre informazioni, vedere [risorse e codice](resources-and-code.md).  
  
> [!NOTE]
> I file di risorse descritti in questo argomento sono diversi dai file di risorse descritti in file di dati, di [contenuto e di risorse dell'applicazione WPF](../app-development/wpf-application-resource-content-and-data-files.md) e diversi dalle risorse incorporate o collegate descritte in [gestire le risorse dell'applicazione (.NET) ](/visualstudio/ide/managing-application-resources-dotnet).  

<a name="usingresources"></a>   
## <a name="using-resources-in-xaml"></a>Uso delle risorse in XAML  
 Nell'esempio seguente viene definito <xref:System.Windows.Media.SolidColorBrush> un come risorsa nell'elemento radice di una pagina. L'esempio fa quindi riferimento alla risorsa e la usa per impostare le proprietà di diversi elementi figlio, <xref:System.Windows.Shapes.Ellipse>inclusi un <xref:System.Windows.Controls.TextBlock>oggetto, un <xref:System.Windows.Controls.Button>oggetto e un oggetto.  
  
 [!code-xaml[FEResourceSH_snip#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]  
  
 Ogni elemento a livello di Framework<xref:System.Windows.FrameworkElement> ( <xref:System.Windows.FrameworkContentElement>o) dispone <xref:System.Windows.FrameworkElement.Resources%2A> di una proprietà, che è la <xref:System.Windows.ResourceDictionary>proprietà che contiene le risorse (come) definite da una risorsa. È possibile definire risorse in qualsiasi elemento. Tuttavia, le risorse vengono spesso definite nell'elemento radice, che è <xref:System.Windows.Controls.Page> nell'esempio.  
  
 Ogni risorsa in un dizionario risorse deve avere una chiave univoca. Quando si definiscono le risorse nel markup, si assegna la chiave univoca tramite la [direttiva x:Key](../../xaml-services/x-key-directive.md). In genere, la chiave è una stringa. È tuttavia possibile impostare la chiave su altri tipi di oggetto tramite le estensioni di markup appropriate. Le chiavi non stringa per le risorse vengono utilizzate da determinate aree [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]di funzionalità in, in particolare per gli stili, le risorse componenti e lo stile dati.  
  
 Dopo aver definito una risorsa, è possibile fare riferimento alla risorsa da usare per un valore della proprietà tramite la sintassi dell'estensione di markup della risorsa, specificando il nome della chiave, ad esempio:  
  
 [!code-xaml[FEResourceSH_snip#KeyNameUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]  
  
 Nell'esempio precedente, quando il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] caricatore elabora il valore `{StaticResource MyBrush}` per la <xref:System.Windows.Controls.Control.Background%2A> proprietà in <xref:System.Windows.Controls.Button>, la logica di ricerca delle risorse verifica prima di tutto il dizionario <xref:System.Windows.Controls.Button> risorse per l'elemento. Se <xref:System.Windows.Controls.Button> non dispone di una definizione della chiave `MyBrush` di risorsa (la relativa raccolta di risorse è vuota), la ricerca successiva controlla l' <xref:System.Windows.Controls.Page>elemento padre di <xref:System.Windows.Controls.Button>, ovvero. Pertanto, quando si definisce una risorsa sull' <xref:System.Windows.Controls.Page> elemento radice, tutti gli elementi nell'albero logico <xref:System.Windows.Controls.Page> di possono accedervi ed è possibile riutilizzare la stessa risorsa per impostare il valore di qualsiasi proprietà che accetta l'oggetto <xref:System.Type> che la risorsa rappresenta. Nell'esempio precedente, la stessa `MyBrush` risorsa imposta due proprietà diverse: la <xref:System.Windows.Controls.Control.Background%2A> proprietà di un <xref:System.Windows.Controls.Button>oggetto e la <xref:System.Windows.Shapes.Shape.Fill%2A> proprietà di <xref:System.Windows.Shapes.Rectangle>un oggetto.  
  
<a name="staticdynamic"></a>   
## <a name="static-and-dynamic-resources"></a>Risorse statiche e dinamiche  
 È possibile fare riferimento a una risorsa come risorsa statica o come risorsa dinamica. A tale scopo, è possibile utilizzare l' [estensione di markup StaticResource](staticresource-markup-extension.md) o l' [estensione di markup DynamicResource](dynamicresource-markup-extension.md). Un'estensione di markup è una funzionalità [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] di che consente di specificare un riferimento a un oggetto mediante l'estensione di markup che elabora la stringa dell'attributo e [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] restituisce l'oggetto a un caricatore. Per altre informazioni sul comportamento dell'estensione di markup, vedere [estensioni di markup e XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 Quando si usa un'estensione di markup, si forniscono in genere uno o più parametri sotto forma di stringa. Questi vengono elaborati da un'estensione di markup specifica, anziché essere valutati nel contesto della proprietà da impostare. L' [estensione di markup StaticResource](staticresource-markup-extension.md) elabora una chiave cercando il valore della chiave in tutti i dizionari risorse disponibili. Ciò avviene durante il caricamento, che è il momento in cui il processo di caricamento deve assegnare il valore della proprietà che accetta il riferimento di risorsa statica. L' [estensione di markup DynamicResource](dynamicresource-markup-extension.md) elabora invece una chiave creando un'espressione e tale espressione rimane non valutata fino a quando l'applicazione non viene effettivamente eseguita, a quel punto l'espressione viene valutata e fornisce un valore.  
  
 Quando si fa riferimento a una risorsa, la decisione di usare un riferimento di risorsa statica o un riferimento di risorsa dinamica può essere influenzata dalle considerazioni seguenti:  
  
- La progettazione complessiva della modalità di creazione delle risorse per l'applicazione (per pagina, nell'applicazione, in modo separato [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]in un assembly di solo risorse).  
  
- La funzionalità dell'applicazione: l'aggiornamento delle risorse in tempo reale fa parte dei requisiti dell'applicazione?  
  
- Il comportamento di ricerca specifico del tipo di riferimento di risorsa.  
  
- La proprietà o il tipo di risorsa specifico e il comportamento nativo di tale tipo.  
  
### <a name="static-resources"></a>Risorse statiche  
 I riferimenti di risorse statiche sono ideali nelle circostanze seguenti:  
  
- In base alla progettazione dell'applicazione, la maggior parte delle risorse è concentrata all'interno di dizionari risorse a livello di pagina o di applicazione. I riferimenti di risorse statiche non vengono rivalutati in base al comportamento in runtime, ad esempio quando viene ricaricata una pagina. È quindi possibile ottenere un miglioramento delle prestazioni, dato che si può evitare di creare riferimenti di risorse dinamiche non effettivamente necessari alla progettazione delle risorse e dell'applicazione.  
  
- Si sta impostando il valore di una proprietà che non si trova <xref:System.Windows.DependencyObject> in un <xref:System.Windows.Freezable>oggetto o.  
  
- Si sta creando un dizionario risorse che verrà compilato in una DLL e incluso nel pacchetto dell'applicazione o condiviso da applicazioni diverse.  
  
- Si sta creando un tema per un controllo personalizzato e si stanno definendo le risorse da usare all'interno dei temi. In questo caso, è in genere consigliabile evitare il comportamento di ricerca dei riferimenti di risorse dinamiche. Il comportamento dei riferimenti di risorse statiche è preferibile, perché è prevedibile e autonomo all'interno del tema. Con i riferimenti di risorse dinamiche, anche un riferimento all'interno di un tema non viene valutato fino al runtime. C'è quindi la possibilità che, quando il tema viene applicato, un elemento locale ridefinisca una chiave a cui il tema tenta di fare riferimento e che l'elemento locale intervenga nella ricerca prima del tema stesso. Se ciò avviene, il tema non si comporterà nel modo previsto.  
  
- Si usano risorse per impostare un numero elevato di proprietà di dipendenza. Per le proprietà di dipendenza la memorizzazione nella cache del valore effettivo viene abilitata dal sistema di proprietà. Pertanto, se si specifica un valore per una proprietà di dipendenza che può essere valutata in fase di caricamento, la proprietà di dipendenza non deve verificare la presenza di un'espressione rivalutata e può restituire l'ultimo valore effettivo. Questa tecnica può garantire un miglioramento delle prestazioni.  
  
- Si desidera modificare la risorsa sottostante per tutti i consumer oppure si desidera mantenere istanze scrivibili separate per ogni consumer utilizzando l' [attributo x:Shared](../../xaml-services/x-shared-attribute.md).  
  
#### <a name="static-resource-lookup-behavior"></a>Comportamento di ricerca delle risorse statiche  
  
1. Il processo di ricerca controlla la presenza della chiave richiesta all'interno del dizionario risorse definito dall'elemento che imposta la proprietà.  
  
2. Il processo di ricerca attraversa quindi l'albero logico verso l'alto, verso l'elemento padre e il dizionario risorse di questo. Il processo continua fino al raggiungimento dell'elemento radice.  
  
3. Vengono quindi controllate le risorse dell'applicazione. Le risorse dell'applicazione sono le risorse all'interno del dizionario risorse definito dall' <xref:System.Windows.Application> oggetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per l'applicazione.  
  
 I riferimenti di risorse statiche all'interno di un dizionario risorse devono fare riferimento a una risorsa già definita lessicalmente prima del riferimento. I riferimenti di risorse statiche non sono in grado di risolvere riferimenti in avanti. Per questo motivo, se si usano riferimenti di risorse statiche, è necessario progettare la struttura del dizionario risorse in modo che le risorse destinate all'uso per risorsa vengano definite in corrispondenza o vicino all'inizio del rispettivo dizionario risorse.  
  
 La ricerca di risorse statiche può estendersi nei temi o nelle risorse di sistema, ma questa operazione [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è supportata solo perché il caricatore rinvia la richiesta. Il rinvio è necessario per consentire la corretta applicazione del tema di runtime all'applicazione al momento del caricamento della pagina. Non è tuttavia consigliabile usare riferimenti di risorse statiche a chiavi che notoriamente esistono solo all'interno di temi o come risorse di sistema. Questo avviene perché tali riferimenti non vengono rivalutati se l'utente modifica il tema in tempo reale. Un riferimento di risorsa dinamica è più affidabile se si richiedono risorse di tema o di sistema. Fa eccezione il caso in cui un elemento tema stesso richieda un'altra risorsa. Per i motivi descritti in precedenza, questi riferimenti devono essere riferimenti di risorse statiche.  
  
 Se non viene trovato un riferimento di risorsa statica, il comportamento dell'eccezione può variare. Se la risorsa è stata rinviata, l'eccezione si verifica in runtime. Se la risorsa non è stata rinviata, l'eccezione si verifica al momento del caricamento.  
  
### <a name="dynamic-resources"></a>Risorse dinamiche  
 Le risorse dinamiche sono ideali nelle circostanze seguenti:  
  
- Il valore della risorsa dipende da condizioni non note fino al runtime, ad esempio risorse di sistema o risorse che possono essere impostate dall'utente in altro modo. Ad esempio, è possibile creare valori Setter che fanno riferimento a proprietà di sistema, come <xref:System.Windows.SystemColors>esposto <xref:System.Windows.SystemFonts>da, <xref:System.Windows.SystemParameters>o. Questi valori sono realmente dinamici perché in ultima analisi derivano dall'ambiente di runtime dell'utente e dal sistema operativo. È anche possibile che eventuali temi a livello di applicazione siano soggetti a modifica e che l'accesso alle risorse a livello di pagina debba anche acquisire la modifica.  
  
- Si stanno creando stili di tema per un controllo personalizzato o si sta facendo riferimento a stili di questo tipo.  
  
- Si intende modificare il contenuto di un oggetto <xref:System.Windows.ResourceDictionary> durante la durata di un'applicazione.  
  
- La struttura delle risorse è complessa e con interdipendenze e potrebbe richiedere riferimenti in avanti. I riferimenti alle risorse statiche non supportano i riferimenti in diretta, ma i riferimenti alle risorse dinamiche le supportano perché la risorsa non deve essere valutata fino al runtime e i riferimenti in diretta non sono pertanto un concetto pertinente.  
  
- Si sta facendo riferimento a una risorsa di dimensioni particolarmente grandi dal punto di vista del compile set o del working set e quando la pagina viene caricata non è possibile usare la risorsa immediatamente. I riferimenti alle risorse statiche vengono [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sempre caricati da quando viene caricata la pagina. Tuttavia, un riferimento a una risorsa dinamica non viene caricato fino a quando non viene effettivamente utilizzato.  
  
- Si sta creando uno stile in cui i valori setter possono derivare da altri valori su cui influiscono temi o altre impostazioni utente.  
  
- Si stanno applicando risorse a elementi che nel corso della durata dell'applicazione potrebbero essere associati a un nuovo elemento padre nell'albero logico. La modifica dell'elemento padre cambia potenzialmente anche l'ambito di ricerca. Se quindi si vuole che la risorsa per un elemento associato a un nuovo elemento padre sia rivalutata in base al nuovo ambito, usare sempre un riferimento di risorsa dinamica.  
  
#### <a name="dynamic-resource-lookup-behavior"></a>Comportamento di ricerca delle risorse dinamiche  
 Il comportamento di ricerca delle risorse per un riferimento a una risorsa dinamica è parallelo al comportamento di ricerca <xref:System.Windows.FrameworkElement.FindResource%2A> nel <xref:System.Windows.FrameworkElement.SetResourceReference%2A>codice se si chiama o.  
  
1. Il processo di ricerca controlla la presenza della chiave richiesta all'interno del dizionario risorse definito dall'elemento che imposta la proprietà.  
  
    - Se l'elemento definisce una <xref:System.Windows.FrameworkElement.Style%2A> proprietà, il <xref:System.Windows.Style.Resources%2A> dizionario all'interno <xref:System.Windows.Style> di viene controllato.  
  
    - Se l'elemento definisce una <xref:System.Windows.Controls.Control.Template%2A> proprietà, il <xref:System.Windows.FrameworkTemplate.Resources%2A> dizionario all'interno <xref:System.Windows.FrameworkTemplate> di viene controllato.  
  
2. Il processo di ricerca attraversa quindi l'albero logico verso l'alto, verso l'elemento padre e il dizionario risorse di questo. Il processo continua fino al raggiungimento dell'elemento radice.  
  
3. Vengono quindi controllate le risorse dell'applicazione. Le risorse dell'applicazione sono le risorse all'interno del dizionario risorse definito dall' <xref:System.Windows.Application> oggetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per l'applicazione.  
  
4. Viene controllato il dizionario risorse per il tema attivo. Se il tema viene modificato in runtime, il valore viene rivalutato.  
  
5. Vengono controllate le risorse di sistema.  
  
 Il comportamento di eventuali eccezioni varia:  
  
- Se una risorsa è stata richiesta da <xref:System.Windows.FrameworkElement.FindResource%2A> una chiamata e non è stata trovata, viene generata un'eccezione.  
  
- Se una <xref:System.Windows.FrameworkElement.TryFindResource%2A> chiamata è stata richiesta da una risorsa e non è stata trovata, non viene generata alcuna eccezione, ma il valore `null`restituito è. Se la proprietà da impostare non accetta `null`, è comunque possibile che venga generata un'eccezione più approfondita (dipende dalla singola proprietà da impostare).  
  
- Se una risorsa è stata richiesta da un riferimento a una [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]risorsa dinamica in e non è stata trovata, il comportamento dipende dal sistema di proprietà generale, ma il comportamento generale è come se non si fosse verificata alcuna operazione di impostazione delle proprietà a livello di risorsa. Se ad esempio si tenta di impostare lo sfondo di un elemento pulsante singolo usando una risorsa che non può essere valutata, risulta che non è stato impostato alcun valore, ma il valore effettivo può comunque derivare da altri elementi che fanno parte del sistema di proprietà e di precedenza dei valori. Il valore dello sfondo, ad esempio, può comunque derivare dallo stile di un pulsante definito localmente o dallo stile del tema. Per le proprietà non definite tramite stili di tema, il valore effettivo dopo una valutazione non riuscita di una risorsa può derivare dal valore predefinito dei metadati delle proprietà.  
  
#### <a name="restrictions"></a>Restrizioni  
 I riferimenti di risorse dinamiche presentano alcune restrizioni rilevanti. Almeno una delle affermazioni seguenti deve essere vera:  
  
- La proprietà impostata deve essere una proprietà di un oggetto <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Tale proprietà deve essere supportata da un oggetto <xref:System.Windows.DependencyProperty>.  
  
- Il riferimento è relativo a un valore all' <xref:System.Windows.Style>interno di un oggetto <xref:System.Windows.Setter>.  
  
- La proprietà impostata deve essere una proprietà di un oggetto <xref:System.Windows.Freezable> fornito come valore di una <xref:System.Windows.FrameworkElement> proprietà o <xref:System.Windows.FrameworkContentElement> oppure di un <xref:System.Windows.Setter> valore.  
  
 Poiché la proprietà impostata deve essere una <xref:System.Windows.DependencyProperty> proprietà o <xref:System.Windows.Freezable> , la maggior parte delle modifiche alle proprietà può propagarsi all'interfaccia utente perché una modifica di proprietà (il valore della risorsa dinamica modificata) viene riconosciuta dal sistema di proprietà. La maggior parte dei controlli include la logica che forza un altro layout di <xref:System.Windows.DependencyProperty> un controllo se una modifica e tale proprietà potrebbe influire sul layout. Tuttavia, non tutte le proprietà che hanno un' [estensione di markup DynamicResource](dynamicresource-markup-extension.md) come valore sono garantiti per fornire il valore in modo che vengano aggiornate in tempo reale nell'interfaccia utente. Tale funzionalità può comunque variare a seconda della proprietà, nonché a seconda del tipo proprietario della proprietà o anche della struttura logica dell'applicazione.  
  
<a name="stylesimplicitkeys"></a>   
## <a name="styles-datatemplates-and-implicit-keys"></a>Stili, modelli di dati e chiavi implicite  
 In precedenza è stato dichiarato che tutti gli elementi in <xref:System.Windows.ResourceDictionary> un oggetto devono avere una chiave. Tuttavia, ciò non significa che tutte le risorse devono avere un esplicito `x:Key`. Diversi tipi di oggetto supportano una chiave implicita quando sono definiti come risorsa in cui il valore della chiave è associato al valore di un'altra proprietà. Questa operazione è nota come chiave implicita, mentre `x:Key` un attributo è una chiave esplicita. È possibile sovrascrivere qualsiasi chiave implicita specificando una chiave esplicita.  
  
 Uno scenario molto importante per le risorse è quando si definisce <xref:System.Windows.Style>un. In realtà, un <xref:System.Windows.Style> è quasi sempre definito come una voce in un dizionario risorse, perché gli stili sono intrinsecamente progettati per il riutilizzo. Per altre informazioni sugli stili, vedere applicazione di stili [e modelli](../controls/styling-and-templating.md).  
  
 Una chiave implicita consente sia di creare stili per controlli che di fare riferimento ad essi. Gli stili di tema che definiscono l'aspetto predefinito di un controllo si basano sulla chiave implicita. La chiave implicita dal punto di vista della richiesta è l' <xref:System.Type> oggetto del controllo stesso. La chiave implicita dal punto di vista della definizione della risorsa <xref:System.Windows.Style.TargetType%2A> è il dello stile. Pertanto, se si creano temi per i controlli personalizzati, creando stili che interagiscono con gli stili del tema esistenti, non è necessario specificare una <xref:System.Windows.Style> [direttiva x:Key](../../xaml-services/x-key-directive.md) . E se si vogliono usare stili con tema, non è necessario specificare alcuno stile. Ad esempio, la definizione di stile seguente funziona anche se la <xref:System.Windows.Style> risorsa non presenta una chiave:  
  
 [!code-xaml[FEResourceSH_snip#ImplicitStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]  
  
 Lo stile ha effettivamente una chiave, ovvero la chiave `typeof(` <xref:System.Windows.Controls.Button> `)`implicita. Nel markup è possibile specificare <xref:System.Windows.Style.TargetType%2A> direttamente come nome del tipo (oppure è possibile usare facoltativamente [{x:Type...}](../../xaml-services/x-type-markup-extension.md) per restituire un <xref:System.Type>oggetto.  
  
 Attraverso i meccanismi di stile del tema predefiniti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]utilizzati da, lo stile viene applicato come stile di runtime <xref:System.Windows.Controls.Button> di un oggetto nella <xref:System.Windows.Controls.Button> pagina, anche se non tenta di specificare <xref:System.Windows.FrameworkElement.Style%2A> la proprietà o una risorsa specifica. riferimento allo stile. Lo stile definito nella pagina viene trovato in precedenza nella sequenza di ricerca rispetto allo stile del dizionario dei temi, usando la stessa chiave dello stile del dizionario del tema. È possibile specificare `<Button>Hello</Button>` semplicemente un punto qualsiasi della pagina e lo stile definito `Button` con <xref:System.Windows.Style.TargetType%2A> si applica a tale pulsante. Se lo si desidera, è comunque possibile impostare in modo esplicito come <xref:System.Windows.Style.TargetType%2A>chiave lo stile con lo stesso valore di tipo di, per maggiore chiarezza nel markup, ma questo è facoltativo.  
  
 Le chiavi implicite per gli stili non si applicano <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> a `true` un controllo se è <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> (si noti anche che può essere impostato come parte del comportamento nativo per la classe del controllo, anziché in modo esplicito in un'istanza del controllo). Inoltre, per supportare le chiavi implicite per gli scenari di classi derivate, <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> il controllo deve eseguire l'override di ( [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tutti i controlli esistenti forniti come parte di questa operazione). Per ulteriori informazioni su stili, temi e progettazione di controlli, vedere [linee guida per la progettazione di controlli Stylable](../controls/guidelines-for-designing-stylable-controls.md).  
  
 <xref:System.Windows.DataTemplate>dispone inoltre di una chiave implicita. La chiave implicita per <xref:System.Windows.DataTemplate> un oggetto <xref:System.Windows.DataTemplate.DataType%2A> è il valore della proprietà. <xref:System.Windows.DataTemplate.DataType%2A>può anche essere specificato come nome del tipo anziché usare in modo esplicito [{x:Type...}](../../xaml-services/x-type-markup-extension.md). Per informazioni dettagliate, vedere [Cenni preliminari sui modelli di dati](../data/data-templating-overview.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.ResourceDictionary>
- [Risorse di applicazioni](optimizing-performance-application-resources.md)
- [Risorse e codice](resources-and-code.md)
- [Definire e fare riferimento a una risorsa](how-to-define-and-reference-a-resource.md)
- [Cenni preliminari sulla gestione di applicazioni](../app-development/application-management-overview.md)
- [Estensione di markup x:Type](../../xaml-services/x-type-markup-extension.md)
- [Estensione di markup StaticResource](staticresource-markup-extension.md)
- [Estensione del markup DynamicResource](dynamicresource-markup-extension.md)
