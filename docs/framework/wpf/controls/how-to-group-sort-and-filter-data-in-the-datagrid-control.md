---
title: 'Procedura: Raggruppare, ordinare e filtrare i dati nel controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 81fdb0a6d5602f612c55d7e790ca9a0fe56c144e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365048"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>Procedura: Raggruppare, ordinare e filtrare dati nel controllo DataGrid

È spesso utile visualizzare i dati in un <xref:System.Windows.Controls.DataGrid> in modi diversi per il raggruppamento, ordinamento e filtro dei dati. Per raggruppare, ordinare e filtrare i dati in un <xref:System.Windows.Controls.DataGrid>, è necessario associarli a un <xref:System.Windows.Data.CollectionView> che supporta queste funzioni. È quindi possibile usare i dati nel <xref:System.Windows.Data.CollectionView> senza modificare l'origine dati sottostante. Le modifiche nella visualizzazione raccolta vengono riflesse nel <xref:System.Windows.Controls.DataGrid> interfaccia utente (UI).

Il <xref:System.Windows.Data.CollectionView> classe fornisce il raggruppamento e ordinamento di funzionalità per un'origine dati che implementa il <xref:System.Collections.IEnumerable> interfaccia. Il <xref:System.Windows.Data.CollectionViewSource> classe consente di impostare le proprietà di un <xref:System.Windows.Data.CollectionView> da XAML.

In questo esempio, una raccolta di `Task` oggetti è associato a un <xref:System.Windows.Data.CollectionViewSource>. Il <xref:System.Windows.Data.CollectionViewSource> viene usato come i <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per il <xref:System.Windows.Controls.DataGrid>. Il raggruppamento, ordinamento e filtro vengono eseguite sul <xref:System.Windows.Data.CollectionViewSource> e vengono visualizzati nel <xref:System.Windows.Controls.DataGrid> dell'interfaccia utente.

