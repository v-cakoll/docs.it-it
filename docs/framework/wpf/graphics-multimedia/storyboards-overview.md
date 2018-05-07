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
ms.openlocfilehash: 36922dce795443a4c1136f6442eff1c297f3c641
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="storyboards-overview"></a>Cenni preliminari sugli storyboard
In questo argomento viene illustrato come utilizzare <xref:System.Windows.Media.Animation.Storyboard> oggetti per organizzare e applicare le animazioni. Viene descritto come modificare in modo interattivo <xref:System.Windows.Media.Animation.Storyboard> oggetti e descrive indiretta destinazioni delle proprietà.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Per comprendere questo argomento, è necessario conoscere i diversi tipi di animazione e le relative funzionalità di base. Per un'introduzione alle animazioni, vedere [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). È anche necessario sapere come usare le proprietà associate. Per altre informazioni sulle proprietà associate, vedere [Cenni preliminari sulle proprietà associate](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).  
  
<a name="whatisatimeline"></a>   
## <a name="what-is-a-storyboard"></a>Che cos'è uno storyboard?  
 Le animazioni non sono l'unico tipo utile della sequenza temporale. Sono disponibili altre classi di sequenze temporali per organizzare set di sequenze temporali e per applicare le sequenze temporali alle proprietà. Le sequenze temporali contenitore derivano dal <xref:System.Windows.Media.Animation.TimelineGroup> classe e includere <xref:System.Windows.Media.Animation.ParallelTimeline> e <xref:System.Windows.Media.Animation.Storyboard>.  
  
 Oggetto <xref:System.Windows.Media.Animation.Storyboard> è un tipo di sequenza temporale contenitore che fornisce informazioni per le sequenze in essa contenute. Uno Storyboard può contenere qualsiasi tipo di <xref:System.Windows.Media.Animation.Timeline>, tra cui altre sequenze temporali di contenitore e le animazioni. <xref:System.Windows.Media.Animation.Storyboard> gli oggetti consentono di combinare le sequenze temporali che influiscono su numerosi oggetti e proprietà in una singola struttura ad albero, rendendo più semplice organizzare e controllano i comportamenti di temporizzazione complessi. Si supponga, ad esempio, di volere un pulsante che esegua queste tre operazioni.  
  
-   Aumentare le dimensioni e cambiare colore quando l'utente seleziona il pulsante.  
  
-   Ridursi e tornare nuovamente alle dimensioni originali quando si fa clic su di esso.  
  
-   Comprimersi e perdere il 50% di opacità quando viene disabilitato.  
  
 In questo caso, si dispone di più set di animazioni che vengono applicati allo stesso oggetto e si desiderano riprodurre in momenti diversi, a seconda dello stato del pulsante. <xref:System.Windows.Media.Animation.Storyboard> gli oggetti consentono di organizzare le animazioni e applicate nei gruppi a uno o più oggetti.  
  
