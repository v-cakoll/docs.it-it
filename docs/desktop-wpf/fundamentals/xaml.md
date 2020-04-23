---
title: Panoramica di XAML
description: Informazioni su come il linguaggio XAML è strutturato e implementato da Windows Presentation Foundation (WPF) per .NET Core.
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
# <a name="xaml-overview-in-wpf"></a>XAML overview in WPF

Questo articolo descrive le funzionalità del linguaggio XAML e illustra come usare XAML per scrivere app Windows Presentation Foundation (WPF). In questo articolo viene descritto in modo specifico XAML come implementato da WPFWPF. XAML stesso è un concetto di linguaggio più ampio di WPFWPF.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="what-is-xaml"></a>Che cos'è XAML

XAML è un linguaggio di markup dichiarativo. Se applicato al modello di programmazione .NET Core, XAML semplifica la creazione di un'interfaccia utente per un'app .NET Core.As applied to the .NET Core programming model, XAML seslifies creating a UI for a .NET Core app. È possibile creare elementi dell'interfaccia utente visibili nel markup XAML dichiarativo e quindi separare la definizione dell'interfaccia utente dalla logica di runtime usando file code-behind uniti al markup tramite definizioni di classe parziali. XAML rappresenta in modo diretto la creazione di istanze di oggetti in un set specifico di tipi di supporto definiti in assembly. In ciò si differenzia dalla maggior parte degli altri linguaggi di markup, che sono in genere linguaggi interpretati senza un legame diretto con il sistema di tipi di supporto. XAML consente un flusso di lavoro in cui parti separate possono lavorare sull'interfaccia utente e la logica di un'app, usando strumenti potenzialmente diversi.

Se rappresentati come testo, i file XAML sono file XML, in genere con estensione `.xaml`. I file possono essere codificati tramite qualsiasi codifica XML, tuttavia la codifica tipica è UTF-8.

Nell'esempio seguente viene illustrato come creare un pulsante come parte di un'interfaccia utente. Questo esempio ha lo scopo di fornire un'esperienza di xaml in che modo XAML rappresenta metafore comuni di programmazione dell'interfaccia utente (non è un esempio completo).

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

## <a name="xaml-syntax-in-brief"></a>Sintassi XAML in breve

