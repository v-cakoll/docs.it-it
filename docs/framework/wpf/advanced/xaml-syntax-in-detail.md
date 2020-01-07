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
ms.openlocfilehash: 2c6a8662236b614545e7fb8545b7b60e1b08b6bd
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559833"
---
# <a name="xaml-syntax-in-detail"></a>Descrizione dettagliata della sintassi XAML
In questo argomento vengono definiti i termini utilizzati per descrivere gli elementi della sintassi XAML. Questi termini vengono usati di frequente nel resto della documentazione, sia per la documentazione di WPF in particolare che per gli altri Framework che usano XAML o i concetti di base di XAML abilitati dal supporto del linguaggio XAML a livello di System. XAML. In questo argomento viene illustrata la terminologia di base introdotta nell'argomento [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).  

<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>Specifica del linguaggio XAML  
 La terminologia di sintassi XAML definita qui viene definita o a cui viene fatto riferimento all'interno della specifica del linguaggio XAML. XAML è un linguaggio basato su XML e segue o si espande in base alle regole strutturali XML. Parte della terminologia è condivisa da o è basata sulla terminologia comunemente utilizzata per descrivere il linguaggio XML o il modello a oggetti documento XML.  
  
 Per ulteriori informazioni sulla specifica del linguaggio XAML, scaricare [\[\]MS-XAML](https://go.microsoft.com/fwlink/?LinkId=114525) dall'area download Microsoft.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>XAML e CLR  
 XAML è un linguaggio di markup. Il Common Language Runtime (CLR), come sottinteso dal nome, Abilita l'esecuzione del runtime. XAML non è da solo uno dei linguaggi comuni utilizzati direttamente dal runtime CLR. È invece possibile considerare XAML come supporto per il proprio sistema di tipi. Il particolare sistema di analisi XAML utilizzato da WPF si basa su CLR e sul sistema dei tipi CLR. Viene eseguito il mapping dei tipi XAML ai tipi CLR per creare un'istanza di una rappresentazione in fase di esecuzione quando XAML per WPF viene analizzato. Per questo motivo, il resto della discussione sulla sintassi di questo documento includerà riferimenti al sistema di tipi CLR, anche se le discussioni sulla sintassi equivalenti nella specifica del linguaggio XAML non lo sono. (Per il livello di specifica del linguaggio XAML, è possibile eseguire il mapping dei tipi XAML a qualsiasi altro sistema di tipi, che non deve essere CLR, ma che richiederebbe la creazione e l'uso di un parser XAML diverso).  
  
#### <a name="members-of-types-and-class-inheritance"></a>Membri di tipi ed ereditarietà delle classi  
 Le proprietà e gli eventi come appaiono come membri XAML di un tipo di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono spesso ereditati dai tipi di base. Si consideri, ad esempio, questo esempio: `<Button Background="Blue" .../>`. La proprietà <xref:System.Windows.Controls.Control.Background%2A> non è una proprietà dichiarata immediatamente nella classe <xref:System.Windows.Controls.Button>, se si desidera esaminare la definizione della classe, i risultati della reflection o la documentazione. Al contrario, <xref:System.Windows.Controls.Control.Background%2A> viene ereditato dalla classe <xref:System.Windows.Controls.Control> di base.  
  
 Il comportamento di ereditarietà delle classi di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementi XAML rappresenta una partenza significativa da un'interpretazione applicata dallo schema del markup XML. L'ereditarietà delle classi può diventare complessa, in particolare quando le classi di base intermedie sono astratte o quando sono incluse le interfacce. Questo è un motivo per cui il set di elementi XAML e i relativi attributi consentiti sono difficili da rappresentare in modo accurato e completo utilizzando i tipi di schema utilizzati generalmente per la programmazione XML, ad esempio il formato DTD o XSD. Un altro motivo è che le funzionalità di estendibilità e mapping dei tipi del linguaggio XAML escludono la completezza di qualsiasi rappresentazione fissa dei tipi e dei membri consentiti.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>Sintassi degli elementi oggetto  
 La *sintassi dell'elemento oggetto* è la sintassi di markup XAML che crea un'istanza di una classe o struttura CLR dichiarando un elemento XML. Questa sintassi è simile alla sintassi degli elementi di altri linguaggi di markup, ad esempio HTML. La sintassi dell'elemento oggetto inizia con una parentesi uncinata aperta (\<), seguita immediatamente dal nome del tipo della classe o della struttura di cui viene creata un'istanza. Zero o più spazi possono seguire il nome del tipo e zero o più attributi possono anche essere dichiarati nell'elemento oggetto, con uno o più spazi che separano ogni coppia nome attributo = "valore". Infine, è necessario che venga soddisfatta una delle condizioni seguenti:  
  
- L'elemento e il tag devono essere chiusi da una barra (/) seguita immediatamente da una parentesi uncinata chiusa (>).  
  
- Il tag di apertura deve essere completato da una parentesi uncinata chiusa (>). Altri elementi oggetto, elementi proprietà o testo interno possono seguire il tag di apertura. Il contenuto che può essere contenuto in questo contesto è in genere vincolato dal modello a oggetti dell'elemento. È necessario che esista anche il tag di chiusura equivalente per l'elemento oggetto, nell'annidamento e nel saldo appropriati con altre coppie di tag di apertura e chiusura.  
  
 XAML implementato da .NET include un set di regole che mappano gli elementi oggetto in tipi, attributi in proprietà o eventi e spazi dei nomi XAML agli spazi dei nomi CLR e ad assembly. Per WPF e .NET, gli elementi oggetto XAML vengono mappati ai tipi .NET come definito negli assembly a cui si fa riferimento e gli attributi vengono mappati ai membri di tali tipi. Quando si fa riferimento a un tipo CLR in XAML, è possibile accedere anche ai membri ereditati di tale tipo.  
  
 Ad esempio, l'esempio seguente è la sintassi dell'elemento oggetto che crea un'istanza di una nuova istanza della classe <xref:System.Windows.Controls.Button> e specifica anche un attributo <xref:System.Windows.FrameworkElement.Name%2A> e un valore per l'attributo:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 Nell'esempio seguente viene illustrata la sintassi dell'elemento oggetto che include anche la sintassi delle proprietà di contenuto XAML. Il testo interno contenuto all'interno di verrà usato per impostare la proprietà di contenuto XAML <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Modelli di contenuto  
 Una classe potrebbe supportare un utilizzo come elemento oggetto XAML in termini di sintassi, ma tale elemento funzionerà correttamente solo in un'applicazione o una pagina quando viene posizionata in una posizione prevista di un modello di contenuto o di un albero di elementi generale. Un <xref:System.Windows.Controls.MenuItem>, ad esempio, deve essere in genere inserito solo come elemento figlio di una classe derivata <xref:System.Windows.Controls.Primitives.MenuBase>, ad esempio <xref:System.Windows.Controls.Menu>. I modelli di contenuto per elementi specifici sono documentati come parte delle osservazioni sulle pagine della classe per i controlli e altre classi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] che possono essere usate come elementi XAML.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>Proprietà degli elementi oggetto  
 Le proprietà in XAML sono impostate da varie sintassi possibili. La sintassi che può essere usata per una particolare proprietà può variare in base alle caratteristiche del sistema di tipi sottostante della proprietà che si sta impostando.  
  
 Impostando i valori delle proprietà, è possibile aggiungere caratteristiche o caratteristiche agli oggetti esistenti nell'oggetto grafico in fase di esecuzione. Lo stato iniziale dell'oggetto creato da un elemento oggetto è basato sul comportamento del costruttore senza parametri. In genere, l'applicazione userà qualcosa di diverso da un'istanza completamente predefinita di un determinato oggetto.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>Sintassi per attributi (proprietà)  
 La sintassi dell'attributo è la sintassi di markup XAML che imposta un valore per una proprietà dichiarando un attributo in un elemento oggetto esistente. Il nome dell'attributo deve corrispondere al nome del membro CLR della proprietà della classe che esegue il backup dell'elemento oggetto pertinente. Il nome dell'attributo è seguito da un operatore di assegnazione (=). Il valore dell'attributo deve essere una stringa racchiusa tra virgolette.  
  
> [!NOTE]
> È possibile utilizzare le virgolette alternative per inserire una virgoletta letterale all'interno di un attributo. Ad esempio, è possibile usare le virgolette singole come mezzo per dichiarare una stringa che contiene un carattere virgolette doppie al suo interno. Se si utilizzano virgolette singole o doppie, è necessario utilizzare una coppia corrispondente per l'apertura e la chiusura della stringa del valore dell'attributo. Sono disponibili anche sequenze di escape o altre tecniche per aggirare le restrizioni relative ai caratteri imposte da una particolare sintassi XAML. Vedere [entità carattere XML e XAML](../../../desktop-wpf/xaml-services/xml-character-entities.md).  
  
 Per poter essere impostato tramite la sintassi dell'attributo, una proprietà deve essere pubblica e deve essere scrivibile. Il valore della proprietà nel sistema di tipi di supporto deve essere un tipo di valore o deve essere un tipo di riferimento di cui è possibile creare un'istanza o a cui fa riferimento un processore XAML durante l'accesso al tipo di supporto pertinente.  
  
 Per gli eventi XAML WPF, l'evento a cui viene fatto riferimento come nome di attributo deve essere pubblico e avere un delegato pubblico.  
  
 La proprietà o l'evento deve essere un membro della classe o della struttura di cui viene creata un'istanza dall'elemento oggetto contenitore.  
  
### <a name="processing-of-attribute-values"></a>Elaborazione dei valori di attributo  
 Il valore stringa contenuto nelle virgolette di apertura e di chiusura viene elaborato da un processore XAML. Per le proprietà, il comportamento di elaborazione predefinito è determinato dal tipo della proprietà CLR sottostante.  
  
 Il valore dell'attributo è riempito da uno dei seguenti elementi, usando questo ordine di elaborazione:  
  
1. Se il processore XAML rileva una parentesi graffa o un elemento oggetto che deriva da <xref:System.Windows.Markup.MarkupExtension>, l'estensione di markup a cui viene fatto riferimento viene valutata per prima anziché elaborare il valore come stringa e l'oggetto restituito dall'estensione di markup viene usato come valore. In molti casi l'oggetto restituito da un'estensione di markup sarà un riferimento a un oggetto esistente oppure un'espressione che rinvia la valutazione fino alla fase di esecuzione e non è un nuovo oggetto di cui è stata creata un'istanza.  
  
2. Se la proprietà viene dichiarata con un <xref:System.ComponentModel.TypeConverter>con attributi oppure il tipo di valore di tale proprietà viene dichiarato con un <xref:System.ComponentModel.TypeConverter>con attributi, il valore stringa dell'attributo viene inviato al convertitore di tipi come input di conversione e il convertitore restituirà una nuova istanza dell'oggetto.  
  
3. Se non è presente alcuna <xref:System.ComponentModel.TypeConverter>, viene tentata una conversione diretta nel tipo di proprietà. Questo livello finale è una conversione diretta al valore nativo del parser tra i tipi primitivi del linguaggio XAML o un controllo per i nomi delle costanti denominate in un'enumerazione (il parser accede quindi ai valori corrispondenti).  
  
#### <a name="enumeration-attribute-values"></a>Valori degli attributi di enumerazione  
 Le enumerazioni in XAML vengono elaborate intrinsecamente da parser XAML e i membri di un'enumerazione devono essere specificati specificando il nome di stringa di una delle costanti denominate dell'enumerazione.  
  
 Per i valori di enumerazione non flag, il comportamento nativo consiste nell'elaborare la stringa di un valore di attributo e risolverla in uno dei valori di enumerazione. Non si specifica l'enumerazione nell' *enumerazione*format. *Valore*, come nel codice. Viene invece specificato solo il *valore*e l' *enumerazione* viene dedotta dal tipo della proprietà che si sta impostando. Se si specifica un attributo nell' *enumerazione*. Il formato del *valore* non verrà risolto correttamente.  
  
 Per le enumerazioni flag, il comportamento è basato sul metodo <xref:System.Enum.Parse%2A?displayProperty=nameWithType>. È possibile specificare più valori per un'enumerazione flag separando ogni valore con una virgola. Tuttavia, non è possibile combinare i valori di enumerazione che non sono flag. Ad esempio, non è possibile usare la sintassi della virgola per tentare di creare un <xref:System.Windows.Trigger> che agisce su più condizioni di un'enumerazione non flag:  
  
```xaml  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Le enumerazioni flag che supportano attributi che possono essere impostati in XAML sono rare in WPF. Tuttavia, una tale enumerazione viene <xref:System.Windows.Media.StyleSimulations>. È possibile, ad esempio, usare la sintassi dell'attributo flag delimitato da virgole per modificare l'esempio fornito nei commenti per la classe <xref:System.Windows.Documents.Glyphs>. `StyleSimulations = "BoldSimulation"` potrebbe diventare `StyleSimulations = "BoldSimulation,ItalicSimulation"`. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType> è un'altra proprietà in cui è possibile specificare più di un valore di enumerazione. Tuttavia, questa proprietà si verifica come un caso speciale, perché l'enumerazione <xref:System.Windows.Input.ModifierKeys> supporta il proprio convertitore di tipi. Il convertitore di tipi per i modificatori utilizza un segno più (+) come delimitatore anziché una virgola (,). Questa conversione supporta la sintassi più tradizionale per rappresentare le combinazioni di tasti nella programmazione di Microsoft Windows, ad esempio "CTRL + ALT".  
  
### <a name="properties-and-event-member-name-references"></a>Riferimenti alle proprietà e al nome del membro evento  
 Quando si specifica un attributo, è possibile fare riferimento a qualsiasi proprietà o evento esistente come membro del tipo CLR di cui è stata creata un'istanza per l'elemento oggetto contenitore.  
  
 In alternativa, è possibile fare riferimento a una proprietà associata o a un evento associato, indipendentemente dall'elemento oggetto contenitore. (Le proprietà associate sono descritte in una sezione imminente).  
  
 È anche possibile assegnare un nome a qualsiasi evento da qualsiasi oggetto accessibile tramite lo spazio dei nomi predefinito usando un *typeName*. nome parzialmente qualificato dell' *evento* ; Questa sintassi supporta il collegamento dei gestori per gli eventi indirizzati in cui il gestore è progettato per gestire il routing degli eventi dagli elementi figlio, ma anche l'elemento padre non dispone di tale evento nella tabella dei membri. Questa sintassi è simile alla sintassi di un evento associato, ma l'evento non è un vero evento associato. Viene invece fatto riferimento a un evento con un nome completo. Per ulteriori informazioni, vedere [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md).  
  
 Per alcuni scenari, i nomi delle proprietà vengono talvolta forniti come valore di un attributo, anziché come nome dell'attributo. Il nome della proprietà può includere anche i qualificatori, ad esempio la proprietà specificata nel formato *tipoProprietario*. *dependencypropertyname*. Questo scenario è comune durante la scrittura di stili o modelli in XAML. Le regole di elaborazione per i nomi di proprietà fornite come valore di attributo sono diverse e sono regolate dal tipo della proprietà impostata o dai comportamenti di particolari sottosistemi WPF. Per informazioni dettagliate, vedere applicazione di [stili e modelli](../controls/styling-and-templating.md).  
  
 Un altro utilizzo per i nomi delle proprietà è quando un valore di attributo descrive una relazione tra proprietà della proprietà. Questa funzionalità viene usata per data binding e per le destinazioni storyboard ed è abilitata dalla classe <xref:System.Windows.PropertyPath> e dal relativo convertitore di tipi. Per una descrizione più completa della semantica di ricerca, vedere [sintassi XAML di PropertyPath](propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>Sintassi per gli elementi proprietà  
 La *sintassi dell'elemento Property* è una sintassi che diverge in parte dalle regole di base della sintassi XML per gli elementi. In XML il valore di un attributo è una stringa de facto, con la sola variazione possibile che indica il formato di codifica delle stringhe utilizzato. In XAML è possibile assegnare altri elementi oggetto come valore di una proprietà. Questa funzionalità è abilitata dalla sintassi dell'elemento Property. Anziché la proprietà specificata come attributo all'interno del tag dell'elemento, la proprietà viene specificata utilizzando un tag di elemento di apertura in *nomeTipoElemento*. *PropertyName* form, il valore della proprietà viene specificato in e quindi l'elemento Property è Closed.  
  
 In particolare, la sintassi inizia con una parentesi uncinata aperta (\<), seguita immediatamente dal nome del tipo della classe o della struttura in cui è contenuta la sintassi dell'elemento Property. Questa operazione è seguita immediatamente da un singolo punto (.), quindi dal nome di una proprietà, quindi da una parentesi uncinata chiusa (>). Come per la sintassi degli attributi, tale proprietà deve esistere all'interno dei membri pubblici dichiarati del tipo specificato. Il valore da assegnare alla proprietà è contenuto all'interno dell'elemento Property. In genere, il valore viene fornito come uno o più elementi oggetto, perché la specifica di oggetti come valori è lo scenario per cui la sintassi dell'elemento proprietà è destinata all'indirizzo. Infine, un tag di chiusura equivalente che specifica lo stesso *nomeTipoElemento*. è necessario specificare la combinazione *PropertyName* , in una nidificazione e un bilanciamento appropriati con altri tag di elemento.  
  
 Ad esempio, di seguito è riportata la sintassi dell'elemento Property per la proprietà <xref:System.Windows.FrameworkElement.ContextMenu%2A> di un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 Il valore all'interno di un elemento Property può essere fornito anche come testo interno, nei casi in cui il tipo di proprietà specificato è un tipo di valore primitivo, ad esempio <xref:System.String>, oppure un'enumerazione in cui viene specificato un nome. Questi due utilizzi sono alquanto rari, perché ognuno di questi casi può utilizzare anche una sintassi di attributo più semplice. Uno scenario per la compilazione di un elemento Property con una stringa è per le proprietà che non sono la proprietà di contenuto XAML, ma vengono comunque usate per la rappresentazione del testo dell'interfaccia utente e gli elementi di spazi vuoti specifici, ad esempio avanzamento riga, devono essere visualizzati nel testo dell'interfaccia utente. La sintassi dell'attributo non può mantenere avanzamento riga, ma la sintassi dell'elemento proprietà può, a condizione che la conservazione significativa degli spazi vuoti sia attiva (per informazioni dettagliate, vedere [elaborazione di spazi vuoti in XAML](../../../desktop-wpf/xaml-services/white-space-processing.md)). Un altro scenario è la possibilità di applicare la [direttiva x:UID](../../../desktop-wpf/xaml-services/xuid-directive.md) all'elemento Property, contrassegnando quindi il valore in come valore che deve essere localizzato nel BAML di output WPF o con altre tecniche.  
  
 Un elemento Property non è rappresentato nell'albero logico WPF. Un elemento Property è solo una particolare sintassi per l'impostazione di una proprietà e non è un elemento con un'istanza o un oggetto sottostante. Per informazioni dettagliate sul concetto di albero logico, vedere [strutture ad albero in WPF](trees-in-wpf.md).  
  
 Per le proprietà in cui sono supportate sia la sintassi degli elementi di attributo che di proprietà, le due sintassi presentano in genere lo stesso risultato, sebbene le sottigliezze, ad esempio la gestione degli spazi vuoti, possano variare leggermente tra le sintassi.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>Sintassi per raccolte  
 La specifica XAML richiede implementazioni del processore XAML per identificare le proprietà in cui il tipo di valore è una raccolta. L'implementazione generale del processore XAML in .NET è basata sul codice gestito e su CLR e identifica i tipi di raccolta tramite uno dei seguenti elementi:  
  
- Il tipo implementa <xref:System.Collections.IList>.  
  
- Il tipo implementa <xref:System.Collections.IDictionary>.  
  
- Il tipo deriva da <xref:System.Array> (per altre informazioni sulle matrici in XAML, vedere [estensione di markup x:Array](../../../desktop-wpf/xaml-services/xarray-markup-extension.md)).  
  
 Se il tipo di una proprietà è una raccolta, il tipo di raccolta derivato non deve essere specificato nel markup come elemento oggetto. Gli elementi destinati a diventare gli elementi della raccolta vengono invece specificati come uno o più elementi figlio dell'elemento Property. Ogni elemento di questo tipo viene valutato a un oggetto durante il caricamento e aggiunto alla raccolta chiamando il metodo `Add` della raccolta implicita. Ad esempio, la proprietà <xref:System.Windows.Style.Triggers%2A> di <xref:System.Windows.Style> accetta il tipo di raccolta specializzato <xref:System.Windows.TriggerCollection>, che implementa <xref:System.Collections.IList>. Non è necessario creare un'istanza di un <xref:System.Windows.TriggerCollection> elemento oggetto nel markup. Al contrario, è necessario specificare uno o più elementi <xref:System.Windows.Trigger> come elementi all'interno dell'elemento proprietà `Style.Triggers`, in cui <xref:System.Windows.Trigger> (o una classe derivata) è il tipo previsto come tipo di elemento per la <xref:System.Windows.TriggerCollection>fortemente tipizzata e implicita.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Una proprietà può essere sia un tipo di raccolta che la proprietà di contenuto XAML per il tipo e i tipi derivati, descritti nella sezione successiva di questo argomento.  
  
 Un elemento della raccolta implicita crea un membro nella rappresentazione ad albero logico, anche se non viene visualizzato nel markup come elemento. In genere, il costruttore del tipo padre esegue la creazione di un'istanza per la raccolta che è una delle relative proprietà e la raccolta inizialmente vuota diventa parte dell'albero degli oggetti.  
  
> [!NOTE]
> Le interfacce di elenco e dizionario generico (<xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IDictionary%602>) non sono supportate per il rilevamento della raccolta. Tuttavia, è possibile usare la classe <xref:System.Collections.Generic.List%601> come classe base, perché implementa direttamente <xref:System.Collections.IList> o <xref:System.Collections.Generic.Dictionary%602> come classe di base, perché implementa <xref:System.Collections.IDictionary> direttamente.  
  
 Nelle pagine di riferimento .NET per i tipi di raccolta, questa sintassi con l'omissione intenzionale dell'elemento oggetto per una raccolta viene occasionalmente indicata nelle sezioni della sintassi XAML come sintassi di raccolta implicita.  
  
 Fatta eccezione per l'elemento radice, ogni elemento oggetto in un file XAML annidato come elemento figlio di un altro elemento è effettivamente un elemento che è uno o entrambi i casi seguenti: un membro di una proprietà di raccolta implicita del relativo elemento padre , o un elemento che specifica il valore della proprietà di contenuto XAML per l'elemento padre (le proprietà del contenuto XAML verranno discusse in una sezione futura). In altre parole, la relazione degli elementi padre e degli elementi figlio in una pagina di markup è effettivamente un singolo oggetto alla radice e ogni elemento oggetto sotto la radice è una singola istanza che fornisce un valore della proprietà dell'elemento padre o uno degli elementi all'interno di un col colta che è anche un valore della proprietà del tipo di raccolta dell'elemento padre. Questo concetto a radice singola è comune con XML e viene spesso rinforzato nel comportamento delle API che caricano XAML, ad esempio <xref:System.Windows.Markup.XamlReader.Load%2A>.  
  
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
  
 Si noti che non è sempre possibile dichiarare esplicitamente la raccolta. Ad esempio, il tentativo di dichiarare <xref:System.Windows.TriggerCollection> in modo esplicito nell'esempio di <xref:System.Windows.Style.Triggers%2A> illustrato in precedenza avrebbe esito negativo. Per dichiarare in modo esplicito la raccolta, è necessario che la classe della raccolta supporti un costruttore senza parametri e <xref:System.Windows.TriggerCollection> non disponga di un costruttore senza parametri.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>Proprietà di contenuto XAML  
 La sintassi del contenuto XAML è una sintassi abilitata solo nelle classi che specificano il <xref:System.Windows.Markup.ContentPropertyAttribute> come parte della dichiarazione di classe. Il <xref:System.Windows.Markup.ContentPropertyAttribute> fa riferimento al nome della proprietà che è la proprietà di contenuto per quel tipo di elemento (incluse le classi derivate). Quando vengono elaborati da un processore XAML, qualsiasi elemento figlio o testo interno trovato tra i tag di apertura e di chiusura dell'elemento oggetto verrà assegnato come valore della proprietà di contenuto XAML per tale oggetto. È possibile specificare elementi della proprietà espliciti per la proprietà Content, ma questo utilizzo non viene in genere visualizzato nelle sezioni della sintassi XAML di .NET Reference. La tecnica esplicita/dettagliata presenta un valore occasionale per la chiarezza del markup o come una questione di stile di markup, ma in genere lo scopo di una proprietà di contenuto consiste nel semplificare il markup in modo che gli elementi che sono intuitivamente correlati come padre-figlio possano essere annidati direttamente. I tag dell'elemento proprietà per altre proprietà di un elemento non sono assegnati come "contenuto" per una definizione di linguaggio XAML Strict; vengono elaborati in precedenza nell'ordine di elaborazione del parser XAML e non sono considerati "Content".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>I valori delle proprietà di contenuto XAML devono essere contigui  
 Il valore di una proprietà di contenuto XAML deve essere specificato interamente prima o completamente dopo qualsiasi altro elemento di proprietà nell'elemento oggetto. Questo vale se il valore di una proprietà di contenuto XAML viene specificato come stringa o come uno o più oggetti. Il markup seguente, ad esempio, non analizza:  
  
```xaml  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Questa operazione non è sostanzialmente valida perché se questa sintassi è stata resa esplicita usando la sintassi dell'elemento Property per la proprietà Content, la proprietà Content verrebbe impostata due volte:  
  
```xaml  
<Button>  
  <Button.Content>I am a </Button.Content>  
  <Button.Background>Blue</Button.Background>  
  <Button.Content> blue button</Button.Content>  
</Button>  
```  
  
 Un esempio non valido è analogo a se la proprietà Content è una raccolta e gli elementi figlio vengono sparpagliati con gli elementi Property:  
  
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
 Per accettare più di un singolo elemento oggetto come contenuto, il tipo della proprietà di contenuto deve essere specificamente un tipo di raccolta. Analogamente alla sintassi dell'elemento Property per i tipi di raccolta, un processore XAML deve identificare i tipi che sono tipi di raccolta. Se un elemento ha una proprietà di contenuto XAML e il tipo della proprietà di contenuto XAML è una raccolta, non è necessario specificare il tipo di raccolta implicito nel markup come elemento oggetto e non è necessario specificare la proprietà di contenuto XAML come proprietà El autorità. Il modello di contenuto apparente nel markup ora può quindi avere più di un elemento figlio assegnato come contenuto. Di seguito è riportata la sintassi del contenuto per un <xref:System.Windows.Controls.Panel> classe derivata. Tutte <xref:System.Windows.Controls.Panel> classi derivate stabiliscono la proprietà di contenuto XAML da <xref:System.Windows.Controls.Panel.Children%2A>, che richiede un valore di tipo <xref:System.Windows.Controls.UIElementCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Si noti che nell'markup non è necessario né l'elemento Property per <xref:System.Windows.Controls.Panel.Children%2A> né l'elemento per l'<xref:System.Windows.Controls.UIElementCollection>. Si tratta di una funzionalità di progettazione di XAML in modo che gli elementi contenuti in modo ricorsivo che definiscono un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] siano rappresentati in modo più intuitivo come albero di elementi annidati con relazioni immediate tra gli elementi padre-figlio, senza tag dell'elemento proprietà o oggetti raccolta. In realtà, non è possibile specificare in modo esplicito <xref:System.Windows.Controls.UIElementCollection> nel markup come elemento oggetto, da progettazione. Poiché l'unico utilizzo previsto è come una raccolta implicita, <xref:System.Windows.Controls.UIElementCollection> non espone un costruttore pubblico senza parametri e pertanto non è possibile crearne un'istanza come elemento oggetto.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>Combinazione di elementi di proprietà ed elementi oggetto in un oggetto con una proprietà Content  
 La specifica XAML dichiara che un processore XAML può applicare che gli elementi oggetto usati per riempire la proprietà di contenuto XAML all'interno di un elemento oggetto devono essere contigui e non devono essere combinati. Questa restrizione sulla combinazione di elementi e contenuto della proprietà viene applicata dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] processori XAML.  
  
 È possibile avere un elemento oggetto figlio come primo markup immediato all'interno di un elemento oggetto. È quindi possibile introdurre elementi della proprietà. In alternativa, è possibile specificare uno o più elementi Property, quindi Content, quindi più elementi Property. Tuttavia, una volta che un elemento Property segue il contenuto, non è possibile introdurre altri contenuti, è possibile aggiungere solo elementi Property.  
  
 Questo requisito dell'ordine degli elementi di contenuto/proprietà non si applica al testo interno usato come contenuto. Tuttavia, è ancora un valido stile di markup per mantenere contiguo il testo interno, perché gli spazi vuoti significativi saranno difficili da rilevare visivamente nel markup se gli elementi della proprietà vengono sparpagliati con testo interno.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>Spazi dei nomi XAML  
 Nessuno degli esempi di sintassi precedenti ha specificato uno spazio dei nomi XAML diverso dallo spazio dei nomi XAML predefinito. Nelle applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipiche lo spazio dei nomi XAML predefinito viene specificato come spazio dei nomi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. È possibile specificare gli spazi dei nomi XAML diversi dallo spazio dei nomi XAML predefinito e usare comunque una sintassi simile. Tuttavia, in qualsiasi punto in cui una classe è denominata non accessibile nello spazio dei nomi XAML predefinito, il nome della classe deve essere preceduto dal prefisso dello spazio dei nomi XAML come mappato allo spazio dei nomi CLR corrispondente. Ad esempio, `<custom:Example/>` è la sintassi dell'elemento oggetto per creare un'istanza della classe `Example`, in cui lo spazio dei nomi CLR contenente tale classe (e possibilmente le informazioni sull'assembly esterno che contiene i tipi di supporto) è stato precedentemente mappato al prefisso `custom`.  
  
 Per altre informazioni sugli spazi dei nomi XAML, vedere [spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Estensioni di markup  
 XAML definisce un'entità di programmazione dell'estensione di markup che consente di eseguire l'escape dalla normale gestione del processore XAML dei valori di attributo stringa o degli elementi oggetto e rinvia l'elaborazione a una classe sottostante. Il carattere che identifica un'estensione di markup a un processore XAML quando si usa la sintassi dell'attributo è la parentesi graffa aperta ({), seguita da qualsiasi carattere diverso da una parentesi graffa chiusa (}). La prima stringa che segue la parentesi graffa aperta deve fare riferimento alla classe che fornisce il comportamento di estensione specifico, in cui il riferimento può omettere la sottostringa "extension" se tale sottostringa fa parte del nome della classe true. Successivamente, è possibile che venga visualizzato un solo spazio, quindi ogni carattere successivo viene usato come input dall'implementazione dell'estensione, fino a quando non viene rilevata la parentesi graffa di chiusura.  
  
 Nell'implementazione XAML di .NET viene utilizzata la <xref:System.Windows.Markup.MarkupExtension> classe astratta come base per tutte le estensioni di markup supportate da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], nonché da altri Framework o tecnologie. Le estensioni di markup che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementano in modo specifico sono spesso destinate a fornire un mezzo per fare riferimento ad altri oggetti esistenti o per creare riferimenti posticipati a oggetti che verranno valutati in fase di esecuzione. Ad esempio, una semplice data binding WPF viene eseguita specificando l'estensione di markup `{Binding}` al posto del valore che una particolare proprietà richiederebbe normalmente. Molte estensioni di markup WPF consentono la sintassi degli attributi per le proprietà in cui la sintassi di un attributo non sarebbe altrimenti possibile. Un oggetto <xref:System.Windows.Style>, ad esempio, è un tipo relativamente complesso che contiene una serie annidata di oggetti e proprietà. Gli stili in WPF vengono in genere definiti come una risorsa in una <xref:System.Windows.ResourceDictionary>e quindi fanno riferimento a una delle due estensioni di markup WPF che richiedono una risorsa. L'estensione di markup rinvia la valutazione del valore della proprietà a una ricerca di risorse e consente di fornire il valore della proprietà <xref:System.Windows.FrameworkElement.Style%2A>, accettando il tipo <xref:System.Windows.Style>, nella sintassi dell'attributo come nell'esempio seguente:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 `StaticResource` identifica la classe <xref:System.Windows.StaticResourceExtension> che fornisce l'implementazione dell'estensione di markup. La stringa successiva `MyStyle` viene utilizzata come input per il costruttore di <xref:System.Windows.StaticResourceExtension> non predefinito, in cui il parametro come tratto dalla stringa di estensione dichiara il <xref:System.Windows.ResourceKey>richiesto. `MyStyle` deve essere il valore [x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md) di un <xref:System.Windows.Style> definito come risorsa. L'utilizzo dell' [estensione di markup StaticResource](staticresource-markup-extension.md) richiede che la risorsa venga utilizzata per fornire il valore della proprietà <xref:System.Windows.Style> tramite la logica di ricerca di risorse statiche in fase di caricamento.  
  
 Per altre informazioni sulle estensioni di markup, vedere [Estensioni di markup e WPF XAML](markup-extensions-and-wpf-xaml.md). Per un riferimento alle estensioni di markup e ad altre funzionalità di programmazione XAML abilitate nell'implementazione generale di XAML .NET, vedere [spazio dei nomi XAML (x:) Funzionalità del linguaggio](../../../desktop-wpf/xaml-services/namespace-language-features.md). Per le estensioni di markup specifiche di WPF, vedere [estensioni XAML WPF](wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>Proprietà associate  
 Le proprietà associate sono un concetto di programmazione introdotto in XAML in cui le proprietà possono essere di proprietà e definite da un particolare tipo, ma impostate come attributi o elementi di proprietà su qualsiasi elemento. Lo scenario principale a cui sono destinate le proprietà è quello di consentire agli elementi figlio in una struttura di markup di segnalare le informazioni a un elemento padre senza richiedere un modello a oggetti ampiamente condiviso in tutti gli elementi. Viceversa, le proprietà associate possono essere utilizzate dagli elementi padre per segnalare le informazioni agli elementi figlio. Per altre informazioni sullo scopo delle proprietà associate e su come creare le proprie proprietà associate, vedere [Cenni preliminari sulle proprietà](attached-properties-overview.md)associate.  
  
 Le proprietà associate utilizzano una sintassi che è simile alla sintassi degli elementi di proprietà, in quanto si specifica anche un *typeName*. combinazione *PropertyName* . Vi sono due differenze importanti:  
  
- È possibile utilizzare il *typeName*. combinazione *PropertyName* anche quando si imposta una proprietà associata tramite la sintassi dell'attributo. Le proprietà associate sono l'unico caso in cui qualificare il nome della proprietà è un requisito in una sintassi di attributo.  
  
- È inoltre possibile utilizzare la sintassi dell'elemento proprietà per le proprietà associate. Tuttavia, per la sintassi tipica degli elementi proprietà, il *typeName* specificato è l'elemento oggetto che contiene l'elemento Property. Se si fa riferimento a una proprietà associata, *typeName* è la classe che definisce la proprietà associata, non l'elemento oggetto contenitore.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>Eventi associati  
 Gli eventi associati sono un altro concetto di programmazione introdotto in XAML in cui gli eventi possono essere definiti da un tipo specifico, ma i gestori possono essere collegati a qualsiasi elemento oggetto. Nell'implementazione di WOF, spesso il tipo che definisce un evento associato è un tipo statico che definisce un servizio e talvolta gli eventi collegati vengono esposti da un alias di evento indirizzato nei tipi che espongono il servizio. I gestori per gli eventi associati vengono specificati tramite la sintassi dell'attributo. Come per gli eventi associati, la sintassi dell'attributo viene espansa per gli eventi associati per consentire un *typeName*. utilizzo di *EventName* , dove *typeName* è la classe che fornisce le funzioni di accesso del gestore eventi `Add` e `Remove` per l'infrastruttura di eventi collegati e *EventName* è il nome dell'evento.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomia di un elemento radice XAML  
 La tabella seguente illustra un tipico elemento radice XAML suddiviso, che Mostra gli attributi specifici di un elemento radice:  
  
|||  
|-|-|  
|`<Page`|Apertura dell'elemento oggetto dell'elemento radice|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|Spazio dei nomi XAML predefinito ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)])|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|Spazio dei nomi XAML del linguaggio XAML|  
|`x:Class="ExampleNamespace.ExampleCode"`|Dichiarazione di classe parziale che connette il markup a qualsiasi code-behind definito per la classe parziale|  
|`>`|Fine dell'elemento oggetto per la radice. L'oggetto non è ancora chiuso perché l'elemento contiene elementi figlio|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>Utilizzi XAML facoltativi e non consigliati  
 Le sezioni seguenti descrivono gli utilizzi XAML tecnicamente supportati dai processori XAML, ma che producono un livello di dettaglio o altri problemi estetici che interferiscono con i file XAML rimanenti leggibili quando si sviluppano applicazioni che contengono origini XAML.  
  
### <a name="optional-property-element-usages"></a>Utilizzi facoltativi degli elementi proprietà  
 Gli utilizzi facoltativi degli elementi proprietà includono la scrittura esplicita delle proprietà del contenuto dell'elemento che il processore XAML considera implicite. Ad esempio, quando si dichiara il contenuto di una <xref:System.Windows.Controls.Menu>, è possibile scegliere di dichiarare in modo esplicito la raccolta di <xref:System.Windows.Controls.ItemsControl.Items%2A> del <xref:System.Windows.Controls.Menu> come tag dell'elemento proprietà `<Menu.Items>` e inserire ogni <xref:System.Windows.Controls.MenuItem> all'interno `<Menu.Items>`, anziché usare il comportamento del processore XAML implicito che tutti gli elementi figlio di un <xref:System.Windows.Controls.Menu> devono essere un <xref:System.Windows.Controls.MenuItem> e vengono inseriti nella raccolta di <xref:System.Windows.Controls.ItemsControl.Items%2A>. Talvolta gli utilizzi facoltativi possono aiutare a chiarire visivamente la struttura dell'oggetto come rappresentata nel markup. O a volte un utilizzo esplicito dell'elemento proprietà può evitare markup tecnicamente funzionale, ma visivamente confuso, ad esempio estensioni di markup annidate all'interno di un valore di attributo.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Attributi completi typeName. MemberName  
 *TypeName*. il formato *memberName* per un attributo funziona in modo più universale rispetto al solo caso di evento indirizzato. In altre situazioni, tuttavia, il form è superfluo ed è consigliabile evitarlo, se solo per motivi di stile di markup e leggibilità. Nell'esempio seguente ognuno dei tre riferimenti all'attributo <xref:System.Windows.Controls.Control.Background%2A> è completamente equivalente:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background` funziona perché la ricerca qualificata per la proprietà in <xref:System.Windows.Controls.Button> ha esito positivo (<xref:System.Windows.Controls.Control.Background%2A> è stata ereditata da Control) e <xref:System.Windows.Controls.Button> è la classe dell'elemento oggetto o di una classe di base. `Control.Background` funziona perché la classe <xref:System.Windows.Controls.Control> definisce effettivamente <xref:System.Windows.Controls.Control.Background%2A> e <xref:System.Windows.Controls.Control> è una classe di base <xref:System.Windows.Controls.Button>.  
  
 Tuttavia, il *typeName*seguente. L'esempio di form *memberName* non funziona e viene quindi visualizzato come commento:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label> è un'altra classe derivata di <xref:System.Windows.Controls.Control>e se è stato specificato `Label.Background` all'interno di un elemento <xref:System.Windows.Controls.Label> oggetto, l'utilizzo avrebbe avuto esito positivo. Tuttavia, poiché <xref:System.Windows.Controls.Label> non è la classe o la classe base di <xref:System.Windows.Controls.Button>, il comportamento del processore XAML specificato consiste nel elaborare `Label.Background` come proprietà associata. `Label.Background` non è una proprietà associata disponibile e questo utilizzo non riesce.  
  
### <a name="basetypenamemembername-property-elements"></a>Elementi della proprietà nomeTipoBase. MemberName  
 In modo analogo a come il *typeName*. il form *membroname* funziona per la sintassi degli attributi, un *nomeTipoBase*. la sintassi *memberName* funziona per la sintassi dell'elemento Property. Ad esempio, la sintassi seguente funziona:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 In questo caso, l'elemento Property è stato fornito come `Control.Background` anche se l'elemento Property era contenuto nell'`Button`.  
  
 Ma proprio come *typeName*. *memberName* form per gli attributi, *nomeTipoBase*. *memberName* è uno stile insufficiente nel markup ed è consigliabile evitarlo.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Funzionalità del linguaggio dello spazio dei nomi XAML (x:)](../../../desktop-wpf/xaml-services/namespace-language-features.md)
- [Estensioni XAML WPF](wpf-xaml-extensions.md)
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [TypeConverter e XAML](typeconverters-and-xaml.md)
- [Classi XAML e personalizzate per WPF](xaml-and-custom-classes-for-wpf.md)
