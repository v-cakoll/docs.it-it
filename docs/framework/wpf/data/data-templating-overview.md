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
ms.openlocfilehash: 556ce7b42f13d7c5ba7fba36b09277cda9bcae5d
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400668"
---
# <a name="data-templating-overview"></a>Cenni preliminari sui modelli di dati
Il modello di applicazione di modelli di dati WPF offre una notevole flessibilità per definire la presentazione dei dati. I controlli WPF dispongono di funzionalità incorporate per supportare la personalizzazione della presentazione dei dati. In questo argomento viene illustrato innanzitutto come definire <xref:System.Windows.DataTemplate> un oggetto e quindi vengono introdotte altre funzionalità di creazione di modelli di dati, ad esempio la selezione di modelli basati sulla logica personalizzata e il supporto per la visualizzazione di dati gerarchici.  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento è incentrato sulle funzionalità di applicazione dei modelli di dati e non è un'introduzione ai concetti di data binding. Per informazioni sui concetti di data binding, vedere [Panoramica sul data binding](data-binding-overview.md).  
  
 <xref:System.Windows.DataTemplate>riguarda la presentazione dei dati ed è una delle numerose funzionalità fornite dal modello di applicazione di stili e modelli WPF. Per un'introduzione al modello di applicazione di stili e modelli WPF, ad esempio come usare <xref:System.Windows.Style> un oggetto per impostare le proprietà nei controlli, vedere l'argomento relativo allo [stile e](../controls/styling-and-templating.md) alla creazione di modelli.  
  
 Inoltre, è importante comprendere `Resources`, che sono essenzialmente quelli che consentono a oggetti <xref:System.Windows.Style> quali e <xref:System.Windows.DataTemplate> di essere riutilizzabili. Per altre informazioni sulle risorse, vedere [Risorse XAML](../advanced/xaml-resources.md).  
  
<a name="DataTemplating_Basic"></a>   
## <a name="data-templating-basics"></a>Nozioni fondamentali sui modelli di dati  
  
 Per illustrare <xref:System.Windows.DataTemplate> il motivo per cui è importante, esaminiamo un data binding esempio. In questo esempio è presente un oggetto <xref:System.Windows.Controls.ListBox> associato a un elenco di `Task` oggetti. Ogni oggetto `Task` dispone di un `TaskName` (stringa), una `Description` (stringa), una `Priority` (intero) e un tipo di proprietà `TaskType`, vale a dire una `Enum` con valori `Home` e `Work`.  
  
 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]  
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]  
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]  
  
<a name="without_a_datatemplate"></a>   
### <a name="without-a-datatemplate"></a>Senza un DataTemplate  
 Senza un <xref:System.Windows.DataTemplate>, l' <xref:System.Windows.Controls.ListBox> aspetto attuale è simile al seguente:  
  
 ![Schermata di esempio data templates](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")  
  
 Ciò che accade è che senza istruzioni specifiche, <xref:System.Windows.Controls.ListBox> per impostazione predefinita chiama `ToString` quando si tenta di visualizzare gli oggetti nella raccolta. Se pertanto l' `Task` oggetto esegue l'override `ToString` del metodo, <xref:System.Windows.Controls.ListBox> Visualizza la rappresentazione di stringa di ogni oggetto di origine nella raccolta sottostante.  
  
 Se ad esempio la classe `Task` esegue l'override del metodo `ToString` in questo modo, dove `name` è il campo della proprietà `TaskName`:  
  
 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]  
  
 L' <xref:System.Windows.Controls.ListBox> aspetto è simile al seguente:  
  
 ![Schermata di esempio data templates](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")  
  
 Questa soluzione risulta tuttavia limitante e poco flessibile. Se si esegue il binding a dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], non sarà inoltre possibile eseguire l'override di `ToString`.  
  
