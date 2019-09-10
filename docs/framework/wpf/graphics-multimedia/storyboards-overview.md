---
title: Cenni preliminari sugli storyboard
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboard syntax [WPF]
- syntax [WPF], Storyboard
- timelines [WPF]
ms.assetid: 1a698c3c-30f1-4b30-ae56-57e8a39811bd
ms.openlocfilehash: 4d5a5ee3f1fcbd09fad9e25773d0e508209e1492
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855834"
---
# <a name="storyboards-overview"></a>Cenni preliminari sugli storyboard

In questo argomento viene illustrato come <xref:System.Windows.Media.Animation.Storyboard> utilizzare gli oggetti per organizzare e applicare animazioni. Viene descritto come modificare <xref:System.Windows.Media.Animation.Storyboard> in modo interattivo gli oggetti e viene descritta la sintassi indiretta per la destinazione della proprietà.

## <a name="prerequisites"></a>Prerequisiti

Per comprendere questo argomento, è necessario conoscere i diversi tipi di animazione e le relative funzionalità di base. Per un'introduzione alle animazioni, vedere [Cenni preliminari sull'animazione](animation-overview.md). È anche necessario sapere come usare le proprietà associate. Per altre informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../advanced/attached-properties-overview.md).

<a name="whatisatimeline"></a>

## <a name="what-is-a-storyboard"></a>Che cos'è uno storyboard?

Le animazioni non sono l'unico tipo utile della sequenza temporale. Sono disponibili altre classi di sequenze temporali per organizzare set di sequenze temporali e per applicare le sequenze temporali alle proprietà. Le sequenze temporali dei <xref:System.Windows.Media.Animation.TimelineGroup> contenitori derivano dalla classe e includono <xref:System.Windows.Media.Animation.ParallelTimeline> e <xref:System.Windows.Media.Animation.Storyboard>.

Un <xref:System.Windows.Media.Animation.Storyboard> è un tipo di sequenza temporale del contenitore che fornisce informazioni di destinazione per le sequenze temporali in essa contenute. Uno storyboard può contenere qualsiasi tipo di <xref:System.Windows.Media.Animation.Timeline>, incluse altre animazioni e sequenze temporali del contenitore. <xref:System.Windows.Media.Animation.Storyboard>gli oggetti consentono di combinare sequenze temporali che interessano una varietà di oggetti e proprietà in un unico albero della sequenza temporale, semplificando l'organizzazione e il controllo dei comportamenti di temporizzazione complessi. Si supponga, ad esempio, di volere un pulsante che esegua queste tre operazioni.

- Aumentare le dimensioni e cambiare colore quando l'utente seleziona il pulsante.

- Ridursi e tornare nuovamente alle dimensioni originali quando si fa clic su di esso.

- Comprimersi e perdere il 50% di opacità quando viene disabilitato.

In questo caso, si dispone di più set di animazioni che vengono applicati allo stesso oggetto e si desiderano riprodurre in momenti diversi, a seconda dello stato del pulsante. <xref:System.Windows.Media.Animation.Storyboard>gli oggetti consentono di organizzare le animazioni e di applicarle in gruppi a uno o più oggetti.

<a name="wherecanyouuseastoryboard"></a>

## <a name="where-can-you-use-a-storyboard"></a>Dov'è possibile usare uno storyboard?

