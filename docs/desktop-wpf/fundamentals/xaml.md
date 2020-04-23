---
title: Panoramica di XAML
description: Informazioni sul modo in cui il linguaggio XAML è strutturato e implementato da Windows Presentation Foundation (WPF) per .NET Core.
author: thraka
ms.date: 08/08/2019
ms.author: adegeo
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interfaces [XAML]
- classes [XAML]
- root element [XAML]
- XAML [WPF], about XAML
- base classes [XAML]
- routed events [WPF]
- code-behind files [WPF], XAML
- collection properties [XAML]
- events [XAML]
- property element [XAML]
- content models [XAML]
- Extensible Application Markup Language (see XAML)
- attribute syntax [XAML]
ms.openlocfilehash: b0a9357b623fbde08731a5b1ddb8fee3a93824c2
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "82071787"
---
# <a name="xaml-overview-in-wpf"></a>Cenni preliminari su XAML in WPF

In questo articolo vengono descritte le funzionalità del linguaggio XAML e viene illustrato come è possibile utilizzare XAML per scrivere app Windows Presentation Foundation (WPF). Questo articolo descrive in modo specifico XAML come implementato da WPF. XAML è un concetto di linguaggio più ampio rispetto a WPF.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-xaml"></a>Informazioni su XAML

XAML è un linguaggio di markup dichiarativo. Come applicato al modello di programmazione .NET Core, XAML semplifica la creazione di un'interfaccia utente per un'app .NET Core. È possibile creare elementi dell'interfaccia utente visibili nel markup XAML dichiarativo, quindi separare la definizione dell'interfaccia utente dalla logica di runtime utilizzando file code-behind uniti al markup tramite definizioni di classe parziali. XAML rappresenta in modo diretto la creazione di istanze di oggetti in un set specifico di tipi di supporto definiti in assembly. In ciò si differenzia dalla maggior parte degli altri linguaggi di markup, che sono in genere linguaggi interpretati senza un legame diretto con il sistema di tipi di supporto. XAML Abilita un flusso di lavoro in cui le parti separate possono funzionare sull'interfaccia utente e la logica di un'app, usando strumenti potenzialmente diversi.

Se rappresentati come testo, i file XAML sono file XML, in genere con estensione `.xaml`. I file possono essere codificati tramite qualsiasi codifica XML, tuttavia la codifica tipica è UTF-8.

Nell'esempio seguente viene illustrato come creare un pulsante come parte di un'interfaccia utente. Questo esempio è destinato a fornire una versione di XAML che rappresenta le metafore comuni di programmazione dell'interfaccia utente (non è un esempio completo).

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

## <a name="xaml-syntax-in-brief"></a>Sintassi XAML in breve

