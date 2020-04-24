---
title: Panoramica sulle proprietà di dipendenza
description: Una proprietà supportata dal sistema di proprietà WPF è nota come proprietà di dipendenza. Questa panoramica descrive il sistema di proprietà WPF e le funzionalità di una proprietà di dipendenza.
ms.date: 06/06/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [WPF], attached
- properties [WPF], overview
- styles [WPF]
- attached properties [WPF]
- data binding [WPF]
- dependency properties [WPF]
- resources [WPF], references to
ms.assetid: d119d00c-3afb-48d6-87a0-c4da4f83dee5
ms.openlocfilehash: c73a61b8c251b12d5b3dac67535632322779a6af
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644061"
---
# <a name="dependency-properties-overview"></a>Panoramica sulle proprietà di dipendenza

Windows Presentation Foundation (WPF) include un set di servizi che è possibile usare per estendere la funzionalità di una [proprietà](../../../standard/base-types/common-type-system.md#properties) di un tipo. In genere, questi servizi vengono definiti collettivamente come sistema di proprietà WPF. Una proprietà supportata dal sistema di proprietà WPF è nota come proprietà di dipendenza. Questa panoramica descrive il sistema di proprietà WPF e le funzionalità di una proprietà di dipendenza. Viene anche spiegato come usare le proprietà di dipendenza esistenti in XAML e nel codice. In questa panoramica vengono anche illustrati aspetti specifici delle proprietà di dipendenza, ad esempio i metadati delle proprietà di dipendenza e la creazione di una proprietà di dipendenza in una classe personalizzata.

## <a name="prerequisites"></a>Prerequisiti
In questo argomento si presuppone che l'utente disponga di una conoscenza di base del sistema di tipi .NET e della programmazione orientata a oggetti. Per seguire gli esempi illustrati in questo argomento, è anche necessario conoscere XAML e saper scrivere applicazioni WPF. Per altre informazioni, vedere [Procedura dettagliata: La prima applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="dependency-properties-and-clr-properties"></a>Proprietà di dipendenza e proprietà CLR
 In WPF le proprietà vengono generalmente esposte come [proprietà](../../../standard/base-types/common-type-system.md#properties) .NET standard. A un livello di base, si potrebbe interagire direttamente con queste proprietà senza sapere che vengono implementate come una proprietà di dipendenza. Tuttavia, è necessario acquisire familiarità con alcune o tutte le funzionalità del sistema di proprietà WPF, in modo da poterle sfruttare.

Lo scopo delle proprietà di dipendenza consiste nel fornire un modo per calcolare il valore di una proprietà in base al valore di altri input. Questi potrebbero includere proprietà del sistema, quali temi e preferenze dell'utente, meccanismi di determinazione della proprietà JIT, ad esempio data binding dati e animazioni o storyboard, modelli multiuso, quali risorse e stili oppure valori noti tramite relazioni padre-figlio con altri elementi dell'albero degli elementi. Inoltre, una proprietà di dipendenza può essere implementata per fornire una convalida autonoma, valori predefiniti, callback per il monitoraggio delle modifiche di altre proprietà, nonché un sistema che può assegnare forzatamente valori della proprietà in base a potenziali informazioni di runtime. Le classi derivate possono anche modificare alcune caratteristiche specifiche di una proprietà esistente, eseguendo l'override dei metadati della proprietà di dipendenza invece dell'override dell'implementazione effettiva delle proprietà esistenti oppure della creazione di nuove proprietà.

Nel riferimento SDK, è possibile identificare la proprietà di dipendenza grazie alla sezione Informazioni sulle proprietà di dipendenza, presente nella pagina di riferimento gestita per quella proprietà. Nella sezione sono inclusi un collegamento al campo dell'identificatore <xref:System.Windows.DependencyProperty> per quella proprietà di dipendenza e un elenco delle opzioni dei metadati impostati per quella proprietà, informazioni sull'override per classe e altri dettagli.

## <a name="dependency-properties-back-clr-properties"></a>Proprietà di dipendenza che supportano le proprietà CLR
Le proprietà di dipendenza e il sistema di proprietà WPF estendono le funzionalità della proprietà fornendo un tipo che supporta una proprietà, come implementazione alternativa al modello standard di supporto della proprietà con un campo privato. Il nome del tipo è <xref:System.Windows.DependencyProperty>. L'altro tipo importante che definisce il sistema di proprietà WPF è <xref:System.Windows.DependencyObject>. <xref:System.Windows.DependencyObject> definisce la classe di base che può essere registrata ed essere proprietaria di una proprietà di dipendenza.

Di seguito è elencata la terminologia usata con le proprietà di dipendenza:

- **Proprietà di dipendenza:** proprietà supportata da un oggetto <xref:System.Windows.DependencyProperty>.

- **Identificatore della proprietà di dipendenza:** istanza di <xref:System.Windows.DependencyProperty>, ottenuta come valore restituito quando si registra una proprietà di dipendenza e quindi archiviata come membro statico di una classe. Questo identificatore viene usato come parametro per molte API che interagiscono con il sistema di proprietà WPF.

- **"Wrapper" CLR:** le implementazioni effetti Get e Set per la proprietà. Queste implementazioni includono l'identificatore della proprietà di dipendenza usandolo nelle chiamate <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A>, in modo da fornire il supporto per la proprietà tramite il sistema di proprietà WPF.

L'esempio seguente definisce la proprietà di dipendenza `IsSpinning` e mostra la relazione tra l'identificatore <xref:System.Windows.DependencyProperty> e la proprietà supportata.

[!code-csharp[PropertiesOvwSupport#DPFormBasic](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
[!code-vb[PropertiesOvwSupport#DPFormBasic](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
  
La convenzione di denominazione della proprietà e del relativo campo <xref:System.Windows.DependencyProperty> di supporto è importante. Il nome del campo è sempre il nome della proprietà al quale viene aggiunto il suffisso `Property`. Per altre informazioni su questa convenzione e i relativi motivi, vedere [Proprietà di dipendenza personalizzate](custom-dependency-properties.md).  

## <a name="setting-property-values"></a>Impostazione dei valori delle proprietà
È possibile impostare le proprietà nel codice o in XAML.

### <a name="setting-property-values-in-xaml"></a>Impostazione dei valori delle proprietà in XAML
L'esempio di XAML seguente specifica il colore di sfondo rosso per un pulsante. Questo esempio illustra un caso in cui il valore di stringa semplice per un attributo XAML viene convertito dal parser XAML WPF in un tipo WPF (<xref:System.Windows.Media.Color> tramite <xref:System.Windows.Media.SolidColorBrush>) nel codice generato.

[!code-xaml[PropertiesOvwSupport#MostBasicProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]

XAML supporta diverse sintassi per l'impostazione delle proprietà. La sintassi da usare per una proprietà particolare dipende dal tipo di valore usato da una proprietà e da altri fattori, quali la presenza di un convertitore dei tipi. Per altre informazioni sulla sintassi XAML per l'impostazione di proprietà, vedere [Cenni preliminari su XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md) e [Descrizione dettagliata della sintassi XAML](xaml-syntax-in-detail.md).

Come esempio di sintassi senza attributi, nell'esempio di XAML seguente viene illustrato lo sfondo di un altro pulsante. Questa volta, invece di impostare un semplice colore a tinta unita, lo sfondo viene impostato su un'immagine, con un elemento che rappresenta tale immagine e la relativa origine, specificate come un attributo dell'elemento annidato. Si tratta di un esempio di sintassi per gli elementi proprietà.

[!code-xaml[PropertiesOvwSupport#PESyntaxProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]

### <a name="setting-properties-in-code"></a>Impostazione delle proprietà nel codice
 L'impostazione dei valori delle proprietà di dipendenza nel codice è in genere solo una chiamata all'implementazione dell'insieme esposta dal "wrapper" CLR.

[!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
[!code-vb[PropertiesOvwSupport#ProceduralPropertySet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]

Anche il recupero di un valore della proprietà prevede sostanzialmente una chiamata all'implementazione del "wrapper" Get:

[!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]

È anche possibile chiamare direttamente <xref:System.Windows.DependencyObject.GetValue%2A> le <xref:System.Windows.DependencyObject.SetValue%2A> API del sistema di proprietà. Ciò non è in genere necessario se si utilizzano proprietà esistenti (i wrapper sono più convenienti e forniscono una migliore esposizione della proprietà per gli strumenti di sviluppo), ma la chiamata diretta delle API è appropriata per determinati scenari.

È anche possibile impostare le proprietà in XAML e successivamente accedervi nel codice tramite code-behind. Per informazioni dettagliate, vedere [Code-behind e XAML in WPF](code-behind-and-xaml-in-wpf.md).

## <a name="property-functionality-provided-by-a-dependency-property"></a>Funzionalità offerte da una proprietà di dipendenza
Una proprietà di dipendenza fornisce funzionalità che consentono di estendere la funzionalità di una proprietà, rispetto a una proprietà supportata da un campo. Spesso tale funzionalità rappresenta o supporta una delle funzionalità specifiche seguenti:

- [Risorse](#resources)

- [Associazione dati](#data-binding)

- [Stili](#styles)

- [Animations](#animations)

- [Override dei metadati](#metadata-overrides)

- [Ereditarietà del valore della proprietà](#property-value-inheritance)

- [Integrazione di WPF DesignerWPF Designer integration](#wpf-designer-integration)

### <a name="resources"></a>Risorse
Un valore della proprietà di dipendenza può essere impostato facendo riferimento a una risorsa. Le risorse vengono in genere specificate come valore della proprietà `Resources` di un elemento radice della pagina o dell'applicazione (questi percorsi consentono un accesso più semplice alla risorsa). L'esempio seguente illustra come definire una risorsa <xref:System.Windows.Media.SolidColorBrush>.

[!code-xaml[PropertiesOvwSupport#ResourcesResource](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]

Una volta definita, è possibile fare riferimento alla risorsa e usarla per fornire un valore della proprietà:

[!code-xaml[PropertiesOvwSupport#ResourcesReference](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]

A questa risorsa particolare viene fatto riferimento come [estensione del markup DynamicResource](dynamicresource-markup-extension.md). In XAML WPF è possibile usare un riferimento di risorsa statica o dinamica. Per usare un riferimento di risorsa dinamica, è necessario eseguire l'impostazione su una proprietà di dipendenza, in modo che il sistema di proprietà WPF attivi l'utilizzo specifico del riferimento di risorsa dinamica. Per altre informazioni, vedere [Risorse XAML](xaml-resources.md).

> [!NOTE]
> Le risorse vengono considerate come valore locale, per cui se si imposta un altro valore locale, il riferimento di risorsa sarà eliminato. Per altre informazioni, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).

### <a name="data-binding"></a>Associazione dati
Una proprietà di dipendenza può fare riferimento a un valore tramite il data binding, che funziona tramite una sintassi per estensione di markup specifica in XAML o l'oggetto <xref:System.Windows.Data.Binding> nel codice. Con il data binding, la determinazione del valore della proprietà finale viene rinviata fino alla fase di esecuzione, momento in cui il valore viene ottenuto da un'origine dati.

L'esempio seguente imposta la proprietà <xref:System.Windows.Controls.ContentControl.Content%2A> per un oggetto <xref:System.Windows.Controls.Button> tramite un'associazione dichiarata in XAML. L'associazione usa un contesto dei dati ereditato e un'origine dati <xref:System.Windows.Data.XmlDataProvider> (non illustrata). L'associazione stessa specifica la proprietà di origine desiderata mediante l'oggetto <xref:System.Windows.Data.Binding.XPath%2A> all'interno dell'origine dati.

[!code-xaml[PropertiesOvwSupport#BasicInlineBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]

> [!NOTE]
> I binding vengono considerati come valore locale, per cui se si imposta un altro valore locale, il binding verrà eliminato. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).

Le proprietà di dipendenza, o la classe <xref:System.Windows.DependencyObject>, non supportano <xref:System.ComponentModel.INotifyPropertyChanged> in modo nativo per la generazione di notifiche delle modifiche nel valore della proprietà di origine <xref:System.Windows.DependencyObject> per le operazioni di associazione di dati. Per altre informazioni su come creare proprietà da usare nel data binding, che consentano di segnalare modifiche di una destinazione di data binding, vedere [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md).

### <a name="styles"></a>Stili
Stili e modelli sono due degli scenari principali che giustificano l'uso delle proprietà di dipendenza. Gli stili sono particolarmente utili per l'impostazione di proprietà che definiscono l'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dell'applicazione. In genere gli stili vengono definiti come risorse in XAML e interagiscono con il sistema di proprietà in quanto di solito contengono "setter" per proprietà particolari, nonché "trigger" che modificano un valore della proprietà in base al valore in tempo reale per un'altra proprietà.

Nell'esempio seguente viene creato uno stile <xref:System.Windows.FrameworkElement.Resources%2A> semplice (che verrebbe definito all'interno di un dizionario, non illustrato), quindi tale stile viene applicato direttamente alla <xref:System.Windows.FrameworkElement.Style%2A> proprietà per un <xref:System.Windows.Controls.Button>oggetto . Il setter all'interno dello stile imposta la proprietà <xref:System.Windows.Controls.Control.Background%2A> di un oggetto <xref:System.Windows.Controls.Button> con stile su verde.

[!code-xaml[PropertiesOvwSupport#SimpleStyleDef](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]

[!code-xaml[PropertiesOvwSupport#SimpleStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]

Per altre informazioni, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

### <a name="animations"></a>Animations
Alle proprietà di dipendenza è possibile aggiungere un'animazione. Quando un'animazione viene applicata ed è in esecuzione, il valore a cui è stata aggiunta un'animazione opera a un livello di precedenza superiore rispetto a qualsiasi altro valore (ad esempio un valore locale) della proprietà.

L'esempio seguente aggiunge un'animazione alla proprietà <xref:System.Windows.Controls.Control.Background%2A> di un oggetto <xref:System.Windows.Controls.Button>. Tecnicamente, l'animazione viene aggiunta alla proprietà <xref:System.Windows.Controls.Control.Background%2A> tramite la sintassi degli elementi proprietà per specificare un <xref:System.Windows.Media.SolidColorBrush> vuoto come <xref:System.Windows.Controls.Control.Background%2A> e quindi la proprietà <xref:System.Windows.Media.SolidColorBrush.Color%2A> dell'oggetto <xref:System.Windows.Media.SolidColorBrush> è la proprietà a cui viene direttamente applicata l'animazione.

[!code-xaml[PropertiesOvwSupport#MiniAnimate](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]

Per altre informazioni sull'animazione di proprietà, vedere [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md) e [Cenni preliminari sugli storyboard](../graphics-multimedia/storyboards-overview.md).

### <a name="metadata-overrides"></a>Override dei metadati
È possibile modificare determinati comportamenti di una proprietà di dipendenza eseguendo l'override dei metadati per quella proprietà, quando si deriva dalla classe che registra originariamente la proprietà di dipendenza. L'override dei metadati si basa sull'identificatore <xref:System.Windows.DependencyProperty>. L'override dei metadati non richiede la reimplementazione della proprietà. La modifica dei metadati viene gestita in modo nativo dal sistema di proprietà. Ogni classe contiene, potenzialmente, i metadati specifici per tutte le proprietà ereditate dalle classi di base, in base al tipo.

L'esempio seguente esegue l'override dei metadati per una proprietà di dipendenza <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>. L'override dei metadati di questa particolare proprietà di dipendenza fa parte di un modello di implementazione che consente di creare controlli che possono usare stili predefiniti dai temi.

[!code-csharp[PropertiesOvwSupport#OverrideMetadata](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
[!code-vb[PropertiesOvwSupport#OverrideMetadata](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]

Per altre informazioni sull'override dei metadati delle proprietà o su come ottenere i metadati delle proprietà, vedere [Metadati delle proprietà di dipendenza](dependency-property-metadata.md).

### <a name="property-value-inheritance"></a>Ereditarietà del valore della proprietà
Un elemento può ereditare il valore di una proprietà di dipendenza dal relativo elemento padre nell'albero di oggetti.

> [!NOTE]
> Il comportamento dell'ereditarietà del valore della proprietà non viene abilitato a livello globale per tutte le proprietà di dipendenza, poiché il tempo di calcolo per l'ereditarietà influisce negativamente sulle prestazioni. In genere, l'ereditarietà del valore della proprietà viene abilitata solo per le proprietà in cui uno scenario particolare suggerisce che tale ereditarietà è appropriata. La possibilità di ereditare di una proprietà di dipendenza può essere determinata consultando la sezione **Informazioni proprietà di dipendenza** per una determinata proprietà di dipendenza, nel riferimento SDK.

L'esempio seguente descrive un'associazione e imposta la proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> che specifica l'origine dell'associazione, non illustrata nell'esempio di associazione precedente. Eventuali associazioni successive in oggetti figlio non devono necessariamente specificare l'origine, ma possono usare il valore ereditato da <xref:System.Windows.FrameworkElement.DataContext%2A> nell'oggetto <xref:System.Windows.Controls.StackPanel> padre. In alternativa, un oggetto figlio può invece scegliere di specificare direttamente il proprio <xref:System.Windows.FrameworkElement.DataContext%2A> o un <xref:System.Windows.Data.Binding.Source%2A> in <xref:System.Windows.Data.Binding> e non usare deliberatamente il valore ereditato per il contesto dei dati delle sue associazioni.

[!code-xaml[PropertiesOvwSupport#InheritanceContext](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]

Per altre informazioni, vedere [Ereditarietà del valore della proprietà](property-value-inheritance.md).

### <a name="wpf-designer-integration"></a>Integrazione di WPF Designer
Un controllo personalizzato con proprietà implementate come proprietà di dipendenza riceverà WPF Designer appropriato per il supporto di Visual Studio.A custom control with properties that are implemented as dependency properties will receive appropriate WPF Designer for Visual Studio support. Un esempio è rappresentato dalla capacità di modificare proprietà di dipendenza dirette e associate tramite la finestra **Proprietà**. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../controls/control-authoring-overview.md).

## <a name="dependency-property-value-precedence"></a>Precedenza del valore della proprietà di dipendenza
Quando si ottiene il valore di una proprietà di dipendenza, si ottiene potenzialmente un valore impostato per tale proprietà tramite uno qualsiasi degli altri input basati su proprietà che fanno parte del sistema di proprietà WPF. La precedenza del valore della proprietà di dipendenza consente interazioni prevedibili per un'ampia gamma di scenari relativi al modo in cui le proprietà ottengono i rispettivi valori.

Si consideri l'esempio seguente. L'esempio include uno stile che si applica a tutti i pulsanti e alle loro proprietà <xref:System.Windows.Controls.Control.Background%2A>, ma specifica anche un pulsante con un valore <xref:System.Windows.Controls.Control.Background%2A> impostato localmente.

> [!NOTE]
> Nella documentazione SDK i termini "valore locale" o "valore impostato localmente" vengono usati talvolta per la descrizione delle proprietà di dipendenza. Un valore impostato localmente è un valore di proprietà che viene impostato direttamente in un'istanza di oggetto nel codice o come attributo di un elemento in XAML.  
  
In teoria, per il primo pulsante la proprietà viene impostata due volte, ma viene applicato un solo valore, quello con la precedenza più alta. Un valore impostato localmente ha la massima precedenza (eccetto per un'animazione in esecuzione; tuttavia, in questo esempio non viene applicata nessuna animazione), pertanto per lo sfondo del primo pulsante viene usato il valore impostato localmente invece del valore del setter di stile. Il secondo pulsante non ha un valore locale (e nessun altro valore con precedenza più alta rispetto a un setter di stile), pertanto lo sfondo di quel pulsante proviene dal setter di stile.

[!code-xaml[PropertiesOvwSupport#MiniPrecedence](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  

### <a name="why-does-dependency-property-precedence-exist"></a>Motivi dell'esistenza della precedenza delle proprietà di dipendenza
In genere, non si desidera che gli stili vengano sempre applicati e che si oscuri anche un valore impostato localmente di un singolo elemento (altrimenti sarebbe difficile usare stili o elementi in generale). Per questo motivo, i valori che provengono dagli stili operano a un livello di precedenza inferiore rispetto a un valore impostato localmente. Per un elenco più completo delle proprietà di dipendenza e informazioni sulla possibile provenienza di un valore effettivo di una proprietà di dipendenza, vedere [Precedenza del valore della proprietà di dipendenza](dependency-property-value-precedence.md).

> [!NOTE]
> Molte proprietà definite negli elementi WPF non sono proprietà di dipendenza. In generale, le proprietà vengono implementate come proprietà di dipendenza solo quando è necessario supportare almeno uno degli scenari abilitati dal sistema di proprietà: data binding, applicazione degli stili, animazione, supporto del valore predefinito, ereditarietà, proprietà associate o invalidamento.

## <a name="learning-more-about-dependency-properties"></a>Altre informazioni sulle proprietà di dipendenza  

- Una proprietà associata è un tipo di proprietà che supporta una sintassi specializzata in XAML. Una proprietà associata spesso non ha una corrispondenza 1:1 con una proprietà CLR (Common Language Runtime) e non è necessariamente una proprietà di dipendenza. Lo scopo tipico di una proprietà associata è consentire agli elementi figlio di segnalare i valori delle proprietà a un elemento padre, anche se l'elemento padre e l'elemento figlio non possiedono entrambi tale proprietà come parte degli elenchi dei membri della classe. Uno scenario principale è l'abilitazione di elementi figlio per informare l'elemento padre di come devono essere presentati in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Per un esempio, vedere <xref:System.Windows.Controls.DockPanel.Dock%2A> o <xref:System.Windows.Controls.Canvas.Left%2A>. Per informazioni dettagliate, vedere [Cenni preliminari sulle proprietà associate](attached-properties-overview.md).

- Gli sviluppatori di componenti o di applicazioni possono decidere di creare una proprietà di dipendenza personalizzata al fine di abilitare funzionalità quali il data binding o il supporto degli stili oppure per il supporto dell'invalidamento e della coercizione del valore. Per informazioni dettagliate, vedere [Proprietà di dipendenza personalizzate](custom-dependency-properties.md).

- Considerare le proprietà di dipendenza come proprietà pubbliche, accessibili o almeno individuabili da qualsiasi chiamante che ha accesso a un'istanza. Per altre informazioni, vedere [Sicurezza delle proprietà di dipendenza](dependency-property-security.md).

## <a name="see-also"></a>Vedere anche

- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
- [Proprietà di dipendenza di sola lettura](read-only-dependency-properties.md)
- [Panoramica di XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Architettura WPF](wpf-architecture.md)
