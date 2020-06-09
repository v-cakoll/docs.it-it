---
title: 'Procedura dettagliata: Visualizzare i dati di un database di SQL Server in un controllo DataGrid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
ms.openlocfilehash: 1398d8408a0b85d6603d638312e92ba35c5e77d3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591033"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="94858-102">Procedura dettagliata: visualizzare i dati di un database di SQL Server in un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="94858-102">Walkthrough: Display data from a SQL Server database in a DataGrid control</span></span>

<span data-ttu-id="94858-103">In questa procedura dettagliata si recuperano i dati da un database di SQL Server e si visualizzano i dati in un <xref:System.Windows.Controls.DataGrid> controllo.</span><span class="sxs-lookup"><span data-stu-id="94858-103">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="94858-104">Usare il Entity Framework ADO.NET per creare le classi di entità che rappresentano i dati e usare LINQ per scrivere una query che recupera i dati specificati da una classe di entità.</span><span class="sxs-lookup"><span data-stu-id="94858-104">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="94858-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="94858-105">Prerequisites</span></span>

<span data-ttu-id="94858-106">Per completare questa procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="94858-106">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="94858-107">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="94858-107">Visual Studio.</span></span>

- <span data-ttu-id="94858-108">Accesso a un'istanza in esecuzione di SQL Server o SQL Server Express a cui è collegato il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="94858-108">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="94858-109">È possibile scaricare il database AdventureWorks da [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span><span class="sxs-lookup"><span data-stu-id="94858-109">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>

## <a name="create-entity-classes"></a><span data-ttu-id="94858-110">Creare classi di entità</span><span class="sxs-lookup"><span data-stu-id="94858-110">Create entity classes</span></span>

1. <span data-ttu-id="94858-111">Creare un nuovo progetto di applicazione WPF in Visual Basic o C# e denominarlo `DataGridSQLExample` .</span><span class="sxs-lookup"><span data-stu-id="94858-111">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>

2. <span data-ttu-id="94858-112">In Esplora soluzioni fare clic con il pulsante destro del mouse sul progetto, scegliere **Aggiungi**, quindi selezionare **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="94858-112">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>

     <span data-ttu-id="94858-113">Verrà visualizzata la finestra di dialogo Aggiungi nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="94858-113">The Add New Item dialog box appears.</span></span>

3. <span data-ttu-id="94858-114">Nel riquadro Modelli installati selezionare **dati** e nell'elenco dei modelli selezionare **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="94858-114">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Model**.</span></span>

     ![Modello di elemento Entity Data Model ADO.NET](../../wcf/feature-details/media/ado-net-entity-data-model-item-template.png)

4. <span data-ttu-id="94858-116">Assegnare un nome al file `AdventureWorksModel.edmx` e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="94858-116">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>

     <span data-ttu-id="94858-117">Verrà visualizzata la procedura guidata Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="94858-117">The Entity Data Model Wizard appears.</span></span>

5. <span data-ttu-id="94858-118">Nella schermata Scegli contenuto Model selezionare **EF Designer from database** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="94858-118">In the Choose Model Contents screen, select **EF Designer from database** and then click **Next**.</span></span>