Le sezioni seguenti descrivono le forme di base della sintassi XAML e offrono un breve esempio di markup. L'obiettivo di queste sezioni non consiste nell'offrire informazioni complete su ogni forma di sintassi, ad esempio sulla modalità di rappresentazione di queste sintassi nel sistema di tipi di supporto. Per ulteriori informazioni sulle specifiche della sintassi XAML, vedere [sintassi XAML in dettaglio](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

La maggior parte del materiale nelle prossime sezioni sarà elementare se si ha familiarità con il linguaggio XML. Ciò è dovuto a uno dei principi di base della progettazione XAML. Il linguaggio XAML definisce i concetti propri, ma questi concetti funzionano all'interno del linguaggio XML e del formato di markup.

### <a name="xaml-object-elements"></a>Elementi oggetto XAML

In genere, un elemento oggetto dichiara un'istanza di un tipo. Tale tipo viene definito negli assembly a cui fa riferimento la tecnologia che utilizza XAML come linguaggio.

La sintassi degli elementi oggetto inizia sempre con una parentesi angolare di apertura (`<`), seguita dal nome del tipo in cui si desidera creare un'istanza. (Il nome può includere un prefisso, un concetto che verrà illustrato più avanti). Successivamente, è possibile dichiarare facoltativamente gli attributi sull'elemento oggetto. Per completare il tag dell'elemento oggetto, terminare con una parentesi angolare di chiusura (`>`). È invece possibile usare un form di chiusura automatica senza contenuto, completando il tag con una barra e una parentesi angolare di chiusura in successione (`/>`). Si osservi, ad esempio, il frammento di markup mostrato in precedenza.

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

Vengono specificati due elementi oggetto: `<StackPanel>` (con contenuto e un tag di chiusura successivo) e `<Button .../>` (forma di chiusura automatica, con diversi attributi). Gli elementi `StackPanel` oggetto e `Button` ogni mapping al nome di una classe definita da WPF e fanno parte degli assembly WPF. Quando si specifica un tag di elemento oggetto, si crea un'istruzione per l'elaborazione XAML per creare una nuova istanza del tipo sottostante. Ogni istanza viene creata chiamando il costruttore senza parametri del tipo sottostante durante l'analisi e il caricamento del codice XAML.

### <a name="attribute-syntax-properties"></a>Sintassi degli attributi (proprietà)

Spesso le proprietà di un oggetto possono essere espresse come attributi dell'elemento oggetto. La sintassi dell'attributo assegna un nome alla proprietà dell'oggetto da impostare, seguita dall'operatore di assegnazione (=). Il valore di un attributo viene sempre specificato come stringa inclusa tra virgolette.

La sintassi per attributi è la sintassi per l'impostazione di proprietà più semplice, nonché la più intuitiva per gli sviluppatori che hanno già usato linguaggi di markup in passato. Il markup seguente, ad esempio, crea un pulsante che presenta un testo rosso e uno sfondo blu oltre a un testo visualizzato specificato come `Content`.

[!code-xaml[XAMLOvwSupport#BlueRedButton](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]

### <a name="property-element-syntax"></a>Sintassi per gli elementi proprietà

Per alcune proprietà di un elemento oggetto, non si può usare la sintassi per attributi in quanto non è possibile esprimere l'oggetto o le informazioni necessarie per indicare il valore di proprietà in modo adeguato tra virgolette e nel rispetto delle limitazioni della stringa della sintassi di attributo. In questi casi, è possibile usare una sintassi diversa, nota come sintassi per elementi proprietà.

La sintassi per il tag di inizio dell'elemento `<TypeName.PropertyName>`proprietà è. In genere, il contenuto di tale tag è un elemento oggetto del tipo che la proprietà accetta come valore. Dopo aver specificato il contenuto, è necessario chiudere l'elemento Property con un tag di fine. La sintassi per il tag di fine `</TypeName.PropertyName>`è.

Se supportata, la sintassi per attributi è in genere più efficace e consente un markup più compatto. Si tratta tuttavia di una questione di stile e non di un limite tecnico. L'esempio seguente mostra le stesse proprietà impostate nell'esempio di sintassi per attributi precedente, tuttavia questa volta viene usata la sintassi per elementi proprietà per tutte le proprietà dell'oggetto `Button`.

[!code-xaml[XAMLOvwSupport#BlueRedButtonPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]

### <a name="collection-syntax"></a>Sintassi delle raccolte

Il linguaggio XAML include alcune ottimizzazioni che producono un markup più leggibile per l'utente. Una di queste ottimizzazioni prevede che se una proprietà specifica accetta un tipo di raccolta, gli elementi dichiarati nel markup come elementi figlio in quel valore della proprietà diventano di conseguenza parte della raccolta. In questo caso, una raccolta di elementi oggetto figlio corrisponde al valore impostato nella proprietà della raccolta.

Nell'esempio seguente viene illustrata la sintassi della raccolta per <xref:System.Windows.Media.GradientBrush.GradientStops%2A> l'impostazione dei valori della proprietà.

```xaml
<LinearGradientBrush>
  <LinearGradientBrush.GradientStops>
    <!-- no explicit new GradientStopCollection, parser knows how to find or create -->
    <GradientStop Offset="0.0" Color="Red" />
    <GradientStop Offset="1.0" Color="Blue" />
  </LinearGradientBrush.GradientStops>
</LinearGradientBrush>
```

### <a name="xaml-content-properties"></a>Proprietà del contenuto XAML

XAML specifica una funzionalità del linguaggio in base alla quale una classe può designare esattamente una delle relative proprietà come proprietà di _contenuto_ XAML. Per impostare il valore di questa proprietà di contenuto vengono usati gli elementi figlio. In altre parole, solo per la proprietà di contenuto, è possibile omettere un elemento proprietà quando si imposta tale proprietà nel markup XAML ed è possibile produrre una metafora padre/figlio più visibile nel markup.

Ad esempio, <xref:System.Windows.Controls.Border> specifica una proprietà di _contenuto_ di <xref:System.Windows.Controls.Decorator.Child%2A>. I due <xref:System.Windows.Controls.Border> elementi seguenti vengono trattati in modo identico. Il primo sfrutta la sintassi della proprietà di contenuto e omette l'elemento proprietà `Border.Child`. Il secondo specifica `Border.Child` in modo esplicito.

```xaml
<Border>
  <TextBox Width="300"/>
</Border>
<!--explicit equivalent-->
<Border>
  <Border.Child>
    <TextBox Width="300"/>
  </Border.Child>
</Border>
```

Secondo le regole del linguaggio XAML, il valore di una proprietà di contenuto XAML deve essere specificato completamente prima o completamente dopo qualsiasi altro elemento proprietà nell'elemento oggetto. Il markup seguente, ad esempio, non viene compilato.

```xaml
<Button>I am a
  <Button.Background>Blue</Button.Background>
  blue button</Button>
```

Per ulteriori informazioni sulle specifiche della sintassi XAML, vedere [sintassi XAML in dettaglio](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

### <a name="text-content"></a>Contenuto di testo

Un numero ridotto di elementi XAML può elaborare il testo direttamente come contenuto. A tale scopo, deve verificarsi uno dei casi seguenti:

- La classe deve dichiarare una proprietà di contenuto e tale proprietà di contenuto deve essere di un tipo assegnabile a una stringa (il tipo potrebbe <xref:System.Object>essere). Ad esempio, qualsiasi <xref:System.Windows.Controls.ContentControl> USA <xref:System.Windows.Controls.ContentControl.Content%2A> come proprietà di contenuto ed è di tipo <xref:System.Object>e questo supporta l'utilizzo seguente in un oggetto <xref:System.Windows.Controls.ContentControl> , ad esempio <xref:System.Windows.Controls.Button>: `<Button>Hello</Button>`.

- Il tipo deve dichiarare un convertitore di tipi e, in tal caso, il contenuto di testo viene usato come testo di inizializzazione per il convertitore di tipi. Ad esempio, `<Brush>Blue</Brush>` converte il valore di contenuto `Blue` di in un pennello. Nella pratica questo caso è meno comune.

- Il tipo deve essere un tipo primitivo noto del linguaggio XAML.

### <a name="content-properties-and-collection-syntax-combined"></a>Proprietà del contenuto e sintassi della raccolta combinate

Si consideri questo esempio.

```xaml
<StackPanel>
  <Button>First Button</Button>
  <Button>Second Button</Button>
</StackPanel>
```

Qui, ognuno <xref:System.Windows.Controls.Button> è un elemento figlio di <xref:System.Windows.Controls.StackPanel>. Si tratta di un markup semplice e intuitivo nel quale vengono omessi due tag per due ragioni diverse.

- **Elemento proprietà StackPanel. Children omesso:** <xref:System.Windows.Controls.StackPanel> deriva da <xref:System.Windows.Controls.Panel>. <xref:System.Windows.Controls.Panel>definisce <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> come proprietà di contenuto XAML.

- **Elemento oggetto UIElementCollection omesso:** La <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> proprietà accetta il tipo <xref:System.Windows.Controls.UIElementCollection>, che implementa <xref:System.Collections.IList>. Il tag dell'elemento della raccolta può essere omesso in base alle regole XAML per l'elaborazione di raccolte <xref:System.Collections.IList>, ad esempio. (In questo caso, <xref:System.Windows.Controls.UIElementCollection> non è possibile creare un'istanza di in quanto non espone un costruttore senza parametri ed è per questo motivo <xref:System.Windows.Controls.UIElementCollection> che l'elemento oggetto viene visualizzato come commento).

```xaml
<StackPanel>
  <StackPanel.Children>
    <!--<UIElementCollection>-->
    <Button>First Button</Button>
    <Button>Second Button</Button>
    <!--</UIElementCollection>-->
  </StackPanel.Children>
</StackPanel>
```

### <a name="attribute-syntax-events"></a>Sintassi degli attributi (Events)

È possibile usare la sintassi per attributi anche per membri che sono eventi anziché proprietà. In questo caso il nome dell'attributo corrisponde al nome dell'evento. Nell'implementazione WPF di eventi per XAML il valore dell'attributo corrisponde al nome di un gestore che implementa il delegato dell'evento. Il markup seguente, ad esempio, assegna un gestore per l' <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento a un <xref:System.Windows.Controls.Button> oggetto creato nel markup:

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

La correlazione tra eventi e XAML in WPF è molto più complessa di questo semplice esempio di sintassi per attributi. Ci si potrebbe chiedere ad esempio, cosa rappresenti `ClickHandler` a cui viene fatto riferimento e come questo venga definito. Questa operazione verrà illustrata nella sezione [eventi imminenti e code-behind XAML](#events-and-xaml-code-behind) di questo articolo.

## <a name="case-and-white-space-in-xaml"></a>Maiuscole e minuscole e spazi vuoti in XAML

In generale, XAML fa distinzione tra maiuscole e minuscole. Ai fini della risoluzione dei tipi di supporto, XAML WPF distingue tra maiuscole e minuscole dalle stesse regole che CLR fa distinzione tra maiuscole e minuscole. Gli elementi oggetto, gli elementi proprietà e i nomi di attributo devono essere sempre specificati usando correttamente le maiuscole e le minuscole quando si esegue il confronto del nome con il nome del tipo sottostante nell'assembly o con il nome di un membro di un tipo. Le parole chiave e le primitive del linguaggio XAML fanno distinzione tra maiuscole e minuscole. I valori non fanno sempre distinzione tra maiuscole e minuscole. Tale distinzione per i valori dipende dal comportamento del convertitore dei tipi associato alla proprietà che accetta il valore o al tipo di valore della proprietà. Ad esempio, le proprietà che accettano <xref:System.Boolean> il tipo possono assumere `true` o `True` come valori equivalenti, ma solo perché la conversione del tipo di parser XAML WPF nativo <xref:System.Boolean> per la stringa consente già tali valori come equivalenti.

I processori XAML WPF e i serializzatori ignoreranno o elimineranno tutti gli spazi vuoti non significativi e normalizzano gli spazi vuoti significativi. Questo comportamento è coerente con le raccomandazioni predefinite di comportamento dello spazio vuoto della specifica XAML. Questo comportamento è di conseguenza solo quando si specificano le stringhe all'interno delle proprietà del contenuto XAML. In termini più semplici, XAML converte spazi, avanzamento riga e caratteri di tabulazione in spazi, quindi conserva uno spazio se trovato a una delle estremità di una stringa contigua. La spiegazione completa della gestione degli spazi vuoti XAML non è illustrata in questo articolo. Per altre informazioni, vedere [elaborazione di spazi vuoti in XAML](../xaml-services/white-space-processing.md).

## <a name="markup-extensions"></a>Estensioni di markup

Le estensioni di markup sono un concetto del linguaggio XAML. Se usate per specificare il valore di una sintassi per attributi, le parentesi graffe (`{` e `}`) indicano l'uso di un'estensione di markup. Questo uso indica all'elaborazione XAML che, diversamente dal solito, i valori degli attributi non devono essere considerati valori di stringa letterale o valori convertibili in stringa.

Le estensioni di markup più comuni utilizzate nella programmazione di app [`Binding`](../../framework/wpf/advanced/binding-markup-extension.md)WPF sono utilizzate per le espressioni data binding e i riferimenti [`StaticResource`](../../framework/wpf/advanced/staticresource-markup-extension.md) alle [`DynamicResource`](../../framework/wpf/advanced/dynamicresource-markup-extension.md)risorse e. Le estensioni di markup consentono di usare la sintassi per attributi per specificare valori per le proprietà anche quando queste non supportano in generale una sintassi per attributi. Le estensioni di markup spesso utilizzano i tipi di espressione intermedia per abilitare funzionalità quali il rinvio di valori o il riferimento ad altri oggetti presenti solo in fase di esecuzione.

Il markup seguente, ad esempio, imposta il valore della <xref:System.Windows.FrameworkElement.Style%2A> proprietà utilizzando la sintassi dell'attributo. La <xref:System.Windows.FrameworkElement.Style%2A> proprietà accetta un'istanza della <xref:System.Windows.Style> classe, che per impostazione predefinita non è stato possibile creare un'istanza da una stringa di sintassi dell'attributo. Tuttavia, in questo caso, l'attributo fa riferimento a un'estensione `StaticResource`di markup particolare. Quando quell'estensione di markup viene elaborata, restituisce un riferimento a uno stile del quale in precedenza è stata creata un'istanza come risorsa con chiave in un dizionario di risorse.

[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources2)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources3](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources3)]

Per un elenco di riferimento di tutte le estensioni di markup per il linguaggio XAML implementato in modo specifico in WPF, vedere [Estensioni XAML WPF](../../framework/wpf/advanced/wpf-xaml-extensions.md). Per un elenco di riferimenti delle estensioni di markup definite da System. XAML e sono più diffuse per le implementazioni XAML di .NET Core, vedere [spazio dei nomi XAML (x:) Funzionalità del linguaggio](../xaml-services/namespace-language-features.md). Per altre informazioni sulle estensioni di markup, vedere [Estensioni di markup e WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

## <a name="type-converters"></a>Convertitori di tipi

La sezione [Cenni sulla sintassi XAML](#xaml-syntax-in-brief) afferma che il valore dell'attributo deve poter essere impostato tramite una stringa. La gestione nativa di base del modo in cui le stringhe vengono convertite in altri tipi di oggetti o valori <xref:System.String> primitivi si basa sul tipo stesso, oltre che sull'elaborazione nativa <xref:System.DateTime> per <xref:System.Uri>determinati tipi, ad esempio o. Tuttavia, molti tipi o membri WPF di questi tipi estendono il comportamento di elaborazione dell'attributo stringa di base in modo che le istanze di tipi di oggetti più complessi possano essere specificate come stringhe e attributi.

La <xref:System.Windows.Thickness> struttura è un esempio di un tipo con una conversione di tipo abilitata per gli utilizzi XAML. <xref:System.Windows.Thickness>indica le misurazioni all'interno di un rettangolo annidato e viene usato come valore <xref:System.Windows.FrameworkElement.Margin%2A>per le proprietà come. Inserendo un convertitore di tipi in <xref:System.Windows.Thickness>, tutte le proprietà che usano <xref:System.Windows.Thickness> un oggetto sono più semplici da specificare in XAML perché possono essere specificate come attributi. Nell'esempio seguente viene utilizzata una conversione di tipo e una sintassi di attributo per fornire <xref:System.Windows.FrameworkElement.Margin%2A>un valore per un oggetto:

[!code-xaml[XAMLOvwSupport#MarginTCE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]

L'esempio di sintassi dell'attributo precedente è equivalente all'esempio di sintassi più dettagliata seguente, in <xref:System.Windows.FrameworkElement.Margin%2A> cui è invece impostato tramite la sintassi dell'elemento <xref:System.Windows.Thickness> proprietà contenente un elemento oggetto. Le quattro proprietà chiave di <xref:System.Windows.Thickness> vengono impostate come attributi nella nuova istanza:

[!code-xaml[XAMLOvwSupport#MarginVerbose](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]

> [!NOTE]
> Esiste anche un numero limitato di oggetti in cui la conversione del tipo è l'unico modo pubblico per impostare una proprietà su tale tipo senza coinvolgere una sottoclasse, perché il tipo stesso non ha un costruttore senza parametri. Un esempio è <xref:System.Windows.Input.Cursor>.

Per ulteriori informazioni sulla conversione dei tipi, vedere [TypeConverter e XAML](../../framework/wpf/advanced/typeconverters-and-xaml.md).

## <a name="xaml-root-elements-and-xaml-namespaces"></a>Elementi radice XAML e spazi dei nomi XAML

Un file XAML deve avere un solo elemento radice, per essere un file XML ben formato e un file XAML valido. Per gli scenari WPF tipici, si usa un elemento radice che ha un significato importante nel modello di app WPF (ad esempio <xref:System.Windows.Window> , <xref:System.Windows.Controls.Page> o per una pagina <xref:System.Windows.ResourceDictionary> , per un dizionario esterno o <xref:System.Windows.Application> per la definizione dell'app). Nell'esempio seguente viene illustrato l'elemento radice di un tipico file XAML per una pagina WPF, con l'elemento radice <xref:System.Windows.Controls.Page>di.

[!code-xaml[XAMLOvwSupport#RootOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]
[!code-xaml[XAMLOvwSupport#RootOnly2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]

L'elemento radice inoltre contiene gli attributi `xmlns` e `xmlns:x`, che indicano a un processore XAML gli spazi dei nomi XAML contenenti le definizioni dei tipi per i tipi di supporto a cui il markup farà riferimento come elementi. L'attributo `xmlns` indica in modo specifico lo spazio dei nomi XAML predefinito. All'interno dello spazio dei nomi XAML predefinito gli elementi oggetto nel markup possono essere specificati senza prefisso. Per la maggior parte degli scenari di app WPF e per quasi tutti gli esempi forniti nelle sezioni WPF dell'SDK, viene eseguito il mapping dello spazio dei nomi XAML predefinito `http://schemas.microsoft.com/winfx/2006/xaml/presentation`allo spazio dei nomi WPF. L'attributo `xmlns:x` indica uno spazio dei nomi XAML aggiuntivo, che viene mappato allo spazio dei nomi del linguaggio XAML `http://schemas.microsoft.com/winfx/2006/xaml`.

Tale uso di `xmlns` per definire un ambito per l'uso e il mapping di un NameScope è coerente con la specifica XML 1.0. I NameScope XAML sono diversi dai NameScope XML solo in quanto nei primi vengono indicati anche alcuni aspetti correlati al supporto degli elementi del NameScope da parte dei tipi riguardo a risoluzione dei tipi e analisi di XAML.

Gli `xmlns` attributi sono strettamente necessari solo sull'elemento radice di ogni file XAML. Le definizioni `xmlns` si applicheranno a tutti gli elementi discendenti dell'elemento radice, un comportamento coerente con la specifica XML 1.0 per `xmlns`. Gli attributi `xmlns` sono inoltre consentiti in altri elementi sottostanti la radice e si applicherebbero a qualsiasi elemento discendente dell'elemento di definizione. Tuttavia, la definizione o ridefinizione frequente degli spazi dei nomi XAML può risultare in uno stile di markup XAML di difficile lettura.

L'implementazione WPF del processore XAML include un'infrastruttura che ha la consapevolezza degli assembly di base di WPF. Gli assembly di base di WPF sono noti che contengono i tipi che supportano i mapping WPF allo spazio dei nomi XAML predefinito. Ciò è consentito tramite la configurazione inclusa nel file di compilazione del progetto e nei sistemi di compilazione e del progetto WPF. Pertanto, la dichiarazione dello spazio dei nomi XAML predefinito come `xmlns` impostazione predefinita è sufficiente per fare riferimento a elementi XAML che provengono da assembly WPF.

### <a name="the-x-prefix"></a>Prefisso x:

L'esempio di elemento radice precedente usa il prefisso `x:` per eseguire il mapping dello spazio dei nomi XAML `http://schemas.microsoft.com/winfx/2006/xaml`, che è lo spazio dei nomi XAML dedicato che supporta costrutti di linguaggio XAML. Questo `x:` prefisso viene usato per il mapping di questo spazio dei nomi XAML nei modelli per i progetti, negli esempi e nella documentazione in questo SDK. Lo spazio dei nomi XAML per il linguaggio XAML contiene diversi costrutti di programmazione che si utilizzeranno di frequente nel codice XAML. Di seguito viene presentato un elenco dei più comuni costrutti di programmazione del prefisso `x:` che verranno usati:

- [x:Key](../xaml-services/xkey-directive.md): imposta una chiave univoca per ogni risorsa in <xref:System.Windows.ResourceDictionary> un (o concetti del dizionario simili in altri Framework). `x:Key`probabilmente sarà conto del 90% degli `x:` utilizzi che saranno visualizzati in un tipico markup dell'app WPF.

- [x:class](../xaml-services/xclass-directive.md): specifica lo spazio dei nomi CLR e il nome della classe per la classe che fornisce il code-behind per una pagina XAML. È necessario che tale classe supporti il code-behind per ciascun modello di programmazione WPF ed è per questa ragione che quasi sempre viene eseguito il mapping di `x:`, anche se non sono presenti risorse.

- [x:Name](../xaml-services/xname-directive.md): specifica il nome di un oggetto di runtime per l'istanza presente nel codice della fase di esecuzione dopo l'elaborazione di un elemento oggetto. In generale, si usa spesso una proprietà equivalente definita in WPF per [x:Name](../xaml-services/xname-directive.md). Tali proprietà vengono mappate in modo specifico a una proprietà di supporto CLR e sono quindi più convenienti per la programmazione di app, in cui spesso si usa il codice di run-time per trovare gli elementi denominati dal codice XAML inizializzato. La proprietà più comune è <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>. È comunque possibile utilizzare [x:Name](../xaml-services/xname-directive.md) quando la proprietà equivalente a livello <xref:System.Windows.FrameworkElement.Name%2A> di Framework WPF non è supportata in un tipo particolare. Tale situazione si verifica in determinati scenari di animazione.

- [x:Static](../xaml-services/xstatic-markup-extension.md): abilita il riferimento che restituisce un valore statico che non costituisce in altro modo una proprietà compatibile con XAML.

- [x:Type](../xaml-services/xtype-markup-extension.md): costruisce un <xref:System.Type> riferimento basato su un nome di tipo. Viene usato per specificare gli attributi che accettano <xref:System.Type>, ad esempio <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>, anche se spesso la proprietà ha una stringa nativa per<xref:System.Type> la conversione in modo tale che l'utilizzo dell'estensione di markup [x:Type](../xaml-services/xtype-markup-extension.md) sia facoltativo.

Nel prefisso `x:` o nello spazio dei nomi XAML sono presenti altri costrutti di programmazione non altrettanto comuni. Per informazioni dettagliate, vedere [Funzionalità del linguaggio dello spazio dei nomi XAML (x:)](../xaml-services/namespace-language-features.md).

## <a name="custom-prefixes-and-custom-types-in-xaml"></a>Prefissi personalizzati e tipi personalizzati in XAML

Per gli assembly personalizzati o per gli assembly esterni al nucleo WPF di **PresentationCore**, **PresentationFramework** e **WindowsBase**, è possibile specificare l'assembly come parte di un mapping personalizzato `xmlns` . È quindi possibile fare riferimento ai tipi dell'assembly in XAML, purché tale tipo sia stato implementato correttamente per supportare gli usi di XAML desiderati.

Di seguito è riportato un esempio di base del funzionamento dei prefissi personalizzati nel markup XAML. Il prefisso `custom` viene definito nel tag dell'elemento radice e mappato a un assembly specifico che è incluso in un pacchetto e disponibile con l'app. Questo assembly contiene un tipo `NumericUpDown`, implementato per supportare l'uso generale di XAML, nonché l'uso di un'ereditarietà delle classi che ne consenta l'inserimento in questo punto specifico in un modello di contenuto XAML WPF. Un'istanza di questo controllo `NumericUpDown` viene dichiarata come elemento oggetto, usando il prefisso in modo tale che un parser XAML sia in grado di riconoscere lo spazio dei nomi XAML contenente il tipo e pertanto la posizione dell'assembly di supporto che contiene la definizione del tipo.

```xaml
<Page
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:custom="clr-namespace:NumericUpDownCustomControl;assembly=CustomLibrary"
    >
  <StackPanel Name="LayoutRoot">
    <custom:NumericUpDown Name="numericCtrl1" Width="100" Height="60"/>
...
  </StackPanel>
</Page>
```

Per altre informazioni sui tipi personalizzati in XAML, vedere [XAML e classi personalizzate per WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).

Per ulteriori informazioni sulla correlazione tra gli spazi dei nomi XML e gli spazi dei nomi di codice negli assembly, vedere [spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).

## <a name="events-and-xaml-code-behind"></a>Eventi e code-behind XAML

La maggior parte delle app WPF è costituita da markup XAML e code-behind. All'interno di un progetto, XAML viene scritto come `.xaml` file e viene usato un linguaggio CLR quale Microsoft Visual Basic o C# per scrivere un file code-behind. Durante la compilazione dal markup di un file XAML come parte dei modelli di applicazione e di programmazione WPF, il percorso del file code-behind XAML per un file XAML viene identificato specificando uno spazio dei nomi e una classe come attributo `x:Class` dell'elemento radice della pagina XAML.

Gli esempi riportati fino a questo momento illustrano molti pulsanti, nessuno dei quali era associato a un comportamento logico. Il meccanismo primario a livello di applicazione per l'aggiunta di un comportamento per un elemento oggetto consiste nell'utilizzo di un evento esistente della classe dell'elemento e nella scrittura di un gestore specifico per l'evento che viene richiamato quando l'evento viene generato in fase di esecuzione. Il nome dell'evento e il nome del gestore da usare sono specificati nel markup, mentre il codice che implementa il gestore è definito nel code-behind.

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

[!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
[!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]

Si noti che il file code-behind usa lo spazio dei nomi CLR `ExampleNamespace` e dichiara `ExamplePage` come classe parziale all'interno di tale spazio dei nomi. Questo è parallelo al valore dell'attributo `x:Class` di `ExampleNamespace``ExamplePage` offerto nella radice del markup. Il compilatore del markup WPF creerà una classe parziale per ogni file XAML compilato derivando una classe dal tipo di elemento radice. Quando si fornisce code-behind che definisce anche la stessa classe parziale, il codice risultante viene combinato nello stesso spazio dei nomi e nella stessa classe dell'app compilata.

Per ulteriori informazioni sui requisiti per la programmazione code-behind in WPF, vedere [code-behind, gestore eventi e requisiti della classe parziale in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md#code-behind-event-handler-and-partial-class-requirements-in-wpf).

Se non si desidera creare un file code-behind distinto, è anche possibile incorporare il codice in un file XAML. Tuttavia, il codice inline è una tecnica meno versatile che presenta limitazioni sostanziali. Per altre informaiton, vedere [code-behind e XAML in WPF](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

### <a name="routed-events"></a>Eventi indirizzati

Una particolare funzionalità evento fondamentale per WPF è un evento indirizzato. Gli eventi indirizzati consentono a un elemento di gestire un evento generato da un elemento diverso, purché gli elementi siano connessi tramite una relazione di struttura ad albero. Quando si specifica la gestione dell'evento con un attributo XAML, l'evento indirizzato può essere ascoltato e gestito in qualsiasi elemento, inclusi quelli che non elencano l'evento specifico nella tabella dei membri della classe. Ciò è possibile qualificando l'attributo del nome evento con il nome della classe di appartenenza. Ad esempio, l'elemento `StackPanel` padre nell'esempio in `StackPanel`  /  `Button` corso potrebbe registrare un gestore per l' <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento del pulsante dell'elemento figlio specificando l' `Button.Click` attributo nell' `StackPanel` elemento oggetto, con il nome del gestore come valore dell'attributo. Per ulteriori informazioni, vedere [Cenni preliminari sugli eventi indirizzati](../../framework/wpf/advanced/routed-events-overview.md).

## <a name="xaml-named-elements"></a>Elementi denominati XAML

Per impostazione predefinita, l'istanza di oggetto creata in un oggetto grafico tramite l'elaborazione di un elemento oggetto XAML non possiede un identificatore univoco o un riferimento a un oggetto. Al contrario, se si chiama un costruttore nel codice, quasi sempre il risultato del costruttore viene usato per impostare una variabile sull'istanza creata, in modo che sia possibile fare riferimento all'istanza nel codice in un secondo momento. Per offrire accesso standard agli oggetti creati tramite una definizione del markup, in XAML viene definito l'[attributo x:Name](../xaml-services/xname-directive.md). È possibile impostare il valore dell'attributo `x:Name` in qualsiasi elemento oggetto. All'interno del code-behind l'identificatore scelto è equivalente a una variabile dell'istanza che fa riferimento all'istanza costruita. In tutti i casi, gli elementi denominati funzionano come istanze di oggetti (il nome fa riferimento a tale istanza) e il code-behind può fare riferimento agli elementi denominati per gestire le interazioni in fase di esecuzione all'interno dell'app. Questa connessione tra istanze e variabili viene eseguita dal compilatore di markup XAML di WPF e più specificamente implicano funzionalità e modelli, <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> ad esempio, che non verranno illustrati in dettaglio in questo articolo.

Gli elementi XAML a livello di Framework WPF <xref:System.Windows.FrameworkElement.Name%2A> ereditano una proprietà, equivalente all'attributo definito `x:Name` da XAML. Altre classi offrono equivalenti a livello di proprietà per `x:Name`, che in genere viene definito anche come proprietà `Name`. In generale se non è possibile individuare una proprietà `Name` nella tabella dei membri dell'elemento o del tipo scelto, usare `x:Name` in alternativa. I `x:Name` valori forniranno un identificatore a un elemento XAML che può essere utilizzato in fase di esecuzione, in base a sottosistemi specifici o a metodi di utilità quali <xref:System.Windows.FrameworkElement.FindName%2A>.

Nell'esempio seguente viene <xref:System.Windows.FrameworkElement.Name%2A> impostato su <xref:System.Windows.Controls.StackPanel> un elemento. Quindi, un gestore su un <xref:System.Windows.Controls.Button> oggetto all' <xref:System.Windows.Controls.StackPanel> interno di <xref:System.Windows.Controls.StackPanel> che fa riferimento a `buttonContainer` tramite il relativo <xref:System.Windows.FrameworkElement.Name%2A>riferimento all'istanza impostato da.

[!code-xaml[XAMLOvwSupport#NamedE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]
[!code-xaml[XAMLOvwSupport#NamedE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]

[!code-csharp[XAMLOvwSupport#NameCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
[!code-vb[XAMLOvwSupport#NameCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]

Come accade per una variabile, il nome XAML di un'istanza è governato da un concetto di ambito, per cui è possibile attivare nomi che siano univoci all'interno di un determinato ambito prevedibile. Il markup primario che definisce una pagina denota un NameScope XAML univoco, il cui limite è costituito dall'elemento radice della pagina. Tuttavia, altre origini di markup possono interagire con una pagina in fase di esecuzione, ad esempio stili o modelli all'interno degli stili, e tali origini di markup hanno spesso i propri ambiti dei nomi XAML che non si connettono necessariamente al NameScope XAML della pagina. Per ulteriori informazioni sugli `x:Name` ambiti dei nomi XAML e <xref:System.Windows.FrameworkElement.Name%2A>, vedere, [direttiva x:Name](../xaml-services/xname-directive.md)o [NameScope XAML WPF](../../framework/wpf/advanced/wpf-xaml-namescopes.md).

## <a name="attached-properties-and-attached-events"></a>Proprietà associate ed eventi associati

XAML specifica una funzionalità del linguaggio che consente di definire determinati eventi o proprietà in qualsiasi elemento, indipendentemente dalla presenza della proprietà o dell'evento all'interno delle definizioni del tipo per l'elemento per cui è impostato l'evento o la proprietà. La versione delle proprietà di questa funzionalità è denominata proprietà associata, la versione degli eventi è denominata evento associato. Concettualmente, è possibile pensare alle proprietà associate e agli eventi associati come a membri globali che possono essere impostati in qualsiasi elemento o istanza di oggetto XAML. Tuttavia, tale elemento, classe o infrastruttura più ampia dovrà supportare un archivio delle proprietà di supporto per i valori associati.

Le proprietà associate in XAML vengono in genere usate tramite la sintassi per attributi. Nella sintassi dell'attributo specificare una proprietà associata nel form `ownerType.propertyName`.

In apparenza, questo è simile all'utilizzo di un elemento proprietà, ma in questo caso `ownerType` l'oggetto specificato è sempre un tipo diverso rispetto all'elemento oggetto in cui viene impostata la proprietà associata. `ownerType`tipo che fornisce i metodi della funzione di accesso richiesti da un processore XAML per ottenere o impostare il valore della proprietà associata.

Lo scenario più comune per le proprietà associate consiste nel consentire agli elementi figlio di segnalare un valore di proprietà al relativo elemento padre.

Nell'esempio seguente viene illustrata <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> la proprietà associata. La <xref:System.Windows.Controls.DockPanel> classe definisce le funzioni di accesso <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> per e pertanto possiede la proprietà associata. La <xref:System.Windows.Controls.DockPanel> classe include anche la logica che scorre gli elementi figlio e controlla in modo specifico ogni elemento per un valore <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>impostato. Se individuato, quel valore viene usato durante il layout per posizionare gli elementi figlio. L'uso della <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà associata e di questa funzionalità di posizionamento è infatti lo scenario motivante per <xref:System.Windows.Controls.DockPanel> la classe.

[!code-xaml[XAMLOvwSupport#DockAP](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]

In WPF, la maggior parte o tutte le proprietà associate vengono implementate anche come proprietà di dipendenza. Per altre informazioni, vedere [Cenni preliminari sulle proprietà associate](../../framework/wpf/advanced/attached-properties-overview.md).

Gli eventi associati utilizzano una `ownerType.eventName` forma simile di sintassi degli attributi. Come per gli eventi non associati, il valore dell'attributo per un evento associato in XAML specifica il nome del metodo di gestione richiamato quando l'evento viene gestito nell'elemento. Gli usi di eventi associati in XAML WPF sono meno comuni. Per altre informazioni, vedere [Cenni preliminari sugli eventi associati](../../framework/wpf/advanced/attached-events-overview.md).

## <a name="base-types-and-xaml"></a>Tipi di base e XAML

Il codice XAML WPF sottostante e il relativo spazio dei nomi XAML sono una raccolta di tipi che corrispondono agli oggetti CLR, oltre agli elementi di markup per XAML. Tuttavia non è possibile eseguire il mapping di tutte le classi agli elementi. Le classi astratte, <xref:System.Windows.Controls.Primitives.ButtonBase>ad esempio, e alcune classi di base non astratte, vengono utilizzate per l'ereditarietà nel modello di oggetti CLR. Le classi di base, incluse quelle astratte, continuano a essere importanti per lo sviluppo di XAML, in quanto ciascuno degli elementi XAML concreti eredita i membri da una classe di base nella relativa gerarchia. Spesso tali membri includono proprietà che possono essere impostate come attributi nell'elemento oppure eventi che possono essere gestiti. <xref:System.Windows.FrameworkElement>è la classe di base dell'interfaccia utente di base concreta di WPF a livello di Framework WPF. Quando si progetta l'interfaccia utente, si useranno varie classi Shape, Panel, Decorator o Control, che derivano tutte da <xref:System.Windows.FrameworkElement>. Una classe di base correlata, <xref:System.Windows.FrameworkContentElement>, supporta gli elementi orientati ai documenti che funzionano bene per una presentazione del layout del flusso, usando le API <xref:System.Windows.FrameworkElement>che rispecchiano intenzionalmente le API in. La combinazione di attributi a livello di elemento e un modello a oggetti CLR fornisce un set di proprietà comuni che è possibile impostare sulla maggior parte degli elementi XAML concreti, indipendentemente dall'elemento XAML specifico e dal tipo sottostante.

## <a name="xaml-security"></a>Sicurezza XAML

XAML è un linguaggio di markup che rappresenta direttamente la creazione di istanze di oggetti e la relativa esecuzione. Gli elementi creati in XAML, pertanto, hanno la stessa capacità di interagire con risorse di sistema (quali accesso di rete e IO file system) del codice generato equivalente. Il codice XAML caricato in un'app completamente attendibile ha lo stesso accesso alle risorse di sistema dell'applicazione host.

### <a name="code-access-security-cas-in-wpf"></a>Sicurezza dall'accesso di codice (CAS) in WPF

**Questa sezione si applica solo ai .NET Framework. WPF per .NET Core non supporta le autorità di certificazione. Per altre informazioni, vedere [differenze di sicurezza dall'accesso di codice](../migration/differences-from-net-framework.md#code-access-security).**

WPF per .NET Framework supporta la sicurezza dall'accesso di codice (CAS). Ciò significa che il contenuto WPF in esecuzione nell'area Internet ha autorizzazioni di esecuzione ridotte. "XAML separato" (pagine di XAML non compilato interpretate in fase di caricamento da un visualizzatore XAML) e l'applicazione XBAP vengono in genere eseguite in questa area Internet e usano lo stesso set di autorizzazioni. Il codice XAML caricato in un'applicazione completamente attendibile, tuttavia, dispone dello stesso accesso alle risorse di sistema dell'applicazione host. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../../framework/wpf/wpf-partial-trust-security.md).

## <a name="loading-xaml-from-code"></a>Caricamento di XAML dal codice

Sebbene sia possibile usare XAML per definire un'interfaccia utente completa, è talvolta opportuno definire solo una parte dell'interfaccia utente tramite XAML. Questa funzionalità può risultare utile per consentire una personalizzazione parziale, l'archiviazione locale di informazioni, l'uso di XAML per offrire un oggetto business o per molti altri scenari possibili. La chiave di questi scenari è la <xref:System.Windows.Markup.XamlReader> classe e il <xref:System.Windows.Markup.XamlReader.Load%2A> relativo metodo. L'input è un file XAML, mentre l'output è un oggetto che rappresenta l'intera struttura ad albero di oggetti di runtime creata dal markup. È quindi possibile inserire l'oggetto in modo che sia una proprietà di un altro oggetto già esistente nell'app. Finché la proprietà è una proprietà appropriata nel modello di contenuto con funzionalità di visualizzazione finali e che invierà una notifica al motore di esecuzione in cui è stato aggiunto nuovo contenuto nell'app, è possibile modificare facilmente il contenuto di un'app in esecuzione eseguendo il caricamento in XAML. Per .NET Framework, questa funzionalità è in genere disponibile solo in applicazioni con attendibilità totale, a causa delle implicazioni di sicurezza del caricamento di file in applicazioni durante l'esecuzione.

## <a name="see-also"></a>Vedere anche

- [Descrizione dettagliata della sintassi XAML](../../framework/wpf/advanced/xaml-syntax-in-detail.md)
- [Classi XAML e personalizzate per WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Spazio dei nomi XAML (x:) Funzionalità del linguaggio](../xaml-services/namespace-language-features.md)
- [Estensioni XAML WPF](../../framework/wpf/advanced/wpf-xaml-extensions.md)
- [Cenni preliminari sugli elementi di base](../../framework/wpf/advanced/base-elements-overview.md)
- [Strutture ad albero in WPF](../../framework/wpf/advanced/trees-in-wpf.md)
