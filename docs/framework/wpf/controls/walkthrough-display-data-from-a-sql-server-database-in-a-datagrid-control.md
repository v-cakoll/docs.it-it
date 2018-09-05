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
ms.openlocfilehash: 1421d076ff202ec87a9d861ab2c7d1c1cdcdc1b7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43735078"
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a><span data-ttu-id="ba320-102">Procedura dettagliata: aggiunta di dati di un database di SQL Server in un controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="ba320-102">Walkthrough: Display Data from a SQL Server Database in a DataGrid Control</span></span>
<span data-ttu-id="ba320-103">In questa procedura dettagliata, si recuperano dati da un database di SQL Server e visualizzare questi dati in un <xref:System.Windows.Controls.DataGrid> controllo.</span><span class="sxs-lookup"><span data-stu-id="ba320-103">In this walkthrough, you retrieve data from a SQL Server database and display that data in a <xref:System.Windows.Controls.DataGrid> control.</span></span> <span data-ttu-id="ba320-104">Si usa ADO.NET Entity Framework per creare le classi di entità che rappresentano i dati e usano LINQ per scrivere una query che recupera i dati specificati da una classe di entità.</span><span class="sxs-lookup"><span data-stu-id="ba320-104">You use the ADO.NET Entity Framework to create the entity classes that represent the data, and use LINQ to write a query that retrieves the specified data from an entity class.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ba320-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ba320-105">Prerequisites</span></span>  
 <span data-ttu-id="ba320-106">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba320-106">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="ba320-107">.</span><span class="sxs-lookup"><span data-stu-id="ba320-107">.</span></span>  
  
-   <span data-ttu-id="ba320-108">Accesso a un'istanza di SQL Server o SQL Server Express che è collegato ad esso il database di esempio AdventureWorks in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ba320-108">Access to a running instance of SQL Server or SQL Server Express that has the AdventureWorks sample database attached to it.</span></span> <span data-ttu-id="ba320-109">È possibile scaricare il database AdventureWorks dal [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span><span class="sxs-lookup"><span data-stu-id="ba320-109">You can download the AdventureWorks database from the [GitHub](https://github.com/Microsoft/sql-server-samples/releases).</span></span>  
  
### <a name="to-create-entity-classes"></a><span data-ttu-id="ba320-110">Per creare classi di entità</span><span class="sxs-lookup"><span data-stu-id="ba320-110">To create entity classes</span></span>  
  
1.  <span data-ttu-id="ba320-111">Creare un nuovo progetto di applicazione WPF in Visual Basic o c# e denominarla `DataGridSQLExample`.</span><span class="sxs-lookup"><span data-stu-id="ba320-111">Create a new WPF Application project in Visual Basic or C#, and name it `DataGridSQLExample`.</span></span>  
  
2.  <span data-ttu-id="ba320-112">In Esplora soluzioni, fare clic sul progetto, scegliere **Add**, quindi selezionare **nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="ba320-112">In Solution Explorer, right-click your project, point to **Add**, and then select **New Item**.</span></span>  
  
     <span data-ttu-id="ba320-113">Viene visualizzata la finestra di dialogo Aggiungi nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="ba320-113">The Add New Item dialog box appears.</span></span>  
  
3.  <span data-ttu-id="ba320-114">Nel riquadro dei modelli installati selezionare **Data** nell'elenco dei modelli, selezionare **ADO.NET Entity Data Model**l.</span><span class="sxs-lookup"><span data-stu-id="ba320-114">In the Installed Templates pane, select **Data** and in the list of templates, select **ADO.NET Entity Data Mode**l.</span></span>  
  
     <span data-ttu-id="ba320-115">![Selezionare ADO.NET Entity Data Model](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step1.png "DataGrid_SQL_EF_Step1")</span><span class="sxs-lookup"><span data-stu-id="ba320-115">![Select ADO.NET Entity Data Model](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step1.png "DataGrid_SQL_EF_Step1")</span></span>  
  
4.  <span data-ttu-id="ba320-116">Denominare il file `AdventureWorksModel.edmx` e quindi fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="ba320-116">Name the file `AdventureWorksModel.edmx` and then click **Add**.</span></span>  
  
     <span data-ttu-id="ba320-117">Verrà visualizzata la procedura guidata Entity Data Model.</span><span class="sxs-lookup"><span data-stu-id="ba320-117">The Entity Data Model Wizard appears.</span></span>  
  