6. <span data-ttu-id="94858-119">Nella schermata scegliere la connessione dati specificare la connessione al database di AdventureWorksLT2008.</span><span class="sxs-lookup"><span data-stu-id="94858-119">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="94858-120">Per ulteriori informazioni, vedere [la finestra di dialogo scegliere la connessione dati](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="94858-120">For more information, see [Choose Your Data Connection Dialog Box](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399244(v=vs.100)).</span></span>

    <span data-ttu-id="94858-121">Verificare che il nome sia `AdventureWorksLT2008Entities` e che la casella di controllo **Salva le impostazioni di connessione dell'entità in app. config come** sia selezionata, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="94858-121">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>

7. <span data-ttu-id="94858-122">Nella schermata Seleziona oggetti di database espandere il nodo tabelle e selezionare le tabelle **Product** e **ProductCategory** .</span><span class="sxs-lookup"><span data-stu-id="94858-122">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>

     <span data-ttu-id="94858-123">È possibile generare classi di entità per tutte le tabelle. Tuttavia, in questo esempio vengono recuperati solo i dati da queste due tabelle.</span><span class="sxs-lookup"><span data-stu-id="94858-123">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>

     <span data-ttu-id="94858-124">![Selezionare Product e ProductCategory dalle tabelle](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="94858-124">![Select Product and ProductCategory from tables](./media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>

8. <span data-ttu-id="94858-125">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="94858-125">Click **Finish**.</span></span>

     <span data-ttu-id="94858-126">Le entità Product e ProductCategory vengono visualizzate nel Entity Designer.</span><span class="sxs-lookup"><span data-stu-id="94858-126">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>

     <span data-ttu-id="94858-127">![Modelli di entità Product e ProductCategory](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="94858-127">![Product and ProductCategory entity models](./media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>

## <a name="retrieve-and-present-the-data"></a><span data-ttu-id="94858-128">Recuperare e presentare i dati</span><span class="sxs-lookup"><span data-stu-id="94858-128">Retrieve and present the data</span></span>

1. <span data-ttu-id="94858-129">Aprire il file MainWindow. XAML.</span><span class="sxs-lookup"><span data-stu-id="94858-129">Open the MainWindow.xaml file.</span></span>

2. <span data-ttu-id="94858-130">Impostare la <xref:System.Windows.FrameworkElement.Width%2A> proprietà su <xref:System.Windows.Window> 450.</span><span class="sxs-lookup"><span data-stu-id="94858-130">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>

3. <span data-ttu-id="94858-131">Nell'editor XAML aggiungere il <xref:System.Windows.Controls.DataGrid> tag seguente tra i `<Grid>` `</Grid>` tag e per aggiungere un oggetto <xref:System.Windows.Controls.DataGrid> denominato `dataGrid1` .</span><span class="sxs-lookup"><span data-stu-id="94858-131">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]

     <span data-ttu-id="94858-132">![Finestra con DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="94858-132">![Window with DataGrid](./media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>

4. <span data-ttu-id="94858-133">Selezionare <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="94858-133">Select the <xref:System.Windows.Window>.</span></span>

5. <span data-ttu-id="94858-134">Usando l'Editor Finestra Proprietà o XAML, creare un gestore eventi per il <xref:System.Windows.Window> nome `Window_Loaded` per l' <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="94858-134">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="94858-135">Per altre informazioni, vedere [procedura: creare un gestore eventi semplice](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="94858-135">For more information, see [How to: Create a Simple Event Handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

     <span data-ttu-id="94858-136">Di seguito viene illustrato il codice XAML per MainWindow. XAML.</span><span class="sxs-lookup"><span data-stu-id="94858-136">The following shows the XAML for MainWindow.xaml.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94858-137">Se si usa Visual Basic, nella prima riga di MainWindow. xaml sostituire `x:Class="DataGridSQLExample.MainWindow"` con `x:Class="MainWindow"` .</span><span class="sxs-lookup"><span data-stu-id="94858-137">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>

     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]

6. <span data-ttu-id="94858-138">Aprire il file code-behind (MainWindow. XAML. vb o MainWindow.xaml.cs) per <xref:System.Windows.Window> .</span><span class="sxs-lookup"><span data-stu-id="94858-138">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>

7. <span data-ttu-id="94858-139">Aggiungere il codice seguente per recuperare solo valori specifici dalle tabelle unite in join e impostare la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà di sui <xref:System.Windows.Controls.DataGrid> Risultati della query.</span><span class="sxs-lookup"><span data-stu-id="94858-139">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>

     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]

8. <span data-ttu-id="94858-140">Eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="94858-140">Run the example.</span></span>

     <span data-ttu-id="94858-141">Verrà visualizzato un <xref:System.Windows.Controls.DataGrid> che Visualizza i dati.</span><span class="sxs-lookup"><span data-stu-id="94858-141">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>

     <span data-ttu-id="94858-142">![DataGrid con dati del database SQL](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="94858-142">![DataGrid with data from SQL database](./media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>

## <a name="see-also"></a><span data-ttu-id="94858-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94858-143">See also</span></span>

- <xref:System.Windows.Controls.DataGrid>
