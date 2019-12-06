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
ms.openlocfilehash: d17d977384962980839fbe2b2c0a4708412d403d
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837220"
---
# <a name="xname-directive"></a>Direttiva x:Name
Identifica in modo univoco gli elementi definiti da XAML in un ambito dei nomi XAML. Gli ambiti dei nomi XAML e i rispettivi modelli di univocità possono essere applicati agli oggetti di cui è stata creata un'istanza, quando i Framework forniscono API o implementano comportamenti che accedono all'oggetto grafico XAML creato in fase di esecuzione.  
  
## <a name="xaml-attribute-usage"></a>Utilizzo della sintassi XAML per attributi  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>Valor XAML  
  
|||  
|-|-|  
|`XAMLNameValue`|Stringa conforme alle restrizioni della [Grammatica XamlName](xamlname-grammar.md).|  
  
## <a name="remarks"></a>Note  
 Quando `x:Name` viene applicato al modello di programmazione sottostante di un Framework, il nome è equivalente alla variabile che include un riferimento a un oggetto o un'istanza di restituita da un costruttore.  
  
 Il valore di un utilizzo della direttiva `x:Name` deve essere univoco all'interno di un ambito dei nomi XAML. Per impostazione predefinita, se usato da .NET Framework API dei servizi XAML, l'ambito dei nomi XAML primario viene definito nell'elemento radice XAML di una singola produzione XAML e include gli elementi contenuti nella produzione XAML. È possibile definire ambiti dei nomi XAML discreti aggiuntivi che possono verificarsi all'interno di una singola produzione XAML tramite Framework per risolvere scenari specifici. In WPF, ad esempio, i nuovi ambiti dei nomi XAML vengono definiti e creati da qualsiasi modello definito anche in tale produzione XAML. Per ulteriori informazioni sugli ambiti dei nomi XAML (scritti per WPF ma pertinenti per molti concetti relativi ai NameScope XAML), vedere [NAMESCOPE XAML WPF](../wpf/advanced/wpf-xaml-namescopes.md).  
  
 In generale, `x:Name` non devono essere applicati in situazioni in cui viene utilizzato anche `x:Key`. Le implementazioni XAML da specifici Framework esistenti hanno introdotto concetti di sostituzione tra `x:Key` e `x:Name`, ma questa non è una procedura consigliata. .NET Framework servizi XAML non supporta questi concetti di sostituzione quando si gestiscono informazioni relative al nome e alla chiave, ad esempio <xref:System.Windows.Markup.INameScope> o <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 Le regole per consentire la `x:Name` e l'imposizione di univocità dei nomi sono potenzialmente definite da Framework di implementazione specifici. Tuttavia, per poter essere utilizzato con i servizi .NET Framework XAML, le definizioni del Framework di univocità dei nomi XAML devono essere coerenti con la definizione di <xref:System.Windows.Markup.INameScope> le informazioni contenute in questa documentazione e devono utilizzare le stesse regole relative alla posizione in cui vengono applicate le informazioni. Ad esempio, l'implementazione di [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] divide vari elementi di markup in intervalli di <xref:System.Windows.NameScope> distinti, ad esempio dizionari risorse, l'albero logico creato dal codice XAML a livello di pagina, modelli e altro contenuto posticipato, quindi applica l'univocità dei nomi XAML all'interno di ognuno di questi ambiti dei nomi XAML.  
  
 Per i tipi personalizzati che usano .NET Framework writer di oggetti XAML dei servizi XAML, è possibile stabilire o modificare una proprietà mappata a `x:Name` in un tipo. Questo comportamento viene definito facendo riferimento al nome della proprietà di cui eseguire il mapping con il <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> nel codice della definizione del tipo.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> è un attributo a livello di tipo.  
  
 I servizi XAML di Using.NET Framework, la logica sottostante per il supporto dell'ambito dei nomi XAML possono essere definiti in modo indipendente dal Framework implementando l'interfaccia <xref:System.Windows.Markup.INameScope>.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo di WPF  
 Nella configurazione di compilazione standard per un'applicazione [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] che usa XAML, classi parziali e code-behind, il `x:Name` specificato diventa il nome di un campo creato nel codice sottostante quando [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] viene elaborato da un'attività di compilazione di compilazione del markup e tale campo include un riferimento all'oggetto. Per impostazione predefinita, il campo creato è interno. È possibile modificare l'accesso ai campi specificando l' [attributo x:FieldModifier](x-fieldmodifier-directive.md). In WPF e Silverlight, la sequenza è che la compilazione del markup definisce e denomina il campo in una classe parziale, ma il valore è inizialmente vuoto. Quindi, un metodo generato denominato `InitializeComponent` viene chiamato dall'interno del costruttore della classe. `InitializeComponent` è costituito da `FindName` chiamate che usano ognuno dei valori `x:Name` presenti nella parte definita da XAML della classe parziale come stringhe di input. I valori restituiti vengono quindi assegnati al riferimento al campo denominato like per inserire i valori dei campi con gli oggetti creati dall'analisi XAML. L'esecuzione di `InitializeComponent` consente di fare riferimento all'oggetto grafico del runtime usando direttamente il nome del `x:Name`/campo, anziché dover chiamare `FindName` in modo esplicito ogni volta che è necessario un riferimento a un oggetto definito da XAML.  
  
 Per un'applicazione WPF che usa le destinazioni di Microsoft Visual Basic e include i file XAML con `Page` azione di compilazione, durante la compilazione viene creata una proprietà di riferimento distinta che aggiunge la parola chiave `WithEvents` a tutti gli elementi che hanno un `x:Name`per supportare la sintassi `Handles` per i delegati del gestore eventi. Questa proprietà è sempre pubblica. Per altre informazioni, vedere [Visual Basic e la gestione degli eventi WPF](../wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 `x:Name` viene utilizzato dal processore XAML WPF per registrare un nome in un ambito dei nomi XAML in fase di caricamento, anche per i casi in cui la pagina non è compilata dal markup dalle azioni di compilazione (ad esempio, il codice XAML separato di un dizionario risorse). Uno dei motivi di questo comportamento è dovuto al fatto che la `x:Name` è potenzialmente necessaria per <xref:System.Windows.Data.Binding.ElementName%2A> binding. Per informazioni dettagliate, vedere [Cenni preliminari sul data binding](../../desktop-wpf/data/data-binding-overview.md).  
  
 Come indicato in precedenza, `x:Name` (o `Name`) non devono essere applicati in situazioni in cui viene utilizzato anche `x:Key`. Il [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> presenta un comportamento speciale della definizione di se stesso come ambito dei nomi XAML, ma restituendo valori non implementati o null per le API <xref:System.Windows.Markup.INameScope> come modo per applicare questo comportamento. Se il parser XAML WPF rileva `Name` o `x:Name` in un <xref:System.Windows.ResourceDictionary>definito da XAML, il nome non viene aggiunto ad alcun ambito dei nomi XAML. Il tentativo di trovare tale nome da qualsiasi NameScope XAML e i metodi `FindName` non restituirà risultati validi.  
  
### <a name="xname-and-name"></a>x:Name e nome  
 Molti scenari di applicazioni WPF possono evitare qualsiasi utilizzo dell'attributo `x:Name`, perché la proprietà di dipendenza `Name` specificata nello spazio dei nomi XAML predefinito per diverse classi di base importanti, ad esempio <xref:System.Windows.FrameworkElement> e <xref:System.Windows.FrameworkContentElement> soddisfa lo stesso scopo. Esistono ancora alcuni scenari comuni di XAML e WPF in cui l'accesso al codice a un elemento senza proprietà `Name` a livello di Framework è importante. Alcune classi di supporto per animazioni e storyboard, ad esempio, non supportano una proprietà `Name`, ma spesso è necessario farvi riferimento nel codice per controllare l'animazione. È necessario specificare `x:Name` come attributo per le sequenze temporali e le trasformazioni create in XAML, se si intende farvi riferimento dal codice in un secondo momento.  
  
 Se <xref:System.Windows.FrameworkElement.Name%2A> è disponibile come proprietà nella classe, <xref:System.Windows.FrameworkElement.Name%2A> e `x:Name` possono essere utilizzati in modo intercambiabile come attributi, ma si otterrà un'eccezione di analisi se entrambi sono specificati nello stesso elemento. Se il markup XAML è compilato, l'eccezione si verificherà nella compilazione del markup; in caso contrario, si verificherà in caso di caricamento.  
  
 è possibile impostare <xref:System.Windows.FrameworkElement.Name%2A> utilizzando la sintassi degli attributi XAML e nel codice utilizzando <xref:System.Windows.DependencyObject.SetValue%2A>; Si noti tuttavia che l'impostazione della proprietà <xref:System.Windows.FrameworkElement.Name%2A> nel codice non crea il riferimento al campo rappresentativo nell'ambito dei nomi XAML nella maggior parte dei casi in cui il codice XAML è già caricato. Anziché tentare di impostare <xref:System.Windows.FrameworkElement.Name%2A> nel codice, utilizzare <xref:System.Windows.NameScope> metodi dal codice rispetto all'ambito dei nomi appropriato.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> possono essere impostate anche usando la sintassi dell'elemento Property con testo interno, ma questo non è comune. Al contrario, non è possibile impostare `x:Name` nella sintassi dell'elemento proprietà XAML o nel codice tramite <xref:System.Windows.DependencyObject.SetValue%2A>; può essere impostato solo utilizzando la sintassi dell'attributo sugli oggetti perché è una direttiva.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight.  
 `x:Name` per Silverlight è documentato separatamente. Per altre informazioni, vedere [spazio dei nomi XAML (x:) Funzionalità del linguaggio (Silverlight)](https://docs.microsoft.com/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc188995(v=vs.95)).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>
- <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>
- [Strutture ad albero in WPF](../wpf/advanced/trees-in-wpf.md)
