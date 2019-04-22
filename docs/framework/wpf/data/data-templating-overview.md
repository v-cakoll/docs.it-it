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
ms.openlocfilehash: 98fff9ba84f386e93549fa94fe84f7b2b0fff5fd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097551"
---
# <a name="data-templating-overview"></a>Cenni preliminari sui modelli di dati
Il modello di applicazione di modelli di dati WPF offre una notevole flessibilità per definire la presentazione dei dati. I controlli WPF dispongono di funzionalità incorporate per supportare la personalizzazione della presentazione dei dati. In questo argomento viene innanzitutto illustrato come definire un <xref:System.Windows.DataTemplate> e successivamente presenta altre funzionalità di creazione di modelli dati, ad esempio la selezione di modelli basato su logica personalizzata e il supporto per la visualizzazione di dati gerarchici.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento è incentrato sulle funzionalità di applicazione dei modelli di dati e non è un'introduzione ai concetti di data binding. Per informazioni sui concetti di data binding, vedere [Panoramica sul data binding](data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate> riguarda la presentazione dei dati ed è una delle numerose funzionalità offerte dal modello di stili e modelli WPF. Per un'introduzione del modello di stili e modelli WPF, ad esempio come usare un <xref:System.Windows.Style> per impostare le proprietà nei controlli, vedere la [Styling and Templating](../controls/styling-and-templating.md) argomento.  
  
 Inoltre, è importante comprendere `Resources`, che sono essenzialmente ciò che consentono ad esempio gli oggetti <xref:System.Windows.Style> e <xref:System.Windows.DataTemplate> essere riutilizzati. Per altre informazioni sulle risorse, vedere [Risorse XAML](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Nozioni fondamentali sui modelli di dati  
  
 Per illustrare il motivo <xref:System.Windows.DataTemplate> è importante, di seguito viene illustrato un esempio di associazione dati. In questo esempio, è necessario un <xref:System.Windows.Controls.ListBox> che è associato a un elenco di `Task` oggetti. Ogni oggetto `Task` dispone di un `TaskName` (stringa), una `Description` (stringa), una `Priority` (intero) e un tipo di proprietà `TaskType`, vale a dire una `Enum` con valori `Home` e `Work`.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Senza un DataTemplate  
 Senza una <xref:System.Windows.DataTemplate>, il <xref:System.Windows.Controls.ListBox> attualmente ha un aspetto simile al seguente:  
  
 ![Schermata di esempio Data templating](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Ciò che accade è che senza istruzioni specifiche, il <xref:System.Windows.Controls.ListBox> chiama per impostazione predefinita `ToString` durante il tentativo di visualizzare gli oggetti nella raccolta. Di conseguenza, se il `Task` esegue l'override dell'oggetto di `ToString` metodo, il <xref:System.Windows.Controls.ListBox> consente di visualizzare la rappresentazione di stringa di ogni oggetto di origine nella raccolta sottostante.  
  
 Se ad esempio la classe `Task` esegue l'override del metodo `ToString` in questo modo, dove `name` è il campo della proprietà `TaskName`:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 Il <xref:System.Windows.Controls.ListBox> simile al seguente:  
  
 ![Schermata di esempio Data templating](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Questa soluzione risulta tuttavia limitante e poco flessibile. Se si esegue il binding a dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], non sarà inoltre possibile eseguire l'override di `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Definizione di DataTemplate semplice  
 La soluzione consiste nel definire un <xref:System.Windows.DataTemplate>. Un modo per farlo consiste nell'impostare il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà del <xref:System.Windows.Controls.ListBox> a un <xref:System.Windows.DataTemplate>. Quello specificato nel <xref:System.Windows.DataTemplate> diventa la struttura visiva dell'oggetto dati. Nell'esempio <xref:System.Windows.DataTemplate> è piuttosto semplice. Vengono fornite istruzioni che ogni elemento viene visualizzato come tre <xref:System.Windows.Controls.TextBlock> elementi all'interno di un <xref:System.Windows.Controls.StackPanel>. Ciascuna <xref:System.Windows.Controls.TextBlock> elemento è associato a una proprietà del `Task` classe.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 I dati sottostanti degli esempi di questo argomento sono una raccolta di oggetti [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. Se si esegue il binding a dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], i concetti fondamentali sono gli stessi, ma con una piccola differenza sintattica. Ad esempio, anziché avere `Path=TaskName`, è necessario impostare <xref:System.Windows.Data.Binding.XPath%2A> a `@TaskName` (se `TaskName` è un attributo del [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] nodo).  
  
 A questo punto il <xref:System.Windows.Controls.ListBox> simile al seguente:  
  
 ![Schermata di esempio Data templating](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Creazione di DataTemplate come risorsa  
 Nell'esempio precedente, è stato definito il <xref:System.Windows.DataTemplate> inline. È più comune definirlo nella sezione delle risorse perché qui diventa un oggetto riutilizzabile, come illustrato nell'esempio seguente:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 È possibile a questo punto usare `myTaskTemplate` come risorsa, come illustrato nell'esempio seguente:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 In quanto `myTaskTemplate` è una risorsa, è possibile ora usare sugli altri controlli che hanno una proprietà che accetta un <xref:System.Windows.DataTemplate> tipo. Come mostrato sopra, per <xref:System.Windows.Controls.ItemsControl> oggetti, ad esempio il <xref:System.Windows.Controls.ListBox>, è il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà. Per la <xref:System.Windows.Controls.ContentControl> oggetti, è il <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> proprietà.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>Proprietà DataType  
 Il <xref:System.Windows.DataTemplate> classe ha un <xref:System.Windows.DataTemplate.DataType%2A> proprietà che è molto simile al <xref:System.Windows.Style.TargetType%2A> proprietà del <xref:System.Windows.Style> classe. Pertanto, anziché specificare una `x:Key` per il <xref:System.Windows.DataTemplate> nell'esempio precedente, è possibile eseguire le operazioni seguenti:  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Ciò <xref:System.Windows.DataTemplate> viene applicato automaticamente a tutti `Task` oggetti. Si noti che in questo caso il valore di `x:Key` è impostato in modo implicito. Pertanto, se si assegna questo <xref:System.Windows.DataTemplate> un' `x:Key` valore, si esegue l'override implicito `x:Key` e il <xref:System.Windows.DataTemplate> non verrà applicato automaticamente.  
  
 Quando si associa un <xref:System.Windows.Controls.ContentControl> a una raccolta di `Task` oggetti, il <xref:System.Windows.Controls.ContentControl> non usa il codice precedente <xref:System.Windows.DataTemplate> automaticamente. Infatti, l'associazione in un <xref:System.Windows.Controls.ContentControl> richiede più informazioni per capire se si desidera associare a un'intera raccolta o a singoli oggetti. Se il <xref:System.Windows.Controls.ContentControl> tiene traccia della selezione di un <xref:System.Windows.Controls.ItemsControl> tipo, è possibile impostare il <xref:System.Windows.Data.Binding.Path%2A> proprietà della <xref:System.Windows.Controls.ContentControl> associazione a "`/`" per indicare che si è interessati all'elemento corrente. Per un esempio, vedere [Procedura: Eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). In caso contrario, è necessario specificare il <xref:System.Windows.DataTemplate> in modo esplicito, impostando il <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> proprietà.  
  
 Il <xref:System.Windows.DataTemplate.DataType%2A> proprietà è particolarmente utile quando si dispone di un <xref:System.Windows.Data.CompositeCollection> di diversi tipi di oggetti dati. Per un esempio, vedere [Procedura: Implementare un oggetto CompositeCollection](how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Aggiunta di altri elementi al DataTemplate  
 I dati presentano a questo punto le informazioni necessarie. È tuttavia possibile migliorarne ulteriormente la presentazione. È possibile migliorare sulla presentazione preparata e aggiungendo un <xref:System.Windows.Controls.Border>, una <xref:System.Windows.Controls.Grid>e alcuni <xref:System.Windows.Controls.TextBlock> gli elementi che descrivono i dati da visualizzare.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 La schermata seguente mostra le <xref:System.Windows.Controls.ListBox> con questa modifica <xref:System.Windows.DataTemplate>:  
  
 ![Schermata di esempio Data templating](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 È possibile impostare <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> al <xref:System.Windows.HorizontalAlignment.Stretch> nel <xref:System.Windows.Controls.ListBox> per assicurarsi che la larghezza degli elementi occupi l'intero spazio:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Con il <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> impostata su <xref:System.Windows.HorizontalAlignment.Stretch>, il <xref:System.Windows.Controls.ListBox> ora ha un aspetto simile al seguente:  
  
 ![Schermata di esempio Data templating](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Utilizzo di DataTrigger per applicare i valori di proprietà  
 La presentazione corrente non indica se un `Task` è un'attività domestica o di ufficio. Si tenga a mente che l'oggetto `Task` dispone di una proprietà `TaskType` di tipo `TaskType`, che è un'enumerazione con valori `Home` e `Work`.  
  
 Nell'esempio seguente, il <xref:System.Windows.DataTrigger> imposta il <xref:System.Windows.Controls.Border.BorderBrush%2A> dell'elemento denominato `border` a `Yellow` se la `TaskType` è di proprietà `TaskType.Home`.  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 L'applicazione presenta ora l'aspetto seguente. Le attività domestiche hanno un bordo giallo mentre le attività di ufficio hanno un bordo azzurro:  
  
 ![Schermata di esempio Data templating](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 In questo esempio il <xref:System.Windows.DataTrigger> Usa un <xref:System.Windows.Setter> per impostare un valore della proprietà. Le classi trigger dispongono inoltre il <xref:System.Windows.TriggerBase.EnterActions%2A> e <xref:System.Windows.TriggerBase.ExitActions%2A> proprietà che consentono di avviare un set di azioni, ad esempio le animazioni. Inoltre, è inoltre disponibile un <xref:System.Windows.MultiDataTrigger> classe che consente di applicare le modifiche basate su più valori di proprietà con associazione a dati.  
  
 Un modo alternativo per ottenere lo stesso risultato consiste nell'associare il <xref:System.Windows.Controls.Border.BorderBrush%2A> proprietà per il `TaskType` proprietà e utilizzare un convertitore di valori per restituire il colore di base il `TaskType` valore. La creazione dell'effetto precedente tramite un convertitore è una soluzione leggermente più efficiente in termini di prestazioni. La creazione di un convertitore personalizzato offre inoltre maggiore flessibilità poiché consente di usare una logica personalizzata. La scelta della tecnica dipende in definitiva dallo scenario e le preferenze personali. Per informazioni su come scrivere un convertitore di tipi, vedere <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Elementi di un DataTemplate  

Nell'esempio precedente, è stato inserito un trigger all'interno di <xref:System.Windows.DataTemplate> utilizzando il <xref:System.Windows.DataTemplate>.<xref:System.Windows.DataTemplate.Triggers%2A> . Il <xref:System.Windows.Setter> del trigger imposta il valore di una proprietà di un elemento (il <xref:System.Windows.Controls.Border> elemento) che si trova all'interno di <xref:System.Windows.DataTemplate>. Tuttavia, se le proprietà che il `Setters` è preoccupati non sono proprietà degli elementi presenti all'interno dell'oggetto <xref:System.Windows.DataTemplate>, potrebbe essere più adatto impostare le proprietà usando un <xref:System.Windows.Style> per il <xref:System.Windows.Controls.ListBoxItem> classe (se il controllo si esegue l'associazione è un <xref:System.Windows.Controls.ListBox>). Ad esempio, se si desidera che il <xref:System.Windows.Trigger> animare il <xref:System.Windows.UIElement.Opacity%2A> valore dell'elemento quando il mouse punta a un elemento, si definiscono trigger all'interno di un <xref:System.Windows.Controls.ListBoxItem> stile. Per un esempio, vedere [Introduction to Styling and Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) (Introduzione all'esempio di applicazione di stili e modelli).
  
 In generale, tenere presente che il <xref:System.Windows.DataTemplate> viene applicata a ogni oggetto generato <xref:System.Windows.Controls.ListBoxItem> (per altre informazioni su come e dove viene effettivamente applicato, vedere il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> pagina.). Il <xref:System.Windows.DataTemplate> riguarda solo la presentazione e l'aspetto degli oggetti dati. Nella maggior parte dei casi, tutti gli altri aspetti della presentazione, ad esempio aspetto di un elemento simile a quando viene selezionata o il <xref:System.Windows.Controls.ListBox> disposto gli elementi non appartengono nella definizione di un <xref:System.Windows.DataTemplate>. Per un esempio, vedere la sezione [Applicazione di stili e modelli di ItemsControl](#DataTemplating_ItemsControl).  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Scelta di un DataTemplate in base alle proprietà dell'oggetto dati  
 Nella sezione [Proprietà DataType](#Styling_DataType) è stato spiegato che è possibile definire modelli di dati diversi per oggetti dati diversi. Che è particolarmente utile quando si dispone di un <xref:System.Windows.Data.CompositeCollection> di raccolte con elementi di tipi diversi o tipi diversi. Nel [utilizzo di DataTrigger per applicare i valori delle proprietà](#DataTrigger_to_Apply_Property_Values) sezione, è stato illustrato che se si dispone di una raccolta dello stesso tipo di oggetti dati è possibile creare un <xref:System.Windows.DataTemplate> e quindi usare i trigger per applicare le modifiche basate sui valori delle proprietà ogni oggetto dati. I trigger consentono tuttavia di applicare valori delle proprietà o avviare animazioni ma non offrono la flessibilità necessaria per ricostruire la struttura degli oggetti dati. Alcuni scenari potrebbe essere necessario creare un altro <xref:System.Windows.DataTemplate> per i dati di oggetti che sono dello stesso tipo ma hanno proprietà diverse.  
  
 Quando ad esempio un oggetto `Task` ha un valore `Priority` di `1`, è possibile conferirgli un aspetto completamente diverso in modo che funga da avviso. In tal caso, si crea una <xref:System.Windows.DataTemplate> per la visualizzazione della priorità elevata `Task` oggetti. È possibile aggiungere il codice seguente <xref:System.Windows.DataTemplate> alla sezione delle risorse:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Si noti che questo esempio viene usato il <xref:System.Windows.DataTemplate>.<xref:System.Windows.FrameworkTemplate.Resources%2A> . Le risorse definite in questa sezione sono condivise dagli elementi all'interno di <xref:System.Windows.DataTemplate>.  
  
 Per fornire la logica per scegliere quali <xref:System.Windows.DataTemplate> da usare in base il `Priority` valore dell'oggetto dati, creare una sottoclasse di <xref:System.Windows.Controls.DataTemplateSelector> ed eseguire l'override di <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> (metodo). Nell'esempio seguente, il <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> metodo fornisce la logica per restituire il modello appropriato in base al valore della `Priority` proprietà. Il modello da restituire è disponibile nelle risorse di busta <xref:System.Windows.Window> elemento.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 È quindi possibile dichiarare il `TaskListDataTemplateSelector` come risorsa:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Per usare la risorsa selettore del modello, assegnarla al <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> proprietà del <xref:System.Windows.Controls.ListBox>. Il <xref:System.Windows.Controls.ListBox> chiama il <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> metodo del `TaskListDataTemplateSelector` per ognuno degli elementi nella raccolta sottostante. La chiamata passa l'oggetto dati come parametro di elemento. Il <xref:System.Windows.DataTemplate> restituito dal metodo viene quindi applicato all'oggetto dati.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Con il selettore del modello, il <xref:System.Windows.Controls.ListBox> appare ora come segue:  
  
 ![Schermata di esempio Data templating](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Questa operazione chiude la spiegazione di questo esempio. Per l'esempio completo, vedere [Introduction to Data Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro) (Introduzione a un esempio di applicazione di modello).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Applicazione di stili e modelli a ItemsControl  
 Anche se il <xref:System.Windows.Controls.ItemsControl> non è l'unico tipo di controllo che è possibile usare una <xref:System.Windows.DataTemplate> , è uno scenario molto comune per associare un <xref:System.Windows.Controls.ItemsControl> a una raccolta. Nel [ciò che appartiene a un DataTemplate](#what_belongs_in_datatemplate) sezione è stato illustrato che la definizione di <xref:System.Windows.DataTemplate> deve essere solo in questione con la presentazione dei dati. Per sapere quando non è opportuno usare un <xref:System.Windows.DataTemplate> è importante comprendere le diverse proprietà di stile e il modello fornita dal <xref:System.Windows.Controls.ItemsControl>. L'esempio seguente è progettato per illustrare la funzione di ognuna di queste proprietà. Il <xref:System.Windows.Controls.ItemsControl> in questo esempio è associato allo stesso `Tasks` insieme come nell'esempio precedente. A scopo dimostrativo, gli stili e i modelli in questo esempio sono tutti dichiarati incorporati.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Lo screenshot seguente mostra l'esempio dopo il rendering:  
  
 ![Screenshot dell'esempio di ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Si noti che invece di usare la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, è possibile usare il <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>. Per un esempio, fare riferimento alla sezione precedente. Analogamente, invece di usare la <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>, è possibile usare il <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>.  
  
 Due altre proprietà correlate allo stile del <xref:System.Windows.Controls.ItemsControl> che non vengono visualizzati qui sono <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> e <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Supporto per i dati gerarchici  
 Sono state finora analizzate unicamente le modalità di associazione e di visualizzazione di una raccolta singola. Si dispone talvolta di una raccolta che contiene altre raccolte. Il <xref:System.Windows.HierarchicalDataTemplate> classe è progettata per essere usato con <xref:System.Windows.Controls.HeaderedItemsControl> tipi per visualizzare tali dati. Nell'esempio seguente `ListLeagueList` è un elenco di oggetti `League`. Ogni oggetto `League` ha un `Name` e una raccolta di oggetti `Division`. Ogni `Division` ha un `Name` e una raccolta di oggetti `Team` e ogni oggetto `Team` ha un `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 Nell'esempio viene illustrato che con l'uso di <xref:System.Windows.HierarchicalDataTemplate>, è possibile visualizzare i dati di elenco che contengono altri elenchi. Lo screenshot seguente mostra l'esempio.  
  
 ![Screenshot di esempio HierarchicalDataTemplate](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Vedere anche

- [Data binding](../advanced/optimizing-performance-data-binding.md)
- [Procedura: trovare elementi generati da un oggetto DataTemplate](how-to-find-datatemplate-generated-elements.md)
- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](../controls/gridview-column-header-styles-and-templates-overview.md)
