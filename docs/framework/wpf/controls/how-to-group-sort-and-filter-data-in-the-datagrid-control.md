---
title: 'Procedura: raggruppare, ordinare e filtrare dati nel controllo DataGrid'
description: Informazioni su come associare un controllo DataGrid Windows Presentation Foundation a un oggetto CollectionView che supporta il raggruppamento, l'ordinamento e il filtro dei dati nelle visualizzazioni.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], sort
- DataGrid [WPF], group
- DataGrid [WPF], filter
ms.assetid: 03345e85-89e3-4aec-9ed0-3b80759df770
ms.openlocfilehash: 072e5a104a91faa40bb54f2a3fc4ed6188e1112e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167663"
---
# <a name="how-to-group-sort-and-filter-data-in-the-datagrid-control"></a>Procedura: raggruppare, ordinare e filtrare dati nel controllo DataGrid

Spesso è utile visualizzare i dati in un <xref:System.Windows.Controls.DataGrid> in modi diversi raggruppando, ordinando e filtrando i dati. Per raggruppare, ordinare e filtrare i dati in un oggetto <xref:System.Windows.Controls.DataGrid> , è necessario associarli a un oggetto <xref:System.Windows.Data.CollectionView> che supporta queste funzioni. È quindi possibile usare i dati in <xref:System.Windows.Data.CollectionView> senza influire sui dati di origine sottostanti. Le modifiche apportate alla visualizzazione raccolta si riflettono nell' <xref:System.Windows.Controls.DataGrid> interfaccia utente.

La <xref:System.Windows.Data.CollectionView> classe fornisce funzionalità di raggruppamento e ordinamento per un'origine dati che implementa l' <xref:System.Collections.IEnumerable> interfaccia. La <xref:System.Windows.Data.CollectionViewSource> classe consente di impostare le proprietà di un oggetto <xref:System.Windows.Data.CollectionView> da XAML.

In questo esempio, una raccolta di `Task` oggetti è associata a un oggetto <xref:System.Windows.Data.CollectionViewSource> . <xref:System.Windows.Data.CollectionViewSource>Viene utilizzato come <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per l'oggetto <xref:System.Windows.Controls.DataGrid> . Il raggruppamento, l'ordinamento e il filtro vengono eseguiti <xref:System.Windows.Data.CollectionViewSource> in e vengono visualizzati nell' <xref:System.Windows.Controls.DataGrid> interfaccia utente.

![Dati raggruppati in un DataGrid](././media/wpf-datagridgroups.png "WPF_DataGridGroups") Dati raggruppati in un DataGrid

## <a name="using-a-collectionviewsource-as-an-itemssource"></a>Uso di un oggetto CollectionViewSource come ItemsSource

Per raggruppare, ordinare e filtrare i dati in un <xref:System.Windows.Controls.DataGrid> controllo, è necessario associare <xref:System.Windows.Controls.DataGrid> a un oggetto <xref:System.Windows.Data.CollectionView> che supporta queste funzioni. In questo esempio, l'oggetto <xref:System.Windows.Controls.DataGrid> è associato a un oggetto <xref:System.Windows.Data.CollectionViewSource> che fornisce queste funzioni per un oggetto <xref:System.Collections.Generic.List%601> di `Task` oggetti.

### <a name="to-bind-a-datagrid-to-a-collectionviewsource"></a>Per associare un DataGrid a un oggetto CollectionViewSource

