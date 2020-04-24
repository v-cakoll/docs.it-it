---
title: Cenni preliminari sui modelli di dati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], templates
- binding data [WPF], templates
- templates [WPF], data
- data templates [WPF]
ms.assetid: 0f4d9f8c-0230-4013-bd7b-e8e7fed01b4a
ms.openlocfilehash: b9e55eac1c72cd3deec21754373da4364a7cfed2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646452"
---
# <a name="data-templating-overview"></a>Cenni preliminari sui modelli di dati
Il modello di applicazione di modelli di dati WPF offre una notevole flessibilità per definire la presentazione dei dati. I controlli WPF dispongono di funzionalità incorporate per supportare la personalizzazione della presentazione dei dati. In questo argomento viene <xref:System.Windows.DataTemplate> innanzitutto illustrato come definire un e quindi vengono introdotte altre funzionalità di modelli di dati, ad esempio la selezione di modelli in base alla logica personalizzata e il supporto per la visualizzazione di dati gerarchici.

<a name="Prerequisites"></a>
## <a name="prerequisites"></a>Prerequisiti
 Questo argomento è incentrato sulle funzionalità di applicazione dei modelli di dati e non è un'introduzione ai concetti di data binding. Per informazioni sui concetti di data binding, vedere [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md).

 <xref:System.Windows.DataTemplate>riguarda la presentazione dei dati ed è una delle molte funzionalità fornite dal modello di stile e modelli WPFWPF. Per un'introduzione del modello di applicazione di stili e <xref:System.Windows.Style> modelli WPFWPF, ad esempio come usare un oggetto per impostare proprietà nei controlli, vedere l'argomento [Applicazione di stili e modelli.](../../../desktop-wpf/fundamentals/styles-templates-overview.md)

 Inoltre, è importante comprendere `Resources`, che sono essenzialmente <xref:System.Windows.Style> ciò che consentono oggetti come e <xref:System.Windows.DataTemplate> di essere riutilizzabili. Per altre informazioni sulle risorse, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

<a name="DataTemplating_Basic"></a>
## <a name="data-templating-basics"></a>Nozioni fondamentali sui modelli di dati

 Per dimostrare perché <xref:System.Windows.DataTemplate> è importante, esaminiamo un esempio di associazione dati. In questo esempio, <xref:System.Windows.Controls.ListBox> abbiamo un che è `Task` associato a un elenco di oggetti. Ogni oggetto `Task` dispone di un `TaskName` (stringa), una `Description` (stringa), una `Priority` (intero) e un tipo di proprietà `TaskType`, vale a dire una `Enum` con valori `Home` e `Work`.

 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]