![Dati raggruppati in un DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") raggruppati i dati in un controllo DataGrid

## <a name="using-a-collectionviewsource-as-an-itemssource"></a>Usando un oggetto CollectionViewSource come una proprietà ItemsSource

Gruppo, ordinare e filtrare i dati in un <xref:System.Windows.Controls.DataGrid> (controllo), si associa il <xref:System.Windows.Controls.DataGrid> a un <xref:System.Windows.Data.CollectionView> che supporta queste funzioni. In questo esempio, il <xref:System.Windows.Controls.DataGrid> è associato a un <xref:System.Windows.Data.CollectionViewSource> che fornisce queste funzioni per un <xref:System.Collections.Generic.List%601> di `Task` oggetti.

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>Per associare un controllo DataGrid a CollectionViewSource

1. Creare una raccolta di dati che implementa il <xref:System.Collections.IEnumerable> interfaccia.

    Se si usa <xref:System.Collections.Generic.List%601> per creare la raccolta, è necessario creare una nuova classe che eredita da <xref:System.Collections.Generic.List%601> invece di creare un'istanza di <xref:System.Collections.Generic.List%601>. Ciò consente di associare i dati nella raccolta in XAML.

    > [!NOTE]
    > Gli oggetti nella raccolta devono implementare il <xref:System.ComponentModel.INotifyPropertyChanged> modificato interfaccia e il <xref:System.ComponentModel.IEditableObject> interfaccia affinché il <xref:System.Windows.Controls.DataGrid> risponda correttamente alla modifica delle proprietà. Per altre informazioni, vedere [Implementare la notifica di modifiche alle proprietà](../data/how-to-implement-property-change-notification.md).

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. In XAML, creare un'istanza della classe di raccolta e impostare il [direttiva X:Key](../../xaml-services/x-key-directive.md).

3. In XAML, creare un'istanza del <xref:System.Windows.Data.CollectionViewSource> classe, impostare il [direttiva X:Key](../../xaml-services/x-key-directive.md)e impostare l'istanza della classe di insiemi come il <xref:System.Windows.Data.CollectionViewSource.Source%2A>.

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. Creare un'istanza del <xref:System.Windows.Controls.DataGrid> classe e impostare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà di <xref:System.Windows.Data.CollectionViewSource>.

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. Per l'accesso di <xref:System.Windows.Data.CollectionViewSource> dal codice, usare il <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> metodo per ottenere un riferimento al <xref:System.Windows.Data.CollectionViewSource>.

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a>Raggruppamento di elementi in un controllo DataGrid

Per specificare la modalità di raggruppamento degli elementi una <xref:System.Windows.Controls.DataGrid>, si utilizza il <xref:System.Windows.Data.PropertyGroupDescription> tipo per raggruppare gli elementi nella visualizzazione origine.

### <a name="to-group-items-in-a-datagrid-using-xaml"></a>Per raggruppare gli elementi in un DataGrid con XAML

1. Creare un <xref:System.Windows.Data.PropertyGroupDescription> che specifica la proprietà a Raggruppa per. È possibile specificare la proprietà in XAML o nel codice.

   1. In XAML, impostare il <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> al nome della proprietà da raggruppare.

   2. Nel codice, passare il nome della proprietà per raggruppare in base al costruttore.

2. Aggiungere il <xref:System.Windows.Data.PropertyGroupDescription> per il <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> raccolta.

3. Aggiungere altre istanze del <xref:System.Windows.Data.PropertyGroupDescription> per il <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> raccolta per aggiungere ulteriori livelli di raggruppamento.

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. Per rimuovere un gruppo, rimuovere il <xref:System.Windows.Data.PropertyGroupDescription> dal <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> raccolta.

5. Per rimuovere tutti i gruppi, chiamare il <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> metodo di <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> raccolta.

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

Quando gli elementi sono raggruppati nel <xref:System.Windows.Controls.DataGrid>, è possibile definire un <xref:System.Windows.Controls.GroupStyle> che specifica l'aspetto di ogni gruppo. Si applica il <xref:System.Windows.Controls.GroupStyle> aggiungendolo al <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> raccolta di DataGrid. Se si dispone di più livelli di raggruppamento, è possibile applicare stili diversi a ogni livello di gruppo. Gli stili vengono applicati nell'ordine in cui sono definiti. Ad esempio, se si definiscono due stili, il primo verrà applicato ai gruppi di righe di livello superiore. Il secondo stile verrà applicato a tutti i gruppi di righe al secondo livello e inferiore. Il <xref:System.Windows.FrameworkElement.DataContext%2A> del <xref:System.Windows.Controls.GroupStyle> è il <xref:System.Windows.Data.CollectionViewGroup> che rappresenta il gruppo.

### <a name="to-change-the-appearance-of-row-group-headers"></a>Per modificare l'aspetto di intestazioni di gruppo di righe

1. Creare un <xref:System.Windows.Controls.GroupStyle> che definisce l'aspetto del gruppo di righe.

2. Inserire il <xref:System.Windows.Controls.GroupStyle> all'interno di `<DataGrid.GroupStyle>` tag.

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a>Ordinamento degli elementi in un controllo DataGrid

Per specificare la modalità di ordinamento degli elementi una <xref:System.Windows.Controls.DataGrid>, si utilizza il <xref:System.ComponentModel.SortDescription> tipo ordinare gli elementi nella vista origine.

### <a name="to-sort-items-in-a-datagrid"></a>Per ordinare gli elementi in un controllo DataGrid

1. Creare un <xref:System.ComponentModel.SortDescription> che specifica la proprietà da ordinare. È possibile specificare la proprietà in XAML o nel codice.

    1. In XAML, impostare il <xref:System.ComponentModel.SortDescription.PropertyName%2A> al nome della proprietà da ordinare.

    2. Nel codice, passare il nome della proprietà da ordinare e <xref:System.ComponentModel.ListSortDirection> al costruttore.

2. Aggiungere il <xref:System.ComponentModel.SortDescription> per il <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> raccolta.

3. Aggiungere altre istanze di <xref:System.ComponentModel.SortDescription> per il <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> insieme per ordinare le proprietà aggiuntive.

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a>Filtraggio degli elementi in un controllo DataGrid

Per filtrare gli elementi in un <xref:System.Windows.Controls.DataGrid> utilizzando un <xref:System.Windows.Data.CollectionViewSource>, è fornire la logica di filtro nel gestore per il <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> evento.

### <a name="to-filter-items-in-a-datagrid"></a>Per filtrare gli elementi in un controllo DataGrid

1. Aggiungere un gestore per il <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> evento.

2. Nel <xref:System.Windows.Data.CollectionViewSource.Filter> gestore eventi, definire la logica di filtro.

    Il filtro verrà applicato ogni volta che viene aggiornata la visualizzazione.

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

In alternativa, è possibile filtrare gli elementi in un <xref:System.Windows.Controls.DataGrid> mediante la creazione di un metodo che fornisce il filtro per la logica e l'impostazione di <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> proprietà a cui applicare il filtro. Per un esempio di questo metodo, vedere [filtrare i dati in una vista](../data/how-to-filter-data-in-a-view.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato il raggruppamento, ordinamento e filtraggio `Task` dati in un <xref:System.Windows.Data.CollectionViewSource> e la visualizzazione raggruppati, ordinati e filtrati `Task` i dati in un <xref:System.Windows.Controls.DataGrid>. Il <xref:System.Windows.Data.CollectionViewSource> viene usato come i <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per il <xref:System.Windows.Controls.DataGrid>. Il raggruppamento, ordinamento e filtro vengono eseguite sul <xref:System.Windows.Data.CollectionViewSource> e vengono visualizzati nel <xref:System.Windows.Controls.DataGrid> dell'interfaccia utente.

Per testare questo esempio, è necessario modificare il nome DGGroupSortFilterExample in modo che corrisponda al nome del progetto. Se si utilizza Visual Basic, è necessario modificare il nome della classe per <xref:System.Windows.Window> al seguente.

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../data/data-binding-overview.md)
- [Creare ed eseguire l'associazione a una classe ObservableCollection](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [Filtrare i dati di una visualizzazione](../data/how-to-filter-data-in-a-view.md)
- [Ordinare i dati in una visualizzazione](../data/how-to-sort-data-in-a-view.md)
- [Ordinare e raggruppare dati con una visualizzazione in XAML](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
