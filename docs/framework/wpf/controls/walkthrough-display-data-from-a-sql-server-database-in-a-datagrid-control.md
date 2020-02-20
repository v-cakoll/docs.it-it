---
title: 'Procedura dettagliata: aggiunta di dati di un database di SQL Server in un controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: fc8b35c89e76a415529d76db687bc96767384e11
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452123"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a>Procedura dettagliata: visualizzare i dati di un database di SQL Server in un controllo DataGrid

In questa procedura dettagliata si recuperano i dati da un database di SQL Server e si visualizzano i dati in un controllo <xref:System.Windows.Controls.DataGrid>. Usare il Entity Framework ADO.NET per creare le classi di entità che rappresentano i dati e usare LINQ per scrivere una query che recupera i dati specificati da una classe di entità.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:

- Visual Studio.

- Accesso a un'istanza in esecuzione di SQL Server o SQL Server Express a cui è collegato il database di esempio AdventureWorks. È possibile scaricare il database AdventureWorks da [GitHub](https://github.com/Microsoft/sql-server-samples/releases).

## <a name="create-entity-classes"></a>Creare classi di entità

1. Creare un nuovo progetto di applicazione WPF in Visual Basic C#o e denominarlo `DataGridSQLExample`.

2. In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto, scegliere **Aggiungi**, quindi selezionare **nuovo elemento**.

     Verrà visualizzata la finestra di dialogo Aggiungi nuovo elemento.

3. Nel riquadro Modelli installati selezionare **dati** e nell'elenco dei modelli selezionare **ADO.NET Entity Data Model**.

     ![Modello di elemento Entity Data Model ADO.NET](../../wcf/feature-details/./media/ado-net-entity-data-model-item-template.png)

4. Denominare il file `AdventureWorksModel.edmx` e quindi fare clic su **Aggiungi**.

     Viene visualizzata la procedura guidata Entity Data Model.

5. Nella schermata Scegli contenuto Model selezionare **EF Designer from database** e quindi fare clic su **Avanti**.

6. Nella schermata scegliere la connessione dati specificare la connessione al database di AdventureWorksLT2008. Per ulteriori informazioni, vedere [la finestra di dialogo scegliere la connessione dati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100)).

    Verificare che il nome sia `AdventureWorksLT2008Entities` e che la casella di controllo **Salva le impostazioni di connessione dell'entità in app. config come** sia selezionata, quindi fare clic su **Avanti**.

7. Nella schermata Seleziona oggetti di database espandere il nodo tabelle e selezionare le tabelle **Product** e **ProductCategory** .

     È possibile generare classi di entità per tutte le tabelle. Tuttavia, in questo esempio vengono recuperati solo i dati da queste due tabelle.

     ![Selezionare Product e ProductCategory dalle tabelle](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")

8. Fare clic su **Fine**.

     Le entità Product e ProductCategory vengono visualizzate nel Entity Designer.

     ![Modelli di entità Product e ProductCategory](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")

## <a name="retrieve-and-present-the-data"></a>Recuperare e presentare i dati

1. Aprire il file MainWindow. XAML.

2. Impostare la proprietà <xref:System.Windows.FrameworkElement.Width%2A> sul <xref:System.Windows.Window> su 450.

3. Nell'editor XAML aggiungere il tag di <xref:System.Windows.Controls.DataGrid> seguente tra i tag `<Grid>` e `</Grid>` per aggiungere una <xref:System.Windows.Controls.DataGrid> denominata `dataGrid1`.

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     ![Finestra con DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")

4. Selezionare <xref:System.Windows.Window>.

5. Usando l'Editor Finestra Proprietà o XAML, creare un gestore eventi per la <xref:System.Windows.Window> denominata `Window_Loaded` per l'evento <xref:System.Windows.FrameworkElement.Loaded>. Per altre informazioni, vedere [procedura: creare un gestore eventi semplice](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).

     Di seguito viene illustrato il codice XAML per MainWindow. XAML.

    > [!NOTE]
    > Se si usa Visual Basic, nella prima riga di MainWindow. xaml sostituire `x:Class="DataGridSQLExample.MainWindow"` con `x:Class="MainWindow"`.

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. Aprire il file code-behind (MainWindow. XAML. vb o MainWindow.xaml.cs) per la <xref:System.Windows.Window>.

7. Aggiungere il codice seguente per recuperare solo valori specifici dalle tabelle unite in join e impostare la proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> della <xref:System.Windows.Controls.DataGrid> sui risultati della query.

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. Eseguire l'esempio.

     Verrà visualizzato un <xref:System.Windows.Controls.DataGrid> che Visualizza i dati.

     ![DataGrid con dati del database SQL](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
