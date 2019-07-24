---
title: Cenni preliminari sulle proprietà associate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF Designer]
ms.assetid: 75928354-dc01-47e8-a018-8409aec1f32d
ms.openlocfilehash: 2eacb0ff49b868f144bf35af4bb64b7d049b30cb
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401379"
---
# <a name="attached-properties-overview"></a>Cenni preliminari sulle proprietà associate

Una proprietà associata è un concetto definito da XAML. Una proprietà associata deve essere usata come un tipo di proprietà globale che è possibile impostare su qualsiasi oggetto. In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] le proprietà associate sono in genere definite come un tipo specializzato di proprietà di dipendenza che non dispone della proprietà "wrapper" convenzionale.

## Prerequisiti<a name="prerequisites"></a>

Questo argomento presuppone la conoscenza delle proprietà di dipendenza dal punto di vista di un consumer delle proprietà di dipendenza esistenti nelle classi di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], nonché la lettura dell'argomento [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md). Per seguire gli esempi in questo argomento, è necessario comprendere anche XAML e sapere come scrivere applicazioni WPF.

## Perché usare le proprietà associate<a name="attached_properties_usage"></a>

Una delle finalità di una proprietà associata consiste nel consentire a diversi elementi figlio di specificare valori univoci di una proprietà effettivamente definita in un elemento padre. Un'applicazione specifica di questo scenario consente agli elementi figlio di notificare all'elemento padre la modalità con cui devono essere presentati nell'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]. Un esempio è la <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà. La <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà viene creata come proprietà associata perché è progettata per essere impostata su elementi contenuti all'interno di un <xref:System.Windows.Controls.DockPanel>, anziché su <xref:System.Windows.Controls.DockPanel> se stesso. La <xref:System.Windows.Controls.DockPanel> classe definisce il campo <xref:System.Windows.DependencyProperty> statico denominato <xref:System.Windows.Controls.DockPanel.DockProperty>, quindi fornisce i <xref:System.Windows.Controls.DockPanel.GetDock%2A> metodi e <xref:System.Windows.Controls.DockPanel.SetDock%2A> come funzioni di accesso pubbliche per la proprietà associata.

## Proprietà associate in XAML<a name="attached_properties_xaml"></a>

In XAML, è possibile impostare le proprietà associate usando la sintassi *ProviderProprietàAssociata*.*NomeProprietà*

Di seguito è riportato un esempio di come è possibile <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> impostare in XAML:

