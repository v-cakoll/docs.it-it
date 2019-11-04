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
ms.openlocfilehash: d088342a08076c69b34f6c3d39dce076cb3890d4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460044"
---
# <a name="data-templating-overview"></a>Cenni preliminari sui modelli di dati
Il modello di applicazione di modelli di dati WPF offre una notevole flessibilità per definire la presentazione dei dati. I controlli WPF dispongono di funzionalità incorporate per supportare la personalizzazione della presentazione dei dati. In questo argomento viene illustrato innanzitutto come definire un <xref:System.Windows.DataTemplate> e quindi vengono introdotte altre funzionalità di creazione di modelli di dati, ad esempio la selezione di modelli basati sulla logica personalizzata e il supporto per la visualizzazione di dati gerarchici.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 Questo argomento è incentrato sulle funzionalità di applicazione dei modelli di dati e non è un'introduzione ai concetti di data binding. Per informazioni sui concetti di data binding, vedere [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate> riguarda la presentazione dei dati ed è una delle numerose funzionalità fornite dal modello di applicazione di stili e modelli WPF. Per un'introduzione al modello di applicazione di stili e modelli WPF, ad esempio come usare un <xref:System.Windows.Style> per impostare le proprietà nei controlli, vedere l'argomento relativo allo [stile e](../controls/styling-and-templating.md) alla creazione di modelli.  
  
 Inoltre, è importante comprendere `Resources`, che sono essenzialmente quelli che consentono a oggetti quali <xref:System.Windows.Style> e <xref:System.Windows.DataTemplate> riutilizzabili. Per altre informazioni sulle risorse, vedere [Risorse XAML](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Nozioni fondamentali sui modelli di dati  
  
 Per illustrare il motivo per cui <xref:System.Windows.DataTemplate> è importante, esaminiamo un data binding esempio. In questo esempio è presente un <xref:System.Windows.Controls.ListBox> associato a un elenco di `Task` oggetti. Ogni oggetto `Task` dispone di un `TaskName` (stringa), una `Description` (stringa), una `Priority` (intero) e un tipo di proprietà `TaskType`, vale a dire una `Enum` con valori `Home` e `Work`.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Senza un DataTemplate  
 Senza una <xref:System.Windows.DataTemplate>, il <xref:System.Windows.Controls.ListBox> attualmente è simile al seguente:  
  
 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Ciò che accade è che senza istruzioni specifiche, il <xref:System.Windows.Controls.ListBox> per impostazione predefinita chiama `ToString` quando si tenta di visualizzare gli oggetti nella raccolta. Se pertanto l'oggetto `Task` esegue l'override del metodo `ToString`, il <xref:System.Windows.Controls.ListBox> Visualizza la rappresentazione di stringa di ogni oggetto di origine nella raccolta sottostante.  
  
 Se ad esempio la classe `Task` esegue l'override del metodo `ToString` in questo modo, dove `name` è il campo della proprietà `TaskName`:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 Il <xref:System.Windows.Controls.ListBox> sarà quindi simile al seguente:  
  
 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Questa soluzione risulta tuttavia limitante e poco flessibile. Se si esegue il binding a dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], non sarà inoltre possibile eseguire l'override di `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Definizione di DataTemplate semplice  
 La soluzione consiste nel definire un <xref:System.Windows.DataTemplate>. Un modo per eseguire questa operazione consiste nell'impostare la proprietà <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> del <xref:System.Windows.Controls.ListBox> su un <xref:System.Windows.DataTemplate>. Gli elementi specificati nel <xref:System.Windows.DataTemplate> diventano la struttura visiva dell'oggetto dati. Il <xref:System.Windows.DataTemplate> seguente è piuttosto semplice. Vengono fornite istruzioni che ogni elemento viene visualizzato come tre elementi <xref:System.Windows.Controls.TextBlock> all'interno di un <xref:System.Windows.Controls.StackPanel>. Ogni elemento <xref:System.Windows.Controls.TextBlock> viene associato a una proprietà della classe `Task`.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 I dati sottostanti per gli esempi in questo argomento sono una raccolta di oggetti CLR. Se si esegue il binding a dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], i concetti fondamentali sono gli stessi, ma con una piccola differenza sintattica. Ad esempio, anziché avere `Path=TaskName`, è necessario impostare <xref:System.Windows.Data.Binding.XPath%2A> su `@TaskName` (se `TaskName` è un attributo del nodo [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]).  
  
 Il <xref:System.Windows.Controls.ListBox> è ora simile al seguente:  
  
 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Creazione di DataTemplate come risorsa  
 Nell'esempio precedente è stato definito il <xref:System.Windows.DataTemplate> inline. È più comune definirlo nella sezione delle risorse perché qui diventa un oggetto riutilizzabile, come illustrato nell'esempio seguente:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 È possibile a questo punto usare `myTaskTemplate` come risorsa, come illustrato nell'esempio seguente:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Poiché `myTaskTemplate` è una risorsa, è ora possibile utilizzarla in altri controlli che dispongono di una proprietà che accetta un tipo di <xref:System.Windows.DataTemplate>. Come illustrato sopra, per <xref:System.Windows.Controls.ItemsControl> oggetti, ad esempio il <xref:System.Windows.Controls.ListBox>, si tratta della proprietà <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>. Per <xref:System.Windows.Controls.ContentControl> oggetti, è la proprietà <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>Proprietà DataType  
 La classe <xref:System.Windows.DataTemplate> dispone di una proprietà <xref:System.Windows.DataTemplate.DataType%2A> molto simile alla proprietà <xref:System.Windows.Style.TargetType%2A> della classe <xref:System.Windows.Style>. Quindi, invece di specificare un `x:Key` per l'<xref:System.Windows.DataTemplate> nell'esempio precedente, è possibile eseguire le operazioni seguenti:  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Questo <xref:System.Windows.DataTemplate> viene applicato automaticamente a tutti gli oggetti `Task`. Si noti che in questo caso il valore di `x:Key` è impostato in modo implicito. Se pertanto si assegna questa <xref:System.Windows.DataTemplate> un valore di `x:Key`, si esegue l'override del `x:Key` implicito e il <xref:System.Windows.DataTemplate> non verrebbe applicato automaticamente.  
  
 Se si associa un <xref:System.Windows.Controls.ContentControl> a una raccolta di oggetti `Task`, il <xref:System.Windows.Controls.ContentControl> non utilizzerà il <xref:System.Windows.DataTemplate> precedente automaticamente. Ciò è dovuto al fatto che l'associazione in un <xref:System.Windows.Controls.ContentControl> necessita di ulteriori informazioni per distinguere se si desidera eseguire il binding a un'intera raccolta o a singoli oggetti. Se il <xref:System.Windows.Controls.ContentControl> tiene traccia della selezione di un tipo di <xref:System.Windows.Controls.ItemsControl>, è possibile impostare la proprietà <xref:System.Windows.Data.Binding.Path%2A> dell'associazione <xref:System.Windows.Controls.ContentControl> su "`/`" per indicare che si è interessati all'elemento corrente. Per un esempio, vedere [Procedura: Eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). In caso contrario, è necessario specificare il <xref:System.Windows.DataTemplate> in modo esplicito impostando la proprietà <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>.  
  
 La proprietà <xref:System.Windows.DataTemplate.DataType%2A> è particolarmente utile quando si dispone di un <xref:System.Windows.Data.CompositeCollection> di diversi tipi di oggetti dati. Per un esempio, vedere [Procedura: Implementare un oggetto CompositeCollection](how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Aggiunta di altri elementi al DataTemplate  
 I dati presentano a questo punto le informazioni necessarie. È tuttavia possibile migliorarne ulteriormente la presentazione. Per migliorare la presentazione, è necessario aggiungere un <xref:System.Windows.Controls.Border>, una <xref:System.Windows.Controls.Grid>e alcuni elementi <xref:System.Windows.Controls.TextBlock> che descrivono i dati visualizzati.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 Lo screenshot seguente mostra la <xref:System.Windows.Controls.ListBox> con questa <xref:System.Windows.DataTemplate>modificata:  
  
 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 È possibile impostare <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> su <xref:System.Windows.HorizontalAlignment.Stretch> nel <xref:System.Windows.Controls.ListBox> per assicurarsi che la larghezza degli elementi occupa l'intero spazio:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Con la proprietà <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> impostata su <xref:System.Windows.HorizontalAlignment.Stretch>, il <xref:System.Windows.Controls.ListBox> ora ha un aspetto simile al seguente:  
  
 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Utilizzo di DataTrigger per applicare i valori di proprietà  
 La presentazione corrente non indica se un `Task` è un'attività domestica o di ufficio. Si tenga a mente che l'oggetto `Task` dispone di una proprietà `TaskType` di tipo `TaskType`, che è un'enumerazione con valori `Home` e `Work`.  
  
 Nell'esempio seguente, il <xref:System.Windows.DataTrigger> imposta la <xref:System.Windows.Controls.Border.BorderBrush%2A> dell'elemento denominato `border` su `Yellow` se la proprietà `TaskType` è `TaskType.Home`.  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 L'applicazione presenta ora l'aspetto seguente. Le attività domestiche hanno un bordo giallo mentre le attività di ufficio hanno un bordo azzurro:  
  
 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 In questo esempio il <xref:System.Windows.DataTrigger> usa un <xref:System.Windows.Setter> per impostare un valore della proprietà. Le classi trigger hanno anche le proprietà <xref:System.Windows.TriggerBase.EnterActions%2A> e <xref:System.Windows.TriggerBase.ExitActions%2A> che consentono di avviare un set di azioni, ad esempio le animazioni. Inoltre, esiste anche una classe <xref:System.Windows.MultiDataTrigger> che consente di applicare le modifiche in base a più valori di proprietà con associazione a dati.  
  
 Un modo alternativo per ottenere lo stesso risultato consiste nell'associare la proprietà <xref:System.Windows.Controls.Border.BorderBrush%2A> alla proprietà `TaskType` e usare un convertitore di valori per restituire il colore in base al valore di `TaskType`. La creazione dell'effetto precedente tramite un convertitore è una soluzione leggermente più efficiente in termini di prestazioni. La creazione di un convertitore personalizzato offre inoltre maggiore flessibilità poiché consente di usare una logica personalizzata. La scelta della tecnica dipende in definitiva dallo scenario e le preferenze personali. Per informazioni su come scrivere un convertitore, vedere <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Elementi di un DataTemplate  

Nell'esempio precedente è stato inserito il trigger all'interno del <xref:System.Windows.DataTemplate> usando il <xref:System.Windows.DataTemplate>.<xref:System.Windows.DataTemplate.Triggers%2A> . Il <xref:System.Windows.Setter> del trigger imposta il valore di una proprietà di un elemento (l'elemento <xref:System.Windows.Controls.Border>) che si trova all'interno della <xref:System.Windows.DataTemplate>. Tuttavia, se le proprietà con cui si occupano i `Setters` non sono proprietà di elementi che rientrano nell'<xref:System.Windows.DataTemplate>corrente, può essere più appropriato impostare le proprietà utilizzando un <xref:System.Windows.Style> per la classe <xref:System.Windows.Controls.ListBoxItem> (se il controllo da associare è <xref:System.Windows.Controls.ListBox>). Se ad esempio si desidera che il <xref:System.Windows.Trigger> animare il valore di <xref:System.Windows.UIElement.Opacity%2A> dell'elemento quando un mouse punta a un elemento, è necessario definire i trigger all'interno di uno stile di <xref:System.Windows.Controls.ListBoxItem>. Per un esempio, vedere [Introduction to Styling and Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) (Introduzione all'esempio di applicazione di stili e modelli).
  
 In generale, tenere presente che la <xref:System.Windows.DataTemplate> viene applicata a ogni <xref:System.Windows.Controls.ListBoxItem> generata (per ulteriori informazioni su come e dove viene effettivamente applicata, vedere la pagina <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>). Il <xref:System.Windows.DataTemplate> è interessato solo dalla presentazione e dall'aspetto degli oggetti dati. Nella maggior parte dei casi, tutti gli altri aspetti della presentazione, ad esempio l'aspetto di un elemento quando viene selezionato o il modo in cui il <xref:System.Windows.Controls.ListBox> definisce gli elementi, non appartengono alla definizione di un <xref:System.Windows.DataTemplate>. Per un esempio, vedere la sezione [Applicazione di stili e modelli di ItemsControl](#DataTemplating_ItemsControl).  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Scelta di un DataTemplate in base alle proprietà dell'oggetto dati  
 Nella sezione [Proprietà DataType](#Styling_DataType) è stato spiegato che è possibile definire modelli di dati diversi per oggetti dati diversi. Ciò è particolarmente utile quando si dispone di un <xref:System.Windows.Data.CompositeCollection> di tipi o raccolte diverse con elementi di tipi diversi. Nella sezione [usare i trigger DataTrigger per applicare i valori delle proprietà](#DataTrigger_to_Apply_Property_Values) è stato illustrato che se si dispone di una raccolta dello stesso tipo di oggetti dati, è possibile creare un <xref:System.Windows.DataTemplate> e quindi usare i trigger per applicare le modifiche in base ai valori delle proprietà di ogni oggetto dati. I trigger consentono tuttavia di applicare valori delle proprietà o avviare animazioni ma non offrono la flessibilità necessaria per ricostruire la struttura degli oggetti dati. Alcuni scenari possono richiedere la creazione di un <xref:System.Windows.DataTemplate> diverso per oggetti dati dello stesso tipo ma con proprietà diverse.  
  
 Quando ad esempio un oggetto `Task` ha un valore `Priority` di `1`, è possibile conferirgli un aspetto completamente diverso in modo che funga da avviso. In tal caso, è possibile creare un <xref:System.Windows.DataTemplate> per la visualizzazione degli oggetti `Task` con priorità alta. Aggiungere la <xref:System.Windows.DataTemplate> seguente alla sezione Resources:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Si noti che questo esempio usa il <xref:System.Windows.DataTemplate>.<xref:System.Windows.FrameworkTemplate.Resources%2A> . Le risorse definite in tale sezione vengono condivise dagli elementi all'interno del <xref:System.Windows.DataTemplate>.  
  
 Per fornire la logica per scegliere quali <xref:System.Windows.DataTemplate> usare in base al valore `Priority` dell'oggetto dati, creare una sottoclasse di <xref:System.Windows.Controls.DataTemplateSelector> ed eseguire l'override del metodo <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A>. Nell'esempio seguente, il metodo <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> fornisce la logica per restituire il modello appropriato in base al valore della proprietà `Priority`. Il modello da restituire viene trovato nelle risorse dell'elemento <xref:System.Windows.Window> di inviluppo.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 È quindi possibile dichiarare il `TaskListDataTemplateSelector` come risorsa:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Per usare la risorsa di selezione dei modelli, assegnarla alla proprietà <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> del <xref:System.Windows.Controls.ListBox>. Il <xref:System.Windows.Controls.ListBox> chiama il metodo <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> della `TaskListDataTemplateSelector` per ogni elemento della raccolta sottostante. La chiamata passa l'oggetto dati come parametro di elemento. Il <xref:System.Windows.DataTemplate> restituito dal metodo viene quindi applicato a tale oggetto dati.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Con il selettore di modello sul posto, il <xref:System.Windows.Controls.ListBox> ora viene visualizzato come segue:  
  
 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Questa operazione chiude la spiegazione di questo esempio. Per l'esempio completo, vedere [Introduction to Data Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro) (Introduzione a un esempio di applicazione di modello).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Applicazione di stili e modelli a ItemsControl  
 Anche se il <xref:System.Windows.Controls.ItemsControl> non è l'unico tipo di controllo che è possibile usare con <xref:System.Windows.DataTemplate>, è uno scenario molto comune per associare un <xref:System.Windows.Controls.ItemsControl> a una raccolta. Nella sezione [What appartiene a DataTemplate](#what_belongs_in_datatemplate) è stato descritto che la definizione del <xref:System.Windows.DataTemplate> dovrebbe essere interessata solo alla presentazione dei dati. Per sapere quando non è adatto a usare un <xref:System.Windows.DataTemplate> è importante comprendere le diverse proprietà dello stile e del modello fornite dall'<xref:System.Windows.Controls.ItemsControl>. L'esempio seguente è progettato per illustrare la funzione di ognuna di queste proprietà. Il <xref:System.Windows.Controls.ItemsControl> in questo esempio è associato alla stessa raccolta di `Tasks` dell'esempio precedente. A scopo dimostrativo, gli stili e i modelli in questo esempio sono tutti dichiarati incorporati.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Lo screenshot seguente mostra l'esempio dopo il rendering:  
  
 ![Schermata di esempio ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Si noti che invece di usare la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, è possibile usare il <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>. Per un esempio, fare riferimento alla sezione precedente. Analogamente, invece di usare la <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>, è possibile usare l'<xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>.  
  
 Altre due proprietà correlate allo stile del <xref:System.Windows.Controls.ItemsControl> che non sono illustrate di seguito sono <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> e <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A>.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Supporto per i dati gerarchici  
 Sono state finora analizzate unicamente le modalità di associazione e di visualizzazione di una raccolta singola. Si dispone talvolta di una raccolta che contiene altre raccolte. La classe <xref:System.Windows.HierarchicalDataTemplate> è progettata per essere utilizzata con i tipi di <xref:System.Windows.Controls.HeaderedItemsControl> per visualizzare tali dati. Nell'esempio seguente `ListLeagueList` è un elenco di oggetti `League`. Ogni oggetto `League` ha un `Name` e una raccolta di oggetti `Division`. Ogni `Division` ha un `Name` e una raccolta di oggetti `Team` e ogni oggetto `Team` ha un `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 L'esempio mostra che con l'uso di <xref:System.Windows.HierarchicalDataTemplate>, è possibile visualizzare facilmente i dati dell'elenco che contengono altri elenchi. Lo screenshot seguente mostra l'esempio.  
  
 ![Schermata di esempio di HierarchicalDataTemplate](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Vedere anche

- [Data binding](../advanced/optimizing-performance-data-binding.md)
- [Procedura: trovare elementi generati da un oggetto DataTemplate](how-to-find-datatemplate-generated-elements.md)
- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](../controls/gridview-column-header-styles-and-templates-overview.md)