Le sezioni seguenti descrivono le forme di base della sintassi XAML e offrono un breve esempio di markup. L'obiettivo di queste sezioni non consiste nell'offrire informazioni complete su ogni forma di sintassi, ad esempio sulla modalità di rappresentazione di queste sintassi nel sistema di tipi di supporto. Per ulteriori informazioni sulle specifiche della sintassi XAML, vedere [Sintassi XAML in dettaglio](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

Gran parte del materiale nelle prossime sezioni sarà elementare per voi se si ha una precedente familiarità con il linguaggio XML. Ciò è dovuto a uno dei principi di base della progettazione XAML. Il linguaggio XAML definisce concetti propri, ma questi concetti funzionano all'interno del linguaggio XML e del modulo di markup.

### <a name="xaml-object-elements"></a>Elementi oggetto XAML

In genere, un elemento oggetto dichiara un'istanza di un tipo. Tale tipo è definito negli assembly a cui fa riferimento la tecnologia che utilizza XAML come linguaggio.

La sintassi degli elementi oggetto inizia sempre con una parentesi angolare di apertura (`<`), seguita dal nome del tipo in cui si desidera creare un'istanza. Il nome può includere un prefisso, un concetto che verrà spiegato più avanti. Successivamente, è possibile dichiarare facoltativamente gli attributi nell'elemento oggetto. Per completare il tag dell'elemento oggetto, terminare con una parentesi angolare di chiusura (`>`). È invece possibile utilizzare un modulo di autochiusura che non ha alcun contenuto, completando`/>`il tag con una barra e una parentesi angolare di chiusura in successione ( ). Ad esempio, esaminare nuovamente il frammento di markup visualizzato in precedenza.

[!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]

Vengono specificati due elementi oggetto: `<StackPanel>` (con contenuto e un tag di chiusura successivo) e `<Button .../>` (forma di chiusura automatica, con diversi attributi). Gli elementi `StackPanel` `Button` oggetto e ogni mapping al nome di una classe definita da WPFWPF e fa parte degli assembly WPFWPF. Quando specifichi un tag dell'elemento oggetto, crei un'istruzione per l'elaborazione XAML per creare una nuova istanza del tipo sottostante. Ogni istanza viene creata chiamando il costruttore senza parametri del tipo sottostante durante l'analisi e il caricamento del codice XAML.

### <a name="attribute-syntax-properties"></a>Sintassi degli attributi (proprietà)

Spesso le proprietà di un oggetto possono essere espresse come attributi dell'elemento oggetto. La sintassi dell'attributo denomina la proprietà dell'oggetto che viene impostata, seguita dall'operatore di assegnazione (Sezione ). Il valore di un attributo viene sempre specificato come stringa inclusa tra virgolette.

La sintassi per attributi è la sintassi per l'impostazione di proprietà più semplice, nonché la più intuitiva per gli sviluppatori che hanno già usato linguaggi di markup in passato. Il markup seguente, ad esempio, crea un pulsante che presenta un testo rosso e uno sfondo blu oltre a un testo visualizzato specificato come `Content`.

[!code-xaml[XAMLOvwSupport#BlueRedButton](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]

### <a name="property-element-syntax"></a>Sintassi per gli elementi proprietà

Per alcune proprietà di un elemento oggetto, non si può usare la sintassi per attributi in quanto non è possibile esprimere l'oggetto o le informazioni necessarie per indicare il valore di proprietà in modo adeguato tra virgolette e nel rispetto delle limitazioni della stringa della sintassi di attributo. In questi casi, è possibile usare una sintassi diversa, nota come sintassi per elementi proprietà.

La sintassi per il `<TypeName.PropertyName>`tag di inizio dell'elemento proprietà è . In genere, il contenuto di tale tag è un elemento oggetto del tipo che la proprietà accetta come valore. Dopo aver specificato il contenuto, è necessario chiudere l'elemento proprietà con un tag di fine. La sintassi per `</TypeName.PropertyName>`il tag di fine è .

Se supportata, la sintassi per attributi è in genere più efficace e consente un markup più compatto. Si tratta tuttavia di una questione di stile e non di un limite tecnico. L'esempio seguente mostra le stesse proprietà impostate nell'esempio di sintassi per attributi precedente, tuttavia questa volta viene usata la sintassi per elementi proprietà per tutte le proprietà dell'oggetto `Button`.

[!code-xaml[XAMLOvwSupport#BlueRedButtonPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]

### <a name="collection-syntax"></a>Sintassi delle raccolte

Il linguaggio XAML include alcune ottimizzazioni che producono un markup più leggibile per l'utente. Una di queste ottimizzazioni prevede che se una proprietà specifica accetta un tipo di raccolta, gli elementi dichiarati nel markup come elementi figlio in quel valore della proprietà diventano di conseguenza parte della raccolta. In questo caso, una raccolta di elementi oggetto figlio corrisponde al valore impostato nella proprietà della raccolta.

Nell'esempio seguente viene illustrata <xref:System.Windows.Media.GradientBrush.GradientStops%2A> la sintassi della raccolta per l'impostazione dei valori della proprietà.

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

Ad esempio, <xref:System.Windows.Controls.Border> specifica una <xref:System.Windows.Controls.Decorator.Child%2A>proprietà di _contenuto_ di . I due <xref:System.Windows.Controls.Border> elementi seguenti sono trattati in modo identico. Il primo sfrutta la sintassi della proprietà di contenuto e omette l'elemento proprietà `Border.Child`. Il secondo specifica `Border.Child` in modo esplicito.

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

Secondo le regole del linguaggio XAML, il valore di una proprietà di contenuto XAML deve essere specificato completamente prima o completamente dopo qualsiasi altro elemento proprietà nell'elemento oggetto. Ad esempio, il markup seguente non viene compilato.

```xaml
<Button>I am a
  <Button.Background>Blue</Button.Background>
  blue button</Button>
```

Per ulteriori informazioni sulle specifiche della sintassi XAML, vedere [Sintassi XAML in dettaglio](../../framework/wpf/advanced/xaml-syntax-in-detail.md).

### <a name="text-content"></a>Contenuto di testo

Un numero ridotto di elementi XAML può elaborare il testo direttamente come contenuto. A tale scopo, deve verificarsi uno dei casi seguenti:

- La classe deve dichiarare una proprietà di contenuto e tale proprietà di contenuto deve <xref:System.Object>essere di un tipo assegnabile a una stringa (il tipo potrebbe essere ). Ad esempio, <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.Controls.ContentControl.Content%2A> qualsiasi utilizzo come proprietà <xref:System.Object>di contenuto ed è di <xref:System.Windows.Controls.ContentControl> tipo e <xref:System.Windows.Controls.Button> `<Button>Hello</Button>`supporta l'utilizzo seguente in un oggetto, ad esempio : .

- Il tipo deve dichiarare un convertitore di tipi e, in tal caso, il contenuto di testo viene usato come testo di inizializzazione per il convertitore di tipi. Ad esempio, `<Brush>Blue</Brush>` converte il `Blue` valore del contenuto di in un pennello. Nella pratica questo caso è meno comune.

- Il tipo deve essere un tipo primitivo noto del linguaggio XAML.

### <a name="content-properties-and-collection-syntax-combined"></a>Proprietà del contenuto e sintassi della raccolta combinati

Si consideri questo esempio.

```xaml
<StackPanel>
  <Button>First Button</Button>
  <Button>Second Button</Button>
</StackPanel>
```

In questo <xref:System.Windows.Controls.Button> caso, ognuno è un elemento figlio di <xref:System.Windows.Controls.StackPanel>. Si tratta di un markup semplice e intuitivo nel quale vengono omessi due tag per due ragioni diverse.

- **Elemento proprietà StackPanel.Children omesso:** <xref:System.Windows.Controls.StackPanel> deriva da <xref:System.Windows.Controls.Panel>. <xref:System.Windows.Controls.Panel>definisce <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> come proprietà di contenuto XAML.

- **Elemento oggetto UIElementCollection omesso:** La <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> proprietà accetta <xref:System.Windows.Controls.UIElementCollection>il <xref:System.Collections.IList>tipo , che implementa . Il tag dell'elemento della raccolta può essere omesso, in <xref:System.Collections.IList>base alle regole XAML per l'elaborazione delle raccolte, ad esempio . (In questo <xref:System.Windows.Controls.UIElementCollection> caso, in realtà non è possibile creare un'istanza perché <xref:System.Windows.Controls.UIElementCollection> non espone un costruttore senza parametri ed è per questo che l'elemento oggetto viene visualizzato commentato).

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

### <a name="attribute-syntax-events"></a>Sintassi degli attributi (eventi)

È possibile usare la sintassi per attributi anche per membri che sono eventi anziché proprietà. In questo caso il nome dell'attributo corrisponde al nome dell'evento. Nell'implementazione WPF di eventi per XAML il valore dell'attributo corrisponde al nome di un gestore che implementa il delegato dell'evento. Ad esempio, il markup seguente assegna <xref:System.Windows.Controls.Primitives.ButtonBase.Click> un <xref:System.Windows.Controls.Button> gestore per l'evento a un oggetto creato nel markup:For example, the following markup assigns a handler for the event to a created in markup:

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

La correlazione tra eventi e XAML in WPF è molto più complessa di questo semplice esempio di sintassi per attributi. Ci si potrebbe chiedere ad esempio, cosa rappresenti `ClickHandler` a cui viene fatto riferimento e come questo venga definito. Questo verrà spiegato nella prossima sezione [Eventi e code-behind XAML](#events-and-xaml-code-behind) di questo articolo.

## <a name="case-and-white-space-in-xaml"></a>Maiuscole/minuscole e spazi vuoti in XAMLCase and white space in XAML

In generale, XAML fa distinzione tra maiuscole e minuscole. Ai fini della risoluzione dei tipi di supporto, XAML WPF fa distinzione tra maiuscole e minuscole in base alle stesse regole in base alle quali CLR fa distinzione tra maiuscole e minuscole. Gli elementi oggetto, gli elementi proprietà e i nomi di attributo devono essere sempre specificati usando correttamente le maiuscole e le minuscole quando si esegue il confronto del nome con il nome del tipo sottostante nell'assembly o con il nome di un membro di un tipo. Anche le parole chiave e le primitive del linguaggio XAML fanno distinzione tra maiuscole e minuscole. Per i valori non viene sempre fatta distinzione tra maiuscole e minuscole. Tale distinzione per i valori dipende dal comportamento del convertitore dei tipi associato alla proprietà che accetta il valore o al tipo di valore della proprietà. Ad esempio, le <xref:System.Boolean> proprietà che `true` accettano il tipo possono accettare uno o `True` come valori <xref:System.Boolean> equivalenti, ma solo perché la conversione del tipo del parser XAML WPF nativo per string consente già questi come equivalenti.

I processori e i serializzatori XAML WPF ignoreranno o interromperanno tutti gli spazi vuoti non significativi e normalizzeranno qualsiasi spazio vuoto significativo. Ciò è coerente con le raccomandazioni di comportamento degli spazi vuoti predefinite della specifica XAML. Questo comportamento è solo di conseguenza quando si specificano stringhe all'interno di proprietà di contenuto XAML. In termini più semplici, XAML converte spazio, avanzamento riga e caratteri di tabulazione in spazi e quindi mantiene uno spazio se trovato a entrambe le estremità di una stringa contigua. La spiegazione completa della gestione degli spazi vuoti XAML non viene trattata in questo articolo. Per altre informazioni, vedere [Elaborazione di spazi](../xaml-services/white-space-processing.md)vuoti in XAML.

## <a name="markup-extensions"></a>Estensioni di markup

Le estensioni di markup sono un concetto del linguaggio XAML. Se usate per specificare il valore di una sintassi per attributi, le parentesi graffe (`{` e `}`) indicano l'uso di un'estensione di markup. Questo uso indica all'elaborazione XAML che, diversamente dal solito, i valori degli attributi non devono essere considerati valori di stringa letterale o valori convertibili in stringa.

Le estensioni di markup più [`Binding`](../../framework/wpf/advanced/binding-markup-extension.md)comuni usate nella programmazione di [`StaticResource`](../../framework/wpf/advanced/staticresource-markup-extension.md) app [`DynamicResource`](../../framework/wpf/advanced/dynamicresource-markup-extension.md)WPFWPF sono , usate per le espressioni di associazione dati e i riferimenti alle risorse e . Le estensioni di markup consentono di usare la sintassi per attributi per specificare valori per le proprietà anche quando queste non supportano in generale una sintassi per attributi. Le estensioni di markup spesso usano tipi di espressione intermedia per abilitare funzionalità quali il rinvio di valori o il riferimento ad altri oggetti presenti solo in fase di esecuzione.

Ad esempio, il markup seguente <xref:System.Windows.FrameworkElement.Style%2A> imposta il valore della proprietà utilizzando la sintassi degli attributi. La <xref:System.Windows.FrameworkElement.Style%2A> proprietà accetta un'istanza <xref:System.Windows.Style> della classe, di cui per impostazione predefinita non è stato possibile creare un'istanza da una stringa di sintassi dell'attributo. Ma in questo caso, l'attributo `StaticResource`fa riferimento a una particolare estensione di markup, . Quando quell'estensione di markup viene elaborata, restituisce un riferimento a uno stile del quale in precedenza è stata creata un'istanza come risorsa con chiave in un dizionario di risorse.

[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources2)]
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources3](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources3)]

Per un elenco di riferimento di tutte le estensioni di markup per il linguaggio XAML implementato in modo specifico in WPF, vedere [Estensioni XAML WPF](../../framework/wpf/advanced/wpf-xaml-extensions.md). Per un elenco di riferimento delle estensioni di markup definite da System.Xaml e più ampiamente disponibili per le implementazioni XAML di .NET Core, vedere [Spazio dei nomi XAML (x:) Caratteristiche del linguaggio](../xaml-services/namespace-language-features.md). Per altre informazioni sulle estensioni di markup, vedere [Estensioni di markup e WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).

## <a name="type-converters"></a>Convertitori di tipi

La sezione [Cenni sulla sintassi XAML](#xaml-syntax-in-brief) afferma che il valore dell'attributo deve poter essere impostato tramite una stringa. La gestione nativa di base della modalità di conversione delle <xref:System.String> stringhe in altri tipi di oggetto o <xref:System.DateTime> <xref:System.Uri>valori primitivi si basa sul tipo stesso, oltre all'elaborazione nativa per determinati tipi, ad esempio o . Tuttavia, molti tipi WPFWPF o membri di tali tipi estendono il comportamento di elaborazione degli attributi di stringa di base in modo che le istanze di tipi di oggetto più complessi possano essere specificate come stringhe e attributi.

La <xref:System.Windows.Thickness> struttura è un esempio di un tipo con una conversione di tipo abilitata per gli utilizzi XAML. <xref:System.Windows.Thickness>indica le misure all'interno di un rettangolo nidificato e viene utilizzato come valore per proprietà quali <xref:System.Windows.FrameworkElement.Margin%2A>. Inserendo un convertitore <xref:System.Windows.Thickness>di tipi in <xref:System.Windows.Thickness> , tutte le proprietà che utilizzano un oggetto sono più facili da specificare in XAML perché possono essere specificate come attributi. Nell'esempio seguente viene utilizzata una conversione di <xref:System.Windows.FrameworkElement.Margin%2A>tipo e la sintassi degli attributi per fornire un valore per un:

[!code-xaml[XAMLOvwSupport#MarginTCE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]

L'esempio di sintassi degli attributi precedente è equivalente <xref:System.Windows.FrameworkElement.Margin%2A> all'esempio di sintassi <xref:System.Windows.Thickness> più dettagliato seguente, in cui l'oggetto viene invece impostato tramite la sintassi degli elementi proprietà contenente un elemento oggetto. Le quattro proprietà <xref:System.Windows.Thickness> chiave di vengono impostate come attributi nella nuova istanza:The four key properties of are set as attributes on the new instance:

[!code-xaml[XAMLOvwSupport#MarginVerbose](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]

> [!NOTE]
> Esistono anche un numero limitato di oggetti in cui la conversione del tipo è l'unico modo pubblico per impostare una proprietà su tale tipo senza coinvolgere una sottoclasse, perché il tipo stesso non dispone di un costruttore senza parametri. Un esempio è <xref:System.Windows.Input.Cursor>.

Per ulteriori informazioni sulla conversione dei tipi, vedere [TypeConverters e XAML.](../../framework/wpf/advanced/typeconverters-and-xaml.md)

## <a name="xaml-root-elements-and-xaml-namespaces"></a>Elementi radice XAML e spazi dei nomi XAMLXAML root elements and XAML namespaces

Un file XAML deve avere un solo elemento radice, per essere sia un file XML ben formato che un file XAML valido. Per gli scenari WPF tipici, si usa un elemento radice con <xref:System.Windows.Window> un <xref:System.Windows.Controls.Page> significato prominente nel modello di app WPF (ad esempio, o per una pagina, <xref:System.Windows.ResourceDictionary> per un dizionario esterno o <xref:System.Windows.Application> per la definizione dell'app). Nell'esempio seguente viene illustrato l'elemento radice di un tipico <xref:System.Windows.Controls.Page>file XAML per una pagina WPF, con l'elemento radice di .

[!code-xaml[XAMLOvwSupport#RootOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]
[!code-xaml[XAMLOvwSupport#RootOnly2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]

L'elemento radice inoltre contiene gli attributi `xmlns` e `xmlns:x`, che indicano a un processore XAML gli spazi dei nomi XAML contenenti le definizioni dei tipi per i tipi di supporto a cui il markup farà riferimento come elementi. L'attributo `xmlns` indica in modo specifico lo spazio dei nomi XAML predefinito. All'interno dello spazio dei nomi XAML predefinito gli elementi oggetto nel markup possono essere specificati senza prefisso. Per la maggior parte degli scenari di app WPFWPF e per quasi tutti gli esempi forniti `http://schemas.microsoft.com/winfx/2006/xaml/presentation`nelle sezioni WPF dell'SDK, lo spazio dei nomi XAML predefinito viene mappato allo spazio dei nomi WPF. L'attributo `xmlns:x` indica uno spazio dei nomi XAML aggiuntivo, che viene mappato allo spazio dei nomi del linguaggio XAML `http://schemas.microsoft.com/winfx/2006/xaml`.

Tale uso di `xmlns` per definire un ambito per l'uso e il mapping di un NameScope è coerente con la specifica XML 1.0. I NameScope XAML sono diversi dai NameScope XML solo in quanto nei primi vengono indicati anche alcuni aspetti correlati al supporto degli elementi del NameScope da parte dei tipi riguardo a risoluzione dei tipi e analisi di XAML.

Gli `xmlns` attributi sono strettamente necessari solo nell'elemento radice di ogni file XAML. Le definizioni `xmlns` si applicheranno a tutti gli elementi discendenti dell'elemento radice, un comportamento coerente con la specifica XML 1.0 per `xmlns`. Gli attributi `xmlns` sono inoltre consentiti in altri elementi sottostanti la radice e si applicherebbero a qualsiasi elemento discendente dell'elemento di definizione. Tuttavia, la definizione o ridefinizione frequente degli spazi dei nomi XAML può risultare in uno stile di markup XAML di difficile lettura.

L'implementazione WPFWPF del processore XAML include un'infrastruttura con conoscenza degli assembly di base WPFWPF. Gli assembly di base WPFWPF sono noti per contenere i tipi che supportano i mapping WPFWPF allo spazio dei nomi XAML predefinito. Ciò è consentito tramite la configurazione inclusa nel file di compilazione del progetto e nei sistemi di compilazione e del progetto WPF. Pertanto, la dichiarazione dello `xmlns` spazio dei nomi XAML predefinito come valore predefinito è tutto ciò che è necessario per fare riferimento a elementi XAML che provengono da assembly WPFWPF.

### <a name="the-x-prefix"></a>Il prefisso x:

L'esempio di elemento radice precedente usa il prefisso `x:` per eseguire il mapping dello spazio dei nomi XAML `http://schemas.microsoft.com/winfx/2006/xaml`, che è lo spazio dei nomi XAML dedicato che supporta costrutti di linguaggio XAML. Questo `x:` prefisso viene usato per il mapping di questo spazio dei nomi XAML nei modelli per i progetti, negli esempi e nella documentazione in tutto questo SDK. Lo spazio dei nomi XAML per il linguaggio XAML contiene diversi costrutti di programmazione che verranno utilizzati di frequente nel codice XAML. Di seguito viene presentato un elenco dei più comuni costrutti di programmazione del prefisso `x:` che verranno usati:

- [x:Key](../xaml-services/xkey-directive.md): Imposta una chiave univoca per ogni risorsa in un <xref:System.Windows.ResourceDictionary> (o concetti di dizionario simili in altri framework). `x:Key`probabilmente rappresenterà il 90% degli `x:` utilizzi che verrà visualizzato nel markup di una tipica app WPF.

- [x:Class](../xaml-services/xclass-directive.md): Specifica lo spazio dei nomi CLR e il nome della classe per la classe che fornisce code-behind per una pagina XAML. È necessario che tale classe supporti il code-behind per ciascun modello di programmazione WPF ed è per questa ragione che quasi sempre viene eseguito il mapping di `x:`, anche se non sono presenti risorse.

- [x:Name](../xaml-services/xname-directive.md): specifica il nome di un oggetto di runtime per l'istanza presente nel codice della fase di esecuzione dopo l'elaborazione di un elemento oggetto. In generale, si usa spesso una proprietà equivalente definita in WPF per [x:Name](../xaml-services/xname-directive.md). Tali proprietà eseguono il mapping in modo specifico a una proprietà di backup CLR e sono quindi più convenienti per la programmazione dell'app, in cui si usa spesso codice di runtime per trovare gli elementi denominati dal codice XAML inizializzato. La proprietà più <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>comune di questo tipo è . È comunque possibile usare [x:Name](../xaml-services/xname-directive.md) quando <xref:System.Windows.FrameworkElement.Name%2A> la proprietà a livello di framework WPF equivalente non è supportata in un determinato tipo. Tale situazione si verifica in determinati scenari di animazione.

- [x:Static](../xaml-services/xstatic-markup-extension.md): abilita il riferimento che restituisce un valore statico che non costituisce in altro modo una proprietà compatibile con XAML.

- [x:Type](../xaml-services/xtype-markup-extension.md): costruisce <xref:System.Type> un riferimento in base a un nome di tipo.x:Type : Constructs a reference based on a type name. Viene utilizzato per specificare <xref:System.Type>gli <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>attributi che accettano , ad<xref:System.Type> esempio , anche se spesso la proprietà dispone di una conversione nativa da stringa a stringa in modo che l'utilizzo dell'estensione di markup [x:Type](../xaml-services/xtype-markup-extension.md) sia facoltativo.

Nel prefisso `x:` o nello spazio dei nomi XAML sono presenti altri costrutti di programmazione non altrettanto comuni. Per informazioni dettagliate, vedere [Funzionalità del linguaggio dello spazio dei nomi XAML (x:)](../xaml-services/namespace-language-features.md).

## <a name="custom-prefixes-and-custom-types-in-xaml"></a>Custom prefixes and custom types in XAML

Per assembly personalizzati o per assembly esterni al core WPF di **PresentationCore**, **PresentationFramework** e **WindowsBase**, è possibile specificare l'assembly come parte di un mapping personalizzato. `xmlns` È quindi possibile fare riferimento ai tipi dell'assembly in XAML, purché tale tipo sia stato implementato correttamente per supportare gli usi di XAML desiderati.

Di seguito è riportato un esempio di base del funzionamento dei prefissi personalizzati nel markup XAML. Il `custom` prefisso viene definito nel tag dell'elemento radice e mappato a un assembly specifico incluso nel pacchetto e disponibile con l'app. Questo assembly contiene un tipo `NumericUpDown`, implementato per supportare l'uso generale di XAML, nonché l'uso di un'ereditarietà delle classi che ne consenta l'inserimento in questo punto specifico in un modello di contenuto XAML WPF. Un'istanza di questo controllo `NumericUpDown` viene dichiarata come elemento oggetto, usando il prefisso in modo tale che un parser XAML sia in grado di riconoscere lo spazio dei nomi XAML contenente il tipo e pertanto la posizione dell'assembly di supporto che contiene la definizione del tipo.

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

Per altre informazioni su come gli spazi dei nomi XML e gli spazi dei nomi del codice negli assembly sono correlati, vedere [Spazi dei nomi XAML e Mapping degli spazi dei nomi per XAML WPF.](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)

## <a name="events-and-xaml-code-behind"></a>Eventi e code-behind XAML

La maggior parte delle app WPFWPF è costituita sia dal markup XAML che dal code-behind. All'interno di un progetto, `.xaml` il codice XAML viene scritto come file e viene usato un linguaggio CLR, ad esempio Microsoft Visual Basic o C, per scrivere un file code-behind. Durante la compilazione dal markup di un file XAML come parte dei modelli di applicazione e di programmazione WPF, il percorso del file code-behind XAML per un file XAML viene identificato specificando uno spazio dei nomi e una classe come attributo `x:Class` dell'elemento radice della pagina XAML.

Gli esempi riportati fino a questo momento illustrano molti pulsanti, nessuno dei quali era associato a un comportamento logico. Il meccanismo principale a livello di applicazione per l'aggiunta di un comportamento per un elemento oggetto consiste nell'utilizzare un evento esistente della classe dell'elemento e nello scrivere un gestore specifico per tale evento che viene richiamato quando tale evento viene generato in fase di esecuzione. Il nome dell'evento e il nome del gestore da usare sono specificati nel markup, mentre il codice che implementa il gestore è definito nel code-behind.

[!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]

[!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
[!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]

Si noti che il file code-behind usa lo spazio dei nomi CLR `ExampleNamespace` e dichiara `ExamplePage` come classe parziale all'interno di tale spazio dei nomi. Questo è parallelo al valore dell'attributo `x:Class` di `ExampleNamespace``ExamplePage` offerto nella radice del markup. Il compilatore del markup WPF creerà una classe parziale per ogni file XAML compilato derivando una classe dal tipo di elemento radice. Quando fornisci code-behind che definisce anche la stessa classe parziale, il codice risultante viene combinato all'interno dello stesso spazio dei nomi e della stessa classe dell'app compilata.

Per altre informazioni sui requisiti per la programmazione code-behind in WPFWPF, vedere [Code-behind, gestore eventi e requisiti di classi parziali in WPF.](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md#code-behind-event-handler-and-partial-class-requirements-in-wpf)

Se non si desidera creare un file code-behind distinto, è anche possibile incorporare il codice in un file XAML. Tuttavia, il codice inline è una tecnica meno versatile che presenta limitazioni sostanziali. Per altre informazioni, vedere [Code-behind e XAML in WPF.](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)

### <a name="routed-events"></a>Eventi indirizzati

Una particolare funzionalità di evento che è fondamentale per WPFWPF è un evento indirizzato. Gli eventi indirizzati consentono a un elemento di gestire un evento generato da un elemento diverso, purché gli elementi siano connessi tramite una relazione di struttura ad albero. Quando si specifica la gestione dell'evento con un attributo XAML, l'evento indirizzato può essere ascoltato e gestito in qualsiasi elemento, inclusi quelli che non elencano l'evento specifico nella tabella dei membri della classe. Ciò è possibile qualificando l'attributo del nome evento con il nome della classe di appartenenza. Ad esempio, `StackPanel` l'elemento `StackPanel`  /  `Button` padre nell'esempio in corso potrebbe <xref:System.Windows.Controls.Primitives.ButtonBase.Click> registrare un `Button.Click` gestore `StackPanel` per l'evento del pulsante dell'elemento figlio specificando l'attributo sull'elemento oggetto, con il nome del gestore come valore dell'attributo. Per ulteriori informazioni, vedere [Cenni preliminari sugli eventi indirizzati](../../framework/wpf/advanced/routed-events-overview.md).

## <a name="xaml-named-elements"></a>Elementi denominati XAML

Per impostazione predefinita, l'istanza di oggetto creata in un oggetto grafico tramite l'elaborazione di un elemento oggetto XAML non possiede un identificatore univoco o un riferimento a un oggetto. Al contrario, se si chiama un costruttore nel codice, quasi sempre il risultato del costruttore viene usato per impostare una variabile sull'istanza creata, in modo che sia possibile fare riferimento all'istanza nel codice in un secondo momento. Per offrire accesso standard agli oggetti creati tramite una definizione del markup, in XAML viene definito l'[attributo x:Name](../xaml-services/xname-directive.md). È possibile impostare il valore dell'attributo `x:Name` in qualsiasi elemento oggetto. All'interno del code-behind l'identificatore scelto è equivalente a una variabile dell'istanza che fa riferimento all'istanza costruita. Sotto tutti gli aspetti, gli elementi denominati funzionano come se fossero istanze di oggetto (il nome fa riferimento a tale istanza) e il code-behind può fare riferimento agli elementi denominati per gestire le interazioni in fase di esecuzione all'interno dell'app. Questa connessione tra istanze e variabili viene eseguita dal compilatore di <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> markup XAML WPF e coinvolge in modo più specifico funzionalità e modelli come quello che non verrà illustrato in dettaglio in questo articolo.

Gli elementi XAML a <xref:System.Windows.FrameworkElement.Name%2A> livello di framework WPF ereditano una proprietà, che equivale all'attributo definito `x:Name` XAML. Altre classi offrono equivalenti a livello di proprietà per `x:Name`, che in genere viene definito anche come proprietà `Name`. In generale se non è possibile individuare una proprietà `Name` nella tabella dei membri dell'elemento o del tipo scelto, usare `x:Name` in alternativa. I `x:Name` valori forniranno un identificatore a un elemento XAML che può essere utilizzato in <xref:System.Windows.FrameworkElement.FindName%2A>fase di esecuzione, da sottosistemi specifici o da metodi di utilità come .

Nell'esempio <xref:System.Windows.FrameworkElement.Name%2A> seguente <xref:System.Windows.Controls.StackPanel> viene impostato su un elemento. Quindi, un gestore su un <xref:System.Windows.Controls.Button> interno che <xref:System.Windows.Controls.StackPanel> fa riferimento al t- relativo riferimento <xref:System.Windows.Controls.StackPanel> `buttonContainer` all'istanza come impostato da <xref:System.Windows.FrameworkElement.Name%2A>.

[!code-xaml[XAMLOvwSupport#NamedE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]
[!code-xaml[XAMLOvwSupport#NamedE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]

[!code-csharp[XAMLOvwSupport#NameCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
[!code-vb[XAMLOvwSupport#NameCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]

Come accade per una variabile, il nome XAML di un'istanza è governato da un concetto di ambito, per cui è possibile attivare nomi che siano univoci all'interno di un determinato ambito prevedibile. Il markup primario che definisce una pagina denota un NameScope XAML univoco, il cui limite è costituito dall'elemento radice della pagina. Tuttavia, altre origini di markup possono interagire con una pagina in fase di esecuzione, ad esempio stili o modelli all'interno di stili, e tali origini di markup hanno spesso i propri ambiti dei nomi XAML che non si connettono necessariamente con l'ambito dei nomi XAML della pagina. Per ulteriori `x:Name` informazioni sugli ambiti dei <xref:System.Windows.FrameworkElement.Name%2A>nomi XAML, vedere , [x:Name Directive](../xaml-services/xname-directive.md)o [WPF XAML Namescopes](../../framework/wpf/advanced/wpf-xaml-namescopes.md).

## <a name="attached-properties-and-attached-events"></a>Proprietà associate ed eventi associati

XAML specifica una funzionalità del linguaggio che consente di definire determinati eventi o proprietà in qualsiasi elemento, indipendentemente dalla presenza della proprietà o dell'evento all'interno delle definizioni del tipo per l'elemento per cui è impostato l'evento o la proprietà. La versione delle proprietà di questa funzionalità è denominata proprietà associata, la versione degli eventi è denominata evento associato. Concettualmente, è possibile pensare alle proprietà associate e agli eventi associati come a membri globali che possono essere impostati in qualsiasi elemento o istanza di oggetto XAML. Tuttavia, tale elemento, classe o infrastruttura più ampia dovrà supportare un archivio delle proprietà di supporto per i valori associati.

Le proprietà associate in XAML vengono in genere usate tramite la sintassi per attributi. Nella sintassi degli attributi, specificare `ownerType.propertyName`una proprietà associata nel formato .

Superficialmente, è simile all'utilizzo di un `ownerType` elemento proprietà, ma in questo caso l'impostazione specificata è sempre un tipo diverso rispetto all'elemento oggetto in cui viene impostata la proprietà associata. `ownerType`è il tipo che fornisce i metodi della funzione di accesso richiesti da un processore XAML per ottenere o impostare il valore della proprietà associata.

Lo scenario più comune per le proprietà associate consiste nel consentire agli elementi figlio di segnalare un valore di proprietà al relativo elemento padre.

Nell'esempio seguente <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> viene illustrata la proprietà associata. La <xref:System.Windows.Controls.DockPanel> classe definisce le <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> funzioni di accesso per e pertanto possiede la proprietà associata. La <xref:System.Windows.Controls.DockPanel> classe include anche la logica che scorre i relativi elementi <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>figlio e controlla in modo specifico ogni elemento per un set value di . Se individuato, quel valore viene usato durante il layout per posizionare gli elementi figlio. L'uso <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> della proprietà associata e di questa funzionalità di posizionamento è infatti lo scenario motivante per la <xref:System.Windows.Controls.DockPanel> classe.

[!code-xaml[XAMLOvwSupport#DockAP](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]

In WPFWPF, la maggior parte o tutte le proprietà associate vengono implementate anche come proprietà di dipendenza. Per altre informazioni, vedere [Cenni preliminari sulle proprietà associate](../../framework/wpf/advanced/attached-properties-overview.md).

Gli eventi associati `ownerType.eventName` utilizzano una forma simile di sintassi degli attributi. Come per gli eventi non associati, il valore dell'attributo per un evento associato in XAML specifica il nome del metodo di gestione richiamato quando l'evento viene gestito nell'elemento. Gli usi di eventi associati in XAML WPF sono meno comuni. Per altre informazioni, vedere [Cenni preliminari sugli eventi associati](../../framework/wpf/advanced/attached-events-overview.md).

## <a name="base-types-and-xaml"></a>Tipi di base e XAML

XAML WPF sottostante e il relativo spazio dei nomi XAML è una raccolta di tipi che corrispondono agli oggetti CLR oltre agli elementi di markup per XAML. Tuttavia non è possibile eseguire il mapping di tutte le classi agli elementi. Le classi astratte, ad <xref:System.Windows.Controls.Primitives.ButtonBase>esempio , e alcune classi base non astratte, vengono utilizzate per l'ereditarietà nel modello di oggetti CLR. Le classi di base, incluse quelle astratte, continuano a essere importanti per lo sviluppo di XAML, in quanto ciascuno degli elementi XAML concreti eredita i membri da una classe di base nella relativa gerarchia. Spesso tali membri includono proprietà che possono essere impostate come attributi nell'elemento oppure eventi che possono essere gestiti. <xref:System.Windows.FrameworkElement>è la classe dell'interfaccia utente di base concreta di WPFWPF a livello di framework WPF. Quando si progetta l'interfaccia utente, si utilizzeranno varie classi di <xref:System.Windows.FrameworkElement>forme, pannelli, elementi Decorator o controlli, che derivano tutte da . Una classe base <xref:System.Windows.FrameworkContentElement>correlata, , supporta elementi orientati al documento che funzionano bene per una presentazione <xref:System.Windows.FrameworkElement>del layout di flusso, utilizzando API che rispecchiano deliberatamente le API in . La combinazione di attributi a livello di elemento e un modello a oggetti CLR fornisce un set di proprietà comuni che sono impostabili nella maggior parte degli elementi XAML concreti, indipendentemente dall'elemento XAML specifico e dal relativo tipo sottostante.

## <a name="xaml-security"></a>Sicurezza XAML

XAML è un linguaggio di markup che rappresenta direttamente la creazione di istanze di oggetti e la relativa esecuzione. Gli elementi creati in XAML, pertanto, hanno la stessa capacità di interagire con risorse di sistema (quali accesso di rete e IO file system) del codice generato equivalente. XAML caricato in un'app completamente attendibile ha lo stesso accesso alle risorse di sistema dell'app di hosting.

### <a name="code-access-security-cas-in-wpf"></a>Sicurezza dall'accesso di codice in WPFCode Access Security (CAS) in WPF

**Questa sezione si applica solo a .NET Framework. WPF per .NET Core non supporta CAS. Per ulteriori informazioni, vedere Differenze relative alla [sicurezza dall'accesso](../migration/differences-from-net-framework.md#code-access-security)di codice .**

WPF per .NET Framework supporta la sicurezza dall'accesso di codice. Ciò significa che il contenuto WPFWPF in esecuzione nell'area Internet dispone di autorizzazioni di esecuzione ridotte. "Loose XAML" (pagine di XAML non compilato interpretate in fase di caricamento da un visualizzatore XAML) e XBAP vengono in genere eseguite in questa area Internet e usano lo stesso set di autorizzazioni. Il codice XAML caricato in un'applicazione completamente attendibile, tuttavia, dispone dello stesso accesso alle risorse di sistema dell'applicazione host. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../../framework/wpf/wpf-partial-trust-security.md).

## <a name="loading-xaml-from-code"></a>Caricamento di XAML dal codiceLoading XAML from code

Sebbene sia possibile usare XAML per definire un'interfaccia utente completa, è talvolta opportuno definire solo una parte dell'interfaccia utente tramite XAML. Questa funzionalità può risultare utile per consentire una personalizzazione parziale, l'archiviazione locale di informazioni, l'uso di XAML per offrire un oggetto business o per molti altri scenari possibili. La chiave di questi <xref:System.Windows.Markup.XamlReader> scenari <xref:System.Windows.Markup.XamlReader.Load%2A> è la classe e il relativo metodo. L'input è un file XAML, mentre l'output è un oggetto che rappresenta l'intera struttura ad albero di oggetti di runtime creata dal markup. È quindi possibile inserire l'oggetto come proprietà di un altro oggetto già esistente nell'app. Finché la proprietà è una proprietà appropriata nel modello di contenuto con funzionalità di visualizzazione eventualmente e che notifica al motore di esecuzione che il nuovo contenuto è stato aggiunto all'app, è possibile modificare facilmente il contenuto di un'app in esecuzione caricandoin XAML. Per .NET Framework, questa funzionalità è in genere disponibile solo nelle applicazioni con attendibilità totale, a causa delle ovvie implicazioni di sicurezza del caricamento di file nelle applicazioni durante l'esecuzione.

## <a name="see-also"></a>Vedere anche

- [Descrizione dettagliata della sintassi XAML](../../framework/wpf/advanced/xaml-syntax-in-detail.md)
- [Classi XAML e personalizzate per WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [Spazio dei nomi XAML (x:) Funzionalità del linguaggio](../xaml-services/namespace-language-features.md)
- [Estensioni XAML WPF](../../framework/wpf/advanced/wpf-xaml-extensions.md)
- [Cenni preliminari sugli elementi di base](../../framework/wpf/advanced/base-elements-overview.md)
- [Strutture ad albero in WPF](../../framework/wpf/advanced/trees-in-wpf.md)
