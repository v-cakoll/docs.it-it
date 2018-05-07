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
ms.openlocfilehash: 7fcb7fe767e892109e48c5e56db26b5943b6ef13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="xname-directive"></a>Direttiva x:Name
Identifica in modo univoco gli elementi XAML in un namescope XAML. Ambiti dei nomi XAML e i relativi modelli di univocità possono essere applicate agli oggetti, un'istanza quando Framework forniscono le API o implementare comportamenti che accedono a creato XAML oggetto grafico in fase di esecuzione.  
  
## <a name="xaml-attribute-usage"></a>Uso della sintassi XAML per gli attributi  
  
```xaml  
<object x:Name="XAMLNameValue".../>  
```  
  
## <a name="xaml-values"></a>Valori XAML  
  
|||  
|-|-|  
|`XAMLNameValue`|Una stringa conforme alle restrizioni del [grammatica XamlName](../../../docs/framework/xaml-services/xamlname-grammar.md).|  
  
## <a name="remarks"></a>Note  
 Dopo aver `x:Name` viene applicato a un framework di supporto del modello di programmazione, il nome è equivalente a una variabile che contiene un riferimento all'oggetto o un'istanza come restituito da un costruttore.  
  
 Il valore di un `x:Name` utilizzo della direttiva deve essere univoco all'interno di un namescope XAML. Per impostazione predefinita quando usati dall'API dei servizi XAML di .NET Framework, l'ambito dei nomi XAML primario è definito nell'elemento radice XAML di una singola produzione XAML e include gli elementi contenuti nella produzione di XAML. NameScope XAML discreti aggiuntivi che potrebbero verificarsi all'interno di una singola produzione XAML possono essere definiti dal framework per indirizzare scenari specifici. Ad esempio, in WPF nuovo NameScope XAML sono definiti e creati da un modello che è anche definito in tale produzione XAML. Per ulteriori informazioni sui NameScope XAML (scritti ma attinenti per molti concetti namescope XAML per WPF), vedere [NameScope XAML WPF](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).  
  
 In generale, `x:Name` non deve essere applicata in situazioni che utilizzano anche `x:Key`. Le implementazioni XAML da framework specifici esistenti sono stati introdotti i concetti di sostituzione tra `x:Key` e `x:Name`, ma che non è una procedura consigliata. Servizi XAML di .NET framework non supporta tali concetti di sostituzione durante la gestione di informazioni/chiave con nome, ad esempio <xref:System.Windows.Markup.INameScope> o <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.  
  
 Le regole dell'autorizzazione di `x:Name` nonché l'imposizione di univocità del nome sono definite potenzialmente dai framework di implementazione specifici. Tuttavia, per poter essere usato con i servizi XAML di .NET Framework, le definizioni del framework di univocità namescope XAML dovrebbero essere coerente con la definizione di <xref:System.Windows.Markup.INameScope> informazioni in questa documentazione e deve utilizzare le stesse regole riguardanti la posizione di vengono applicate le informazioni. Ad esempio, il [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] implementazione divide vari elementi di markup in separato <xref:System.Windows.NameScope> gli intervalli, ad esempio dizionari delle risorse, l'albero logico creato dalle XAML a livello di pagina, modelli e altri posticipata contenuto e quindi applica XAML univocità dei nomi all'interno di ogni spazio dei nomi XAML.  
  
 Per i tipi personalizzati che utilizzano i writer di oggetti XAML dei servizi XAML di .NET Framework, una proprietà che esegue il mapping a `x:Name` su un tipo può essere stabilito o modificato. Per definire questo comportamento è necessario fare riferimento al nome della proprietà per eseguire il mapping con la <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> nel codice di definizione del tipo.  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> è un attributo a livello di tipo.  
  
 Servizi XAML di.NET Framework, la logica di supporto per il supporto namescope XAML può essere definiti in modo indipendente dal framework implementando il <xref:System.Windows.Markup.INameScope> interfaccia.  
  
