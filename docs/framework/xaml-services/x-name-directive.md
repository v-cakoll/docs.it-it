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
ms.openlocfilehash: 08594d9757596eed470ffba8b5b63a01c493c358
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583930"
---
# <a name="xname-directive"></a>Direttiva x:Name
Identifica in modo univoco gli elementi definiti XAML un namescope XAML. Ambiti dei nomi XAML e i relativi modelli di univocità è applicabile agli oggetti istanziati, quando Framework forniscono le API o implementare comportamenti che accedono a creato XAML dall'oggetto grafico in fase di esecuzione.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`XAMLNameValue`|Una stringa conforme alle restrizioni del [grammatica XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md).|  
  
## <a name="remarks"></a>Note  
 Dopo aver `x:Name` viene applicato a un framework di supporto del modello di programmazione, il nome è equivalente alla variabile che contiene un riferimento all'oggetto o un'istanza come restituito da un costruttore.  
  
 Il valore di un `x:Name` utilizzo della direttiva deve essere univoco all'interno di un namescope XAML. Per impostazione predefinita quando usati dall'API dei servizi XAML di .NET Framework, l'ambito dei nomi XAML primario è definito in corrispondenza dell'elemento radice XAML di una singola produzione XAML e include gli elementi contenuti in tale ambiente di produzione XAML. Aggiuntivi NameScope XAML discreti che potrebbero verificarsi all'interno di una singola produzione XAML possono essere definiti dal framework per affrontare gli scenari specifici. In WPF, ad esempio, nuovi ambiti dei nomi XAML sono definiti e creati da un modello che è anche definito in tale ambiente di produzione XAML. Per altre informazioni su ambiti dei nomi XAML (scritto ma rilevanti per molti concetti namescope XAML per WPF), vedere [NameScope XAML WPF](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 In genere `x:Name` non deve essere applicata in situazioni in cui anche usano `x:Key`. Le implementazioni XAML dai Framework esistenti specifici sono introdotti i concetti di sostituzione tra `x:Key` e `x:Name`, ma che non è una procedura consigliata. Servizi XAML di .NET framework non supporta tali concetti di sostituzione durante la gestione di informazioni/chiave con nome, ad esempio <xref:System.Windows.Markup.INameScope> o <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 Le regole dell'autorizzazione di `x:Name` , nonché l'imposizione di univocità del nome potenzialmente definiti dal framework di implementazione specifici. Tuttavia, per poter essere usato con i servizi XAML di .NET Framework, le definizioni di framework di univocità namescope XAML dovrebbero essere coerente con la definizione di <xref:System.Windows.Markup.INameScope> informazioni nella presente documentazione e devono usare le stesse regole relative alle dove la vengono applicate le informazioni. Ad esempio, il [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] implementazione divide i vari elementi di markup distinte <xref:System.Windows.NameScope> gli intervalli, ad esempio i dizionari risorse, l'albero logico dal XAML a livello di pagina, modelli e altri posticipata contenuto creato e quindi applica XAML univocità dei nomi all'interno di ogni spazio dei nomi XAML.  
  
 Per i tipi personalizzati che usano i writer di oggetti XAML di servizi XAML di .NET Framework, una proprietà che è mappata a `x:Name` su un tipo può essere stabilito o modificato. Per definire questo comportamento, fare riferimento al nome della proprietà per eseguire il mapping con il <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> nel codice di definizione del tipo.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> è un attributo a livello di tipo.  
  
 Dei servizi XAML di.NET Framework, la logica di supporto per il supporto di namescope XAML possono essere definiti in modo indipendente dal framework implementando il <xref:System.Windows.Markup.INameScope> interfaccia.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 In base alla configurazione di compilazione standard per un [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] dell'applicazione che usa XAML, le classi parziali e code-behind specificato `x:Name` diventa il nome di un campo che viene creato in sottostante codice quando [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] viene elaborato da un markup attività di generazione di compilazione e tale campo contiene un riferimento all'oggetto. Per impostazione predefinita, il campo creato è interno. È possibile modificare l'accesso al campo specificando il [X:FieldModifier attributo](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md). In WPF e Silverlight, la sequenza è che definisce la compilazione del markup e i nomi di campo in una classe parziale, ma il valore è inizialmente vuoto. Quindi, un metodo generato denominato `InitializeComponent` viene chiamato dall'interno il costruttore della classe. `InitializeComponent` è costituito `FindName` chiama utilizzando ognuna del `x:Name` valori presenti nella parte definita XAML della classe parziale come stringhe di input. I valori restituiti vengono quindi assegnati per il riferimento al campo con nome analogo per riempire i valori dei campi con gli oggetti creati da XAML l'analisi. L'esecuzione di `InitializeComponent` rendono possibile il riferimento l'oggetto runtime graph usando il `x:Name` / nome del campo direttamente, anziché dover chiamare `FindName` in modo esplicito ogni volta che è necessario un riferimento a un oggetto definito XAML.  
  
 Per un controllo WPF ha come destinazione dell'applicazione che usa Microsoft Visual Basic e include i file XAML con `Page` azione di compilazione, una proprietà di riferimento separata viene creata durante la compilazione che aggiunge il `WithEvents` (parola chiave) a tutti gli elementi che hanno un' `x:Name`per supportare `Handles` sintassi per i delegati dei gestori eventi. Questa proprietà è sempre pubblica. Per altre informazioni, vedere [Visual Basic e la gestione degli eventi WPF](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 `x:Name` viene utilizzato dal processore XAML WPF per registrare un nome in un namescope XAML in fase di caricamento, anche per i casi in cui la pagina non compilato dal markup dalle azioni di compilazione (ad esempio, XAML loose di un dizionario risorse). Uno dei motivi per questo comportamento è perché la `x:Name` potenzialmente è necessaria per <xref:System.Windows.Data.Binding.ElementName%2A> associazione. Per informazioni dettagliate, vedere [Panoramica sul Data Binding](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Come accennato in precedenza `x:Name` (o `Name`) non deve essere applicata in situazioni in cui anche usano `x:Key`. Il [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> presenta un comportamento speciale della definizione di se stesso come un namescope XAML ma restituzione non implementato o valori null per <xref:System.Windows.Markup.INameScope> API che consente di applicare questo comportamento. Se viene rilevato il parser XAML WPF `Name` oppure `x:Name` in un XAML definito <xref:System.Windows.ResourceDictionary>, il nome non viene aggiunto a qualsiasi namescope XAML. Tentativo di trovare il nome da qualsiasi ambito dei nomi XAML e `FindName` metodi non restituirà risultati validi.  
  
### <a name="xname-and-name"></a>x: nome e il nome  
 Molti scenari di applicazione WPF possono evitare qualsiasi uso del `x:Name` dell'attributo, perché il `Name` proprietà di dipendenza come specificato nel valore predefinito dello spazio dei nomi XAML per diversi importanti classi di base, ad esempio <xref:System.Windows.FrameworkElement> e <xref:System.Windows.FrameworkContentElement> soddisfa questo stesso scopo. Esistono ancora alcuni scenari comuni in XAML e WPF di codice in cui l'accesso a un elemento senza `Name` proprietà a livello di framework è importante. Ad esempio, alcune classi di supporto di animazioni e storyboard non supportano un `Name` proprietà, ma spesso è necessario farvi riferimento nel codice per controllare l'animazione. È consigliabile specificare `x:Name` come attributo di sequenze temporali e le trasformazioni che vengono create in XAML, se si prevede di fare riferimento a essi dal codice in un secondo momento.  
  
 Se <xref:System.Windows.FrameworkElement.Name%2A> è disponibile come proprietà della classe <xref:System.Windows.FrameworkElement.Name%2A> e `x:Name` possono essere utilizzati indifferentemente come attributi, ma genererà un'eccezione di analisi se vengono specificati entrambi nello stesso elemento. Se il XAML verrà compilato dal markup, l'eccezione si verificherà nella compilazione del markup, in caso contrario, si verifica al caricamento.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> può essere impostato utilizzando la sintassi degli attributi XAML e nel codice usando <xref:System.Windows.DependencyObject.SetValue%2A>; si noti tuttavia che l'impostazione di <xref:System.Windows.FrameworkElement.Name%2A> proprietà nel codice non viene creato il riferimento al campo rappresentativo entro l'ambito dei nomi XAML nella maggior parte dei casi in cui il XAML è già caricato. Invece di provare a impostare <xref:System.Windows.FrameworkElement.Name%2A> nel codice usare <xref:System.Windows.NameScope> metodi del codice in base l'ambito dei nomi appropriato.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> può essere impostato anche utilizzando la sintassi degli elementi con testo interno, ma che è insolito. Al contrario, `x:Name` non può essere impostata nella sintassi degli elementi proprietà XAML o nel codice utilizzando <xref:System.Windows.DependencyObject.SetValue%2A>; può essere impostata solo tramite sintassi degli attributi negli oggetti perché è una direttiva.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight  
 `x:Name` per Silverlight è documentato separatamente. Per altre informazioni, vedere [XAML Namespace (x) Funzionalità del linguaggio (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>  
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>  
 [Strutture ad albero in WPF](../../../docs/framework/wpf/advanced/trees-in-wpf.md)
