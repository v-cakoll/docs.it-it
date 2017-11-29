---
title: "Cenni preliminari sulle proprietà di dipendenza"
description: "Una proprietà supportata dal sistema di proprietà WPF è noto come proprietà di dipendenza. Questa panoramica descrive il sistema di proprietà WPF e le funzionalità di una proprietà di dipendenza."
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-wpf
ms.topic: article
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
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aa1ad02de74cc73ea67267de7548442078a2f5db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="dependency-properties-overview"></a>Cenni preliminari sulle proprietà di dipendenza

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] include un set di servizi che è possibile usare per estendere la funzionalità di una proprietà [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]. In genere, questi servizi vengono definiti collettivamente come sistema di proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Una proprietà supportata dal sistema di proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] è nota come proprietà di dipendenza. Questa panoramica descrive il sistema di proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e le funzionalità di una proprietà di dipendenza. Viene anche spiegato come usare le proprietà di dipendenza esistenti in XAML e nel codice. In questa panoramica vengono anche illustrati aspetti specifici delle proprietà di dipendenza, ad esempio i metadati delle proprietà di dipendenza e la creazione di una proprietà di dipendenza in una classe personalizzata.

## <a name="prerequisites"></a>Prerequisiti
In questo argomento si presuppone che l'utente disponga di una conoscenza di base di [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] e della programmazione orientata a oggetti. Per seguire gli esempi illustrati in questo argomento, è anche necessario conoscere [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e saper scrivere applicazioni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per ulteriori informazioni, vedere [procedura dettagliata: applicazione desktop WPF prima](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
## <a name="dependency-properties-and-clr-properties"></a>Proprietà di dipendenza e le proprietà CLR
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le proprietà vengono generalmente esposte come proprietà [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]. A un livello di base, si potrebbe interagire direttamente con queste proprietà senza sapere che vengono implementate come una proprietà di dipendenza. Tuttavia, è necessario acquisire familiarità con alcune o tutte le funzionalità del sistema di proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], in modo da poterle sfruttare.

Lo scopo delle proprietà di dipendenza consiste nel fornire un modo per calcolare il valore di una proprietà in base al valore di altri input. Questi potrebbero includere proprietà del sistema, quali temi e preferenze dell'utente, meccanismi di determinazione della proprietà JIT, ad esempio data binding dati e animazioni o storyboard, modelli multiuso, quali risorse e stili oppure valori noti tramite relazioni padre-figlio con altri elementi dell'albero degli elementi. Inoltre, una proprietà di dipendenza può essere implementata per fornire una convalida autonoma, valori predefiniti, callback per il monitoraggio delle modifiche di altre proprietà, nonché un sistema che può assegnare forzatamente valori della proprietà in base a potenziali informazioni di runtime. Le classi derivate possono anche modificare alcune caratteristiche specifiche di una proprietà esistente, eseguendo l'override dei metadati della proprietà di dipendenza invece dell'override dell'implementazione effettiva delle proprietà esistenti oppure della creazione di nuove proprietà.

Nel riferimento SDK, è possibile identificare la proprietà di dipendenza grazie alla sezione Informazioni sulle proprietà di dipendenza, presente nella pagina di riferimento gestita per quella proprietà. La sezione informazioni sulle proprietà di dipendenza include un collegamento per il <xref:System.Windows.DependencyProperty> identificatore di campo per la proprietà di dipendenza e include anche un elenco di opzioni dei metadati impostati per tale proprietà, informazioni sull'override di classi e altri dettagli.

## <a name="dependency-properties-back-clr-properties"></a>Le proprietà di dipendenza supportano le proprietà CLR
Le proprietà di dipendenza e il sistema di proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] estendono le funzionalità della proprietà fornendo un tipo che supporta una proprietà, come implementazione alternativa al modello standard di supporto della proprietà con un campo privato. Il nome di questo tipo è <xref:System.Windows.DependencyProperty>. L'altro tipo importante che definisce il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di proprietà <xref:System.Windows.DependencyObject>. <xref:System.Windows.DependencyObject>definisce la classe di base che consente di registrare e proprietari di una proprietà di dipendenza.

Di seguito viene riportato un riepilogo della terminologia usata in questa documentazione [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)] per la descrizione delle proprietà di dipendenza:

- **Proprietà di dipendenza:** una proprietà che è supportata da un <xref:System.Windows.DependencyProperty>.