1. Creare una raccolta di dati che implementi l' <xref:System.Collections.IEnumerable> interfaccia.

    Se si utilizza <xref:System.Collections.Generic.List%601> per creare la raccolta, è necessario creare una nuova classe che eredita da <xref:System.Collections.Generic.List%601> anziché creare un'istanza di <xref:System.Collections.Generic.List%601> . In questo modo è possibile associare dati alla raccolta in XAML.

    > [!NOTE]
    > Gli oggetti nella raccolta devono implementare l' <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia modificata e l' <xref:System.ComponentModel.IEditableObject> interfaccia affinché il <xref:System.Windows.Controls.DataGrid> risponda correttamente alle modifiche delle proprietà e alle modifiche. Per altre informazioni, vedere [Implementare la notifica di modifiche alle proprietà](../data/how-to-implement-property-change-notification.md).

    [!code-csharp[DataGrid_GroupSortFilter#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#101)]
    [!code-vb[DataGrid_GroupSortFilter#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#101)]

2. In XAML creare un'istanza della classe Collection e impostare la [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md).

3. In XAML creare un'istanza della <xref:System.Windows.Data.CollectionViewSource> classe, impostare la [direttiva x:Key](../../../desktop-wpf/xaml-services/xkey-directive.md)e impostare l'istanza della classe di raccolta come <xref:System.Windows.Data.CollectionViewSource.Source%2A> .

    [!code-xaml[DataGrid_GroupSortFilter#201](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml#201)]

4. Creare un'istanza della <xref:System.Windows.Controls.DataGrid> classe e impostare la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà su <xref:System.Windows.Data.CollectionViewSource> .

    [!code-xaml[DataGrid_GroupSortFilter#002](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#002)]

5. Per accedere al <xref:System.Windows.Data.CollectionViewSource> dal codice, usare il <xref:System.Windows.Data.CollectionViewSource.GetDefaultView%2A> metodo per ottenere un riferimento a <xref:System.Windows.Data.CollectionViewSource> .

    [!code-csharp[DataGrid_GroupSortFilter#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#102)]
    [!code-vb[DataGrid_GroupSortFilter#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#102)]

## <a name="grouping-items-in-a-datagrid"></a>Raggruppamento di elementi in un controllo DataGrid

Per specificare il modo in cui gli elementi vengono raggruppati in un oggetto <xref:System.Windows.Controls.DataGrid> , è possibile utilizzare il <xref:System.Windows.Data.PropertyGroupDescription> tipo per raggruppare gli elementi nella visualizzazione origine.

### <a name="to-group-items-in-a-datagrid-using-xaml"></a>Per raggruppare gli elementi in un DataGrid usando XAML

1. Creare un oggetto <xref:System.Windows.Data.PropertyGroupDescription> che specifica la proprietà in base alla quale eseguire il raggruppamento. È possibile specificare la proprietà in XAML o nel codice.

   1. In XAML, impostare sul <xref:System.Windows.Data.PropertyGroupDescription.PropertyName%2A> nome della proprietà in base alla quale eseguire il raggruppamento.

   2. Nel codice passare il nome della proprietà da raggruppare per il costruttore.

2. Aggiungere alla <xref:System.Windows.Data.PropertyGroupDescription> <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A?displayProperty=nameWithType> raccolta.

3. Aggiungere altre istanze di <xref:System.Windows.Data.PropertyGroupDescription> alla <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> raccolta per aggiungere altri livelli di raggruppamento.

    [!code-xaml[DataGrid_GroupSortFilter#012](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#012)]
    [!code-csharp[DataGrid_GroupSortFilter#112](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#112)]
    [!code-vb[DataGrid_GroupSortFilter#112](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#112)]

4. Per rimuovere un gruppo, rimuovere <xref:System.Windows.Data.PropertyGroupDescription> dalla <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> raccolta.

5. Per rimuovere tutti i gruppi, chiamare il <xref:System.Collections.ObjectModel.Collection%601.Clear%2A> metodo della <xref:System.Windows.Data.CollectionViewSource.GroupDescriptions%2A> raccolta.

    [!code-csharp[DataGrid_GroupSortFilter#114](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#114)]
    [!code-vb[DataGrid_GroupSortFilter#114](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#114)]

Quando gli elementi vengono raggruppati in <xref:System.Windows.Controls.DataGrid> , è possibile definire un oggetto <xref:System.Windows.Controls.GroupStyle> che specifica l'aspetto di ogni gruppo. Per applicare l'oggetto, <xref:System.Windows.Controls.GroupStyle> aggiungerlo alla <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> raccolta del DataGrid. Se si dispone di più livelli di raggruppamento, è possibile applicare stili diversi a ogni livello di gruppo. Gli stili vengono applicati nell'ordine in cui sono definiti. Se, ad esempio, si definiscono due stili, il primo verrà applicato ai gruppi di righe di primo livello. Il secondo stile verrà applicato a tutti i gruppi di righe al secondo livello e a un livello inferiore. Il <xref:System.Windows.FrameworkElement.DataContext%2A> di <xref:System.Windows.Controls.GroupStyle> è l'oggetto <xref:System.Windows.Data.CollectionViewGroup> rappresentato dal gruppo.

### <a name="to-change-the-appearance-of-row-group-headers"></a>Per modificare l'aspetto delle intestazioni dei gruppi di righe

1. Creare un oggetto <xref:System.Windows.Controls.GroupStyle> che definisce l'aspetto del gruppo di righe.

2. Inserire l'oggetto <xref:System.Windows.Controls.GroupStyle> all'interno dei `<DataGrid.GroupStyle>` tag.

    [!code-xaml[DataGrid_GroupSortFilter#003](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#003)]

## <a name="sorting-items-in-a-datagrid"></a>Ordinamento di elementi in un DataGrid

Per specificare la modalità di ordinamento degli elementi in un oggetto <xref:System.Windows.Controls.DataGrid> , è possibile utilizzare il <xref:System.ComponentModel.SortDescription> tipo per ordinare gli elementi nella visualizzazione origine.

### <a name="to-sort-items-in-a-datagrid"></a>Per ordinare gli elementi in un DataGrid

1. Creare un oggetto <xref:System.ComponentModel.SortDescription> che specifica la proprietà in base alla quale eseguire l'ordinamento. È possibile specificare la proprietà in XAML o nel codice.

    1. In XAML, impostare sul <xref:System.ComponentModel.SortDescription.PropertyName%2A> nome della proprietà in base alla quale eseguire l'ordinamento.

    2. Nel codice passare il nome della proprietà da ordinare in base a e al <xref:System.ComponentModel.ListSortDirection> costruttore.

2. Aggiungere alla <xref:System.ComponentModel.SortDescription> <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A?displayProperty=nameWithType> raccolta.

3. Aggiungere altre istanze di <xref:System.ComponentModel.SortDescription> alla <xref:System.Windows.Data.CollectionViewSource.SortDescriptions%2A> raccolta per eseguire l'ordinamento in base a proprietà aggiuntive.

    [!code-xaml[DataGrid_GroupSortFilter#011](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#011)]
    [!code-csharp[DataGrid_GroupSortFilter#211](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/WindowSnips1.xaml.cs#211)]
    [!code-vb[DataGrid_GroupSortFilter#211](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#211)]

## <a name="filtering-items-in-a-datagrid"></a>Filtraggio di elementi in un controllo DataGrid

Per filtrare gli elementi in un oggetto <xref:System.Windows.Controls.DataGrid> utilizzando un oggetto <xref:System.Windows.Data.CollectionViewSource> , è necessario specificare la logica di filtro nel gestore per l' <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> evento.

### <a name="to-filter-items-in-a-datagrid"></a>Per filtrare gli elementi in un DataGrid

1. Aggiungere un gestore per l' <xref:System.Windows.Data.CollectionViewSource.Filter?displayProperty=nameWithType> evento.

2. Nel <xref:System.Windows.Data.CollectionViewSource.Filter> gestore dell'evento definire la logica di filtro.

    Il filtro verrà applicato ogni volta che viene aggiornata la visualizzazione.

    [!code-xaml[DataGrid_GroupSortFilter#013](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#013)]
    [!code-csharp[DataGrid_GroupSortFilter#113](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#113)]
    [!code-vb[DataGrid_GroupSortFilter#113](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#113)]

In alternativa, è possibile filtrare gli elementi in un oggetto <xref:System.Windows.Controls.DataGrid> creando un metodo che fornisce la logica di filtro e impostando la <xref:System.Windows.Data.CollectionView.Filter%2A?displayProperty=nameWithType> proprietà per applicare il filtro. Per vedere un esempio di questo metodo, vedere [filtrare i dati in una visualizzazione](../data/how-to-filter-data-in-a-view.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato il raggruppamento, l'ordinamento e il filtraggio `Task` dei dati in un oggetto <xref:System.Windows.Data.CollectionViewSource> e la visualizzazione dei dati raggruppati, ordinati e filtrati `Task` in un oggetto <xref:System.Windows.Controls.DataGrid> . <xref:System.Windows.Data.CollectionViewSource>Viene utilizzato come <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per l'oggetto <xref:System.Windows.Controls.DataGrid> . Il raggruppamento, l'ordinamento e il filtro vengono eseguiti <xref:System.Windows.Data.CollectionViewSource> in e vengono visualizzati nell' <xref:System.Windows.Controls.DataGrid> interfaccia utente.

Per testare questo esempio, sarà necessario modificare il nome del DGGroupSortFilterExample in modo che corrisponda al nome del progetto. Se si utilizza Visual Basic, sarà necessario modificare il nome della classe per nel <xref:System.Windows.Window> modo seguente.

`<Window x:Class="MainWindow"`

[!code-xaml[DataGrid_GroupSortFilter#000](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml#000)]
[!code-csharp[DataGrid_GroupSortFilter#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_GroupSortFilter/CS/MainWindow.xaml.cs#100)]
[!code-vb[DataGrid_GroupSortFilter#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_GroupSortFilter/VB/MainWindow.xaml.vb#100)]

## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Creare ed eseguire l'associazione a un oggetto ObservableCollection](../data/how-to-create-and-bind-to-an-observablecollection.md)
- [Filtrare i dati in una visualizzazione](../data/how-to-filter-data-in-a-view.md)
- [Ordinare i dati in una visualizzazione](../data/how-to-sort-data-in-a-view.md)
- [Ordinare e raggruppare dati tramite una visualizzazione in XAML](../data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