[!code-xaml[PropertiesOvwSupport#APBasicUsage](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#apbasicusage)]

Si noti che l'utilizzo è piuttosto simile a una proprietà statica. si fa sempre riferimento al <xref:System.Windows.Controls.DockPanel> tipo proprietario e si registra la proprietà associata, anziché fare riferimento a qualsiasi istanza specificata in base al nome.

Inoltre, dato che una proprietà associata in XAML è un attributo che viene impostato nel markup, solo l'operazione di impostazione ha una certa rilevanza. Non è possibile ottenere direttamente una proprietà in XAML, sebbene esistano alcuni meccanismi indiretti per confrontare i valori, ad esempio i trigger negli stili. Per altri dettagli, vedere [Applicazione di stili e modelli](../controls/styling-and-templating.md).

### <a name="attached-property-implementation-in-wpf"></a>Implementazione delle proprietà associate in WPF

In [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]la maggior parte delle proprietà associate presenti nei tipi WPF correlati alla presentazione dell'interfaccia utente viene implementata come proprietà di dipendenza. Le proprietà associate sono un concetto XAML, mentre le proprietà di dipendenza sono un concetto WPF. Poiché le proprietà associate a WPF sono proprietà di dipendenza, supportano concetti della proprietà di dipendenza quali i metadati della proprietà e i valori predefiniti dei metadati della proprietà.

## Modalità di utilizzo delle proprietà associate da parte del tipo proprietario<a name="howused"></a>

Anche se le proprietà associate possono essere impostate per qualsiasi oggetto, ciò non significa che l'impostazione della proprietà produce un risultato tangibile o che il valore verrà usato da un altro oggetto. In genere, le proprietà associate sono concepite in modo che gli oggetti provenienti da un'ampia varietà di possibili gerarchie di classi o di relazioni logiche possano ciascuno riportare informazioni comuni al tipo che definisce la proprietà associata. Il tipo che definisce la proprietà associata si attiene di regola a uno di questi modelli:

- Il tipo che definisce la proprietà associata è progettato in modo da poter essere l'elemento padre degli elementi che imposteranno i valori per la proprietà associata. Il tipo scorre quindi gli oggetti figlio attraverso la logica interna in base a una struttura ad albero degli oggetti, ottiene i valori e agisce in qualche modo su tali valori.

- Il tipo che definisce la proprietà associata verrà usato come elemento figlio per un'ampia gamma di elementi padre e modelli di contenuto possibili.

- Il tipo che definisce la proprietà associata rappresenta un servizio. Gli altri tipi impostano i valori per la proprietà associata. Pertanto, quando l'elemento che imposta la proprietà viene valutato nel contesto del servizio, i valori della proprietà associata vengono ottenuti tramite la logica interna della classe del servizio.

### <a name="an-example-of-a-parent-defined-attached-property"></a>Esempio di proprietà associata definita dall'elemento padre

Lo scenario più comune in cui WPF definisce una proprietà associata è quando un elemento padre supporta una raccolta di elementi figlio e implementa anche un comportamento in cui le specifiche del comportamento vengono segnalate singolarmente per ogni elemento figlio.

<xref:System.Windows.Controls.DockPanel>definisce la <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà associata e <xref:System.Windows.Controls.DockPanel> dispone di codice a livello di classe come parte della logica di rendering (in <xref:System.Windows.Controls.DockPanel.MeasureOverride%2A> particolare <xref:System.Windows.Controls.DockPanel.ArrangeOverride%2A>, e). Un' <xref:System.Windows.Controls.DockPanel> istanza di verificherà sempre se uno degli elementi figlio immediati ha impostato un valore per <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>. In questo caso, tali valori diventano l'input per la logica di rendering applicata a quel particolare elemento figlio. Ognuna <xref:System.Windows.Controls.DockPanel> delle istanze annidate considera le raccolte di elementi figlio immediate, ma tale comportamento è specifico dell'implementazione <xref:System.Windows.Controls.DockPanel> per <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> la modalità di elaborazione dei valori. In teoria, è possibile che alcune proprietà associate abbiano effetto su elementi più distanti dell'elemento padre immediato. Se la <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> proprietà associata è impostata su un elemento che non <xref:System.Windows.Controls.DockPanel> ha un elemento padre su cui agire, non viene generato alcun errore o eccezione. Ciò significa semplicemente che è stato impostato un valore di proprietà globale, ma non dispone <xref:System.Windows.Controls.DockPanel> di un elemento padre corrente che potrebbe utilizzare le informazioni.

## Proprietà associate nel codice<a name="attached_properties_code"></a>

Le proprietà associate in WPF non dispongono dei tipici metodi "wrapper" di CLR per un accesso semplice di tipo get/set. Ciò è dovuto al fatto che la proprietà associata non appartiene necessariamente allo spazio dei nomi CLR per le istanze in cui è impostata la proprietà. Tuttavia, un processore XAML deve essere in grado di impostare tali valori quando il codice XAML viene analizzato. Per supportare un utilizzo efficace delle proprietà associate, il tipo di proprietario della proprietà associata deve implementare i metodi delle funzioni di accesso dedicate nel formato **Get_PropertyName_** e **Set_PropertyName_** . Questi metodi della funzione di accesso dedicati sono anche utili per ottenere o impostare la proprietà associata nel codice. Dal punto di vista del codice, una proprietà associata è simile a un campo sottostante che dispone di funzioni di accesso ai metodi anziché di funzioni di accesso alle proprietà e tale campo sottostante può trovarsi in qualsiasi oggetto senza che sia necessario definirlo in modo specifico.

L'esempio seguente illustra come impostare una proprietà associata nel codice. In questo esempio, `myCheckBox` è un'istanza <xref:System.Windows.Controls.CheckBox> della classe.

[!code-csharp[PropertiesOvwSupport#APCode](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#apcode)]
[!code-vb[PropertiesOvwSupport#APCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#apcode)]

Analogamente al caso XAML, se `myCheckBox` non è già stato aggiunto come elemento figlio di `myDockPanel` dalla terza riga di codice, la quarta riga di codice non genera un'eccezione, ma il valore della proprietà non interagisce con un <xref:System.Windows.Controls.DockPanel> elemento padre e pertanto non esegue alcuna operazione. Solo un <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType> valore impostato su un elemento figlio combinato con la presenza di un <xref:System.Windows.Controls.DockPanel> elemento padre provocherà un comportamento effettivo nell'applicazione sottoposta a rendering. In questo caso, è possibile impostare la proprietà associata e quindi effettuare l'associazione alla struttura ad albero. In alternativa, è possibile effettuare l'associazione alla struttura ad albero, quindi impostare la proprietà associata. Qualunque sia l'ordine delle azioni, il risultato è il medesimo.

## Metadati delle proprietà associate<a name="attached_properties_metadata"></a>

Quando si registra la proprietà, <xref:System.Windows.FrameworkPropertyMetadata> viene impostato per specificare le caratteristiche della proprietà, ad esempio se la proprietà influisca sul rendering, sulla misurazione e così via. I metadati di una proprietà associata non sono in genere diversi rispetto a quelli presenti per una proprietà di dipendenza. Se si specifica un valore predefinito in un override per i metadati di una proprietà associata, tale valore diventa il valore predefinito della proprietà associata implicita nelle istanze della classe che esegue l'override. In particolare, il valore predefinito viene segnalato se un processo esegue una query per recuperare il valore di una proprietà associata tramite la funzione di accesso al metodo `Get` di quella proprietà, specificando un'istanza della classe in cui sono stati definiti i metadati e il valore per quella proprietà collegata non è stato impostato diversamente.

Se si vuole abilitare l'ereditarietà del valore di una proprietà, è necessario usare le proprietà associate anziché le proprietà di dipendenza non associate. Per informazioni dettagliate, vedere [Ereditarietà del valore della proprietà](property-value-inheritance.md).

## Proprietà associate personalizzate<a name="custom"></a>

### Quando creare una proprietà associata<a name="create_attached_properties"></a>

È possibile creare una proprietà associata quando è necessario disporre di un meccanismo di impostazione delle proprietà per le classi diverse dalla classe di definizione. In questo caso, lo scenario più comune è il layout. Esempi di proprietà di layout esistenti <xref:System.Windows.Controls.DockPanel.Dock%2A?displayProperty=nameWithType>sono <xref:System.Windows.Controls.Panel.ZIndex%2A?displayProperty=nameWithType>, e <xref:System.Windows.Controls.Canvas.Top%2A?displayProperty=nameWithType>. Nello scenario abilitato in questo contesto, gli elementi disponibili come elementi figlio degli elementi di controllo del layout sono in grado di indicare i requisiti del layout agli elementi padre del layout singolarmente, impostando ciascuno un valore della proprietà definito dall'elemento padre come proprietà associata.

Un altro scenario per l'uso di una proprietà associata è quello in cui la classe rappresenta un servizio e si vuole che le classi siano in grado di integrare il servizio in modo più trasparente.

Un altro scenario è la ricezione del supporto di progettazione WPF di Visual Studio, ad esempio la modifica della finestra **Proprietà** . Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).

Come indicato in precedenza, è necessario eseguire la registrazione come proprietà associata se si vuole usare l'ereditarietà del valore della proprietà.

### Come creare una proprietà associata<a name="how_do_i_create_attached_properties"></a>

Se la classe definisce la proprietà associata esclusivamente per l'uso in altri tipi, la classe non deve derivare da <xref:System.Windows.DependencyObject>. Tuttavia, è necessario derivare da <xref:System.Windows.DependencyObject> se si segue il modello WPF generale di che la proprietà associata sia anche una proprietà di dipendenza.

Definire la proprietà associata come proprietà di dipendenza dichiarando un `public static readonly` campo di tipo <xref:System.Windows.DependencyProperty>. Questo campo viene definito usando il valore restituito del <xref:System.Windows.DependencyProperty.RegisterAttached%2A> metodo. Il nome del campo deve corrispondere al nome della proprietà associata, accodato con `Property`la stringa, per seguire il modello WPF stabilito di denominazione dei campi di identificazione rispetto alle proprietà che rappresentano. Il provider di proprietà associate deve fornire anche metodi **Get_PropertyName_** e **Set_PropertyName_** statici come funzioni di accesso per la proprietà associata. in caso contrario, il sistema di proprietà non potrà utilizzare la proprietà associata.

> [!NOTE]
> Se si omette la funzione di accesso get della proprietà associata, data binding sulla proprietà non funzionerà negli strumenti di progettazione, ad esempio Visual Studio ed Expression Blend.

#### <a name="the-get-accessor"></a>Funzione di accesso Get

La firma per la funzione di accesso **Get_PropertyName_** deve essere:

`public static object GetPropertyName(object target)`

- L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. Il <xref:System.Windows.Controls.DockPanel.GetDock%2A?displayProperty=nameWithType> metodo, ad esempio, digita il parametro <xref:System.Windows.UIElement>come, perché la proprietà associata è <xref:System.Windows.UIElement> destinata solo a essere impostata per le istanze.

- Il valore restituito può essere specificato come tipo più specifico nell'implementazione. Il <xref:System.Windows.Controls.DockPanel.GetDock%2A> metodo, ad esempio, lo digita <xref:System.Windows.Controls.Dock>come, perché il valore può essere impostato solo su tale enumerazione.

#### <a name="the-set-accessor"></a>Funzione di accesso Set

La firma per la funzione di accesso **Set_PropertyName_** deve essere:

`public static void SetPropertyName(object target, object value)`

- L'oggetto `target` può essere specificato come tipo più specifico nell'implementazione. Il <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodo, ad esempio, lo digita <xref:System.Windows.UIElement>come, perché la proprietà associata è <xref:System.Windows.UIElement> destinata solo a essere impostata per le istanze.

- L'oggetto `value` può essere specificato come tipo più specifico nell'implementazione. Il <xref:System.Windows.Controls.DockPanel.SetDock%2A> metodo, ad esempio, lo digita <xref:System.Windows.Controls.Dock>come, perché il valore può essere impostato solo su tale enumerazione. Tenere presente che il valore per questo metodo è l'input proveniente dal caricatore XAML quando rileva la proprietà associata in un utilizzo della proprietà associata nel markup. Tale input è il valore specificato come valore di attributo XAML nel markup. Pertanto, per il tipo usato devono essere disponibili la conversione di tipo, il serializzatore del valore o il supporto per l'estensione di markup, in modo da poter creare il tipo appropriato in base al valore dell'attributo, rappresentato in pratica semplicemente da una stringa.

Nell'esempio seguente viene illustrata la registrazione della proprietà di <xref:System.Windows.DependencyProperty.RegisterAttached%2A> dipendenza (tramite il metodo), nonché le funzioni di accesso **Get_PropertyName_** e **Set_PropertyName_** . Nell'esempio, la proprietà associata è denominata `IsBubbleSource`. Pertanto, le funzioni di accesso devono essere chiamate `GetIsBubbleSource` e `SetIsBubbleSource`.

[!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
[!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]

#### <a name="attached-property-attributes"></a>Attributi delle proprietà associate

WPF definisce diversi [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] che hanno lo scopo di fornire informazioni sulle proprietà associate ai processi di reflection e agli utenti tipici delle informazioni sulla reflection e sulle proprietà, ad esempio le finestre di progettazione. Dato che le proprietà associate hanno un tipo con ambito illimitato, le finestre di progettazione devono disporre di un modo per evitare di sopraffare gli utenti con un elenco globale di tutte le proprietà associate definite in una particolare implementazione della tecnologia che usa XAML. L' [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] oggetto definito da WPF per le proprietà associate può essere utilizzato per definire l'ambito delle situazioni in cui una determinata proprietà associata deve essere visualizzata in una finestra delle proprietà. È possibile prendere in considerazione l'applicazione di questi attributi anche per le proprietà associate personalizzate. Lo scopo e la sintassi degli [!INCLUDE[TLA2#tla_netframewkattr#plural](../../../../includes/tla2sharptla-netframewkattrsharpplural-md.md)] vengono descritti nelle relative pagine di riferimento:

- <xref:System.Windows.AttachedPropertyBrowsableAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForChildrenAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableForTypeAttribute>

- <xref:System.Windows.AttachedPropertyBrowsableWhenAttributePresentAttribute>

## Ulteriori informazioni sulle proprietà associate<a name="more"></a>

- Per altre informazioni sulla creazione di una proprietà associata, vedere [Registrare una proprietà associata](how-to-register-an-attached-property.md).

- Per scenari di utilizzo più avanzati delle proprietà di dipendenza e delle proprietà associate, vedere [Proprietà di dipendenza personalizzate](custom-dependency-properties.md).

- È anche possibile registrare una proprietà come proprietà associata e proprietà di dipendenza, ma continuare a esporre le implementazioni del "wrapper". In questo caso, la proprietà può essere impostata in tale elemento o in qualsiasi elemento tramite la sintassi per le proprietà associate XAML. Un esempio di proprietà con uno scenario appropriato per gli utilizzi standard e collegati è <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.DependencyProperty>
- [Panoramica sulle proprietà di dipendenza](dependency-properties-overview.md)
- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Cenni preliminari su XAML (WPF)](xaml-overview-wpf.md)
- [Registrare una proprietà associata](how-to-register-an-attached-property.md)
