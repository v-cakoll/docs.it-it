---
title: Cenni preliminari sulle proprietà associate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: 626cc0a5ddb1ba51be14eb045bcedcf7574cfb11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542171"
---
# <a name="attached-properties-overview"></a>Cenni preliminari sulle proprietà associate
Una proprietà associata è un concetto definito da XAML. Una proprietà associata deve essere usata come un tipo di proprietà globale che è possibile impostare su qualsiasi oggetto. In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] le proprietà associate sono in genere definite come un tipo specializzato di proprietà di dipendenza che non dispone della proprietà "wrapper" convenzionale.  
  
   
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento presuppone la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer delle proprietà di dipendenza esistenti nelle classi di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md). Per seguire gli esempi illustrati in questo argomento, è anche necessario conoscere XAML e saper scrivere applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="attached_properties_usage"></a>   
## <a name="why-use-attached-properties"></a>Vantaggi dell'uso delle proprietà associate  
 Una delle finalità di una proprietà associata consiste nel consentire a diversi elementi figlio di specificare valori univoci di una proprietà effettivamente definita in un elemento padre. Un'applicazione specifica di questo scenario consente agli elementi figlio di notificare all'elemento padre la modalità con cui devono essere presentati nell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Ad esempio, il <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà. Il <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà viene creata come una proprietà associata perché è stato progettato per essere impostate su elementi che sono contenuti all'interno di un <xref:System.Windows.Controls.DockPanel>, anziché sul <xref:System.Windows.Controls.DockPanel> stesso. Il <xref:System.Windows.Controls.DockPanel> classe definisce il metodo statico <xref:System.Windows.DependencyProperty> campo denominato <xref:System.Windows.Controls.DockPanel.DockProperty>e quindi fornisce il <xref:System.Windows.Controls.DockPanel.GetDock%2A> e <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodi come funzioni di accesso pubbliche della proprietà associata.  
  
<a name="attached_properties_xaml"></a>   
## <a name="attached-properties-in-xaml"></a>Proprietà associate in XAML  
 In XAML, è possibile impostare le proprietà associate usando la sintassi *ProviderProprietàAssociata*.*NomeProprietà*  
  
 Di seguito è riportato un esempio di come si può impostare <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> in XAML:  
  
 [!code-xaml[PropertiesOvwSupport#APBasicUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]  
  
 Si noti che l'utilizzo è simile a una proprietà statica. sempre riferimento al tipo <xref:System.Windows.Controls.DockPanel> che possiede e registra la proprietà associata, anziché fare riferimento a qualsiasi istanza specificata in base al nome.  
  
 Inoltre, dato che una proprietà associata in XAML è un attributo che viene impostato nel markup, solo l'operazione di impostazione ha una certa rilevanza. Non è possibile ottenere direttamente una proprietà in XAML, sebbene esistano alcuni meccanismi indiretti per confrontare i valori, ad esempio i trigger negli stili. Per altri dettagli, vedere [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).  
  
### <a name="attached-property-implementation-in-wpf"></a>Implementazione delle proprietà associate in WPF  
 In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] la maggior parte delle proprietà associate esistenti per i tipi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] correlati alla presentazione dell'interfaccia utente viene implementata come proprietà di dipendenza. Le proprietà associate sono un concetto di XAML, mentre le proprietà di dipendenza sono un concetto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Dato che le proprietà associate [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sono proprietà di dipendenza, supportano concetti correlati alle proprietà di dipendenza, come i metadati delle proprietà e i valori predefiniti da questi metadati.  
  
<a name="howused"></a>   
## <a name="how-attached-properties-are-used-by-the-owning-type"></a>Uso delle proprietà associate da parte del tipo proprietario  
 Anche se le proprietà associate possono essere impostate per qualsiasi oggetto, ciò non significa che l'impostazione della proprietà produce un risultato tangibile o che il valore verrà usato da un altro oggetto. In genere, le proprietà associate sono concepite in modo che gli oggetti provenienti da un'ampia varietà di possibili gerarchie di classi o di relazioni logiche possano ciascuno riportare informazioni comuni al tipo che definisce la proprietà associata. Il tipo che definisce la proprietà associata si attiene di regola a uno di questi modelli:  
  
