---
title: Direttiva x:Name
ms.date: 03/30/2017
f1_keywords:
- x:Name
- xName
- Name
helpviewer_keywords:
- x:Name attribute [XAML Services]
- XAML [XAML Services], x:Name attribute
- Name attribute in XAML [XAML Services]
ms.assetid: b7e61222-e8cf-48d2-acd0-6df3b7685d48
ms.openlocfilehash: 9f812a49a3217a563be1bd7f1d999b641c28463d
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071451"
---
# <a name="xname-directive"></a>Direttiva x:Name

Identifica in modo univoco gli elementi definiti da XAML in un ambito dei nomi XAML. Gli ambiti dei nomi XAML e i relativi modelli di univocità possono essere applicati agli oggetti di cui è stata creata un'istanza, quando i framework forniscono API o implementano comportamenti che accedono all'oggetto grafico creato da XAML in fase di esecuzione.

## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi

```xaml
<object x:Name="XAMLNameValue".../>
```

## <a name="xaml-values"></a>Valori XAML

|||
|-|-|
|`XAMLNameValue`|Stringa conforme alle restrizioni della grammatica [XamlName](xamlname-grammar.md).|

## <a name="remarks"></a>Osservazioni

Dopo `x:Name` che viene applicato al modello di programmazione di backup di un framework, il nome è equivalente alla variabile che contiene un riferimento a un oggetto o un'istanza restituita da un costruttore.

Il valore `x:Name` di un utilizzo della direttiva deve essere univoco all'interno di un ambito dei nomi XAML. Per impostazione predefinita, se utilizzato dall'API dei servizi XAML .NET, l'ambito dei nomi XAML primario viene definito nell'elemento radice XAML di una singola produzione XAML e include gli elementi contenuti in tale produzione XAML. Gli ambiti dei nomi XAML discreti aggiuntivi che potrebbero verificarsi all'interno di una singola produzione XAML possono essere definiti dai framework per risolvere scenari specifici. Ad esempio, in WPFWPF, i nuovi ambiti dei nomi XAML vengono definiti e creati da qualsiasi modello definito anche in tale produzione XAML. Per altre informazioni sugli ambiti dei nomi XAML (scritti per WPF ma rilevanti per molti concetti relativi all'ambito dei nomi XAML), vedere Ambiti dei nomi [XAML WPF](../../framework/wpf/advanced/wpf-xaml-namescopes.md).

In generale, `x:Name` non dovrebbe essere applicato `x:Key`in situazioni che utilizzano anche . Le implementazioni XAML di framework esistenti `x:Key` specifici `x:Name`hanno introdotto concetti di sostituzione tra e , ma questa non è una procedura consigliata. I servizi XAML .NET non supportano tali concetti <xref:System.Windows.Markup.INameScope> di <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>sostituzione quando si gestiscono informazioni su nome/chiave, ad esempio o .

Le regole per `x:Name` l'autorizzazione e l'applicazione dell'univocità del nome sono potenzialmente definite da specifici framework di implementazione. Tuttavia, per essere utilizzabili con i servizi XAML .NET, le definizioni <xref:System.Windows.Markup.INameScope> del framework di univocità dell'ambito dei nomi XAML devono essere coerenti con la definizione delle informazioni in questa documentazione e devono usare le stesse regole relative alla posizione in cui vengono applicate le informazioni. Ad esempio, [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] l'implementazione divide <xref:System.Windows.NameScope> vari elementi di markup in intervalli separati, ad esempio dizionari risorse, l'albero logico creato dal codice XAML a livello di pagina, modelli e altro contenuto posticipato, quindi applica l'univocità del nome XAML all'interno di ognuno di questi ambiti dei nomi XAML.

Per i tipi personalizzati che usano writer di oggetti `x:Name` XAML dei servizi XAML di .NET, è possibile stabilire o modificare una proprietà che esegue il mapping a un tipo. Per definire questo comportamento, fare riferimento al nome <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> della proprietà di cui eseguire il mapping con il nel codice di definizione del tipo.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>è un attributo a livello di tipo.

Using.NET servizi XAML, la logica di supporto per il supporto dell'ambito <xref:System.Windows.Markup.INameScope> dei nomi XAML può essere definita in modo indipendente dal framework implementando l'interfaccia.

## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF

Nella configurazione di compilazione standard per un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che usa XAML, classi parziali e code-behind, l'oggetto specificato `x:Name` diventa il nome di un campo creato nel codice sottostante quando [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] viene elaborato da un'attività di compilazione della compilazione del markup e tale campo contiene un riferimento all'oggetto. Per impostazione predefinita, il campo creato è interno. È possibile modificare l'accesso ai campi specificando [l'attributo x:FieldModifier](xfieldmodifier-directive.md). In WPF e Silverlight, la sequenza è che la compilazione del markup definisce e denomina il campo in una classe parziale, ma il valore è inizialmente vuoto. Quindi, un metodo `InitializeComponent` generato denominato viene chiamato dall'interno del costruttore di classe. `InitializeComponent`è `FindName` costituito da `x:Name` chiamate che utilizzano ognuno dei valori presenti nella parte definita da XAML della classe parziale come stringhe di input. I valori restituiti vengono quindi assegnati al riferimento al campo con nome simile per riempire i valori dei campi con oggetti creati dall'analisi XAML. L'esecuzione `InitializeComponent` di rendere possibile fare riferimento all'oggetto grafico in fase di esecuzione utilizzando direttamente il nome del `x:Name` campo / , anziché dover chiamare `FindName` in modo esplicito ogni volta che è necessario un riferimento a un oggetto definito da XAML.

Per un'applicazione WPFWPF che usa le destinazioni di Microsoft Visual Basic e include `Page` `WithEvents` file XAML con azione `x:Name`di `Handles` compilazione, durante la compilazione viene creata una proprietà di riferimento separata che aggiunge la parola chiave a tutti gli elementi che dispongono di un oggetto , per supportare la sintassi per i delegati del gestore eventi. Questa proprietà è sempre pubblica. Per altre informazioni, vedere [Visual Basic e la gestione degli eventi WPF](../../framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).

`x:Name`viene utilizzato dal processore XAML WPF per registrare un nome in un ambito dei nomi XAML in fase di caricamento, anche nei casi in cui la pagina non viene compilata dal markup dalle azioni di compilazione (ad esempio, XAML separato di un dizionario risorse). Uno dei motivi di `x:Name` questo comportamento è <xref:System.Windows.Data.Binding.ElementName%2A> perché l'oggetto è potenzialmente necessario per l'associazione. Per informazioni dettagliate, vedere [Cenni preliminari sull'associazione dati](../data/data-binding-overview.md).

Come accennato in precedenza, `x:Name` (o `Name`) `x:Key`non devono essere applicati in situazioni che utilizzano anche . L'oggetto [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> ha un comportamento speciale di definizione di se stesso <xref:System.Windows.Markup.INameScope> come ambito dei nomi XAML, ma la restituzione di valori Not Implemented o null per le API è un modo per applicare questo comportamento. Se il parser XAML `Name` `x:Name` WPF rileva o <xref:System.Windows.ResourceDictionary>in un oggetto definito da XAML, il nome non viene aggiunto ad alcun ambito dei nomi XAML. Il tentativo di trovare tale nome da `FindName` qualsiasi ambito dei nomi XAML e i metodi non restituiranno risultati validi.

### <a name="xname-and-name"></a>x:Nome e nome

Molti scenari di applicazione WPFWPF `x:Name` possono evitare qualsiasi utilizzo dell'attributo, perché la `Name` proprietà di <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> dipendenza specificata nello spazio dei nomi XAML predefinito per diverse delle classi di base importanti, ad esempio e soddisfa lo stesso scopo. Esistono ancora alcuni scenari XAML e WPF comuni in `Name` cui l'accesso del codice a un elemento senza proprietà a livello di framework è importante. Ad esempio, alcune classi di supporto `Name` di animazione e storyboard non supportano una proprietà, ma spesso è necessario farvi riferimento nel codice per controllare l'animazione. È necessario `x:Name` specificare come attributo nelle sequenze temporali e nelle trasformazioni create in XAML, se si intende farvi riferimento dal codice in un secondo momento.

Se <xref:System.Windows.FrameworkElement.Name%2A> è disponibile come proprietà <xref:System.Windows.FrameworkElement.Name%2A> nella `x:Name` classe e può essere utilizzata in modo intercambiabile come attributi, ma verrà verificata un'eccezione di analisi se entrambi vengono specificati nello stesso elemento. Se il codice XAML è markup compilato, l'eccezione si verificherà durante la compilazione del markup, in caso contrario si verifica al caricamento.

<xref:System.Windows.FrameworkElement.Name%2A>può essere impostato utilizzando la sintassi <xref:System.Windows.DependencyObject.SetValue%2A>degli attributi XAML e nel codice usando ; Si noti <xref:System.Windows.FrameworkElement.Name%2A> tuttavia che l'impostazione della proprietà nel codice non crea il riferimento al campo rappresentativo all'interno dell'ambito dei nomi XAML nella maggior parte dei casi in cui il codice XAML è già caricato. Anziché tentare <xref:System.Windows.FrameworkElement.Name%2A> di impostare <xref:System.Windows.NameScope> nel codice, utilizzare i metodi dal codice, in base all'ambito dei nomi appropriato.

<xref:System.Windows.FrameworkElement.Name%2A>può anche essere impostato utilizzando la sintassi degli elementi proprietà con testo interno, ma questo non è comune. Al contrario, `x:Name` non può essere impostato nella <xref:System.Windows.DependencyObject.SetValue%2A>sintassi degli elementi proprietà XAML o nel codice che usa ; può essere impostato solo utilizzando la sintassi degli attributi sugli oggetti perché è una direttiva.

## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight

`x:Name`per Silverlight è documentato separatamente. Per altre informazioni, vedere [Spazio dei nomi XAML (x:) Funzionalità del linguaggio (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [Strutture ad albero in WPF](../../framework/wpf/advanced/trees-in-wpf.md)