<a name="defining_simple_datatemplate"></a>   
### <a name="defining-a-simple-datatemplate"></a>Definizione di DataTemplate semplice  
 La soluzione consiste nel definire un <xref:System.Windows.DataTemplate>oggetto. Un modo per eseguire questa operazione consiste nell'impostare <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> la proprietà <xref:System.Windows.Controls.ListBox> di su un <xref:System.Windows.DataTemplate>oggetto. Gli elementi specificati in <xref:System.Windows.DataTemplate> diventano la struttura visiva dell'oggetto dati. Il codice <xref:System.Windows.DataTemplate> seguente è piuttosto semplice. Vengono fornite istruzioni che ogni elemento viene visualizzato come tre <xref:System.Windows.Controls.TextBlock> elementi all'interno <xref:System.Windows.Controls.StackPanel>di un oggetto. Ogni <xref:System.Windows.Controls.TextBlock> elemento è associato a una proprietà `Task` della classe.  
  
 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]  
  
 I dati sottostanti per gli esempi in questo argomento sono una raccolta di oggetti CLR. Se si esegue il binding a dati [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)], i concetti fondamentali sono gli stessi, ma con una piccola differenza sintattica. Ad esempio, anziché avere `Path=TaskName`, è necessario impostare <xref:System.Windows.Data.Binding.XPath%2A> su `@TaskName` (se `TaskName` è un attributo del [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] nodo).  
  
 A questo punto, l' aspettoèsimilealseguente:<xref:System.Windows.Controls.ListBox>  
  
 ![Schermata di esempio data templates](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")  
  
<a name="defining_datatemplate_as_a_resource"></a>   
### <a name="creating-the-datatemplate-as-a-resource"></a>Creazione di DataTemplate come risorsa  
 Nell'esempio precedente è stato definito <xref:System.Windows.DataTemplate> inline. È più comune definirlo nella sezione delle risorse perché qui diventa un oggetto riutilizzabile, come illustrato nell'esempio seguente:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 È possibile a questo punto usare `myTaskTemplate` come risorsa, come illustrato nell'esempio seguente:  
  
 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]  
  
 Poiché `myTaskTemplate` è una risorsa, è ora possibile utilizzarla in altri controlli che dispongono di una proprietà che accetta <xref:System.Windows.DataTemplate> un tipo. Come illustrato sopra, per <xref:System.Windows.Controls.ItemsControl> gli oggetti, ad esempio <xref:System.Windows.Controls.ListBox>, è la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà. Per <xref:System.Windows.Controls.ContentControl> gli oggetti, è la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> proprietà.  
  
<a name="Styling_DataType"></a>   
### <a name="the-datatype-property"></a>Proprietà DataType  
 La <xref:System.Windows.DataTemplate> classe dispone di <xref:System.Windows.DataTemplate.DataType%2A> una proprietà che <xref:System.Windows.Style.TargetType%2A> è molto simile <xref:System.Windows.Style> alla proprietà della classe. Quindi, invece di specificare un `x:Key` per l' <xref:System.Windows.DataTemplate> oggetto nell'esempio precedente, è possibile eseguire le operazioni seguenti:  
  
 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]  
  
 Questa <xref:System.Windows.DataTemplate> operazione viene applicata automaticamente a `Task` tutti gli oggetti. Si noti che in questo caso il valore di `x:Key` è impostato in modo implicito. Se pertanto si <xref:System.Windows.DataTemplate> assegna un `x:Key` valore, si <xref:System.Windows.DataTemplate> esegue l'override dell'oggetto implicito `x:Key` e non viene applicato automaticamente.  
  
 Se <xref:System.Windows.Controls.ContentControl> si associa un oggetto a una raccolta di `Task` oggetti, <xref:System.Windows.Controls.ContentControl> non utilizzerà automaticamente il valore <xref:System.Windows.DataTemplate> precedente. Ciò è dovuto al fatto che l' <xref:System.Windows.Controls.ContentControl> associazione su un oggetto necessita di ulteriori informazioni per distinguere se si desidera eseguire il binding a un'intera raccolta o a singoli oggetti. `/` <xref:System.Windows.Controls.ContentControl> <xref:System.Windows.Data.Binding.Path%2A> <xref:System.Windows.Controls.ItemsControl> Se il stamonitorandolaselezionediuntipo,èpossibileimpostarelaproprietàdell'associazionesu""perindicarechesièinteressatiall'elementocorrente.<xref:System.Windows.Controls.ContentControl> Per un esempio, vedere [Procedura: Eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). In caso contrario, è necessario specificare <xref:System.Windows.DataTemplate> in modo esplicito impostando la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> proprietà.  
  
 La <xref:System.Windows.DataTemplate.DataType%2A> proprietà è particolarmente utile quando si dispone di <xref:System.Windows.Data.CompositeCollection> un oggetto di tipi diversi di oggetti dati. Per un esempio, vedere [Procedura: Implementare un oggetto CompositeCollection](how-to-implement-a-compositecollection.md).  
  
