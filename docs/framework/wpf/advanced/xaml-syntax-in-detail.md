---
title: Descrizione dettagliata della sintassi XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XML [WPF], namespaces
- XAML [WPF], parsing of attributes
- parsing of attributes [WPF]
- XAML [WPF], markup extensions
- attached properties [WPF]
- tag syntax [XAML]
- markup extensions [WPF]
- XAML [WPF], object element syntax
- XAML [WPF], syntax terminology
- attached events [WPF]
- lookup semantics [WPF]
- XAML [WPF], attached events
- XAML [WPF], content syntax
- XAML [WPF], lookup semantics
- content syntax [WPF]
- object element syntax [WPF]
- syntax terminology [XAML]
- XAML [WPF], attached properties
- attributes [XAML], parsing
- XAML [WPF], tag syntax
- XAML [WPF], attribute syntax
- property element syntax [WPF]
- terminology [XAML]
- namespaces [WPF], XML
- attribute syntax [XAML]
- XAML [WPF], property element syntax
ms.assetid: 67cce290-ca26-4c41-a797-b68aabc45479
ms.openlocfilehash: 5f8bb862ce443fd7397036b10f69cda65a6960bc
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646151"
---
# <a name="xaml-syntax-in-detail"></a>Descrizione dettagliata della sintassi XAML
In questo argomento vengono definiti i termini utilizzati per descrivere gli elementi della sintassi XAML. Questi termini vengono usati frequentemente nella parte restante di questa documentazione, sia per la documentazione WPF in modo specifico che per gli altri framework che usano XAML o i concetti XAML di base abilitati dal supporto del linguaggio XAML a livello di System.Xaml. Questo argomento si espande sulla terminologia di base introdotta nell'argomento [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).  

