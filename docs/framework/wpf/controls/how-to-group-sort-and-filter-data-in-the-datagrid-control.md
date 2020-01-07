---
title: 'Procedura: raggruppare, ordinare e filtrare dati nel controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 622b64fd7738b02cd72131e7e9fe91c04314b1d0
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559474"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>Procedura: raggruppare, ordinare e filtrare dati nel controllo DataGrid

Spesso è utile visualizzare i dati in un <xref:System.Windows.Controls.DataGrid> in modi diversi raggruppando, ordinando e filtrando i dati. Per raggruppare, ordinare e filtrare i dati in una <xref:System.Windows.Controls.DataGrid>, è necessario associarli a una <xref:System.Windows.Data.CollectionView> che supporti queste funzioni. È quindi possibile utilizzare i dati nella <xref:System.Windows.Data.CollectionView> senza influire sui dati di origine sottostanti. Le modifiche apportate alla visualizzazione raccolta sono riflesse nell'interfaccia utente di <xref:System.Windows.Controls.DataGrid>.

La classe <xref:System.Windows.Data.CollectionView> fornisce funzionalità di raggruppamento e ordinamento per un'origine dati che implementa l'interfaccia <xref:System.Collections.IEnumerable>. La classe <xref:System.Windows.Data.CollectionViewSource> consente di impostare le proprietà di una <xref:System.Windows.Data.CollectionView> da XAML.

In questo esempio, una raccolta di oggetti `Task` è associata a una <xref:System.Windows.Data.CollectionViewSource>. Il <xref:System.Windows.Data.CollectionViewSource> viene usato come <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per il <xref:System.Windows.Controls.DataGrid>. Il raggruppamento, l'ordinamento e il filtro vengono eseguiti sulla <xref:System.Windows.Data.CollectionViewSource> e vengono visualizzati nell'interfaccia utente di <xref:System.Windows.Controls.DataGrid>.