<a name="without_a_datatemplate"></a>
### <a name="without-a-datatemplate"></a>Senza un DataTemplate
 Senza <xref:System.Windows.DataTemplate>un <xref:System.Windows.Controls.ListBox> , il nostro attualmente si presenta così:

 ![Schermata di esempio di modelli di datiData templating sample screenshot](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")

 Quello che sta accadendo è che <xref:System.Windows.Controls.ListBox> senza `ToString` istruzioni specifiche, le chiamate per impostazione predefinita quando si tenta di visualizzare gli oggetti nella raccolta. Pertanto, `Task` se l'oggetto esegue l'override del `ToString` metodo, <xref:System.Windows.Controls.ListBox> quindi visualizza la rappresentazione di stringa di ogni oggetto di origine nella raccolta sottostante.

 Se ad esempio la classe `Task` esegue l'override del metodo `ToString` in questo modo, dove `name` è il campo della proprietà `TaskName`:

 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]

 Poi <xref:System.Windows.Controls.ListBox> il si presenta come il seguente:

 ![Schermata di esempio di modelli di datiData templating sample screenshot](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")

 Questa soluzione risulta tuttavia limitante e poco flessibile. Inoltre, se si esegue l'associazione a dati `ToString`XML, non sarà possibile eseguire l'override di .

<a name="defining_simple_datatemplate"></a>
### <a name="defining-a-simple-datatemplate"></a>Definizione di DataTemplate semplice
 La soluzione consiste <xref:System.Windows.DataTemplate>nel definire un file . Un modo per eseguire questa <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> operazione <xref:System.Windows.Controls.ListBox> consiste <xref:System.Windows.DataTemplate>nell'impostare la proprietà dell'oggetto su un oggetto . Ciò che <xref:System.Windows.DataTemplate> specificato nel file diventa la struttura visiva dell'oggetto dati. Quanto <xref:System.Windows.DataTemplate> segue è abbastanza semplice. Stiamo dando istruzioni che ogni <xref:System.Windows.Controls.TextBlock> elemento appare <xref:System.Windows.Controls.StackPanel>come tre elementi all'interno di un . Ogni <xref:System.Windows.Controls.TextBlock> elemento è associato a `Task` una proprietà della classe.

 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]

 I dati sottostanti per gli esempi in questo argomento sono una raccolta di oggetti CLR. Se si esegue l'associazione a dati XML, i concetti fondamentali sono gli stessi, ma esiste una leggera differenza sintattica. Ad esempio, anziché `Path=TaskName`impostare <xref:System.Windows.Data.Binding.XPath%2A> `@TaskName` su `TaskName` , se è un attributo del nodo XML.

 Ora <xref:System.Windows.Controls.ListBox> il nostro aspetto come il seguente:

 ![Schermata di esempio di modelli di datiData templating sample screenshot](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")

<a name="defining_datatemplate_as_a_resource"></a>
### <a name="creating-the-datatemplate-as-a-resource"></a>Creazione di DataTemplate come risorsa
 Nell'esempio precedente, abbiamo <xref:System.Windows.DataTemplate> definito l'inline. È più comune definirlo nella sezione delle risorse perché qui diventa un oggetto riutilizzabile, come illustrato nell'esempio seguente:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 È possibile a questo punto usare `myTaskTemplate` come risorsa, come illustrato nell'esempio seguente:

 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]

 Poiché `myTaskTemplate` è una risorsa, è ora possibile utilizzarlo in <xref:System.Windows.DataTemplate> altri controlli che dispongono di una proprietà che accetta un tipo. Come illustrato in <xref:System.Windows.Controls.ItemsControl> precedenza, <xref:System.Windows.Controls.ListBox>per gli <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> oggetti , ad esempio , si tratta della proprietà . Per <xref:System.Windows.Controls.ContentControl> gli oggetti, <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> è la proprietà.

<a name="Styling_DataType"></a>
### <a name="the-datatype-property"></a>Proprietà DataType
 La <xref:System.Windows.DataTemplate> classe <xref:System.Windows.DataTemplate.DataType%2A> dispone di una proprietà <xref:System.Windows.Style.TargetType%2A> molto <xref:System.Windows.Style> simile alla proprietà della classe. Pertanto, anziché `x:Key` specificare <xref:System.Windows.DataTemplate> un per l'esempio nell'esempio precedente, è possibile eseguire le operazioni seguenti:

 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]

 Questo <xref:System.Windows.DataTemplate> viene applicato `Task` automaticamente a tutti gli oggetti. Si noti che in questo caso il valore di `x:Key` è impostato in modo implicito. Pertanto, se <xref:System.Windows.DataTemplate> si `x:Key` assegna un valore, `x:Key` si <xref:System.Windows.DataTemplate> esegue l'override di implicito e il non verrà applicato automaticamente.

 Se si associa <xref:System.Windows.Controls.ContentControl> a una `Task` raccolta <xref:System.Windows.Controls.ContentControl> di oggetti, <xref:System.Windows.DataTemplate> l'oggetto non utilizza automaticamente quanto sopra. Ciò è dovuto <xref:System.Windows.Controls.ContentControl> al fatto che l'associazione in un oggetto richiede ulteriori informazioni per distinguere se si desidera eseguire l'associazione a un'intera raccolta o ai singoli oggetti. Se <xref:System.Windows.Controls.ContentControl> si tiene traccia <xref:System.Windows.Controls.ItemsControl> della selezione di <xref:System.Windows.Data.Binding.Path%2A> un tipo, è possibile impostare la proprietà dell'associazione <xref:System.Windows.Controls.ContentControl> su "`/`" per indicare che si è interessati all'elemento corrente. Per un esempio, vedere [Procedura: Eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). In caso contrario, <xref:System.Windows.DataTemplate> è necessario <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> specificare l'oggetto in modo esplicito impostando la proprietà .

 La <xref:System.Windows.DataTemplate.DataType%2A> proprietà è particolarmente utile <xref:System.Windows.Data.CompositeCollection> quando si dispone di diversi tipi di oggetti dati. Per un esempio, vedere [Procedura: Implementare un oggetto CompositeCollection](how-to-implement-a-compositecollection.md).

