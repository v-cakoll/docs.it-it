---
title: Descrizione dettagliata della sintassi XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0aa85c9ec6e6b911444b07a4169dc769ac4df816
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xaml-syntax-in-detail"></a>Descrizione dettagliata della sintassi XAML
In questo argomento definisce le condizioni che consentono di descrivere gli elementi della sintassi XAML. Questi termini vengono utilizzati di frequente in tutto il resto della documentazione, sia per la documentazione di WPF in modo specifico e per gli altri modelli che utilizzano XAML o i concetti di base XAML abilitati per il supporto del linguaggio XAML a livello di System. Xaml. In questo argomento consente di espandere la terminologia di base presentata nell'argomento [Panoramica di XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  

  
<a name="the_xaml_language_specification"></a>   
## <a name="the-xaml-language-specification"></a>Specifica del linguaggio XAML  
 La terminologia di sintassi XAML definita in questa sezione è anche definita o a cui fa riferimento nella specifica del linguaggio XAML. XAML è un linguaggio basato su XML e segue o si espande sul regole strutturali XML. Parte della terminologia viene condiviso da o si basa sulla terminologia comunemente utilizzata per descrivere il linguaggio XML o il modello a oggetti documento XML.  
  
 Per ulteriori informazioni sulla specifica del linguaggio XAML, scaricare [ \[MS-XAML\] ](http://go.microsoft.com/fwlink/?LinkId=114525) da Microsoft Download Center.  
  
<a name="xaml_and_clr"></a>   
## <a name="xaml-and-clr"></a>Common Language Runtime e XAML  
 XAML è un linguaggio di markup. Il [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)], come suggerito dal nome, consente l'esecuzione di runtime. XAML non è da solo uno dei linguaggi comuni utilizzati direttamente dal runtime CLR. In alternativa, può essere considerato di XAML come il proprio sistema di tipi di supporto. Il sistema di analisi XAML specifico che viene usato in WPF si basa su CLR e il sistema di tipi CLR. Tipi di XAML vengono eseguito il mapping a tipi CLR per creare un'istanza di una rappresentazione in fase di esecuzione quando viene analizzato il codice XAML per WPF. Per questo motivo, il resto della discussione di sintassi in questo documento includerà riferimenti al sistema di tipi CLR, anche se non le discussioni sintassi equivalente della specifica del linguaggio XAML. (Per ogni livello di specifica del linguaggio XAML, tipi di XAML potrebbero eseguire il mapping a qualsiasi altro sistema di tipi, che non deve essere CLR, ma che richiedono la creazione e utilizzo di un parser XAML.)  
  
#### <a name="members-of-types-and-class-inheritance"></a>Membri di tipi ed ereditarietà di classe  
 Le proprietà e gli eventi vengono visualizzati come membri XAML di un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipo spesso vengono ereditate dai tipi di base. Ad esempio, si consideri l'esempio: `<Button Background="Blue" .../>`. Il <xref:System.Windows.Controls.Control.Background%2A> proprietà non è una proprietà dichiarata immediatamente sulla <xref:System.Windows.Controls.Button> classe, se analizzano la definizione della classe, i risultati della reflection o la documentazione. In alternativa, <xref:System.Windows.Controls.Control.Background%2A> viene ereditato dalla base <xref:System.Windows.Controls.Control> classe.  
  
 Il comportamento dell'ereditarietà di classe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementi XAML è un allontanamento significativo dall'interpretazione del markup XML schema-applicata in. Ereditarietà di classe possono essere complesse, in particolare quando le classi di base intermedie sono astratte o interfacce sono coinvolti. Si tratta di un motivo per cui il set di elementi XAML e dei relativi attributi consentiti è difficile da rappresentare in modo accurato e completo con i tipi di schema che viene generalmente utilizzato per [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] di programmazione, ad esempio formato XSD o DTD. Un altro motivo è che estendibilità e funzionalità di mapping dei tipi del linguaggio XAML precludono completezza di qualsiasi rappresentazione fissa tipi consentiti e i membri.  
  
<a name="object_element_syntax"></a>   
## <a name="object-element-syntax"></a>Sintassi degli elementi oggetto  
 *La sintassi dell'elemento dell'oggetto* è la sintassi del markup XAML che crea un'istanza di una classe CLR o una struttura dichiarando un elemento XML. Questa sintassi è simile alla sintassi di elemento di altri linguaggi di markup, ad esempio HTML. Sintassi dell'elemento oggetto inizia con una parentesi uncinata (\<), seguito immediatamente dal nome del tipo di classe o struttura viene creata un'istanza. Zero o più spazi possono seguire il nome del tipo e possono anche essere dichiarati zero o più attributi dell'elemento oggetto, con uno o più spazi, separare ogni nome di attributo = coppia "value". Infine, uno dei seguenti deve essere true:  
  
-   L'elemento e il tag deve essere chiuso da una barra (/) seguita immediatamente da una parentesi uncinata chiusa (>).  
  