![Dati raggruppati in un DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") Dati raggruppati in un DataGrid

## <a name="using-a-collectionviewsource-as-an-itemssource"></a>Uso di un oggetto CollectionViewSource come ItemsSource

Per raggruppare, ordinare e filtrare i dati in un controllo <xref:System.Windows.Controls.DataGrid>, associare il <xref:System.Windows.Controls.DataGrid> a una <xref:System.Windows.Data.CollectionView> che supporta queste funzioni. In questo esempio, il <xref:System.Windows.Controls.DataGrid> è associato a una <xref:System.Windows.Data.CollectionViewSource> che fornisce queste funzioni per un <xref:System.Collections.Generic.List%601> di oggetti `Task`.

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>Per associare un DataGrid a un oggetto CollectionViewSource

1. Creare una raccolta di dati che implementi l'interfaccia <xref:System.Collections.IEnumerable>.

    Se si utilizza <xref:System.Collections.Generic.List%601> per creare la raccolta, è necessario creare una nuova classe che erediti da <xref:System.Collections.Generic.List%601> anziché creare un'istanza di <xref:System.Collections.Generic.List%601>. In questo modo è possibile associare dati alla raccolta in XAML.

    > [!NOTE]
    > Gli oggetti nella raccolta devono implementare il <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia modificata e l'interfaccia <xref:System.ComponentModel.IEditableObject> per consentire al <xref:System.Windows.Controls.DataGrid> di rispondere correttamente alle modifiche e alle modifiche delle proprietà. Per altre informazioni, vedere [Implementare la notifica di modifiche alle proprietà](../data/how-to-implement-property-change-notification.md).

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. In XAML creare un'istanza della classe Collection e impostare la [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md).

3. In XAML creare un'istanza della classe <xref:System.Windows.Data.CollectionViewSource>, impostare la [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md)e impostare l'istanza della classe di raccolta come <xref:System.Windows.Data.CollectionViewSource.Source%2A>.

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. Creare un'istanza della classe <xref:System.Windows.Controls.DataGrid> e impostare la proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> sul <xref:System.Windows.Data.CollectionViewSource>.

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. Per accedere al <xref:System.Windows.Data.CollectionViewSource> dal codice, usare il metodo <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> per ottenere un riferimento al <xref:System.Windows.Data.CollectionViewSource>.

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a>Raggruppamento di elementi in un controllo DataGrid

Per specificare il modo in cui gli elementi vengono raggruppati in una <xref:System.Windows.Controls.DataGrid>, è possibile utilizzare il tipo di <xref:System.Windows.Data.PropertyGroupDescription> per raggruppare gli elementi nella visualizzazione origine.

### <a name="to-group-items-in-a-datagrid-using-xaml"></a>Per raggruppare gli elementi in un DataGrid usando XAML

1. Creare una <xref:System.Windows.Data.PropertyGroupDescription> che specifichi la proprietà in base alla quale eseguire il raggruppamento. È possibile specificare la proprietà in XAML o nel codice.

   1. In XAML, impostare il <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> sul nome della proprietà in base alla quale eseguire il raggruppamento.

   2. Nel codice passare il nome della proprietà da raggruppare per il costruttore.

2. Aggiungere la <xref:System.Windows.Data.PropertyGroupDescription> alla raccolta di <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType>.

3. Aggiungere altre istanze di <xref:System.Windows.Data.PropertyGroupDescription> alla raccolta <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> per aggiungere altri livelli di raggruppamento.

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. Per rimuovere un gruppo, rimuovere il <xref:System.Windows.Data.PropertyGroupDescription> dalla raccolta di <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>.

5. Per rimuovere tutti i gruppi, chiamare il metodo <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> della raccolta di <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A>.

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

Quando gli elementi vengono raggruppati nella <xref:System.Windows.Controls.DataGrid>, è possibile definire una <xref:System.Windows.Controls.GroupStyle> che specifichi l'aspetto di ogni gruppo. Per applicare il <xref:System.Windows.Controls.GroupStyle>, aggiungerlo alla raccolta <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> della griglia DataGrid. Se si dispone di più livelli di raggruppamento, è possibile applicare stili diversi a ogni livello di gruppo. Gli stili vengono applicati nell'ordine in cui sono definiti. Se, ad esempio, si definiscono due stili, il primo verrà applicato ai gruppi di righe di primo livello. Il secondo stile verrà applicato a tutti i gruppi di righe al secondo livello e a un livello inferiore. Il <xref:System.Windows.FrameworkElement.DataContext%2A> del <xref:System.Windows.Controls.GroupStyle> è il <xref:System.Windows.Data.CollectionViewGroup> rappresentato dal gruppo.

### <a name="to-change-the-appearance-of-row-group-headers"></a>Per modificare l'aspetto delle intestazioni dei gruppi di righe

1. Creare una <xref:System.Windows.Controls.GroupStyle> che definisce l'aspetto del gruppo di righe.

2. Inserire la <xref:System.Windows.Controls.GroupStyle> all'interno dei tag `<DataGrid.GroupStyle>`.

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a>Ordinamento di elementi in un DataGrid

Per specificare la modalità di ordinamento degli elementi in una <xref:System.Windows.Controls.DataGrid>, è possibile utilizzare il tipo di <xref:System.ComponentModel.SortDescription> per ordinare gli elementi nella visualizzazione origine.

### <a name="to-sort-items-in-a-datagrid"></a>Per ordinare gli elementi in un DataGrid

1. Creare una <xref:System.ComponentModel.SortDescription> che specifichi la proprietà in base alla quale eseguire l'ordinamento. È possibile specificare la proprietà in XAML o nel codice.

    1. In XAML impostare il <xref:System.ComponentModel.SortDescription.PropertyName%2A> sul nome della proprietà in base a cui eseguire l'ordinamento.

    2. Nel codice passare il nome della proprietà in base alla quale eseguire l'ordinamento e il <xref:System.ComponentModel.ListSortDirection> al costruttore.

2. Aggiungere la <xref:System.ComponentModel.SortDescription> alla raccolta di <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType>.

3. Aggiungere altre istanze di <xref:System.ComponentModel.SortDescription> alla raccolta <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> per eseguire l'ordinamento in base a proprietà aggiuntive.

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a>Filtraggio di elementi in un controllo DataGrid

Per filtrare gli elementi di una <xref:System.Windows.Controls.DataGrid> usando un <xref:System.Windows.Data.CollectionViewSource>, è necessario specificare la logica di filtro nel gestore per l'evento <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType>.

### <a name="to-filter-items-in-a-datagrid"></a>Per filtrare gli elementi in un DataGrid

1. Aggiungere un gestore per l'evento <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType>.

2. Nel gestore dell'evento <xref:System.Windows.Data.CollectionViewSource.Filter> definire la logica di filtro.

    Il filtro verrà applicato ogni volta che viene aggiornata la visualizzazione.

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

In alternativa, è possibile filtrare gli elementi in un <xref:System.Windows.Controls.DataGrid> creando un metodo che fornisce la logica di filtro e impostando la proprietà <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> per applicare il filtro. Per vedere un esempio di questo metodo, vedere [filtrare i dati in una visualizzazione](../data/how-to-filter-data-in-a-view.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato il raggruppamento, l'ordinamento e il filtro dei dati `Task` in un <xref:System.Windows.Data.CollectionViewSource> e la visualizzazione dei dati di `Task` raggruppati, ordinati e filtrati in una <xref:System.Windows.Controls.DataGrid>. Il <xref:System.Windows.Data.CollectionViewSource> viene usato come <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per il <xref:System.Windows.Controls.DataGrid>. Il raggruppamento, l'ordinamento e il filtro vengono eseguiti sulla <xref:System.Windows.Data.CollectionViewSource> e vengono visualizzati nell'interfaccia utente di <xref:System.Windows.Controls.DataGrid>.

Per testare questo esempio, sarà necessario modificare il nome del DGGroupSortFilterExample in modo che corrisponda al nome del progetto. Se si utilizza Visual Basic, sarà necessario modificare il nome della classe per <xref:System.Windows.Window> come riportato di seguito.

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'associazione dati](../../../desktop-wpf/data/data-binding-overview.md)
- [Creare ed eseguire l'associazione a una classe ObservableCollection](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [Filtrare i dati di una visualizzazione](../data/how-to-filter-data-in-a-view.md)
- [Ordinare i dati in una visualizzazione](../data/how-to-sort-data-in-a-view.md)
- [Ordinare e raggruppare dati con una visualizzazione in XAML](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