5.  <span data-ttu-id="ba320-118">Nella schermata di Scegli contenuto Model, selezionare **genera da database** e quindi fare clic su **successivo**.</span><span class="sxs-lookup"><span data-stu-id="ba320-118">In the Choose Model Contents screen, select **Generate from database** and then click **Next**.</span></span>  
  
     <span data-ttu-id="ba320-119">![Selezionare Generate dall'opzione di database](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step2.png "DataGrid_SQL_EF_Step2")</span><span class="sxs-lookup"><span data-stu-id="ba320-119">![Select Generate from database option](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step2.png "DataGrid_SQL_EF_Step2")</span></span>  
  
6.  <span data-ttu-id="ba320-120">Nella schermata Seleziona connessione dati, specificare la connessione al database AdventureWorksLT2008.</span><span class="sxs-lookup"><span data-stu-id="ba320-120">In the Choose Your Data Connection screen, provide the connection to your AdventureWorksLT2008 database.</span></span> <span data-ttu-id="ba320-121">Per altre informazioni, vedere [dialogo scegliere la connessione dati](https://go.microsoft.com/fwlink/?LinkId=160190).</span><span class="sxs-lookup"><span data-stu-id="ba320-121">For more information, see [Choose Your Data Connection Dialog Box](https://go.microsoft.com/fwlink/?LinkId=160190).</span></span>  
  
     <span data-ttu-id="ba320-122">![Fornire una connessione al database](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step3.png "DataGrid_SQL_EF_Step3")</span><span class="sxs-lookup"><span data-stu-id="ba320-122">![Provide connection to database](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step3.png "DataGrid_SQL_EF_Step3")</span></span>  
  
7.  <span data-ttu-id="ba320-123">Assicurarsi che il nome sia `AdventureWorksLT2008Entities` e che il **Salva impostazioni di connessione entity in App. config come** casella di controllo sia selezionata e quindi fare clic su **successivo**.</span><span class="sxs-lookup"><span data-stu-id="ba320-123">Make sure that the name is `AdventureWorksLT2008Entities` and that the **Save entity connection settings in App.Config as** check box is selected, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="ba320-124">Nella schermata Seleziona oggetti di Database, espandere il nodo tabelle e selezionare il **prodotto** e **ProductCategory** tabelle.</span><span class="sxs-lookup"><span data-stu-id="ba320-124">In the Choose Your Database Objects screen, expand the Tables node, and select the **Product** and **ProductCategory** tables.</span></span>  
  
     <span data-ttu-id="ba320-125">È possibile generare le classi di entità per tutte le tabelle. Tuttavia, in questo esempio è solo recuperare dati da queste due tabelle.</span><span class="sxs-lookup"><span data-stu-id="ba320-125">You can generate entity classes for all of the tables; however, in this example you only retrieve data from those two tables.</span></span>  
  
     <span data-ttu-id="ba320-126">![Selezionare Product e ProductCategory dalle tabelle](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span><span class="sxs-lookup"><span data-stu-id="ba320-126">![Select Product and ProductCategory from tables](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")</span></span>  
  
9. <span data-ttu-id="ba320-127">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="ba320-127">Click **Finish**.</span></span>  
  
     <span data-ttu-id="ba320-128">In Entity Designer vengono visualizzate le entità Product e ProductCategory.</span><span class="sxs-lookup"><span data-stu-id="ba320-128">The Product and ProductCategory entities are displayed in the Entity Designer.</span></span>  
  
     <span data-ttu-id="ba320-129">![Modelli di entità Product e ProductCategory](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span><span class="sxs-lookup"><span data-stu-id="ba320-129">![Product and ProductCategory entity models](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")</span></span>  
  
### <a name="to-retrieve-and-present-the-data"></a><span data-ttu-id="ba320-130">Per recuperare e presentare i dati</span><span class="sxs-lookup"><span data-stu-id="ba320-130">To retrieve and present the data</span></span>  
  
1.  <span data-ttu-id="ba320-131">Aprire il file MainWindow. Xaml.</span><span class="sxs-lookup"><span data-stu-id="ba320-131">Open the MainWindow.xaml file.</span></span>  
  
2.  <span data-ttu-id="ba320-132">Impostare il <xref:System.Windows.FrameworkElement.Width%2A> proprietà di <xref:System.Windows.Window> a 450.</span><span class="sxs-lookup"><span data-stu-id="ba320-132">Set the <xref:System.Windows.FrameworkElement.Width%2A> property on the <xref:System.Windows.Window> to 450.</span></span>  
  
3.  <span data-ttu-id="ba320-133">Nell'editor XAML, aggiungere quanto segue <xref:System.Windows.Controls.DataGrid> tag tra il `<Grid>` e `</Grid>` tag per aggiungere un <xref:System.Windows.Controls.DataGrid> denominato `dataGrid1`.</span><span class="sxs-lookup"><span data-stu-id="ba320-133">In the XAML editor, add the following <xref:System.Windows.Controls.DataGrid> tag between the `<Grid>` and `</Grid>` tags to add a <xref:System.Windows.Controls.DataGrid> named `dataGrid1`.</span></span>  
  
     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]  
  
     <span data-ttu-id="ba320-134">![Finestra con DataGrid](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span><span class="sxs-lookup"><span data-stu-id="ba320-134">![Window with DataGrid](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")</span></span>  
  
4.  <span data-ttu-id="ba320-135">Selezionare <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="ba320-135">Select the <xref:System.Windows.Window>.</span></span>  
  
5.  <span data-ttu-id="ba320-136">Usando la finestra proprietà o l'editor XAML, creare un gestore eventi per il <xref:System.Windows.Window> denominate `Window_Loaded` per il <xref:System.Windows.FrameworkElement.Loaded> evento.</span><span class="sxs-lookup"><span data-stu-id="ba320-136">Using the Properties window or XAML editor, create an event handler for the <xref:System.Windows.Window> named `Window_Loaded` for the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span> <span data-ttu-id="ba320-137">Per altre informazioni, vedere [procedura: creare un gestore eventi semplice](https://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span><span class="sxs-lookup"><span data-stu-id="ba320-137">For more information, see [How to: Create a Simple Event Handler](https://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span></span>  
  
     <span data-ttu-id="ba320-138">Di seguito viene illustrato il XAML per MainWindow. Xaml.</span><span class="sxs-lookup"><span data-stu-id="ba320-138">The following shows the XAML for MainWindow.xaml.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ba320-139">Se si usa Visual Basic, nella prima riga del file MainWindow. XAML, sostituire `x:Class="DataGridSQLExample.MainWindow"` con `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="ba320-139">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="DataGridSQLExample.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]  
  
6.  <span data-ttu-id="ba320-140">Aprire il file code-behind (. Xaml. vb o MainWindow.xaml.cs) per il <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="ba320-140">Open the code-behind file (MainWindow.xaml.vb or MainWindow.xaml.cs) for the <xref:System.Windows.Window>.</span></span>  
  
7.  <span data-ttu-id="ba320-141">Aggiungere il codice seguente per recuperare solo specifici valori dalle tabelle unite in join e impostare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.DataGrid> ai risultati della query.</span><span class="sxs-lookup"><span data-stu-id="ba320-141">Add the following code to retrieve only specific values from the joined tables and set the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.DataGrid> to the results of the query.</span></span>  
  
     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]  
  
8.  <span data-ttu-id="ba320-142">Eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="ba320-142">Run the example.</span></span>  
  
     <span data-ttu-id="ba320-143">Verrà visualizzato un <xref:System.Windows.Controls.DataGrid> che visualizza i dati.</span><span class="sxs-lookup"><span data-stu-id="ba320-143">You should see a <xref:System.Windows.Controls.DataGrid> that displays data.</span></span>  
  
     <span data-ttu-id="ba320-144">![DataGrid con i dati dal database SQL](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span><span class="sxs-lookup"><span data-stu-id="ba320-144">![DataGrid with data from SQL database](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ba320-145">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ba320-145">Next Steps</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba320-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba320-146">See Also</span></span>  
 <xref:System.Windows.Controls.DataGrid>  
 [<span data-ttu-id="ba320-147">Come ricerca per categorie: iniziare a usare Entity Framework nelle applicazioni WPF?</span><span class="sxs-lookup"><span data-stu-id="ba320-147">How Do I: Get Started with Entity Framework in WPF Applications?</span></span>](https://go.microsoft.com/fwlink/?LinkId=159868)