-   Il tipo che definisce la proprietà associata è progettato in modo da poter essere l'elemento padre degli elementi che imposteranno i valori per la proprietà associata. Il tipo scorre quindi gli oggetti figlio attraverso la logica interna in base a una struttura ad albero degli oggetti, ottiene i valori e agisce in qualche modo su tali valori.  
  
-   Il tipo che definisce la proprietà associata verrà usato come elemento figlio per un'ampia gamma di elementi padre e modelli di contenuto possibili.  
  
-   Il tipo che definisce la proprietà associata rappresenta un servizio. Gli altri tipi impostano i valori per la proprietà associata. Pertanto, quando l'elemento che imposta la proprietà viene valutato nel contesto del servizio, i valori della proprietà associata vengono ottenuti tramite la logica interna della classe del servizio.  
  
### <a name="an-example-of-a-parent-defined-attached-property"></a>Esempio di proprietà associata definita dall'elemento padre  
 Lo scenario più tipico in cui [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] definisce una proprietà associata è quello in cui un elemento padre supporta una raccolta di elementi figlio e implementa inoltre un comportamento tale che le specifiche del comportamento vengono segnalate singolarmente per ogni elemento figlio.  
  
 <xref:System.Windows.Controls.DockPanel> definisce il <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> associata, e <xref:System.Windows.Controls.DockPanel> dispone di codice a livello di classe come parte della logica di rendering (in particolare, <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> e <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>). Oggetto <xref:System.Windows.Controls.DockPanel> istanza sempre controlla se uno dei relativi elementi figlio immediati ha impostato un valore per <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. In questo caso, tali valori diventano l'input per la logica di rendering applicata a quel particolare elemento figlio. Annidati <xref:System.Windows.Controls.DockPanel> istanze ogni trattare le proprie raccolte di elementi figlio diretti, ma questo comportamento è specifico dell'implementazione come <xref:System.Windows.Controls.DockPanel> processi <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> valori. In teoria, è possibile che alcune proprietà associate abbiano effetto su elementi più distanti dell'elemento padre immediato. Se il <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà associata è impostata su un elemento che non ha alcun <xref:System.Windows.Controls.DockPanel> viene generato l'elemento padre per eseguire un'azione, nessun errore o eccezione. Ciò significa semplicemente che è stato impostato un valore della proprietà globale, ma presente alcun elemento <xref:System.Windows.Controls.DockPanel> padre che possa utilizzare le informazioni.  
  