<a name="wherecanyouuseastoryboard"></a>   
## <a name="where-can-you-use-a-storyboard"></a>Dov'è possibile usare uno storyboard?  
 Oggetto <xref:System.Windows.Media.Animation.Storyboard> può essere utilizzato per aggiungere un'animazione di classi che supportano le proprietà di dipendenza (per ulteriori informazioni su cosa costituisce una classe che supporta l'animazione, vedere il [panoramica dell'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)). Tuttavia, poiché lo storyboard è una funzionalità a livello di framework, l'oggetto deve appartenere al <xref:System.Windows.NameScope> di un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  
  
 Ad esempio, è possibile utilizzare un <xref:System.Windows.Media.Animation.Storyboard> per eseguire le operazioni seguenti:  
  
-   Animare un <xref:System.Windows.Media.SolidColorBrush> (elemento Non framework) che disegna lo sfondo di un pulsante (un tipo di <xref:System.Windows.FrameworkElement>),  
  
-   Animare un <xref:System.Windows.Media.SolidColorBrush> (elemento Non framework) che disegna il riempimento di un <xref:System.Windows.Media.GeometryDrawing> (elemento Non framework) visualizzati utilizzando un <xref:System.Windows.Controls.Image> (<xref:System.Windows.FrameworkElement>).  
  
-   Nel codice, animare un <xref:System.Windows.Media.SolidColorBrush> dichiarato da una classe che contiene anche un <xref:System.Windows.FrameworkElement>, se il <xref:System.Windows.Media.SolidColorBrush> registrato il relativo nome con cui <xref:System.Windows.FrameworkElement>.  
  
 Tuttavia, non sarà possibile utilizzare un <xref:System.Windows.Media.Animation.Storyboard> animare un <xref:System.Windows.Media.SolidColorBrush> che non è stato registrato il nome con un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, o non è stato utilizzato per impostare una proprietà di un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>.  
  
<a name="applyanimationswithastoryboard"></a>   
## <a name="how-to-apply-animations-with-a-storyboard"></a>Come applicare animazioni con uno storyboard  
 Per utilizzare un <xref:System.Windows.Media.Animation.Storyboard> per organizzare e applicare le animazioni, è necessario aggiungere le animazioni come sequenze temporali figlio del <xref:System.Windows.Media.Animation.Storyboard>. Il <xref:System.Windows.Media.Animation.Storyboard> classe fornisce il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> le proprietà associate. Impostare queste proprietà su un'animazione per specificare l'oggetto di destinazione e la proprietà relativi.  
  
 Per applicare le animazioni alle destinazioni, iniziare il <xref:System.Windows.Media.Animation.Storyboard> utilizzando un'azione di trigger o un metodo. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], si utilizza un <xref:System.Windows.Media.Animation.BeginStoryboard> dell'oggetto con un <xref:System.Windows.EventTrigger>, <xref:System.Windows.Trigger>, o <xref:System.Windows.DataTrigger>. Nel codice, è inoltre possibile utilizzare il <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> metodo.  
  
 La tabella seguente illustra le diverse posizioni in cui ogni <xref:System.Windows.Media.Animation.Storyboard> iniziare tecnica è supportata: per ogni istanza, stile, modello di controllo e il modello di dati. "Per istanza" si riferisce alla tecnica di applicazione di un'animazione o uno storyboard direttamente a istanze di un oggetto, piuttosto che in uno stile, un modello di controllo o un modello di dati.  
  
|Storyboard iniziato usando…|Per istanza|Stile|Modello di controllo|Modello di dati|Esempio|  
|--------------------------------|-------------------|-----------|----------------------|-------------------|-------------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> e un oggetto <xref:System.Windows.EventTrigger>|Yes|Sì|Sì|Yes|[Animare una proprietà utilizzando uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> e una proprietà <xref:System.Windows.Trigger>|No|Sì|Sì|Yes|[Attivare un'animazione quando il valore di una proprietà viene modificato](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> e un <xref:System.Windows.DataTrigger>|No|Sì|Sì|Yes|[Procedura: Attivare un'animazione quando i dati vengono modificati](http://msdn.microsoft.com/library/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|Metodo <xref:System.Windows.Media.Animation.Storyboard.Begin%2A>|Yes|No|No|No|[Animare una proprietà utilizzando uno storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 Nell'esempio seguente viene utilizzato un <xref:System.Windows.Media.Animation.Storyboard> per animare la <xref:System.Windows.FrameworkElement.Width%2A> di un <xref:System.Windows.Shapes.Rectangle> elemento e il <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush> usato per disegnare che <xref:System.Windows.Shapes.Rectangle>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#1)]  
  
 [!code-csharp[storyboards_ovw_snip#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#100)]  
  
 Le sezioni seguenti descrivono il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> e <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> associate in modo più dettagliato.  
  
<a name="targetingelementsandfreezables"></a>   
## <a name="targeting-framework-elements-framework-content-elements-and-freezables"></a>Elementi del framework, elementi di contenuto del framework e oggetti Freezable  
 Nella sezione precedente è stato indicato che per trovare la relativa destinazione un'animazione deve conoscere il nome e la proprietà relativi cui aggiungere un'animazione. Specifica la proprietà da animare è semplice: è sufficiente impostare <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A?displayProperty=nameWithType> con il nome della proprietà da animare.  Specificare il nome dell'oggetto a cui si desidera aggiungere un'animazione impostando la proprietà di <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A?displayProperty=nameWithType> proprietà l'animazione.  
  
 Per il <xref:System.Windows.Setter.TargetName%2A> proprietà funzioni, l'oggetto di destinazione deve avere un nome. L'assegnazione di un nome di un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] è diverso rispetto all'assegnazione di un nome per un <xref:System.Windows.Freezable> oggetto.  
  
 Gli elementi del Framework sono classi che ereditano dalla <xref:System.Windows.FrameworkElement> classe. Esempi di elementi di framework <xref:System.Windows.Window>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Button>, e <xref:System.Windows.Shapes.Rectangle>. Praticamente tutte le finestre, i pannelli e i controlli sono elementi. Gli elementi di contenuto del Framework sono classi che ereditano dalla <xref:System.Windows.FrameworkContentElement> classe. Esempi di elementi con contenuto framework <xref:System.Windows.Documents.FlowDocument> e <xref:System.Windows.Documents.Paragraph>. Se non si sa se un tipo è un elemento del framework o un elemento di contenuto del framework, verificare la presenza di una proprietà Name. Se è presente, è probabile che sia un elemento del framework o un elemento di contenuto del framework. Per esserne certi, verificare la sezione Gerarchia di ereditarietà della relativa pagina di tipo.  
  
 Per abilitare l'assegnazione di un elemento framework o di un elemento di contenuto del framework in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], impostare il relativo <xref:System.Windows.FrameworkElement.Name%2A> proprietà. Nel codice, è inoltre necessario utilizzare il <xref:System.Windows.NameScope.RegisterName%2A> metodo per registrare il nome dell'elemento con l'elemento per cui è stato creato un <xref:System.Windows.NameScope>.  
  
 Nell'esempio seguente, tratto dall'esempio precedente, assegna il nome `MyRectangle` un <xref:System.Windows.Shapes.Rectangle>, un tipo di <xref:System.Windows.FrameworkElement>.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#2)]  
  
 [!code-csharp[storyboards_ovw_snip#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#102)]  
  
 Dopo aver impostato un nome, è possibile aggiungere un'animazione a una proprietà di quell'elemento.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#5)]  
  
 [!code-csharp[storyboards_ovw_snip#105](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#105)]  
  
 <xref:System.Windows.Freezable> i tipi sono classi che ereditano dal <xref:System.Windows.Freezable> classe. Esempi di <xref:System.Windows.Freezable> includono <xref:System.Windows.Media.SolidColorBrush>, <xref:System.Windows.Media.RotateTransform>, e <xref:System.Windows.Media.GradientStop>.  
  
 Per abilitare l'assegnazione di un <xref:System.Windows.Freezable> tramite un'animazione in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], si utilizza il [direttiva X:Name](../../../../docs/framework/xaml-services/x-name-directive.md) per assegnare un nome. Nel codice utilizza il <xref:System.Windows.NameScope.RegisterName%2A> metodo per registrare il proprio nome di elemento per cui è stato creato un <xref:System.Windows.NameScope>.  
  
 Nell'esempio seguente viene assegnato un nome di un <xref:System.Windows.Freezable> oggetto.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#3)]  
  
 [!code-csharp[storyboards_ovw_snip#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#103)]  
  
 L'oggetto può essere quindi impostato come destinazione da un'animazione.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/StoryboardsExample.xaml#7)]  
  
 [!code-csharp[storyboards_ovw_snip#107](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/StoryboardsExample.cs#107)]  
  
 <xref:System.Windows.Media.Animation.Storyboard> gli oggetti usano gli ambiti del nome per risolvere il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> proprietà. Per altre informazioni sugli ambiti dei nomi WPF, vedere [NameScope XAML WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md). Se il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> proprietà viene omessa, l'elemento su cui è stato definito o, nel caso di stili, l'elemento con stile ha come destinazione l'animazione.  
  
 Talvolta non è possibile assegnare un nome di un <xref:System.Windows.Freezable> oggetto. Ad esempio, se un <xref:System.Windows.Freezable> viene dichiarato come una risorsa o utilizzato per impostare un valore della proprietà in uno stile, non è possibile assegnare un nome. Poiché non dispone di un nome, non è possibile impostarlo direttamente come destinazione, ma può essere impostato indirettamente. Le sezioni seguenti descrivono come usare l'impostazione indiretta delle destinazioni.  
  
<a name="pathsyntaxforchangeable"></a>   
## <a name="indirect-targeting"></a>Impostazione indiretta delle destinazioni  
 Talvolta un <xref:System.Windows.Freezable> non può essere la destinazione direttamente da un'animazione, ad esempio quando il <xref:System.Windows.Freezable> viene dichiarato come una risorsa o utilizzato per impostare un valore della proprietà in uno stile. In questi casi, anche se è possibile destinazione direttamente, è ancora possibile animare la <xref:System.Windows.Freezable> oggetto. Anziché impostare la <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> proprietà con il nome del <xref:System.Windows.Freezable>, assegnare ad esso il nome dell'elemento a cui il <xref:System.Windows.Freezable> "appartiene". Ad esempio, un <xref:System.Windows.Media.SolidColorBrush> utilizzato per impostare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un rettangolo elemento appartiene a questo rettangolo. Per animare il pennello, impostare l'animazione <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> con una catena di proprietà che inizia in corrispondenza la proprietà dell'elemento del framework o elemento di contenuto del framework di <xref:System.Windows.Freezable> è stato utilizzato per impostare e termina con il <xref:System.Windows.Freezable> proprietà da animare.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#33)]  
  
 [!code-csharp[storyboards_ovw_snip#134](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#134)]  
  
 Si noti che, se il <xref:System.Windows.Freezable> è bloccata, verrà eseguito un duplicato e tale duplicato verrà animato. In questo caso, l'oggetto originale <xref:System.Windows.Media.Animation.Animatable.HasAnimatedProperties%2A> proprietà continua a restituire `false`, perché l'oggetto originale non è effettivamente animato. Per ulteriori informazioni sulla clonazione, vedere il [panoramica sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Si noti inoltre che, quando si usa l'impostazione indiretta delle destinazioni di proprietà, è possibile impostare come destinazione oggetti che non esistono. Ad esempio, si potrebbe supporre che il <xref:System.Windows.Controls.Control.Background%2A> di un pulsante è stato impostato con un <xref:System.Windows.Media.SolidColorBrush> e si tenta di aggiungere un'animazione a colore, quando in realtà un <xref:System.Windows.Media.LinearGradientBrush> è stato utilizzato per impostare lo sfondo del pulsante. In questi casi, viene generata alcuna eccezione; l'animazione non ha un effetto visibile perché <xref:System.Windows.Media.LinearGradientBrush> non rispondere alle modifiche apportate al <xref:System.Windows.Media.SolidColorBrush.Color%2A> proprietà.  
  
 Le sezioni seguenti descrivono la sintassi dell'impostazione indiretta delle destinazioni di proprietà in modo più dettagliato.  
  
<a name="xamlsyntaxchangeableproperty"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-xaml"></a>Impostazione indiretta della destinazione di una proprietà di un oggetto Freezable in XAML  
 Per impostare come destinazione una proprietà di un oggetto freezable in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], utilizzare la sintassi seguente.  
  
||  
|-|  
|*ElementPropertyName* `.` *FreezablePropertyName*|  
  
 Dove  
  
-   *ElementPropertyName* è la proprietà del <xref:System.Windows.FrameworkElement> cui il <xref:System.Windows.Freezable> utilizzato per impostare, e  
  
-   *FreezablePropertyName* è la proprietà del <xref:System.Windows.Freezable> per l'animazione.  
  
 Il codice seguente viene illustrato come animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush> utilizzato per impostare il  
  
 <xref:System.Windows.Shapes.Shape.Fill%2A> di un elemento rettangolo.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#32)]  
  
 Talvolta è necessario impostare come destinazione un oggetto freezable contenuto in una raccolta o una matrice.  
  
 Per impostare come destinazione un oggetto freezable contenuto in una raccolta, usare la sintassi del tracciato seguente.  
  
||  
|-|  
|*ElementPropertyName* `.Children[` *CollectionIndex* `].` *FreezablePropertyName*|  
  
 Dove *CollectionIndex* è l'indice dell'oggetto nella matrice o raccolta.  
  
 Ad esempio, si supponga che un rettangolo ha un <xref:System.Windows.Media.TransformGroup> risorsa applicata alla relativa <xref:System.Windows.UIElement.RenderTransform%2A> proprietà e si desidera aggiungere un'animazione a una delle trasformazioni contiene.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#34)]  
  
 Il codice seguente viene illustrato come animare la <xref:System.Windows.Media.RotateTransform.Angle%2A> proprietà del <xref:System.Windows.Media.RotateTransform> illustrato nell'esempio precedente.  
  
 [!code-xaml[storyboards_ovw_snip_XAML#35](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip_XAML/CS/IndirectTargetingExample.xaml#35)]  
  
<a name="targetingpropertyofchangeableincode"></a>   
### <a name="indirectly-targeting-a-property-of-a-freezable-in-code"></a>Impostazione indiretta della destinazione di una proprietà di un oggetto Freezable nel codice  
 Nel codice, si crea un <xref:System.Windows.PropertyPath> oggetto. Quando si crea il <xref:System.Windows.PropertyPath>, si specifica un <xref:System.Windows.PropertyPath.Path%2A> e <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 Per creare <xref:System.Windows.PropertyPath.PathParameters%2A>, si crea una matrice di tipo <xref:System.Windows.DependencyProperty> che contiene un elenco di campi di identificatore di proprietà di dipendenza. È il primo campo dell'identificatore della proprietà del <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> che il <xref:System.Windows.Freezable> utilizzato per impostare. Il campo dell'identificatore successivo rappresenta la proprietà del <xref:System.Windows.Freezable> di destinazione. Considerarlo come una catena di proprietà che si connette il <xref:System.Windows.Freezable> per il <xref:System.Windows.FrameworkElement> oggetto.  
  
 Di seguito è riportato un esempio di una catena di proprietà di dipendenza che ha come destinazione il <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush> utilizzato per impostare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un elemento rettangolo.  
  
 [!code-csharp[storyboards_ovw_snip#135](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#135)]  
  
 È inoltre necessario specificare un <xref:System.Windows.PropertyPath.Path%2A>. A <xref:System.Windows.PropertyPath.Path%2A> è un <xref:System.String> che indica il <xref:System.Windows.PropertyPath.Path%2A> come interpretare il <xref:System.Windows.PropertyPath.PathParameters%2A>. Usa la sintassi seguente.  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *FreezablePropertyArrayIndex* `)`|  
  
 Dove  
  
-   *OwnerPropertyArrayIndex* è l'indice del <xref:System.Windows.DependencyProperty> matrice che contiene l'identificatore del <xref:System.Windows.FrameworkElement> proprietà dell'oggetto che il <xref:System.Windows.Freezable> utilizzato per impostare, e  
  
-   *FreezablePropertyArrayIndex* è l'indice del <xref:System.Windows.DependencyProperty> matrice che contiene l'identificatore della proprietà di destinazione.  
  
 Nell'esempio seguente il <xref:System.Windows.PropertyPath.Path%2A> associata al <xref:System.Windows.PropertyPath.PathParameters%2A> definito nell'esempio precedente.
  
 [!code-csharp[storyboards_ovw_snip#PropertyChainAndPath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#propertychainandpath)]  
  
 L'esempio seguente unisce il codice negli esempi precedenti per animare la <xref:System.Windows.Media.SolidColorBrush.Color%2A> di un <xref:System.Windows.Media.SolidColorBrush> utilizzato per impostare il <xref:System.Windows.Shapes.Shape.Fill%2A> di un elemento rettangolo.  
  
 [!code-csharp[storyboards_ovw_snip#137](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#137)]  
  
 Talvolta è necessario impostare come destinazione un oggetto freezable contenuto in una raccolta o una matrice. Ad esempio, si supponga che un rettangolo ha un <xref:System.Windows.Media.TransformGroup> risorsa applicata alla relativa <xref:System.Windows.UIElement.RenderTransform%2A> proprietà e si desidera aggiungere un'animazione a una delle trasformazioni contiene.  
  
 [!code-xaml[storyboards_ovw_snip#142](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml#142)]  
  
 Destinazione un <xref:System.Windows.Freezable> è contenuto in una raccolta, utilizzare la seguente sintassi del percorso.  
  
||  
|-|  
|`(` *OwnerPropertyArrayIndex* `).(` *CollectionChildrenPropertyArrayIndex* `)` `[` *CollectionIndex* `].(` *FreezablePropertyArrayIndex* `)`|  
  
 Dove *CollectionIndex* è l'indice dell'oggetto nella matrice o raccolta.  
  
 Alla destinazione di <xref:System.Windows.Media.RotateTransform.Angle%2A> proprietà del <xref:System.Windows.Media.RotateTransform>, la seconda trasformazione nel <xref:System.Windows.Media.TransformGroup>, è necessario utilizzare la seguente <xref:System.Windows.PropertyPath.Path%2A> e <xref:System.Windows.PropertyPath.PathParameters%2A>.  
  
 [!code-csharp[storyboards_ovw_snip#139](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#139)]  
  
 Nell'esempio seguente viene illustrato il codice completo per l'animazione di <xref:System.Windows.Media.RotateTransform.Angle%2A> di un <xref:System.Windows.Media.RotateTransform> contenuti all'interno di un <xref:System.Windows.Media.TransformGroup>.  
  
 [!code-csharp[storyboards_ovw_snip#138](../../../../samples/snippets/csharp/VS_Snippets_Wpf/storyboards_ovw_snip/CSharp/IndirectTargetingExample.xaml.cs#138)]  
  
### <a name="indirectly-targeting-with-a-freezable-as-the-starting-point"></a>Impostazione indiretta della destinazione con un oggetto Freezable come punto di partenza  
 Nelle sezioni precedenti descrivono indirettamente riferimento a un <xref:System.Windows.Freezable> a partire da un <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement> e la creazione di una catena di proprietà per un <xref:System.Windows.Freezable> delle sottoproprietà. È inoltre possibile utilizzare un <xref:System.Windows.Freezable> come un avvio di un punto e indirettamente riferimento a una delle relative <xref:System.Windows.Freezable> sottoproprietà. Un'ulteriore restrizione si applica quando si utilizza un <xref:System.Windows.Freezable> come punto di partenza per indiretta: l'avvio <xref:System.Windows.Freezable> e ogni <xref:System.Windows.Freezable> tra questo e di sottoproprietà indirettamente come destinazione non deve essere bloccato.  
  
<a name="controllable_storyboards"></a>   
## <a name="interactively-controlling-a-storyboard-in-xaml"></a>Controllo interattivo di uno storyboard in XAML  
 Per avviare uno storyboard in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], si utilizza un <xref:System.Windows.Media.Animation.BeginStoryboard> azione attivata. <xref:System.Windows.Media.Animation.BeginStoryboard> distribuisce le animazioni agli oggetti e proprietà animate e avvia lo storyboard. (Per informazioni dettagliate su questo processo, vedere il [animazione e temporizzazione System Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).) Se si assegna il <xref:System.Windows.Media.Animation.BeginStoryboard> specificando un nome di relativo <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> proprietà consentono di uno storyboard controllabile. È quindi possibile controllare in modo interattivo lo storyboard dopo l'avvio. Di seguito è riportato un elenco di azioni dello storyboard controllabili da usare con i trigger di evento per controllare uno storyboard.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Sospende lo storyboard.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Consente di riprendere uno storyboard in pausa.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Modifica la velocità dello storyboard.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Sposta uno storyboard alla fine del periodo di riempimento, se presente.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Interrompe lo storyboard.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Rimuove lo storyboard.  
  
 Nell'esempio seguente le azioni di storyboard controllabili vengono usate per controllare uno storyboard in modo interattivo.  
  
 [!code-xaml[animation_ovws_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snip/CS/ControllableStoryboardExample.xaml#controllablestoryboardexamplewholepage)]  
  
<a name="controllable_storyboards_procedural"></a>   
## <a name="interactively-controlling-a-storyboard-by-using-code"></a>Controllo interattivo di uno storyboard tramite il codice  
 Gli esempi precedenti hanno illustrato come aggiungere animazioni tramite le azioni trigger. Nel codice, è inoltre possibile controllare uno storyboard utilizzando metodi interattivi della <xref:System.Windows.Media.Animation.Storyboard> classe. Per un <xref:System.Windows.Media.Animation.Storyboard> per rendere interattivo nel codice, è necessario utilizzare l'overload appropriato dello storyboard <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> (metodo) e specificare `true` per renderlo controllabile. Vedere il <xref:System.Windows.Media.Animation.Storyboard.Begin%28System.Windows.FrameworkElement%2CSystem.Boolean%29> pagina per altre informazioni.  
  
 Nell'elenco seguente sono illustrati i metodi che possono essere utilizzati per manipolare una <xref:System.Windows.Media.Animation.Storyboard> dopo l'avvio:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Remove%2A>  
  
 Il vantaggio dell'utilizzo di questi metodi è che non è necessario creare <xref:System.Windows.Trigger> o <xref:System.Windows.TriggerAction> oggetti, è sufficiente un riferimento a controllabile che <xref:System.Windows.Media.Animation.Storyboard> si desidera modificare.  
  
 **Nota:** tutte le azioni interattive effettuate su un <xref:System.Windows.Media.Animation.Clock>e, pertanto anche su un <xref:System.Windows.Media.Animation.Storyboard> si verificherà in tick successivo del motore di temporizzazione che precederà il rendering successivo. Ad esempio, se si utilizza il <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> metodo per passare a un altro punto di un'animazione, il valore della proprietà non cambia immediatamente, invece, il valore viene modificato al tick successivo del motore di temporizzazione.  
  
 Nell'esempio seguente viene illustrato come applicare e controllare le animazioni utilizzando i metodi interattivi della <xref:System.Windows.Media.Animation.Storyboard> classe.  
  
 [!code-csharp[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_procedural_snip/CSharp/ControllableStoryboardExample.cs#controllablestoryboardexamplewholepage)]
 [!code-vb[animation_ovws_procedural_snip#ControllableStoryboardExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animation_ovws_procedural_snip/visualbasic/controllablestoryboardexample.vb#controllablestoryboardexamplewholepage)]  
  
<a name="usingstoryboardsinstyles"></a>   
## <a name="animate-in-a-style"></a>Aggiungere un'animazione in uno stile  
 È possibile utilizzare <xref:System.Windows.Media.Animation.Storyboard> oggetti per definire le animazioni in un <xref:System.Windows.Style>. Animazione con un <xref:System.Windows.Media.Animation.Storyboard> in un <xref:System.Windows.Style> è simile all'utilizzo di un <xref:System.Windows.Media.Animation.Storyboard> altrove, con le tre eccezioni seguenti:  
  
-   Non si specifica un <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A>; <xref:System.Windows.Media.Animation.Storyboard> sempre l'elemento a cui è destinato il <xref:System.Windows.Style> viene applicato. Destinazione <xref:System.Windows.Freezable> oggetti, è necessario utilizzare indiretta. Per ulteriori informazioni sulla modalità indiretta, vedere il [indiretta](#pathsyntaxforchangeable) sezione.  
  
-   Non è possibile specificare un <xref:System.Windows.EventTrigger.SourceName%2A> per un <xref:System.Windows.EventTrigger> o <xref:System.Windows.Trigger>.  
  
-   È possibile utilizzare espressioni di associazione dati o riferimenti a risorse dinamiche per impostare <xref:System.Windows.Media.Animation.Storyboard> o i valori delle proprietà di animazione. Poiché tutti gli elementi all'interno di un <xref:System.Windows.Style> deve essere thread-safe, e il sistema di temporizzazione deve <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> oggetti in modo thread-safe. Oggetto <xref:System.Windows.Media.Animation.Storyboard> non può essere bloccato se è o le sequenze temporali figlio contengono espressioni di associazione dati o riferimenti a risorse dinamiche. Per ulteriori informazioni sul blocco e altri su <xref:System.Windows.Freezable> funzionalità, vedere il [panoramica sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile dichiarare i gestori eventi per <xref:System.Windows.Media.Animation.Storyboard> o eventi di animazione.  
  
 Per un esempio che illustra come definire uno storyboard in uno stile, vedere il [Animate in uno stile](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-style.md) esempio.  
  
<a name="defineAStoryboardInAControlTemplateSection"></a>   
## <a name="animate-in-a-controltemplate"></a>Eseguire un'animazione in un ControlTemplate  
 È possibile utilizzare <xref:System.Windows.Media.Animation.Storyboard> oggetti per definire le animazioni in un <xref:System.Windows.Controls.ControlTemplate>. Animazione con un <xref:System.Windows.Media.Animation.Storyboard> in un <xref:System.Windows.Controls.ControlTemplate> è simile all'utilizzo di un <xref:System.Windows.Media.Animation.Storyboard> altrove, con le due eccezioni seguenti:  
  
-   Il <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> possono fare riferimento solo agli oggetti figlio del <xref:System.Windows.Controls.ControlTemplate>. Se <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> non viene specificato, l'elemento a cui è destinato l'animazione di <xref:System.Windows.Controls.ControlTemplate> viene applicato.  
  
-   Il <xref:System.Windows.EventTrigger.SourceName%2A> per un <xref:System.Windows.EventTrigger> o <xref:System.Windows.Trigger> possono fare riferimento solo agli oggetti figlio del <xref:System.Windows.Controls.ControlTemplate>.  
  
-   È possibile utilizzare espressioni di associazione dati o riferimenti a risorse dinamiche per impostare <xref:System.Windows.Media.Animation.Storyboard> o i valori delle proprietà di animazione. Poiché tutti gli elementi all'interno di un <xref:System.Windows.Controls.ControlTemplate> deve essere thread-safe, e il sistema di temporizzazione deve <xref:System.Windows.Freezable.Freeze%2A> <xref:System.Windows.Media.Animation.Storyboard> oggetti in modo thread-safe. Oggetto <xref:System.Windows.Media.Animation.Storyboard> non può essere bloccato se è o le sequenze temporali figlio contengono espressioni di associazione dati o riferimenti a risorse dinamiche. Per ulteriori informazioni sul blocco e altri su <xref:System.Windows.Freezable> funzionalità, vedere il [panoramica sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
-   In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], è possibile dichiarare i gestori eventi per <xref:System.Windows.Media.Animation.Storyboard> o eventi di animazione.  
  
 Per un esempio che illustra come definire uno storyboard in un <xref:System.Windows.Controls.ControlTemplate>, vedere il [Animate in ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md) esempio.  
  
<a name="animateWhenAPropertyValueChanges"></a>   
## <a name="animate-when-a-property-value-changes"></a>Aggiungere un'animazione quando viene modificato il valore di una proprietà  
 Negli stili e nei modelli di controllo è possibile usare oggetti Trigger per avviare uno storyboard quando una proprietà viene modificata. Per esempi, vedere [Trigger animazione quando una proprietà cambia un valore di](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md) e [Animate in ControlTemplate](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-in-a-controltemplate.md).  
  
 Le animazioni applicate tramite proprietà <xref:System.Windows.Trigger> oggetti si comportano in modo più complesso rispetto a <xref:System.Windows.EventTrigger> animazioni o a quelle avviate tramite <xref:System.Windows.Media.Animation.Storyboard> metodi.  Essi "handoff" con le animazioni definite da altri <xref:System.Windows.Trigger> oggetti, ma possono essere combinate con <xref:System.Windows.EventTrigger> e le animazioni basate su metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Cenni preliminari sulle tecniche di animazione delle proprietà](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