<a name="adding_more_to_datatemplate"></a>   
## <a name="adding-more-to-the-datatemplate"></a>Aggiunta di altri elementi al DataTemplate  
 I dati presentano a questo punto le informazioni necessarie. È tuttavia possibile migliorarne ulteriormente la presentazione. Per migliorare la presentazione, è necessario aggiungere un <xref:System.Windows.Controls.Border>oggetto, <xref:System.Windows.Controls.Grid>un oggetto e <xref:System.Windows.Controls.TextBlock> alcuni elementi che descrivono i dati che vengono visualizzati.  
  
 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 La schermata seguente mostra la <xref:System.Windows.Controls.ListBox> con questa modifica <xref:System.Windows.DataTemplate>:  
  
 ![Schermata di esempio data templates](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")  
  
 È possibile impostare <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.HorizontalAlignment.Stretch> su su <xref:System.Windows.Controls.ListBox> per assicurarsi che la larghezza degli elementi occupa tutto lo spazio:  
  
 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]  
  
 Con la <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> proprietà impostata su <xref:System.Windows.HorizontalAlignment.Stretch>, ora <xref:System.Windows.Controls.ListBox> ha un aspetto simile al seguente:  
  
 ![Schermata di esempio data templates](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")  
  
<a name="DataTrigger_to_Apply_Property_Values"></a>   
### <a name="use-datatriggers-to-apply-property-values"></a>Utilizzo di DataTrigger per applicare i valori di proprietà  
 La presentazione corrente non indica se un `Task` è un'attività domestica o di ufficio. Si tenga a mente che l'oggetto `Task` dispone di una proprietà `TaskType` di tipo `TaskType`, che è un'enumerazione con valori `Home` e `Work`.  
  
 Nell'esempio <xref:System.Windows.DataTrigger> seguente, imposta l'oggetto <xref:System.Windows.Controls.Border.BorderBrush%2A> dell'elemento denominato `border` su `Yellow` se la `TaskType` proprietà è `TaskType.Home`.  
  
 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]  
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]  
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]  
  
 L'applicazione presenta ora l'aspetto seguente. Le attività domestiche hanno un bordo giallo mentre le attività di ufficio hanno un bordo azzurro:  
  
 ![Schermata di esempio data templates](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")  
  
 In questo esempio usa <xref:System.Windows.DataTrigger> un oggetto <xref:System.Windows.Setter> per impostare un valore della proprietà. Le classi trigger dispongono anche delle <xref:System.Windows.TriggerBase.EnterActions%2A> proprietà <xref:System.Windows.TriggerBase.ExitActions%2A> e che consentono di avviare un set di azioni, ad esempio le animazioni. Inoltre, esiste anche una <xref:System.Windows.MultiDataTrigger> classe che consente di applicare le modifiche in base a più valori di proprietà con associazione a dati.  
  
 Un modo alternativo per ottenere lo stesso risultato consiste nell'associare la <xref:System.Windows.Controls.Border.BorderBrush%2A> proprietà `TaskType` alla proprietà e usare un convertitore di valori per restituire il colore in base al `TaskType` valore. La creazione dell'effetto precedente tramite un convertitore è una soluzione leggermente più efficiente in termini di prestazioni. La creazione di un convertitore personalizzato offre inoltre maggiore flessibilità poiché consente di usare una logica personalizzata. La scelta della tecnica dipende in definitiva dallo scenario e le preferenze personali. Per informazioni su come scrivere un convertitore, vedere <xref:System.Windows.Data.IValueConverter>.  
  
<a name="what_belongs_in_datatemplate"></a>   
### <a name="what-belongs-in-a-datatemplate"></a>Elementi di un DataTemplate  

Nell'esempio precedente è stato inserito il trigger all'interno <xref:System.Windows.DataTemplate> di <xref:System.Windows.DataTemplate>usando.<xref:System.Windows.DataTemplate.Triggers%2A> . Il <xref:System.Windows.Setter> del trigger imposta il valore di una proprietà di un elemento (l' <xref:System.Windows.Controls.Border> elemento <xref:System.Windows.DataTemplate>) che si trova all'interno di. Tuttavia, se le proprietà con cui `Setters` si è interessati non sono proprietà di elementi che si trovano all'interno <xref:System.Windows.DataTemplate>dell'oggetto corrente, può essere più appropriato impostare le proprietà utilizzando <xref:System.Windows.Style> un oggetto per la <xref:System.Windows.Controls.ListBoxItem> classe (se il il controllo da associare è un <xref:System.Windows.Controls.ListBox>oggetto). Se, ad esempio, si desidera <xref:System.Windows.Trigger> che il <xref:System.Windows.UIElement.Opacity%2A> valore dell'elemento venga animato quando un mouse punta a un elemento, è necessario definire i trigger <xref:System.Windows.Controls.ListBoxItem> all'interno di uno stile. Per un esempio, vedere [Introduction to Styling and Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) (Introduzione all'esempio di applicazione di stili e modelli).
  
 In generale, tenere presente che l' <xref:System.Windows.DataTemplate> oggetto viene applicato a ogni oggetto generato <xref:System.Windows.Controls.ListBoxItem> . per ulteriori informazioni su come e dove viene effettivamente applicato, vedere la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> pagina. Il <xref:System.Windows.DataTemplate> è interessato solo dalla presentazione e dall'aspetto degli oggetti dati. Nella maggior parte dei casi, tutti gli altri aspetti della presentazione, ad esempio l'aspetto di un elemento quando viene selezionato o <xref:System.Windows.Controls.ListBox> il modo in cui dispone gli elementi, non appartengono alla definizione di <xref:System.Windows.DataTemplate>un oggetto. Per un esempio, vedere la sezione [Applicazione di stili e modelli di ItemsControl](#DataTemplating_ItemsControl).  
  
<a name="Styling_StyleSelection"></a>   
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Scelta di un DataTemplate in base alle proprietà dell'oggetto dati  
 Nella sezione [Proprietà DataType](#Styling_DataType) è stato spiegato che è possibile definire modelli di dati diversi per oggetti dati diversi. Ciò è particolarmente utile quando si dispone di <xref:System.Windows.Data.CompositeCollection> un di tipi o raccolte diversi con elementi di tipi diversi. Nella sezione [usare i trigger DataTrigger per applicare i valori delle proprietà](#DataTrigger_to_Apply_Property_Values) è stato illustrato che se si dispone di una raccolta dello stesso tipo di oggetti dati, è possibile <xref:System.Windows.DataTemplate> creare un oggetto e quindi usare i trigger per applicare le modifiche in base ai valori delle proprietà di ogni oggetto dati. I trigger consentono tuttavia di applicare valori delle proprietà o avviare animazioni ma non offrono la flessibilità necessaria per ricostruire la struttura degli oggetti dati. Per alcuni scenari potrebbe essere necessario creare un oggetto <xref:System.Windows.DataTemplate> diverso per oggetti dati dello stesso tipo ma con proprietà diverse.  
  
 Quando ad esempio un oggetto `Task` ha un valore `Priority` di `1`, è possibile conferirgli un aspetto completamente diverso in modo che funga da avviso. In tal caso, viene creato un <xref:System.Windows.DataTemplate> oggetto per la visualizzazione degli oggetti con priorità `Task` alta. Aggiungere quanto segue <xref:System.Windows.DataTemplate> alla sezione Resources:  
  
 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]  
  
 Si noti che questo esempio <xref:System.Windows.DataTemplate>USA.<xref:System.Windows.FrameworkTemplate.Resources%2A> . Le risorse definite in tale sezione vengono condivise dagli elementi all'interno <xref:System.Windows.DataTemplate>di.  
  
 Per fornire la logica per scegliere <xref:System.Windows.DataTemplate> quale utilizzare in base al `Priority` valore dell'oggetto dati, creare una sottoclasse di <xref:System.Windows.Controls.DataTemplateSelector> ed eseguire l' <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> override del metodo. Nell'esempio seguente, il <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> metodo fornisce la logica per restituire il modello appropriato in base al valore `Priority` della proprietà. Il modello da restituire viene trovato nelle risorse dell' <xref:System.Windows.Window> elemento di inviluppo.  
  
 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]  
  
 È quindi possibile dichiarare il `TaskListDataTemplateSelector` come risorsa:  
  
 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]  
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]  
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]  
  
 Per usare la risorsa <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> <xref:System.Windows.Controls.ListBox>di selezione dei modelli, assegnarla alla proprietà di. Chiama il <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> metodo di`TaskListDataTemplateSelector` per ogni elemento della raccolta sottostante. <xref:System.Windows.Controls.ListBox> La chiamata passa l'oggetto dati come parametro di elemento. L' <xref:System.Windows.DataTemplate> oggetto restituito dal metodo viene quindi applicato a tale oggetto dati.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]  
  
 Con il selettore di modello sul <xref:System.Windows.Controls.ListBox> posto, ora viene visualizzato come segue:  
  
 ![Schermata di esempio data templates](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")  

Questa operazione chiude la spiegazione di questo esempio. Per l'esempio completo, vedere [Introduction to Data Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro) (Introduzione a un esempio di applicazione di modello).

<a name="DataTemplating_ItemsControl"></a>   
## <a name="styling-and-templating-an-itemscontrol"></a>Applicazione di stili e modelli a ItemsControl  
 Anche se <xref:System.Windows.Controls.ItemsControl> non è l'unico tipo di controllo che è possibile <xref:System.Windows.DataTemplate> usare con, è uno scenario molto comune per associare un oggetto <xref:System.Windows.Controls.ItemsControl> a una raccolta. Nella sezione [What appartiene a DataTemplate](#what_belongs_in_datatemplate) è stato descritto che la definizione del <xref:System.Windows.DataTemplate> deve essere interessata solo alla presentazione dei dati. Per sapere quando non è adatto all'uso di un <xref:System.Windows.DataTemplate> , è importante comprendere le diverse proprietà dello stile e del modello fornite <xref:System.Windows.Controls.ItemsControl>da. L'esempio seguente è progettato per illustrare la funzione di ognuna di queste proprietà. In questo esempio è associato alla stessa `Tasks` raccolta dell'esempio precedente. <xref:System.Windows.Controls.ItemsControl> A scopo dimostrativo, gli stili e i modelli in questo esempio sono tutti dichiarati incorporati.  
  
 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]  
  
 Lo screenshot seguente mostra l'esempio dopo il rendering:  
  
 ![Screenshot dell'esempio di ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")  
  
 Si noti che anziché <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>utilizzare, è possibile <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A>utilizzare. Per un esempio, fare riferimento alla sezione precedente. Analogamente, invece di usare <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>, è possibile <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A>usare.  
  
 Altre due proprietà correlate allo stile di <xref:System.Windows.Controls.ItemsControl> che non sono illustrate di seguito sono <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A> <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> e.  
  
<a name="DataTemplating_HeirarchicalDataTemplate"></a>   
## <a name="support-for-hierarchical-data"></a>Supporto per i dati gerarchici  
 Sono state finora analizzate unicamente le modalità di associazione e di visualizzazione di una raccolta singola. Si dispone talvolta di una raccolta che contiene altre raccolte. La <xref:System.Windows.HierarchicalDataTemplate> classe è progettata per essere utilizzata con <xref:System.Windows.Controls.HeaderedItemsControl> i tipi per visualizzare tali dati. Nell'esempio seguente `ListLeagueList` è un elenco di oggetti `League`. Ogni oggetto `League` ha un `Name` e una raccolta di oggetti `Division`. Ogni `Division` ha un `Name` e una raccolta di oggetti `Team` e ogni oggetto `Team` ha un `Name`.  
  
 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]  
  
 Nell'esempio viene mostrato che, con l' <xref:System.Windows.HierarchicalDataTemplate>utilizzo di, è possibile visualizzare facilmente i dati dell'elenco che contengono altri elenchi. Lo screenshot seguente mostra l'esempio.  
  
 ![Schermata di esempio di HierarchicalDataTemplate](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")  
  
## <a name="see-also"></a>Vedere anche

- [Data binding](../advanced/optimizing-performance-data-binding.md)
- [Procedura: trovare elementi generati da un oggetto DataTemplate](how-to-find-datatemplate-generated-elements.md)
- [Applicazione di stili e modelli](../controls/styling-and-templating.md)
- [Panoramica sul data binding](data-binding-overview.md)
- [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](../controls/gridview-column-header-styles-and-templates-overview.md)
