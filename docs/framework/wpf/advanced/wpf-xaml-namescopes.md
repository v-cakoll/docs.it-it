---
title: Ambiti dei nomi XAML WPF
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
ms.openlocfilehash: d4a4e1eee5dc60e330a5425d5075c7e5b8c44127
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666338"
---
# <a name="wpf-xaml-namescopes"></a>Ambiti dei nomi XAML WPF
Un ambito dei nomi XAML è un concetto che identifica gli oggetti definiti in XAML. I nomi in un ambito dei nomi XAML possono essere usati per stabilire relazioni tra i nomi definiti da XAML degli oggetti e i rispettivi equivalenti di istanza in un albero di oggetti. In genere gli ambiti dei nomi nel codice gestito [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono creati durante il caricamento degli elementi radice delle singole pagine XAML per un'applicazione XAML. Ambiti dei nomi XAML come oggetto di programmazione sono definiti dal <xref:System.Windows.Markup.INameScope> dell'interfaccia e vengono anche implementati dalla classe pratica <xref:System.Windows.NameScope>.  

<a name="Namescopes_in_Loaded_XAML_Applications"></a>   
## <a name="namescopes-in-loaded-xaml-applications"></a>Ambiti dei nomi in applicazioni XAML caricate  
 In un più ampio contesto di programmazione o informatico i concetti di programmazione includono spesso il principio di identificatore o nome univoco, che può essere usato per accedere a un oggetto. Per i sistemi che usano identificatori o nomi, l'ambito dei nomi definisce i limiti entro i quali un processo o una tecnica individuerà se è necessario un oggetto con tale nome oppure i limiti entro i quali viene applicata l'univocità dei nomi di identificazione. Questi principi generali si applicano agli ambiti dei nomi XAML. In WPF gli ambiti dei nomi XAML vengono creati nell'elemento radice per una pagina XAML quando questa viene caricata. Ogni nome specificato nella pagina XAML che inizia in corrispondenza della radice della pagina viene aggiunto a un ambito dei nomi XAML pertinente.  
  
 In XAML WPF, gli elementi che sono elementi radice comuni (ad esempio <xref:System.Windows.Controls.Page>, e <xref:System.Windows.Window>) controllano sempre un namescope XAML. Se un elemento, ad esempio <xref:System.Windows.FrameworkElement> oppure <xref:System.Windows.FrameworkContentElement> è l'elemento radice della pagina nel markup, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor aggiunge un <xref:System.Windows.Controls.Page> radice in modo implicito in modo che il <xref:System.Windows.Controls.Page> può fornire un ambito dei nomi XAML funzionante.  
  
> [!NOTE]
>  Le azioni di compilazione di WPF creano un ambito dei nomi XAML per una produzione XAML anche se non è definito alcun attributo `Name` o `x:Name` in alcun elemento nel markup [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Se si prova a usare lo stesso nome due volte in un ambito dei nomi XAML, viene generata un'eccezione. Per codice XAML WPF che include code-behind e che fa parte di un'applicazione compilata, l'eccezione viene generata in fase di compilazione dalle azioni di compilazione di WPF, quando viene creata la classe generata per la pagina durante la compilazione iniziale del markup. Per codice XAML non compilato dal markup tramite alcuna azione di compilazione, potrebbero essere generate eccezioni correlate a problemi dell'ambito dei nomi XAML durante il caricamento di XAML. I progettisti XAML possono anche prevedere i problemi relativi all'ambito dei nomi XAML in fase di progettazione.  
  
### <a name="adding-objects-to-runtime-object-trees"></a>Aggiunta di oggetti all'albero di oggetti di runtime  
 Il momento in cui XAML viene analizzato rappresenta il momento in cui viene creato e definito un ambito dei nomi XAML WPF. Se si aggiunge un oggetto a un albero di oggetti in un momento successivo all'analisi del codice XAML che ha prodotto l'albero, un valore `Name` o `x:Name` nel nuovo oggetto non aggiorna automaticamente le informazioni in un ambito dei nomi XAML. Per aggiungere un nome per un oggetto in un namescope XAML WPF dopo il caricamento di XAML, è necessario chiamare l'implementazione corretta del <xref:System.Windows.Markup.INameScope.RegisterName%2A> sull'oggetto che definisce l'ambito dei nomi XAML, che in genere è la radice della pagina XAML. Se il nome non è registrato, l'oggetto aggiunto non è possibile farvi riferimento in base al nome tramite metodi, ad esempio <xref:System.Windows.FrameworkElement.FindName%2A>, e non è possibile usare tale nome per la destinazione dell'animazione.  
  
 Lo scenario più comune per gli sviluppatori di applicazioni è che si userà <xref:System.Windows.FrameworkElement.RegisterName%2A> registrare nomi nell'ambito dei nomi XAML nella radice della pagina corrente. <xref:System.Windows.FrameworkElement.RegisterName%2A> fa parte di uno scenario importante per gli storyboard che gli oggetti di destinazione per le animazioni. Per altre informazioni, vedere [Cenni preliminari sugli storyboard](../graphics-multimedia/storyboards-overview.md).  
  
 Se si chiama <xref:System.Windows.FrameworkElement.RegisterName%2A> su un oggetto diverso dall'oggetto che definisce l'ambito dei nomi XAML, il nome è ancora registrato per l'ambito dei nomi XAML che è contenuto l'oggetto chiamante, come se si fosse chiamato <xref:System.Windows.FrameworkElement.RegisterName%2A> nel namescope XAML la definizione di oggetto.  
  
### <a name="xaml-namescopes-in-code"></a>Ambiti dei nomi XAML nel codice  
 È possibile creare e quindi usare ambiti dei nomi XAML nel codice. Le API e i concetti interessati dalla creazione di ambiti dei nomi XAML sono gli stessi, anche per l'utilizzo di codice puro, perché il processore XAML per [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa questi concetti e API quando elabora il codice XAML stesso. I concetti e le API hanno prevalentemente lo scopo di trovare oggetti in base al nome all'interno di un albero di oggetti definito parzialmente o interamente in XAML.  
  
 Per le applicazioni che vengono create a livello di codice e non da XAML caricato, l'oggetto che definisce un namescope XAML deve implementare <xref:System.Windows.Markup.INameScope>, o essere un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> derivato (classe), per supportare la creazione di un namescope XAML nel relativo istanze.  
  
 Inoltre, per qualsiasi elemento che non viene caricato ed elaborato da un processore XAML, l'ambito dei nomi XAML per l'oggetto non viene creato o inizializzato per impostazione predefinita. È necessario creare un nuovo ambito dei nomi XAML per qualsiasi oggetto in cui si intende successivamente registrare nomi. Per creare un namescope XAML, si chiama il metodo statico <xref:System.Windows.NameScope.SetNameScope%2A> (metodo). Specificare l'oggetto che sarà proprietario come le `dependencyObject` parametro e un nuovo <xref:System.Windows.NameScope.%23ctor%2A> chiamata al costruttore come il `value` parametro.  
  
 Se l'oggetto fornito come `dependencyObject` per <xref:System.Windows.NameScope.SetNameScope%2A> non è un <xref:System.Windows.Markup.INameScope> implementazione <xref:System.Windows.FrameworkElement> oppure <xref:System.Windows.FrameworkContentElement>, la chiamata <xref:System.Windows.FrameworkElement.RegisterName%2A> su qualsiasi elemento figlio elementi avrà alcun effetto. Se non è possibile creare il nuovo ambito dei nomi XAML in modo esplicito, quindi chiama a <xref:System.Windows.FrameworkElement.RegisterName%2A> genererà un'eccezione.  
  
 Per un esempio dell'uso di API di ambito dei nomi XAML nel codice, vedere [Definire un ambito dei nomi](../graphics-multimedia/how-to-define-a-name-scope.md).  
  
<a name="Namescopes_in_Styles_and_Templates"></a>   
## <a name="xaml-namescopes-in-styles-and-templates"></a>Ambiti dei nomi XAML in stili e modelli  
 Gli stili e i modelli in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permettono di riutilizzare e riapplicare contenuto in modo diretto. Tuttavia, stili e modelli potrebbero includere anche elementi con nomi XAML definiti a livello del modello. Questo stesso modello potrebbe essere usato più volte in una pagina. Per questo motivo, gli stili e i modelli definiscono entrambi ambiti dei nomi XAML propri, indipendentemente dalla posizione in un albero di oggetti in cui viene applicato lo stile o il modello.  
  
 Si consideri l'esempio seguente:  
  
 [!code-xaml[XamlOvwSupport#NameScopeTemplates](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page6.xaml#namescopetemplates)]  
  
 Qui viene applicato lo stesso modello a due diversi pulsanti. Se i modelli non avessero ambiti dei nomi XAML discreti, il nome `TheBorder` usato nel modello causerebbe un conflitto di nomi nell'ambito dei nomi XAML. Poiché la creazione di ogni istanza del modello ha un ambito dei nomi XAML proprio, in questo esempio l'ambito dei nomi di ogni modello di cui è stata creata un'istanza contiene esattamente un solo nome.  
  
 Anche gli stili definiscono un ambito dei nomi XAML proprio, per lo più in modo che alle parti degli storyboard possano essere assegnati nomi specifici. Questi nomi permettono comportamenti specifici dei controlli destinati a elementi con questi nomi, anche se il modello è stato ridefinito come parte della personalizzazione del controllo.  
  
 A causa della presenza di ambiti dei nomi XAML separati, la ricerca di elementi denominati in un modello è più complessa rispetto all'individuazione di un elemento denominato senza modello in una pagina. È necessario innanzitutto determinare il modello applicato ottenendo il <xref:System.Windows.Controls.Control.Template%2A> valore della proprietà del controllo in cui viene applicato il modello. Chiamare quindi la versione del modello <xref:System.Windows.FrameworkTemplate.FindName%2A>, passando il controllo in cui è stato applicato il modello come secondo parametro.  
  
 Se si è un autore di controlli e si desidera generare una convenzione in cui un determinato elemento denominato in un modello applicato è la destinazione di un comportamento definito dal controllo stesso, è possibile usare il <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> metodo dal codice di implementazione del controllo. Il <xref:System.Windows.FrameworkElement.GetTemplateChild%2A> metodo è protetto, in modo che solo l'autore del controllo possa accedervi.  
  
 Se si lavora da all'interno di un modello e necessità di accedere al namescope XAML in cui viene applicato il modello, ottenere il valore della <xref:System.Windows.FrameworkElement.TemplatedParent%2A>, quindi chiamare <xref:System.Windows.FrameworkElement.FindName%2A> non esiste. Un esempio di questa situazione è quando si scrive l'implementazione del gestore eventi in cui l'evento verrà generato da un elemento in un modello applicato.  
  
<a name="Namescopes_and_Name_related_APIs"></a>   
## <a name="xaml-namescopes-and-name-related-apis"></a>Ambiti dei nomi XAML e API correlate ai nomi  
 <xref:System.Windows.FrameworkElement> ha <xref:System.Windows.FrameworkElement.FindName%2A>, <xref:System.Windows.FrameworkElement.RegisterName%2A> e <xref:System.Windows.FrameworkElement.UnregisterName%2A> metodi. Se l'oggetto in cui vengono chiamati questi metodi è proprietario di un ambito dei nomi XAML, i metodi chiamano nei metodi dell'ambito dei nomi XAML pertinente. In caso contrario, l'elemento padre viene controllato per verificare se è proprietario di un ambito dei nomi XAML e questo processo continua in modo ricorsivo fino a quando non viene trovato un ambito dei nomi XAML. A causa del comportamento del processore XAML, esiste sicuramente un ambito dei nomi XAML nella radice. <xref:System.Windows.FrameworkContentElement> ha comportamenti analoghi, con l'eccezione che non <xref:System.Windows.FrameworkContentElement> sarà mai proprietario di un namescope XAML. I metodi presenti <xref:System.Windows.FrameworkContentElement> in modo che le chiamate possono essere inoltrate alla fine di un <xref:System.Windows.FrameworkElement> elemento padre.  
  
 <xref:System.Windows.NameScope.SetNameScope%2A> viene usato per eseguire il mapping di un nuovo ambito dei nomi XAML a un oggetto esistente. È possibile chiamare <xref:System.Windows.NameScope.SetNameScope%2A> più volte per reimpostare o cancellare il XAML ambito dei nomi, ma che non è un utilizzo comune. Inoltre, <xref:System.Windows.NameScope.GetNameScope%2A> non è in genere usato dal codice.  
  
### <a name="xaml-namescope-implementations"></a>Implementazioni di ambiti dei nomi XAML  
 Le seguenti classi implementano <xref:System.Windows.Markup.INameScope> direttamente:  
  
- <xref:System.Windows.NameScope>  
  
- <xref:System.Windows.Style>  
  
- <xref:System.Windows.ResourceDictionary>  
  
- <xref:System.Windows.FrameworkTemplate>  
  
 <xref:System.Windows.ResourceDictionary> non usa XAML o ambiti dei nomi; ma Usa chiavi, perché è un'implementazione di dizionario. L'unico motivo per cui <xref:System.Windows.ResourceDictionary> implementa <xref:System.Windows.Markup.INameScope> è in modo che può generare eccezioni per il codice utente che consentono di chiarire la distinzione tra un namescope XAML true e la modalità un <xref:System.Windows.ResourceDictionary> gestisce le chiavi, oltre ad assicurare che gli ambiti dei nomi XAML non vengono applicati a un <xref:System.Windows.ResourceDictionary> dagli elementi padre.  
  
 <xref:System.Windows.FrameworkTemplate> e <xref:System.Windows.Style> implementare <xref:System.Windows.Markup.INameScope> tramite definizioni di interfaccia esplicita. Le implementazioni esplicite permettono a questi ambiti dei nomi XAML di comportarsi in modo convenzionale quando vi si accede tramite il <xref:System.Windows.Markup.INameScope> interfaccia, ovvero il modo in cui gli ambiti dei nomi XAML vengono comunicati dal [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] processi interni. Ma le definizioni di interfaccia esplicite non fanno parte della sua superficie API convenzionale <xref:System.Windows.FrameworkTemplate> e <xref:System.Windows.Style>, perché raramente è necessario chiamare il <xref:System.Windows.Markup.INameScope> metodi sul <xref:System.Windows.FrameworkTemplate> e <xref:System.Windows.Style> direttamente e invece si utilizza un'API ad esempio <xref:System.Windows.FrameworkElement.GetTemplateChild%2A>.  
  
 Le classi seguenti definiscono i propri namescope XAML, usando il <xref:System.Windows.NameScope?displayProperty=nameWithType> classe helper e ci si connette alla relativa implementazione namescope XAML tramite il <xref:System.Windows.NameScope.NameScope%2A?displayProperty=nameWithType> proprietà associata:  
  
- <xref:System.Windows.FrameworkElement>  
  
- <xref:System.Windows.FrameworkContentElement>  
  
## <a name="see-also"></a>Vedere anche

- [Spazi dei nomi XAML e mapping dello spazio dei nomi per XAML WPF](xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)
- [Direttiva x:Name](../../xaml-services/x-name-directive.md)
