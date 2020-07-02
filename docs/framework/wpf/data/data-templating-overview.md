---
title: Cenni preliminari sui modelli di dati
description: Esplorare il modello di data template flessibilità che definisce la presentazione dei dati in Windows Presentation Foundation (WPF).
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
ms.openlocfilehash: 0226085a82cf97ea799a5a2d38e879b239d9b52a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619650"
---
# <a name="data-templating-overview"></a>Cenni preliminari sui modelli di dati
Il modello di applicazione di modelli di dati WPF offre una notevole flessibilità per definire la presentazione dei dati. I controlli WPF dispongono di funzionalità incorporate per supportare la personalizzazione della presentazione dei dati. In questo argomento viene illustrato innanzitutto come definire un oggetto <xref:System.Windows.DataTemplate> e quindi vengono introdotte altre funzionalità di creazione di modelli di dati, ad esempio la selezione di modelli basati sulla logica personalizzata e il supporto per la visualizzazione di dati gerarchici.

<a name="Prerequisites"></a>
## <a name="prerequisites"></a>Prerequisiti
 Questo argomento è incentrato sulle funzionalità di applicazione dei modelli di dati e non è un'introduzione ai concetti di data binding. Per informazioni sui concetti di data binding, vedere [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md).

 <xref:System.Windows.DataTemplate>riguarda la presentazione dei dati ed è una delle numerose funzionalità fornite dal modello di applicazione di stili e modelli WPF. Per un'introduzione al modello di applicazione di stili e modelli WPF, ad esempio come usare un oggetto <xref:System.Windows.Style> per impostare le proprietà nei controlli, vedere l'argomento relativo allo [stile e](../../../desktop-wpf/fundamentals/styles-templates-overview.md) alla creazione di modelli.

 Inoltre, è importante comprendere `Resources` , che sono essenzialmente quelli che consentono a oggetti quali <xref:System.Windows.Style> e <xref:System.Windows.DataTemplate> di essere riutilizzabili. Per altre informazioni sulle risorse, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

