---
title: 'Procedura: raggruppare, ordinare e filtrare dati nel controllo DataGrid'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e648b5a4a45c3583d496ac0ea6036d268d6d33a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a><span data-ttu-id="f92ed-102">Procedura: raggruppare, ordinare e filtrare dati nel controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="f92ed-102">How to: Group, Sort, and Filter Data in the DataGrid Control</span></span>
<span data-ttu-id="f92ed-103">È spesso utile visualizzare i dati in un <xref:System.Windows.Controls.DataGrid> in modi diversi per il raggruppamento, ordinamento e filtro dei dati.</span><span class="sxs-lookup"><span data-stu-id="f92ed-103">It is often useful to view data in a <xref:System.Windows.Controls.DataGrid> in different ways by grouping, sorting, and filtering the data.</span></span> <span data-ttu-id="f92ed-104">Per raggruppare, ordinare e filtrare i dati in un <xref:System.Windows.Controls.DataGrid>, è necessario associarli a un <xref:System.Windows.Data.CollectionView> che supporti queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="f92ed-104">To group, sort, and filter the data in a <xref:System.Windows.Controls.DataGrid>, you bind it to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="f92ed-105">È quindi possibile utilizzare i dati di <xref:System.Windows.Data.CollectionView> senza modificare l'origine dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="f92ed-105">You can then work with the data in the <xref:System.Windows.Data.CollectionView> without affecting the underlying source data.</span></span> <span data-ttu-id="f92ed-106">Le modifiche nella visualizzazione raccolta vengono riflesse nel <xref:System.Windows.Controls.DataGrid> interfaccia utente (UI).</span><span class="sxs-lookup"><span data-stu-id="f92ed-106">The changes in the collection view are reflected in the <xref:System.Windows.Controls.DataGrid> user interface (UI).</span></span>  
  
 <span data-ttu-id="f92ed-107">Il <xref:System.Windows.Data.CollectionView> classe fornisce il raggruppamento e ordinamento delle funzionalità per un'origine dati che implementa il <xref:System.Collections.IEnumerable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f92ed-107">The <xref:System.Windows.Data.CollectionView> class provides grouping and sorting functionality for a data source that implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="f92ed-108">Il <xref:System.Windows.Data.CollectionViewSource> classe consente di impostare le proprietà di un <xref:System.Windows.Data.CollectionView> da XAML.</span><span class="sxs-lookup"><span data-stu-id="f92ed-108">The <xref:System.Windows.Data.CollectionViewSource> class enables you to set the properties of a <xref:System.Windows.Data.CollectionView> from XAML.</span></span>  
  
 <span data-ttu-id="f92ed-109">In questo esempio, una raccolta di `Task` oggetti è associato a un <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="f92ed-109">In this example, a collection of `Task` objects is bound to a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="f92ed-110">Il <xref:System.Windows.Data.CollectionViewSource> viene utilizzato come il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per il <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="f92ed-110">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="f92ed-111">Il raggruppamento, ordinamento e filtro vengono eseguite sul <xref:System.Windows.Data.CollectionViewSource> e vengono visualizzati nel <xref:System.Windows.Controls.DataGrid> dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="f92ed-111">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="f92ed-112">![Dati raggruppati in un controllo DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span><span class="sxs-lookup"><span data-stu-id="f92ed-112">![Grouped data in a DataGrid](../../../../docs/framework/wpf/controls/media/wpf-datagridgroups.png "WPF_DataGridGroups")</span></span>  
<span data-ttu-id="f92ed-113">Dati raggruppati in un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="f92ed-113">Grouped Data in a DataGrid</span></span>  
  
## <a name="using-a-collectionviewsource-as-an-itemssource"></a><span data-ttu-id="f92ed-114">Utilizzo di un oggetto CollectionViewSource come ItemsSource</span><span class="sxs-lookup"><span data-stu-id="f92ed-114">Using a CollectionViewSource as an ItemsSource</span></span>  
 <span data-ttu-id="f92ed-115">Al gruppo, ordinamento e filtrare i dati in un <xref:System.Windows.Controls.DataGrid> controllo, associare il <xref:System.Windows.Controls.DataGrid> per un <xref:System.Windows.Data.CollectionView> che supporti queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="f92ed-115">To group, sort, and filter data in a <xref:System.Windows.Controls.DataGrid> control, you bind the <xref:System.Windows.Controls.DataGrid> to a <xref:System.Windows.Data.CollectionView> that supports these functions.</span></span> <span data-ttu-id="f92ed-116">In questo esempio, il <xref:System.Windows.Controls.DataGrid> è associato a un <xref:System.Windows.Data.CollectionViewSource> che fornisce queste funzioni per un <xref:System.Collections.Generic.List%601> di `Task` oggetti.</span><span class="sxs-lookup"><span data-stu-id="f92ed-116">In this example, the <xref:System.Windows.Controls.DataGrid> is bound to a <xref:System.Windows.Data.CollectionViewSource> that provides these functions for a <xref:System.Collections.Generic.List%601> of `Task` objects.</span></span>  
  
#### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a><span data-ttu-id="f92ed-117">Per associare un controllo DataGrid a CollectionViewSource</span><span class="sxs-lookup"><span data-stu-id="f92ed-117">To bind a DataGrid to a CollectionViewSource</span></span>  
  
1.  <span data-ttu-id="f92ed-118">Creare una raccolta di dati che implementa il <xref:System.Collections.IEnumerable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f92ed-118">Create a data collection that implements the <xref:System.Collections.IEnumerable> interface.</span></span>  
  
     <span data-ttu-id="f92ed-119">Se si utilizza <xref:System.Collections.Generic.List%601> per creare la raccolta, è necessario creare una nuova classe che eredita da <xref:System.Collections.Generic.List%601> anziché creare un'istanza di un'istanza di <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="f92ed-119">If you use <xref:System.Collections.Generic.List%601> to create your collection, you should create a new class that inherits from <xref:System.Collections.Generic.List%601> instead of instantiating an instance of <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="f92ed-120">Ciò consente di associare dati alla raccolta in XAML.</span><span class="sxs-lookup"><span data-stu-id="f92ed-120">This enables you to data bind to the collection in XAML.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f92ed-121">Gli oggetti nella raccolta devono implementare il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia modificata e <xref:System.ComponentModel.IEditableObject> interfaccia affinché il <xref:System.Windows.Controls.DataGrid> risponda correttamente alla modifica delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="f92ed-121">The objects in the collection must implement the <xref:System.ComponentModel.INotifyPropertyChanged> changed interface and the <xref:System.ComponentModel.IEditableObject> interface in order for the <xref:System.Windows.Controls.DataGrid> to respond correctly to property changes and edits.</span></span> <span data-ttu-id="f92ed-122">Per altre informazioni, vedere [Implementare la notifica di modifiche alle proprietà](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="f92ed-122">For more information, see [Implement Property Change Notification](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
     [!code-vb[DataGrid_GroupSortFilter#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]  
  
2.  <span data-ttu-id="f92ed-123">In XAML, creare un'istanza della classe di raccolta e impostare il [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md).</span><span class="sxs-lookup"><span data-stu-id="f92ed-123">In XAML, create an instance of the collection class and set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md).</span></span>  
  
3.  <span data-ttu-id="f92ed-124">In XAML, creare un'istanza di <xref:System.Windows.Data.CollectionViewSource> , impostare il [direttiva X:Key](../../../../docs/framework/xaml-services/x-key-directive.md)e impostare l'istanza della classe di raccolta come il <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span><span class="sxs-lookup"><span data-stu-id="f92ed-124">In XAML, create an instance of the <xref:System.Windows.Data.CollectionViewSource> class, set the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md), and set the instance of your collection class as the <xref:System.Windows.Data.CollectionViewSource.Source%2A>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#201](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]  
  
4.  <span data-ttu-id="f92ed-125">Creare un'istanza del <xref:System.Windows.Controls.DataGrid> , quindi impostare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà per il <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="f92ed-125">Create an instance of the <xref:System.Windows.Controls.DataGrid> class, and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#002](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]  
  
5.  <span data-ttu-id="f92ed-126">Per l'accesso di <xref:System.Windows.Data.CollectionViewSource> dal codice, utilizzare il <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> metodo per ottenere un riferimento al <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="f92ed-126">To access the <xref:System.Windows.Data.CollectionViewSource> from your code, use the <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> method to get a reference to the <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
     [!code-vb[DataGrid_GroupSortFilter#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]  
  
## <a name="grouping-items-in-a-datagrid"></a><span data-ttu-id="f92ed-127">Raggruppamento di elementi in un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="f92ed-127">Grouping items in a DataGrid</span></span>  
 <span data-ttu-id="f92ed-128">Per specificare la modalità di raggruppamento di elementi un <xref:System.Windows.Controls.DataGrid>, si utilizza il <xref:System.Windows.Data.PropertyGroupDescription> tipo per raggruppare gli elementi nella visualizzazione origine.</span><span class="sxs-lookup"><span data-stu-id="f92ed-128">To specify how items are grouped in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.Windows.Data.PropertyGroupDescription> type to group the items in the source view.</span></span>  
  
#### <a name="to-group-items-in-a-datagrid-using-xaml"></a><span data-ttu-id="f92ed-129">Per raggruppare gli elementi in un controllo DataGrid tramite XAML</span><span class="sxs-lookup"><span data-stu-id="f92ed-129">To group items in a DataGrid using XAML</span></span>  
  
1.  <span data-ttu-id="f92ed-130">Creare un <xref:System.Windows.Data.PropertyGroupDescription> che specifica la proprietà a Raggruppa per.</span><span class="sxs-lookup"><span data-stu-id="f92ed-130">Create a <xref:System.Windows.Data.PropertyGroupDescription> that specifies the property to group by.</span></span> <span data-ttu-id="f92ed-131">È possibile specificare la proprietà in XAML o nel codice.</span><span class="sxs-lookup"><span data-stu-id="f92ed-131">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="f92ed-132">In XAML, impostare il <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> per il nome della proprietà da raggruppare.</span><span class="sxs-lookup"><span data-stu-id="f92ed-132">In XAML, set the <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> to the name of the property to group by.</span></span>  
  
    2.  <span data-ttu-id="f92ed-133">Nel codice, passare il nome della proprietà per raggruppare in base al costruttore.</span><span class="sxs-lookup"><span data-stu-id="f92ed-133">In code, pass the name of the property to group by to the constructor.</span></span>  
  
2.  <span data-ttu-id="f92ed-134">Aggiungere il <xref:System.Windows.Data.PropertyGroupDescription> per il <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> insieme.</span><span class="sxs-lookup"><span data-stu-id="f92ed-134">Add the <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="f92ed-135">Aggiungere istanze aggiuntive di <xref:System.Windows.Data.PropertyGroupDescription> per il <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> raccolta per aggiungere ulteriori livelli di raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="f92ed-135">Add additional instances of <xref:System.Windows.Data.PropertyGroupDescription> to the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection to add more levels of grouping.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#012](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#112](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
     [!code-vb[DataGrid_GroupSortFilter#112](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]  
  
4.  <span data-ttu-id="f92ed-136">Per rimuovere un gruppo, rimuovere il <xref:System.Windows.Data.PropertyGroupDescription> dal <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> insieme.</span><span class="sxs-lookup"><span data-stu-id="f92ed-136">To remove a group, remove the <xref:System.Windows.Data.PropertyGroupDescription> from the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
5.  <span data-ttu-id="f92ed-137">Per rimuovere tutti i gruppi, chiamare il <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> metodo il <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> insieme.</span><span class="sxs-lookup"><span data-stu-id="f92ed-137">To remove all groups, call the <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> method of the <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> collection.</span></span>  
  
     [!code-csharp[DataGrid_GroupSortFilter#114](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
     [!code-vb[DataGrid_GroupSortFilter#114](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]  
  
 <span data-ttu-id="f92ed-138">Quando gli elementi sono raggruppati nel <xref:System.Windows.Controls.DataGrid>, è possibile definire un <xref:System.Windows.Controls.GroupStyle> che specifica l'aspetto di ogni gruppo.</span><span class="sxs-lookup"><span data-stu-id="f92ed-138">When items are grouped in the <xref:System.Windows.Controls.DataGrid>, you can define a <xref:System.Windows.Controls.GroupStyle> that specifies the appearance of each group.</span></span> <span data-ttu-id="f92ed-139">Si applica il <xref:System.Windows.Controls.GroupStyle> aggiungendolo al <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> insieme di DataGrid.</span><span class="sxs-lookup"><span data-stu-id="f92ed-139">You apply the <xref:System.Windows.Controls.GroupStyle> by adding it to the <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> collection of the DataGrid.</span></span> <span data-ttu-id="f92ed-140">Se si dispone di più livelli di raggruppamento, è possibile applicare stili a ogni livello di gruppo.</span><span class="sxs-lookup"><span data-stu-id="f92ed-140">If you have multiple levels of grouping, you can apply different styles to each group level.</span></span> <span data-ttu-id="f92ed-141">Gli stili vengono applicati nell'ordine in cui sono definiti.</span><span class="sxs-lookup"><span data-stu-id="f92ed-141">Styles are applied in the order in which they are defined.</span></span> <span data-ttu-id="f92ed-142">Ad esempio, se si definiscono due stili, il primo verrà applicato ai gruppi di righe di livello superiore.</span><span class="sxs-lookup"><span data-stu-id="f92ed-142">For example, if you define two styles, the first will be applied to top level row groups.</span></span> <span data-ttu-id="f92ed-143">Il secondo stile sarà applicato a tutti i gruppi di righe al secondo livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="f92ed-143">The second style will be applied to all row groups at the second level and lower.</span></span> <span data-ttu-id="f92ed-144">Il <xref:System.Windows.FrameworkElement.DataContext%2A> del <xref:System.Windows.Controls.GroupStyle> è il <xref:System.Windows.Data.CollectionViewGroup> che rappresenta il gruppo.</span><span class="sxs-lookup"><span data-stu-id="f92ed-144">The <xref:System.Windows.FrameworkElement.DataContext%2A> of the <xref:System.Windows.Controls.GroupStyle> is the <xref:System.Windows.Data.CollectionViewGroup> that the group represents.</span></span>  
  
#### <a name="to-change-the-appearance-of-row-group-headers"></a><span data-ttu-id="f92ed-145">Per modificare l'aspetto delle intestazioni di riga gruppo</span><span class="sxs-lookup"><span data-stu-id="f92ed-145">To change the appearance of row group headers</span></span>  
  
1.  <span data-ttu-id="f92ed-146">Creare un <xref:System.Windows.Controls.GroupStyle> che definisce l'aspetto del gruppo di righe.</span><span class="sxs-lookup"><span data-stu-id="f92ed-146">Create a <xref:System.Windows.Controls.GroupStyle> that defines the appearance of the row group.</span></span>  
  
2.  <span data-ttu-id="f92ed-147">Inserire il <xref:System.Windows.Controls.GroupStyle> all'interno di `<DataGrid.GroupStyle>` tag.</span><span class="sxs-lookup"><span data-stu-id="f92ed-147">Put the <xref:System.Windows.Controls.GroupStyle> inside the `<DataGrid.GroupStyle>` tags.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#003](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]  
  
## <a name="sorting-items-in-a-datagrid"></a><span data-ttu-id="f92ed-148">Ordinamento degli elementi in un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="f92ed-148">Sorting items in a DataGrid</span></span>  
 <span data-ttu-id="f92ed-149">Per specificare la modalità con cui gli elementi vengono ordinati un <xref:System.Windows.Controls.DataGrid>, si utilizza il <xref:System.ComponentModel.SortDescription> tipo per ordinare gli elementi nella visualizzazione origine.</span><span class="sxs-lookup"><span data-stu-id="f92ed-149">To specify how items are sorted in a <xref:System.Windows.Controls.DataGrid>, you use the <xref:System.ComponentModel.SortDescription> type to sort the items in the source view.</span></span>  
  
#### <a name="to-sort-items-in-a-datagrid"></a><span data-ttu-id="f92ed-150">Per ordinare gli elementi in un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="f92ed-150">To sort items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="f92ed-151">Creare un <xref:System.ComponentModel.SortDescription> che specifica la proprietà di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="f92ed-151">Create a <xref:System.ComponentModel.SortDescription> that specifies the property to sort by.</span></span> <span data-ttu-id="f92ed-152">È possibile specificare la proprietà in XAML o nel codice.</span><span class="sxs-lookup"><span data-stu-id="f92ed-152">You can specify the property in XAML or in code.</span></span>  
  
    1.  <span data-ttu-id="f92ed-153">In XAML, impostare il <xref:System.ComponentModel.SortDescription.PropertyName%2A> per il nome della proprietà da ordinare.</span><span class="sxs-lookup"><span data-stu-id="f92ed-153">In XAML, set the <xref:System.ComponentModel.SortDescription.PropertyName%2A> to the name of the property to sort by.</span></span>  
  
    2.  <span data-ttu-id="f92ed-154">Nel codice, passare il nome della proprietà di ordinamento e <xref:System.ComponentModel.ListSortDirection> al costruttore.</span><span class="sxs-lookup"><span data-stu-id="f92ed-154">In code, pass the name of the property to sort by and the <xref:System.ComponentModel.ListSortDirection> to the constructor.</span></span>  
  
2.  <span data-ttu-id="f92ed-155">Aggiungere il <xref:System.ComponentModel.SortDescription> per il <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> insieme.</span><span class="sxs-lookup"><span data-stu-id="f92ed-155">Add the <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> collection.</span></span>  
  
3.  <span data-ttu-id="f92ed-156">Aggiungere istanze aggiuntive di <xref:System.ComponentModel.SortDescription> per il <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> insieme in base a proprietà aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="f92ed-156">Add additional instances of <xref:System.ComponentModel.SortDescription> to the <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> collection to sort by additional properties.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#011](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#211](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
     [!code-vb[DataGrid_GroupSortFilter#211](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]  
  
## <a name="filtering-items-in-a-datagrid"></a><span data-ttu-id="f92ed-157">Filtraggio degli elementi in un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="f92ed-157">Filtering items in a DataGrid</span></span>  
 <span data-ttu-id="f92ed-158">Per filtrare gli elementi in un <xref:System.Windows.Controls.DataGrid> utilizzando un <xref:System.Windows.Data.CollectionViewSource>, è fornire la logica di filtro nel gestore per il <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="f92ed-158">To filter items in a <xref:System.Windows.Controls.DataGrid> using a <xref:System.Windows.Data.CollectionViewSource>, you provide the filtering logic in the handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
#### <a name="to-filter-items-in-a-datagrid"></a><span data-ttu-id="f92ed-159">Per filtrare gli elementi in un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="f92ed-159">To filter items in a DataGrid</span></span>  
  
1.  <span data-ttu-id="f92ed-160">Aggiungere un gestore per il <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> evento.</span><span class="sxs-lookup"><span data-stu-id="f92ed-160">Add a handler for the <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> event.</span></span>  
  
2.  <span data-ttu-id="f92ed-161">Nel <xref:System.Windows.Data.CollectionViewSource.Filter> gestore eventi, definire la logica di filtro.</span><span class="sxs-lookup"><span data-stu-id="f92ed-161">In the <xref:System.Windows.Data.CollectionViewSource.Filter> event handler, define the filtering logic.</span></span>  
  
     <span data-ttu-id="f92ed-162">Il filtro verrà applicato ogni volta che viene aggiornata la visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f92ed-162">The filter will be applied every time the view is refreshed.</span></span>  
  
     [!code-xaml[DataGrid_GroupSortFilter#013](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]  
  
     [!code-csharp[DataGrid_GroupSortFilter#113](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
     [!code-vb[DataGrid_GroupSortFilter#113](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]  
  
 <span data-ttu-id="f92ed-163">In alternativa, è possibile filtrare gli elementi in un <xref:System.Windows.Controls.DataGrid> mediante la creazione di un metodo che fornisce la logica di filtro e l'impostazione di <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> proprietà a cui applicare il filtro.</span><span class="sxs-lookup"><span data-stu-id="f92ed-163">Alternatively, you can filter items in a <xref:System.Windows.Controls.DataGrid> by creating a method that provides the filtering logic and setting the <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> property to apply the filter.</span></span> <span data-ttu-id="f92ed-164">Per un esempio di questo metodo, vedere [filtrare i dati in una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span><span class="sxs-lookup"><span data-stu-id="f92ed-164">To see an example of this method, see [Filter Data in a View](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f92ed-165">Esempio</span><span class="sxs-lookup"><span data-stu-id="f92ed-165">Example</span></span>  
 <span data-ttu-id="f92ed-166">L'esempio seguente illustra il raggruppamento, ordinamento e filtro `Task` dati in un <xref:System.Windows.Data.CollectionViewSource> e la visualizzazione raggruppati, ordinati e filtrati `Task` dati in un <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="f92ed-166">The following example demonstrates grouping, sorting, and filtering `Task` data in a <xref:System.Windows.Data.CollectionViewSource> and displaying the grouped, sorted, and filtered `Task` data in a <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="f92ed-167">Il <xref:System.Windows.Data.CollectionViewSource> viene utilizzato come il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per il <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="f92ed-167">The <xref:System.Windows.Data.CollectionViewSource> is used as the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="f92ed-168">Il raggruppamento, ordinamento e filtro vengono eseguite sul <xref:System.Windows.Data.CollectionViewSource> e vengono visualizzati nel <xref:System.Windows.Controls.DataGrid> dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="f92ed-168">Grouping, sorting, and filtering are performed on the <xref:System.Windows.Data.CollectionViewSource> and are displayed in the <xref:System.Windows.Controls.DataGrid> UI.</span></span>  
  
 <span data-ttu-id="f92ed-169">Per testare questo esempio, è necessario modificare il nome DGGroupSortFilterExample in modo che corrisponda al nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="f92ed-169">To test this example, you will need to adjust the DGGroupSortFilterExample name to match your project name.</span></span> <span data-ttu-id="f92ed-170">Se si utilizza Visual Basic, sarà necessario modificare il nome di classe per <xref:System.Windows.Window> al seguente.</span><span class="sxs-lookup"><span data-stu-id="f92ed-170">If you are using Visual Basic, you will need to change the class name for <xref:System.Windows.Window> to the following.</span></span>  
  
 `<Window x:Class="MainWindow"`  
  
 [!code-xaml[DataGrid_GroupSortFilter#000](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]  
  
 [!code-csharp[DataGrid_GroupSortFilter#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
 [!code-vb[DataGrid_GroupSortFilter#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f92ed-171">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f92ed-171">Compiling the Code</span></span>  
  
-  
  
## <a name="robust-programming"></a><span data-ttu-id="f92ed-172">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="f92ed-172">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f92ed-173">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f92ed-173">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f92ed-174">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f92ed-174">See Also</span></span>  
 [<span data-ttu-id="f92ed-175">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="f92ed-175">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="f92ed-176">Creare ed eseguire l'associazione a una classe ObservableCollection</span><span class="sxs-lookup"><span data-stu-id="f92ed-176">Create and Bind to an ObservableCollection</span></span>](../../../../docs/framework/wpf/data/how-to-create-and-bind-to-an-observablecollection.md)  
 [<span data-ttu-id="f92ed-177">Filtrare i dati di una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="f92ed-177">Filter Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [<span data-ttu-id="f92ed-178">Ordinare i dati in una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="f92ed-178">Sort Data in a View</span></span>](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [<span data-ttu-id="f92ed-179">Ordinare e raggruppare dati con una visualizzazione in XAML</span><span class="sxs-lookup"><span data-stu-id="f92ed-179">Sort and Group Data Using a View in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