-   Il tag di apertura deve essere completato da una parentesi uncinata chiusa (>). Altri elementi oggetto, proprietà o testo interno, è possibile seguire il tag di apertura. Il contenuto esatto che è possibile qui in genere è vincolato dal modello a oggetti dell'elemento. L'equivalente di tag di chiusura per l'elemento oggetto deve anche nell'area di nidificazione appropriata e bilanciato con altre coppie di tag di apertura e chiusura.  
  
 XAML come implementato per .NET è un set di regole che eseguono il mapping in tipi di attributi di proprietà o eventi e spazi dei nomi XAML per gli spazi dei nomi CLR e assembly, gli elementi oggetto. Per WPF e .NET Framework, gli elementi oggetto XAML eseguire il mapping a [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] tipi come definito nell'assembly di riferimento e gli attributi vengono associati ai membri di tali tipi. Quando si fa riferimento un tipo CLR in XAML, è possibile accedere ai membri ereditati di tale tipo anche.  
  
 Ad esempio, l'esempio seguente è la sintassi degli elementi oggetto che crea una nuova istanza del <xref:System.Windows.Controls.Button> classe e viene specificato un <xref:System.Windows.FrameworkElement.Name%2A> attributo e un valore per l'attributo:  
  
 [!code-xaml[XAMLOvwSupport#SyntaxOE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxoe)]  
  
 L'esempio seguente è la sintassi degli elementi oggetto che include anche la sintassi di proprietà di contenuto XAML. Il testo interno contenuto verrà utilizzato per impostare il <xref:System.Windows.Controls.TextBox> le proprietà di contenuto XAML, <xref:System.Windows.Controls.TextBox.Text%2A>.  
  
 [!code-xaml[XAMLOvwSupport#ThisIsATextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#thisisatextbox)]  
  
### <a name="content-models"></a>Modelli di contenuto  
 Una classe può supportare un utilizzo come elemento oggetto XAML in termini di sintassi, ma tale elemento funzionerà correttamente in un'applicazione o pagina solo quando viene inserito in una posizione prevista di un albero del modello o un elemento contenuto globale. Ad esempio, un <xref:System.Windows.Controls.MenuItem> devono in genere essere inserite solo come elemento figlio di un <xref:System.Windows.Controls.Primitives.MenuBase> classe derivata, ad esempio <xref:System.Windows.Controls.Menu>. Modelli per elementi specifici sono documentati come parte delle note nelle pagine delle classi per i controlli e altro contenuto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le classi che possono essere utilizzate come elementi XAML.  
  
<a name="properties_of_object_elements"></a>   
## <a name="properties-of-object-elements"></a>Proprietà degli elementi oggetto  
 Proprietà in XAML vengono impostate da una varietà di sintassi possibili. È possibile utilizzare la sintassi per una particolare proprietà varia in base alle caratteristiche di sistema tipo sottostante della proprietà da impostare.  
  
 Impostando i valori delle proprietà, aggiungere le funzionalità o caratteristiche agli oggetti in cui si trovano nell'oggetto grafico fase di esecuzione. Lo stato iniziale dell'oggetto creato da un elemento oggetto si basa sul comportamento di costruttore predefinito. In genere, l'applicazione utilizzerà un valore diverso da un'istanza completamente predefinita di qualsiasi oggetto specificato.  
  
<a name="attribute_syntax_properties"></a>   
## <a name="attribute-syntax-properties"></a>Sintassi per attributi (proprietà)  
 La sintassi degli attributi è la sintassi del markup XAML che imposta un valore per una proprietà dichiarando un attributo in un elemento oggetto esistente. Il nome di attributo deve corrispondere il nome del membro CLR della proprietà della classe che supporta l'elemento oggetto pertinente. Il nome dell'attributo è seguito da un operatore di assegnazione (=). Il valore dell'attributo deve essere una stringa racchiusa tra virgolette.  
  
> [!NOTE]
>  È possibile utilizzare le virgolette alterne per inserire un segno di virgolette letterale all'interno di un attributo. Per l'istanza è possibile utilizzare le virgolette singole come mezzo per dichiarare una stringa che contiene un carattere di virgoletta doppia all'interno di esso. Se si utilizzano le virgolette singole o doppie, è necessario utilizzare una coppia corrispondente per l'apertura e chiusura di stringa del valore di attributo. Sono disponibili anche le sequenze di escape o altre tecniche per risolvere le restrizioni relative ai caratteri imposto da qualsiasi particolare sintassi XAML. Vedere [entità carattere XML e XAML](../../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md).  
  
 Per poter essere impostata tramite la sintassi degli attributi, una proprietà deve essere pubblica e deve essere scrivibile. Il valore della proprietà nel sistema di tipi di backup deve essere un tipo di valore o deve essere un tipo riferimento che può essere creata un'istanza o a cui fa riferimento un processore XAML durante l'accesso del tipo di supporto.  
  
 Per gli eventi XAML di WPF, l'evento che viene fatto riferimento come il nome dell'attributo deve essere pubblici e dispone di un delegato pubblico.  
  
 La proprietà o evento deve essere un membro della classe o struttura che viene creata un'istanza per l'elemento oggetto contenitore.  
  
### <a name="processing-of-attribute-values"></a>Elaborazione dei valori di attributo  
 Il valore stringa contenuto all'interno delle parentesi e virgolette di chiusura viene elaborato da un processore XAML. Per le proprietà, il comportamento di elaborazione predefinito è determinato dal tipo della proprietà CLR sottostante.  
  
 Il valore dell'attributo viene inserito uno dei seguenti, utilizzando questo ordine di elaborazione:  
  
1.  Se il processore XAML rileva una parentesi graffa o un elemento oggetto che deriva da <xref:System.Windows.Markup.MarkupExtension>, quindi l'estensione di markup di cui viene fatto riferimento viene valutata per prima anziché il valore sotto forma di stringa di elaborazione e l'oggetto restituito dall'estensione di markup viene utilizzato come il valore. In molti casi, l'oggetto restituito da un'estensione di markup sarà un riferimento a un oggetto esistente o un'espressione che rinvia la valutazione in fase di esecuzione, non è un oggetto appena creata un'istanza.  
  
2.  Se la proprietà è dichiarata con un oggetto con attributi <xref:System.ComponentModel.TypeConverter>, o il tipo di valore di tale proprietà viene dichiarato con un oggetto con attributi <xref:System.ComponentModel.TypeConverter>, il valore di stringa dell'attributo viene inviato al convertitore di tipi come input una conversione e restituirà il convertitore di un nuova istanza dell'oggetto.  
  
3.  Se è presente alcun <xref:System.ComponentModel.TypeConverter>, viene tentata una conversione diretta al tipo di proprietà. Questo livello finale è una conversione diretta in corrispondenza del valore di parser nativo tra tipi primitivi del linguaggio XAML, o un controllo per i nomi delle costanti denominate in un'enumerazione (il parser accede quindi a valori corrispondenti).  
  
#### <a name="enumeration-attribute-values"></a>Valori di attributo di enumerazione  
 Le enumerazioni in XAML vengono elaborate in modo intrinseco dai parser XAML e i membri di un'enumerazione devono essere specificati, specificando il nome della stringa di una delle costanti denominate dell'enumerazione.  
  
 Per i valori di enumerazione nonflag, il comportamento nativo è per elaborare la stringa di un valore di attributo e che viene risolta in uno dei valori di enumerazione. Non si specifica l'enumerazione nel formato *enumerazione*. *Valore*, come avviene nel codice. È invece necessario specificare solo *valore*, e *enumerazione* viene dedotto dal tipo di proprietà sta impostando. Se si specifica un attributo di *enumerazione*. *Valore* , non verrà risolto correttamente.  
  
 Per le enumerazioni, il comportamento dipende il <xref:System.Enum.Parse%2A?displayProperty=nameWithType> metodo. È possibile specificare più valori per un'enumerazione di flag per flag separando ogni valore con una virgola. Tuttavia, è possibile combinare i valori di enumerazione non basati su flag. Ad esempio, è possibile utilizzare la sintassi della virgola per tentare di creare un <xref:System.Windows.Trigger> che agisce su più condizioni di un'enumerazione:  
  
```  
<!--This will not compile, because Visibility is not a flagwise enumeration.-->  
...  
<Trigger Property="Visibility" Value="Collapsed,Hidden">  
  <Setter ... />  
</Trigger>  
...  
```  
  
 Le enumerazioni che supporta gli attributi che possono essere impostati in XAML sono rare in WPF. Tuttavia, è un'enumerazione di questo tipo è <xref:System.Windows.Media.StyleSimulations>. È possibile, ad esempio, utilizzare la sintassi delimitato da virgole di attributi basata su flag per modificare l'esempio fornito nella sezione Osservazioni per il <xref:System.Windows.Documents.Glyphs> classe; `StyleSimulations = "BoldSimulation"` potrebbe diventare `StyleSimulations = "BoldSimulation,ItalicSimulation"`. <xref:System.Windows.Input.KeyBinding.Modifiers%2A?displayProperty=nameWithType>è un'altra proprietà in cui può essere specificato più di un valore di enumerazione. Tuttavia, questa proprietà è un caso speciale, perché il <xref:System.Windows.Input.ModifierKeys> enumerazione supporta il proprio convertitore. Il convertitore di tipi per i modificatori utilizza un segno più (+) come delimitatore, anziché una virgola (,). Questa conversione supporta la sintassi più tradizionale per rappresentare le combinazioni di tasti nella programmazione di Microsoft Windows, ad esempio "Ctrl + Alt".  
  
### <a name="properties-and-event-member-name-references"></a>Le proprietà e i riferimenti al nome membro evento  
 Quando si specifica un attributo, è possibile fare riferimento a qualsiasi proprietà o evento esistente come membro del tipo CLR che è creata un'istanza per l'elemento oggetto contenitore.  
  
 In alternativa, è possibile fare riferimento a una proprietà associata o evento associato, indipendente dell'elemento oggetto contenitore. (Le proprietà associate verranno esaminate in una sezione successiva).  
  
 È inoltre possibile assegnare un nome qualsiasi evento di qualsiasi oggetto che è possibile accedere tramite lo spazio dei nomi predefinito utilizzando un *typeName*. *evento* nome parziale, questa sintassi supporta l'associazione di gestori per gli eventi indirizzati in cui il gestore ha lo scopo di gestire l'evento indirizzato da elementi figlio, ma l'elemento padre non tale evento è presente nella tabella dei membri. Questa sintassi è simile alla sintassi di un evento associato, ma in questo caso l'evento non è un evento associato effettivo. Al contrario, si fa riferimento a un evento con un nome completo. Per ulteriori informazioni, vedere [indirizzato Cenni preliminari sugli eventi](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Per alcuni scenari, i nomi delle proprietà vengono talvolta forniti come valore di un attributo, anziché il nome dell'attributo. Nome di tale proprietà può includere anche qualificatori, ad esempio la proprietà specificata nel formato *ownerType*. *dependencyPropertyName*. Questo scenario è comune quando si scrivono stili o modelli in XAML. Le regole di elaborazione per i nomi di proprietà forniti come valore di attributo sono diverse e dipendono dal tipo di proprietà da impostare o dai comportamenti di particolari sottosistemi WPF. Per informazioni dettagliate, vedere [stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
 Un altro utilizzo per i nomi delle proprietà è quando un valore di attributo descrive una relazione di proprietà property. Questa funzionalità viene utilizzata per il data binding e per le destinazioni di storyboard ed è abilitata per la <xref:System.Windows.PropertyPath> classe e il relativo convertitore di tipo. Per una descrizione più completa della semantica di ricerca, vedere [sintassi di PropertyPath XAML](../../../../docs/framework/wpf/advanced/propertypath-xaml-syntax.md).  
  
<a name="property_element_syntax"></a>   
## <a name="property-element-syntax"></a>Sintassi per gli elementi proprietà  
 *La sintassi degli elementi* certi versi dalle regole di sintassi di base XML per gli elementi. Nel codice XML, il valore di un attributo è una stringa di fatto, con la sola possibile variazione viene utilizzato il formato di codifica di stringa. In XAML, è possibile assegnare altri elementi dell'oggetto come valore di una proprietà. Questa funzionalità è abilitata per la sintassi. Anziché la proprietà viene specificata come un attributo all'interno del tag di elemento, la proprietà viene specificata utilizzando un elemento di apertura tag *nomeTipoElemento*. *propertyName* modulo, interno è specificato il valore della proprietà e quindi viene chiuso l'elemento proprietà.  
  
 In particolare, la sintassi inizia con una parentesi uncinata (\<), seguito immediatamente dal nome del tipo di classe o struttura che la sintassi è contenuta all'interno. Questo è immediatamente seguito da un punto singolo (.), quindi dal nome di una proprietà, quindi da una parentesi uncinata chiusa (>). Come con la sintassi degli attributi, tale proprietà deve esistere all'interno i membri pubblici dichiarati nel tipo specificato. Il valore da assegnare alla proprietà è contenuto all'interno dell'elemento proprietà. In genere, il valore viene assegnato come uno o più elementi oggetto, perché gli oggetti come valori è lo scenario che la sintassi degli elementi è dedicato alla risoluzione. Infine, un tag di chiusura equivalente specificando lo stesso *nomeTipoElemento*. *propertyName* combinazione deve essere specificata, in opportunamente annidato e bilanciato con gli altri tag di elemento.  
  
 Ad esempio, ecco la sintassi degli elementi di proprietà per il <xref:System.Windows.FrameworkElement.ContextMenu%2A> proprietà di un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[XAMLOvwSupport#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#contextmenu)]  
  
 Il valore all'interno di un elemento proprietà può anche essere fornito come testo interno, nei casi in cui il tipo della proprietà specificato è un tipo di valore primitivo, ad esempio <xref:System.String>, o un'enumerazione in cui viene specificato un nome. Questi due utilizzi sono molto comuni, in quanto ognuno di questi casi può anche usare una sintassi più semplice per gli attributi. Uno scenario per la compilazione di un elemento proprietà con una stringa per le proprietà che non sono proprietà di contenuto XAML, ma comunque vengono usate per la rappresentazione testo dell'interfaccia utente, e sono necessari determinati elementi di spazio, ad esempio i caratteri di avanzamento riga venga visualizzato nel testo dell'interfaccia utente. La sintassi degli attributi non è possibile mantenere gli avanzamenti riga, ma la sintassi degli elementi può, in modo che il mantenimento degli spazi vuoti significativi sia attivo (per informazioni dettagliate, vedere [elaborazione degli spazi vuoti in XAML](../../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)). È un altro scenario in modo che [direttiva X:UID](../../../../docs/framework/xaml-services/x-uid-directive.md) può essere applicato all'elemento property e contrassegnare quindi il valore all'interno come un valore che deve essere localizzato in WPF BAML output o altre tecniche.  
  
 Un elemento di proprietà non è rappresentato nell'albero logico WPF. Un elemento di proprietà è semplicemente una sintassi particolare per l'impostazione di una proprietà e non è un elemento che dispone di un'istanza o un oggetto sostegno. (Per informazioni dettagliate sul concetto di struttura ad albero logica, vedere [alberi in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).)  
  
 Per le proprietà in cui sono supportate sia l'attributo proprietà la sintassi dell'elemento, in genere le due sintassi hanno lo stesso risultato, anche se possono variare leggermente sfumature, ad esempio gestione degli spazi vuoti tra i due tipi di sintassi.  
  
<a name="collection_syntax"></a>   
## <a name="collection-syntax"></a>Sintassi per raccolte  
 La specifica di XAML richiede che le implementazioni del processore XAML per identificare le proprietà in cui il tipo di valore è una raccolta. Implementazione del processore XAML generale in .NET è basato sul codice gestito e CLR e identifica i tipi di raccolta tramite uno dei valori seguenti:  
  
-   Il tipo implementa <xref:System.Collections.IList>.  
  
-   Il tipo implementa <xref:System.Collections.IDictionary>.  
  
-   Tipo deriva da <xref:System.Array> (per ulteriori informazioni sulle matrici in XAML, vedere [estensione di Markup X:Array](../../../../docs/framework/xaml-services/x-array-markup-extension.md).)  
  
 Se il tipo di una proprietà è una raccolta, il tipo di raccolta dedotto non necessario essere specificato nel markup come elemento oggetto. Gli elementi che devono essere gli elementi nella raccolta vengono invece specificati come uno o più elementi figlio dell'elemento proprietà. Ognuno di questi elementi viene valutata a un oggetto durante il caricamento e aggiunto alla raccolta chiamando il `Add` dell'insieme implicita. Ad esempio, il <xref:System.Windows.Style.Triggers%2A> proprietà di <xref:System.Windows.Style> accetta il tipo di raccolta specializzato <xref:System.Windows.TriggerCollection>, che implementa l'interfaccia <xref:System.Collections.IList>. Non è necessario creare un'istanza di un <xref:System.Windows.TriggerCollection> elemento oggetto nel markup. È invece necessario specificare uno o più <xref:System.Windows.Trigger> elementi come elementi all'interno di `Style.Triggers` elemento proprietà, in cui <xref:System.Windows.Trigger> (o una classe derivata) è il tipo previsto come tipo di elemento fortemente tipizzato e implicito <xref:System.Windows.TriggerCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxPECollection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/Page1.xaml#syntaxpecollection)]  
  
 Una proprietà può essere un tipo di raccolta e la proprietà di contenuto XAML per quel tipo e tipi derivati, illustrata nella sezione successiva di questo argomento.  
  
 Un elemento insieme implicito crea un membro nella rappresentazione dell'albero logico, anche se non viene visualizzato nel markup come un elemento. In genere il costruttore del tipo padre esegue la creazione dell'istanza per la raccolta che è una delle relative proprietà e la raccolta inizialmente vuota diventa parte dell'albero degli oggetti.  
  
> [!NOTE]
>  L'elenco e il dizionario di interfacce generiche (<xref:System.Collections.Generic.IList%601> e <xref:System.Collections.Generic.IDictionary%602>) non sono supportate per il rilevamento della raccolta. Tuttavia, è possibile utilizzare il <xref:System.Collections.Generic.List%601> classe come classe base, poiché implementa <xref:System.Collections.IList> , direttamente o <xref:System.Collections.Generic.Dictionary%602> come classe base, perché implementa <xref:System.Collections.IDictionary> direttamente.  
  
 Nelle pagine di riferimento di .NET per tipi di raccolta, questa sintassi con l'omissione intenzionale dell'elemento oggetto per una raccolta si nota occasionalmente nelle sezioni di sintassi di XAML come sintassi raccolta implicita.  
  
 Fatta eccezione per l'elemento radice, ogni elemento dell'oggetto in un file XAML come elemento figlio di un altro elemento nidificato è effettivamente uno o entrambi i casi seguenti: un membro di una proprietà di raccolta implicita del relativo elemento padre , o un elemento che specifica il valore della proprietà di contenuto XAML per l'elemento padre (contenuto in una sezione successiva verranno descritte le proprietà XAML). In altre parole, la relazione tra gli elementi padre e figlio in una pagina di markup è realmente un singolo oggetto alla radice e ogni elemento oggetto sotto la radice è una singola istanza che fornisce un valore di proprietà dell'elemento padre, o uno degli elementi all'interno di una colonna PROSSIMITA che è anche un valore della proprietà tipo di raccolta dell'elemento padre. Questo concetto di radice singola è comune in XML e spesso è consolidato nel comportamento delle API che caricano XAML, ad esempio <xref:System.Windows.Markup.XamlReader.Load%2A>.  
  
 Nell'esempio seguente viene illustrata una sintassi con l'elemento oggetto per una raccolta (<xref:System.Windows.Media.GradientStopCollection>) specificato in modo esplicito.  
  
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
  
 Si noti che non sempre è possibile dichiarare in modo esplicito la raccolta. Ad esempio, il tentativo di dichiarare <xref:System.Windows.TriggerCollection> in modo esplicito illustrato in precedenza <xref:System.Windows.Style.Triggers%2A> esempio avrà esito negativo. Dichiarare in modo esplicito la raccolta richiede che la classe di raccolta deve supportare un costruttore predefinito e <xref:System.Windows.TriggerCollection> non dispone di un costruttore predefinito.  
  
<a name="xaml_content_properties"></a>   
## <a name="xaml-content-properties"></a>Proprietà di contenuto XAML  
 Sintassi del contenuto XAML è una sintassi che è disponibile solo nelle classi che specificano il <xref:System.Windows.Markup.ContentPropertyAttribute> come parte della relativa dichiarazione di classe. Il <xref:System.Windows.Markup.ContentPropertyAttribute> fa riferimento il nome della proprietà che è la proprietà di contenuto per il tipo di elemento (incluse le classi derivate). Quando vengono elaborati da un processore XAML, qualsiasi elemento figlio o testo interno rilevato tra il tag di apertura e chiusura dell'elemento oggetto verrà assegnato come valore della proprietà di contenuto XAML dell'oggetto. È consentito specificare gli elementi di proprietà espliciti per la proprietà di contenuto, ma questo utilizzo non è in genere illustrato nelle sezioni di sintassi di XAML in riferimento a .NET. La tecnica esplicita/dettagliata ha un valore occasionale per maggiore chiarezza markup o lo stile del markup, ma in genere di una proprietà di contenuto si desidera semplificare il markup in modo che gli elementi correlati in modo intuitivo come padre-figlio possono essere annidati direttamente. Tag di elemento di proprietà per le altre proprietà in un elemento non vengono assegnati come "contenuto" per una definizione del linguaggio XAML strict; essi vengono elaborati in precedenza nell'ordine di elaborazione del parser XAML e non sono considerati "contenuto".  
  
### <a name="xaml-content-property-values-must-be-contiguous"></a>I valori di proprietà di contenuto XAML devono essere contigui  
 Il valore di una proprietà di contenuto XAML deve essere assegnato completamente prima o completamente dopo qualsiasi altro elemento proprietà in quell'elemento oggetto. Ciò è vero se il valore di una proprietà di contenuto XAML è specificato come stringa o come uno o più oggetti. Non è ad esempio, analizzare il markup seguente:  
  
```  
<Button>I am a   
  <Button.Background>Blue</Button.Background>  
  blue button</Button>  
```  
  
 Questa situazione non è consentita perché se questa sintassi sono stata apportata esplicita tramite la sintassi degli elementi per la proprietà di contenuto, quindi la proprietà di contenuto sarebbe stato possibile impostare due volte:  
  
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
 Per accettare più di un elemento singolo oggetto contenuto, il tipo della proprietà di contenuto deve essere specificamente un tipo di raccolta. Simile alla sintassi degli elementi di proprietà per i tipi di raccolta, un processore XAML deve identificare i tipi che sono tipi di raccolta. Se un elemento contiene una proprietà di contenuto XAML e il tipo della proprietà di contenuto XAML è una raccolta, il tipo di raccolta implicito non deve essere specificato nel markup come elemento oggetto e la proprietà di contenuto XAML non dovrà essere specificato come un elenco di eventi di proprietà ement. Pertanto il modello di contenuto apparente nel markup ora possibile avere più di un elemento figlio assegnato come contenuto. Di seguito è riportata la sintassi del contenuto per un <xref:System.Windows.Controls.Panel> classe derivata. Tutti <xref:System.Windows.Controls.Panel> classi derivate di stabilire la proprietà di contenuto XAML come <xref:System.Windows.Controls.Panel.Children%2A>, che richiede un valore di tipo <xref:System.Windows.Controls.UIElementCollection>.  
  
 [!code-xaml[XAMLOvwSupport#SyntaxContent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page5.xaml#syntaxcontent)]  
  
 Si noti che né l'elemento di proprietà per <xref:System.Windows.Controls.Panel.Children%2A> né l'elemento per il <xref:System.Windows.Controls.UIElementCollection> è necessaria nel markup. Questa è una funzionalità di progettazione di XAML in modo che in modo ricorsivo contiene elementi che definiscono un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sono rappresentati in modo più intuitivo come una struttura ad albero di elementi annidati con relazioni padre-figlio immediati, senza sono frapposti tag di elemento di proprietà o oggetti della raccolta. In effetti, <xref:System.Windows.Controls.UIElementCollection> non può essere specificato in modo esplicito nel markup come elemento oggetto in base alla progettazione. Poiché il solo utilizzo previsto è come raccolta implicita, <xref:System.Windows.Controls.UIElementCollection> non espone un costruttore predefinito pubblico e pertanto non può essere un'istanza come elemento oggetto.  
  
### <a name="mixing-property-elements-and-object-elements-in-an-object-with-a-content-property"></a>La combinazione di elementi di proprietà e gli elementi oggetto in un oggetto con una proprietà di contenuto  
 La specifica di XAML dichiara che un processore XAML possa imporre che gli elementi oggetto utilizzati per compilare la proprietà di contenuto XAML all'interno di un elemento oggetto devono essere contigui e non devono essere combinati. Questa restrizione che limita la combinazione di elementi di proprietà e il contenuto viene applicata per il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] processori XAML.  
  
 È possibile avere un elemento oggetto figlio come primo markup all'interno di un elemento dell'oggetto. È possibile introdurre elementi proprietà. In alternativa, è possibile specificare uno o più elementi di proprietà, quindi e altri elementi proprietà. Tuttavia, dopo un elemento proprietà dopo il contenuto, è possibile inserire ulteriore contenuto, è possibile aggiungere solo gli elementi di proprietà.  
  
 Questo contenuto / proprietà elemento ordine requisito si applica al testo interno utilizzato come contenuto. Tuttavia, è ancora uno stile consigliabile mantenere il testo interno contigue, perché saranno difficili rilevare visivamente nel markup se gli elementi di proprietà vengono intercalati con testo interno degli spazi vuoti significativi.  
  
<a name="xaml_namespaces"></a>   
## <a name="xaml-namespaces"></a>Spazi dei nomi XAML  
 Nessuno degli esempi di sintassi precedente specificato uno spazio dei nomi XAML diverso da spazio dei nomi XAML predefinito. In genere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applicazioni, il valore predefinito di spazio dei nomi XAML specificato è il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dello spazio dei nomi. È possibile specificare spazi dei nomi XAML diversi lo spazio dei nomi XAML predefinito e continuare a utilizzare la sintassi seguente. Quindi, in qualsiasi punto in cui viene denominata una classe che non è accessibile all'interno dello spazio dei nomi XAML predefinito, il nome della classe deve essere preceduto con il prefisso dello spazio dei nomi XAML mappato allo spazio dei nomi CLR corrispondente. Ad esempio, `<custom:Example/>` è la sintassi degli elementi oggetto per creare un'istanza del `Example` (classe), in cui lo spazio dei nomi CLR che contiene tale classe (ed eventualmente le informazioni di assembly esterno che contiene i tipi di supporto) è stato precedentemente mappato per il `custom` prefisso.  
  
 Per ulteriori informazioni sugli spazi dei nomi XAML, vedere [spazi dei nomi XAML e Namespace Mapping per XAML di WPF](../../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
<a name="markup_extensions"></a>   
## <a name="markup-extensions"></a>Estensioni di markup  
 Codice XAML definisce un'estensione di markup entità costituisce un'alternativa dalla normale gestione processore XAML di valori di attributo di stringa o gli elementi oggetto, che rinvia l'elaborazione di una classe di supporto di programmazione. Il carattere che identifica un'estensione di markup per un processore XAML quando si utilizza la sintassi degli attributi è la parentesi graffa di apertura ({), seguita da qualsiasi carattere diverso da una parentesi graffa di chiusura (}). La prima stringa segue la parentesi graffa di apertura deve fare riferimento la classe che fornisce il comportamento di estensione specifica, in cui il riferimento è possibile omettere la sottostringa "Extension", se tale sottostringa fa parte del nome della classe true. Successivamente, può risultare uno spazio, e quindi ogni carattere successivo viene utilizzato come input per l'implementazione dell'estensione, fino a quando non viene rilevata la parentesi graffa di chiusura.  
  
 Usa l'implementazione XAML di .NET di <xref:System.Windows.Markup.MarkupExtension> classe astratta come base per tutte le estensioni di markup supportate da [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] nonché altri framework o tecnologie. Le estensioni di markup che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementa specificatamente è spesso destinate a fornire un mezzo per fare riferimento ad altri oggetti esistenti o per rinviare i riferimenti agli oggetti che verranno valutati in fase di esecuzione. Ad esempio, un'associazione dati WPF semplice specificando il `{Binding}` estensione di markup al posto del valore che in genere richiede una particolare proprietà. Molte delle estensioni di markup WPF consentono una sintassi degli attributi per le proprietà in cui una sintassi degli attributi non sarebbe possibile. Ad esempio, un <xref:System.Windows.Style> oggetto è un tipo relativamente complesso che contiene una serie di proprietà e oggetti nidificata. In WPF vengono in genere definiti come una risorsa in un <xref:System.Windows.ResourceDictionary>e quindi viene fatto riferimento tramite una delle due estensioni di markup WPF che richiedono una risorsa. L'estensione di markup posticipa la valutazione del valore della proprietà da una ricerca di risorse e consente di specificare il valore della <xref:System.Windows.FrameworkElement.Style%2A> proprietà, che accetta il tipo <xref:System.Windows.Style>, nell'attributo sintassi come illustrato nell'esempio seguente:  
  
 `<Button Style="{StaticResource MyStyle}">My button</Button>`  
  
 In questo caso, `StaticResource` identifica il <xref:System.Windows.StaticResourceExtension> classe che fornisce l'implementazione dell'estensione di markup. La stringa successiva `MyStyle` viene utilizzato come input per il valore non predefinito <xref:System.Windows.StaticResourceExtension> costruttore, in cui il parametro accettato dalla stringa di estensione dichiara l'oggetto richiesto <xref:System.Windows.ResourceKey>. `MyStyle`è previsto che il [X:Key](../../../../docs/framework/xaml-services/x-key-directive.md) valore di un <xref:System.Windows.Style> definito come risorsa. Il [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) utilizzo richiede che la risorsa venga utilizzata per fornire il <xref:System.Windows.Style> valore della proprietà tramite la logica di ricerca di risorse statiche in fase di caricamento.  
  
 Per altre informazioni sulle estensioni di markup, vedere [Estensioni di markup e WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md). Per informazioni di riferimento sulle estensioni di markup e altre funzionalità abilitate nell'implementazione XAML di .NET generale di programmazione XAML, vedere [Namespace XAML (x) Funzionalità del linguaggio](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md). Per le estensioni di markup specifico di WPF, vedere [estensioni XAML WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md).  
  
<a name="attached_properties"></a>   
## <a name="attached-properties"></a>Proprietà associate  
 Le proprietà associate sono un concetto di programmazione introdotto in XAML, in base al quale le proprietà possono essere di proprietà e definite da un particolare tipo, ma come attributi o elementi di proprietà impostate su qualsiasi elemento. Lo scenario principale che sono destinate le proprietà associate consiste nell'abilitare gli elementi figlio in una struttura di tag per fornire le informazioni a un elemento padre senza la necessità di un modello a oggetti ampiamente condiviso tra tutti gli elementi. Viceversa, le proprietà associate possono essere utilizzate dagli elementi padre per fornire le informazioni per gli elementi figlio. Per ulteriori informazioni sullo scopo delle proprietà associate e come crearne di proprie proprietà associate, vedere [collegato Cenni preliminari sulle proprietà](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
 Le proprietà associate utilizzano una sintassi che apparentemente alla sintassi degli elementi di proprietà, in quanto è anche possibile specificare un *typeName*. *propertyName* combinazione. Vi sono due differenze importanti:  
  
-   È possibile utilizzare il *typeName*. *propertyName* anche quando si imposta una proprietà associata tramite la sintassi degli attributi. Le proprietà associate sono che l'unico caso in cui la qualifica il nome della proprietà è un requisito in una sintassi degli attributi.  
  
-   È anche possibile utilizzare la sintassi degli elementi per le proprietà associate. Tuttavia, per la sintassi degli elementi di proprietà tipica, la *typeName* si specifica l'elemento oggetto che contiene l'elemento proprietà. Se si fa riferimento a una proprietà associata, il *typeName* è la classe che definisce la proprietà associata, non l'elemento oggetto contenitore.  
  
<a name="attached_events"></a>   
## <a name="attached-events"></a>Eventi associati  
 Gli eventi associati sono un altro concetto di programmazione introdotto in XAML in cui gli eventi possono essere definiti da un tipo specifico, ma è possibile associare i gestori in qualsiasi elemento oggetto. Nell'implementazione di WPF, spesso il tipo che definisce un evento associato è un tipo statico che definisce un servizio, e in alcuni casi gli eventi associati sono esposti dall'alias di un evento indirizzato in tipi che espongono il servizio. Gestori per gli eventi associati vengono specificati tramite la sintassi degli attributi. Come con gli eventi associati, la sintassi degli attributi viene espanso per gli eventi associati consentire un *typeName*. *eventName* utilizzo, in cui *typeName* è la classe che fornisce `Add` e `Remove` funzioni di accesso del gestore eventi per l'infrastruttura degli eventi associati e *eventName* è il nome dell'evento.  
  
<a name="anatomy_of_a_xaml_page_root_element"></a>   
## <a name="anatomy-of-a-xaml-root-element"></a>Anatomia di un elemento radice XAML  
 Nella tabella seguente viene illustrato un tipico elemento radice XAML frammentato, che mostra gli attributi specifici di un elemento radice:  
  
|||  
|-|-|  
|`<Page`|Apertura dell'elemento oggetto dell'elemento radice|  
|`xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"`|Il valore predefinito ([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) spazio dei nomi XAML|  
|`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`|Nomi XAML del linguaggio XAML|  
|`x:Class="ExampleNamespace.ExampleCode"`|Dichiarazione di classe parziale che connette il markup per un qualsiasi code-behind definito per la classe parziale|  
|`>`|Fine dell'elemento oggetto per la radice. Oggetto non ancora chiuso perché l'elemento contiene elementi figlio|  
  
<a name="optional_and_nonrecommended_xaml_usages"></a>   
## <a name="optional-and-nonrecommended-xaml-usages"></a>Utilizzi di XAML facoltativo e non consigliati  
 Nelle sezioni seguenti vengono descritti gli utilizzi XAML tecnicamente supportate dai processori XAML, ma che generano il livello di dettaglio o altri problemi estetici che interferiscono con i file XAML leggibile quando rimanenti del sviluppare applicazioni che contengono origini XAML .  
  
### <a name="optional-property-element-usages"></a>Utilizzi degli elementi di proprietà facoltativa  
 Gli utilizzi degli elementi di proprietà facoltativa comprendono la scrittura in modo esplicito le proprietà del contenuto di elemento che il processore XAML considera implicito. Ad esempio, quando si dichiara il contenuto di un <xref:System.Windows.Controls.Menu>, è possibile scegliere di dichiarare in modo esplicito il <xref:System.Windows.Controls.ItemsControl.Items%2A> insieme del <xref:System.Windows.Controls.Menu> come un `<Menu.Items>` il tag di elemento di proprietà e inserire ciascun <xref:System.Windows.Controls.MenuItem> all'interno di `<Menu.Items>`, anziché rispetto all'utilizzo del comportamento di processore XAML implicito che tutti gli elementi figlio di un <xref:System.Windows.Controls.Menu> deve essere un <xref:System.Windows.Controls.MenuItem> e vengono inseriti nel <xref:System.Windows.Controls.ItemsControl.Items%2A> insieme. Talvolta gli utilizzi facoltativi possono aiutare a chiarire visivamente la struttura degli oggetti come indicato nel markup. In alcuni casi utilizzo di un elemento di proprietà espliciti può evitare markup tecnicamente funzionale ma visivamente confuso, ad esempio le estensioni di markup annidato all'interno di un valore di attributo.  
  
### <a name="full-typenamemembername-qualified-attributes"></a>Attributi qualificati nomeTipo. nomemembro completi  
 Il *typeName*. *memberName* modulo per un attributo funziona effettivamente più ampio rispetto all'evento indirizzato. In altre situazioni tale formato è superfluo ma è consigliabile evitarlo, anche solo per motivi di stile di markup e migliorare la leggibilità. Nell'esempio seguente, ognuno dei tre riferimenti al <xref:System.Windows.Controls.Control.Background%2A> attributo sono completamente equivalenti:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenameprop)]  
  
 `Button.Background`Poiché la ricerca qualificata per tale proprietà su <xref:System.Windows.Controls.Button> ha esito positivo (<xref:System.Windows.Controls.Control.Background%2A> è stata ereditata dal controllo del codice) e <xref:System.Windows.Controls.Button> è la classe dell'elemento oggetto o una classe di base. `Control.Background`Poiché il <xref:System.Windows.Controls.Control> classe definisce effettivamente <xref:System.Windows.Controls.Control.Background%2A> e <xref:System.Windows.Controls.Control> è un <xref:System.Windows.Controls.Button> classe di base.  
  
 Tuttavia, le operazioni seguenti *typeName*. *memberName* esempio di form non funziona e in cui sono visualizzato i commento:  
  
 [!code-xaml[XAMLOvwSupport#TypeNameBadProp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#typenamebadprop)]  
  
 <xref:System.Windows.Controls.Label>un'altra classe derivata di <xref:System.Windows.Controls.Control>, e se è stato specificato `Label.Background` all'interno di un <xref:System.Windows.Controls.Label> elemento oggetto, questo utilizzo avrebbe avuto esito positivo. Tuttavia, poiché <xref:System.Windows.Controls.Label> non è la classe o una classe di base di <xref:System.Windows.Controls.Button>, il comportamento del processore XAML specificato consiste nell'elaborazione `Label.Background` come una proprietà associata. `Label.Background`non è una proprietà associata disponibile, e questo utilizzo non riesce.  
  
### <a name="basetypenamemembername-property-elements"></a>Elementi proprietà nomeTipoBase. nomemembro  
 In modo analogo a come il *typeName*. *memberName* formato funziona per la sintassi di attributo, un *nomeTipoBase*. *memberName* funziona per la sintassi degli elementi di sintassi. Ad esempio, la sintassi seguente funziona:  
  
 [!code-xaml[XAMLOvwSupport#GoofyPE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page8.xaml#goofype)]  
  
 In questo caso, l'elemento di proprietà viene fornito come `Control.Background` anche se la proprietà era contenuto in `Button`.  
  
 Ma come *typeName*. *memberName* form per gli attributi, *nomeTipoBase*. *memberName* non rappresenta uno stile nel markup e che è opportuno evitare.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Funzionalità del linguaggio dello spazio dei nomi XAML (x:)](../../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)  
 [Estensioni XAML WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-extensions.md)  
 [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [TypeConverter e XAML](../../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)  
 [Classi XAML e personalizzate per WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)