<a name="attached_properties_code"></a>   
## <a name="attached-properties-in-code"></a>Proprietà associate nel codice  
 Le proprietà associate in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non dispongono dei tipici metodi "wrapper" [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] per facilitare l'accesso alle operazioni Get/Set. Ciò è dovuto al fatto che la proprietà associata non è necessariamente inclusa nello spazio dei nomi [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] per le istanze in cui la proprietà è impostata. Tuttavia, un processore XAML deve essere in grado di impostare tali valori quando il codice XAML viene analizzato. Per supportare l'utilizzo efficace delle proprietà associata, il tipo proprietario della proprietà associata deve implementare i metodi della funzione di accesso dedicati nel formato `Get`*NomeProprietà* e `Set`*NomeProprietà*. Questi metodi della funzione di accesso dedicati sono anche utili per ottenere o impostare la proprietà associata nel codice. Dal punto di vista del codice, una proprietà associata è simile a un campo sottostante che dispone di funzioni di accesso ai metodi anziché di funzioni di accesso alle proprietà e tale campo sottostante può trovarsi in qualsiasi oggetto senza che sia necessario definirlo in modo specifico.  
  
 L'esempio seguente illustra come impostare una proprietà associata nel codice. In questo esempio, `myCheckBox` è un'istanza di <xref:System.Windows.Controls.CheckBox> classe.  
  
 [!code-csharp[PropertiesOvwSupport#APCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
 [!code-vb[PropertiesOvwSupport#APCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]  
  
 Caso simile a XAML, se `myCheckBox` non fosse già stato aggiunto come elemento figlio di `myDockPanel` nella terza riga di codice, la quarta riga di codice non genera un'eccezione, ma il valore della proprietà non si interagisce con un <xref:System.Windows.Controls.DockPanel> padre e pertanto potrebbe non eseguire alcuna operazione. Solo un <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> valore impostato su un elemento figlio combinato con la presenza di un <xref:System.Windows.Controls.DockPanel> elemento padre provocherà un comportamento efficace nell'applicazione sottoposta a rendering. In questo caso, è possibile impostare la proprietà associata e quindi effettuare l'associazione alla struttura ad albero. In alternativa, è possibile effettuare l'associazione alla struttura ad albero, quindi impostare la proprietà associata. Qualunque sia l'ordine delle azioni, il risultato è il medesimo.  
  
<a name="attached_properties_metadata"></a>   
## <a name="attached-property-metadata"></a>Metadati delle proprietà associate  
 Durante la registrazione, la proprietà <xref:System.Windows.FrameworkPropertyMetadata> è impostato per specificare le caratteristiche della proprietà, ad esempio se la proprietà influisce sul rendering misurazione e così via. I metadati di una proprietà associata non sono in genere diversi rispetto a quelli presenti per una proprietà di dipendenza. Se si specifica un valore predefinito in un override per i metadati di una proprietà associata, tale valore diventa il valore predefinito della proprietà associata implicita nelle istanze della classe che esegue l'override. In particolare, il valore predefinito viene segnalato se un processo esegue una query per recuperare il valore di una proprietà associata tramite la funzione di accesso al metodo `Get` di quella proprietà, specificando un'istanza della classe in cui sono stati definiti i metadati e il valore per quella proprietà collegata non è stato impostato diversamente.  
  
 Se si vuole abilitare l'ereditarietà del valore di una proprietà, è necessario usare le proprietà associate anziché le proprietà di dipendenza non associate. Per informazioni dettagliate, vedere [Ereditarietà del valore della proprietà](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
<a name="custom"></a>   
## <a name="custom-attached-properties"></a>Proprietà associate personalizzate  
  
<a name="create_attached_properties"></a>   
### <a name="when-to-create-an-attached-property"></a>Quando creare una proprietà associata  
 È possibile creare una proprietà associata quando è necessario disporre di un meccanismo di impostazione delle proprietà per le classi diverse dalla classe di definizione. In questo caso, lo scenario più comune è il layout. Esempi di proprietà di layout esistenti sono <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>, e <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>. Nello scenario abilitato in questo contesto, gli elementi disponibili come elementi figlio degli elementi di controllo del layout sono in grado di indicare i requisiti del layout agli elementi padre del layout singolarmente, impostando ciascuno un valore della proprietà definito dall'elemento padre come proprietà associata.  
  
 Un altro scenario per l'uso di una proprietà associata è quello in cui la classe rappresenta un servizio e si vuole che le classi siano in grado di integrare il servizio in modo più trasparente.  
  
 Infine, un ulteriore scenario prevede di ricevere il supporto di [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)][!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)], ad esempio la modifica della finestra **Proprietà**. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Come indicato in precedenza, è necessario eseguire la registrazione come proprietà associata se si vuole usare l'ereditarietà del valore della proprietà.  
  
<a name="how_do_i_create_attached_properties"></a>   
### <a name="how-to-create-an-attached-property"></a>Come creare una proprietà associata  
 Se la classe definisce la proprietà associata esclusivamente per l'utilizzo in altri tipi, quindi la classe deve derivare da <xref:System.Windows.DependencyObject>. Ma è necessario derivare da <xref:System.Windows.DependencyObject> se si segue generale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] modello di cui la proprietà associata anche essere una proprietà di dipendenza.  
  
 Definire la proprietà associata come proprietà di dipendenza dichiarando un `public` `static` `readonly` campo di tipo <xref:System.Windows.DependencyProperty>. Per definire questo campo, utilizzare il valore restituito del <xref:System.Windows.DependencyProperty.RegisterAttached%2A> metodo. Il nome del campo deve corrispondere al nome della proprietà associata, a cui viene aggiunta la stringa `Property`, secondo il modello [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stabilito per la denominazione dei campi di identificazione in base alle proprietà che rappresentano. Il provider della proprietà associata deve inoltre fornire metodi `Get`*NomeProprietà* e `Set`*NomeProprietà* statici come funzioni di accesso per la proprietà associata. In caso contrario, il sistema di proprietà non sarà in grado di usare la proprietà associata.  
  
> [!NOTE]
>  Se si omette funzione di accesso get della proprietà associata, associazione dati per la proprietà non funzionerà negli strumenti di progettazione, ad esempio Visual Studio ed Expression Blend.  
  
#### <a name="the-get-accessor"></a>Funzione di accesso Get  
 La firma per la funzione di accesso `Get`*NomeProprietà* deve essere:  
  
 `public static object Get` *PropertyName* `(object` `target` `)`  
  
-   L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. Ad esempio, il <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> il parametro come tipi di metodo <xref:System.Windows.UIElement>, perché la proprietà associata ha solo scopo deve essere impostato su <xref:System.Windows.UIElement> istanze.  
  
-   Il valore restituito può essere specificato come tipo più specifico nell'implementazione. Ad esempio, il <xref:System.Windows.Controls.DockPanel.GetDock%2A> come tipi di metodo <xref:System.Windows.Controls.Dock>, perché il valore può essere impostato solo per tale enumerazione.  
  
#### <a name="the-set-accessor"></a>Funzione di accesso Set  
 La firma per la funzione di accesso `Set`*NomeProprietà* deve essere:  
  
 `public static void Set` *NomeProprietà* `(object` `target` `, object` `value` `)`  
  
-   L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. Ad esempio, il <xref:System.Windows.Controls.DockPanel.SetDock%2A> come tipi di metodo <xref:System.Windows.UIElement>, perché la proprietà associata ha solo scopo deve essere impostato su <xref:System.Windows.UIElement> istanze.  
  
-   L'oggetto `value` può essere specificato come tipo più specifico nell'implementazione. Ad esempio, il <xref:System.Windows.Controls.DockPanel.SetDock%2A> come tipi di metodo <xref:System.Windows.Controls.Dock>, perché il valore può essere impostato solo per tale enumerazione. Tenere presente che il valore per questo metodo è l'input proveniente dal caricatore XAML quando rileva la proprietà associata in un utilizzo della proprietà associata nel markup. Tale input è il valore specificato come valore di attributo XAML nel markup. Pertanto, per il tipo usato devono essere disponibili la conversione di tipo, il serializzatore del valore o il supporto per l'estensione di markup, in modo da poter creare il tipo appropriato in base al valore dell'attributo, rappresentato in pratica semplicemente da una stringa.  
  
 L'esempio seguente illustra la registrazione di proprietà di dipendenza (utilizzando la <xref:System.Windows.DependencyProperty.RegisterAttached%2A> metodo), nonché il `Get` *PropertyName* e `Set` *PropertyName* funzioni di accesso . Nell'esempio, la proprietà associata è denominata `IsBubbleSource`. Pertanto, le funzioni di accesso devono essere chiamate `GetIsBubbleSource` e `SetIsBubbleSource`.  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
#### <a name="attached-property-attributes"></a>Attributi delle proprietà associate  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] vengono definiti diversi attributi [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] allo scopo di fornire informazioni sulle proprietà associate ai processi di reflection e agli utenti tipici delle informazioni sulla reflection e sulle proprietà, ad esempio le finestre di progettazione. Dato che le proprietà associate hanno un tipo con ambito illimitato, le finestre di progettazione devono disporre di un modo per evitare di sopraffare gli utenti con un elenco globale di tutte le proprietà associate definite in una particolare implementazione della tecnologia che usa XAML. Gli [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] specificati in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] per le proprietà associate possono essere usati per definire l'ambito di situazioni in cui una certa proprietà associata deve essere visualizzata in una finestra delle proprietà. È possibile prendere in considerazione l'applicazione di questi attributi anche per le proprietà associate personalizzate. Lo scopo e la sintassi degli [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] vengono descritti nelle relative pagine di riferimento:  
  
-   <xref:System.Windows.AttachedPropertyBrowsableAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>  
  
-   <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>  
  
<a name="more"></a>   
## <a name="learning-more-about-attached-properties"></a>Ulteriori informazioni sulle proprietà associate  
  
-   Per altre informazioni sulla creazione di una proprietà associata, vedere [Registrare una proprietà associata](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md).  
  
-   Per scenari di utilizzo più avanzati delle proprietà di dipendenza e delle proprietà associate, vedere [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  
  
-   È anche possibile registrare una proprietà come proprietà associata e proprietà di dipendenza, ma continuare a esporre le implementazioni del "wrapper". In questo caso, la proprietà può essere impostata in tale elemento o in qualsiasi elemento tramite la sintassi per le proprietà associate XAML. Un esempio di una proprietà con uno scenario appropriato per gli utilizzi di gestione delle eccezioni standard e collegati è <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.DependencyProperty>  
 [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Registrare una proprietà associata](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)
