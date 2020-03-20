---
title: Ambiti dei nomi XAML
ms.date: 03/30/2017
helpviewer_keywords:
- namescopes [WPF]
- styles [WPF], namescopes in
- templates [WPF], namescopes in
- APIs [WPF], name-related
- name-related APIs
- XAML [WPF], namescopes
- classes [WPF], FrameworkContentElement
ms.assetid: 52bbf4f2-15fc-40d4-837b-bb4c21ead7d4
ms.openlocfilehash: f9d4439c6b102d0d430b5201e3649985daee0b7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186278"
---
# <a name="wpf-xaml-namescopes"></a>Ambiti dei nomi XAML WPF
Un ambito dei nomi XAML è un concetto che identifica gli oggetti definiti in XAML. I nomi in un ambito dei nomi XAML possono essere usati per stabilire relazioni tra i nomi definiti da XAML degli oggetti e i rispettivi equivalenti di istanza in un albero di oggetti. In genere gli ambiti dei nomi nel codice gestito [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono creati durante il caricamento degli elementi radice delle singole pagine XAML per un'applicazione XAML. Gli ambiti dei nomi XAML come <xref:System.Windows.Markup.INameScope> oggetto di programmazione sono <xref:System.Windows.NameScope>definiti dall'interfaccia e vengono implementati anche dalla classe pratica .  

<a name="Namescopes_in_Loaded_XAML_Applications"></a>
## <a name="namescopes-in-loaded-xaml-applications"></a>Ambiti dei nomi in applicazioni XAML caricate  
 In un più ampio contesto di programmazione o informatico i concetti di programmazione includono spesso il principio di identificatore o nome univoco, che può essere usato per accedere a un oggetto. Per i sistemi che usano identificatori o nomi, l'ambito dei nomi definisce i limiti entro i quali un processo o una tecnica individuerà se è necessario un oggetto con tale nome oppure i limiti entro i quali viene applicata l'univocità dei nomi di identificazione. Questi principi generali si applicano agli ambiti dei nomi XAML. In WPF gli ambiti dei nomi XAML vengono creati nell'elemento radice per una pagina XAML quando questa viene caricata. Ogni nome specificato nella pagina XAML che inizia in corrispondenza della radice della pagina viene aggiunto a un ambito dei nomi XAML pertinente.  
  
 In XAML WPF gli elementi che sono <xref:System.Windows.Controls.Page>elementi <xref:System.Windows.Window>radice comuni (ad esempio , e ) controllano sempre un ambito dei nomi XAML. Se un elemento, <xref:System.Windows.FrameworkElement> ad esempio o <xref:System.Windows.FrameworkContentElement> è l'elemento radice della pagina nel markup, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processore aggiunge una <xref:System.Windows.Controls.Page> radice in modo implicito in modo che l'oggetto <xref:System.Windows.Controls.Page> possa fornire un ambito dei nomi XAML funzionante.  
  
> [!NOTE]
> Le azioni di compilazione di WPF creano un ambito dei nomi XAML per una produzione XAML anche se non è definito alcun attributo `Name` o `x:Name` in alcun elemento nel markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Se si prova a usare lo stesso nome due volte in un ambito dei nomi XAML, viene generata un'eccezione. Per codice XAML WPF che include code-behind e che fa parte di un'applicazione compilata, l'eccezione viene generata in fase di compilazione dalle azioni di compilazione di WPF, quando viene creata la classe generata per la pagina durante la compilazione iniziale del markup. Per codice XAML non compilato dal markup tramite alcuna azione di compilazione, potrebbero essere generate eccezioni correlate a problemi dell'ambito dei nomi XAML durante il caricamento di XAML. I progettisti XAML possono anche prevedere i problemi relativi all'ambito dei nomi XAML in fase di progettazione.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>Aggiunta di oggetti all'albero di oggetti di runtime  
 Il momento in cui XAML viene analizzato rappresenta il momento in cui viene creato e definito un ambito dei nomi XAML WPF. Se si aggiunge un oggetto a un albero di oggetti in un momento successivo all'analisi del codice XAML che ha prodotto l'albero, un valore `Name` o `x:Name` nel nuovo oggetto non aggiorna automaticamente le informazioni in un ambito dei nomi XAML. Per aggiungere un nome per un oggetto in un ambito dei nomi XAML <xref:System.Windows.Markup.INameScope.RegisterName%2A> WPF dopo il caricamento di XAML, è necessario chiamare l'implementazione appropriata di sull'oggetto che definisce l'ambito dei nomi XAML, che in genere è la radice della pagina XAML. Se il nome non è registrato, non è possibile fare <xref:System.Windows.FrameworkElement.FindName%2A>riferimento all'oggetto aggiunto in base al nome tramite metodi quali , e non è possibile utilizzare tale nome per la destinazione dell'animazione.  
  
 Lo scenario più comune per gli <xref:System.Windows.FrameworkElement.RegisterName%2A> sviluppatori di applicazioni è che verrà utilizzato per registrare i nomi nell'ambito dei nomi XAML nella radice corrente della pagina. <xref:System.Windows.FrameworkElement.RegisterName%2A>fa parte di uno scenario importante per gli storyboard destinati agli oggetti per le animazioni. Per altre informazioni, vedere [Cenni preliminari sugli storyboard](../graphics-multimedia/storyboards-overview.md).  
  
 Se si <xref:System.Windows.FrameworkElement.RegisterName%2A> chiama su un oggetto diverso dall'oggetto che definisce l'ambito dei nomi XAML, il nome viene comunque registrato nell'ambito dei nomi XAML all'interno dell'oggetto chiamante, come se si fosse chiamato <xref:System.Windows.FrameworkElement.RegisterName%2A> sull'oggetto di definizione dell'ambito dei nomi XAML.  
  
### <a name="xaml-namescopes-in-code"></a>Ambiti dei nomi XAML nel codice  
 È possibile creare e quindi usare ambiti dei nomi XAML nel codice. Le API e i concetti interessati dalla creazione di ambiti dei nomi XAML sono gli stessi, anche per l'utilizzo di codice puro, perché il processore XAML per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa questi concetti e API quando elabora il codice XAML stesso. I concetti e le API hanno prevalentemente lo scopo di trovare oggetti in base al nome all'interno di un albero di oggetti definito parzialmente o interamente in XAML.  
  
 Per le applicazioni create a livello di codice e non da XAML caricato, l'oggetto che definisce un ambito dei nomi XAML deve implementare <xref:System.Windows.Markup.INameScope>, o essere una <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> classe derivata, per supportare la creazione di un ambito dei nomi XAML nelle relative istanze.  
  
 Inoltre, per qualsiasi elemento che non viene caricato ed elaborato da un processore XAML, l'ambito dei nomi XAML per l'oggetto non viene creato o inizializzato per impostazione predefinita. È necessario creare un nuovo ambito dei nomi XAML per qualsiasi oggetto in cui si intende successivamente registrare nomi. Per creare un ambito dei nomi <xref:System.Windows.NameScope.SetNameScope%2A> XAML, chiamare il metodo statico. Specificare l'oggetto che `dependencyObject` lo sarà proprietario <xref:System.Windows.NameScope.%23ctor%2A> come parametro e una nuova chiamata al `value` costruttore come parametro.  
  
 Se l'oggetto `dependencyObject` <xref:System.Windows.NameScope.SetNameScope%2A> fornito come <xref:System.Windows.Markup.INameScope> per <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement>non <xref:System.Windows.FrameworkElement.RegisterName%2A> è un'implementazione, oppure , la chiamata su qualsiasi elemento figlio non avrà alcun effetto. Se non si riesce a creare il <xref:System.Windows.FrameworkElement.RegisterName%2A> nuovo ambito dei nomi XAML in modo esplicito, le chiamate a genereranno un'eccezione.  
  
 Per un esempio dell'uso di API di ambito dei nomi XAML nel codice, vedere [Definire un ambito dei nomi](../graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>
## <a name="xaml-namescopes-in-styles-and-templates"></a>Ambiti dei nomi XAML in stili e modelli  
 Gli stili e i modelli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permettono di riutilizzare e riapplicare contenuto in modo diretto. Tuttavia, stili e modelli potrebbero includere anche elementi con nomi XAML definiti a livello del modello. Questo stesso modello potrebbe essere usato più volte in una pagina. Per questo motivo, gli stili e i modelli definiscono entrambi ambiti dei nomi XAML propri, indipendentemente dalla posizione in un albero di oggetti in cui viene applicato lo stile o il modello.  
  
 Prendere in considerazione gli esempi seguenti:  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Qui viene applicato lo stesso modello a due diversi pulsanti. Se i modelli non avessero ambiti dei nomi XAML discreti, il nome `TheBorder` usato nel modello causerebbe un conflitto di nomi nell'ambito dei nomi XAML. Poiché la creazione di ogni istanza del modello ha un ambito dei nomi XAML proprio, in questo esempio l'ambito dei nomi di ogni modello di cui è stata creata un'istanza contiene esattamente un solo nome.  
  
 Anche gli stili definiscono un ambito dei nomi XAML proprio, per lo più in modo che alle parti degli storyboard possano essere assegnati nomi specifici. Questi nomi permettono comportamenti specifici dei controlli destinati a elementi con questi nomi, anche se il modello è stato ridefinito come parte della personalizzazione del controllo.  
  
 A causa della presenza di ambiti dei nomi XAML separati, la ricerca di elementi denominati in un modello è più complessa rispetto all'individuazione di un elemento denominato senza modello in una pagina. È innanzitutto necessario determinare il modello <xref:System.Windows.Controls.Control.Template%2A> applicato, ottenendo il valore della proprietà del controllo in cui viene applicato il modello. Quindi, chiamare la versione <xref:System.Windows.FrameworkTemplate.FindName%2A>del modello di , passando il controllo in cui è stato applicato il modello come secondo parametro.  
  
 Se si è un autore di controlli e si sta generando una convenzione in cui un particolare elemento denominato <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> in un modello applicato è la destinazione di un comportamento definito dal controllo stesso, è possibile utilizzare il metodo dal codice di implementazione del controllo. Il <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> metodo è protetto, pertanto solo l'autore del controllo ha accesso ad esso.  
  
 Se si lavora dall'interno di un modello ed è necessario accedere all'ambito <xref:System.Windows.FrameworkElement.TemplatedParent%2A>dei nomi <xref:System.Windows.FrameworkElement.FindName%2A> XAML in cui viene applicato il modello, ottenere il valore di , quindi chiamare in tale modello. Un esempio di questa situazione è quando si scrive l'implementazione del gestore eventi in cui l'evento verrà generato da un elemento in un modello applicato.  
  
<a name="Namescopes_and_Name_related_APIs"></a>
## <a name="xaml-namescopes-and-name-related-apis"></a>Ambiti dei nomi XAML e API correlate ai nomi  
 <xref:System.Windows.FrameworkElement>dispone <xref:System.Windows.FrameworkElement.FindName%2A> <xref:System.Windows.FrameworkElement.RegisterName%2A> di <xref:System.Windows.FrameworkElement.UnregisterName%2A> metodi , e . Se l'oggetto in cui vengono chiamati questi metodi è proprietario di un ambito dei nomi XAML, i metodi chiamano nei metodi dell'ambito dei nomi XAML pertinente. In caso contrario, l'elemento padre viene controllato per verificare se è proprietario di un ambito dei nomi XAML e questo processo continua in modo ricorsivo fino a quando non viene trovato un ambito dei nomi XAML. A causa del comportamento del processore XAML, esiste sicuramente un ambito dei nomi XAML nella radice. <xref:System.Windows.FrameworkContentElement>ha comportamenti analoghi, con l'eccezione che nessun <xref:System.Windows.FrameworkContentElement> acquisirà mai un ambito dei nomi XAML. I metodi <xref:System.Windows.FrameworkContentElement> esistono in modo che le chiamate <xref:System.Windows.FrameworkElement> possano essere inoltrate alla fine a un elemento padre.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A>viene utilizzato per eseguire il mapping di un nuovo ambito dei nomi XAML a un oggetto esistente. È possibile <xref:System.Windows.NameScope.SetNameScope%2A> chiamare più di una volta per reimpostare o cancellare l'ambito dei nomi XAML, ma questo non è un utilizzo comune. Inoltre, <xref:System.Windows.NameScope.GetNameScope%2A> non viene in genere utilizzato dal codice.  
  
### <a name="xaml-namescope-implementations"></a>Implementazioni di ambiti dei nomi XAML  
 Le classi <xref:System.Windows.Markup.INameScope> seguenti implementano direttamente:  
  
- <xref:System.Windows.NameScope>  
  
- <xref:System.Windows.Style>  
  
- <xref:System.Windows.ResourceDictionary>  
  
- <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary>non utilizza nomi XAML o ambiti dei nomi ; utilizza invece le chiavi, perché è un'implementazione del dizionario. L'unico <xref:System.Windows.ResourceDictionary> motivo che implementa <xref:System.Windows.Markup.INameScope> è in modo che possa generare eccezioni al <xref:System.Windows.ResourceDictionary> codice utente che consentono di chiarire la distinzione <xref:System.Windows.ResourceDictionary> tra un vero ambito dei nomi XAML e come un gestisce le chiavi e anche per assicurare che gli ambiti dei nomi XAML non vengono applicati a un da elementi padre.  
  
 <xref:System.Windows.FrameworkTemplate>e <xref:System.Windows.Style> <xref:System.Windows.Markup.INameScope> implementare tramite definizioni di interfaccia esplicite. Le implementazioni esplicite consentono a questi ambiti dei nomi XAML <xref:System.Windows.Markup.INameScope> di comportarsi in modo convenzionale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] quando vi si accede tramite l'interfaccia, ovvero il modo in cui gli ambiti dei nomi XAML vengono comunicati dai processi interni. Ma le definizioni di interfaccia esplicite <xref:System.Windows.FrameworkTemplate> non <xref:System.Windows.Style>fanno parte della superficie API <xref:System.Windows.Markup.INameScope> convenzionale di e , perché raramente è necessario chiamare i metodi su <xref:System.Windows.FrameworkTemplate> e <xref:System.Windows.Style> direttamente e invece utilizzerebbe altre API come <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>.  
  
 Le classi seguenti definiscono il proprio <xref:System.Windows.NameScope?displayProperty=nameWithType> ambito dei nomi XAML, usando la <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> classe helper e connettendosi all'implementazione dell'ambito dei nomi XAML tramite la proprietà associata:The following classes define their own XAML namescope, by using the helper class and connecting to its XAML namescope implementation through the attached property:  
  
- <xref:System.Windows.FrameworkElement>  
  
- <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>Vedere anche

- [Spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [Direttiva x:Name](../../../desktop-wpf/xaml-services/xname-directive.md)
