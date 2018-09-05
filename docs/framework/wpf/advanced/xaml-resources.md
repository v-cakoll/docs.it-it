---
title: Risorse XAML
ms.date: 03/30/2017
helpviewer_keywords:
- reusing resources [WPF]
- resources [WPF], reusing
- reusing commonly defined objects [WPF]
- XAML [WPF], reusing resources
ms.assetid: 91580b89-a0a8-4889-aecb-fddf8e63175f
ms.openlocfilehash: c43505497b947004ffb282346459967579d52375
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43674083"
---
# <a name="xaml-resources"></a>Risorse XAML
Una risorsa è un oggetto che è possibile riusare in posizioni diverse all'interno dell'applicazione. Sono esempi di risorse pennelli e stili. Questa panoramica viene descritto come usare le risorse di [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. È anche possibile creare e accedere alle risorse tramite il codice o in modo intercambiabile tra codice e [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Per altre informazioni, vedere [risorse e codice](../../../../docs/framework/wpf/advanced/resources-and-code.md).  
  
> [!NOTE]
>  I file di risorse descritti in questo argomento sono diversi rispetto a file di risorse descritti [WPF Application Resource, contenuto e i file di dati](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md) e diverso da quello delle risorse incorporate o collegate descritte [ La gestione delle risorse dell'applicazione (.NET)](https://msdn.microsoft.com/library/f2582734-8ada-4baa-8a7c-e2ef943ddf7e).  
  
  
<a name="usingresources"></a>   
## <a name="using-resources-in-xaml"></a>Uso delle risorse in XAML  
 L'esempio seguente definisce un <xref:System.Windows.Media.SolidColorBrush> come risorsa nell'elemento radice di una pagina. Nell'esempio viene quindi fa riferimento alla risorsa e lo usa per impostare le proprietà di diversi elementi figlio, inclusi un' <xref:System.Windows.Shapes.Ellipse>, una <xref:System.Windows.Controls.TextBlock>e un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[FEResourceSH_snip#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xaml)]  
  
 Ogni elemento a livello di framework (<xref:System.Windows.FrameworkElement> oppure <xref:System.Windows.FrameworkContentElement>) è un <xref:System.Windows.FrameworkElement.Resources%2A> proprietà, ovvero la proprietà che contiene le risorse (come un <xref:System.Windows.ResourceDictionary>) che definisce una risorsa. È possibile definire risorse in qualsiasi elemento. Tuttavia, le risorse vengono spesso definite per l'elemento radice, ovvero <xref:System.Windows.Controls.Page> nell'esempio.  
  
 Ogni risorsa in un dizionario risorse deve avere una chiave univoca. Quando si definiscono le risorse nel markup, si assegna la chiave univoca tramite il [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md). In genere, la chiave è una stringa. È tuttavia possibile impostare la chiave su altri tipi di oggetto tramite le estensioni di markup appropriate. Le chiavi per le risorse vengono utilizzate aree funzionali specifiche in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], in particolare per stili, risorse componenti e formattazione dei dati.  
  
 Dopo aver definito una risorsa, è possibile fare riferimento alla risorsa da usare per un valore della proprietà tramite la sintassi dell'estensione di markup della risorsa, specificando il nome della chiave, ad esempio:  
  
 [!code-xaml[FEResourceSH_snip#KeyNameUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#keynameusage)]  
  
 Nell'esempio precedente, quando la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] caricatore elabora il valore `{StaticResource MyBrush}` per il <xref:System.Windows.Controls.Control.Background%2A> proprietà sul <xref:System.Windows.Controls.Button>, la logica di ricerca di risorse controlla prima di tutto il dizionario risorse per la <xref:System.Windows.Controls.Button> elemento. Se <xref:System.Windows.Controls.Button> non dispone di una definizione della chiave di risorsa `MyBrush` (non esiste, ovvero l'insieme di risorse è vuoto), la ricerca controlla l'elemento padre del <xref:System.Windows.Controls.Button>, ovvero <xref:System.Windows.Controls.Page>. Di conseguenza, quando si definisce una risorsa nella <xref:System.Windows.Controls.Page> elemento radice, tutti gli elementi dell'albero logico del <xref:System.Windows.Controls.Page> possono accedervi ed è possibile riusare la stessa risorsa per l'impostazione del valore di qualsiasi proprietà che accetta il <xref:System.Type> che la risorsa rappresenta. Nell'esempio precedente, lo stesso `MyBrush` risorsa imposta due proprietà diverse: le <xref:System.Windows.Controls.Control.Background%2A> di un <xref:System.Windows.Controls.Button>e il <xref:System.Windows.Shapes.Shape.Fill%2A> di un <xref:System.Windows.Shapes.Rectangle>.  
  
<a name="staticdynamic"></a>   
## <a name="static-and-dynamic-resources"></a>Risorse statiche e dinamiche  
 È possibile fare riferimento a una risorsa come risorsa statica o come risorsa dinamica. Questa operazione viene eseguita utilizzando il [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) o nella [estensione di Markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md). Un'estensione di markup è una funzionalità del [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che consente di specificare un riferimento all'oggetto facendo in modo che l'estensione di markup elaborare la stringa di attributo e restituendo l'oggetto a un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] caricatore. Per altre informazioni sul comportamento delle estensioni di markup, vedere [estensioni di Markup e XAML WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Quando si usa un'estensione di markup, si forniscono in genere uno o più parametri sotto forma di stringa. Questi vengono elaborati da un'estensione di markup specifica, anziché essere valutati nel contesto della proprietà da impostare. Il [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) elabora una chiave cercando il valore della chiave stessa in tutti i dizionari risorse disponibili. Ciò avviene durante il caricamento, che è il momento in cui il processo di caricamento deve assegnare il valore della proprietà che accetta il riferimento di risorsa statica. Il [estensione di Markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) invece di elaborare una chiave tramite la creazione di un'espressione e tale espressione non valutata fino a quando non viene effettivamente eseguita l'applicazione, momento in cui l'espressione viene valutata e fornisce un valore.  
  
 Quando si fa riferimento a una risorsa, la decisione di usare un riferimento di risorsa statica o un riferimento di risorsa dinamica può essere influenzata dalle considerazioni seguenti:  
  
-   La progettazione complessiva del modo in cui si creano le risorse per l'applicazione (per pagina, nell'applicazione, in file separati [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], in un assembly di sole risorse).  
  
-   La funzionalità dell'applicazione: l'aggiornamento delle risorse in tempo reale fa parte dei requisiti dell'applicazione?  
  
-   Il comportamento di ricerca specifico del tipo di riferimento di risorsa.  
  
-   La proprietà o il tipo di risorsa specifico e il comportamento nativo di tale tipo.  
  
### <a name="static-resources"></a>Risorse statiche  
 I riferimenti di risorse statiche sono ideali nelle circostanze seguenti:  
  
-   In base alla progettazione dell'applicazione, la maggior parte delle risorse è concentrata all'interno di dizionari risorse a livello di pagina o di applicazione. I riferimenti di risorse statiche non vengono rivalutati in base al comportamento in runtime, ad esempio quando viene ricaricata una pagina. È quindi possibile ottenere un miglioramento delle prestazioni, dato che si può evitare di creare riferimenti di risorse dinamiche non effettivamente necessari alla progettazione delle risorse e dell'applicazione.  
  
-   Si sta impostando il valore di una proprietà che non si trova in una <xref:System.Windows.DependencyObject> o un <xref:System.Windows.Freezable>.  
  
-   Si sta creando un dizionario risorse che verrà compilato in una DLL e incluso nel pacchetto dell'applicazione o condiviso da applicazioni diverse.  
  
-   Si sta creando un tema per un controllo personalizzato e si stanno definendo le risorse da usare all'interno dei temi. In questo caso, è in genere consigliabile evitare il comportamento di ricerca dei riferimenti di risorse dinamiche. Il comportamento dei riferimenti di risorse statiche è preferibile, perché è prevedibile e autonomo all'interno del tema. Con i riferimenti di risorse dinamiche, anche un riferimento all'interno di un tema non viene valutato fino al runtime. C'è quindi la possibilità che, quando il tema viene applicato, un elemento locale ridefinisca una chiave a cui il tema tenta di fare riferimento e che l'elemento locale intervenga nella ricerca prima del tema stesso. Se ciò avviene, il tema non si comporterà nel modo previsto.  
  
-   Si usano risorse per impostare un numero elevato di proprietà di dipendenza. Per le proprietà di dipendenza la memorizzazione nella cache del valore effettivo viene abilitata dal sistema di proprietà. Pertanto, se si specifica un valore per una proprietà di dipendenza che può essere valutata in fase di caricamento, la proprietà di dipendenza non deve verificare la presenza di un'espressione rivalutata e può restituire l'ultimo valore effettivo. Questa tecnica può garantire un miglioramento delle prestazioni.  
  
-   Si vuole modificare la risorsa sottostante per tutti i consumer o si vuole mantenere istanze scrivibili separate per ogni consumer tramite la [x: Shared Attribute](../../../../docs/framework/xaml-services/x-shared-attribute.md).  
  
#### <a name="static-resource-lookup-behavior"></a>Comportamento di ricerca delle risorse statiche  
  
1.  Il processo di ricerca controlla la presenza della chiave richiesta all'interno del dizionario risorse definito dall'elemento che imposta la proprietà.  
  
2.  Il processo di ricerca attraversa quindi l'albero logico verso l'alto, verso l'elemento padre e il dizionario risorse di questo. Il processo continua fino al raggiungimento dell'elemento radice.  
  
3.  Vengono quindi controllate le risorse dell'applicazione. Si tratta delle risorse all'interno del dizionario risorse definito dall'applicazione il <xref:System.Windows.Application> dell'oggetto per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.  
  
 I riferimenti di risorse statiche all'interno di un dizionario risorse devono fare riferimento a una risorsa già definita lessicalmente prima del riferimento. I riferimenti di risorse statiche non sono in grado di risolvere riferimenti in avanti. Per questo motivo, se si usano riferimenti di risorse statiche, è necessario progettare la struttura del dizionario risorse in modo che le risorse destinate all'uso per risorsa vengano definite in corrispondenza o vicino all'inizio del rispettivo dizionario risorse.  
  
 Ricerca delle risorse statiche può estendersi all'interno di temi, o alle risorse di sistema, ma questa funzionalità è supportata solo perché il [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] caricatore rinvia la richiesta. Il rinvio è necessario per consentire la corretta applicazione del tema di runtime all'applicazione al momento del caricamento della pagina. Non è tuttavia consigliabile usare riferimenti di risorse statiche a chiavi che notoriamente esistono solo all'interno di temi o come risorse di sistema. Questo avviene perché tali riferimenti non vengono rivalutati se l'utente modifica il tema in tempo reale. Un riferimento di risorsa dinamica è più affidabile se si richiedono risorse di tema o di sistema. Fa eccezione il caso in cui un elemento tema stesso richieda un'altra risorsa. Per i motivi descritti in precedenza, questi riferimenti devono essere riferimenti di risorse statiche.  
  
 Se non viene trovato un riferimento di risorsa statica, il comportamento dell'eccezione può variare. Se la risorsa è stata rinviata, l'eccezione si verifica in runtime. Se la risorsa non è stata rinviata, l'eccezione si verifica al momento del caricamento.  
  
### <a name="dynamic-resources"></a>Risorse dinamiche  
 Le risorse dinamiche sono ideali nelle circostanze seguenti:  
  
-   Il valore della risorsa dipende da condizioni non note fino al runtime, ad esempio risorse di sistema o risorse che possono essere impostate dall'utente in altro modo. Ad esempio, è possibile creare valori setter che fanno riferimento a proprietà di sistema, come esposto da <xref:System.Windows.SystemColors>, <xref:System.Windows.SystemFonts>, o <xref:System.Windows.SystemParameters>. Questi valori sono realmente dinamici perché in ultima analisi derivano dall'ambiente di runtime dell'utente e dal sistema operativo. È anche possibile che eventuali temi a livello di applicazione siano soggetti a modifica e che l'accesso alle risorse a livello di pagina debba anche acquisire la modifica.  
  
-   Si stanno creando stili di tema per un controllo personalizzato o si sta facendo riferimento a stili di questo tipo.  
  
-   Si intende modificare il contenuto di un <xref:System.Windows.ResourceDictionary> durante un ciclo di vita dell'applicazione.  
  
-   La struttura delle risorse è complessa e con interdipendenze e potrebbe richiedere riferimenti in avanti. Riferimenti di risorse statiche non supportano i riferimenti in avanti, ma i riferimenti di risorsa dinamica li supportano, perché la risorsa non dovrà essere valutata solo in fase di esecuzione e i riferimenti in avanti non sono pertanto un concetto rilevante.  
  
-   Si sta facendo riferimento a una risorsa di dimensioni particolarmente grandi dal punto di vista del compile set o del working set e quando la pagina viene caricata non è possibile usare la risorsa immediatamente. Riferimenti di risorse statiche vengono sempre caricati da [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] quando la pagina viene caricata; tuttavia, un riferimento di risorsa dinamica non viene caricato finché non viene effettivamente usato.  
  
-   Si sta creando uno stile in cui i valori setter possono derivare da altri valori su cui influiscono temi o altre impostazioni utente.  
  
-   Si stanno applicando risorse a elementi che nel corso della durata dell'applicazione potrebbero essere associati a un nuovo elemento padre nell'albero logico. La modifica dell'elemento padre cambia potenzialmente anche l'ambito di ricerca. Se quindi si vuole che la risorsa per un elemento associato a un nuovo elemento padre sia rivalutata in base al nuovo ambito, usare sempre un riferimento di risorsa dinamica.  
  
#### <a name="dynamic-resource-lookup-behavior"></a>Comportamento di ricerca delle risorse dinamiche  
 Comportamento di ricerca delle risorse per un riferimento di risorsa dinamica è parallelo al comportamento di ricerca nel codice se si chiama <xref:System.Windows.FrameworkElement.FindResource%2A> o <xref:System.Windows.FrameworkElement.SetResourceReference%2A>.  
  
1.  Il processo di ricerca controlla la presenza della chiave richiesta all'interno del dizionario risorse definito dall'elemento che imposta la proprietà.  
  
    -   Se l'elemento definisce un <xref:System.Windows.FrameworkElement.Style%2A> proprietà, il <xref:System.Windows.Style.Resources%2A> dizionario interno la <xref:System.Windows.Style> sia selezionata.  
  
    -   Se l'elemento definisce un <xref:System.Windows.Controls.Control.Template%2A> proprietà, il <xref:System.Windows.FrameworkTemplate.Resources%2A> dizionario interno la <xref:System.Windows.FrameworkTemplate> sia selezionata.  
  
2.  Il processo di ricerca attraversa quindi l'albero logico verso l'alto, verso l'elemento padre e il dizionario risorse di questo. Il processo continua fino al raggiungimento dell'elemento radice.  
  
3.  Vengono quindi controllate le risorse dell'applicazione. Si tratta delle risorse all'interno del dizionario risorse definito dall'applicazione il <xref:System.Windows.Application> dell'oggetto per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione.  
  
4.  Viene controllato il dizionario risorse per il tema attivo. Se il tema viene modificato in runtime, il valore viene rivalutato.  
  
5.  Vengono controllate le risorse di sistema.  
  
 Il comportamento di eventuali eccezioni varia:  
  
-   Se una risorsa è stata richiesta da un <xref:System.Windows.FrameworkElement.FindResource%2A> chiamare e non è stato trovato, viene generata un'eccezione.  
  
-   Se una risorsa è stata richiesta da un <xref:System.Windows.FrameworkElement.TryFindResource%2A> chiamare e non è stato trovato, viene generata alcuna eccezione, ma il valore restituito è `null`. Se la proprietà impostata non accetta `null`, è comunque possibile che venga generata un'eccezione più grave (questo dipende dalla proprietà specifica impostata).  
  
-   Se una risorsa è stata richiesta da un riferimento di risorsa dinamica in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]e non è stato trovato, quindi il comportamento dipende dal sistema di proprietà generale, ma il comportamento generale è come se si è verificata alcuna operazione di impostazione di proprietà a livello in cui risiede la risorsa. Se ad esempio si tenta di impostare lo sfondo di un elemento pulsante singolo usando una risorsa che non può essere valutata, risulta che non è stato impostato alcun valore, ma il valore effettivo può comunque derivare da altri elementi che fanno parte del sistema di proprietà e di precedenza dei valori. Il valore dello sfondo, ad esempio, può comunque derivare dallo stile di un pulsante definito localmente o dallo stile del tema. Per le proprietà non definite tramite stili di tema, il valore effettivo dopo una valutazione non riuscita di una risorsa può derivare dal valore predefinito dei metadati delle proprietà.  
  
#### <a name="restrictions"></a>Restrizioni  
 I riferimenti di risorse dinamiche presentano alcune restrizioni rilevanti. Almeno una delle affermazioni seguenti deve essere vera:  
  
-   La proprietà impostata deve essere una proprietà in un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>. Tale proprietà deve essere supportata da un <xref:System.Windows.DependencyProperty>.  
  
-   Il riferimento è relativo a un valore all'interno di un <xref:System.Windows.Style> <xref:System.Windows.Setter>.  
  
-   La proprietà impostata deve essere una proprietà di un <xref:System.Windows.Freezable> che viene fornito come un valore di un <xref:System.Windows.FrameworkElement> oppure <xref:System.Windows.FrameworkContentElement> proprietà, o un <xref:System.Windows.Setter> valore.  
  
 Poiché la proprietà impostata deve essere un <xref:System.Windows.DependencyProperty> o <xref:System.Windows.Freezable> proprietà, la maggior parte delle modifiche delle proprietà possono propagarsi all'interfaccia utente perché una modifica della proprietà (il valore di risorsa dinamica modificata) viene riconosciuta dal sistema di proprietà. La maggior parte dei controlli includono la logica che forzerà un altro layout di un controllo se una <xref:System.Windows.DependencyProperty> le modifiche e proprietà può influire sul layout. Tuttavia, non tutte le proprietà che hanno una [estensione di Markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) come relativo valore vengono garantiti per fornire il valore in modo che aggiorni in tempo reale nell'interfaccia utente. Tale funzionalità può comunque variare a seconda della proprietà, nonché a seconda del tipo proprietario della proprietà o anche della struttura logica dell'applicazione.  
  
<a name="stylesimplicitkeys"></a>   
## <a name="styles-datatemplates-and-implicit-keys"></a>Stili, modelli di dati e chiavi implicite  
 In precedenza, è stato dichiarato che tutti gli elementi un <xref:System.Windows.ResourceDictionary> deve avere una chiave. Tuttavia, ciò non significa che tutte le risorse devono avere un'esplicita `x:Key`. Diversi tipi di oggetto supportano una chiave implicita quando sono definiti come risorsa in cui il valore della chiave è associato al valore di un'altra proprietà. Ciò è noto come chiave implicita, mentre un `x:Key` attributo è una chiave esplicita. È possibile sovrascrivere qualsiasi chiave implicita specificando una chiave esplicita.  
  
 Uno scenario molto importante per le risorse è quando si definisce un <xref:System.Windows.Style>. In effetti, un <xref:System.Windows.Style> è quasi sempre definito come una voce in un dizionario risorse, perché gli stili sono intrinsecamente destinati al riutilizzo. Per altre informazioni sugli stili, vedere [stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Una chiave implicita consente sia di creare stili per controlli che di fare riferimento ad essi. Gli stili di tema che definiscono l'aspetto predefinito di un controllo si basano sulla chiave implicita. Dal punto di vista della richiesta, la chiave implicita corrisponde il <xref:System.Type> del controllo stesso. Dal punto di vista della definizione della risorsa la chiave implicita corrisponde il <xref:System.Windows.Style.TargetType%2A> dello stile. Pertanto, se si siano creando temi per controlli personalizzati, la creazione di stili che interagiscono con stili di tema esistenti non devi specificare un [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) tale <xref:System.Windows.Style>. E se si vogliono usare stili con tema, non è necessario specificare alcuno stile. Ad esempio, la definizione di stile seguente funziona, anche se il <xref:System.Windows.Style> risorse sembra non disporre di una chiave:  
  
 [!code-xaml[FEResourceSH_snip#ImplicitStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page2.xaml#implicitstyle)]  
  
 Che stile dispone effettivamente di una chiave: la chiave implicita `typeof(` <xref:System.Windows.Controls.Button> `)`. Nel markup, è possibile specificare una <xref:System.Windows.Style.TargetType%2A> direttamente come tipo di nome (o è possibile usare facoltativamente [{... x: Type}](../../../../docs/framework/xaml-services/x-type-markup-extension.md) per restituire un <xref:System.Type>.  
  
 Tramite i meccanismi di stile del tema predefinito utilizzati da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], che lo stile viene applicato come stile di runtime di un <xref:System.Windows.Controls.Button> nella pagina, anche se il <xref:System.Windows.Controls.Button> stesso non tenta di specificare relativo <xref:System.Windows.FrameworkElement.Style%2A> proprietà o una risorsa specifica Fare riferimento allo stile. Lo stile definito nella pagina viene trovato prima nella sequenza di ricerca che nello stile del dizionario temi, tramite la stessa chiave di quest'ultimo. È possibile specificare semplicemente `<Button>Hello</Button>` in un punto qualsiasi nella pagina e lo stile definito con <xref:System.Windows.Style.TargetType%2A> di `Button` verrà applicata a tale pulsante. Se si desidera, è possibile usare in modo esplicito una chiave lo stile con lo stesso valore di tipo come <xref:System.Windows.Style.TargetType%2A>per maggiore chiarezza nel markup, ma che è facoltativo.  
  
 Le chiavi implicite per gli stili non sono applicabili in un controllo se <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> viene `true` (si noti anche che <xref:System.Windows.FrameworkElement.OverridesDefaultStyle%2A> potrebbe essere impostato come parte del comportamento nativo per la classe del controllo, anziché in modo esplicito in un'istanza del controllo). Inoltre, per supportare le chiavi implicite per gli scenari di classe derivata, il controllo deve eseguire l'override <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> (tutti i controlli esistenti forniti come parte di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] eseguire questa operazione). Per altre informazioni sulla progettazione di controlli, temi e stili, vedere [linee guida per la progettazione di controlli di stile](../../../../docs/framework/wpf/controls/guidelines-for-designing-stylable-controls.md).  
  
 <xref:System.Windows.DataTemplate> ha anche una chiave implicita. La chiave implicita per un <xref:System.Windows.DataTemplate> è il <xref:System.Windows.DataTemplate.DataType%2A> valore della proprietà. <xref:System.Windows.DataTemplate.DataType%2A> può anche essere specificato come il nome del tipo anziché in modo esplicito usando [{... x: Type} ](../../../../docs/framework/xaml-services/x-type-markup-extension.md). Per informazioni dettagliate, vedere [Cenni preliminari sui modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.ResourceDictionary>  
 [Risorse di applicazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Risorse e codice](../../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [Definire e fare riferimento a una risorsa](../../../../docs/framework/wpf/advanced/how-to-define-and-reference-a-resource.md)  
 [Cenni preliminari sulla gestione di applicazioni](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [Estensione di markup x:Type](../../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [Estensione di markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)  
 [Estensione del markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
