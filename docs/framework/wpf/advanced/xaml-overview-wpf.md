---
title: Cenni preliminari su XAML (WPF)
ms.date: 03/30/2017
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
ms.assetid: a80db4cd-dd0f-479f-a45f-3740017c22e4
ms.openlocfilehash: 7aa695ae3402c4a834e5f83c40f341c5448ab524
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364125"
---
# <a name="xaml-overview-wpf"></a>Cenni preliminari su XAML (WPF)
Questo argomento descrive le funzionalità del linguaggio XAML e ne illustra l'uso per la scrittura di applicazioni [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. In particolare descrive il linguaggio XAML implementato in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Il linguaggio XAML in quanto tale, tuttavia, rappresenta un concetto di linguaggio più ampio rispetto a quello implementato in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  

<a name="what_is_xaml"></a>   
## <a name="what-is-xaml"></a>Definizione di XAML  
 XAML è un linguaggio di markup dichiarativo. Come applicato al modello di programmazione .NET Framework, XAML semplifica la creazione di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] un per un'applicazione .NET Framework. È possibile creare elementi di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] visibili nel markup XAML dichiarativo, quindi separare la definizione di [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] dalla logica di runtime usando file code-behind, uniti al markup tramite definizioni di classe parziali. XAML rappresenta in modo diretto la creazione di istanze di oggetti in un set specifico di tipi di supporto definiti in assembly. In ciò si differenzia dalla maggior parte degli altri linguaggi di markup, che sono in genere linguaggi interpretati senza un legame diretto con il sistema di tipi di supporto. XAML consente un flusso di lavoro in cui parti distinte possono operare nella [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] e nella logica di un'applicazione, usando strumenti potenzialmente diversi.  
  
 Se rappresentati come testo, i file XAML sono file XML, in genere con estensione `.xaml`. I file possono essere codificati tramite qualsiasi codifica XML, tuttavia la codifica tipica è UTF-8.  
  
 L'esempio seguente illustra come creare un pulsante come parte di una [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. L'esempio non deve essere ritenuto esaustivo e ha il semplice scopo di dare un'idea molto generale del modo in cui XAML rappresenta metafore di programmazione della [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] comuni.  
  
 [!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]  
  
<a name="xaml_syntax_in_brief"></a>   
## <a name="xaml-syntax-in-brief"></a>Sintassi XAML in breve  
 Le sezioni seguenti descrivono le forme di base della sintassi XAML e offrono un breve esempio di markup. L'obiettivo di queste sezioni non consiste nell'offrire informazioni complete su ogni forma di sintassi, ad esempio sulla modalità di rappresentazione di queste sintassi nel sistema di tipi di supporto. Per altre informazioni sulle specifiche della sintassi XAML per ognuna delle forme di sintassi introdotte in questo argomento, vedere [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md).  
  
 Se si ha familiarità con il linguaggio XML, la maggior parte del materiale incluso in alcune delle sezioni successive risulterà di facile comprensione. Ciò è dovuto a uno dei principi di base della progettazione XAML.  Il linguaggio XAML definisce i concetti propri, ma questi concetti funzionano all'interno del linguaggio XML e del formato di markup.  
  
