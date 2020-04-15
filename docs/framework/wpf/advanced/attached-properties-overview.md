---
title: Cenni preliminari sulle proprietà associate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: 5086401f4616074d364c1d387b751116120d5969
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389006"
---
# <a name="attached-properties-overview"></a>Cenni preliminari sulle proprietà associate

Una proprietà associata è un concetto definito da XAML. Una proprietà associata deve essere usata come un tipo di proprietà globale che è possibile impostare su qualsiasi oggetto. In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] le proprietà associate sono in genere definite come un tipo specializzato di proprietà di dipendenza che non dispone della proprietà "wrapper" convenzionale.

## <a name="prerequisites"></a>Prerequisiti<a name="prerequisites"></a>

Questo argomento presuppone la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer delle proprietà di dipendenza esistenti nelle classi di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md). Per seguire gli esempi in questo argomento, è inoltre necessario comprendere XAML e sapere come scrivere applicazioni WPFWPF.

## <a name="why-use-attached-properties"></a>Perché utilizzare le proprietà associateWhy Use Attached Properties<a name="attached_properties_usage"></a>

Una delle finalità di una proprietà associata consiste nel consentire a diversi elementi figlio di specificare valori univoci di una proprietà effettivamente definita in un elemento padre. Un'applicazione specifica di questo scenario consente agli elementi figlio di notificare all'elemento padre la modalità con cui devono essere presentati nell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Un esempio <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> è la proprietà. La <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà viene creata come proprietà associata perché è progettata per <xref:System.Windows.Controls.DockPanel>essere impostata su elementi contenuti all'interno di un oggetto , anziché su <xref:System.Windows.Controls.DockPanel> se stesso. La <xref:System.Windows.Controls.DockPanel> classe definisce <xref:System.Windows.DependencyProperty> il <xref:System.Windows.Controls.DockPanel.DockProperty>campo statico <xref:System.Windows.Controls.DockPanel.GetDock%2A> denominato <xref:System.Windows.Controls.DockPanel.SetDock%2A> , quindi fornisce i metodi e come funzioni di accesso pubbliche per la proprietà associata.

## <a name="attached-properties-in-xaml"></a>Proprietà associate in XAMLAttached Properties in XAML<a name="attached_properties_xaml"></a>

In XAML, è possibile impostare le proprietà associate usando la sintassi *ProviderProprietàAssociata*.*NomeProprietà*

Di seguito è riportato un <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> esempio di come è possibile impostare in XAML:The following is an example of how you can set in XAML:

