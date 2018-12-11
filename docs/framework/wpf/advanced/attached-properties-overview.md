---
title: Cenni preliminari sulle proprietà associate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: bcf218efeb7bff5f7457164411efed796314ba82
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129480"
---
# <a name="attached-properties-overview"></a>Cenni preliminari sulle proprietà associate

Una proprietà associata è un concetto definito da XAML. Una proprietà associata deve essere usata come un tipo di proprietà globale che è possibile impostare su qualsiasi oggetto. In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] le proprietà associate sono in genere definite come un tipo specializzato di proprietà di dipendenza che non dispone della proprietà "wrapper" convenzionale.

## Prerequisiti <a name="prerequisites"></a>

Questo argomento presuppone la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer delle proprietà di dipendenza esistenti nelle classi di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md). Per seguire gli esempi in questo argomento, è anche necessario conoscere XAML e saper scrivere applicazioni WPF.

## Perché usare le proprietà associate <a name="attached_properties_usage"></a>

Una delle finalità di una proprietà associata consiste nel consentire a diversi elementi figlio di specificare valori univoci di una proprietà effettivamente definita in un elemento padre. Un'applicazione specifica di questo scenario consente agli elementi figlio di notificare all'elemento padre la modalità con cui devono essere presentati nell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Un esempio è il <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà. Il <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà viene creata come una proprietà associata perché è progettato per essere impostate su elementi contenuti all'interno di un <xref:System.Windows.Controls.DockPanel>, anziché sul <xref:System.Windows.Controls.DockPanel> stesso. Il <xref:System.Windows.Controls.DockPanel> classe definisce il metodo statico <xref:System.Windows.DependencyProperty> campo denominato <xref:System.Windows.Controls.DockPanel.DockProperty>e quindi fornisce i <xref:System.Windows.Controls.DockPanel.GetDock%2A> e <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodi come funzioni di accesso pubbliche della proprietà associata.

## Proprietà associate in XAML <a name="attached_properties_xaml"></a>

In XAML, è possibile impostare le proprietà associate usando la sintassi *ProviderProprietàAssociata*.*NomeProprietà*

Di seguito è riportato un esempio di come è possibile impostare <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> in XAML:

[!code-xaml[PropertiesOvwSupport#APBasicUsage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

Si noti che l'utilizzo è simile a una proprietà statica; sempre fare riferimento al tipo <xref:System.Windows.Controls.DockPanel> che possiede e si registra la proprietà associata, anziché fare riferimento a qualsiasi istanza specificata in base al nome.

Inoltre, dato che una proprietà associata in XAML è un attributo che viene impostato nel markup, solo l'operazione di impostazione ha una certa rilevanza. Non è possibile ottenere direttamente una proprietà in XAML, sebbene esistano alcuni meccanismi indiretti per confrontare i valori, ad esempio i trigger negli stili. Per altri dettagli, vedere [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).

### <a name="attached-property-implementation-in-wpf"></a>Implementazione delle proprietà associate in WPF

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], la maggior parte delle proprietà associate esistenti sui tipi WPF che riguardano la presentazione dell'interfaccia utente vengono implementata come proprietà di dipendenza. Le proprietà associate sono un concetto di XAML, mentre le proprietà di dipendenza sono un concetto WPF. Poiché le proprietà WPF collegati sono proprietà di dipendenza, supportano concetti correlati alle proprietà di dipendenza, ad esempio i metadati della proprietà e i valori predefiniti che i metadati della proprietà.

## Come le proprietà associate vengono usate da parte del tipo proprietario <a name="howused"></a>

Anche se le proprietà associate possono essere impostate per qualsiasi oggetto, ciò non significa che l'impostazione della proprietà produce un risultato tangibile o che il valore verrà usato da un altro oggetto. In genere, le proprietà associate sono concepite in modo che gli oggetti provenienti da un'ampia varietà di possibili gerarchie di classi o di relazioni logiche possano ciascuno riportare informazioni comuni al tipo che definisce la proprietà associata. Il tipo che definisce la proprietà associata si attiene di regola a uno di questi modelli:

-   Il tipo che definisce la proprietà associata è progettato in modo da poter essere l'elemento padre degli elementi che imposteranno i valori per la proprietà associata. Il tipo scorre quindi gli oggetti figlio attraverso la logica interna in base a una struttura ad albero degli oggetti, ottiene i valori e agisce in qualche modo su tali valori.

-   Il tipo che definisce la proprietà associata verrà usato come elemento figlio per un'ampia gamma di elementi padre e modelli di contenuto possibili.

-   Il tipo che definisce la proprietà associata rappresenta un servizio. Gli altri tipi impostano i valori per la proprietà associata. Pertanto, quando l'elemento che imposta la proprietà viene valutato nel contesto del servizio, i valori della proprietà associata vengono ottenuti tramite la logica interna della classe del servizio.

### <a name="an-example-of-a-parent-defined-attached-property"></a>Esempio di proprietà associata definita dall'elemento padre

Lo scenario più comune in cui WPF definisce una proprietà associata è quando un elemento padre supporta una raccolta di elementi figlio e implementa inoltre un comportamento in cui le specifiche del comportamento vengono segnalate singolarmente per ogni elemento figlio.

<xref:System.Windows.Controls.DockPanel> Definisce i <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà associata, e <xref:System.Windows.Controls.DockPanel> dispone di codice a livello di classe come parte della logica di rendering (in particolare <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> e <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>). Oggetto <xref:System.Windows.Controls.DockPanel> istanza sempre controllerà se uno qualsiasi dei relativi elementi figlio immediati ha impostato un valore per <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. In questo caso, tali valori diventano l'input per la logica di rendering applicata a quel particolare elemento figlio. Annidato <xref:System.Windows.Controls.DockPanel> istanze ogni trattare le proprie raccolte di elementi figlio immediati, ma questo comportamento è specifico dell'implementazione al modo in cui <xref:System.Windows.Controls.DockPanel> processi <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> valori. In teoria, è possibile che alcune proprietà associate abbiano effetto su elementi più distanti dell'elemento padre immediato. Se il <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà associata è impostata su un elemento che non ha alcun <xref:System.Windows.Controls.DockPanel> viene generato l'elemento padre su cui intervenire, nessun errore o eccezione. Ciò significa semplicemente che è stato impostato un valore della proprietà globale, ma presente alcun elemento <xref:System.Windows.Controls.DockPanel> padre che possa usare le informazioni.

## Proprietà associate nel codice <a name="attached_properties_code"></a>

Le proprietà associate in WPF non dispongono dei tipici [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] metodi "wrapper" per l'accesso facile ottenere o impostare. Ciò è dovuto al fatto che la proprietà associata non è necessariamente inclusa nello spazio dei nomi [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] per le istanze in cui la proprietà è impostata. Tuttavia, un processore XAML deve essere in grado di impostare tali valori quando il codice XAML viene analizzato. Per supportare un utilizzo efficace delle proprietà associata, il tipo di proprietario della proprietà associata deve implementare i metodi della funzione di accesso dedicati nel formato **Get_PropertyName_** e **Set_PropertyName_**. Questi metodi della funzione di accesso dedicati sono anche utili per ottenere o impostare la proprietà associata nel codice. Dal punto di vista del codice, una proprietà associata è simile a un campo sottostante che dispone di funzioni di accesso ai metodi anziché di funzioni di accesso alle proprietà e tale campo sottostante può trovarsi in qualsiasi oggetto senza che sia necessario definirlo in modo specifico.

L'esempio seguente illustra come impostare una proprietà associata nel codice. In questo esempio `myCheckBox` è un'istanza del <xref:System.Windows.Controls.CheckBox> classe.

[!code-csharp[PropertiesOvwSupport#APCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

Caso analogo per il XAML, se `myCheckBox` non fosse già stato aggiunto come elemento figlio di `myDockPanel` dalla terza riga di codice, la quarta riga del codice non genera un'eccezione, ma il valore della proprietà non può interagire con un <xref:System.Windows.Controls.DockPanel> padre e di conseguenza viene eseguita alcuna operazione. Solo un <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> impostata su un elemento figlio combinato con la presenza di un <xref:System.Windows.Controls.DockPanel> elemento padre provocherà un comportamento effettivo nell'applicazione sottoposta a rendering. In questo caso, è possibile impostare la proprietà associata e quindi effettuare l'associazione alla struttura ad albero. In alternativa, è possibile effettuare l'associazione alla struttura ad albero, quindi impostare la proprietà associata. Qualunque sia l'ordine delle azioni, il risultato è il medesimo.

## Metadati delle proprietà associate <a name="attached_properties_metadata"></a>

Quando si registra la proprietà, <xref:System.Windows.FrameworkPropertyMetadata> è impostato per specificare le caratteristiche della proprietà, ad esempio se la proprietà influisce sul rendering, misurazione e così via. I metadati di una proprietà associata non sono in genere diversi rispetto a quelli presenti per una proprietà di dipendenza. Se si specifica un valore predefinito in un override per i metadati di una proprietà associata, tale valore diventa il valore predefinito della proprietà associata implicita nelle istanze della classe che esegue l'override. In particolare, il valore predefinito viene segnalato se un processo esegue una query per recuperare il valore di una proprietà associata tramite la funzione di accesso al metodo `Get` di quella proprietà, specificando un'istanza della classe in cui sono stati definiti i metadati e il valore per quella proprietà collegata non è stato impostato diversamente.

Se si vuole abilitare l'ereditarietà del valore di una proprietà, è necessario usare le proprietà associate anziché le proprietà di dipendenza non associate. Per informazioni dettagliate, vedere [Ereditarietà del valore della proprietà](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).

## Proprietà associate personalizzate <a name="custom"></a>

### Creazione di una proprietà associata <a name="create_attached_properties"></a>

È possibile creare una proprietà associata quando è necessario disporre di un meccanismo di impostazione delle proprietà per le classi diverse dalla classe di definizione. In questo caso, lo scenario più comune è il layout. Sono esempi di proprietà di layout esistente <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>, e <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>. Nello scenario abilitato in questo contesto, gli elementi disponibili come elementi figlio degli elementi di controllo del layout sono in grado di indicare i requisiti del layout agli elementi padre del layout singolarmente, impostando ciascuno un valore della proprietà definito dall'elemento padre come proprietà associata.

Un altro scenario per l'uso di una proprietà associata è quello in cui la classe rappresenta un servizio e si vuole che le classi siano in grado di integrare il servizio in modo più trasparente.

Infine, un altro scenario prevede di ricevere supporto in Visual Studio WPF Designer, ad esempio **proprietà** la modifica della finestra. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md).

Come indicato in precedenza, è necessario eseguire la registrazione come proprietà associata se si vuole usare l'ereditarietà del valore della proprietà.

### Come creare una proprietà associata <a name="how_do_i_create_attached_properties"></a>

Se la classe definisce la proprietà associata esclusivamente per l'uso in altri tipi, quindi non deve derivare dalla classe <xref:System.Windows.DependencyObject>. Ma è necessario derivare da <xref:System.Windows.DependencyObject> se si segue il modello generale di WPF di avere la proprietà associata sia anche una proprietà di dipendenza.

Definire la proprietà associata come proprietà di dipendenza dichiarando un `public static readonly` campo di tipo <xref:System.Windows.DependencyProperty>. È possibile definire questo campo usando il valore restituito del <xref:System.Windows.DependencyProperty.RegisterAttached%2A> (metodo). Il nome del campo deve corrispondere al nome di proprietà associata, viene aggiunto la stringa `Property`, seguire il modello WPF stabilito di denominazione dei campi di identificazione in base alle proprietà che rappresentano. Il provider di proprietà associata deve inoltre fornire statica **Get_PropertyName_** e **Set_PropertyName_** metodi come funzioni di accesso per la proprietà associata; riesce a eseguire questa operazione comporterà la proprietà sistema sia in grado di usare la proprietà associata.

> [!NOTE]
> Se si omette di accesso get della proprietà associata, data binding per la proprietà non funzionerà negli strumenti di progettazione, ad esempio Visual Studio ed Expression Blend.

#### <a name="the-get-accessor"></a>Funzione di accesso Get

La firma per il **Get_PropertyName_** della funzione di accesso deve essere:

`public static object GetPropertyName(object target)`

-   L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. Ad esempio, il <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> parametro, come i tipi di metodo <xref:System.Windows.UIElement>, perché la proprietà associata è destinata esclusivamente al nelze nastavit <xref:System.Windows.UIElement> istanze.

-   Il valore restituito può essere specificato come tipo più specifico nell'implementazione. Ad esempio, il <xref:System.Windows.Controls.DockPanel.GetDock%2A> come tipi di metodo <xref:System.Windows.Controls.Dock>, perché il valore può essere impostato solo su tale enumerazione.

#### <a name="the-set-accessor"></a>Funzione di accesso Set

La firma per il **Set_PropertyName_** della funzione di accesso deve essere:

`public static void SetPropertyName(object target, object value)`

-   L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. Ad esempio, il <xref:System.Windows.Controls.DockPanel.SetDock%2A> come tipi di metodo <xref:System.Windows.UIElement>, perché la proprietà associata è destinata esclusivamente al nelze nastavit <xref:System.Windows.UIElement> istanze.

-   L'oggetto `value` può essere specificato come tipo più specifico nell'implementazione. Ad esempio, il <xref:System.Windows.Controls.DockPanel.SetDock%2A> come tipi di metodo <xref:System.Windows.Controls.Dock>, perché il valore può essere impostato solo su tale enumerazione. Tenere presente che il valore per questo metodo è l'input proveniente dal caricatore XAML quando rileva la proprietà associata in un utilizzo della proprietà associata nel markup. Tale input è il valore specificato come valore di attributo XAML nel markup. Pertanto, per il tipo usato devono essere disponibili la conversione di tipo, il serializzatore del valore o il supporto per l'estensione di markup, in modo da poter creare il tipo appropriato in base al valore dell'attributo, rappresentato in pratica semplicemente da una stringa.

L'esempio seguente illustra la registrazione di proprietà di dipendenza (usando il <xref:System.Windows.DependencyProperty.RegisterAttached%2A> metodo), nonché il **Get_PropertyName_** e **Set_PropertyName_** funzioni di accesso. Nell'esempio, la proprietà associata è denominata `IsBubbleSource`. Pertanto, le funzioni di accesso devono essere chiamate `GetIsBubbleSource` e `SetIsBubbleSource`.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>Attributi delle proprietà associate

WPF definisce vari [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] che sono destinate a fornire informazioni sulle proprietà associate ai processi di reflection e agli utenti tipici della reflection e sulle proprietà, ad esempio le finestre di progettazione. Dato che le proprietà associate hanno un tipo con ambito illimitato, le finestre di progettazione devono disporre di un modo per evitare di sopraffare gli utenti con un elenco globale di tutte le proprietà associate definite in una particolare implementazione della tecnologia che usa XAML. Il [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] da WPF definisce per le proprietà associate possono essere usate per definire l'ambito di situazioni in cui una proprietà associata di specificato deve essere visualizzata in una finestra delle proprietà. È possibile prendere in considerazione l'applicazione di questi attributi anche per le proprietà associate personalizzate. Lo scopo e la sintassi degli [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] vengono descritti nelle relative pagine di riferimento:

-   <xref:System.Windows.AttachedPropertyBrowsableAttribute>

-   <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

-   <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

-   <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## Ulteriori informazioni sulle proprietà associate <a name="more"></a>

-   Per altre informazioni sulla creazione di una proprietà associata, vedere [Registrare una proprietà associata](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md).

-   Per scenari di utilizzo più avanzati delle proprietà di dipendenza e delle proprietà associate, vedere [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).

-   È anche possibile registrare una proprietà come proprietà associata e proprietà di dipendenza, ma continuare a esporre le implementazioni del "wrapper". In questo caso, la proprietà può essere impostata in tale elemento o in qualsiasi elemento tramite la sintassi per le proprietà associate XAML. Un esempio di una proprietà con uno scenario adatto per gli utilizzi sia standard sia collegati è <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.DependencyProperty>
- [Panoramica sulle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
- [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Registrare una proprietà associata](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md)