Un <xref:System.Windows.Media.Animation.Storyboard> oggetto può essere usato per animare le proprietà di dipendenza delle classi animata (per altre informazioni su ciò che rende animata una classe, vedere [Cenni preliminari sull'animazione](animation-overview.md)). Tuttavia, poiché lo storyboard è una funzionalità a livello <xref:System.Windows.NameScope> di Framework, l'oggetto deve appartenere a di un <xref:System.Windows.FrameworkElement> oggetto <xref:System.Windows.FrameworkContentElement>o.

Ad esempio, è possibile usare un <xref:System.Windows.Media.Animation.Storyboard> oggetto per eseguire le operazioni seguenti:

- Anima un <xref:System.Windows.Media.SolidColorBrush> (elemento non Framework) che dipinge lo sfondo di un pulsante (un tipo di <xref:System.Windows.FrameworkElement>),

- Anima un <xref:System.Windows.Media.SolidColorBrush> (elemento non Framework) che dipinge il riempimento di un <xref:System.Windows.Media.GeometryDrawing> ( <xref:System.Windows.Controls.Image> elemento non Framework) visualizzato usando (<xref:System.Windows.FrameworkElement>).

- Nel codice, aggiungere un'animazione <xref:System.Windows.Media.SolidColorBrush> a un oggetto dichiarato da una classe che <xref:System.Windows.FrameworkElement>contiene anche un <xref:System.Windows.Media.SolidColorBrush> oggetto, se il nome <xref:System.Windows.FrameworkElement>è stato registrato con.

Non è tuttavia possibile usare un oggetto <xref:System.Windows.Media.Animation.Storyboard> per animare un <xref:System.Windows.Media.SolidColorBrush> oggetto che non ha registrato il nome con <xref:System.Windows.FrameworkElement> un <xref:System.Windows.FrameworkContentElement>oggetto o oppure non è stato usato per impostare una proprietà <xref:System.Windows.FrameworkElement> di <xref:System.Windows.FrameworkContentElement>un oggetto o.

<a name="applyanimationswithastoryboard"></a>

## <a name="how-to-apply-animations-with-a-storyboard"></a>Come applicare animazioni con uno storyboard

Per usare un <xref:System.Windows.Media.Animation.Storyboard> oggetto per organizzare e applicare animazioni, è necessario aggiungere le animazioni come sequenze temporali <xref:System.Windows.Media.Animation.Storyboard>figlio dell'oggetto. La <xref:System.Windows.Media.Animation.Storyboard> classe fornisce le <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> proprietà <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> associate e. Impostare queste proprietà su un'animazione per specificare l'oggetto di destinazione e la proprietà relativi.

Per applicare animazioni alle relative destinazioni, iniziare <xref:System.Windows.Media.Animation.Storyboard> usando un'azione trigger o un metodo. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]è possibile utilizzare un <xref:System.Windows.Media.Animation.BeginStoryboard> oggetto con <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>o <xref:System.Windows.DataTrigger>. Nel codice è anche possibile usare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo.

La tabella seguente illustra le diverse posizioni in cui <xref:System.Windows.Media.Animation.Storyboard> è supportata ciascuna tecnica di inizio: per istanza, stile, modello di controllo e modello di dati. "Per istanza" si riferisce alla tecnica di applicazione di un'animazione o uno storyboard direttamente a istanze di un oggetto, piuttosto che in uno stile, un modello di controllo o un modello di dati.

|Storyboard iniziato usando…|Per istanza|Style|Modello di controllo|Modello di dati|Esempio|
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|
|<xref:System.Windows.Media.Animation.BeginStoryboard>e un<xref:System.Windows.EventTrigger>|Sì|Sì|Sì|Sì|[Animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard>e una proprietà<xref:System.Windows.Trigger>|No|Yes|Sì|Yes|[Attivare un'animazione quando il valore di una proprietà viene modificato](how-to-trigger-an-animation-when-a-property-value-changes.md)|
|<xref:System.Windows.Media.Animation.BeginStoryboard>e un<xref:System.Windows.DataTrigger>|No|Yes|Sì|Sì|[Procedura: Attiva un'animazione quando i dati vengono modificati](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa970679(v=vs.90))|
|Metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Sì|No|No|No|[Animare una proprietà utilizzando uno storyboard](how-to-animate-a-property-by-using-a-storyboard.md)|

Nell'esempio seguente viene utilizzato <xref:System.Windows.Media.Animation.Storyboard> un oggetto per animare l' <xref:System.Windows.Shapes.Rectangle> <xref:System.Windows.FrameworkElement.Width%2A> oggetto di un <xref:System.Windows.Media.SolidColorBrush.Color%2A> elemento e <xref:System.Windows.Media.SolidColorBrush> l'oggetto di un <xref:System.Windows.Shapes.Rectangle>oggetto utilizzato per disegnare tale oggetto.

[!code-xaml[storyboards_ovw_snip_XAML#1](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]

[!code-csharp[storyboards_ovw_snip#100](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]

Le sezioni seguenti descrivono <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> le <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> proprietà e associate in modo più dettagliato.

<a name="targetingelementsandfreezables"></a>

## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Elementi del framework, elementi di contenuto del framework e oggetti Freezable

Nella sezione precedente è stato indicato che per trovare la relativa destinazione un'animazione deve conoscere il nome e la proprietà relativi cui aggiungere un'animazione. Specificare la proprietà da animare è semplice: è sufficiente impostare <xref:System.Windows.Media.Animation.Storyboard.TargetProperty?displayProperty=nameWithType> con il nome della proprietà a cui aggiungere un'animazione.  Specificare il nome dell'oggetto di cui si desidera aggiungere un'animazione impostando la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> proprietà sull'animazione.

Per il <xref:System.Windows.Setter.TargetName%2A> corretto funzionamento della proprietà, l'oggetto di destinazione deve avere un nome. L'assegnazione di un nome a <xref:System.Windows.FrameworkElement> <xref:System.Windows.FrameworkContentElement> o a in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è diversa dall'assegnazione di un nome a un <xref:System.Windows.Freezable> oggetto.

Gli elementi del Framework sono le classi che ereditano dalla <xref:System.Windows.FrameworkElement> classe. Esempi di elementi del Framework <xref:System.Windows.Window>sono <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Button>,, e <xref:System.Windows.Shapes.Rectangle>. Praticamente tutte le finestre, i pannelli e i controlli sono elementi. Gli elementi di contenuto del Framework sono le classi che <xref:System.Windows.FrameworkContentElement> ereditano dalla classe. Esempi di elementi di contenuto del <xref:System.Windows.Documents.FlowDocument> Framework <xref:System.Windows.Documents.Paragraph>includono e. Se non si sa se un tipo è un elemento del framework o un elemento di contenuto del framework, verificare la presenza di una proprietà Name. Se è presente, è probabile che sia un elemento del framework o un elemento di contenuto del framework. Per esserne certi, verificare la sezione Gerarchia di ereditarietà della relativa pagina di tipo.

Per abilitare la destinazione di un elemento del Framework o di un elemento di contenuto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]del Framework in, <xref:System.Windows.FrameworkElement.Name%2A> impostare la relativa proprietà. Nel codice è anche necessario usare il <xref:System.Windows.NameScope.RegisterName%2A> metodo per registrare il nome dell'elemento con l'elemento per cui è stato creato un oggetto. <xref:System.Windows.NameScope>

Nell'esempio seguente, tratto dall'esempio precedente, viene assegnato il nome `MyRectangle` a <xref:System.Windows.Shapes.Rectangle>, un tipo di <xref:System.Windows.FrameworkElement>.

[!code-xaml[storyboards_ovw_snip_XAML#2](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]

[!code-csharp[storyboards_ovw_snip#102](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]

Dopo aver impostato un nome, è possibile aggiungere un'animazione a una proprietà di quell'elemento.

[!code-xaml[storyboards_ovw_snip_XAML#5](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]

[!code-csharp[storyboards_ovw_snip#105](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]

<xref:System.Windows.Freezable>i tipi sono le classi che ereditano <xref:System.Windows.Freezable> dalla classe. Esempi di <xref:System.Windows.Freezable> includono <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform>e .<xref:System.Windows.Media.GradientStop>

Per abilitare la destinazione di un <xref:System.Windows.Freezable> oggetto mediante un'animazione in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], usare la [direttiva x:Name](../../xaml-services/x-name-directive.md) per assegnarle un nome. Nel codice viene usato il <xref:System.Windows.NameScope.RegisterName%2A> metodo per registrare il nome con l'elemento per cui è stato creato un oggetto. <xref:System.Windows.NameScope>

Nell'esempio seguente viene assegnato un nome a un <xref:System.Windows.Freezable> oggetto.

[!code-xaml[storyboards_ovw_snip_XAML#3](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]

[!code-csharp[storyboards_ovw_snip#103](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]

L'oggetto può essere quindi impostato come destinazione da un'animazione.

[!code-xaml[storyboards_ovw_snip_XAML#7](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]

[!code-csharp[storyboards_ovw_snip#107](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]

<xref:System.Windows.Media.Animation.Storyboard>gli oggetti utilizzano gli ambiti dei nomi <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> per risolvere la proprietà. Per altre informazioni sugli ambiti dei nomi WPF, vedere [NameScope XAML WPF](../advanced/wpf-xaml-namescopes.md). Se la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> proprietà viene omessa, l'animazione è destinata all'elemento su cui è definita oppure, nel caso di stili, all'elemento con stile.

A volte un nome non può essere assegnato <xref:System.Windows.Freezable> a un oggetto. Se, ad esempio, <xref:System.Windows.Freezable> un oggetto viene dichiarato come risorsa o viene usato per impostare un valore di proprietà in uno stile, non è possibile assegnargli un nome. Poiché non dispone di un nome, non è possibile impostarlo direttamente come destinazione, ma può essere impostato indirettamente. Le sezioni seguenti descrivono come usare l'impostazione indiretta delle destinazioni.

<a name="pathsyntaxforchangeable"></a>

## <a name="indirect-targeting"></a>Impostazione indiretta delle destinazioni

In alcuni casi <xref:System.Windows.Freezable> non <xref:System.Windows.Freezable> è possibile indirizzare direttamente un'animazione, ad esempio quando viene dichiarata come risorsa o utilizzata per impostare un valore di proprietà in uno stile. In questi casi, anche se non è possibile indirizzarlo direttamente, è comunque possibile animare <xref:System.Windows.Freezable> l'oggetto. Anziché impostare la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> proprietà con il nome dell'oggetto <xref:System.Windows.Freezable>, assegnargli il nome dell'elemento a cui <xref:System.Windows.Freezable> appartiene "." Ad esempio, un <xref:System.Windows.Media.SolidColorBrush> oggetto utilizzato per impostare <xref:System.Windows.Shapes.Shape.Fill%2A> l'oggetto di un elemento Rectangle appartiene a tale rettangolo. Per animare il pennello, impostare la proprietà dell'animazione <xref:System.Windows.Media.Animation.Storyboard.TargetProperty> con una catena di proprietà che inizia in corrispondenza della proprietà dell'elemento del Framework o dell'elemento di contenuto del <xref:System.Windows.Freezable> Framework utilizzato per impostare e terminare con <xref:System.Windows.Freezable> la proprietà a cui aggiungere un'animazione.

[!code-xaml[storyboards_ovw_snip_XAML#33](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]

[!code-csharp[storyboards_ovw_snip#134](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]

Si noti che, se <xref:System.Windows.Freezable> è bloccato, verrà creato un clone e tale clone verrà animato. In questo caso, la <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> proprietà dell'oggetto originale continua a restituire `false`, perché l'oggetto originale non è effettivamente animato. Per ulteriori informazioni sulla clonazione, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).

Si noti inoltre che, quando si usa l'impostazione indiretta delle destinazioni di proprietà, è possibile impostare come destinazione oggetti che non esistono. Si supponga, ad esempio, che l' <xref:System.Windows.Controls.Control.Background%2A> oggetto di un determinato pulsante sia stato impostato <xref:System.Windows.Media.SolidColorBrush> con un oggetto e tenti di animare il colore, quando <xref:System.Windows.Media.LinearGradientBrush> in realtà è stato usato un oggetto per impostare lo sfondo del pulsante. In questi casi non viene generata alcuna eccezione. l'animazione non ha un effetto visibile perché <xref:System.Windows.Media.LinearGradientBrush> non reagisce alle modifiche apportate <xref:System.Windows.Media.SolidColorBrush.Color%2A> alla proprietà.

Le sezioni seguenti descrivono la sintassi dell'impostazione indiretta delle destinazioni di proprietà in modo più dettagliato.

<a name="xamlsyntaxchangeableproperty"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Impostazione indiretta della destinazione di una proprietà di un oggetto Freezable in XAML

Per fare riferimento a una proprietà di un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]oggetto Freezable in, usare la sintassi seguente.

| |
|-|
|*ElementPropertyName* `.` *FreezablePropertyName*|

Where

- *ElementPropertyName* è la proprietà dell'oggetto <xref:System.Windows.FrameworkElement> <xref:System.Windows.Freezable> utilizzato da per impostare e

- *FreezablePropertyName* è la proprietà dell'oggetto <xref:System.Windows.Freezable> a cui aggiungere un'animazione.

Nel codice seguente viene illustrato come animare l' <xref:System.Windows.Media.SolidColorBrush.Color%2A> oggetto di <xref:System.Windows.Media.SolidColorBrush> un oggetto utilizzato per <xref:System.Windows.Shapes.Shape.Fill%2A> impostare l'oggetto di un elemento Rectangle.

[!code-xaml[storyboards_ovw_snip_XAML#32](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]

Talvolta è necessario impostare come destinazione un oggetto freezable contenuto in una raccolta o una matrice.

Per impostare come destinazione un oggetto freezable contenuto in una raccolta, usare la sintassi del tracciato seguente.

| |
|-|
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|

Dove *CollectionIndex* è l'indice dell'oggetto nella matrice o nella raccolta.

Si supponga, ad esempio, che <xref:System.Windows.Media.TransformGroup> <xref:System.Windows.UIElement.RenderTransform%2A> alla proprietà di un rettangolo sia applicata una risorsa e che si desideri animare una delle trasformazioni in essa contenute.

[!code-xaml[storyboards_ovw_snip_XAML#34](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]

Nel codice seguente viene illustrato come aggiungere un'animazione <xref:System.Windows.Media.RotateTransform.Angle%2A> alla proprietà dell' <xref:System.Windows.Media.RotateTransform> oggetto illustrato nell'esempio precedente.

[!code-xaml[storyboards_ovw_snip_XAML#35](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]

<a name="targetingpropertyofchangeableincode"></a>

### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Impostazione indiretta della destinazione di una proprietà di un oggetto Freezable nel codice

Nel codice viene creato un <xref:System.Windows.PropertyPath> oggetto. Quando si crea <xref:System.Windows.PropertyPath>, si <xref:System.Windows.PropertyPath.Path%2A> specificano e <xref:System.Windows.PropertyPath.PathParameters%2A>.

Per creare <xref:System.Windows.PropertyPath.PathParameters%2A>, è necessario creare una matrice di <xref:System.Windows.DependencyProperty> tipo contenente un elenco di campi dell'identificatore della proprietà di dipendenza. Il primo campo identificatore è per la proprietà di <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> che l'oggetto <xref:System.Windows.Freezable> viene utilizzato per impostare. Il campo identificatore successivo rappresenta la proprietà dell' <xref:System.Windows.Freezable> oggetto di destinazione. Considerarlo come una catena di proprietà che connette <xref:System.Windows.Freezable> <xref:System.Windows.FrameworkElement> all'oggetto.

Di seguito è riportato un esempio di una catena di proprietà di dipendenza <xref:System.Windows.Media.SolidColorBrush.Color%2A> destinata <xref:System.Windows.Media.SolidColorBrush> a di un oggetto <xref:System.Windows.Shapes.Shape.Fill%2A> utilizzato per impostare l'oggetto di un elemento Rectangle.

[!code-csharp[storyboards_ovw_snip#135](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]

È anche necessario specificare un <xref:System.Windows.PropertyPath.Path%2A>. Un <xref:System.Windows.PropertyPath.Path%2A> oggetto è <xref:System.String> un oggetto che <xref:System.Windows.PropertyPath.Path%2A> indica come interpretare <xref:System.Windows.PropertyPath.PathParameters%2A>la proprietà. Usa la sintassi seguente.

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|

Where

- *OwnerPropertyArrayIndex* è l'indice della <xref:System.Windows.DependencyProperty> matrice che contiene <xref:System.Windows.FrameworkElement> l'identificatore della proprietà <xref:System.Windows.Freezable> dell'oggetto utilizzato da per impostare.

- *FreezablePropertyArrayIndex* è l'indice della <xref:System.Windows.DependencyProperty> matrice che contiene l'identificatore della proprietà di destinazione.

Nell'esempio seguente viene illustrato <xref:System.Windows.PropertyPath.Path%2A> l'oggetto che dovrebbe <xref:System.Windows.PropertyPath.PathParameters%2A> accompagnare l'oggetto definito nell'esempio precedente.

[!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]

Nell'esempio seguente viene combinato il codice degli esempi precedenti per animare l' <xref:System.Windows.Media.SolidColorBrush.Color%2A> oggetto di <xref:System.Windows.Media.SolidColorBrush> un oggetto utilizzato per <xref:System.Windows.Shapes.Shape.Fill%2A> impostare l'oggetto di un elemento Rectangle.

[!code-csharp[storyboards_ovw_snip#137](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]

Talvolta è necessario impostare come destinazione un oggetto freezable contenuto in una raccolta o una matrice. Si supponga, ad esempio, che <xref:System.Windows.Media.TransformGroup> <xref:System.Windows.UIElement.RenderTransform%2A> alla proprietà di un rettangolo sia applicata una risorsa e che si desideri animare una delle trasformazioni in essa contenute.

[!code-xaml[storyboards_ovw_snip#142](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]

Per fare riferimento <xref:System.Windows.Freezable> a un oggetto contenuto in una raccolta, usare la sintassi del percorso seguente.

| |
|-|
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|

Dove *CollectionIndex* è l'indice dell'oggetto nella matrice o nella raccolta.

Per fare riferimento <xref:System.Windows.Media.RotateTransform.Angle%2A> alla proprietà <xref:System.Windows.Media.RotateTransform>di, <xref:System.Windows.Media.TransformGroup>la seconda trasformazione in, si utilizzeranno gli elementi <xref:System.Windows.PropertyPath.Path%2A> e <xref:System.Windows.PropertyPath.PathParameters%2A>.

[!code-csharp[storyboards_ovw_snip#139](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]

Nell'esempio seguente viene illustrato il codice completo per l' <xref:System.Windows.Media.RotateTransform.Angle%2A> animazione di un oggetto <xref:System.Windows.Media.RotateTransform> contenuto in <xref:System.Windows.Media.TransformGroup>un oggetto.

[!code-csharp[storyboards_ovw_snip#138](~/samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]

### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Impostazione indiretta della destinazione con un oggetto Freezable come punto di partenza

Nelle sezioni precedenti è stato descritto come definire indirettamente <xref:System.Windows.Freezable> come destinazione un oggetto <xref:System.Windows.FrameworkElement> iniziando <xref:System.Windows.FrameworkContentElement> con o e creando una catena di <xref:System.Windows.Freezable> proprietà a una sottoproprietà. È anche possibile usare un <xref:System.Windows.Freezable> come punto di partenza e indirizzare indirettamente una delle <xref:System.Windows.Freezable> relative sottoproprietà. Una restrizione aggiuntiva si applica <xref:System.Windows.Freezable> quando si usa un come punto di partenza per la destinazione <xref:System.Windows.Freezable> indiretta <xref:System.Windows.Freezable> : l'inizio e ogni tra di essi e la sottoproprietà di destinazione indirettamente non devono essere bloccati.

<a name="controllable_storyboards"></a>

## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Controllo interattivo di uno storyboard in XAML

Per avviare uno storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], usare un' <xref:System.Windows.Media.Animation.BeginStoryboard> azione trigger. <xref:System.Windows.Media.Animation.BeginStoryboard>distribuisce le animazioni agli oggetti e alle proprietà a cui viene aggiunta un'animazione e avvia lo storyboard. Per informazioni dettagliate su questo processo, vedere [Cenni preliminari sull'animazione e sul sistema di temporizzazione](animation-and-timing-system-overview.md). Se si assegna <xref:System.Windows.Media.Animation.BeginStoryboard> un nome specificando la relativa <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> proprietà, si imposta uno storyboard controllabile. È quindi possibile controllare in modo interattivo lo storyboard dopo l'avvio. Di seguito è riportato un elenco di azioni dello storyboard controllabili da usare con i trigger di evento per controllare uno storyboard.

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

Gli esempi precedenti hanno illustrato come aggiungere animazioni tramite le azioni trigger. Nel codice è anche possibile controllare uno storyboard usando metodi interattivi della <xref:System.Windows.Media.Animation.Storyboard> classe. Affinché un <xref:System.Windows.Media.Animation.Storyboard> oggetto venga reso interattivo nel codice, è necessario utilizzare l'overload appropriato del <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo dello storyboard e specificare `true` per renderlo controllabile. Per ulteriori <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> informazioni, vedere la pagina.

Nell'elenco seguente vengono illustrati i metodi che possono essere utilizzati per <xref:System.Windows.Media.Animation.Storyboard> modificare un oggetto dopo l'avvio:

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>

- <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>

Il vantaggio dell'uso di questi metodi è che non è necessario creare <xref:System.Windows.Trigger> oggetti <xref:System.Windows.TriggerAction> o. è sufficiente un <xref:System.Windows.Media.Animation.Storyboard> riferimento al controllabile che si vuole modificare.

> [!NOTE]
> Tutte le azioni interattive eseguite <xref:System.Windows.Media.Animation.Clock>su un oggetto e quindi anche <xref:System.Windows.Media.Animation.Storyboard> su un oggetto si verificheranno al successivo ciclo del motore di temporizzazione che verrà eseguito poco prima del rendering successivo. Se, ad esempio, si usa <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> il metodo per passare a un altro punto di un'animazione, il valore della proprietà non viene modificato immediatamente, ma il valore viene modificato al successivo ciclo del motore di temporizzazione.

Nell'esempio seguente viene illustrato come applicare e controllare le animazioni mediante i metodi interattivi <xref:System.Windows.Media.Animation.Storyboard> della classe.

[!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
[!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]

<a name="usingstoryboardsinstyles"></a>

## <a name="animate-in-a-style"></a>Aggiungere un'animazione in uno stile

È possibile usare <xref:System.Windows.Media.Animation.Storyboard> gli oggetti per definire animazioni in <xref:System.Windows.Style>un oggetto. L'animazione con un <xref:System.Windows.Media.Animation.Storyboard> oggetto <xref:System.Windows.Style> in è simile all'uso di <xref:System.Windows.Media.Animation.Storyboard> un'altra, con le tre eccezioni seguenti:

- Non si specifica un <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>oggetto; <xref:System.Windows.Media.Animation.Storyboard> la destinazione è sempre l'elemento a <xref:System.Windows.Style> cui viene applicato l'oggetto. Per gli <xref:System.Windows.Freezable> oggetti di destinazione, è necessario usare la destinazione indiretta. Per ulteriori informazioni sulla destinazione indiretta, vedere la sezione [destinazione indiretta](#pathsyntaxforchangeable) .

- Non è possibile specificare <xref:System.Windows.EventTrigger.SourceName%2A> un oggetto <xref:System.Windows.EventTrigger> per un <xref:System.Windows.Trigger>oggetto o un oggetto.

- Non è possibile usare riferimenti a risorse dinamiche o espressioni di <xref:System.Windows.Media.Animation.Storyboard> data binding per impostare o impostare i valori delle proprietà. Questo perché tutti gli elementi all' <xref:System.Windows.Style> interno di devono essere thread-safe e il sistema di <xref:System.Windows.Freezable.Freeze%2A> temporizzazione deve <xref:System.Windows.Media.Animation.Storyboard> essere in grado di renderli thread-safe. Non <xref:System.Windows.Media.Animation.Storyboard> è possibile bloccare un oggetto se o le sequenze temporali figlio contengono riferimenti a risorse dinamiche o espressioni data binding. Per ulteriori informazioni sul blocco e su <xref:System.Windows.Freezable> altre funzionalità, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).

- In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]non è possibile dichiarare i gestori eventi per <xref:System.Windows.Media.Animation.Storyboard> gli eventi di animazione o.

Per un esempio che illustra come definire uno storyboard in uno stile, vedere l'esempio [animate in uno stile](how-to-animate-in-a-style.md) .

<a name="defineAStoryboardInAControlTemplateSection"></a>

## <a name="animate-in-a-controltemplate"></a>Eseguire un'animazione in un ControlTemplate

È possibile usare <xref:System.Windows.Media.Animation.Storyboard> gli oggetti per definire animazioni in <xref:System.Windows.Controls.ControlTemplate>un oggetto. L'animazione con un <xref:System.Windows.Media.Animation.Storyboard> oggetto <xref:System.Windows.Controls.ControlTemplate> in è simile all'uso di <xref:System.Windows.Media.Animation.Storyboard> un'altra posizione, con le due eccezioni seguenti:

- Può fare riferimento solo agli oggetti figlio dell'oggetto <xref:System.Windows.Controls.ControlTemplate>. <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> Se <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> viene omesso, l'animazione è destinata all'elemento a <xref:System.Windows.Controls.ControlTemplate> cui viene applicato l'oggetto.

- Per un <xref:System.Windows.EventTrigger> oggetto o un <xref:System.Windows.Trigger> oggetto<xref:System.Windows.Controls.ControlTemplate>può fare riferimento solo agli oggetti figlio dell'oggetto. <xref:System.Windows.EventTrigger.SourceName%2A>

- Non è possibile usare riferimenti a risorse dinamiche o espressioni di <xref:System.Windows.Media.Animation.Storyboard> data binding per impostare o impostare i valori delle proprietà. Questo perché tutti gli elementi all' <xref:System.Windows.Controls.ControlTemplate> interno di devono essere thread-safe e il sistema di <xref:System.Windows.Freezable.Freeze%2A> temporizzazione deve <xref:System.Windows.Media.Animation.Storyboard> essere in grado di renderli thread-safe. Non <xref:System.Windows.Media.Animation.Storyboard> è possibile bloccare un oggetto se o le sequenze temporali figlio contengono riferimenti a risorse dinamiche o espressioni data binding. Per ulteriori informazioni sul blocco e su <xref:System.Windows.Freezable> altre funzionalità, vedere [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md).

- In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]non è possibile dichiarare i gestori eventi per <xref:System.Windows.Media.Animation.Storyboard> gli eventi di animazione o.

Per un esempio che illustra come definire uno storyboard in un <xref:System.Windows.Controls.ControlTemplate>oggetto, vedere l'esempio di [animazione in un oggetto ControlTemplate](how-to-animate-in-a-controltemplate.md) .

<a name="animateWhenAPropertyValueChanges"></a>

## <a name="animate-when-a-property-value-changes"></a>Aggiungere un'animazione quando viene modificato il valore di una proprietà

Negli stili e nei modelli di controllo è possibile usare oggetti Trigger per avviare uno storyboard quando una proprietà viene modificata. Per esempi, vedere [attivare un'animazione quando il valore di una proprietà viene modificato](how-to-trigger-an-animation-when-a-property-value-changes.md) e [animato in un oggetto ControlTemplate](how-to-animate-in-a-controltemplate.md).

Le animazioni applicate dagli <xref:System.Windows.Trigger> oggetti proprietà si comportano in modo <xref:System.Windows.EventTrigger> più complesso rispetto alle animazioni <xref:System.Windows.Media.Animation.Storyboard> o alle animazioni avviate mediante i metodi.  Le "consegne" con animazioni definite da <xref:System.Windows.Trigger> altri oggetti, ma compongono con <xref:System.Windows.EventTrigger> animazioni attivate dal metodo.

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'animazione](animation-overview.md)
- [Cenni preliminari sulle tecniche di animazione delle proprietà](property-animation-techniques-overview.md)
- [Cenni preliminari sugli oggetti Freezable](../advanced/freezable-objects-overview.md)