[!code-xaml[PropertiesOvwSupport#APBasicUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

Si noti che l'utilizzo è in qualche modo simile a una proprietà statica; si fa sempre <xref:System.Windows.Controls.DockPanel> riferimento al tipo che possiede e registra la proprietà associata, anziché fare riferimento a qualsiasi istanza specificata dal nome.

Inoltre, dato che una proprietà associata in XAML è un attributo che viene impostato nel markup, solo l'operazione di impostazione ha una certa rilevanza. Non è possibile ottenere direttamente una proprietà in XAML, sebbene esistano alcuni meccanismi indiretti per confrontare i valori, ad esempio i trigger negli stili. Per altri dettagli, vedere [Applicazione di stili e modelli](../controls/styling-and-templating.md).

### <a name="attached-property-implementation-in-wpf"></a>Implementazione delle proprietà associate in WPF

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], la maggior parte delle proprietà associate presenti nei tipi WPFWPF correlati alla presentazione dell'interfaccia utente vengono implementate come proprietà di dipendenza. Le proprietà associate sono un concetto XAML, mentre le proprietà di dipendenza sono un concetto WPFWPF. Poiché le proprietà associate WPFWPF sono proprietà di dipendenza, supportano i concetti delle proprietà di dipendenza, ad esempio i metadati della proprietà e i valori predefiniti dai metadati della proprietà.

## <a name="how-attached-properties-are-used-by-the-owning-type"></a>Come le proprietà associate vengono utilizzate dal tipo proprietario<a name="howused"></a>

Anche se le proprietà associate possono essere impostate per qualsiasi oggetto, ciò non significa che l'impostazione della proprietà produce un risultato tangibile o che il valore verrà usato da un altro oggetto. In genere, le proprietà associate sono concepite in modo che gli oggetti provenienti da un'ampia varietà di possibili gerarchie di classi o di relazioni logiche possano ciascuno riportare informazioni comuni al tipo che definisce la proprietà associata. Il tipo che definisce la proprietà associata si attiene di regola a uno di questi modelli:

- Il tipo che definisce la proprietà associata è progettato in modo da poter essere l'elemento padre degli elementi che imposteranno i valori per la proprietà associata. Il tipo scorre quindi gli oggetti figlio attraverso la logica interna in base a una struttura ad albero degli oggetti, ottiene i valori e agisce in qualche modo su tali valori.

- Il tipo che definisce la proprietà associata verrà usato come elemento figlio per un'ampia gamma di elementi padre e modelli di contenuto possibili.

- Il tipo che definisce la proprietà associata rappresenta un servizio. Gli altri tipi impostano i valori per la proprietà associata. Pertanto, quando l'elemento che imposta la proprietà viene valutato nel contesto del servizio, i valori della proprietà associata vengono ottenuti tramite la logica interna della classe del servizio.

### <a name="an-example-of-a-parent-defined-attached-property"></a>Esempio di proprietà associata definita dall'elemento padre

Lo scenario più tipico in cui WPFWPF definisce una proprietà associata è quando un elemento padre supporta una raccolta di elementi figlio e implementa anche un comportamento in cui le specifiche del comportamento vengono segnalate singolarmente per ogni elemento figlio.

<xref:System.Windows.Controls.DockPanel>definisce <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> la proprietà associata e <xref:System.Windows.Controls.DockPanel> dispone di codice a livello <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> di <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>classe come parte della logica di rendering (in particolare e ). Un'istanza <xref:System.Windows.Controls.DockPanel> controllerà sempre se uno dei relativi elementi <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>figlio immediati ha impostato un valore per . In questo caso, tali valori diventano l'input per la logica di rendering applicata a quel particolare elemento figlio. Le <xref:System.Windows.Controls.DockPanel> istanze annidate trattano ognuna le proprie raccolte <xref:System.Windows.Controls.DockPanel> di elementi <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> figlio immediati, ma tale comportamento è specifico dell'implementazione per il modo in cui elabora i valori. In teoria, è possibile che alcune proprietà associate abbiano effetto su elementi più distanti dell'elemento padre immediato. Se <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> la proprietà associata è impostata <xref:System.Windows.Controls.DockPanel> su un elemento che non dispone di alcun elemento padre per agire su di esso, non viene generato alcun errore o eccezione. Ciò significa semplicemente che è stato impostato un <xref:System.Windows.Controls.DockPanel> valore di proprietà globale, ma non dispone di alcun elemento padre corrente che potrebbe utilizzare le informazioni.

## <a name="attached-properties-in-code"></a>Proprietà associate nel codiceAttached Properties in Code<a name="attached_properties_code"></a>

Le proprietà associate in WPFWPF non dispongono dei tipici metodi di "wrapper" CLR per un facile accesso get/set. Ciò è dovuto al fatto che la proprietà associata non fa necessariamente parte dello spazio dei nomi CLR per le istanze in cui la proprietà è impostata. Tuttavia, un processore XAML deve essere in grado di impostare tali valori quando il codice XAML viene analizzato. Per supportare un utilizzo effettivo della proprietà associata, il tipo di proprietario della proprietà associata deve implementare metodi della funzione di accesso dedicati sotto forma **Get_PropertyName_** e **Set_PropertyName_**. Questi metodi della funzione di accesso dedicati sono anche utili per ottenere o impostare la proprietà associata nel codice. Dal punto di vista del codice, una proprietà associata è simile a un campo sottostante che dispone di funzioni di accesso ai metodi anziché di funzioni di accesso alle proprietà e tale campo sottostante può trovarsi in qualsiasi oggetto senza che sia necessario definirlo in modo specifico.

L'esempio seguente illustra come impostare una proprietà associata nel codice. In questo `myCheckBox` esempio, è <xref:System.Windows.Controls.CheckBox> un'istanza della classe .

[!code-csharp[PropertiesOvwSupport#APCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

Analogamente al caso `myCheckBox` XAML, se non fosse `myDockPanel` già stato aggiunto come elemento figlio della quarta riga di codice, la quinta <xref:System.Windows.Controls.DockPanel> riga di codice non genererebbe un'eccezione, ma il valore della proprietà non interagirebbe con un elemento padre e pertanto non farebbe alcuna operazione. Solo <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> un valore impostato su un elemento <xref:System.Windows.Controls.DockPanel> figlio combinato con la presenza di un elemento padre causerà un comportamento efficace nell'applicazione sottoposta a rendering. In questo caso, è possibile impostare la proprietà associata e quindi effettuare l'associazione alla struttura ad albero. In alternativa, è possibile effettuare l'associazione alla struttura ad albero, quindi impostare la proprietà associata. Qualunque sia l'ordine delle azioni, il risultato è il medesimo.

## <a name="attached-property-metadata"></a>Metadati delle proprietà associateAttached Property Metadata<a name="attached_properties_metadata"></a>

Quando si registra <xref:System.Windows.FrameworkPropertyMetadata> la proprietà, viene impostata per specificare le caratteristiche della proprietà, ad esempio se la proprietà influisce sul rendering, la misurazione e così via. I metadati di una proprietà associata non sono in genere diversi rispetto a quelli presenti per una proprietà di dipendenza. Se si specifica un valore predefinito in un override per i metadati di una proprietà associata, tale valore diventa il valore predefinito della proprietà associata implicita nelle istanze della classe che esegue l'override. In particolare, il valore predefinito viene segnalato se un processo esegue una query per recuperare il valore di una proprietà associata tramite la funzione di accesso al metodo `Get` di quella proprietà, specificando un'istanza della classe in cui sono stati definiti i metadati e il valore per quella proprietà collegata non è stato impostato diversamente.

Se si vuole abilitare l'ereditarietà del valore di una proprietà, è necessario usare le proprietà associate anziché le proprietà di dipendenza non associate. Per informazioni dettagliate, vedere [Ereditarietà del valore della proprietà](property-value-inheritance.md).

## <a name="custom-attached-properties"></a>Proprietà associate personalizzate<a name="custom"></a>

### <a name="when-to-create-an-attached-property"></a>Quando creare una proprietà associataWhen to Create an Attached Property<a name="create_attached_properties"></a>

È possibile creare una proprietà associata quando è necessario disporre di un meccanismo di impostazione delle proprietà per le classi diverse dalla classe di definizione. In questo caso, lo scenario più comune è il layout. Esempi di proprietà <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>di <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>layout <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>esistenti sono , , e . Nello scenario abilitato in questo contesto, gli elementi disponibili come elementi figlio degli elementi di controllo del layout sono in grado di indicare i requisiti del layout agli elementi padre del layout singolarmente, impostando ciascuno un valore della proprietà definito dall'elemento padre come proprietà associata.

Un altro scenario per l'uso di una proprietà associata è quello in cui la classe rappresenta un servizio e si vuole che le classi siano in grado di integrare il servizio in modo più trasparente.

Ancora un altro scenario consiste nel ricevere il supporto di Progettazione WPF di Visual Studio, ad esempio la modifica della finestra Proprietà.Anan another scenario is to receive Visual Studio WPF Designer support, such as **Properties** window editing. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).

Come indicato in precedenza, è necessario eseguire la registrazione come proprietà associata se si vuole usare l'ereditarietà del valore della proprietà.

### <a name="how-to-create-an-attached-property"></a>Come creare una proprietà associataHow to Create an Attached Property<a name="how_do_i_create_attached_properties"></a>

Se la classe definisce la proprietà associata esclusivamente per l'utilizzo su <xref:System.Windows.DependencyObject>altri tipi, la classe non deve derivare da . Ma è necessario derivare da <xref:System.Windows.DependencyObject> se si segue il modello WPF globale di avere la proprietà associata anche essere una proprietà di dipendenza.

Definire la proprietà associata come proprietà di `public static readonly` dipendenza <xref:System.Windows.DependencyProperty>dichiarando un campo di tipo . Per definire questo campo, utilizzare <xref:System.Windows.DependencyProperty.RegisterAttached%2A> il valore restituito del metodo. Il nome del campo deve corrispondere al nome `Property`della proprietà associata, aggiunto con la stringa , per seguire il modello WPF stabilito di denominazione dei campi di identificazione rispetto alle proprietà che rappresentano. Il provider della proprietà associata deve inoltre fornire metodi **statici Get_PropertyName_** e **Set_PropertyName_** come funzioni di accesso per la proprietà associata. in caso contrario, il sistema di proprietà non sarà in grado di utilizzare la proprietà associata.

> [!NOTE]
> Se si ometti la funzione di accesso get della proprietà associata, l'associazione dati sulla proprietà non funzionerà negli strumenti di progettazione, ad esempio Visual Studio e Blend per Visual Studio.

#### <a name="the-get-accessor"></a>Funzione di accesso Get

La firma per la funzione di accesso **Get_PropertyName_** deve essere:

`public static object GetPropertyName(object target)`

- L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. Ad esempio, <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> il metodo <xref:System.Windows.UIElement>digita il parametro come , poiché <xref:System.Windows.UIElement> la proprietà associata deve essere impostata solo sulle istanze.

- Il valore restituito può essere specificato come tipo più specifico nell'implementazione. Ad esempio, <xref:System.Windows.Controls.DockPanel.GetDock%2A> il metodo <xref:System.Windows.Controls.Dock>lo digita come , perché il valore può essere impostato solo su tale enumerazione.

#### <a name="the-set-accessor"></a>Funzione di accesso Set

La firma per la funzione di accesso **Set_PropertyName_** deve essere:

`public static void SetPropertyName(object target, object value)`

- L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. Ad esempio, <xref:System.Windows.Controls.DockPanel.SetDock%2A> il metodo <xref:System.Windows.UIElement>lo digita come , poiché la <xref:System.Windows.UIElement> proprietà associata deve essere impostata solo sulle istanze.

- L'oggetto `value` può essere specificato come tipo più specifico nell'implementazione. Ad esempio, <xref:System.Windows.Controls.DockPanel.SetDock%2A> il metodo <xref:System.Windows.Controls.Dock>lo digita come , perché il valore può essere impostato solo su tale enumerazione. Tenere presente che il valore per questo metodo è l'input proveniente dal caricatore XAML quando rileva la proprietà associata in un utilizzo della proprietà associata nel markup. Tale input è il valore specificato come valore di attributo XAML nel markup. Pertanto, per il tipo usato devono essere disponibili la conversione di tipo, il serializzatore del valore o il supporto per l'estensione di markup, in modo da poter creare il tipo appropriato in base al valore dell'attributo, rappresentato in pratica semplicemente da una stringa.

Nell'esempio seguente viene illustrata la <xref:System.Windows.DependencyProperty.RegisterAttached%2A> registrazione della proprietà di dipendenza (tramite il metodo), nonché le funzioni di **accesso Get_PropertyName_** e **Set_PropertyName_.** Nell'esempio, la proprietà associata è denominata `IsBubbleSource`. Pertanto, le funzioni di accesso devono essere chiamate `GetIsBubbleSource` e `SetIsBubbleSource`.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>Attributi delle proprietà associate

WPFWPF definisce diversi attributi .NET che hanno lo scopo di fornire informazioni sulle proprietà associate ai processi di reflection e agli utenti tipici di reflection e informazioni sulle proprietà, ad esempio finestre di progettazione. Dato che le proprietà associate hanno un tipo con ambito illimitato, le finestre di progettazione devono disporre di un modo per evitare di sopraffare gli utenti con un elenco globale di tutte le proprietà associate definite in una particolare implementazione della tecnologia che usa XAML. Gli attributi .NET che WPFWPF definisce per le proprietà associate possono essere utilizzati per definire l'ambito delle situazioni in cui una determinata proprietà associata deve essere visualizzata in una finestra delle proprietà. È possibile prendere in considerazione l'applicazione di questi attributi anche per le proprietà associate personalizzate. Lo scopo e la sintassi degli attributi .NET sono descritti nelle pagine di riferimento appropriate:

- <xref:System.Windows.AttachedPropertyBrowsableAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## <a name="learning-more-about-attached-properties"></a>Ulteriori informazioni sulle proprietà associate<a name="more"></a>

- Per altre informazioni sulla creazione di una proprietà associata, vedere [Registrare una proprietà associata](how-to-register-an-attached-property.md).

- Per scenari di utilizzo più avanzati delle proprietà di dipendenza e delle proprietà associate, vedere [Proprietà di dipendenza personalizzate](custom-dependency-properties.md).

- È anche possibile registrare una proprietà come proprietà associata e proprietà di dipendenza, ma continuare a esporre le implementazioni del "wrapper". In questo caso, la proprietà può essere impostata in tale elemento o in qualsiasi elemento tramite la sintassi per le proprietà associate XAML. Un esempio di proprietà con uno scenario appropriato sia <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>per gli utilizzi standard che per gli utilizzi associati è .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.DependencyProperty>
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Registrare una proprietà associata](how-to-register-an-attached-property.md)
