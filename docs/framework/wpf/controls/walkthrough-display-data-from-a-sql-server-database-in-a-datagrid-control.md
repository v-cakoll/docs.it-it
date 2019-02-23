---
title: 'Procedura dettagliata: Visualizzare i dati da un Database SQL Server in un controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 6cf56a853377a9c062009fb8a4082cd5380905c6
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748414"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a>Procedura dettagliata: Visualizzare i dati da un database di SQL Server in un controllo DataGrid

In questa procedura dettagliata, si recuperano dati da un database di SQL Server e visualizzare questi dati in un <xref:System.Windows.Controls.DataGrid> controllo. Si usa ADO.NET Entity Framework per creare le classi di entità che rappresentano i dati e usano LINQ per scrivere una query che recupera i dati specificati da una classe di entità.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

-   Visual Studio.

-   Accesso a un'istanza di SQL Server o SQL Server Express che è collegato ad esso il database di esempio AdventureWorks in esecuzione. È possibile scaricare il database AdventureWorks dal [GitHub](https://github.com/Microsoft/sql-server-samples/releases).

## <a name="create-entity-classes"></a>Creare classi di entità

1.  Creare un nuovo progetto di applicazione WPF in Visual Basic o c# e denominarla `DataGridSQLExample`.

2.  In Esplora soluzioni, fare clic sul progetto, scegliere **Add**, quindi selezionare **nuovo elemento**.

     Viene visualizzata la finestra di dialogo Aggiungi nuovo elemento.

3.  Nel riquadro dei modelli installati selezionare **Data** nell'elenco dei modelli, selezionare **ADO.NET Entity Data Model**.

     ![Modello di elemento ADO.NET Entity Data Model](../../wcf/feature-details/media/ado-net-entity-data-model-item-template.png)

4.  Denominare il file `AdventureWorksModel.edmx` e quindi fare clic su **Add**.

     Verrà visualizzata la procedura guidata Entity Data Model.

5.  Nella schermata di Scegli contenuto Model, selezionare **Entity Framework Designer dal database** e quindi fare clic su **successivo**.

6.  Nella schermata Seleziona connessione dati, specificare la connessione al database AdventureWorksLT2008. Per altre informazioni, vedere [dialogo scegliere la connessione dati](https://go.microsoft.com/fwlink/?LinkId=160190).

    Assicurarsi che il nome sia `AdventureWorksLT2008Entities` e che il **Salva impostazioni di connessione entity in App. config come** casella di controllo sia selezionata e quindi fare clic su **successivo**.

7.  Nella schermata Seleziona oggetti di Database, espandere il nodo tabelle e selezionare il **prodotto** e **ProductCategory** tabelle.

     È possibile generare le classi di entità per tutte le tabelle. Tuttavia, in questo esempio è solo recuperare dati da queste due tabelle.

     ![Selezionare Product e ProductCategory dalle tabelle](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")

8. Scegliere **Fine**.

     In Entity Designer vengono visualizzate le entità Product e ProductCategory.

     ![Modelli di entità Product e ProductCategory](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")

## <a name="retrieve-and-present-the-data"></a>Recuperare e presentare i dati

1.  Aprire il file MainWindow. Xaml.

2.  Impostare il <xref:System.Windows.FrameworkElement.Width%2A> proprietà di <xref:System.Windows.Window> a 450.

3.  Nell'editor XAML, aggiungere quanto segue <xref:System.Windows.Controls.DataGrid> tag tra il `<Grid>` e `</Grid>` tag per aggiungere un <xref:System.Windows.Controls.DataGrid> denominato `dataGrid1`.

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     ![Finestra con DataGrid](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")

4.  Selezionare <xref:System.Windows.Window>.

5.  Usando la finestra proprietà o l'editor XAML, creare un gestore eventi per il <xref:System.Windows.Window> denominate `Window_Loaded` per il <xref:System.Windows.FrameworkElement.Loaded> evento. Per altre informazioni, vedere [Procedura: Creare un gestore eventi semplice](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

     Di seguito viene illustrato il XAML per MainWindow. Xaml.

    > [!NOTE]
    > Se si usa Visual Basic, nella prima riga del file MainWindow. XAML, sostituire `x:Class="DataGridSQLExample.MainWindow"` con `x:Class="MainWindow"`.

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6.  Aprire il file code-behind (. Xaml. vb o MainWindow.xaml.cs) per il <xref:System.Windows.Window>.

7.  Aggiungere il codice seguente per recuperare solo specifici valori dalle tabelle unite in join e impostare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.DataGrid> ai risultati della query.

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8.  Eseguire l'esempio.

     Verrà visualizzato un <xref:System.Windows.Controls.DataGrid> che visualizza i dati.

     ![DataGrid con i dati dal database SQL](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- [Procedura: Introduzione a Entity Framework nelle applicazioni WPF?](https://go.microsoft.com/fwlink/?LinkId=159868)