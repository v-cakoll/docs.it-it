---
title: Cenni preliminari sugli storyboard
desription: Organize and apply animations in storyboards. Use property-targeting syntax and combine timelines in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboard syntax [WPF]
- syntax [WPF], Storyboard
- timelines [WPF]
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
ms.openlocfilehash: 50f45953da3801bf73016c09b78a6a1b54878bc0
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853648"
---
# <a name="storyboards-overview"></a>Cenni preliminari sugli storyboard

In questo argomento viene illustrato come utilizzare <xref:System.Windows.Media.Animation.Storyboard> gli oggetti per organizzare e applicare animazioni. Viene descritto come modificare in modo interattivo <xref:System.Windows.Media.Animation.Storyboard> gli oggetti e viene descritta la sintassi indiretta per la destinazione della proprietà.

## <a name="prerequisites"></a>Prerequisiti

Per comprendere questo argomento, è necessario conoscere i diversi tipi di animazione e le relative funzionalità di base. Per un'introduzione alle animazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md). È anche necessario sapere come usare le proprietà associate. Per altre informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).

<a name="whatisatimeline"></a>

## <a name="what-is-a-storyboard"></a>Che cos'è uno storyboard?

Le animazioni non sono l'unico tipo utile della sequenza temporale. Sono disponibili altre classi di sequenze temporali per organizzare set di sequenze temporali e per applicare le sequenze temporali alle proprietà. Le sequenze temporali dei contenitori derivano dalla <xref:System.Windows.Media.Animation.TimelineGroup> classe e includono <xref:System.Windows.Media.Animation.ParallelTimeline> e <xref:System.Windows.Media.Animation.Storyboard> .

Un <xref:System.Windows.Media.Animation.Storyboard> è un tipo di sequenza temporale del contenitore che fornisce informazioni di destinazione per le sequenze temporali in essa contenute. Uno storyboard può contenere qualsiasi tipo di <xref:System.Windows.Media.Animation.Timeline> , incluse altre animazioni e sequenze temporali del contenitore. <xref:System.Windows.Media.Animation.Storyboard>gli oggetti consentono di combinare sequenze temporali che interessano una varietà di oggetti e proprietà in un unico albero della sequenza temporale, semplificando l'organizzazione e il controllo dei comportamenti di temporizzazione complessi. Si supponga, ad esempio, di volere un pulsante che esegua queste tre operazioni.

- Aumentare le dimensioni e cambiare colore quando l'utente seleziona il pulsante.

- Ridursi e tornare nuovamente alle dimensioni originali quando si fa clic su di esso.

- Comprimersi e perdere il 50% di opacità quando viene disabilitato.

In questo caso, si dispone di più set di animazioni che vengono applicati allo stesso oggetto e si desiderano riprodurre in momenti diversi, a seconda dello stato del pulsante. <xref:System.Windows.Media.Animation.Storyboard>gli oggetti consentono di organizzare le animazioni e di applicarle in gruppi a uno o più oggetti.

<a name="wherecanyouuseastoryboard"></a>

## <a name="where-can-you-use-a-storyboard"></a>Dov'è possibile usare uno storyboard?