## <a name="wpf-usage-notes"></a>Note sull'utilizzo WPF  
 In base alla configurazione di compilazione standard per un [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] applicazione che usa XAML, classi parziali e code-behind, specificato `x:Name` diventa il nome di un campo che viene creato nell'oggetto sottostante il codice quando [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] viene elaborato da un markup attività di compilazione di compilazione e il campo contiene un riferimento all'oggetto. Per impostazione predefinita, il campo creato è interno. È possibile modificare l'accesso al campo specificando il [attributo X:FieldModifier](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md). In WPF e Silverlight, la sequenza è che definisce la compilazione del markup e nomi di campo in una classe parziale, ma il valore è inizialmente vuoto. Quindi, un metodo generato denominato `InitializeComponent` viene chiamata dall'interno del costruttore della classe. `InitializeComponent` è costituito da `FindName` chiamate tramite ognuno del `x:Name` valori presenti nella parte definite da XAML della classe parziale come stringhe di input. I valori restituiti vengono quindi assegnati per il riferimento al nome di campo per riempire i valori dei campi con gli oggetti creati da XAML durante l'analisi. L'esecuzione di `InitializeComponent` consentono di riferimento l'oggetto fase di esecuzione grafico utilizzando il `x:Name` / nome del campo direttamente, anziché dover chiamare `FindName` in modo esplicito ogni volta che è necessario un riferimento a un oggetto definite da XAML.  
  
 Per un'applicazione WPF ha come destinazione dell'applicazione che utilizza Microsoft Visual Basic e include i file XAML con `Page` operazione di compilazione, una proprietà di riferimento separata viene creata durante la compilazione che aggiunge il `WithEvents` (parola chiave) a tutti gli elementi che dispongono di un' `x:Name`per supportare `Handles` sintassi delegati del gestore eventi. Questa proprietà è sempre pubblica. Per altre informazioni, vedere [Visual Basic e la gestione degli eventi WPF](../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md).  
  
 `x:Name` viene utilizzato dal processore XAML di WPF per registrare un nome in un namescope XAML in fase di caricamento, anche per i casi in cui la pagina non è compilato dal markup dalle azioni di compilazione (ad esempio, XAML separato di un dizionario risorse). Uno dei motivi per questo comportamento è perché il `x:Name` può essere necessario per <xref:System.Windows.Data.Binding.ElementName%2A> associazione. Per informazioni dettagliate, vedere [Panoramica del Data Binding](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Come accennato in precedenza, `x:Name` (o `Name`) non deve essere applicata in situazioni che utilizzano anche `x:Key`. Il [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.ResourceDictionary> presenta un comportamento speciale di definizione di se stesso come un namescope XAML ma restituendo Not Implemented o valori null per <xref:System.Windows.Markup.INameScope> API come un modo per applicare questo comportamento. Se il parser XAML WPF rileva `Name` o `x:Name` in un definite da XAML <xref:System.Windows.ResourceDictionary>, il nome non è stato aggiunto a qualsiasi ambito dei nomi XAML. Tentativo di trovare tale nome dai namescope XAML e `FindName` metodi non restituiscono risultati validi.  
  
### <a name="xname-and-name"></a>x: nome e il nome  
 Molti scenari di applicazione WPF è possono evitare l'utilizzo della `x:Name` attributo, perché il `Name` proprietà di dipendenza specificata nel valore predefinito dello spazio dei nomi XAML per molte delle classi base importanti, ad esempio <xref:System.Windows.FrameworkElement> e <xref:System.Windows.FrameworkContentElement> soddisfa questo stesso scopo. Sono disponibili alcuni scenari comuni di XAML e WPF in cui accesso di codice a un elemento senza `Name` proprietà a livello di framework è importante. Ad esempio, alcune classi di supporto di animazioni e storyboard non supportano un `Name` proprietà, ma spesso è necessario fare riferimento nel codice per controllare l'animazione. È necessario specificare `x:Name` come attributo nelle sequenze temporali e le trasformazioni che vengono create in XAML, se si prevede di fare riferimento a esse dal codice in un secondo momento.  
  
 Se <xref:System.Windows.FrameworkElement.Name%2A> è disponibile come una proprietà sulla classe, <xref:System.Windows.FrameworkElement.Name%2A> e `x:Name` possono essere utilizzate indifferentemente come attributi, ma se vengono specificati entrambi nello stesso elemento si verificherà un'eccezione di analisi. Se il codice XAML viene compilata, l'eccezione si verificherà nella compilazione del markup, in caso contrario si verifica al caricamento.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> può essere impostato utilizzando sintassi XAML per gli attributi e nel codice usando <xref:System.Windows.DependencyObject.SetValue%2A>; si noti tuttavia che l'impostazione di <xref:System.Windows.FrameworkElement.Name%2A> proprietà nel codice non viene creato il riferimento al campo rappresentativo entro l'ambito dei nomi XAML nella maggior parte dei casi in cui il codice XAML è già caricato. Anziché tentare di impostare <xref:System.Windows.FrameworkElement.Name%2A> nel codice, utilizzare <xref:System.Windows.NameScope> metodi del codice in base l'ambito dei nomi appropriato.  
  
 <xref:System.Windows.FrameworkElement.Name%2A> può essere impostato anche utilizzando la sintassi degli elementi di proprietà con il testo interno, ma che è comune. Al contrario, `x:Name` non può essere impostata nella sintassi degli elementi di proprietà XAML o nel codice usando <xref:System.Windows.DependencyObject.SetValue%2A>; può essere impostata solo utilizzando la sintassi degli attributi per gli oggetti perché è una direttiva.  
  
## <a name="silverlight-usage-notes"></a>Note sull'utilizzo di Silverlight  
 `x:Name` per Silverlight è documentato separatamente. Per ulteriori informazioni, vedere [Namespace XAML (x) Funzionalità del linguaggio (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.FrameworkElement.Name%2A?displayProperty=nameWithType>  
 <xref:System.Windows.FrameworkContentElement.Name%2A?displayProperty=nameWithType>  
 [Strutture ad albero in WPF](../../../docs/framework/wpf/advanced/trees-in-wpf.md)