- **Identificatore della proprietà di dipendenza:** A <xref:System.Windows.DependencyProperty> istanza, che viene ottenuto come valore restituito quando si registra una proprietà di dipendenza e quindi archiviato come un membro statico di una classe. Questo identificatore viene usato come parametro per molte [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] che interagiscono con il sistema di proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

- **"Wrapper" CLR:** le implementazioni effetti Get e Set per la proprietà. Queste implementazioni incorporano l'identificatore della proprietà di dipendenza utilizzando nel <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> chiamate, in modo da fornire il supporto per la proprietà utilizzando il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema di proprietà.

L'esempio seguente definisce il `IsSpinning` proprietà di dipendenza e Mostra la relazione tra il <xref:System.Windows.DependencyProperty> identificatore della proprietà per il ripristino.

[!code-csharp[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#dpformbasic)]
[!code-vb[PropertiesOvwSupport#DPFormBasic](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#dpformbasic)]  
  
La convenzione di denominazione della proprietà e il relativo backup <xref:System.Windows.DependencyProperty> campo è importante. Il nome del campo è sempre il nome della proprietà al quale viene aggiunto il suffisso `Property`. Per altre informazioni su questa convenzione e i relativi motivi, vedere [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).  

## <a name="setting-property-values"></a>Impostazione dei valori di proprietà
È possibile impostare le proprietà nel codice o in XAML.

### <a name="setting-property-values-in-xaml"></a>Impostazione dei valori di proprietà in XAML 
L'esempio di XAML seguente specifica il colore di sfondo rosso per un pulsante. Questo esempio viene illustrato un caso in cui il valore di stringa semplice per un attributo XAML è di tipo convertito dal parser XAML di WPF in un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tipo (un <xref:System.Windows.Media.Color>, per mezzo di un <xref:System.Windows.Media.SolidColorBrush>) nel codice generato.

[!code-xaml[PropertiesOvwSupport#MostBasicProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#mostbasicproperty)]

XAML supporta diverse sintassi per l'impostazione delle proprietà. La sintassi da usare per una proprietà particolare dipende dal tipo di valore usato da una proprietà e da altri fattori, quali la presenza di un convertitore dei tipi. Per altre informazioni sulla sintassi XAML per l'impostazione di proprietà, vedere [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) e [Descrizione dettagliata della sintassi XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).

Come esempio di sintassi senza attributi, nell'esempio di XAML seguente viene illustrato lo sfondo di un altro pulsante. Questa volta, invece di impostare un semplice colore a tinta unita, lo sfondo viene impostato su un'immagine, con un elemento che rappresenta tale immagine e la relativa origine, specificate come un attributo dell'elemento annidato. Si tratta di un esempio di sintassi per gli elementi proprietà.

[!code-xaml[PropertiesOvwSupport#PESyntaxProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml#pesyntaxproperty)]

### <a name="setting-properties-in-code"></a>Impostazione delle proprietà nel codice
 L'impostazione dei valori della proprietà di dipendenza nel codice consiste, in genere, solo in una chiamata all'implementazione Set esposta dal "wrapper" [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].

[!code-csharp[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyset)]
[!code-vb[PropertiesOvwSupport#ProceduralPropertySet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyset)]

Anche il recupero di un valore della proprietà prevede sostanzialmente una chiamata all'implementazione del "wrapper" Get:

[!code-csharp[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/Page1.xaml.cs#proceduralpropertyget)]
 [!code-vb[PropertiesOvwSupport#ProceduralPropertyGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page1.xaml.vb#proceduralpropertyget)]

È inoltre possibile chiamare il sistema di proprietà [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] <xref:System.Windows.DependencyObject.GetValue%2A> e <xref:System.Windows.DependencyObject.SetValue%2A> direttamente. In genere, questa operazione non è necessaria se si usano proprietà esistenti (i wrapper sono più utili e forniscono una migliore esposizione della proprietà per gli strumenti dello sviluppatore), ma la chiamata diretta delle [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] risulta appropriata per determinati scenari.

È anche possibile impostare le proprietà in XAML e successivamente accedervi nel codice tramite code-behind. Per informazioni dettagliate, vedere [Code-behind e XAML in WPF](../../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md).

## <a name="property-functionality-provided-by-a-dependency-property"></a>Funzionalità di proprietà fornita da una proprietà di dipendenza
Una proprietà di dipendenza fornisce funzionalità che consentono di estendere la funzionalità di una proprietà, rispetto a una proprietà supportata da un campo. Spesso, ciascuna di queste funzionalità rappresenta o supporta una funzionalità specifica dell'intero set di funzionalità [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

- [Risorse](#resources)

- [Data binding](#data-binding)

- [Stili](#styles)

- [Animazioni](#animations)

- [Override dei metadati](#metadata-overrides)

- [Ereditarietà del valore della proprietà](#property-value-inheritance)

- [Integrazione di WPF Designer](#wpf-designer-integration)

### <a name="resources"></a>Risorse
Un valore della proprietà di dipendenza può essere impostato facendo riferimento a una risorsa. Le risorse vengono in genere specificate come valore della proprietà `Resources` di un elemento radice della pagina o dell'applicazione (questi percorsi consentono un accesso più semplice alla risorsa). Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.Media.SolidColorBrush> risorse.

[!code-xaml[PropertiesOvwSupport#ResourcesResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesresource)]

Una volta definita, è possibile fare riferimento alla risorsa e usarla per fornire un valore della proprietà:

[!code-xaml[PropertiesOvwSupport#ResourcesReference](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page2.xaml#resourcesreference)]

A questa risorsa particolare viene fatto riferimento come [estensione del markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md). In XAML WPF è possibile usare un riferimento di risorsa statica o dinamica. Per usare un riferimento di risorsa dinamica, è necessario eseguire l'impostazione su una proprietà di dipendenza, in modo che il sistema di proprietà [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] attivi l'utilizzo specifico del riferimento di risorsa dinamica. Per altre informazioni, vedere [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).

> [!NOTE]
> Le risorse vengono considerate come valore locale, per cui se si imposta un altro valore locale, il riferimento di risorsa sarà eliminato. Per altre informazioni, vedere [Precedenza del valore della proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

### <a name="data-binding"></a>Associazione dati
Una proprietà di dipendenza può fare riferimento a un valore tramite il data binding, Associazione dati funziona tramite una sintassi dell'estensione di markup specifico in XAML o <xref:System.Windows.Data.Binding> oggetto nel codice. Con il data binding, la determinazione del valore della proprietà finale viene rinviata fino alla fase di esecuzione, momento in cui il valore viene ottenuto da un'origine dati.

L'esempio seguente imposta il <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà per un <xref:System.Windows.Controls.Button>, utilizzando un'associazione dichiarato in XAML. L'associazione utilizza un contesto dati ereditato e un <xref:System.Windows.Data.XmlDataProvider> origine dati (non illustrata). L'associazione stessa specifica la proprietà di origine desiderato da <xref:System.Windows.Data.Binding.XPath%2A> all'interno dell'origine dati.

[!code-xaml[PropertiesOvwSupport#BasicInlineBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#basicinlinebinding)]

> [!NOTE]
> I binding vengono considerati come valore locale, per cui se si imposta un altro valore locale, il binding verrà eliminato. Per altri dettagli, vedere [Precedenza del valore della proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

Proprietà di dipendenza, o <xref:System.Windows.DependencyObject> classe, in modo nativo non supportano <xref:System.ComponentModel.INotifyPropertyChanged> per la produzione delle notifiche di modifiche in <xref:System.Windows.DependencyObject> valore della proprietà per le operazioni di associazione di dati di origine. Per altre informazioni su come creare proprietà da usare nel data binding, che consentano di segnalare modifiche di una destinazione di data binding, vedere [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md).

### <a name="styles"></a>Stili
Stili e modelli sono due degli scenari principali che giustificano l'uso delle proprietà di dipendenza. Gli stili sono particolarmente utili per l'impostazione di proprietà che definiscono l'[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] dell'applicazione. In genere gli stili vengono definiti come risorse in XAML e interagiscono con il sistema di proprietà in quanto di solito contengono "setter" per proprietà particolari, nonché "trigger" che modificano un valore della proprietà in base al valore in tempo reale per un'altra proprietà.

Nell'esempio seguente viene creato uno stile molto semplice (definito all'interno di un <xref:System.Windows.FrameworkElement.Resources%2A> dizionario, non visualizzato), che successivamente applicato direttamente il <xref:System.Windows.FrameworkElement.Style%2A> proprietà per un <xref:System.Windows.Controls.Button>. Il setter nello stile imposta il <xref:System.Windows.Controls.Control.Background%2A> proprietà per un stile <xref:System.Windows.Controls.Button> verde.

[!code-xaml[PropertiesOvwSupport#SimpleStyleDef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyledef)]

[!code-xaml[PropertiesOvwSupport#SimpleStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#simplestyle)]

Per altre informazioni, vedere [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).

### <a name="animations"></a>Animations
Alle proprietà di dipendenza è possibile aggiungere un'animazione. Quando un'animazione viene applicata ed è in esecuzione, il valore a cui è stata aggiunta un'animazione opera a un livello di precedenza superiore rispetto a qualsiasi altro valore (ad esempio un valore locale) della proprietà.

Nell'esempio seguente aggiunge un'animazione il <xref:System.Windows.Controls.Control.Background%2A> su un <xref:System.Windows.Controls.Button> proprietà (tecnicamente, la <xref:System.Windows.Controls.Control.Background%2A> viene animata utilizzando la sintassi degli elementi di proprietà per specificare un valore vuoto <xref:System.Windows.Media.SolidColorBrush> come il <xref:System.Windows.Controls.Control.Background%2A>, il <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà dell'oggetto <xref:System.Windows.Media.SolidColorBrush> è la proprietà che viene animata direttamente).

[!code-xaml[PropertiesOvwSupport#MiniAnimate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#minianimate)]

Per altre informazioni sull'animazione di proprietà, vedere [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) e [Cenni preliminari sugli storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).

### <a name="metadata-overrides"></a>Esegue l'override dei metadati
È possibile modificare determinati comportamenti di una proprietà di dipendenza eseguendo l'override dei metadati per quella proprietà, quando si deriva dalla classe che registra originariamente la proprietà di dipendenza. L'override dei metadati si basa sul <xref:System.Windows.DependencyProperty> identificatore. L'override dei metadati non richiede una nuova implementazione della proprietà. La modifica dei metadati viene gestita in modo nativo dal sistema di proprietà. Ogni classe contiene, potenzialmente, i metadati specifici per tutte le proprietà ereditate dalle classi di base, in base al tipo.

Nell'esempio seguente viene eseguito l'override dei metadati per una proprietà di dipendenza <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A>. L'override dei metadati di questa particolare proprietà di dipendenza fa parte di un modello di implementazione che consente di creare controlli che possono usare stili predefiniti dai temi.

[!code-csharp[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#overridemetadata)]
[!code-vb[PropertiesOvwSupport#OverrideMetadata](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#overridemetadata)]

Per altre informazioni sull'override dei metadati delle proprietà o su come ottenere i metadati delle proprietà, vedere [Metadati delle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).

### <a name="property-value-inheritance"></a>Ereditarietà del valore proprietà
Un elemento può ereditare il valore di una proprietà di dipendenza dal relativo elemento padre nell'albero di oggetti.

> [!NOTE]
> Il comportamento dell'ereditarietà del valore della proprietà non viene abilitato a livello globale per tutte le proprietà di dipendenza, poiché il tempo di calcolo per l'ereditarietà influisce negativamente sulle prestazioni. In genere, l'ereditarietà del valore della proprietà viene abilitata solo per le proprietà in cui uno scenario particolare suggerisce che tale ereditarietà è appropriata. La possibilità di ereditare di una proprietà di dipendenza può essere determinata consultando la sezione **Informazioni proprietà di dipendenza** per una determinata proprietà di dipendenza, nel riferimento SDK.

Nell'esempio seguente viene mostrata un'associazione e imposta il <xref:System.Windows.FrameworkElement.DataContext%2A> proprietà che specifica l'origine dell'associazione, che non è stato illustrato nell'esempio di associazione precedenti. Qualsiasi associazione successiva negli oggetti figlio non è necessario specificare l'origine, possono usare il valore ereditato da <xref:System.Windows.FrameworkElement.DataContext%2A> nell'elemento padre <xref:System.Windows.Controls.StackPanel> oggetto. (In alternativa, un oggetto figlio invece possibile scegliere di specificare direttamente il proprio <xref:System.Windows.FrameworkElement.DataContext%2A> o <xref:System.Windows.Data.Binding.Source%2A> nel <xref:System.Windows.Data.Binding>e non utilizzare il valore ereditato per il contesto di dati delle associazioni.)

[!code-xaml[PropertiesOvwSupport#InheritanceContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#inheritancecontext)]

Per altre informazioni, vedere [Ereditarietà del valore della proprietà](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).

### <a name="wpf-designer-integration"></a>Integrazione di progettazione WPF
Un controllo personalizzato con proprietà implementate come proprietà di dipendenza riceverà un supporto appropriato di [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]. Un esempio è rappresentato dalla capacità di modificare proprietà di dipendenza dirette e associate tramite la finestra **Proprietà**. Per altre informazioni, vedere [Cenni preliminari sulla modifica di controlli](../../../../docs/framework/wpf/controls/control-authoring-overview.md).

## <a name="dependency-property-value-precedence"></a>Precedenza dei valori di proprietà di dipendenza
Quando si ottiene il valore di una proprietà di dipendenza, si ottiene potenzialmente un valore impostato per tale proprietà tramite uno qualsiasi degli altri input basati sulla proprietà che partecipano al sistema di proprietà di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. La precedenza del valore della proprietà di dipendenza consente interazioni prevedibili per un'ampia gamma di scenari relativi al modo in cui le proprietà ottengono i rispettivi valori.

Si osservi l'esempio riportato di seguito. L'esempio include uno stile che si applica a tutti i pulsanti e le relative <xref:System.Windows.Controls.Control.Background%2A> proprietà, ma anche specifica di un pulsante con impostato localmente <xref:System.Windows.Controls.Control.Background%2A> valore.

> [!NOTE]
> Nella documentazione SDK i termini "valore locale" o "valore impostato localmente" vengono usati talvolta per la descrizione delle proprietà di dipendenza. Un valore impostato localmente è un valore di proprietà che viene impostato direttamente in un'istanza di oggetto nel codice o come attributo di un elemento in XAML.  
  
In teoria, per il primo pulsante la proprietà viene impostata due volte, ma viene applicato un solo valore, quello con la precedenza più alta. Un valore impostato localmente ha la massima precedenza (eccetto per un'animazione in esecuzione; tuttavia, in questo esempio non viene applicata nessuna animazione), pertanto per lo sfondo del primo pulsante viene usato il valore impostato localmente invece del valore del setter di stile. Il secondo pulsante non ha un valore locale (e nessun altro valore con precedenza più alta rispetto a un setter di stile), pertanto lo sfondo di quel pulsante proviene dal setter di stile.

[!code-xaml[PropertiesOvwSupport#MiniPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml#miniprecedence)]  

### <a name="why-does-dependency-property-precedence-exist"></a>Motivo per cui esiste la precedenza di proprietà di dipendenza
In genere, non si vuole che gli stili vengano sempre applicati e che nascondano persino un valore impostato localmente di un singolo elemento, altrimenti sarebbe molto difficile usare gli stili o gli elementi in generale. Per questo motivo, i valori che provengono dagli stili operano a un livello di precedenza inferiore rispetto a un valore impostato localmente. Per un elenco più completo delle proprietà di dipendenza e informazioni sulla possibile provenienza di un valore effettivo di una proprietà di dipendenza, vedere [Precedenza del valore della proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md).

> [!NOTE]
> Molte proprietà definite negli elementi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non sono proprietà di dipendenza. In generale, le proprietà vengono implementate come proprietà di dipendenza solo quando è necessario supportare almeno uno degli scenari abilitati dal sistema di proprietà: data binding, applicazione degli stili, animazione, supporto del valore predefinito, ereditarietà, proprietà associate o invalidamento.

## <a name="learning-more-about-dependency-properties"></a>Informazioni approfondite sulle proprietà di dipendenza  

- Una proprietà associata è un tipo di proprietà che supporta una sintassi specializzata in XAML. Una proprietà associata spesso non ha una corrispondenza 1:1 con una proprietà [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] e non è necessariamente una proprietà di dipendenza. Lo scopo tipico di una proprietà associata consiste nel consentire agli elementi figlio di segnalare i valori della proprietà a un elemento padre, anche se quest'ultimo e l'elemento figlio non possiedono tale proprietà, come parte degli elenchi dei membri della classe. È uno scenario principale per gli elementi figlio per l'elemento padre che indicano come deve essere presentate [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]; per un esempio, vedere <xref:System.Windows.Controls.DockPanel.Dock%2A> o <xref:System.Windows.Controls.Canvas.Left%2A>. Per informazioni dettagliate, vedere [Cenni preliminari sulle proprietà associate](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).

- Gli sviluppatori di componenti o di applicazioni possono decidere di creare una proprietà di dipendenza personalizzata al fine di abilitare funzionalità quali il data binding o il supporto degli stili oppure per il supporto dell'invalidamento e della coercizione del valore. Per informazioni dettagliate, vedere [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md).

- Generalmente, le proprietà di dipendenza devono essere considerate come proprietà pubbliche, accessibili o almeno individuabili da parte di qualsiasi chiamante con accesso a un'istanza. Per altre informazioni, vedere [Sicurezza delle proprietà di dipendenza](../../../../docs/framework/wpf/advanced/dependency-property-security.md).

## <a name="see-also"></a>Vedere anche
 [Proprietà di dipendenza personalizzate](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Proprietà di dipendenza di sola lettura](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)  
 [Cenni preliminari su XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Architettura WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