Un oggetto <xref:System.Windows.Media.Animation.Storyboard> può essere usato per animare le proprietà di dipendenza delle classi animata (per altre informazioni su ciò che rende animata una classe, vedere [Cenni preliminari sull'animazione](animation-overview.md)). Tuttavia, poiché lo storyboard è una funzionalità a livello di Framework, l'oggetto deve appartenere a <xref:System.Windows.NameScope> di un oggetto <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> .

Ad esempio, è possibile usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> per eseguire le operazioni seguenti:

- Anima un <xref:System.Windows.Media.SolidColorBrush> (elemento non Framework) che dipinge lo sfondo di un pulsante (un tipo di <xref:System.Windows.FrameworkElement> ),

- Anima un <xref:System.Windows.Media.SolidColorBrush> (elemento non Framework) che dipinge il riempimento di un <xref:System.Windows.Media.GeometryDrawing> (elemento non Framework) visualizzato usando <xref:System.Windows.Controls.Image> ( <xref:System.Windows.FrameworkElement> ).

- Nel codice, aggiungere un'animazione a un oggetto <xref:System.Windows.Media.SolidColorBrush> dichiarato da una classe che contiene anche un oggetto <xref:System.Windows.FrameworkElement> , se il nome è stato <xref:System.Windows.Media.SolidColorBrush> registrato con <xref:System.Windows.FrameworkElement> .

Non è tuttavia possibile usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> per animare un oggetto <xref:System.Windows.Media.SolidColorBrush> che non ha registrato il nome con un oggetto <xref:System.Windows.FrameworkElement> o oppure <xref:System.Windows.FrameworkContentElement> non è stato usato per impostare una proprietà di un oggetto <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> .

<a name="applyanimationswithastoryboard"></a>

## <a name="how-to-apply-animations-with-a-storyboard"></a>Come applicare animazioni con uno storyboard

Per usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> per organizzare e applicare animazioni, è necessario aggiungere le animazioni come sequenze temporali figlio dell'oggetto <xref:System.Windows.Media.Animation.Storyboard> . La <xref:System.Windows.Media.Animation.Storyboard> classe fornisce le <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> proprietà associate e. Impostare queste proprietà su un'animazione per specificare l'oggetto di destinazione e la proprietà relativi.

Per applicare animazioni alle relative destinazioni, iniziare <xref:System.Windows.Media.Animation.Storyboard> usando un'azione trigger o un metodo. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è possibile utilizzare un <xref:System.Windows.Media.Animation.BeginStoryboard> oggetto con <xref:System.Windows.EventTrigger> , <xref:System.Windows.Trigger> o <xref:System.Windows.DataTrigger> . Nel codice è anche possibile usare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo.

La tabella seguente illustra le diverse posizioni in cui <xref:System.Windows.Media.Animation.Storyboard> è supportata ciascuna tecnica di inizio: per istanza, stile, modello di controllo e modello di dati. "Per istanza" si riferisce alla tecnica di applicazione di un'animazione o uno storyboard direttamente a istanze di un oggetto, piuttosto che in uno stile, un modello di controllo o un modello di dati.

|Storyboard iniziato usando…|Per istanza|Stile|Modello del controllo|Modello di dati|Esempio|
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|
|<xref:System.Windows.Media.Animation.BeginStoryboard>e un<xref:System.Windows.EventTrigger>|Sì|Sì|Sì|Sì|[Aggiungere un'animazione a una proprietà usando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard>e una proprietà<xref:System.Windows.Trigger>|No|Sì|Sì|Sì|[Attivare un'animazione quando il valore di una proprietà viene modificato](how-to-trigger-an-animation-when-a-property-value-changes.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard>e un<xref:System.Windows.DataTrigger>|No|Sì|Sì|Sì|[Procedura: Attivare un'animazione quando i dati vengono modificati](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|
|Metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Sì|No|No|No|[Aggiungere un'animazione a una proprietà usando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)|

Nell'esempio seguente viene utilizzato un oggetto <xref:System.Windows.Media.Animation.Storyboard> per animare l'oggetto <xref:System.Windows.FrameworkElement.Width%2A> di un <xref:System.Windows.Shapes.Rectangle> elemento e l'oggetto <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un oggetto <xref:System.Windows.Media.SolidColorBrush> utilizzato per disegnare tale oggetto <xref:System.Windows.Shapes.Rectangle> .

[!code-xaml[storyboards_ovw_snip_XAML#1](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]

[!code-csharp[storyboards_ovw_snip#100](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]

Le sezioni seguenti descrivono <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> le <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> proprietà e associate in modo più dettagliato.

<a name="targetingelementsandfreezables"></a>

## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Elementi del framework, elementi di contenuto del framework e oggetti Freezable

Nella sezione precedente è stato indicato che per trovare la relativa destinazione un'animazione deve conoscere il nome e la proprietà relativi cui aggiungere un'animazione. Specificare la proprietà da animare è semplice: è sufficiente impostare <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> con il nome della proprietà a cui aggiungere un'animazione.  Specificare il nome dell'oggetto di cui si desidera aggiungere un'animazione impostando la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> proprietà sull'animazione.

Per il corretto <xref:System.Windows.Setter.TargetName%2A> funzionamento della proprietà, l'oggetto di destinazione deve avere un nome. L'assegnazione di un nome a <xref:System.Windows.FrameworkElement> o a <xref:System.Windows.FrameworkContentElement> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è diversa dall'assegnazione di un nome a un <xref:System.Windows.Freezable> oggetto.

Gli elementi del Framework sono le classi che ereditano dalla <xref:System.Windows.FrameworkElement> classe. Esempi di elementi del Framework sono <xref:System.Windows.Window> ,, <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Button> e <xref:System.Windows.Shapes.Rectangle> . Praticamente tutte le finestre, i pannelli e i controlli sono elementi. Gli elementi di contenuto del Framework sono le classi che ereditano dalla <xref:System.Windows.FrameworkContentElement> classe. Esempi di elementi di contenuto del Framework includono <xref:System.Windows.Documents.FlowDocument> e <xref:System.Windows.Documents.Paragraph> . Se non si sa se un tipo è un elemento del framework o un elemento di contenuto del framework, verificare la presenza di una proprietà Name. Se è presente, è probabile che sia un elemento del framework o un elemento di contenuto del framework. Per esserne certi, verificare la sezione Gerarchia di ereditarietà della relativa pagina di tipo.

Per abilitare la destinazione di un elemento del Framework o di un elemento di contenuto del Framework in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , impostare la relativa <xref:System.Windows.FrameworkElement.Name%2A> Proprietà. Nel codice è anche necessario usare il <xref:System.Windows.NameScope.RegisterName%2A> metodo per registrare il nome dell'elemento con l'elemento per cui è stato creato un oggetto <xref:System.Windows.NameScope> .

Nell'esempio seguente, tratto dall'esempio precedente, viene assegnato il nome `MyRectangle` a <xref:System.Windows.Shapes.Rectangle> , un tipo di <xref:System.Windows.FrameworkElement> .

[!code-xaml[storyboards_ovw_snip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]

[!code-csharp[storyboards_ovw_snip#102](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]

Dopo aver impostato un nome, è possibile aggiungere un'animazione a una proprietà di quell'elemento.

[!code-xaml[storyboards_ovw_snip_XAML#5](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]

[!code-csharp[storyboards_ovw_snip#105](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]

<xref:System.Windows.Freezable>i tipi sono le classi che ereditano dalla <xref:System.Windows.Freezable> classe. Esempi di <xref:System.Windows.Freezable> includono <xref:System.Windows.Media.SolidColorBrush> , <xref:System.Windows.Media.RotateTransform> e <xref:System.Windows.Media.GradientStop> .

Per abilitare la destinazione di un oggetto <xref:System.Windows.Freezable> mediante un'animazione in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , usare la [direttiva x:Name](../../../desktop-wpf/xaml-services/xname-directive.md) per assegnarle un nome. Nel codice viene usato il <xref:System.Windows.NameScope.RegisterName%2A> metodo per registrare il nome con l'elemento per cui è stato creato un oggetto <xref:System.Windows.NameScope> .

Nell'esempio seguente viene assegnato un nome a un <xref:System.Windows.Freezable> oggetto.

[!code-xaml[storyboards_ovw_snip_XAML#3](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]

[!code-csharp[storyboards_ovw_snip#103](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]

L'oggetto può essere quindi impostato come destinazione da un'animazione.

[!code-xaml[storyboards_ovw_snip_XAML#7](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]

[!code-csharp[storyboards_ovw_snip#107](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]

<xref:System.Windows.Media.Animation.Storyboard>gli oggetti utilizzano gli ambiti dei nomi per risolvere la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Proprietà. Per altre informazioni sugli ambiti dei nomi WPF, vedere [NameScope XAML WPF](../advanced/wpf-xaml-namescopes.md). Se la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> proprietà viene omessa, l'animazione è destinata all'elemento su cui è definita oppure, nel caso di stili, all'elemento con stile.

A volte un nome non può essere assegnato a un <xref:System.Windows.Freezable> oggetto. Se, ad esempio, un oggetto <xref:System.Windows.Freezable> viene dichiarato come risorsa o viene usato per impostare un valore di proprietà in uno stile, non è possibile assegnargli un nome. Poiché non dispone di un nome, non è possibile impostarlo direttamente come destinazione, ma può essere impostato indirettamente. Le sezioni seguenti descrivono come usare l'impostazione indiretta delle destinazioni.

<a name="pathsyntaxforchangeable"></a>

## <a name="indirect-targeting"></a>Impostazione indiretta delle destinazioni

<xref:System.Windows.Freezable>In alcuni casi non è possibile indirizzare direttamente un'animazione, ad esempio quando <xref:System.Windows.Freezable> viene dichiarata come risorsa o utilizzata per impostare un valore di proprietà in uno stile. In questi casi, anche se non è possibile indirizzarlo direttamente, è comunque possibile animare l' <xref:System.Windows.Freezable> oggetto. Anziché impostare la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> proprietà con il nome dell'oggetto <xref:System.Windows.Freezable> , assegnargli il nome dell'elemento a cui <xref:System.Windows.Freezable> appartiene "." Ad esempio, un oggetto <xref:System.Windows.Media.SolidColorBrush> utilizzato per impostare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un elemento Rectangle appartiene a tale rettangolo. Per animare il pennello, impostare la proprietà dell'animazione <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> con una catena di proprietà che inizia in corrispondenza della proprietà dell'elemento del Framework o dell'elemento di contenuto del Framework <xref:System.Windows.Freezable> utilizzato per impostare e terminare con la <xref:System.Windows.Freezable> proprietà a cui aggiungere un'animazione.

[!code-xaml[storyboards_ovw_snip_XAML#33](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]

[!code-csharp[storyboards_ovw_snip#134](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]

Si noti che, se <xref:System.Windows.Freezable> è bloccato, verrà creato un clone e tale clone verrà animato. In questo caso, la proprietà dell'oggetto originale <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> continua a restituire `false` , perché l'oggetto originale non è effettivamente animato. Per ulteriori informazioni sulla clonazione, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).

Si noti inoltre che, quando si usa l'impostazione indiretta delle destinazioni di proprietà, è possibile impostare come destinazione oggetti che non esistono. Si supponga, ad esempio, che l'oggetto <xref:System.Windows.Controls.Control.Background%2A> di un determinato pulsante sia stato impostato con un oggetto <xref:System.Windows.Media.SolidColorBrush> e tenti di animare il colore, quando in realtà <xref:System.Windows.Media.LinearGradientBrush> è stato usato un oggetto per impostare lo sfondo del pulsante. In questi casi non viene generata alcuna eccezione. l'animazione non ha un effetto visibile perché non <xref:System.Windows.Media.LinearGradientBrush> reagisce alle modifiche apportate alla <xref:System.Windows.Media.SolidColorBrush.Color%2A> Proprietà.

Le sezioni seguenti descrivono la sintassi dell'impostazione indiretta delle destinazioni di proprietà in modo più dettagliato.

<a name="xamlsyntaxchangeableproperty"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Impostazione indiretta della destinazione di una proprietà di un oggetto Freezable in XAML

Per fare riferimento a una proprietà di un oggetto Freezable in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , usare la sintassi seguente.

| |
|-|
|*ElementPropertyName* `.` *FreezablePropertyName*|

Dove

- *ElementPropertyName* è la proprietà dell'oggetto <xref:System.Windows.FrameworkElement> <xref:System.Windows.Freezable> utilizzato da per impostare e

- *FreezablePropertyName* è la proprietà dell'oggetto <xref:System.Windows.Freezable> a cui aggiungere un'animazione.

Nel codice seguente viene illustrato come animare l'oggetto <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un oggetto <xref:System.Windows.Media.SolidColorBrush> utilizzato per impostare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un elemento Rectangle.

[!code-xaml[storyboards_ovw_snip_XAML#32](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]

Talvolta è necessario impostare come destinazione un oggetto freezable contenuto in una raccolta o una matrice.

Per impostare come destinazione un oggetto freezable contenuto in una raccolta, usare la sintassi del tracciato seguente.

| |
|-|
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|

Dove *CollectionIndex* è l'indice dell'oggetto nella matrice o nella raccolta.

Si supponga, ad esempio, che alla proprietà di un rettangolo sia <xref:System.Windows.Media.TransformGroup> applicata una risorsa <xref:System.Windows.UIElement.RenderTransform%2A> e che si desideri animare una delle trasformazioni in essa contenute.

[!code-xaml[storyboards_ovw_snip_XAML#34](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]

Nel codice seguente viene illustrato come aggiungere un'animazione alla <xref:System.Windows.Media.RotateTransform.Angle%2A> proprietà dell'oggetto <xref:System.Windows.Media.RotateTransform> illustrato nell'esempio precedente.

[!code-xaml[storyboards_ovw_snip_XAML#35](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]

<a name="targetingpropertyofchangeableincode"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Impostazione indiretta della destinazione di una proprietà di un oggetto Freezable nel codice

Nel codice viene creato un <xref:System.Windows.PropertyPath> oggetto. Quando si crea <xref:System.Windows.PropertyPath> , si specificano <xref:System.Windows.PropertyPath.Path%2A> e <xref:System.Windows.PropertyPath.PathParameters%2A> .

Per creare <xref:System.Windows.PropertyPath.PathParameters%2A> , è necessario creare una matrice di tipo contenente <xref:System.Windows.DependencyProperty> un elenco di campi dell'identificatore della proprietà di dipendenza. Il primo campo identificatore è per la proprietà di <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> che l'oggetto <xref:System.Windows.Freezable> viene utilizzato per impostare. Il campo identificatore successivo rappresenta la proprietà dell'oggetto <xref:System.Windows.Freezable> di destinazione. Considerarlo come una catena di proprietà che connette all' <xref:System.Windows.Freezable> <xref:System.Windows.FrameworkElement> oggetto.

Di seguito è riportato un esempio di una catena di proprietà di dipendenza destinata <xref:System.Windows.Media.SolidColorBrush.Color%2A> a di un oggetto <xref:System.Windows.Media.SolidColorBrush> utilizzato per impostare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un elemento Rectangle.

[!code-csharp[storyboards_ovw_snip#135](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]

È anche necessario specificare un <xref:System.Windows.PropertyPath.Path%2A> . Un oggetto <xref:System.Windows.PropertyPath.Path%2A> è un oggetto <xref:System.String> che indica <xref:System.Windows.PropertyPath.Path%2A> come interpretare <xref:System.Windows.PropertyPath.PathParameters%2A> la proprietà. Usa la sintassi seguente.

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|

Dove

- *OwnerPropertyArrayIndex* è l'indice della <xref:System.Windows.DependencyProperty> matrice che contiene l'identificatore della proprietà dell' <xref:System.Windows.FrameworkElement> oggetto <xref:System.Windows.Freezable> utilizzato da per impostare.

- *FreezablePropertyArrayIndex* è l'indice della <xref:System.Windows.DependencyProperty> matrice che contiene l'identificatore della proprietà di destinazione.

Nell'esempio seguente viene illustrato l'oggetto <xref:System.Windows.PropertyPath.Path%2A> che dovrebbe accompagnare l'oggetto <xref:System.Windows.PropertyPath.PathParameters%2A> definito nell'esempio precedente.

[!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]

Nell'esempio seguente viene combinato il codice degli esempi precedenti per animare l'oggetto <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un oggetto <xref:System.Windows.Media.SolidColorBrush> utilizzato per impostare l'oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> di un elemento Rectangle.

[!code-csharp[storyboards_ovw_snip#137](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]

Talvolta è necessario impostare come destinazione un oggetto freezable contenuto in una raccolta o una matrice. Si supponga, ad esempio, che alla proprietà di un rettangolo sia <xref:System.Windows.Media.TransformGroup> applicata una risorsa <xref:System.Windows.UIElement.RenderTransform%2A> e che si desideri animare una delle trasformazioni in essa contenute.

[!code-xaml[storyboards_ovw_snip#142](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]

Per fare riferimento a un oggetto <xref:System.Windows.Freezable> contenuto in una raccolta, usare la sintassi del percorso seguente.

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|

Dove *CollectionIndex* è l'indice dell'oggetto nella matrice o nella raccolta.

Per fare riferimento alla <xref:System.Windows.Media.RotateTransform.Angle%2A> proprietà di <xref:System.Windows.Media.RotateTransform> , la seconda trasformazione in <xref:System.Windows.Media.TransformGroup> , si utilizzeranno gli elementi <xref:System.Windows.PropertyPath.Path%2A> e <xref:System.Windows.PropertyPath.PathParameters%2A> .

[!code-csharp[storyboards_ovw_snip#139](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]

Nell'esempio seguente viene illustrato il codice completo per l'animazione <xref:System.Windows.Media.RotateTransform.Angle%2A> di un oggetto <xref:System.Windows.Media.RotateTransform> contenuto in un oggetto <xref:System.Windows.Media.TransformGroup> .

[!code-csharp[storyboards_ovw_snip#138](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]

### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Impostazione indiretta della destinazione con un oggetto Freezable come punto di partenza

Nelle sezioni precedenti è stato descritto come definire indirettamente come destinazione un oggetto <xref:System.Windows.Freezable> iniziando con <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> e creando una catena di proprietà a una <xref:System.Windows.Freezable> sottoproprietà. È anche possibile usare un <xref:System.Windows.Freezable> come punto di partenza e indirizzare indirettamente una delle relative <xref:System.Windows.Freezable> sottoproprietà. Una restrizione aggiuntiva si applica quando si usa un <xref:System.Windows.Freezable> come punto di partenza per la destinazione indiretta: l'inizio <xref:System.Windows.Freezable> e ogni <xref:System.Windows.Freezable> tra di essi e la sottoproprietà di destinazione indirettamente non devono essere bloccati.

<a name="controllable_storyboards"></a>

## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Controllo interattivo di uno storyboard in XAML

Per avviare uno storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , usare un' <xref:System.Windows.Media.Animation.BeginStoryboard> azione trigger. <xref:System.Windows.Media.Animation.BeginStoryboard>distribuisce le animazioni agli oggetti e alle proprietà a cui viene aggiunta un'animazione e avvia lo storyboard. Per informazioni dettagliate su questo processo, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md). Se si assegna <xref:System.Windows.Media.Animation.BeginStoryboard> un nome specificando la relativa <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> proprietà, si imposta uno storyboard controllabile. È quindi possibile controllare in modo interattivo lo storyboard dopo l'avvio. Di seguito è riportato un elenco di azioni dello storyboard controllabili da usare con i trigger di evento per controllare uno storyboard.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Sospende lo storyboard.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Riprende uno storyboard sospeso.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Modifica la velocità dello storyboard.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Sposta uno storyboard alla fine del periodo di riempimento, se presente.

- <xref:System.Windows.Media.Animation.StopStoryboard>: Arresta lo storyboard.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Rimuove lo storyboard.

Nell'esempio seguente le azioni di storyboard controllabili vengono usate per controllare uno storyboard in modo interattivo.

[!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]

<a name="controllable_storyboards_procedural"></a>

## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Controllo interattivo di uno storyboard tramite il codice

Gli esempi precedenti hanno illustrato come aggiungere animazioni tramite le azioni trigger. Nel codice è anche possibile controllare uno storyboard usando metodi interattivi della <xref:System.Windows.Media.Animation.Storyboard> classe. Affinché un oggetto <xref:System.Windows.Media.Animation.Storyboard> venga reso interattivo nel codice, è necessario utilizzare l'overload appropriato del metodo dello storyboard <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> e specificare `true` per renderlo controllabile. Per altre informazioni, vedere <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29>.

Nell'elenco seguente vengono illustrati i metodi che possono essere utilizzati per modificare un oggetto <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio:

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>

Il vantaggio dell'uso di questi metodi è che non è necessario creare <xref:System.Windows.Trigger> <xref:System.Windows.TriggerAction> oggetti o. è sufficiente un riferimento al controllabile <xref:System.Windows.Media.Animation.Storyboard> che si vuole modificare.

> [!NOTE]
> Tutte le azioni interattive eseguite su un oggetto <xref:System.Windows.Media.Animation.Clock> e quindi anche su un oggetto <xref:System.Windows.Media.Animation.Storyboard> si verificheranno al successivo ciclo del motore di temporizzazione che verrà eseguito poco prima del rendering successivo. Se, ad esempio, si usa il <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> metodo per passare a un altro punto di un'animazione, il valore della proprietà non viene modificato immediatamente, ma il valore viene modificato al successivo ciclo del motore di temporizzazione.

Nell'esempio seguente viene illustrato come applicare e controllare le animazioni mediante i metodi interattivi della <xref:System.Windows.Media.Animation.Storyboard> classe.

[!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
[!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]

<a name="usingstoryboardsinstyles"></a>

## <a name="animate-in-a-style"></a>Aggiungere un'animazione in uno stile

È possibile usare <xref:System.Windows.Media.Animation.Storyboard> gli oggetti per definire animazioni in un oggetto <xref:System.Windows.Style> . L'animazione con un oggetto <xref:System.Windows.Media.Animation.Storyboard> in <xref:System.Windows.Style> è simile all'uso di un' <xref:System.Windows.Media.Animation.Storyboard> altra, con le tre eccezioni seguenti:

- Non si specifica un oggetto <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> ; la <xref:System.Windows.Media.Animation.Storyboard> destinazione è sempre l'elemento a cui <xref:System.Windows.Style> viene applicato l'oggetto. Per <xref:System.Windows.Freezable> gli oggetti di destinazione, è necessario usare la destinazione indiretta. Per ulteriori informazioni sulla destinazione indiretta, vedere la sezione [destinazione indiretta](#pathsyntaxforchangeable) .

- Non è possibile specificare un oggetto per un oggetto <xref:System.Windows.EventTrigger.SourceName%2A> <xref:System.Windows.EventTrigger> o un oggetto <xref:System.Windows.Trigger> .

- Non è possibile usare riferimenti a risorse dinamiche o espressioni di data binding per impostare <xref:System.Windows.Media.Animation.Storyboard> o impostare i valori delle proprietà. Questo perché tutti gli elementi all'interno di <xref:System.Windows.Style> devono essere thread-safe e il sistema di temporizzazione deve essere <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> in grado di renderli thread-safe. Non è possibile bloccare un oggetto <xref:System.Windows.Media.Animation.Storyboard> se o le sequenze temporali figlio contengono riferimenti a risorse dinamiche o espressioni data binding. Per ulteriori informazioni sul blocco e su altre <xref:System.Windows.Freezable> funzionalità, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).

- In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non è possibile dichiarare i gestori eventi per <xref:System.Windows.Media.Animation.Storyboard> gli eventi di animazione o.

Per un esempio che illustra come definire uno storyboard in uno stile, vedere l'esempio [animate in uno stile](how-to-animate-in-a-style.md) .

<a name="defineAStoryboardInAControlTemplateSection"></a>

## <a name="animate-in-a-controltemplate"></a>Eseguire un'animazione in un ControlTemplate

È possibile usare <xref:System.Windows.Media.Animation.Storyboard> gli oggetti per definire animazioni in un oggetto <xref:System.Windows.Controls.ControlTemplate> . L'animazione con un oggetto <xref:System.Windows.Media.Animation.Storyboard> in <xref:System.Windows.Controls.ControlTemplate> è simile all'uso di un' <xref:System.Windows.Media.Animation.Storyboard> altra posizione, con le due eccezioni seguenti:

- <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>Può fare riferimento solo agli oggetti figlio dell'oggetto <xref:System.Windows.Controls.ControlTemplate> . Se <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> viene omesso, l'animazione è destinata all'elemento a cui <xref:System.Windows.Controls.ControlTemplate> viene applicato l'oggetto.

- <xref:System.Windows.EventTrigger.SourceName%2A>Per un oggetto <xref:System.Windows.EventTrigger> o un oggetto <xref:System.Windows.Trigger> può fare riferimento solo agli oggetti figlio dell'oggetto <xref:System.Windows.Controls.ControlTemplate> .

- Non è possibile usare riferimenti a risorse dinamiche o espressioni di data binding per impostare <xref:System.Windows.Media.Animation.Storyboard> o impostare i valori delle proprietà. Questo perché tutti gli elementi all'interno di <xref:System.Windows.Controls.ControlTemplate> devono essere thread-safe e il sistema di temporizzazione deve essere <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> in grado di renderli thread-safe. Non è possibile bloccare un oggetto <xref:System.Windows.Media.Animation.Storyboard> se o le sequenze temporali figlio contengono riferimenti a risorse dinamiche o espressioni data binding. Per ulteriori informazioni sul blocco e su altre <xref:System.Windows.Freezable> funzionalità, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).

- In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] non è possibile dichiarare i gestori eventi per <xref:System.Windows.Media.Animation.Storyboard> gli eventi di animazione o.

Per un esempio che illustra come definire uno storyboard in un oggetto <xref:System.Windows.Controls.ControlTemplate> , vedere l'esempio di [animazione in un oggetto ControlTemplate](how-to-animate-in-a-controltemplate.md) .

<a name="animateWhenAPropertyValueChanges"></a>

## <a name="animate-when-a-property-value-changes"></a>Aggiungere un'animazione quando viene modificato il valore di una proprietà

Negli stili e nei modelli di controllo è possibile usare oggetti Trigger per avviare uno storyboard quando una proprietà viene modificata. Per esempi, vedere [attivare un'animazione quando il valore di una proprietà viene modificato](how-to-trigger-an-animation-when-a-property-value-changes.md) e [animato in un oggetto ControlTemplate](how-to-animate-in-a-controltemplate.md).

Le animazioni applicate dagli <xref:System.Windows.Trigger> oggetti proprietà si comportano in modo più complesso rispetto alle animazioni <xref:System.Windows.EventTrigger> o alle animazioni avviate mediante i <xref:System.Windows.Media.Animation.Storyboard> metodi.  Le "consegne" con animazioni definite da altri <xref:System.Windows.Trigger> oggetti, ma compongono con <xref:System.Windows.EventTrigger> animazioni attivate dal metodo.

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