### <a name="xaml-object-elements"></a>Elementi oggetto XAML  
 In genere, un elemento oggetto dichiara un'istanza di un tipo. Il tipo è definito negli assembly che rendono disponibili i tipi di supporto per una tecnologia che usa XAML come linguaggio.  
  
 La sintassi degli elementi oggetto inizia sempre con una parentesi angolare di apertura (\<), seguita dal nome del tipo in cui si desidera creare un'istanza. Il nome può includere un prefisso. Questo concetto verrà illustrato in seguito. Se lo si desidera, è quindi possibile dichiarare attributi nell'elemento oggetto. Per completare il tag dell'elemento oggetto, terminare con una parentesi angolare di chiusura (>). In alternativa, è possibile usare una forma di chiusura automatica senza contenuto, completando il tag con una barra e una parentesi angolare di chiusura in successione (/>). Osservare nuovamente il frammento di markup illustrato in precedenza:  
  
 [!code-xaml[XAMLOvwSupport#DirtSimple](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#dirtsimple)]  
  
 Vengono specificati due elementi oggetto: `<StackPanel>` (con contenuto e un tag di chiusura successivo) e `<Button .../>` (forma di chiusura automatica, con diversi attributi). Gli elementi oggetto `StackPanel` e `Button` vengono mappati ciascuno al nome di una classe definita da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e che fa parte degli assembly [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Quando si specifica il tag di un elemento oggetto, si crea un'istruzione per la creazione di una nuova istanza da parte dell'elaborazione XAML. Ogni istanza viene creata chiamando il costruttore senza parametri del tipo sottostante durante l'analisi e il caricamento del codice XAML.  
  
### <a name="attribute-syntax-properties"></a>Sintassi degli attributi (proprietà)  
 Spesso le proprietà di un oggetto possono essere espresse come attributi dell'elemento oggetto. Una sintassi per attributi definisce un nome per la proprietà impostata nella sintassi, seguito dall'operatore di assegnazione (=). Il valore di un attributo viene sempre specificato come stringa inclusa tra virgolette.  
  
 La sintassi per attributi è la sintassi per l'impostazione di proprietà più semplice, nonché la più intuitiva per gli sviluppatori che hanno già usato linguaggi di markup in passato. Il markup seguente, ad esempio, crea un pulsante che presenta un testo rosso e uno sfondo blu oltre a un testo visualizzato specificato come `Content`.  
  
 [!code-xaml[XAMLOvwSupport#BlueRedButton](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbutton)]  
  
### <a name="property-element-syntax"></a>Sintassi degli elementi proprietà  
 Per alcune proprietà di un elemento oggetto, non si può usare la sintassi per attributi in quanto non è possibile esprimere l'oggetto o le informazioni necessarie per indicare il valore di proprietà in modo adeguato tra virgolette e nel rispetto delle limitazioni della stringa della sintassi di attributo. In questi casi, è possibile usare una sintassi diversa, nota come sintassi per elementi proprietà.  
  
 La sintassi per il tag di inizio dell'elemento proprietà è `<`*nomeTipo*`.`*nomeProprietà*`>`. In genere, il contenuto di tale tag è un elemento oggetto del tipo che la proprietà accetta come valore. Dopo aver specificato il contenuto, è necessario chiudere l'elemento Property con un tag di fine. La sintassi per il tag di fine è `</`*nomeTipo*`.`*nomeProprietà*`>`.  
  
 Se supportata, la sintassi per attributi è in genere più efficace e consente un markup più compatto. Si tratta tuttavia di una questione di stile e non di un limite tecnico. L'esempio seguente mostra le stesse proprietà impostate nell'esempio di sintassi per attributi precedente, tuttavia questa volta viene usata la sintassi per elementi proprietà per tutte le proprietà dell'oggetto `Button`.  
  
 [!code-xaml[XAMLOvwSupport#BlueRedButtonPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#blueredbuttonpe)]  
  
### <a name="collection-syntax"></a>Sintassi della raccolta  
 Il linguaggio XAML include alcune ottimizzazioni che producono un markup più leggibile per l'utente. Una di queste ottimizzazioni prevede che se una proprietà specifica accetta un tipo di raccolta, gli elementi dichiarati nel markup come elementi figlio in quel valore della proprietà diventano di conseguenza parte della raccolta. In questo caso, una raccolta di elementi oggetto figlio corrisponde al valore impostato nella proprietà della raccolta.  
  
 Nell'esempio seguente viene illustrata la sintassi della raccolta per <xref:System.Windows.Media.GradientBrush.GradientStops%2A> l'impostazione dei valori della proprietà:  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <!-- no explicit new GradientStopCollection, parser knows how to find or create -->  
    <GradientStop Offset="0.0" Color="Red" />  
    <GradientStop Offset="1.0" Color="Blue" />  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
### <a name="xaml-content-properties"></a>Proprietà di contenuto XAML  
 XAML specifica una funzionalità del linguaggio tramite cui una classe può designare esattamente una delle relative proprietà come proprietà di contenuto XAML. Per impostare il valore di questa proprietà di contenuto vengono usati gli elementi figlio. In altre parole, solo per la proprietà di contenuto, è possibile omettere un elemento proprietà quando si imposta tale proprietà nel markup XAML ed è possibile produrre una metafora padre/figlio più visibile nel markup.  
  
 Ad esempio, <xref:System.Windows.Controls.Border> specifica una proprietà di contenuto <xref:System.Windows.Controls.Decorator.Child%2A>di. I due <xref:System.Windows.Controls.Border> elementi seguenti vengono trattati in modo identico. Il primo sfrutta la sintassi della proprietà di contenuto e omette l'elemento proprietà `Border.Child`. Il secondo specifica `Border.Child` in modo esplicito.  
  
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
  
 Secondo le regole del linguaggio XAML, il valore di una proprietà di contenuto XAML deve essere specificato completamente prima o completamente dopo qualsiasi altro elemento proprietà nell'elemento oggetto. Ad esempio, il markup seguente non viene compilato:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Per altre informazioni su questa restrizione nelle proprietà di contenuto XAML, vedere la sezione "Proprietà di contenuto XAML" di [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md).  
  
### <a name="text-content"></a>Contenuto di testo  
 Un numero ridotto di elementi XAML può elaborare il testo direttamente come contenuto. A tale scopo, deve verificarsi uno dei casi seguenti:  
  
- La classe deve dichiarare una proprietà di contenuto e tale proprietà di contenuto deve essere di un tipo assegnabile a una stringa (il tipo potrebbe <xref:System.Object>essere). Ad esempio, qualsiasi <xref:System.Windows.Controls.ContentControl> USA <xref:System.Windows.Controls.ContentControl.Content%2A> come proprietà di contenuto ed è di tipo <xref:System.Object>e questo supporta l'utilizzo <xref:System.Windows.Controls.Button>seguente su un oggetto pratico <xref:System.Windows.Controls.ContentControl> , ad esempio: `<Button>Hello</Button>`.  
  
- Il tipo deve dichiarare un convertitore di tipi e, in tal caso, il contenuto di testo viene usato come testo di inizializzazione per il convertitore di tipi. Ad esempio `<Brush>Blue</Brush>`. Nella pratica questo caso è meno comune.  
  
- Il tipo deve essere un tipo primitivo noto del linguaggio XAML.  
  
### <a name="content-properties-and-collection-syntax-combined"></a>Proprietà del contenuto e sintassi della raccolta combinate  
 Si consideri l'esempio seguente:  
  
```xaml  
<StackPanel>  
  <Button>First Button</Button>  
  <Button>Second Button</Button>  
</StackPanel>  
```  
  
 Qui, ognuno <xref:System.Windows.Controls.Button> è un elemento figlio di <xref:System.Windows.Controls.StackPanel>. Si tratta di un markup semplice e intuitivo nel quale vengono omessi due tag per due ragioni diverse.  
  
- **Elemento proprietà StackPanel. Children omesso:** <xref:System.Windows.Controls.StackPanel> deriva da <xref:System.Windows.Controls.Panel>. <xref:System.Windows.Controls.Panel>definisce <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> come proprietà di contenuto XAML.  
  
- **Elemento oggetto UIElementcollection omesso:** La <xref:System.Windows.Controls.Panel.Children%2A?displayProperty=nameWithType> proprietà accetta il tipo <xref:System.Windows.Controls.UIElementCollection>, che implementa <xref:System.Collections.IList>. Il tag dell'elemento della raccolta può essere omesso in base alle regole XAML per l'elaborazione di raccolte <xref:System.Collections.IList>, ad esempio. (In questo caso, <xref:System.Windows.Controls.UIElementCollection> non è possibile creare un'istanza di in quanto non espone un costruttore senza parametri ed è per questo motivo <xref:System.Windows.Controls.UIElementCollection> che l'elemento oggetto viene visualizzato come commento).  
  
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
  
 La correlazione tra eventi e XAML in WPF è molto più complessa di questo semplice esempio di sintassi per attributi. Ci si potrebbe chiedere ad esempio, cosa rappresenti `ClickHandler` a cui viene fatto riferimento e come questo venga definito. La sezione [Eventi e code-behind XAML](xaml-overview-wpf.md#events_and_xaml_codebehind) più avanti in questo argomento illustra questi aspetti.  
  
<a name="case_and_white space_in_xaml"></a>   
## <a name="case-and-white-space-in-xaml"></a>Maiuscole e minuscole e spazi vuoti in XAML  
 In genere XAML fa distinzione tra maiuscole e minuscole. Per la risoluzione di tipi di supporto, XAML WPF fa distinzione tra maiuscole e minuscole in base alle stesse regole applicate da CLR relativamente a tale distinzione. Gli elementi oggetto, gli elementi proprietà e i nomi di attributo devono essere sempre specificati usando correttamente le maiuscole e le minuscole quando si esegue il confronto del nome con il nome del tipo sottostante nell'assembly o con il nome di un membro di un tipo. La distinzione tra maiuscole e minuscole vale anche per le parole chiave e le primitive del linguaggio XAML. Per i valori la distinzione tra maiuscole e minuscole non si applica sempre. Tale distinzione per i valori dipende dal comportamento del convertitore dei tipi associato alla proprietà che accetta il valore o al tipo di valore della proprietà. Ad esempio, le proprietà che accettano <xref:System.Boolean> il tipo possono `true` assumere o `True` come valori equivalenti, ma solo perché la conversione del tipo di parser XAML <xref:System.Boolean> WPF nativo per la stringa consente già tali valori come equivalenti.  
  
 I processori XAML WPF e i serializzatori ignoreranno o elimineranno tutti gli spazi vuoti non significativi e normalizzano gli spazi vuoti significativi. Questo comportamento è coerente con le raccomandazioni predefinite di comportamento dello spazio vuoto della specifica XAML. Questo comportamento è generalmente significativo solo quando si specificano stringhe all'interno di proprietà di contenuto XAML. In termini più semplici, in XAML i caratteri di spazio, avanzamento riga e tabulazione vengono convertiti in spazi e viene conservato solo l'eventuale spazio rilevato a una delle estremità di una stringa contigua. La spiegazione completa della gestione degli spazi vuoti XAML non è illustrata in questo argomento. Per informazioni dettagliate, vedere [elaborazione di spazi vuoti in XAML](../../xaml-services/whitespace-processing-in-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Estensioni di markup  
 Le estensioni di markup sono un concetto del linguaggio XAML. Se usate per specificare il valore di una sintassi per attributi, le parentesi graffe (`{` e `}`) indicano l'uso di un'estensione di markup. Questo uso indica all'elaborazione XAML che, diversamente dal solito, i valori degli attributi non devono essere considerati valori di stringa letterale o valori convertibili in stringa.  
  
 Le estensioni di markup maggiormente usate nella programmazione di applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono [Binding](binding-markup-extension.md), usata per le espressioni di associazione dati e i riferimenti alle risorse [StaticResource](staticresource-markup-extension.md) e [DynamicResource](dynamicresource-markup-extension.md). Le estensioni di markup consentono di usare la sintassi per attributi per specificare valori per le proprietà anche quando queste non supportano in generale una sintassi per attributi. Spesso le estensioni di markup vengono usate con tipi di espressione intermedi per abilitare funzionalità quali il posticipo di valori o il riferimento ad altri oggetti presenti solo in fase di esecuzione.  
  
 Il markup seguente, ad esempio, imposta il valore della <xref:System.Windows.FrameworkElement.Style%2A> proprietà utilizzando la sintassi dell'attributo. La <xref:System.Windows.FrameworkElement.Style%2A> proprietà accetta un'istanza <xref:System.Windows.Style> della classe, che per impostazione predefinita non è stato possibile creare un'istanza da una stringa di sintassi dell'attributo. Tuttavia, in questo caso l'attributo fa riferimento a una particolare estensione di markup, [StaticResource](staticresource-markup-extension.md). Quando quell'estensione di markup viene elaborata, restituisce un riferimento a uno stile del quale in precedenza è stata creata un'istanza come risorsa con chiave in un dizionario di risorse.  
  
 [!code-xaml[FEResourceSH_snip#XAMLOvwShortResources](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources)]  
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources2](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources2)]  
[!code-xaml[FEResourceSH_snip#XAMLOvwShortResources3](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResourceSH_snip/CS/page1.xaml#xamlovwshortresources3)]  
  
 Per un elenco di riferimento di tutte le estensioni di markup per il linguaggio XAML implementato in modo specifico in WPF, vedere [Estensioni XAML WPF](wpf-xaml-extensions.md). Per un elenco di riferimenti delle estensioni di markup definite da System. XAML e sono più diffuse per le implementazioni di .NET Framework XAML, vedere [spazio dei nomi XAML (x:) Funzionalità](../../xaml-services/xaml-namespace-x-language-features.md)del linguaggio. Per altre informazioni sulle estensioni di markup, vedere [Estensioni di markup e WPF XAML](markup-extensions-and-wpf-xaml.md).  
  
<a name="type_converters"></a>   
## <a name="type-converters"></a>Convertitori di tipi  
 La sezione [Cenni sulla sintassi XAML](xaml-overview-wpf.md#xaml_syntax_in_brief) afferma che il valore dell'attributo deve poter essere impostato tramite una stringa. La gestione nativa di base del modo in cui le stringhe vengono convertite in altri tipi di oggetti o valori <xref:System.String> primitivi si basa sul tipo stesso, oltre che sull'elaborazione nativa <xref:System.DateTime> per <xref:System.Uri>determinati tipi, ad esempio o. Molti tipi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] o membri di tali tipi, tuttavia, estendono il comportamento di elaborazione degli attributi stringa di base in modo che le istanze di tipi di oggetto più complessi possano essere specificate come stringhe e attributi.  
  
 La <xref:System.Windows.Thickness> struttura è un esempio di un tipo con una conversione di tipo abilitata per gli utilizzi XAML. <xref:System.Windows.Thickness>indica le misurazioni all'interno di un rettangolo annidato e viene usato come valore <xref:System.Windows.FrameworkElement.Margin%2A>per le proprietà come. Inserendo un convertitore di tipi in <xref:System.Windows.Thickness>, tutte le proprietà che usano <xref:System.Windows.Thickness> un oggetto sono più semplici da specificare in XAML perché possono essere specificate come attributi. Nell'esempio seguente viene utilizzata una conversione di tipo e una sintassi di attributo per fornire <xref:System.Windows.FrameworkElement.Margin%2A>un valore per un oggetto:  
  
 [!code-xaml[XAMLOvwSupport#MarginTCE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#margintce)]  
  
 L'esempio di sintassi dell'attributo precedente è equivalente all'esempio di sintassi più dettagliata seguente, in <xref:System.Windows.FrameworkElement.Margin%2A> cui è invece impostato tramite la sintassi dell'elemento <xref:System.Windows.Thickness> proprietà contenente un elemento oggetto. Le quattro proprietà chiave di <xref:System.Windows.Thickness> vengono impostate come attributi nella nuova istanza:  
  
 [!code-xaml[XAMLOvwSupport#MarginVerbose](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#marginverbose)]  
  
> [!NOTE]
>  Esiste anche un numero limitato di oggetti in cui la conversione del tipo è l'unico modo pubblico per impostare una proprietà su tale tipo senza coinvolgere una sottoclasse, perché il tipo stesso non ha un costruttore senza parametri. Un esempio è <xref:System.Windows.Input.Cursor>.  
  
 Per altre informazioni sul supporto della conversione dei tipi e del relativo uso per la sintassi per attributi, vedere [TypeConverter e XAML](typeconverters-and-xaml.md).  
  
<a name="xaml_root_elements_and_xaml_namespaces"></a>   
## <a name="xaml-root-elements-and-xaml-namespaces"></a>Elementi radice XAML e spazi dei nomi XAML  
 Per essere sia un file [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] ben formato sia un file XAML valido, un file XAML deve includere solo un elemento radice. Per gli scenari WPF tipici, si utilizza un elemento radice che ha un significato importante nel modello di applicazione WPF (ad esempio <xref:System.Windows.Window> , <xref:System.Windows.Controls.Page> o per una pagina <xref:System.Windows.ResourceDictionary> , per un dizionario esterno o <xref:System.Windows.Application> per la definizione dell'applicazione). Nell'esempio seguente viene illustrato l'elemento radice di un tipico file XAML per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] una pagina, con l'elemento radice <xref:System.Windows.Controls.Page>di.  
  
 [!code-xaml[XAMLOvwSupport#RootOnly](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly)]  
[!code-xaml[XAMLOvwSupport#RootOnly2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page2.xaml#rootonly2)]  
  
 L'elemento radice inoltre contiene gli attributi `xmlns` e `xmlns:x`, che indicano a un processore XAML gli spazi dei nomi XAML contenenti le definizioni dei tipi per i tipi di supporto a cui il markup farà riferimento come elementi. L'attributo `xmlns` indica in modo specifico lo spazio dei nomi XAML predefinito. All'interno dello spazio dei nomi XAML predefinito gli elementi oggetto nel markup possono essere specificati senza prefisso. Per la maggior parte degli scenari con applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e per quasi tutti gli esempi offerti nelle sezioni di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nell'[!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)], lo spazio dei nomi XAML predefinito viene mappato allo spazio dei nomi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA#tla_wpfxmlnsv1](../../../../includes/tlasharptla-wpfxmlnsv1-md.md)]. L'attributo `xmlns:x` indica uno spazio dei nomi XAML aggiuntivo, che viene mappato allo spazio dei nomi del linguaggio XAML [!INCLUDE[TLA#tla_xamlxmlnsv1](../../../../includes/tlasharptla-xamlxmlnsv1-md.md)].  
  
 Tale uso di `xmlns` per definire un ambito per l'uso e il mapping di un NameScope è coerente con la specifica XML 1.0. I NameScope XAML sono diversi dai NameScope XML solo in quanto nei primi vengono indicati anche alcuni aspetti correlati al supporto degli elementi del NameScope da parte dei tipi riguardo a risoluzione dei tipi e analisi di XAML.  
  
 Si noti che gli attributi `xmlns` sono strettamente necessari solo per l'elemento radice di ogni file XAML. Le definizioni `xmlns` si applicheranno a tutti gli elementi discendenti dell'elemento radice, un comportamento coerente con la specifica XML 1.0 per `xmlns`. Gli attributi `xmlns` sono inoltre consentiti in altri elementi sottostanti la radice e si applicherebbero a qualsiasi elemento discendente dell'elemento di definizione. Tuttavia, la definizione o ridefinizione frequente degli spazi dei nomi XAML può risultare in uno stile di markup XAML di difficile lettura.  
  
 L'implementazione [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] del relativo processore XAML include un'infrastruttura che rileva gli assembly principali WPF. Gli assembly principali [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contengono notoriamente i tipi che supportano i mapping [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] allo spazio dei nomi XAML predefinito. Ciò è consentito tramite la configurazione inclusa nel file di compilazione del progetto e nei sistemi di compilazione e del progetto WPF. La dichiarazione dello spazio dei nomi XAML predefinito come `xmlns` predefinito è pertanto l'unica operazione necessaria per fare riferimento a elementi XAML provenienti da assembly [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="the-x-prefix"></a>Prefisso x:  
 L'esempio di elemento radice precedente usa il prefisso `x:` per eseguire il mapping dello spazio dei nomi XAML [!INCLUDE[TLA#tla_xamlxmlnsv1](../../../../includes/tlasharptla-xamlxmlnsv1-md.md)] , che è lo spazio dei nomi XAML dedicato che supporta costrutti di linguaggio XAML. Il prefisso `x:` viene usato per il mapping di questo spazio dei nomi XAML nei modelli per i progetti, negli esempi e nella documentazione in tutto l'[!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]. Lo spazio dei nomi XAML per il linguaggio XAML contiene diversi costrutti di programmazione che si utilizzeranno molto spesso nel codice XAML. Di seguito viene presentato un elenco dei più comuni costrutti di programmazione del prefisso `x:` che verranno usati:  
  
- [x:Key](../../xaml-services/x-key-directive.md): Imposta una chiave univoca per ogni risorsa in <xref:System.Windows.ResourceDictionary> un (o concetti del dizionario simili in altri Framework). `x:Key` sarà coinvolto probabilmente nel 90% degli usi di `x:` osservati nel markup di un'applicazione WPF tipica.  
  
- [x:Class](../../xaml-services/x-class-directive.md): Specifica lo [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] spazio dei nomi e il nome della classe per la classe che fornisce il code-behind per una pagina XAML. È necessario che tale classe supporti il code-behind per ciascun modello di programmazione WPF ed è per questa ragione che quasi sempre viene eseguito il mapping di `x:`, anche se non sono presenti risorse.  
  
- [x:Name](../../xaml-services/x-name-directive.md): Specifica un nome di oggetto in fase di esecuzione per l'istanza esistente nel codice di run-time dopo l'elaborazione di un elemento oggetto. In generale, si usa spesso una proprietà equivalente definita in WPF per [x:Name](../../xaml-services/x-name-directive.md). Tali proprietà eseguono specificamente il mapping a una proprietà di supporto CLR e risultano pertanto più utili per la programmazione di applicazioni, in cui spesso viene uso codice della fase di esecuzione per individuare gli elementi denominati dal linguaggio XAML inizializzato. La proprietà più comune è <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>. È comunque possibile utilizzare [x:Name](../../xaml-services/x-name-directive.md) quando la proprietà equivalente a livello <xref:System.Windows.FrameworkElement.Name%2A> di Framework WPF non è supportata in un tipo particolare. Tale situazione si verifica in determinati scenari di animazione.  
  
- [x:static](../../xaml-services/x-static-markup-extension.md): Abilita un riferimento che restituisce un valore statico che non è altrimenti una proprietà compatibile con XAML.  
  
- [x:Type](../../xaml-services/x-type-markup-extension.md): Costruisce un <xref:System.Type> riferimento basato su un nome di tipo. Viene usato per specificare gli attributi che accettano <xref:System.Type>, <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>ad esempio, anche se spesso la proprietà ha una stringa<xref:System.Type> nativa per la conversione in modo tale che l'utilizzo dell'estensione di markup [x:Type](../../xaml-services/x-type-markup-extension.md) sia facoltativo.  
  
 Nel prefisso `x:` o nello spazio dei nomi XAML sono presenti altri costrutti di programmazione non altrettanto comuni. Per informazioni dettagliate, [vedere spazio dei nomi XAML (x:) Funzionalità](../../xaml-services/xaml-namespace-x-language-features.md)del linguaggio.  
  
<a name="custom_prefixes_and_custom_types_in_xaml"></a>   
## <a name="custom-prefixes-and-custom-types-in-xaml"></a>Prefissi personalizzati e tipi personalizzati in XAML  
 Per gli assembly personalizzati o per gli assembly esterni agli elementi principali WPF di PresentationCore, PresentationFramework e WindowsBase, è possibile specificare l'assembly come parte di un mapping `xmlns` personalizzato. È quindi possibile fare riferimento ai tipi dell'assembly in XAML, purché tale tipo sia stato implementato correttamente per supportare gli usi di XAML desiderati.  
  
 Di seguito viene riportato un esempio molto semplice del funzionamento dei prefissi personalizzati nel markup XAML. Il prefisso `custom` è definito nel tag dell'elemento radice e viene mappato a un assembly specifico compresso e disponibile con l'applicazione. Questo assembly contiene un tipo `NumericUpDown`, implementato per supportare l'uso generale di XAML, nonché l'uso di un'ereditarietà delle classi che ne consenta l'inserimento in questo punto specifico in un modello di contenuto XAML WPF. Un'istanza di questo controllo `NumericUpDown` viene dichiarata come elemento oggetto, usando il prefisso in modo tale che un parser XAML sia in grado di riconoscere lo spazio dei nomi XAML contenente il tipo e pertanto la posizione dell'assembly di supporto che contiene la definizione del tipo.  
  
```  
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
  
 Per altre informazioni sui tipi personalizzati in XAML, vedere [XAML e classi personalizzate per WPF](xaml-and-custom-classes-for-wpf.md).  
  
 Per altre informazioni sulla modalità di correlazione tra gli spazi dei nomi XML e gli spazi dei nomi del codice di supporto negli assembly, vedere [Spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="events_and_xaml_codebehind"></a>   
## <a name="events-and-xaml-code-behind"></a>Eventi e code-behind XAML  
 La maggior parte delle applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] include sia markup che code-behind XAML. All'interno di un progetto, XAML viene scritto come `.xaml` file e viene usato [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] un linguaggio quale Microsoft Visual Basic o C# per scrivere un file code-behind. Durante la compilazione dal markup di un file XAML come parte dei modelli di applicazione e di programmazione WPF, il percorso del file code-behind XAML per un file XAML viene identificato specificando uno spazio dei nomi e una classe come attributo `x:Class` dell'elemento radice della pagina XAML.  
  
 Gli esempi riportati fino a questo momento illustrano molti pulsanti, nessuno dei quali era associato a un comportamento logico. Il meccanismo primario a livello di applicazione per l'aggiunta di un comportamento per un elemento oggetto consiste nell'uso di un evento esistente della classe dell'elemento e nella scrittura di un gestore specifico per quell'evento che viene richiamato nel momento in cui l'evento viene generato in fase di esecuzione. Il nome dell'evento e il nome del gestore da usare sono specificati nel markup, mentre il codice che implementa il gestore è definito nel code-behind.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml#buttonwithcodebehind)]  
  
 [!code-csharp[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page3.xaml.cs#buttonwithcodebehindhandler)]
 [!code-vb[XAMLOvwSupport#ButtonWithCodeBehindHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#buttonwithcodebehindhandler)]  
  
 Si noti che il file code-behind usa lo spazio dei nomi CLR `ExampleNamespace` e dichiara `ExamplePage` come classe parziale all'interno di tale spazio dei nomi. Questo è parallelo al valore dell'attributo `x:Class` di `ExampleNamespace``ExamplePage` offerto nella radice del markup. Il compilatore del markup WPF creerà una classe parziale per ogni file XAML compilato derivando una classe dal tipo di elemento radice. Quando si offre code-behind che definisce anche la stessa classe parziale, il codice risultante viene combinato all'interno dello stesso spazio dei nomi e della stessa classe dell'applicazione compilata.  
  
 Per altre informazioni sui requisiti per la programmazione di code-behind in WPF, vedere la sezione di [Code-behind e XAML in WPF](code-behind-and-xaml-in-wpf.md) Code-behind, gestore eventi e requisiti della classe parziale in WPF.  
  
 Se non si desidera creare un file code-behind distinto, è anche possibile incorporare il codice in un file XAML. Tuttavia, il codice inline è una tecnica meno versatile che presenta limitazioni sostanziali. Per informazioni dettagliate, vedere [Code-behind e XAML in WPF](code-behind-and-xaml-in-wpf.md).  
  
### <a name="routed-events"></a>Eventi indirizzati  
 Un evento indirizzato è una particolare funzionalità evento fondamentale per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Gli eventi indirizzati consentono a un elemento di gestire un evento generato da un elemento diverso, purché gli elementi siano connessi tramite una relazione di struttura ad albero. Quando si specifica la gestione dell'evento con un attributo XAML, l'evento indirizzato può essere ascoltato e gestito in qualsiasi elemento, inclusi quelli che non elencano l'evento specifico nella tabella dei membri della classe. Ciò è possibile qualificando l'attributo del nome evento con il nome della classe di appartenenza. Ad esempio, l'elemento `StackPanel` padre nell'  /  `Button` `StackPanel` esempioin`Button.Click` corso `StackPanel` potrebbe registrare un gestore per l' eventodelpulsantedell'elementofigliospecificandol'attributonel<xref:System.Windows.Controls.Primitives.ButtonBase.Click> elemento oggetto, con il nome del gestore come valore dell'attributo. Per altre informazioni sul funzionamento degli eventi indirizzati, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
<a name="x_name_and_xaml_named_elements"></a>   
## <a name="xaml-named-elements"></a>Elementi denominati XAML  
 Per impostazione predefinita, l'istanza di oggetto creata in un oggetto grafico tramite l'elaborazione di un elemento oggetto XAML non possiede un identificatore univoco o un riferimento a un oggetto. Al contrario, se si chiama un costruttore nel codice, quasi sempre il risultato del costruttore viene usato per impostare una variabile sull'istanza creata, in modo che sia possibile fare riferimento all'istanza nel codice in un secondo momento. Per offrire accesso standard agli oggetti creati tramite una definizione del markup, in XAML viene definito l'[attributo x:Name](../../xaml-services/x-name-directive.md). È possibile impostare il valore dell'attributo `x:Name` in qualsiasi elemento oggetto. All'interno del code-behind l'identificatore scelto è equivalente a una variabile dell'istanza che fa riferimento all'istanza costruita. Gli elementi denominati funzionano sotto ogni aspetto come istanze dell'oggetto (il nome fa riferimento a tale istanza) e il code-behind può fare riferimento agli elementi denominati per gestire le interazioni di runtime all'interno dell'applicazione. Questa connessione tra istanze e variabili viene eseguita dal compilatore di markup XAML di WPF e più specificamente implicano funzionalità e modelli, <xref:System.Windows.Markup.IComponentConnector.InitializeComponent%2A> ad esempio, che non verranno illustrati in dettaglio in questo argomento.  
  
 Gli elementi XAML a livello di Framework WPF <xref:System.Windows.FrameworkElement.Name%2A> ereditano una proprietà, equivalente all'attributo definito `x:Name` da XAML. Altre classi offrono equivalenti a livello di proprietà per `x:Name`, che in genere viene definito anche come proprietà `Name`. In generale se non è possibile individuare una proprietà `Name` nella tabella dei membri dell'elemento o del tipo scelto, usare `x:Name` in alternativa. I `x:Name` valori forniranno un identificatore a un elemento XAML che può essere utilizzato in fase di esecuzione, in base a sottosistemi specifici o a metodi di utilità <xref:System.Windows.FrameworkElement.FindName%2A>quali.  
  
 Nell'esempio seguente viene <xref:System.Windows.FrameworkElement.Name%2A> impostato su <xref:System.Windows.Controls.StackPanel> un elemento. Quindi, un gestore su un <xref:System.Windows.Controls.Button> oggetto all' <xref:System.Windows.Controls.StackPanel> interno di che fa riferimento a `buttonContainer` tramite il relativo <xref:System.Windows.FrameworkElement.Name%2A>riferimento all' <xref:System.Windows.Controls.StackPanel> istanza impostato da.  
  
 [!code-xaml[XAMLOvwSupport#NamedE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede)]  
[!code-xaml[XAMLOvwSupport#NamedE2](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml#namede2)]  
  
 [!code-csharp[XAMLOvwSupport#NameCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page7.xaml.cs#namecode)]
 [!code-vb[XAMLOvwSupport#NameCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XAMLOvwSupport/VisualBasic/Page1.xaml.vb#namecode)]  
  
 Come accade per una variabile, il nome XAML di un'istanza è governato da un concetto di ambito, per cui è possibile attivare nomi che siano univoci all'interno di un determinato ambito prevedibile. Il markup primario che definisce una pagina denota un NameScope XAML univoco, il cui limite è costituito dall'elemento radice della pagina. Altre origini di markup, tuttavia, possono interagire con una pagina in fase di esecuzione, ad esempio gli stili o i modelli all'interno degli stili, e tali origini di markup spesso dispongono di NameScope XAML propri non necessariamente connessi al NameScope XAML della pagina. Per ulteriori informazioni sugli `x:Name` ambiti dei nomi XAML e <xref:System.Windows.FrameworkElement.Name%2A>, vedere, [direttiva x:Name](../../xaml-services/x-name-directive.md)o [NameScope XAML WPF](wpf-xaml-namescopes.md).  
  
<a name="attached_properties_and_attached_events"></a>   
## <a name="attached-properties-and-attached-events"></a>Proprietà associate ed eventi associati  
 XAML specifica una funzionalità del linguaggio che consente di definire determinati eventi o proprietà in qualsiasi elemento, indipendentemente dalla presenza della proprietà o dell'evento all'interno delle definizioni del tipo per l'elemento per cui è impostato l'evento o la proprietà. La versione delle proprietà di questa funzionalità è denominata proprietà associata, la versione degli eventi è denominata evento associato. Concettualmente, è possibile pensare alle proprietà associate e agli eventi associati come a membri globali che possono essere impostati in qualsiasi elemento o istanza di oggetto XAML. Tuttavia, tale elemento, classe o infrastruttura più ampia dovrà supportare un archivio delle proprietà di supporto per i valori associati.  
  
 Le proprietà associate in XAML vengono in genere usate tramite la sintassi per attributi. Per specificare una proprietà associata in questa sintassi, è necessario usare il formato *tipoProprietario*.*nomeProprietà*.  
  
 In apparenza, assomiglia all'uso di un elemento proprietà, tuttavia in questo caso *tipoProprietario* che si specifica è sempre un tipo diverso rispetto all'elemento oggetto nel quale è impostata la proprietà associata. *tipoProprietario* è il tipo che offre i metodi della funzione di accesso richiesti da un processore XAML per ottenere o impostare il valore della proprietà associata.  
  
 Lo scenario più comune per le proprietà associate consiste nel consentire agli elementi figlio di segnalare un valore di proprietà al relativo elemento padre.  
  
 Nell'esempio seguente viene illustrata <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> la proprietà associata. La <xref:System.Windows.Controls.DockPanel> classe definisce le funzioni di accesso <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> per e pertanto possiede la proprietà associata. La <xref:System.Windows.Controls.DockPanel> classe include anche la logica che scorre gli elementi figlio e controlla in modo specifico ogni elemento per un <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>valore impostato. Se individuato, quel valore viene usato durante il layout per posizionare gli elementi figlio. L'uso della <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà associata e di questa funzionalità di posizionamento è infatti lo scenario motivante per <xref:System.Windows.Controls.DockPanel> la classe.  
  
 [!code-xaml[XAMLOvwSupport#DockAP](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#dockap)]  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la maggior parte o tutte le proprietà associate sono implementate anche come proprietà di dipendenza. Per informazioni dettagliate, vedere [Cenni preliminari sulle proprietà associate](attached-properties-overview.md).  
  
 Gli eventi associati usano un formato di sintassi per attributi *tipoProprietario*.*nomeEvento* simile. Come per gli eventi non associati, il valore dell'attributo per un evento associato in XAML specifica il nome del metodo di gestione richiamato quando l'evento viene gestito nell'elemento. Gli usi di eventi associati in XAML WPF sono meno comuni. Per altre informazioni, vedere [Cenni preliminari sugli eventi associati](attached-events-overview.md).  
  
<a name="base_classes_and_xaml"></a>   
## <a name="base-types-and-xaml"></a>Tipi di base e XAML  
 Il markup XAML WPF sottostante e il relativo spazio dei nomi XAML sono una raccolta di tipi corrispondenti a oggetti [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)], nonché a elementi di markup da usare in XAML. Tuttavia non è possibile eseguire il mapping di tutte le classi agli elementi. Le classi astratte, <xref:System.Windows.Controls.Primitives.ButtonBase>ad esempio, e alcune classi di base non astratte vengono utilizzate [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] per l'ereditarietà nel modello di oggetti. Le classi di base, incluse quelle astratte, continuano a essere importanti per lo sviluppo di XAML, in quanto ciascuno degli elementi XAML concreti eredita i membri da una classe di base nella relativa gerarchia. Spesso tali membri includono proprietà che possono essere impostate come attributi nell'elemento oppure eventi che possono essere gestiti. <xref:System.Windows.FrameworkElement>è la classe base [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] concreta [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di a livello di Framework WPF. Quando si [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]progetta, si useranno varie classi Shape, Panel, Decorator o Control, che derivano tutte <xref:System.Windows.FrameworkElement>da. Una classe di base correlata, <xref:System.Windows.FrameworkContentElement>, supporta gli elementi orientati ai documenti che funzionano bene per una presentazione del layout del flusso, usando le API che rispecchiano intenzionalmente le API in. <xref:System.Windows.FrameworkElement> La combinazione di attributi a livello di elemento e di un modello a oggetti [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] offre un set di proprietà comuni che è possibile impostare nella maggior parte degli elementi XAML concreti, indipendentemente dall'elemento XAML specifico e dal relativo tipo sottostante.  
  
<a name="xaml_security"></a>   
## <a name="xaml-security"></a>Sicurezza XAML  
 XAML è un linguaggio di markup che rappresenta direttamente la creazione di istanze di oggetti e la relativa esecuzione. Gli elementi creati in XAML, pertanto, hanno la stessa capacità di interagire con risorse di sistema (quali accesso di rete e IO file system) del codice generato equivalente.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]supporta la sicurezza dall'accesso di codice (CAS) di .NET Framework 4 Security Framework. Di conseguenza, il contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in esecuzione nell'area Internet dispone di autorizzazioni di esecuzione ridotte. In questa area Internet vengono in genere eseguiti il codice "XAML separato", ovvero pagine di XAML non compilato interpretato in fase di caricamento da parte di un visualizzatore XAML, e l'[!INCLUDE[TLA#tla_xbap](../../../../includes/tlasharptla-xbap-md.md)], che usano lo stesso set di autorizzazioni.  Il codice XAML caricato in un'applicazione completamente attendibile, tuttavia, dispone dello stesso accesso alle risorse di sistema dell'applicazione host. Per altre informazioni, vedere [Sicurezza con attendibilità parziale in WPF](../wpf-partial-trust-security.md).  
  
<a name="loading_xaml_from_code"></a>   
## <a name="loading-xaml-from-code"></a>Caricamento di XAML dal codice  
 Sebbene sia possibile usare XAML per definire un'interfaccia utente completa, è talvolta opportuno definire solo una parte dell'interfaccia utente tramite XAML. Questa funzionalità può risultare utile per consentire una personalizzazione parziale, l'archiviazione locale di informazioni, l'uso di XAML per offrire un oggetto business o per molti altri scenari possibili. La chiave di questi scenari è la <xref:System.Windows.Markup.XamlReader> classe e il <xref:System.Windows.Markup.XamlReader.Load%2A> relativo metodo. L'input è un file XAML, mentre l'output è un oggetto che rappresenta l'intera struttura ad albero di oggetti di runtime creata dal markup. È possibile quindi inserire l'oggetto in modo che sia una proprietà di un altro oggetto già esistente nell'applicazione. Se la proprietà è una proprietà appropriata nel modello di contenuto che dispone di funzionalità di visualizzazione e che notifica al motore di esecuzione che è stato aggiunto nuovo contenuto nell'applicazione, è possibile modificare in modo piuttosto semplice il contenuto di un'applicazione in esecuzione tramite il caricamento in XAML. Si noti che questa funzionalità in genere è disponibile solo nelle applicazioni con attendibilità completa, a causa delle ovvie implicazioni di sicurezza del caricamento di file all'interno delle applicazioni in esecuzione.  
  
<a name="whats_next"></a>   
## <a name="whats-next"></a>Argomenti successivi  
 Questo argomento offre un'introduzione di base ai concetti e alla terminologia correlati alla sintassi XAML applicata a WPF. Per altre informazioni sui termini usati in questo argomento, vedere [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md).  
  
 Se non è ancora stato fatto, provare gli esercizi nell'argomento [dell'esercitazione Procedura dettagliata: Prima applicazione](../getting-started/walkthrough-my-first-wpf-desktop-application.md)desktop WPF. Durante la creazione dell'applicazione basata sul markup descritta nell'esercitazione, l'esercizio consentirà di approfondire molti dei concetti trattati in questo argomento.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Usa un particolare modello di applicazione basato sulla <xref:System.Windows.Application> classe. Per informazioni dettagliate, vedere [Cenni preliminari sulla gestione di applicazioni](../app-development/application-management-overview.md).  
  
 In [Compilazione di un'applicazione WPF](../app-development/building-a-wpf-application-wpf.md) vengono offerti maggiori dettagli su come compilare applicazioni che includono XAML usando la riga di comando e [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].  
  
 [Cenni preliminari sulle proprietà di dipendenza](dependency-properties-overview.md) offre altre informazioni sulla versatilità delle proprietà in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] introduce il concetto di proprietà di dipendenza.  
  
## <a name="see-also"></a>Vedere anche

- [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md)
- [Classi XAML e personalizzate per WPF](xaml-and-custom-classes-for-wpf.md)
- [Spazio dei nomi XAML (x:) Funzionalità del linguaggio](../../xaml-services/xaml-namespace-x-language-features.md)
- [Estensioni XAML WPF](wpf-xaml-extensions.md)
- [Cenni preliminari sugli elementi di base](base-elements-overview.md)
- [Strutture ad albero in WPF](trees-in-wpf.md)