<a name="the_xaml_language_specification"></a>
## <a name="the-xaml-language-specification"></a>Specifiche del linguaggio XAMLThe XAML Language Specification  
 La terminologia della sintassi XAML definita qui è anche definita o a cui viene fatto riferimento all'interno della specifica del linguaggio XAML. XAML è un linguaggio basato su XML e segue o espande le regole strutturali XML. Parte della terminologia è condivisa da o si basa sulla terminologia comunemente utilizzata per descrivere il linguaggio XML o il modello a oggetti del documento XML.  
  
 Per ulteriori informazioni sulla specifica del linguaggio XAML, scaricare [ \[MS-XAML\] ](https://download.microsoft.com/download/0/A/6/0A6F7755-9AF5-448B-907D-13985ACCF53E/[MS-XAML].pdf) dall'Area download Microsoft.  
  
<a name="xaml_and_clr"></a>
## <a name="xaml-and-clr"></a>XAML e CLR  
 XAML è un linguaggio di markup. Common Language Runtime (CLR), come implicito dal nome, consente l'esecuzione di runtime. XAML non è di per sé uno dei linguaggi comuni che viene utilizzato direttamente dal runtime CLR. Al contrario, è possibile pensare a XAML come supporto del proprio sistema di tipi. Il particolare sistema di analisi XAML utilizzato da WPFWPF si basa su CLR e sul sistema di tipi CLR. I tipi XAML vengono mappati ai tipi CLR per creare un'istanza di una rappresentazione in fase di esecuzione quando il codice XAML per WPF viene analizzato. Per questo motivo, il resto della discussione sulla sintassi in questo documento includerà riferimenti al sistema di tipi CLR, anche se le discussioni di sintassi equivalenti nella specifica del linguaggio XAML non lo fanno. (In base al livello di specifica del linguaggio XAML, i tipi XAML potrebbero essere mappati a qualsiasi altro sistema di tipi, che non deve essere CLR, ma che richiederebbe la creazione e l'uso di un parser XAML diverso.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Membri di tipi ed ereditarietà delle classi  
 Le proprietà e gli eventi visualizzati come membri XAML di un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipo vengono spesso ereditati dai tipi di base. Si consideri ad `<Button Background="Blue" .../>`esempio questo esempio: . La <xref:System.Windows.Controls.Control.Background%2A> proprietà non è una <xref:System.Windows.Controls.Button> proprietà dichiarata immediatamente nella classe, se si esamina la definizione della classe, i risultati della reflection o la documentazione. Al <xref:System.Windows.Controls.Control.Background%2A> contrario, viene <xref:System.Windows.Controls.Control> ereditato dalla classe di base.  
  
 Il comportamento di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ereditarietà delle classi degli elementi XAML è una deviazione significativa rispetto a un'interpretazione applicata allo schema del markup XML. L'ereditarietà delle classi può diventare complessa, in particolare quando le classi di base intermedie sono astratte o quando sono coinvolte interfacce. Questo è uno dei motivi per cui il set di elementi XAML e i relativi attributi consentiti è difficile da rappresentare in modo accurato e completo utilizzando i tipi di schema che vengono in genere utilizzati per la programmazione XML, ad esempio il formato DTD o XSD. Un altro motivo è che le funzionalità di estendibilità e mapping dei tipi del linguaggio XAML stesso impediscono la completezza di qualsiasi rappresentazione fissa dei tipi e dei membri consentiti.  
  
<a name="object_element_syntax"></a>
## <a name="object-element-syntax"></a>Sintassi degli elementi oggetto  
 *La sintassi* degli elementi oggetto è la sintassi del markup XAML che crea un'istanza di una classe o struttura CLR dichiarando un elemento XML. Questa sintassi è simile alla sintassi degli elementi di altri linguaggi di markup, ad esempio HTML. La sintassi degli elementi oggetto\<inizia con una parentesi angolare sinistra ( ), seguita immediatamente dal nome del tipo della classe o della struttura di cui viene creata un'istanza. Zero o più spazi possono seguire il nome del tipo e zero o più attributi possono anche essere dichiarati sull'elemento oggetto, con uno o più spazi che separano ogni attributo nome -"valore" coppia. Infine, deve essere vera una delle seguenti condizioni:  
  
- L'elemento e il tag devono essere chiusi da una barra (/) seguita immediatamente da una parentesi angolare destra (>).  
  
- Il tag di apertura deve essere completato da una parentesi angolare destra (>). Altri elementi oggetto, elementi di proprietà o testo interno possono seguire il tag di apertura. Il contenuto può essere contenuto in questo caso è in genere vincolato dal modello a oggetti dell'elemento. Deve esistere anche il tag di chiusura equivalente per l'elemento oggetto, nella corretta nidificazione ed equilibrio con altre coppie di tag di apertura e chiusura.  
  
 XAML come implementato da .NET dispone di un set di regole che eseguono il mapping di elementi oggetto in tipi, attributi in proprietà o eventi e spazi dei nomi XAML agli spazi dei nomi CLR più assembly. Per WPF e .NET, gli elementi oggetto XAML eseguono il mapping ai tipi .NET definiti negli assembly a cui si fa riferimento e gli attributi eseguono il mapping ai membri di tali tipi. Quando si fa riferimento a un tipo CLR in XAML, si ha accesso anche ai membri ereditati di tale tipo.  
  
 Ad esempio, l'esempio seguente è la sintassi <xref:System.Windows.Controls.Button> degli elementi oggetto che <xref:System.Windows.FrameworkElement.Name%2A> crea un'istanza di una nuova istanza della classe e specifica anche un attributo e un valore per tale attributo:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 L'esempio seguente è la sintassi degli elementi oggetto che include anche la sintassi delle proprietà di contenuto XAML. Il testo interno contenuto all'interno <xref:System.Windows.Controls.TextBox> verrà utilizzato <xref:System.Windows.Controls.TextBox.Text%2A>per impostare la proprietà di contenuto XAML, .  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Modelli di contenuto  
 Una classe potrebbe supportare un utilizzo come elemento oggetto XAML in termini di sintassi, ma tale elemento funzionerà correttamente solo in un'applicazione o una pagina quando viene posizionato in una posizione prevista di un modello di contenuto o di una struttura ad albero dell'elemento. Ad esempio, <xref:System.Windows.Controls.MenuItem> un oggetto deve in genere <xref:System.Windows.Controls.Primitives.MenuBase> essere inserito solo come figlio di una classe derivata, ad <xref:System.Windows.Controls.Menu>esempio . I modelli di contenuto per elementi specifici vengono documentati come [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte delle osservazioni nelle pagine delle classi per i controlli e altre classi che possono essere usate come elementi XAML.  
  
<a name="properties_of_object_elements"></a>
## <a name="properties-of-object-elements"></a>Proprietà degli elementi oggetto  
 Le proprietà in XAML vengono impostate da una varietà di sintassi possibili. La sintassi che può essere utilizzata per una determinata proprietà varia in base alle caratteristiche del sistema di tipi sottostanti della proprietà che si sta impostando.  
  
 Impostando i valori delle proprietà, si aggiungono feature o caratteristiche agli oggetti così come esistono nell'oggetto grafico della fase di esecuzione. Lo stato iniziale dell'oggetto creato da un elemento oggetto si basa sul comportamento del costruttore senza parametri. In genere, l'applicazione utilizzerà un elemento diverso da un'istanza completamente predefinita di qualsiasi oggetto specificato.  
  
<a name="attribute_syntax_properties"></a>
## <a name="attribute-syntax-properties"></a>Sintassi per attributi (proprietà)  
 La sintassi degli attributi è la sintassi del markup XAML che imposta un valore per una proprietà dichiarando un attributo su un elemento oggetto esistente. Il nome dell'attributo deve corrispondere al nome del membro CLR della proprietà della classe che supporta l'elemento oggetto pertinente. Il nome dell'attributo è seguito da un operatore di assegnazione (Sezione ). Il valore dell'attributo deve essere una stringa racchiusa tra virgolette.  
  
> [!NOTE]
> È possibile utilizzare le virgolette alternate per inserire una virgoletta letterale all'interno di un attributo. Ad esempio, è possibile utilizzare le virgolette singole come mezzo per dichiarare una stringa che contiene un carattere di virgolette doppie al suo interno. Se si utilizzano virgolette singole o doppie, è necessario utilizzare una coppia corrispondente per aprire e chiudere la stringa del valore dell'attributo. Sono inoltre disponibili sequenze di escape o altre tecniche per aggirare le restrizioni relative ai caratteri imposte da una particolare sintassi XAML. Vedere [Entità carattere XML e XAML.](../../../desktop-wpf/xaml-services/xml-character-entities.md)  
  
 Per essere impostata tramite la sintassi dell'attributo, una proprietà deve essere pubblica e scrivibile. Il valore della proprietà nel sistema di tipi di supporto deve essere un tipo di valore o deve essere un tipo di riferimento di cui può essere creata un'istanza o referenziata da un processore XAML quando si accede al tipo di supporto pertinente.  
  
 Per gli eventi XAML WPFWPF, l'evento a cui viene fatto riferimento come nome dell'attributo deve essere pubblico e disporre di un delegato pubblico.  
  
 La proprietà o l'evento deve essere un membro della classe o della struttura di cui viene creata un'istanza dall'elemento oggetto contenitore.  
  
### <a name="processing-of-attribute-values"></a>Elaborazione dei valori degli attributiProcessing of Attribute Values  
 Il valore stringa contenuto nelle virgolette di apertura e chiusura viene elaborato da un processore XAML. Per le proprietà, il comportamento di elaborazione predefinito è determinato dal tipo della proprietà CLR sottostante.  
  
 Il valore dell'attributo viene compilato da uno dei seguenti elementi, utilizzando questo ordine di elaborazione:  
  
1. Se il processore XAML rileva una parentesi graffa o <xref:System.Windows.Markup.MarkupExtension>un elemento oggetto che deriva da , l'estensione di markup a cui si fa riferimento viene valutata prima anziché elaborare il valore come stringa e l'oggetto restituito dall'estensione di markup viene utilizzato come valore. In molti casi l'oggetto restituito da un'estensione di markup sarà un riferimento a un oggetto esistente o un'espressione che rinvia la valutazione fino alla fase di esecuzione e non è un oggetto appena istanziato.  
  
2. Se la proprietà viene dichiarata <xref:System.ComponentModel.TypeConverter>con un attributo o il tipo <xref:System.ComponentModel.TypeConverter>di valore di tale proprietà viene dichiarato con un attributo , il valore stringa dell'attributo viene inviato al convertitore di tipi come input di conversione e il convertitore restituirà una nuova istanza dell'oggetto.  
  
3. Se non <xref:System.ComponentModel.TypeConverter>è presente alcun , viene tentata una conversione diretta al tipo di proprietà. Questo livello finale è una conversione diretta in corrispondenza del valore nativo del parser tra i tipi primitivi del linguaggio XAML o un controllo per i nomi delle costanti denominate in un'enumerazione (il parser accede quindi ai valori corrispondenti).  
  
#### <a name="enumeration-attribute-values"></a>Valori degli attributi di enumerazione  
 Le enumerazioni in XAML vengono elaborate intrinsecamente dai parser XAML e i membri di un'enumerazione devono essere specificati specificando il nome di stringa di una delle costanti denominate dell'enumerazione.  
  
 Per i valori di enumerazione non flag, il comportamento nativo consiste nell'elaborare la stringa di un valore di attributo e risolverla in uno dei valori di enumerazione. Non si specifica l'enumerazione nel formato *Enumerazione*. *Valore*, come nel codice. Si specifica invece solo *Value*e *Enumeration* viene dedotto dal tipo della proprietà che si sta impostando. Se si specifica un attributo nella finestra *Enumeration*. Modulo di *valore,* non si risolverà correttamente.  
  
 Per le enumerazioni flagwise, il <xref:System.Enum.Parse%2A?displayProperty=nameWithType> comportamento è basato sul metodo . È possibile specificare più valori per un'enumerazione flagwise separando ogni valore con una virgola. Tuttavia, è possibile combinare valori di enumerazione che non sono flagwise. Ad esempio, non è possibile utilizzare la <xref:System.Windows.Trigger> sintassi della virgola per tentare di creare un che agisce su più condizioni di un'enumerazione non flag:For instance, you cannot use the comma syntax to attempt to create a that acts on multiple conditions of a nonflag enumeration:  
  
```xaml  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Le enumerazioni Flagwise che supportano gli attributi impostabili in XAML sono rare in WPFWPF. Tuttavia, una <xref:System.Windows.Media.StyleSimulations>di queste enumerazioni è . È possibile, ad esempio, utilizzare la sintassi dell'attributo flagwise delimitata da virgole per modificare l'esempio fornito nelle osservazioni per la <xref:System.Windows.Documents.Glyphs> classe; `StyleSimulations = "BoldSimulation"` potrebbe `StyleSimulations = "BoldSimulation,ItalicSimulation"`diventare . <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>è un'altra proprietà in cui è possibile specificare più di un valore di enumerazione. Tuttavia, questa proprietà si verifica per <xref:System.Windows.Input.ModifierKeys> essere un caso speciale, perché l'enumerazione supporta il proprio convertitore di tipi. Il convertitore di tipi per i modificatori utilizza un segno più (-) come delimitatore anziché una virgola (,). Questa conversione supporta la sintassi più tradizionale per rappresentare le combinazioni di tasti nella programmazione di Microsoft Windows, ad esempio "Ctrl-Alt".  
  
### <a name="properties-and-event-member-name-references"></a>Proprietà e riferimenti a nomi di membri evento  
 Quando si specifica un attributo, è possibile fare riferimento a qualsiasi proprietà o evento esistente come membro del tipo CLR di cui è stata creata un'istanza per l'elemento oggetto contenitore.  
  
 In alternativa, è possibile fare riferimento a una proprietà associata o a un evento associato, indipendentemente dall'elemento oggetto che lo contiene. Le proprietà associate vengono descritte in una sezione successiva.  
  
 È inoltre possibile assegnare un nome a qualsiasi evento da qualsiasi oggetto accessibile tramite lo spazio dei nomi predefinito utilizzando *typeName*. nome parzialmente qualificato *dell'evento;* questa sintassi supporta l'associazione di gestori per gli eventi indirizzati in cui il gestore è destinato a gestire il routing degli eventi dagli elementi figlio, ma l'elemento padre non dispone anche di tale evento nella relativa tabella dei membri. Questa sintassi è simile a una sintassi dell'evento associato, ma l'evento qui non è un vero evento associato. Si fa invece riferimento a un evento con un nome completo. Per ulteriori informazioni, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 Per alcuni scenari, i nomi delle proprietà vengono talvolta forniti come valore di un attributo, anziché come nome dell'attributo. Tale nome di proprietà può includere anche qualificatori, ad esempio la proprietà specificata nel form *ownerType*. *dependencyPropertyName*. Questo scenario è comune quando si scrivono stili o modelli in XAML. Le regole di elaborazione per i nomi di proprietà fornite come valore di attributo sono diverse e sono regolate dal tipo della proprietà impostata o dai comportamenti di particolari sottosistemi WPFWPF. Per informazioni dettagliate, consultate [Applicazione di stili e modelli.](../../../desktop-wpf/fundamentals/styles-templates-overview.md)  
  
 Un altro utilizzo per i nomi delle proprietà è quando un valore di attributo descrive una relazione proprietà-proprietà. Questa funzionalità viene utilizzata per l'associazione dati <xref:System.Windows.PropertyPath> e per le destinazioni dello storyboard ed è abilitata dalla classe e dal relativo convertitore di tipi. Per una descrizione più completa della semantica di ricerca, vedere [Sintassi XAML PropertyPath](propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>
## <a name="property-element-syntax"></a>Sintassi per gli elementi proprietà  
 *La sintassi* degli elementi proprietà è una sintassi che differisce in qualche modo dalle regole di sintassi XML di base per gli elementi. In XML, il valore di un attributo è una stringa de facto, con l'unica variazione possibile da quale formato di codifica stringa viene utilizzato. In XAML, è possibile assegnare altri elementi oggetto come valore di una proprietà. Questa funzionalità è abilitata dalla sintassi degli elementi proprietà. Anziché essere specificata come attributo all'interno del tag dell'elemento, la proprietà viene specificata utilizzando un tag di elemento di apertura in *elementTypeName*. *propertyName,* il valore della proprietà viene specificato all'interno e quindi l'elemento proprietà viene chiuso.  
  
 In particolare, la sintassi inizia\<con una parentesi angolare sinistra ( ), seguita immediatamente dal nome del tipo della classe o della struttura in cui è contenuta la sintassi dell'elemento proprietà. Questo è seguito immediatamente da un singolo punto (.), quindi dal nome di una proprietà, quindi da una parentesi angolare destra (>). Come per la sintassi dell'attributo, tale proprietà deve esistere all'interno dei membri pubblici dichiarati del tipo specificato. Il valore da assegnare alla proprietà è contenuto all'interno dell'elemento proprietà. In genere, il valore viene fornito come uno o più elementi oggetto, perché la specifica di oggetti come valori è lo scenario a cui la sintassi degli elementi proprietà deve essere indirizzata. Infine, un tag di chiusura equivalente che specifica lo stesso *elementTypeName*. È necessario fornire la combinazione *propertyName,* in modo corretto annidamento ed equilibrio con altri tag di elemento.  
  
 Di seguito è riportata, ad <xref:System.Windows.FrameworkElement.ContextMenu%2A> esempio, <xref:System.Windows.Controls.Button>la sintassi degli elementi proprietà per la proprietà di un oggetto .  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 Il valore all'interno di un elemento proprietà può essere specificato anche come testo interno, <xref:System.String>nei casi in cui il tipo di proprietà specificato è un tipo di valore primitivo, ad esempio , o un'enumerazione in cui viene specificato un nome. Questi due utilizzi sono in qualche modo rari, perché ognuno di questi casi potrebbe anche usare una sintassi degli attributi più semplice. Uno scenario per il riempimento di un elemento proprietà con una stringa è per le proprietà che non sono la proprietà di contenuto XAML ma vengono comunque utilizzate per la rappresentazione del testo dell'interfaccia utente e particolari elementi di spazio vuoto, ad esempio gli avanzamenti riga, devono essere visualizzati nel testo dell'interfaccia utente. La sintassi degli attributi non può mantenere gli avanzamenti riga, ma la sintassi degli elementi proprietà può, purché sia attiva una conservazione significativa degli spazi vuoti (per informazioni dettagliate, vedere [Elaborazione degli spazi vuoti in XAML).](../../../desktop-wpf/xaml-services/white-space-processing.md) Un altro scenario è in modo che [x:Uid direttiva](../../../desktop-wpf/xaml-services/xuid-directive.md) può essere applicata all'elemento proprietà e quindi contrassegnare il valore all'interno come un valore che deve essere localizzato nel BAML di output WPFWPF o da altre tecniche.  
  
 Un elemento proprietà non è rappresentato nell'albero logico WPFWPF. Un elemento proprietà è solo una sintassi specifica per l'impostazione di una proprietà e non è un elemento che dispone di un'istanza o di un oggetto che lo esegue. Per informazioni dettagliate sul concetto di albero logico, vedere [Strutture ad albero in WPF.](trees-in-wpf.md)  
  
 Per le proprietà in cui sono supportate sia la sintassi degli attributi che quelli degli elementi proprietà, le due sintassi hanno in genere lo stesso risultato, anche se le sottigliezze, ad esempio la gestione degli spazi vuoti, possono variare leggermente tra le sintassi.  
  
<a name="collection_syntax"></a>
## <a name="collection-syntax"></a>Sintassi per raccolte  
 La specifica XAML richiede implementazioni del processore XAML per identificare le proprietà in cui il tipo di valore è una raccolta. L'implementazione generale del processore XAML in .NET è basata sul codice gestito e CLR e identifica i tipi di raccolta tramite uno degli elementi seguenti:  
  
- Tipo <xref:System.Collections.IList>implementa .  
  
- Tipo <xref:System.Collections.IDictionary>implementa .  
  
- Il tipo <xref:System.Array> deriva da (per ulteriori informazioni sulle matrici in XAML, vedere [x:Array Markup Extension](../../../desktop-wpf/xaml-services/xarray-markup-extension.md).)  
  
 Se il tipo di una proprietà è una raccolta, non è necessario specificare il tipo di raccolta dedotta nel markup come elemento oggetto. Al contrario, gli elementi che devono diventare gli elementi nella raccolta vengono specificati come uno o più elementi figlio dell'elemento proprietà. Ogni elemento di questo tipo viene valutato a un `Add` oggetto durante il caricamento e aggiunto alla raccolta chiamando il metodo della raccolta implicita. Ad esempio, <xref:System.Windows.Style.Triggers%2A> la <xref:System.Windows.Style> proprietà di <xref:System.Windows.TriggerCollection>accetta il <xref:System.Collections.IList>tipo di insieme specializzato , che implementa . Non è necessario creare <xref:System.Windows.TriggerCollection> un'istanza di un elemento oggetto nel markup. È invece necessario <xref:System.Windows.Trigger> specificare uno `Style.Triggers` o più <xref:System.Windows.Trigger> elementi come elementi all'interno dell'elemento proprietà, dove (o <xref:System.Windows.TriggerCollection>una classe derivata) è il tipo previsto come tipo di elemento per l'elemento fortemente tipizzato e implicito.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Una proprietà può essere sia un tipo di raccolta che la proprietà di contenuto XAML per il tipo e i tipi derivati, come descritto nella sezione successiva di questo argomento.  
  
 Un elemento di raccolta implicito crea un membro nella rappresentazione dell'albero logico, anche se non viene visualizzato nel markup come elemento. In genere il costruttore del tipo padre esegue la creazione di istanze per la raccolta che è una delle relative proprietà e la raccolta inizialmente vuota diventa parte della struttura ad albero di oggetti.  
  
> [!NOTE]
> Le interfacce di elenco<xref:System.Collections.Generic.IList%601> <xref:System.Collections.Generic.IDictionary%602>e dizionario generiche ( e ) non sono supportate per il rilevamento delle raccolte. Tuttavia, è <xref:System.Collections.Generic.List%601> possibile usare la classe come <xref:System.Collections.IList> classe <xref:System.Collections.Generic.Dictionary%602> base, perché implementa direttamente <xref:System.Collections.IDictionary> o come classe base, perché implementa direttamente.  
  
 Nelle pagine di riferimento .NET per i tipi di raccolta, questa sintassi con l'omissione intenzionale dell'elemento oggetto per una raccolta è occasionalmente indicata nelle sezioni della sintassi XAML come Sintassi di raccolta implicita.  
  
 Ad eccezione dell'elemento radice, ogni elemento oggetto in un file XAML annidato come elemento figlio di un altro elemento è in realtà un elemento che è uno o entrambi i casi seguenti: un membro di una proprietà di raccolta implicita del relativo elemento padre o un elemento che specifica il valore della proprietà di contenuto XAML per l'elemento padre (le proprietà di contenuto XAML verranno illustrate in una sezione successiva). In altre parole, la relazione degli elementi padre e degli elementi figlio in una pagina di markup è in realtà un singolo oggetto alla radice e ogni elemento oggetto sotto la radice è una singola istanza che fornisce un valore di proprietà dell'elemento padre o uno degli elementi all'interno di una raccolta che è anche un valore della proprietà di tipo raccolta dell'elemento padre. Questo concetto a radice singola è comune con XML ed è spesso rafforzato <xref:System.Windows.Markup.XamlReader.Load%2A>nel comportamento delle API che caricano XAML, ad esempio .  
  
 L'esempio seguente è una sintassi con<xref:System.Windows.Media.GradientStopCollection>l'elemento oggetto per un insieme ( ) specificato in modo esplicito.  
  
```xaml  
<LinearGradientBrush>  
  <LinearGradientBrush.GradientStops>  
    <GradientStopCollection>  
      <GradientStop Offset="0.0" Color="Red" />  
      <GradientStop Offset="1.0" Color="Blue" />  
    </GradientStopCollection>  
  </LinearGradientBrush.GradientStops>  
</LinearGradientBrush>  
```  
  
 Si noti che non è sempre possibile dichiarare in modo esplicito la raccolta. Ad esempio, il <xref:System.Windows.TriggerCollection> tentativo di dichiarare <xref:System.Windows.Style.Triggers%2A> in modo esplicito nell'esempio illustrato in precedenza avrebbe esito negativo. La dichiarazione esplicita dell'insieme richiede che la <xref:System.Windows.TriggerCollection> classe di raccolta supporti un costruttore senza parametri e non disponga di un costruttore senza parametri.  
  
<a name="xaml_content_properties"></a>
## <a name="xaml-content-properties"></a>Proprietà di contenuto XAML  
 La sintassi del contenuto XAML è una <xref:System.Windows.Markup.ContentPropertyAttribute> sintassi abilitata solo nelle classi che specificano la classe come parte della relativa dichiarazione di classe. Il <xref:System.Windows.Markup.ContentPropertyAttribute> riferimento al nome della proprietà che è la proprietà di contenuto per quel tipo di elemento (incluse le classi derivate). Quando vengono elaborati da un processore XAML, tutti gli elementi figlio o il testo interno che si trovano tra i tag di apertura e chiusura dell'elemento oggetto verranno assegnati come valore della proprietà di contenuto XAML per tale oggetto. È possibile specificare elementi di proprietà espliciti per la proprietà di contenuto, ma questo utilizzo non viene in genere illustrato nelle sezioni della sintassi XAML nel riferimento .NET. La tecnica explicit/verbose ha un valore occasionale per la chiarezza del markup o per una questione di stile di markup, ma in genere lo scopo di una proprietà di contenuto è semplificare il markup in modo che gli elementi che sono intuitivamente correlati come padre-figlio possono essere annidati direttamente. I tag degli elementi proprietà per altre proprietà in un elemento non vengono assegnati come "contenuto" in base a una definizione di linguaggio XAML rigorosa; vengono elaborati in precedenza nell'ordine di elaborazione del parser XAML e non sono considerati "contenuto".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>XAML Content Property Values Must Be Contiguous  
 Il valore di una proprietà di contenuto XAML deve essere specificato interamente prima o interamente dopo qualsiasi altro elemento proprietà in tale elemento oggetto. Questo è vero se il valore di una proprietà di contenuto XAML è specificato come stringa o come uno o più oggetti. Ad esempio, il markup seguente non analizza:For example, the following markup does not parse:  
  
```xaml  
<Button>I am a
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Ciò non è illegale essenzialmente perché se questa sintassi fosse resa esplicita utilizzando la sintassi degli elementi proprietà per la proprietà content, la proprietà content verrebbe impostata due volte:  
  
```xaml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Un esempio simile non valido è se la proprietà content è una raccolta e gli elementi figlio sono intervallati da elementi proprietà:A similarly illegal example is if the content property is a collection, and child elements are interspersed with property elements:  
  
```xaml  
<StackPanel>  
  <Button>This example</Button>  
  <StackPanel.Resources>  
    <SolidColorBrush x:Key="BlueBrush" Color="Blue"/>  
  </StackPanel.Resources>  
  <Button>... is illegal XAML</Button>  
</StackPanel>  
```  
  
<a name="content_properties_and_collection_syntax_combined"></a>
## <a name="content-properties-and-collection-syntax-combined"></a>Combinazione di proprietà di contenuto e sintassi per raccolte  
 Per accettare più di un singolo elemento oggetto come contenuto, il tipo della proprietà di contenuto deve essere in modo specifico un tipo di raccolta. Analogamente alla sintassi degli elementi proprietà per i tipi di raccolta, un processore XAML deve identificare i tipi che sono tipi di raccolta. Se un elemento ha una proprietà di contenuto XAML e il tipo della proprietà di contenuto XAML è una raccolta, non è necessario specificare il tipo di raccolta implicita nel markup come elemento oggetto e la proprietà di contenuto XAML non deve essere specificata come elemento proprietà. Pertanto, il modello di contenuto apparente nel markup può ora avere più di un elemento figlio assegnato come contenuto. Di seguito è riportata la sintassi del contenuto per una <xref:System.Windows.Controls.Panel> classe derivata. Tutte <xref:System.Windows.Controls.Panel> le classi derivate stabiliscono che la proprietà di contenuto XAML è <xref:System.Windows.Controls.Panel.Children%2A>, che richiede un valore di tipo <xref:System.Windows.Controls.UIElementCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Si noti che <xref:System.Windows.Controls.Panel.Children%2A> né l'elemento <xref:System.Windows.Controls.UIElementCollection> proprietà per né l'elemento per è obbligatorio nel markup. Si tratta di una funzionalità di progettazione di XAML [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in modo che gli elementi concontenuti in modo ricorsivo che definiscono un sono rappresentati in modo più intuitivo come una struttura ad albero di elementi annidati con relazioni immediate degli elementi padre-figlio, senza intervenire i tag degli elementi proprietà o gli oggetti raccolta. Infatti, <xref:System.Windows.Controls.UIElementCollection> non può essere specificato in modo esplicito nel markup come elemento oggetto, in base alla progettazione. Poiché l'unico utilizzo previsto <xref:System.Windows.Controls.UIElementCollection> è come una raccolta implicita, non espone un costruttore pubblico senza parametri e pertanto non è possibile creare un'istanza come elemento oggetto.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Combinazione di elementi di proprietà ed elementi oggetto in un oggetto con una proprietà di contenutoMixing Property Elements and Object Elements in an Object with a Content Property  
 La specifica XAML dichiara che un processore XAML può imporre che gli elementi oggetto utilizzati per riempire la proprietà di contenuto XAML all'interno di un elemento oggetto devono essere contigui e non devono essere combinati. Questa restrizione sulla combinazione di elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di proprietà e contenuto viene applicata dai processori XAML.  
  
 È possibile avere un elemento oggetto figlio come primo markup immediato all'interno di un elemento oggetto. È quindi possibile introdurre elementi di proprietà. In alternativa, è possibile specificare uno o più elementi proprietà, quindi il contenuto e altri elementi di proprietà. Tuttavia, una volta che un elemento proprietà segue il contenuto, non è possibile introdurre altro contenuto, è possibile aggiungere solo elementi proprietà.  
  
 Questo requisito di ordine dell'elemento contenuto/proprietà non si applica al testo interno utilizzato come contenuto. Tuttavia, è ancora un buon stile di markup per mantenere il testo interno contiguo, perché uno spazio vuoto significativo sarà difficile da rilevare visivamente nel markup se gli elementi della proprietà sono intervallati da testo interno.  
  
<a name="xaml_namespaces"></a>
## <a name="xaml-namespaces"></a>Spazi dei nomi XAML  
 Nessuno degli esempi di sintassi precedenti ha specificato uno spazio dei nomi XAML diverso dallo spazio dei nomi XAML predefinito. Nelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni tipiche, lo spazio dei [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nomi XAML predefinito viene specificato come spazio dei nomi. È possibile specificare spazi dei nomi XAML diversi dallo spazio dei nomi XAML predefinito e utilizzare comunque una sintassi simile. Tuttavia, in qualsiasi punto in cui viene denominata una classe che non è accessibile all'interno dello spazio dei nomi XAML predefinito, tale nome di classe deve essere preceduto dal prefisso dello spazio dei nomi XAML come mappato allo spazio dei nomi CLR corrispondente. Ad esempio, `<custom:Example/>` è la sintassi degli `Example` elementi oggetto per creare un'istanza della classe, in cui lo spazio dei `custom` nomi CLR contenente tale classe (ed eventualmente le informazioni sull'assembly esterno che contiene i tipi di supporto) è stato precedentemente mappato al prefisso.  
  
 Per altre informazioni sugli spazi dei nomi XAML, vedere [Spazi dei nomi XAML e Mapping degli spazi dei nomi per XAML WPF.](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)  
  
<a name="markup_extensions"></a>
## <a name="markup-extensions"></a>Estensioni di markup  
 XAML definisce un'entità di programmazione dell'estensione di markup che consente un escape dalla normale gestione del processore XAML di valori di attributo stringa o elementi oggetto e rinvia l'elaborazione a una classe di backup. Il carattere che identifica un'estensione di markup per un processore XAML quando si usa la sintassi degli attributi è la parentesi graffa di apertura, seguita da qualsiasi carattere diverso da una parentesi graffa di chiusura ('). La prima stringa che segue la parentesi graffa di apertura deve fare riferimento alla classe che fornisce il particolare comportamento di estensione, in cui il riferimento può omettere la sottostringa "Extension" se tale sottostringa fa parte del nome della classe true. Successivamente, può essere visualizzato un singolo spazio e quindi ogni carattere successivo viene utilizzato come input dall'implementazione dell'estensione, fino a quando non viene rilevata la parentesi graffa di chiusura.  
  
 L'implementazione XAML <xref:System.Windows.Markup.MarkupExtension> di .NET usa la classe astratta [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] come base per tutte le estensioni di markup supportate da oltre ad altri framework o tecnologie. Le estensioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] di markup che implementa in modo specifico sono spesso destinate a fornire un mezzo per fare riferimento ad altri oggetti esistenti o per creare riferimenti posticipati a oggetti che verranno valutati in fase di esecuzione. Ad esempio, un'associazione dati WPF semplice `{Binding}` viene eseguita specificando l'estensione di markup al posto del valore che una determinata proprietà normalmente richiederebbe. Molte delle estensioni di markup WPFWPF consentono una sintassi degli attributi per le proprietà in cui una sintassi degli attributi non sarebbe altrimenti possibile. Ad esempio, <xref:System.Windows.Style> un oggetto è un tipo relativamente complesso che contiene una serie annidata di oggetti e proprietà. Gli stili in WPFWPF vengono <xref:System.Windows.ResourceDictionary>in genere definiti come una risorsa in un oggetto , quindi su cui viene fatto riferimento tramite una delle due estensioni di markup WPFWPF che richiedono una risorsa. L'estensione di markup rinvia la valutazione del valore della proprietà <xref:System.Windows.FrameworkElement.Style%2A> a una <xref:System.Windows.Style>ricerca di risorse e consente di fornire il valore della proprietà, prendendo tipo , nella sintassi degli attributi come nell'esempio seguente:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 In `StaticResource` questo <xref:System.Windows.StaticResourceExtension> caso, identifica la classe che fornisce l'implementazione dell'estensione di markup. La stringa `MyStyle` successiva viene utilizzata come input <xref:System.Windows.StaticResourceExtension> per il costruttore non predefinito, in <xref:System.Windows.ResourceKey>cui il parametro derivato dalla stringa di estensione dichiara l'oggetto richiesto. `MyStyle`è previsto che sia il valore <xref:System.Windows.Style> [x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) di un oggetto definito come risorsa. L'utilizzo [dell'estensione di markup StaticResource](staticresource-markup-extension.md) <xref:System.Windows.Style> richiede che la risorsa venga utilizzata per fornire il valore della proprietà tramite la logica di ricerca di risorse statiche in fase di caricamento.  
  
 Per altre informazioni sulle estensioni di markup, vedere [Estensioni di markup e WPF XAML](markup-extensions-and-wpf-xaml.md). Per un riferimento alle estensioni di markup e ad altre funzionalità di programmazione XAML abilitate nell'implementazione XAML generale di .NET, vedere [Spazio dei nomi XAML (x:) Caratteristiche del linguaggio](../../../desktop-wpf/xaml-services/namespace-language-features.md). Per le estensioni di markup specifiche di WPF, consultate [Estensioni XAML WPF.](wpf-xaml-extensions.md)  
  
<a name="attached_properties"></a>
## <a name="attached-properties"></a>Proprietà associate  
 Le proprietà associate sono un concetto di programmazione introdotto in XAML in cui le proprietà possono essere di proprietà e definite da un particolare tipo, ma impostate come attributi o elementi proprietà in qualsiasi elemento. Lo scenario principale a cui sono destinate le proprietà associate è consentire agli elementi figlio in una struttura di markup di riportare le informazioni a un elemento padre senza richiedere un modello a oggetti ampiamente condiviso tra tutti gli elementi. Al contrario, le proprietà associate possono essere utilizzate dagli elementi padre per riportare le informazioni agli elementi figlio. Per ulteriori informazioni sullo scopo delle proprietà associate e su come creare proprietà associate personalizzate, vedere [Cenni preliminari](attached-properties-overview.md)sulle proprietà associate .  
  
 Le proprietà associate utilizzano una sintassi che assomiglia superficialmente alla sintassi degli elementi proprietà, in quanto si specifica anche un *typeName*. combinazione *propertyName.* Vi sono due differenze importanti:  
  
- È possibile utilizzare il *typeName*. *combinazione propertyName* anche quando si imposta una proprietà associata tramite la sintassi degli attributi. Le proprietà associate sono l'unico caso in cui la qualifica del nome della proprietà è un requisito in una sintassi degli attributi.  
  
- È inoltre possibile utilizzare la sintassi degli elementi proprietà per le proprietà associate. Tuttavia, per la sintassi tipica degli elementi proprietà, il *typeName* specificato è l'elemento oggetto che contiene l'elemento proprietà. Se si fa riferimento a una proprietà associata, *typeName* è la classe che definisce la proprietà associata, non l'elemento oggetto contenitore.  
  
<a name="attached_events"></a>
## <a name="attached-events"></a>Eventi associati  
 Gli eventi associati sono un altro concetto di programmazione introdotto in XAML in cui gli eventi possono essere definiti da un tipo specifico, ma i gestori possono essere associati a qualsiasi elemento oggetto. Nell'implementazione WOF, spesso il tipo che definisce un evento associato è un tipo statico che definisce un servizio e talvolta tali eventi associati vengono esposti da un alias di evento indirizzato nei tipi che espongono il servizio. I gestori per gli eventi associati vengono specificati tramite la sintassi degli attributi. Come per gli eventi associati, la sintassi degli attributi viene espansa per gli eventi associati per consentire un *typeName*. *eventName* usage, dove *typeName* è `Add` `Remove` la classe che fornisce e le funzioni di accesso del gestore eventi per l'infrastruttura dell'evento associato e *eventName* è il nome dell'evento.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomia di un elemento radice XAMLAnatomy of a XAML Root Element  
 Nella tabella seguente viene illustrato un tipico elemento radice XAML suddiviso, che mostra gli attributi specifici di un elemento radice:The following table shows a typical XAML root element broken down, showing the specific attributes of a root element:  
  
|||  
|-|-|  
|`<Page`|Apertura dell'elemento object dell'elemento radice|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|Spazio dei[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]nomi XAML predefinito ( )|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|Spazio dei nomi XAML del linguaggio XAML|  
|`x:Class="ExampleNamespace.ExampleCode"`|Dichiarazione di classe parziale che connette il markup a qualsiasi code-behind definito per la classe parziale|  
|`>`|Fine dell'elemento oggetto per la radice. L'oggetto non è ancora chiuso perché l'elemento contiene elementi figlio|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>
## <a name="optional-and-nonrecommended-xaml-usages"></a>Utilizzo XAML facoltativo e non consigliatoOptional and Nonrecommended XAML Usages  
 Le sezioni seguenti descrivono gli utilizzi XAML tecnicamente supportati dai processori XAML, ma che producono dettaglio o altri problemi estetici che interferiscono con i file XAML che rimangono leggibili quando si sviluppano applicazioni che contengono origini XAML.  
  
### <a name="optional-property-element-usages"></a>Utilizzo facoltativo degli elementi proprietàOptional Property Element Usages  
 Gli utilizzi facoltativi degli elementi proprietà includono la scrittura esplicita delle proprietà di contenuto dell'elemento considerate implicite dal processore XAML. Ad esempio, quando si dichiara <xref:System.Windows.Controls.Menu>il contenuto di un <xref:System.Windows.Controls.ItemsControl.Items%2A> oggetto <xref:System.Windows.Controls.Menu> , `<Menu.Items>` è possibile scegliere di <xref:System.Windows.Controls.MenuItem> dichiarare in modo esplicito l'insieme di come tag dell'elemento proprietà e di inserirla `<Menu.Items>`all'interno di , anziché utilizzare il comportamento implicito del processore XAML che tutti gli elementi figlio di un <xref:System.Windows.Controls.Menu> oggetto devono essere a <xref:System.Windows.Controls.MenuItem> e vengono inseriti nell'insieme. <xref:System.Windows.Controls.ItemsControl.Items%2A> A volte gli utilizzi facoltativi consentono di chiarire visivamente la struttura dell'oggetto rappresentata nel markup. O a volte l'utilizzo esplicito di un elemento proprietà può evitare markup tecnicamente funzionale ma visivamente confuso, ad esempio le estensioni di markup annidate all'interno di un valore di attributo.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Attributi qualificati typeName.memberName completi  
 Il *typeName*. *memberName* per un attributo funziona in realtà in modo più universale rispetto al caso dell'evento indirizzato. Ma in altre situazioni che formano è superfluo e si dovrebbe evitare, se non altro per motivi di stile di markup e leggibilità. Nell'esempio seguente, ognuno dei <xref:System.Windows.Controls.Control.Background%2A> tre riferimenti all'attributo è completamente equivalente:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`funziona perché la ricerca qualificata per tale proprietà <xref:System.Windows.Controls.Button> ha esito positivo (è<xref:System.Windows.Controls.Control.Background%2A> stato ereditato da Control) ed <xref:System.Windows.Controls.Button> è la classe dell'elemento oggetto o una classe base. `Control.Background`funziona perché <xref:System.Windows.Controls.Control> la classe <xref:System.Windows.Controls.Control.Background%2A> <xref:System.Windows.Controls.Control> definisce <xref:System.Windows.Controls.Button> effettivamente ed è una classe base.  
  
 Tuttavia, il seguente *typeName*. L'esempio del modulo *nomemembro* non funziona e viene quindi visualizzato commentato:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>è un'altra <xref:System.Windows.Controls.Control>classe derivata `Label.Background` di <xref:System.Windows.Controls.Label> , e se si fosse specificato all'interno di un elemento oggetto, questo utilizzo avrebbe funzionato. Tuttavia, <xref:System.Windows.Controls.Label> poiché non è <xref:System.Windows.Controls.Button>la classe o la classe `Label.Background` base di , il comportamento del processore XAML specificato consiste nel elaborare come proprietà associata. `Label.Background`non è una proprietà associata disponibile e questo utilizzo non riesce.  
  
### <a name="basetypenamemembername-property-elements"></a>Elementi di proprietà baseTypeName.memberName  
 In modo analogo al modo in cui *typeName*. *memberName* funziona per la sintassi degli attributi, un *baseTypeName*. La sintassi *di nomemembro* funziona per la sintassi degli elementi proprietà. Ad esempio, la sintassi seguente funziona:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 In questo caso, l'elemento proprietà è stato fornito come `Control.Background` anche se l'elemento proprietà era contenuto in `Button`.  
  
 Ma proprio come *typeName*. *memberName* per gli attributi, *baseTypeName*. *memberName* è di stile scadente nel markup ed è consigliabile evitarlo.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Spazio dei nomi XAML (x:) Funzionalità del linguaggio](../../../desktop-wpf/xaml-services/namespace-language-features.md)
- [Estensioni XAML WPF](wpf-xaml-extensions.md)
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [TypeConverter e XAML](typeconverters-and-xaml.md)
- [Classi XAML e personalizzate per WPF](xaml-and-custom-classes-for-wpf.md)