<a name="DataTemplating_Basic"></a>
## <a name="data-templating-basics"></a>Nozioni fondamentali sui modelli di dati

 Per illustrare il motivo per cui <xref:System.Windows.DataTemplate> è importante, esaminiamo un data binding esempio. In questo esempio è presente un oggetto <xref:System.Windows.Controls.ListBox> associato a un elenco di `Task` oggetti. Ogni oggetto `Task` dispone di un `TaskName` (stringa), una `Description` (stringa), una `Priority` (intero) e un tipo di proprietà `TaskType`, vale a dire una `Enum` con valori `Home` e `Work`.

 [!code-xaml[DataTemplatingIntro_snip#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#resources)]
[!code-xaml[DataTemplatingIntro_snip#UI1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui1)]
[!code-xaml[DataTemplatingIntro_snip#UI2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#ui2)]

<a name="without_a_datatemplate"></a>
### <a name="without-a-datatemplate"></a>Senza un DataTemplate
 Senza un <xref:System.Windows.DataTemplate> , l' <xref:System.Windows.Controls.ListBox> aspetto attuale è simile al seguente:

 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig1.png "DataTemplatingIntro_fig1")

 Ciò che accade è che senza istruzioni specifiche, <xref:System.Windows.Controls.ListBox> per impostazione predefinita chiama `ToString` quando si tenta di visualizzare gli oggetti nella raccolta. Se pertanto l' `Task` oggetto esegue l'override del `ToString` metodo, <xref:System.Windows.Controls.ListBox> Visualizza la rappresentazione di stringa di ogni oggetto di origine nella raccolta sottostante.

 Se ad esempio la classe `Task` esegue l'override del metodo `ToString` in questo modo, dove `name` è il campo della proprietà `TaskName`:

 [!code-csharp[DataTemplatingIntro_snip#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Data.cs#tostring)]
 [!code-vb[DataTemplatingIntro_snip#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/data.vb#tostring)]

 L' <xref:System.Windows.Controls.ListBox> aspetto è simile al seguente:

 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig2.png "DataTemplatingIntro_fig2")

 Questa soluzione risulta tuttavia limitante e poco flessibile. Inoltre, se si esegue il binding ai dati XML, non sarà possibile eseguire l'override di `ToString` .

<a name="defining_simple_datatemplate"></a>
### <a name="defining-a-simple-datatemplate"></a>Definizione di DataTemplate semplice
 La soluzione consiste nel definire un oggetto <xref:System.Windows.DataTemplate> . Un modo per eseguire questa operazione consiste nell'impostare la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà di <xref:System.Windows.Controls.ListBox> su un oggetto <xref:System.Windows.DataTemplate> . Gli elementi specificati in <xref:System.Windows.DataTemplate> diventano la struttura visiva dell'oggetto dati. Il codice seguente <xref:System.Windows.DataTemplate> è piuttosto semplice. Vengono fornite istruzioni che ogni elemento viene visualizzato come tre <xref:System.Windows.Controls.TextBlock> elementi all'interno di un oggetto <xref:System.Windows.Controls.StackPanel> . Ogni <xref:System.Windows.Controls.TextBlock> elemento è associato a una proprietà della `Task` classe.

 [!code-xaml[DataTemplatingIntro_snip#Inline](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#inline)]

 I dati sottostanti per gli esempi in questo argomento sono una raccolta di oggetti CLR. Se si esegue il binding ai dati XML, i concetti fondamentali sono gli stessi, ma c'è una lieve differenza sintattica. Ad esempio, anziché avere `Path=TaskName` , è necessario impostare <xref:System.Windows.Data.Binding.XPath%2A> su `@TaskName` (se `TaskName` è un attributo del nodo XML).

 A questo punto <xref:System.Windows.Controls.ListBox> , l'aspetto è simile al seguente:

 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig3.png "DataTemplatingIntro_fig3")

<a name="defining_datatemplate_as_a_resource"></a>
### <a name="creating-the-datatemplate-as-a-resource"></a>Creazione di DataTemplate come risorsa
 Nell'esempio precedente è stato definito <xref:System.Windows.DataTemplate> inline. È più comune definirlo nella sezione delle risorse perché qui diventa un oggetto riutilizzabile, come illustrato nell'esempio seguente:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#AsResource](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#asresource)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 È possibile a questo punto usare `myTaskTemplate` come risorsa, come illustrato nell'esempio seguente:

 [!code-xaml[DataTemplatingIntro_snip#MyTaskTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#mytasktemplate)]

 Poiché `myTaskTemplate` è una risorsa, è ora possibile utilizzarla in altri controlli che dispongono di una proprietà che accetta un <xref:System.Windows.DataTemplate> tipo. Come illustrato sopra, per <xref:System.Windows.Controls.ItemsControl> gli oggetti, ad esempio <xref:System.Windows.Controls.ListBox> , è la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Proprietà. Per <xref:System.Windows.Controls.ContentControl> gli oggetti, è la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Proprietà.

<a name="Styling_DataType"></a>
### <a name="the-datatype-property"></a>Proprietà DataType
 La <xref:System.Windows.DataTemplate> classe dispone di una <xref:System.Windows.DataTemplate.DataType%2A> proprietà che è molto simile alla <xref:System.Windows.Style.TargetType%2A> proprietà della <xref:System.Windows.Style> classe. Quindi, invece di specificare un `x:Key` per l'oggetto <xref:System.Windows.DataTemplate> nell'esempio precedente, è possibile eseguire le operazioni seguenti:

 [!code-xaml[DataTemplatingIntro_snip#DataType](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#datatype)]

 Questa operazione <xref:System.Windows.DataTemplate> viene applicata automaticamente a tutti `Task` gli oggetti. Si noti che in questo caso il valore di `x:Key` è impostato in modo implicito. Se pertanto si assegna <xref:System.Windows.DataTemplate> un `x:Key` valore, si esegue l'override dell'oggetto implicito `x:Key` e <xref:System.Windows.DataTemplate> non viene applicato automaticamente.

 Se si associa un oggetto <xref:System.Windows.Controls.ContentControl> a una raccolta di `Task` oggetti, <xref:System.Windows.Controls.ContentControl> non utilizzerà automaticamente il valore precedente <xref:System.Windows.DataTemplate> . Ciò è dovuto al fatto che l'associazione su un oggetto <xref:System.Windows.Controls.ContentControl> necessita di ulteriori informazioni per distinguere se si desidera eseguire il binding a un'intera raccolta o a singoli oggetti. Se il <xref:System.Windows.Controls.ContentControl> sta monitorando la selezione di un <xref:System.Windows.Controls.ItemsControl> tipo, è possibile impostare la <xref:System.Windows.Data.Binding.Path%2A> proprietà dell' <xref:System.Windows.Controls.ContentControl> associazione su " `/` " per indicare che si è interessati all'elemento corrente. Per un esempio, vedere [Procedura: Eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata](how-to-bind-to-a-collection-and-display-information-based-on-selection.md). In caso contrario, è necessario specificare in <xref:System.Windows.DataTemplate> modo esplicito impostando la <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> Proprietà.

 La <xref:System.Windows.DataTemplate.DataType%2A> proprietà è particolarmente utile quando si dispone di un oggetto <xref:System.Windows.Data.CompositeCollection> di tipi diversi di oggetti dati. Per un esempio, vedere [Procedura: Implementare un oggetto CompositeCollection](how-to-implement-a-compositecollection.md).

<a name="adding_more_to_datatemplate"></a>
## <a name="adding-more-to-the-datatemplate"></a>Aggiunta di altri elementi al DataTemplate
 I dati presentano a questo punto le informazioni necessarie. È tuttavia possibile migliorarne ulteriormente la presentazione. Per migliorare la presentazione, è necessario aggiungere un oggetto <xref:System.Windows.Controls.Border> , un oggetto <xref:System.Windows.Controls.Grid> e alcuni <xref:System.Windows.Controls.TextBlock> elementi che descrivono i dati che vengono visualizzati.

 [!code-xaml[DataTemplatingIntro#AddingMore](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 La schermata seguente mostra la <xref:System.Windows.Controls.ListBox> con questa modifica <xref:System.Windows.DataTemplate> :

 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig4.png "DataTemplatingIntro_fig4")

 È possibile impostare <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> <xref:System.Windows.HorizontalAlignment.Stretch> su su <xref:System.Windows.Controls.ListBox> per assicurarsi che la larghezza degli elementi occupa tutto lo spazio:

 [!code-xaml[DataTemplatingIntro_snip#Stretch](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#stretch)]

 Con la <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> proprietà impostata su <xref:System.Windows.HorizontalAlignment.Stretch> , ora ha un <xref:System.Windows.Controls.ListBox> aspetto simile al seguente:

 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig5.png "DataTemplatingIntro_fig5")

<a name="DataTrigger_to_Apply_Property_Values"></a>
### <a name="use-datatriggers-to-apply-property-values"></a>Utilizzo di DataTrigger per applicare i valori di proprietà
 La presentazione corrente non indica se un `Task` è un'attività domestica o di ufficio. Si tenga a mente che l'oggetto `Task` dispone di una proprietà `TaskType` di tipo `TaskType`, che è un'enumerazione con valori `Home` e `Work`.

 Nell'esempio seguente, <xref:System.Windows.DataTrigger> imposta l'oggetto <xref:System.Windows.Controls.Border.BorderBrush%2A> dell'elemento denominato `border` su `Yellow` se la `TaskType` proprietà è `TaskType.Home` .

 [!code-xaml[DataTemplatingIntro#DT](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#dt)]
[!code-xaml[DataTemplatingIntro#DataTrigger](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#datatrigger)]
[!code-xaml[DataTemplatingIntro#AddingMore2](~/samples/snippets/xaml/VS_Snippets_Wpf/DataTemplatingIntro/xaml/window1.xaml#addingmore2)]

 L'applicazione presenta ora l'aspetto seguente. Le attività domestiche hanno un bordo giallo mentre le attività di ufficio hanno un bordo azzurro:

 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig6.png "DataTemplatingIntro_fig6")

 In questo esempio <xref:System.Windows.DataTrigger> Usa un oggetto <xref:System.Windows.Setter> per impostare un valore della proprietà. Le classi trigger dispongono anche delle <xref:System.Windows.TriggerBase.EnterActions%2A> <xref:System.Windows.TriggerBase.ExitActions%2A> proprietà e che consentono di avviare un set di azioni, ad esempio le animazioni. Inoltre, esiste anche una <xref:System.Windows.MultiDataTrigger> classe che consente di applicare le modifiche in base a più valori di proprietà con associazione a dati.

 Un modo alternativo per ottenere lo stesso risultato consiste nell'associare la <xref:System.Windows.Controls.Border.BorderBrush%2A> proprietà alla `TaskType` proprietà e usare un convertitore di valori per restituire il colore in base al `TaskType` valore. La creazione dell'effetto precedente tramite un convertitore è una soluzione leggermente più efficiente in termini di prestazioni. La creazione di un convertitore personalizzato offre inoltre maggiore flessibilità poiché consente di usare una logica personalizzata. La scelta della tecnica dipende in definitiva dallo scenario e le preferenze personali. Per informazioni su come scrivere un convertitore, vedere <xref:System.Windows.Data.IValueConverter> .

<a name="what_belongs_in_datatemplate"></a>
### <a name="what-belongs-in-a-datatemplate"></a>Elementi di un DataTemplate

Nell'esempio precedente è stato inserito il trigger all'interno di <xref:System.Windows.DataTemplate> usando la <xref:System.Windows.DataTemplate.Triggers%2A?displayProperty=nameWithType> Proprietà. Il <xref:System.Windows.Setter> del trigger imposta il valore di una proprietà di un elemento (l' <xref:System.Windows.Controls.Border> elemento) che si trova all'interno di <xref:System.Windows.DataTemplate> . Tuttavia, se le proprietà con cui `Setters` si è interessati non sono proprietà di elementi che si trovano all'interno dell'oggetto corrente <xref:System.Windows.DataTemplate> , può essere più appropriato impostare le proprietà usando un oggetto <xref:System.Windows.Style> per la <xref:System.Windows.Controls.ListBoxItem> classe (se il controllo da associare è <xref:System.Windows.Controls.ListBox> ). Se, ad esempio, si desidera che il <xref:System.Windows.Trigger> <xref:System.Windows.UIElement.Opacity%2A> valore dell'elemento venga animato quando un mouse punta a un elemento, è necessario definire i trigger all'interno di uno <xref:System.Windows.Controls.ListBoxItem> stile. Per un esempio, vedere [Introduction to Styling and Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating) (Introduzione all'esempio di applicazione di stili e modelli).

 In generale, tenere presente che l'oggetto <xref:System.Windows.DataTemplate> viene applicato a ogni oggetto generato <xref:System.Windows.Controls.ListBoxItem> . per ulteriori informazioni su come e dove viene effettivamente applicato, vedere la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> pagina. Il <xref:System.Windows.DataTemplate> è interessato solo dalla presentazione e dall'aspetto degli oggetti dati. Nella maggior parte dei casi, tutti gli altri aspetti della presentazione, ad esempio l'aspetto di un elemento quando viene selezionato o il modo <xref:System.Windows.Controls.ListBox> in cui dispone gli elementi, non appartengono alla definizione di un oggetto <xref:System.Windows.DataTemplate> . Per un esempio, vedere la sezione [Applicazione di stili e modelli di ItemsControl](#DataTemplating_ItemsControl).

<a name="Styling_StyleSelection"></a>
## <a name="choosing-a-datatemplate-based-on-properties-of-the-data-object"></a>Scelta di un DataTemplate in base alle proprietà dell'oggetto dati
 Nella sezione [Proprietà DataType](#Styling_DataType) è stato spiegato che è possibile definire modelli di dati diversi per oggetti dati diversi. Ciò è particolarmente utile quando si dispone di un <xref:System.Windows.Data.CompositeCollection> di tipi o raccolte diversi con elementi di tipi diversi. Nella sezione [usare i trigger DataTrigger per applicare i valori delle proprietà](#DataTrigger_to_Apply_Property_Values) è stato illustrato che se si dispone di una raccolta dello stesso tipo di oggetti dati, è possibile creare un oggetto <xref:System.Windows.DataTemplate> e quindi usare i trigger per applicare le modifiche in base ai valori delle proprietà di ogni oggetto dati. I trigger consentono tuttavia di applicare valori delle proprietà o avviare animazioni ma non offrono la flessibilità necessaria per ricostruire la struttura degli oggetti dati. Per alcuni scenari potrebbe essere necessario creare un oggetto diverso <xref:System.Windows.DataTemplate> per oggetti dati dello stesso tipo ma con proprietà diverse.

 Quando ad esempio un oggetto `Task` ha un valore `Priority` di `1`, è possibile conferirgli un aspetto completamente diverso in modo che funga da avviso. In tal caso, viene creato un oggetto <xref:System.Windows.DataTemplate> per la visualizzazione degli oggetti con priorità alta `Task` . Aggiungere quanto segue <xref:System.Windows.DataTemplate> alla sezione Resources:

 [!code-xaml[DataTemplatingIntro_snip#ImportantTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#importanttemplate)]

Questo esempio usa la proprietà [DataTemplate. resources](xref:System.Windows.FrameworkTemplate.Resources%2A) . Le risorse definite in tale sezione vengono condivise dagli elementi all'interno di <xref:System.Windows.DataTemplate> .

 Per fornire la logica per scegliere quale <xref:System.Windows.DataTemplate> utilizzare in base al `Priority` valore dell'oggetto dati, creare una sottoclasse di <xref:System.Windows.Controls.DataTemplateSelector> ed eseguire l'override del <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> metodo. Nell'esempio seguente, il <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> metodo fornisce la logica per restituire il modello appropriato in base al valore della `Priority` Proprietà. Il modello da restituire viene trovato nelle risorse dell'elemento di inviluppo <xref:System.Windows.Window> .

 [!code-csharp[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/TaskListDataTemplateSelector.cs#dtsclass)]
 [!code-vb[DataTemplatingIntro_snip#DTSClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataTemplatingIntro_snip/visualbasic/tasklistdatatemplateselector.vb#dtsclass)]

 È quindi possibile dichiarare il `TaskListDataTemplateSelector` come risorsa:

 [!code-xaml[DataTemplatingIntro_snip#R1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r1)]
[!code-xaml[DataTemplatingIntro_snip#DTS](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#dts)]
[!code-xaml[DataTemplatingIntro_snip#R2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#r2)]

 Per usare la risorsa di selezione dei modelli, assegnarla alla <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> proprietà di <xref:System.Windows.Controls.ListBox> . <xref:System.Windows.Controls.ListBox>Chiama il <xref:System.Windows.Controls.DataTemplateSelector.SelectTemplate%2A> metodo di `TaskListDataTemplateSelector` per ogni elemento della raccolta sottostante. La chiamata passa l'oggetto dati come parametro di elemento. L' <xref:System.Windows.DataTemplate> oggetto restituito dal metodo viene quindi applicato a tale oggetto dati.

 [!code-xaml[DataTemplatingIntro_snip#ItemTemplateSelector](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemtemplateselector)]

 Con il selettore di modello sul posto, <xref:System.Windows.Controls.ListBox> ora viene visualizzato come segue:

 ![Schermata di esempio data Templates](./media/datatemplatingintro-fig7.png "DataTemplatingIntro_fig7")

Questa operazione chiude la spiegazione di questo esempio. Per l'esempio completo, vedere [Introduction to Data Templating Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/DataTemplatingIntro) (Introduzione a un esempio di applicazione di modello).

<a name="DataTemplating_ItemsControl"></a>
## <a name="styling-and-templating-an-itemscontrol"></a>Applicazione di stili e modelli a ItemsControl
 Anche se <xref:System.Windows.Controls.ItemsControl> non è l'unico tipo di controllo che è possibile usare <xref:System.Windows.DataTemplate> con, è uno scenario molto comune per associare un oggetto <xref:System.Windows.Controls.ItemsControl> a una raccolta. Nella sezione [What appartiene a DataTemplate](#what_belongs_in_datatemplate) è stato descritto che la definizione del <xref:System.Windows.DataTemplate> deve essere interessata solo alla presentazione dei dati. Per sapere quando non è adatto all'uso di un <xref:System.Windows.DataTemplate> , è importante comprendere le diverse proprietà dello stile e del modello fornite da <xref:System.Windows.Controls.ItemsControl> . L'esempio seguente è progettato per illustrare la funzione di ognuna di queste proprietà. <xref:System.Windows.Controls.ItemsControl>In questo esempio è associato alla stessa raccolta dell' `Tasks` esempio precedente. A scopo dimostrativo, gli stili e i modelli in questo esempio sono tutti dichiarati incorporati.

 [!code-xaml[DataTemplatingIntro_snip#ItemsControlProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/DataTemplatingIntro_snip/CSharp/Window1.xaml#itemscontrolproperties)]

 Lo screenshot seguente mostra l'esempio dopo il rendering:

 ![Screenshot di esempio ItemsControl](./media/databinding-itemscontrolproperties.png "DataBinding_ItemsControlProperties")

 Si noti che anziché utilizzare <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> , è possibile utilizzare <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> . Per un esempio, fare riferimento alla sezione precedente. Analogamente, invece di usare <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> , è possibile usare <xref:System.Windows.Controls.ItemsControl.ItemContainerStyleSelector%2A> .

 Altre due proprietà correlate allo stile di <xref:System.Windows.Controls.ItemsControl> che non sono illustrate di seguito sono <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> e <xref:System.Windows.Controls.ItemsControl.GroupStyleSelector%2A> .

<a name="DataTemplating_HeirarchicalDataTemplate"></a>
## <a name="support-for-hierarchical-data"></a>Supporto per i dati gerarchici
 Sono state finora analizzate unicamente le modalità di associazione e di visualizzazione di una raccolta singola. Si dispone talvolta di una raccolta che contiene altre raccolte. La <xref:System.Windows.HierarchicalDataTemplate> classe è progettata per essere utilizzata con i <xref:System.Windows.Controls.HeaderedItemsControl> tipi per visualizzare tali dati. Nell'esempio seguente `ListLeagueList` è un elenco di oggetti `League`. Ogni oggetto `League` ha un `Name` e una raccolta di oggetti `Division`. Ogni `Division` ha un `Name` e una raccolta di oggetti `Team` e ogni oggetto `Team` ha un `Name`.

 [!code-xaml[HierarchicalDataTemplateSnippet#HDT](~/samples/snippets/csharp/VS_Snippets_Wpf/HierarchicalDataTemplateSnippet/CS/window1.xaml#hdt)]

 Nell'esempio viene mostrato che, con l'utilizzo di <xref:System.Windows.HierarchicalDataTemplate> , è possibile visualizzare facilmente i dati dell'elenco che contengono altri elenchi. Lo screenshot seguente mostra l'esempio.

 ![Schermata di esempio di HierarchicalDataTemplate](./media/databinding-hierarchicaldatatemplate.png "DataBinding_HierarchicalDataTemplate")

## <a name="see-also"></a>Vedere anche

- [Data binding](../advanced/optimizing-performance-data-binding.md)
- [Trovare elementi generati da un oggetto DataTemplate](how-to-find-datatemplate-generated-elements.md)
- [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Panoramica sui modelli e sugli stili di intestazione delle colonne in GridView](../controls/gridview-column-header-styles-and-templates-overview.md)
