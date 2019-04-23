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
ms.openlocfilehash: bf4118c6e811f409715b7b6684851b8b3e8bbb25
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298890"
---
# <a name="xaml-syntax-in-detail"></a>Descrizione dettagliata della sintassi XAML
In questo argomento definisce le condizioni che vengono usate per descrivere gli elementi della sintassi XAML. Questi termini vengono utilizzati spesso in tutto il resto della presente documentazione, sia per la documentazione di WPF in modo specifico e per gli altri modelli che usano XAML o i concetti di base XAML abilitati per il supporto del linguaggio XAML a livello di System. Xaml. In questo argomento consente di espandere la terminologia di base introdotta nell'argomento [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md).  

<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>La specifica del linguaggio XAML  
 La terminologia di sintassi XAML definita in questa sezione viene inoltre definita o fare riferimento all'interno di specifiche del linguaggio XAML. XAML è un linguaggio basato su XML e segue o si espande sulla regole strutturali XML. Alcuni termini è una condivisione o è basato su termini comunemente utilizzati che descrive il linguaggio XML o un modello a oggetti documento XML.  
  
 Per altre informazioni sulle specifiche del linguaggio XAML, scaricare [ \[MS-XAML\] ](https://go.microsoft.com/fwlink/?LinkId=114525) dal Microsoft Download Center.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>XAML e CLR  
 XAML è un linguaggio di markup. Il [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], come suggerito dal nome, consente l'esecuzione del runtime. XAML non è da solo uno dei linguaggi comuni che è utilizzata direttamente dal runtime CLR. In alternativa, è possibile pensare XAML come il proprio sistema di tipi di supporto. Il sistema di analisi XAML specifico usato da WPF si basa su CLR e il sistema di tipi CLR. Vengono eseguito il mapping di tipi XAML per tipi CLR per creare un'istanza di una rappresentazione di runtime quando viene analizzato il XAML per WPF. Per questo motivo, il resto della descrizione della sintassi in questo documento include riferimenti al sistema di tipi CLR, anche se non lo sono le discussioni sintassi equivalente della specifica del linguaggio XAML. (Per ogni livello di specifica del linguaggio XAML, i tipi XAML è stato possibile eseguire il mapping a qualsiasi altro sistema di tipi, che non deve essere il CLR, ma che richiedono la creazione e l'uso di un parser XAML.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Membri di tipi e l'ereditarietà di classe  
 Proprietà e gli eventi man mano che vengono visualizzate come membri XAML di un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipo spesso vengono ereditate dai tipi di base. In questo esempio si consideri ad esempio: `<Button Background="Blue" .../>`. Il <xref:System.Windows.Controls.Control.Background%2A> proprietà non è una proprietà dichiarata immediatamente per il <xref:System.Windows.Controls.Button> classe, se si intende esaminare la definizione di classe, i risultati di reflection o la documentazione. Al contrario, <xref:System.Windows.Controls.Control.Background%2A> viene ereditato dalla base <xref:System.Windows.Controls.Control> classe.  
  
 Il comportamento dell'ereditarietà di classe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementi XAML è un'importante variazione da un'interpretazione a livello di schema del markup XML. Ereditarietà delle classi può diventare complessa, in particolare quando intermedie classi base sono astratte o quando sono coinvolte le interfacce. Questo è il motivo che il set di elementi XAML e dei relativi attributi consentiti è difficile rappresentare in modo accurato e completo con i tipi di schema che viene generalmente utilizzato per [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] programmazione, ad esempio formato XSD o DTD. Un altro motivo è che estendibilità e funzionalità di mapping dei tipi del linguaggio XAML preclude completezza di qualsiasi rappresentazione predefinito dei tipi consentiti e i membri.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>Sintassi degli elementi oggetto  
 *La sintassi dell'elemento dell'oggetto* è la sintassi di markup XAML che crea un'istanza di una classe CLR o una struttura con la dichiarazione di un elemento XML. Questa sintassi è simile alla sintassi degli elementi di altri linguaggi di markup, ad esempio HTML. Sintassi degli elementi oggetto inizia con una parentesi uncinata (\<), seguito immediatamente dal nome del tipo della classe o struttura viene creata un'istanza. Zero o più spazi possono seguire il nome del tipo, e zero o più attributi possono anche essere dichiarati nell'elemento oggetto, con uno o più spazi, separare ogni nome di attributo = coppia di "value". Infine, uno dei seguenti deve essere true:  
  
-   L'elemento e il tag deve essere chiuso da una barra (/) seguita immediatamente da una parentesi uncinata chiusa (>).  
  
-   Il tag di apertura deve essere completato da una parentesi uncinata chiusa (>). Altri elementi oggetto, proprietà o il testo interno, è possibile seguire il tag di apertura. Esattamente quali contenuti possono essere contenuti in questo caso è solitamente limitato dal modello a oggetti dell'elemento. L'equivalente di tag di chiusura per l'elemento oggetto deve inoltre esistere, in una nidificazione appropriata e bilanciato con altre coppie di tag di apertura e chiusura.  
  
 XAML come implementato dalla .NET ha un set di regole che eseguono il mapping di elementi oggetto nei tipi, gli attributi di proprietà o eventi e gli spazi dei nomi XAML per gli spazi dei nomi CLR e assembly. Per WPF e .NET Framework, eseguire il mapping di elementi oggetto XAML a [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] tipi come definito nell'assembly di riferimento e gli attributi vengono mappati ai membri di tali tipi. Quando si fa riferimento a un tipo CLR in XAML, si ha accesso ai membri ereditati di anche quel tipo.  
  
 Ad esempio, l'esempio seguente è la sintassi degli elementi oggetto che crea una nuova istanza del <xref:System.Windows.Controls.Button> classe e viene inoltre un <xref:System.Windows.FrameworkElement.Name%2A> attributo e un valore per l'attributo:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 L'esempio seguente è una sintassi dell'elemento oggetto che include anche la sintassi di proprietà di contenuto XAML. Il testo interno contenuto da utilizzare per impostare il <xref:System.Windows.Controls.TextBox> proprietà di contenuto XAML, <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Modelli di contenuto  
 Una classe può supportare un utilizzo come elemento oggetto XAML in termini di sintassi, ma quell'elemento funzionano correttamente in un'applicazione o una pagina solo quando è inserito in una posizione prevista di un albero del modello o un elemento contenuto globale. Ad esempio, un <xref:System.Windows.Controls.MenuItem> in genere deve solo essere inserito come figlio di un <xref:System.Windows.Controls.Primitives.MenuBase> classe derivata, ad esempio <xref:System.Windows.Controls.Menu>. Modelli per elementi specifici sono documentati come parte delle note nelle pagine delle classi per i controlli e altri contenuti [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] classi che possono essere utilizzate come elementi XAML.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>Proprietà degli elementi oggetto  
 Proprietà in XAML vengono impostate da un'ampia gamma di possibili sintassi. La sintassi può essere utilizzata per una particolare proprietà varia basata sulle caratteristiche di sistema tipo sottostante della proprietà da impostare.  
  
 Impostando i valori delle proprietà, si aggiungere caratteristiche o funzionalità agli oggetti in cui si trovano nel grafico di oggetti della fase di esecuzione. Lo stato iniziale dell'oggetto creato da un elemento oggetto basa il comportamento del costruttore predefinito. In genere, l'applicazione userà un valore diverso da un'istanza completamente predefinita di un determinato oggetto.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>Sintassi per attributi (proprietà)  
 Sintassi di attributo è la sintassi di markup XAML che imposta un valore per una proprietà con la dichiarazione di un attributo in un elemento oggetto esistente. Il nome dell'attributo deve corrispondere al nome di membro CLR della proprietà della classe che supporta l'elemento oggetto pertinente. Il nome dell'attributo è seguito da un operatore di assegnazione (=). Il valore dell'attributo deve essere una stringa racchiusa tra virgolette.  
  
> [!NOTE]
>  È possibile usare le virgolette alternative per inserire un valore letterale virgolette all'interno di un attributo. Ad esempio è possibile utilizzare le virgolette singole come mezzo per dichiarare una stringa che contiene un carattere di virgoletta doppia all'interno di esso. Se si usano virgolette singole o doppie, è necessario utilizzare una coppia corrispondente per l'apertura e chiusura di stringa del valore di attributo. Sono disponibili anche le sequenze di escape o altre tecniche per risolvere restrizioni dei caratteri imposto da qualsiasi particolare sintassi XAML. Visualizzare [entità carattere XML e XAML](../../xaml-services/xml-character-entities-and-xaml.md).  
  
 Per poter essere impostato tramite la sintassi di attributo, una proprietà deve essere pubblica e deve essere scrivibile. Il valore della proprietà nel sistema di tipi di backup deve essere un tipo di valore o deve essere un tipo di riferimento che può essere creata un'istanza o fatto riferimento da un processore XAML quando si accede al relativo tipo di supporto.  
  
 Per gli eventi XAML WPF, l'evento che viene fatto riferimento come il nome dell'attributo deve essere pubblica e dispone di un delegato pubblico.  
  
 La proprietà o evento deve essere un membro della classe o struttura che crea un'istanza dell'elemento oggetto contenitore.  
  
### <a name="processing-of-attribute-values"></a>Elaborazione dei valori di attributo  
 Il valore stringa contenuto all'interno delle parentesi e virgolette di chiusura viene elaborato da un processore XAML. Per le proprietà, il comportamento di elaborazione predefinito è determinato dal tipo della proprietà CLR sottostante.  
  
 Il valore dell'attributo viene inserito uno dei seguenti, utilizzando questo ordine di elaborazione:  
  
1. Se il processore XAML rileva una parentesi graffa o un elemento oggetto che deriva da <xref:System.Windows.Markup.MarkupExtension>, quindi l'estensione di markup di cui viene fatto riferimento viene valutato per primo anziché il valore sotto forma di stringa di elaborazione e l'oggetto restituito dall'estensione di markup viene utilizzato come il valore. In molti casi l'oggetto restituito da un'estensione di markup sarà un riferimento a un oggetto esistente, o un'espressione che rinvia la valutazione fino alla fase di esecuzione, non è un oggetto appena creata un'istanza.  
  
2. Se la proprietà è dichiarata con un oggetto con attributi <xref:System.ComponentModel.TypeConverter>, o il tipo di valore di tale proprietà viene dichiarato con un oggetto con attributi <xref:System.ComponentModel.TypeConverter>, il valore di stringa dell'attributo viene inviato al convertitore di tipi come input una conversione e il convertitore restituirà un nuova istanza dell'oggetto.  
  
3. Se è presente alcun <xref:System.ComponentModel.TypeConverter>, viene tentata una conversione diretta per il tipo di proprietà. Questo livello finale è una conversione diretta in corrispondenza del valore native del parser tra tipi primitivi del linguaggio XAML, o un controllo per i nomi delle costanti denominate in un'enumerazione (parser accede quindi i valori corrispondenti).  
  
#### <a name="enumeration-attribute-values"></a>Valori di attributo di enumerazione  
 Enumerazioni in XAML vengono elaborate in modo intrinseco dal parser XAML e i membri di un'enumerazione devono essere specificati, specificando il nome della stringa di una delle costanti denominate dell'enumerazione.  
  
 Per i valori di enumerazione nonflag, il comportamento nativo è per elaborare la stringa di un valore di attributo e risolvere il problema a uno dei valori di enumerazione. Non si specifica l'enumerazione nel formato *enumerazione*. *Valore*, come avviene nel codice. È invece necessario specificare solo *valore*, e *enumerazione* viene dedotto dal tipo di proprietà sta impostando. Se si specifica un attributo nel *enumerazione*. *Valore* , non verrà risolto in modo corretto.  
  
 Per le enumerazioni, il comportamento dipende il <xref:System.Enum.Parse%2A?displayProperty=nameWithType> (metodo). È possibile specificare più valori per un'enumerazione di flag per flag separando ogni valore con una virgola. Tuttavia, è possibile combinare i valori di enumerazione non basati su flag. È ad esempio, non è possibile utilizzare la sintassi di virgole per tentare di creare un <xref:System.Windows.Trigger> che agisce su più condizioni di un'enumerazione:  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Le enumerazioni che supportano gli attributi che possono essere impostati in XAML sono rare in WPF. Tuttavia, è un'enumerazione di questo tipo è <xref:System.Windows.Media.StyleSimulations>. È possibile utilizzare la sintassi di attributo basato su flag delimitato da virgole, ad esempio, per modificare l'esempio fornito nella sezione Osservazioni per il <xref:System.Windows.Documents.Glyphs> classe; `StyleSimulations = "BoldSimulation"` potrebbero diventare `StyleSimulations = "BoldSimulation,ItalicSimulation"`. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType> è un'altra proprietà in cui è possibile specificare più di un valore di enumerazione. Tuttavia, questa proprietà si trova un caso speciale, poiché il <xref:System.Windows.Input.ModifierKeys> enumerazione supporta il propria convertitore di tipi. Il convertitore di tipi per i modificatori Usa un segno più (+) come delimitatore, anziché una virgola (,). Questa conversione supporta la sintassi più tradizionale per rappresentare le combinazioni di tasti nella programmazione di Microsoft Windows, ad esempio "Ctrl + Alt".  
  
### <a name="properties-and-event-member-name-references"></a>Proprietà e i riferimenti al nome di membro di evento  
 Quando si specifica un attributo, è possibile fare riferimento a qualsiasi proprietà o un evento esistente come membro del tipo CLR che è creata un'istanza dell'elemento oggetto contenitore.  
  
 In alternativa, è possibile fare riferimento a una proprietà associata o evento, indipendente dell'elemento oggetto contenitore associato. (In una sezione successiva vengono illustrate le proprietà associate).  
  
 È anche possibile assegnare un nome qualsiasi evento da qualsiasi oggetto che è accessibile tramite lo spazio dei nomi predefinito con un *nomeTipo*. *evento* nome parziale; questa sintassi supporta l'associazione di gestori per gli eventi indirizzati in cui il gestore consente di gestire gli eventi di routing da elementi figlio, ma l'elemento padre non tale evento è presente nella relativa tabella dei membri. Questa sintassi è simile a una sintassi di evento associato, ma in questo caso l'evento non è un evento associato true. Al contrario, si fa riferimento a un evento con un nome completo. Per altre informazioni, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 Per alcuni scenari, i nomi delle proprietà sono a volte disponibili come valore di un attributo, anziché il nome dell'attributo. Nome di tale proprietà può anche includere qualificatori, ad esempio la proprietà specificata nel formato *TipoProprietario*. *dependencyPropertyName*. Questo scenario è comune quando si scrivono gli stili o modelli in XAML. Le regole di elaborazione per i nomi di proprietà forniti come valore di attributo sono diverse e sono disciplinate dal tipo di proprietà da impostare o i comportamenti dei sottosistemi WPF particolari. Per informazioni dettagliate, vedere [stili e modelli](../controls/styling-and-templating.md).  
  
 Un altro utilizzo per i nomi delle proprietà è quando un valore di attributo descrive una relazione proprietà-proprietà. Questa funzionalità viene usata per il data binding e per le destinazioni dello storyboard ed è abilitata per il <xref:System.Windows.PropertyPath> classe e il convertitore dei tipi. Per una descrizione più completa della semantica di ricerca, vedere [sintassi XAML di PropertyPath](propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>Sintassi per gli elementi proprietà  
 *Sintassi per elementi proprietà* certi versi dalle regole di sintassi di base XML per gli elementi. Nel codice XML, il valore di un attributo è una stringa standard de facto, con la variazione possibile solo il formato di codifica di stringa è in uso. In XAML, è possibile assegnare altri elementi oggetto come valore di una proprietà. Questa funzionalità è abilitata per la sintassi per elementi proprietà. Anziché la proprietà viene specificata come un attributo all'interno del tag di elemento, la proprietà viene specificata utilizzando un elemento di apertura nel tag *nomeTipoElemento*. *propertyName* form, il valore della proprietà viene specificato all'interno e quindi l'elemento di proprietà viene chiuso.  
  
 In particolare, la sintassi inizia con una parentesi uncinata (\<), seguito immediatamente dal nome del tipo della classe o struttura che la sintassi è contenuta all'interno. Questa è seguita immediatamente da un punto singolo (.), quindi dal nome di una proprietà, quindi di una parentesi uncinata chiusa (>). Come con la sintassi di attributo, tale proprietà deve esistere entro i membri pubblici dichiarati nel tipo specificato. Il valore da assegnare alla proprietà è contenuto all'interno dell'elemento di proprietà. In genere, il valore viene passato come uno o più elementi oggetto, perché gli oggetti come valori è lo scenario che la sintassi degli elementi è dedicato alla risoluzione. Infine, un tag di chiusura equivalente specificando le stesse *nomeTipoElemento*. *propertyName* combinazione è necessario specificare, corretta l'annidamento e bilanciato con altri tag di elemento.  
  
 Ad esempio, ecco la sintassi degli elementi di proprietà per il <xref:System.Windows.FrameworkElement.ContextMenu%2A> proprietà di un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 Il valore all'interno di un elemento di proprietà può essere assegnato anche come testo interno, nei casi in cui il tipo della proprietà specificato è un tipo di valore primitivo, ad esempio <xref:System.String>, o un'enumerazione in cui viene specificato un nome. Questi due utilizzi sono molto comuni, perché ognuno di questi casi può anche usare una sintassi di attributo più semplice. Uno scenario per il riempimento di un elemento proprietà con una stringa per le proprietà non sono proprietà di contenuto XAML ma ancora usate per la rappresentazione testo dell'interfaccia utente, e sono necessari determinati elementi di spazi vuoti, ad esempio gli avanzamenti riga venga visualizzato nel testo dell'interfaccia utente. Sintassi di attributo non è possibile mantenere gli avanzamenti riga, ma la sintassi degli elementi può, purché la conservazione di spazi vuoti significativa è attiva (per informazioni dettagliate, vedere [elaborazione di XAML degli spazi vuoti](../../xaml-services/whitespace-processing-in-xaml.md)). Un altro scenario è, in modo che [X:Uid Directive](../../xaml-services/x-uid-directive.md) può essere applicato all'elemento property e contrassegnare quindi il valore all'interno di BAML output un valore che deve essere localizzato in WPF o da altre tecniche.  
  
 Un elemento di proprietà non è rappresentato nell'albero logico WPF. Prvek vlastnosti è semplicemente una sintassi particolare per l'impostazione di una proprietà e non è un elemento con un'istanza o un oggetto sottostante. (Per informazioni dettagliate sul concetto di albero logico, vedere [strutture ad albero in WPF](trees-in-wpf.md).)  
  
 Per le proprietà in cui sono supportati sia attributi sia proprietà sintassi degli elementi, in genere le due sintassi hanno lo stesso risultato, anche se possono variare leggermente sottigliezze come la gestione degli spazi vuoti tra i tipi di sintassi.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>Sintassi per raccolte  
 La specifica di XAML richiede le implementazioni del processore XAML per identificare le proprietà in cui il tipo di valore è una raccolta. Implementazione del processore XAML generale in .NET è basato sul codice gestito e CLR, e identifica i tipi di raccolta tramite uno dei seguenti:  
  
-   Il tipo implementa <xref:System.Collections.IList>.  
  
-   Il tipo implementa <xref:System.Collections.IDictionary>.  
  
-   Tipo deriva da <xref:System.Array> (per altre informazioni sulle matrici in XAML, vedere [estensione di Markup X:Array](../../xaml-services/x-array-markup-extension.md).)  
  
 Se il tipo di una proprietà è una raccolta, quindi il tipo di raccolta derivato non dovrà essere specificato nel markup come elemento oggetto. Gli elementi destinati a diventare gli elementi nella raccolta vengono invece specificati come uno o più elementi figlio dell'elemento proprietà. Ognuno di questi elementi viene valutata in un oggetto durante il caricamento e aggiungere alla raccolta, chiamare il `Add` metodo della raccolta implicita. Ad esempio, il <xref:System.Windows.Style.Triggers%2A> proprietà di <xref:System.Windows.Style> accetta il tipo di insieme specializzato <xref:System.Windows.TriggerCollection>, che implementa l'interfaccia <xref:System.Collections.IList>. Non è necessario creare un'istanza di un <xref:System.Windows.TriggerCollection> elemento oggetto nel markup. È invece specificare uno o più <xref:System.Windows.Trigger> elementi come elementi all'interno di `Style.Triggers` elemento proprietà, in cui <xref:System.Windows.Trigger> (o una classe derivata) è il tipo previsto come tipo di elemento fortemente tipizzato e implicite <xref:System.Windows.TriggerCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Una proprietà può essere un tipo di raccolta e la proprietà di contenuto XAML per il tipo e tipi derivati, come descritto nella sezione successiva di questo argomento.  
  
 Un elemento della raccolta implicita consente di creare un membro nella rappresentazione dell'albero logico, anche se non viene visualizzato nel markup come elemento. In genere il costruttore del tipo padre esegue la creazione di istanze per la raccolta che è una delle sue proprietà e raccolta inizialmente vuota diventa parte dell'albero di oggetti.  
  
> [!NOTE]
>  L'elenco e il dizionario di interfacce generiche (<xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IDictionary%602>) non sono supportate per il rilevamento della raccolta. Tuttavia, è possibile usare la <xref:System.Collections.Generic.List%601> classe come classe di base, perché implementa <xref:System.Collections.IList> direttamente, o <xref:System.Collections.Generic.Dictionary%602> come classe di base, perché implementa <xref:System.Collections.IDictionary> direttamente.  
  
 Nelle pagine di riferimento .NET per i tipi di raccolta, questa sintassi con l'omissione dell'elemento oggetto per una raccolta intenzionale in alcuni casi è indicata nella sezione sintassi XAML come sintassi per raccolte implicite.  
  
 Fatta eccezione per l'elemento radice, ogni elemento dell'oggetto in un file XAML è annidato come elemento figlio di un altro elemento è davvero un elemento che corrisponde a uno o entrambi i casi seguenti: un membro di una proprietà di raccolte implicite del proprio elemento padre , o un elemento che specifica il valore della proprietà di contenuto XAML per l'elemento padre (XAML contenuto verranno descritte le proprietà in una sezione successiva). In altre parole, la relazione tra gli elementi padre e gli elementi figlio in una pagina di markup è realmente un singolo oggetto in corrispondenza della radice e ogni elemento dell'oggetto sotto la radice è una singola istanza che fornisce un valore di proprietà dell'elemento padre, o uno degli elementi all'interno di una colonna PROSSIMITA che è anche un valore della proprietà di tipo raccolta dell'elemento padre. Questo concetto single-root è comune in XML e spesso è consolidato nel comportamento delle API di caricamento XAML, ad esempio <xref:System.Windows.Markup.XamlReader.Load%2A>.  
  
 L'esempio seguente è una sintassi con l'elemento oggetto per una raccolta (<xref:System.Windows.Media.GradientStopCollection>) specificata in modo esplicito.  
  
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
  
 Si noti che non è sempre possibile dichiarare in modo esplicito la raccolta. Ad esempio, il tentativo di dichiarare <xref:System.Windows.TriggerCollection> in modo esplicito nel mostrato in precedenza <xref:System.Windows.Style.Triggers%2A> esempio avrebbe esito negativo. Dichiarare in modo esplicito la raccolta richiede che la classe di raccolta deve supportare un costruttore predefinito e <xref:System.Windows.TriggerCollection> non dispone di un costruttore predefinito.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>Proprietà di contenuto XAML  
 Sintassi di contenuto XAML è una sintassi che è abilitata solo sulle classi che specificano il <xref:System.Windows.Markup.ContentPropertyAttribute> come parte della relativa dichiarazione di classe. Il <xref:System.Windows.Markup.ContentPropertyAttribute> fa riferimento al nome di proprietà che è la proprietà di contenuto per il tipo di elemento (inclusi le classi derivate). Quando vengono elaborati da un processore XAML, eventuali elementi figlio o testo interno che si trovano tra i tag di apertura e chiusura dell'elemento oggetto verrà assegnato il valore della proprietà di contenuto XAML per quell'oggetto. È consentito specificare gli elementi di proprietà esplicito per la proprietà di contenuto, ma questo utilizzo non viene visualizzato a livello generale nelle sezioni di sintassi di XAML in riferimento a .NET. La tecnica esplicite/dettagliato ha un valore occasionale per maggiore chiarezza del markup, o come una questione di stile markup, ma in genere di una proprietà di contenuto si desidera semplificare il markup in modo che gli elementi correlati in modo intuitivo come padre-figlio possono essere annidati direttamente. Tag di elemento di proprietà per le altre proprietà in un elemento non vengono assegnati come "contenuto" per una definizione del linguaggio XAML strict; essi vengono elaborati in precedenza nell'ordine di elaborazione del parser XAML e non sono considerati come "contenuto".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>I valori di proprietà di contenuto XAML devono essere contigui  
 Il valore di una proprietà di contenuto XAML deve essere assegnato completamente prima o completamente dopo qualsiasi altro elemento proprietà nell'elemento oggetto. Ciò è vero che indica se il valore di una proprietà di contenuto XAML viene specificato sotto forma di stringa o come uno o più oggetti. Ad esempio, non esegue l'analisi il markup seguente:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Questa situazione non è consentita perché se questa sintassi sono stata apportata esplicita tramite sintassi degli elementi proprietà per la proprietà di contenuto, quindi la proprietà di contenuto viene impostata due volte:  
  
```xml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Un esempio è se la proprietà di contenuto è una raccolta e gli elementi figlio sono frammisto a elementi di proprietà:  
  
```xml  
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
 Per accettare più di un elemento oggetto singolo come contenuto, il tipo della proprietà di contenuto deve essere in modo specifico un tipo di raccolta. Simile alla sintassi degli elementi di proprietà per i tipi di raccolta, un processore XAML deve identificare i tipi che sono tipi di raccolta. Se un elemento dispone di una proprietà di contenuto XAML e il tipo della proprietà di contenuto XAML è una raccolta, quindi il tipo di raccolta implicita non dovrà essere specificato nel markup come elemento oggetto e la proprietà di contenuto XAML non dovrà essere specificato come un el proprietà ement. Di conseguenza il modello di contenuto evidente nel markup può ora includere più di un elemento figlio assegnato come contenuto. Di seguito è riportata la sintassi del contenuto per un <xref:System.Windows.Controls.Panel> classe derivata. Tutti i <xref:System.Windows.Controls.Panel> alle classi derivate stabiliscono le proprietà di contenuto XAML per essere <xref:System.Windows.Controls.Panel.Children%2A>, che richiede un valore di tipo <xref:System.Windows.Controls.UIElementCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Si noti che né l'elemento di proprietà per <xref:System.Windows.Controls.Panel.Children%2A> né l'elemento per il <xref:System.Windows.Controls.UIElementCollection> è necessaria nel markup. Questa è una funzionalità di progettazione di XAML in modo che i contenuti in modo ricorsivo gli elementi che definiscono un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sono rappresentate in modo più intuitivo come un albero di elementi annidati con relazioni padre-figlio immediato, senza sono frapposti tag di elemento di proprietà o oggetti della raccolta. In effetti, <xref:System.Windows.Controls.UIElementCollection> non è possibile specificare in modo esplicito nel markup come elemento oggetto, per impostazione predefinita. Perché il solo utilizzo previsto è come una raccolta di implicita, <xref:System.Windows.Controls.UIElementCollection> non espone un costruttore predefinito pubblico e pertanto non è possibile creare istanze come elemento oggetto.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>La combinazione di elementi di proprietà e gli elementi oggetto in un oggetto con una proprietà di contenuto  
 La specifica di XAML dichiara che un processore XAML possa imporre che gli elementi di oggetti utilizzati per compilare la proprietà di contenuto XAML all'interno di un elemento oggetto devono essere contigui e non devono essere combinati. Questa restrizione che limita la combinazione di elementi di proprietà e il contenuto viene applicata dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] processori XAML.  
  
 È possibile avere un elemento oggetto figlio come primo markup all'interno di un elemento oggetto. È quindi possibile introdurre elementi proprietà. In alternativa, è possibile specificare uno o più elementi di proprietà, quindi il contenuto e altri elementi di proprietà. Ma una volta che un elemento proprietà dopo il contenuto, non sarà possibile apportare qualsiasi ulteriore contenuto, è possibile aggiungere solo gli elementi di proprietà.  
  
 Questo contenuto / proprietà elemento ordine requisito non si applica al testo interno utilizzato come contenuto. Tuttavia, è ancora uno stile di markup buona per mantenere il testo interno contigui, dal momento che gli spazi vuoti significativi sarà difficili rilevare visivamente nel markup se gli elementi di proprietà vengono intercalati con testo interno.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>Spazi dei nomi XAML  
 Nessuno degli esempi di sintassi precedente specificato uno spazio dei nomi XAML diversi da spazio dei nomi XAML predefinito. Nel tipico [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le applicazioni, il valore dello spazio dei nomi XAML predefinito viene specificata la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dello spazio dei nomi. È possibile specificare spazi dei nomi XAML diversi dello spazio dei nomi XAML predefinito e continuare a utilizzare la sintassi seguente. Tuttavia, in qualsiasi punto in cui una classe è denominata che non è accessibile all'interno dello spazio dei nomi XAML predefinito, il nome della classe deve essere preceduto con il prefisso dello spazio dei nomi XAML mappato allo spazio dei nomi CLR corrispondente. Ad esempio, `<custom:Example/>` è la sintassi degli elementi oggetto per creare un'istanza del `Example` (classe), in cui lo spazio dei nomi CLR contenente tale classe (e possibilmente le informazioni di assembly esterno che contiene i tipi di backup) è stato già associato ai `custom` prefisso.  
  
 Per altre informazioni sugli spazi dei nomi XAML, vedere [spazi dei nomi XAML e Mapping di Namespace per XAML WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Estensioni di markup  
 XAML definisce un'estensione di markup di entità che consente a un carattere di escape dalla gestione del processore XAML normale dei valori di attributo di stringa o oggetto elementi e rinvia l'elaborazione di una classe sottostante di programmazione. Il carattere che identifica un'estensione di markup a un processore XAML quando si usa la sintassi degli attributi è la parentesi graffa di apertura ({), seguita da qualsiasi carattere diverso da una parentesi graffa di chiusura (}). La prima stringa segue la parentesi graffa deve fare riferimento alla classe che fornisce il comportamento dipende dall'estensione, in cui il riferimento è possibile omettere la sottostringa "Extension" se la sottostringa fa parte del nome della classe true. Successivamente, può risultare uno spazio singolo, e quindi ogni carattere successivo viene usato come input dall'implementazione dell'estensione, fino a quando non viene rilevata la parentesi graffa di chiusura.  
  
 L'implementazione XAML di .NET usa la <xref:System.Windows.Markup.MarkupExtension> classe astratta come base per tutte le estensioni di markup supportate da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , nonché altri framework o tecnologie. Le estensioni di markup che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementa in particolare spesso devono fornire un mezzo per fare riferimento ad altri oggetti esistenti o per rinviare i riferimenti agli oggetti che verranno valutati in fase di esecuzione. Ad esempio, un'associazione dati WPF semplice specificando il `{Binding}` estensione di markup al posto del valore che in genere richiederebbe una particolare proprietà. Molte delle estensioni di markup WPF consentono una sintassi per attributi per le proprietà in cui una sintassi di attributo non sarebbe possibile. Ad esempio, un <xref:System.Windows.Style> oggetto è un tipo relativamente complesso che contiene una serie di oggetti e proprietà annidata. In WPF vengono in genere definiti come una risorsa in un <xref:System.Windows.ResourceDictionary>, cui viene fatto riferimento tramite una delle due estensioni di markup WPF che richiedono una risorsa. L'estensione di markup rinvia la valutazione del valore della proprietà da una ricerca delle risorse e consente di specificare il valore della <xref:System.Windows.FrameworkElement.Style%2A> proprietà, che accetta il tipo <xref:System.Windows.Style>, nella sintassi come illustrato di seguito dell'attributo:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 In questo caso, `StaticResource` identifica il <xref:System.Windows.StaticResourceExtension> classe che fornisce l'implementazione dell'estensione di markup. Stringa successiva `MyStyle` viene usato come input per il valore non predefinito <xref:System.Windows.StaticResourceExtension> costruttore, in cui il parametro accettato dalla stringa di estensione dichiara l'oggetto richiesto <xref:System.Windows.ResourceKey>. `MyStyle` è previsto che il [X:Key](../../xaml-services/x-key-directive.md) pari a un <xref:System.Windows.Style> definito come una risorsa. Il [estensione di Markup StaticResource](staticresource-markup-extension.md) utilizzo richiede che la risorsa venga utilizzata per fornire la <xref:System.Windows.Style> valore della proprietà tramite la logica di ricerca di risorse statica in fase di caricamento.  
  
 Per altre informazioni sulle estensioni di markup, vedere [Estensioni di markup e WPF XAML](markup-extensions-and-wpf-xaml.md). Per un riferimento di estensioni di markup e altre XAML funzionalità abilitate nell'implementazione .NET XAML generale di programmazione, vedere [XAML Namespace (x) Funzionalità del linguaggio](../../xaml-services/xaml-namespace-x-language-features.md). Le estensioni di markup specifiche di WPF, vedere [estensioni XAML WPF](wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>Proprietà associate  
 Le proprietà associate sono un concetto di programmazione introdotto XAML in base al quale le proprietà possono essere di proprietà e definite da un determinato tipo, ma impostare come attributi o elementi di proprietà su qualsiasi elemento. Lo scenario principale è che le proprietà associate sono concepite per consentire gli elementi figlio in una struttura di markup per registrare le informazioni a un elemento padre senza la necessità di un modello a oggetti ampiamente condivise tra tutti gli elementi. Viceversa, le proprietà associate possono essere utilizzate dagli elementi padre di fornire informazioni agli elementi figlio. Per altre informazioni sullo scopo delle proprietà associate e come creare il proprio associate le proprietà, vedere [Cenni preliminari sulle proprietà associate](attached-properties-overview.md).  
  
 Le proprietà associate usano una sintassi in apparenza simile alla sintassi degli elementi di proprietà, in quanto è anche possibile specificare una *nomeTipo*. *propertyName* combinazione. Vi sono due differenze importanti:  
  
-   È possibile usare la *nomeTipo*. *propertyName* anche quando si imposta una proprietà associata tramite la sintassi degli attributi. Le proprietà associate sono che l'unico caso in cui la qualifica il nome della proprietà è un requisito in una sintassi per attributi.  
  
-   È anche possibile usare la sintassi degli elementi per le proprietà associate. Tuttavia, per la sintassi per elementi proprietà tipico, il *typeName* è specificare l'elemento oggetto che contiene l'elemento di proprietà. Se si fa riferimento a una proprietà associata, il *typeName* è la classe che definisce la proprietà associata, non l'elemento oggetto contenitore.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>Eventi associati  
 Gli eventi associati sono un altro concetto di programmazione introdotto XAML in cui gli eventi possono essere definiti da un tipo specifico, ma è possibile associare i gestori in qualsiasi elemento oggetto. Nell'implementazione WPF, spesso il tipo che definisce un evento associato è un tipo statico che definisce un servizio e a volte gli eventi associati vengono esposti dall'alias di un evento indirizzato nei tipi che espongono il servizio. Gestori per gli eventi associati vengono specificati tramite la sintassi di attributo. Come con gli eventi associati, la sintassi degli attributi viene espanso per gli eventi associati consentire una *nomeTipo*. *eventName* sull'utilizzo, in cui *typeName* è la classe che fornisce `Add` e `Remove` funzioni di accesso del gestore eventi per l'infrastruttura degli eventi associati e *eventName* è il nome dell'evento.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomia di un elemento radice XAML  
 Nella tabella seguente viene illustrato un tipico XAML elemento radice frammentato, che mostra gli attributi specifici di un elemento radice:  
  
|||  
|-|-|  
|`<Page`|Apertura dell'elemento oggetto dell'elemento radice|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|Il valore predefinito ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) dello spazio dei nomi XAML|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|Spazio dei nomi XAML del linguaggio XAML|  
|`x:Class="ExampleNamespace.ExampleCode"`|Dichiarazione di classe parziale che si connette markup al code-behind definito per la classe parziale|  
|`>`|Fine dell'elemento oggetto per la radice. Oggetto non è ancora chiuso perché l'elemento contiene elementi figlio|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>Utilizzi XAML non consigliati e facoltativi  
 Le sezioni seguenti descrivono gli utilizzi XAML che tecnicamente sono supportate dai processori XAML, ma che producono il livello di dettaglio o altri problemi estetiche che interferiscono con i file XAML rimanenti leggibile dall'utente quando si sviluppano applicazioni che contengono origini XAML.  
  
### <a name="optional-property-element-usages"></a>Utilizzi degli elementi di proprietà facoltativa  
 Gli utilizzi degli elementi di proprietà facoltative includono scrive in modo esplicito le proprietà di contenuto di elemento che il processore XAML considera implicito. Ad esempio, quando si dichiara il contenuto di un <xref:System.Windows.Controls.Menu>, è possibile scegliere di dichiarare in modo esplicito il <xref:System.Windows.Controls.ItemsControl.Items%2A> raccolta del <xref:System.Windows.Controls.Menu> come un `<Menu.Items>` tag di elemento di proprietà e inserire ciascun <xref:System.Windows.Controls.MenuItem> all'interno di `<Menu.Items>`, anziché rispetto all'uso del comportamento del processore XAML implicito che tutti gli elementi figlio di un <xref:System.Windows.Controls.Menu> deve essere un <xref:System.Windows.Controls.MenuItem> e vengono inseriti nel <xref:System.Windows.Controls.ItemsControl.Items%2A> raccolta. In alcuni casi gli utilizzi facoltativi possono aiutare a chiarire visivamente la struttura dell'oggetto come rappresentato nel markup. In alcuni casi utilizzo di un elemento di proprietà esplicito può evitare markup che tecnicamente funzionale ma visivamente possono generare confusione, ad esempio le estensioni di markup annidato all'interno di un valore di attributo.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Attributi qualificati nomeTipo. nomemembro completo  
 Il *nomeTipo*. *memberName* modulo per un attributo in realtà funziona in maniera più diretta rispetto a soltanto il case di evento indirizzato. Ma in altre situazioni è superfluo tale form ed è consigliabile evitare che, se solo per ragioni di stile di markup e migliorare la leggibilità. Nell'esempio seguente, ognuno dei tre riferimenti al <xref:System.Windows.Controls.Control.Background%2A> attributo sono completamente equivalenti:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background` funziona perché la ricerca completo per tale proprietà sul <xref:System.Windows.Controls.Button> ha esito positivo (<xref:System.Windows.Controls.Control.Background%2A> è stata ereditata dal controllo del codice) e <xref:System.Windows.Controls.Button> è la classe dell'elemento oggetto o una classe di base. `Control.Background` funziona perché il <xref:System.Windows.Controls.Control> classe definisce effettivamente <xref:System.Windows.Controls.Control.Background%2A> e <xref:System.Windows.Controls.Control> è un <xref:System.Windows.Controls.Button> classe di base.  
  
 Tuttavia, quanto segue *nomeTipo*. *memberName* esempio di form non funziona e in cui sono visualizzato i commento:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label> è un'altra classe derivata di <xref:System.Windows.Controls.Control>, e se è stato specificato `Label.Background` all'interno di un <xref:System.Windows.Controls.Label> elemento oggetto, questo uso avrebbe avuto esito positivo. Tuttavia, poiché <xref:System.Windows.Controls.Label> non è la classe o classe di base di <xref:System.Windows.Controls.Button>, il comportamento del processore XAML specificato viene quindi elaborare `Label.Background` come proprietà associata. `Label.Background` non è una proprietà associata disponibile e si verifica un errore di questo utilizzo.  
  
### <a name="basetypenamemembername-property-elements"></a>Elementi di proprietà nomeTipoBase. nomemembro  
 In modo analogo al modo in cui il *nomeTipo*. *nomeMembro* funzionamento del modulo per la sintassi di attributo, una *nomeTipoBase*. *memberName* sintassi funziona per la sintassi per elementi proprietà. Ad esempio, la sintassi seguente funziona:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 In questo caso, è stato specificato l'elemento property `Control.Background` anche se l'elemento di proprietà è stato incluso in `Button`.  
  
 Ma in modo analogo *nomeTipo*. *nomeMembro* modulo per gli attributi *nomeTipoBase*. *memberName* non rappresenta uno stile nel markup ed è opportuno evitare.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [XAML Namespace (x) Funzionalità del linguaggio](../../xaml-services/xaml-namespace-x-language-features.md)
- [Estensioni XAML WPF](wpf-xaml-extensions.md)
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [TypeConverter e XAML](typeconverters-and-xaml.md)
- [Classi XAML e personalizzate per WPF](xaml-and-custom-classes-for-wpf.md)