<a name="adding_more_to_datatemplate"></a>
## <a name="adding-more-to-the-datatemplate"></a>Aggiunta di altri elementi al DataTemplate
 I dati presentano a questo punto le informazioni necessarie. È tuttavia possibile migliorarne ulteriormente la presentazione. È possibile migliorare la presentazione <xref:System.Windows.Controls.Border>aggiungendo <xref:System.Windows.Controls.Grid>un , <xref:System.Windows.Controls.TextBlock> un , e alcuni elementi che descrivono i dati visualizzati.

 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 La seguente schermata mostra il <xref:System.Windows.Controls.ListBox> con questa modifica <xref:System.Windows.DataTemplate>:

 ![Schermata di esempio di modelli di datiData templating sample screenshot](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")

 Possiamo <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> impostare <xref:System.Windows.HorizontalAlignment.Stretch> su <xref:System.Windows.Controls.ListBox> on on per assicurarsi che la larghezza degli elementi occupa l'intero spazio:

 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]

 Con <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> la proprietà <xref:System.Windows.HorizontalAlignment.Stretch>impostata su , il <xref:System.Windows.Controls.ListBox> punto ora è simile al seguente:

 ![Schermata di esempio di modelli di datiData templating sample screenshot](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")

<a name="DataTrigger_to_Apply_Property_Values"></a>
### <a name="use-datatriggers-to-apply-property-values"></a>Utilizzo di DataTrigger per applicare i valori di proprietà
 La presentazione corrente non indica se un `Task` è un'attività domestica o di ufficio. Si tenga a mente che l'oggetto `Task` dispone di una proprietà `TaskType` di tipo `TaskType`, che è un'enumerazione con valori `Home` e `Work`.

 Nell'esempio riportato <xref:System.Windows.DataTrigger> di <xref:System.Windows.Controls.Border.BorderBrush%2A> seguito, `border` l'oggetto `TaskType` imposta `TaskType.Home`l'elemento denominato su `Yellow` se la proprietà è .

 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 L'applicazione presenta ora l'aspetto seguente. Le attività domestiche hanno un bordo giallo mentre le attività di ufficio hanno un bordo azzurro:

 ![Schermata di esempio di modelli di datiData templating sample screenshot](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")

 In questo <xref:System.Windows.DataTrigger> esempio <xref:System.Windows.Setter> viene utilizzato un per impostare un valore della proprietà. Le classi trigger <xref:System.Windows.TriggerBase.EnterActions%2A> dispongono anche delle proprietà e <xref:System.Windows.TriggerBase.ExitActions%2A> che consentono di avviare un set di azioni, ad esempio animazioni. È inoltre disponibile una <xref:System.Windows.MultiDataTrigger> classe che consente di applicare le modifiche in base a più valori di proprietà con associazione a dati.

 Un modo alternativo per ottenere lo <xref:System.Windows.Controls.Border.BorderBrush%2A> stesso effetto `TaskType` consiste nell'associare la proprietà alla `TaskType` proprietà e utilizzare un convertitore di valori per restituire il colore in base al valore. La creazione dell'effetto precedente tramite un convertitore è una soluzione leggermente più efficiente in termini di prestazioni. La creazione di un convertitore personalizzato offre inoltre maggiore flessibilità poiché consente di usare una logica personalizzata. La scelta della tecnica dipende in definitiva dallo scenario e le preferenze personali. Per informazioni su come scrivere <xref:System.Windows.Data.IValueConverter>un convertitore, vedere .

<a name="what_belongs_in_datatemplate"></a>
### <a name="what-belongs-in-a-datatemplate"></a>Elementi di un DataTemplate

Nell'esempio precedente, il trigger <xref:System.Windows.DataTemplate> è <xref:System.Windows.DataTemplate.Triggers%2A?displayProperty=nameWithType> stato inserito all'interno della proprietà using . Il <xref:System.Windows.Setter> trigger imposta il valore di una proprietà <xref:System.Windows.Controls.Border> di un elemento <xref:System.Windows.DataTemplate>(l'elemento) che si trova all'interno di . Tuttavia, se le `Setters` proprietà che si occupano non sono <xref:System.Windows.DataTemplate>proprietà di elementi all'interno dell'oggetto corrente , potrebbe essere più adatto impostare le proprietà utilizzando un <xref:System.Windows.Style> oggetto che è per la <xref:System.Windows.Controls.ListBoxItem> classe (se il controllo che si sta associando è un <xref:System.Windows.Controls.ListBox>). Ad esempio, se <xref:System.Windows.Trigger> si desidera <xref:System.Windows.UIElement.Opacity%2A> animare il valore dell'elemento quando un mouse <xref:System.Windows.Controls.ListBoxItem> punta a un elemento, si definiscono i trigger all'interno di uno stile. Per un esempio, vedere [Introduction to Styling and Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) (Introduzione all'esempio di applicazione di stili e modelli).

 In generale, tenere presente <xref:System.Windows.DataTemplate> che l'oggetto viene <xref:System.Windows.Controls.ListBoxItem> applicato a ciascuno dei generati (per ulteriori <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> informazioni su come e dove viene effettivamente applicato, vedere la pagina.). L'utente <xref:System.Windows.DataTemplate> riguarda solo la presentazione e l'aspetto degli oggetti dati. Nella maggior parte dei casi, tutti gli altri aspetti della presentazione, ad <xref:System.Windows.Controls.ListBox> esempio l'aspetto di un elemento quando <xref:System.Windows.DataTemplate>viene selezionato o il modo in cui gli elementi vengono visualizzati, non appartengono alla definizione di un oggetto . Per un esempio, vedere la sezione [Applicazione di stili e modelli di ItemsControl](#DataTemplating_ItemsControl).

<a name="Styling_StyleSelection"></a>
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Scelta di un DataTemplate in base alle proprietà dell'oggetto dati
 Nella sezione [Proprietà DataType](#Styling_DataType) è stato spiegato che è possibile definire modelli di dati diversi per oggetti dati diversi. Ciò è particolarmente utile <xref:System.Windows.Data.CompositeCollection> quando si dispone di un di tipi diversi o raccolte con elementi di tipi diversi. Nella sezione [Usare DataTrigger per applicare](#DataTrigger_to_Apply_Property_Values) valori di proprietà è stato illustrato che se si dispone <xref:System.Windows.DataTemplate> di una raccolta dello stesso tipo di oggetti dati è possibile creare un oggetto e quindi utilizzare i trigger per applicare le modifiche in base ai valori delle proprietà di ogni oggetto dati. I trigger consentono tuttavia di applicare valori delle proprietà o avviare animazioni ma non offrono la flessibilità necessaria per ricostruire la struttura degli oggetti dati. Alcuni scenari potrebbero richiedere la <xref:System.Windows.DataTemplate> creazione di un elemento diverso per gli oggetti dati dello stesso tipo ma con proprietà diverse.

 Quando ad esempio un oggetto `Task` ha un valore `Priority` di `1`, è possibile conferirgli un aspetto completamente diverso in modo che funga da avviso. In tal caso, <xref:System.Windows.DataTemplate> si crea un per `Task` la visualizzazione degli oggetti ad alta priorità. Aggiungiamo quanto segue <xref:System.Windows.DataTemplate> alla sezione delle risorse:

 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]

In questo esempio viene utilizzata la proprietà [DataTemplate.Resources.](xref:System.Windows.FrameworkTemplate.Resources%2A) Le risorse definite in tale sezione <xref:System.Windows.DataTemplate>sono condivise dagli elementi all'interno del file .

 Per fornire la <xref:System.Windows.DataTemplate> logica per scegliere `Priority` quale usare in base al <xref:System.Windows.Controls.DataTemplateSelector> valore dell'oggetto dati, creare una sottoclasse di ed eseguire l'override del <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> metodo. Nell'esempio seguente, <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> il metodo fornisce la logica per restituire `Priority` il modello appropriato in base al valore della proprietà. Il modello da restituire si trova nelle risorse <xref:System.Windows.Window> dell'elemento avvolgente.

 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]

 È quindi possibile dichiarare il `TaskListDataTemplateSelector` come risorsa:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 Per utilizzare la risorsa selettore di <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> modello, <xref:System.Windows.Controls.ListBox>assegnarla alla proprietà dell'oggetto . Il <xref:System.Windows.Controls.ListBox> chiama <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> il `TaskListDataTemplateSelector` metodo di for ciascuno degli elementi nella raccolta sottostante. La chiamata passa l'oggetto dati come parametro di elemento. L'oggetto <xref:System.Windows.DataTemplate> restituito dal metodo viene quindi applicato a tale oggetto dati.

 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]

 Con il selettore del <xref:System.Windows.Controls.ListBox> modello in posizione, il now appare come segue:

 ![Schermata di esempio di modelli di datiData templating sample screenshot](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")

Questa operazione chiude la spiegazione di questo esempio. Per l'esempio completo, vedere [Introduction to Data Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro) (Introduzione a un esempio di applicazione di modello).

<a name="DataTemplating_ItemsControl"></a>
## <a name="styling-and-templating-an-itemscontrol"></a>Applicazione di stili e modelli a ItemsControl
 Anche se <xref:System.Windows.Controls.ItemsControl> l'è non l'unico <xref:System.Windows.DataTemplate> tipo di controllo che è possibile <xref:System.Windows.Controls.ItemsControl> utilizzare un con, è uno scenario molto comune per associare un a una raccolta. Nella sezione [Cosa appartiene a un DataTemplate](#what_belongs_in_datatemplate) <xref:System.Windows.DataTemplate> abbiamo discusso che la definizione di your deve riguardare solo la presentazione dei dati. Per sapere quando non è adatto <xref:System.Windows.DataTemplate> utilizzare un è importante comprendere le diverse <xref:System.Windows.Controls.ItemsControl>proprietà di stile e modello fornite dal . L'esempio seguente è progettato per illustrare la funzione di ognuna di queste proprietà. L'oggetto <xref:System.Windows.Controls.ItemsControl> in questo esempio `Tasks` è associato alla stessa raccolta dell'esempio precedente. A scopo dimostrativo, gli stili e i modelli in questo esempio sono tutti dichiarati incorporati.

 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]

 Lo screenshot seguente mostra l'esempio dopo il rendering:

 ![Screenshot di esempio ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")

 Si noti che <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>anziché utilizzare <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>il , è possibile utilizzare il file . Per un esempio, fare riferimento alla sezione precedente. Analogamente, invece <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>di utilizzare il , <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>è possibile utilizzare il file .

 Altre due proprietà relative <xref:System.Windows.Controls.ItemsControl> allo stile dell'oggetto che non sono illustrate di seguito sono <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> e <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.

<a name="DataTemplating_HeirarchicalDataTemplate"></a>
## <a name="support-for-hierarchical-data"></a>Supporto per i dati gerarchici
 Sono state finora analizzate unicamente le modalità di associazione e di visualizzazione di una raccolta singola. Si dispone talvolta di una raccolta che contiene altre raccolte. La <xref:System.Windows.HierarchicalDataTemplate> classe è progettata <xref:System.Windows.Controls.HeaderedItemsControl> per essere utilizzata con i tipi per visualizzare tali dati. Nell'esempio seguente `ListLeagueList` è un elenco di oggetti `League`. Ogni oggetto `League` ha un `Name` e una raccolta di oggetti `Division`. Ogni `Division` ha un `Name` e una raccolta di oggetti `Team` e ogni oggetto `Team` ha un `Name`.

 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]

 Nell'esempio viene illustrato <xref:System.Windows.HierarchicalDataTemplate>che con l'utilizzo di , è possibile visualizzare facilmente i dati di elenco che contengono altri elenchi. Lo screenshot seguente mostra l'esempio.

 ![Schermata di esempio HierarchicalDataTemplate](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")

## <a name="see-also"></a>Vedere anche

- [Associazione dati](../advanced/optimizing-performance-data-binding.md)
- [Trova elementi generati da DataTemplate](how-to-find-datatemplate-generated-elements.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](../controls/gridview-column-header-styles-and-templates-overview.md)
