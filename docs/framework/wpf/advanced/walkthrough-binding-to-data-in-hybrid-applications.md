---
title: 'Procedura dettagliata: associazione ai dati in applicazioni ibride'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: 1bb38436049e338ab6033ae3b6370732a457d520
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794218"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="bf6e3-102">Procedura dettagliata: associazione ai dati in applicazioni ibride</span><span class="sxs-lookup"><span data-stu-id="bf6e3-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>

<span data-ttu-id="bf6e3-103">Il binding di un'origine dati a un controllo è essenziale per consentire agli utenti di accedere ai dati sottostanti, indipendentemente dal fatto che si utilizzino Windows Forms o [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf6e3-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using Windows Forms or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="bf6e3-104">Questa procedura dettagliata illustra come è possibile usare data binding in applicazioni ibride che includono controlli sia Windows Forms che [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf6e3-104">This walkthrough shows how you can use data binding in hybrid applications that include both Windows Forms and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>

<span data-ttu-id="bf6e3-105">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf6e3-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="bf6e3-106">Creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-106">Creating the project.</span></span>

- <span data-ttu-id="bf6e3-107">Definizione del modello dati.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-107">Defining the data template.</span></span>

- <span data-ttu-id="bf6e3-108">Specifica del layout del form.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-108">Specifying the form layout.</span></span>

- <span data-ttu-id="bf6e3-109">Specifica delle associazioni dati.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-109">Specifying data bindings.</span></span>

- <span data-ttu-id="bf6e3-110">Visualizzazione dei dati usando l'interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-110">Displaying data by using interoperation.</span></span>

- <span data-ttu-id="bf6e3-111">Aggiunta dell'origine dati al progetto.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-111">Adding the data source to the project.</span></span>

- <span data-ttu-id="bf6e3-112">Associazione all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-112">Binding to the data source.</span></span>

<span data-ttu-id="bf6e3-113">Per un listato di codice completo delle attività illustrate in questa procedura dettagliata, vedere [esempio di associazione dati in applicazioni ibride](https://go.microsoft.com/fwlink/?LinkID=159983).</span><span class="sxs-lookup"><span data-stu-id="bf6e3-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983).</span></span>

<span data-ttu-id="bf6e3-114">Al termine, si conosceranno le funzionalità di associazione dati nelle applicazioni ibride.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf6e3-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="bf6e3-115">Prerequisites</span></span>

<span data-ttu-id="bf6e3-116">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bf6e3-116">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="bf6e3-117">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-117">Visual Studio.</span></span>

- <span data-ttu-id="bf6e3-118">Accesso al database di esempio Northwind in esecuzione in Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="bf6e3-119">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="bf6e3-119">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="bf6e3-120">Per creare e impostare il progetto</span><span class="sxs-lookup"><span data-stu-id="bf6e3-120">To create and set up the project</span></span>

1. <span data-ttu-id="bf6e3-121">Creare un progetto di applicazione WPF denominato `WPFWithWFAndDatabinding`.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>

2. <span data-ttu-id="bf6e3-122">In Esplora soluzioni aggiungere riferimenti agli assembly seguenti.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-122">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="bf6e3-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="bf6e3-123">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="bf6e3-124">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="bf6e3-124">System.Windows.Forms</span></span>

3. <span data-ttu-id="bf6e3-125">Aprire MainWindow. XAML in WPF Designer.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-125">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="bf6e3-126">Nell'elemento <xref:System.Windows.Window> aggiungere il mapping degli spazi dei nomi Windows Forms seguente.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-126">In the <xref:System.Windows.Window> element, add the following Windows Forms namespaces mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="bf6e3-127">Denominare l'elemento predefinito <xref:System.Windows.Controls.Grid> `mainGrid` assegnando la proprietà <xref:System.Windows.FrameworkElement.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a><span data-ttu-id="bf6e3-128">Definizione del modello dati</span><span class="sxs-lookup"><span data-stu-id="bf6e3-128">Defining the Data Template</span></span>

<span data-ttu-id="bf6e3-129">L'elenco principale dei clienti viene visualizzato in un controllo <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="bf6e3-130">Nell'esempio di codice seguente viene definito un oggetto <xref:System.Windows.DataTemplate> denominato `ListItemsTemplate` che controlla la struttura ad albero visuale del controllo <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="bf6e3-131">Questo <xref:System.Windows.DataTemplate> viene assegnato alla proprietà <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> del controllo <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>

### <a name="to-define-the-data-template"></a><span data-ttu-id="bf6e3-132">Per definire il modello di dati</span><span class="sxs-lookup"><span data-stu-id="bf6e3-132">To define the data template</span></span>

- <span data-ttu-id="bf6e3-133">Copiare il codice XAML seguente nella dichiarazione dell'elemento <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a><span data-ttu-id="bf6e3-134">Specifica del layout del form</span><span class="sxs-lookup"><span data-stu-id="bf6e3-134">Specifying the Form Layout</span></span>

<span data-ttu-id="bf6e3-135">Il layout del form è definito da una griglia con tre righe e tre colonne.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="bf6e3-136">per identificare ogni colonna della tabella Customers sono disponibili controlli <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>

### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="bf6e3-137">Per impostare il layout Grid</span><span class="sxs-lookup"><span data-stu-id="bf6e3-137">To set up the Grid layout</span></span>

- <span data-ttu-id="bf6e3-138">Copiare il codice XAML seguente nella dichiarazione dell'elemento <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="bf6e3-139">Per impostare i controlli Label</span><span class="sxs-lookup"><span data-stu-id="bf6e3-139">To set up the Label controls</span></span>

- <span data-ttu-id="bf6e3-140">Copiare il codice XAML seguente nella dichiarazione dell'elemento <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a><span data-ttu-id="bf6e3-141">Specifica delle associazioni dati</span><span class="sxs-lookup"><span data-stu-id="bf6e3-141">Specifying Data Bindings</span></span>

<span data-ttu-id="bf6e3-142">L'elenco principale dei clienti viene visualizzato in un controllo <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="bf6e3-143">Il `ListItemsTemplate` collegato associa un controllo <xref:System.Windows.Controls.TextBlock> al campo `ContactName` dal database.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>

<span data-ttu-id="bf6e3-144">I dettagli di ogni record cliente vengono visualizzati in diversi controlli <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>

### <a name="to-specify-data-bindings"></a><span data-ttu-id="bf6e3-145">Per specificare le associazioni dati</span><span class="sxs-lookup"><span data-stu-id="bf6e3-145">To specify data bindings</span></span>

- <span data-ttu-id="bf6e3-146">Copiare il codice XAML seguente nella dichiarazione dell'elemento <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     <span data-ttu-id="bf6e3-147">La classe <xref:System.Windows.Data.Binding> associa i controlli <xref:System.Windows.Controls.TextBox> ai campi appropriati nel database.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="bf6e3-148">Visualizzazione dei dati utilizzando l'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="bf6e3-148">Displaying Data by Using Interoperation</span></span>

<span data-ttu-id="bf6e3-149">Gli ordini corrispondenti al cliente selezionato vengono visualizzati in un controllo <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> denominato `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="bf6e3-150">Il controllo `dataGridView1` viene associato all'origine dati nel file code-behind.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="bf6e3-151">Un controllo <xref:System.Windows.Forms.Integration.WindowsFormsHost> è l'elemento padre di questo controllo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this Windows Forms control.</span></span>

### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="bf6e3-152">Per visualizzare i dati nel controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="bf6e3-152">To display data in the DataGridView control</span></span>

- <span data-ttu-id="bf6e3-153">Copiare il codice XAML seguente nella dichiarazione dell'elemento <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="bf6e3-154">Aggiunta dell'origine dati al progetto</span><span class="sxs-lookup"><span data-stu-id="bf6e3-154">Adding the Data Source to the Project</span></span>

<span data-ttu-id="bf6e3-155">Con Visual Studio è possibile aggiungere facilmente un'origine dati al progetto.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-155">With Visual Studio, you can easily add a data source to your project.</span></span> <span data-ttu-id="bf6e3-156">Con questa procedura vengono aggiunti dati fortemente tipizzati al progetto.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="bf6e3-157">Vengono anche aggiunte altre classi di supporto, ad esempio adattatori di tabelle.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="bf6e3-158">Per aggiungere l'origine dati</span><span class="sxs-lookup"><span data-stu-id="bf6e3-158">To add the data source</span></span>

1. <span data-ttu-id="bf6e3-159">Scegliere **Aggiungi nuova origine dati**dal menu **dati** .</span><span class="sxs-lookup"><span data-stu-id="bf6e3-159">From the **Data** menu, select **Add New Data Source**.</span></span>

2. <span data-ttu-id="bf6e3-160">Nella **Configurazione guidata origine dati**creare una connessione al database Northwind utilizzando un set di dati.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="bf6e3-161">Per altre informazioni, vedere [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="bf6e3-161">For more information, see [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span></span>

3. <span data-ttu-id="bf6e3-162">Quando viene richiesta la **Configurazione guidata origine dati**, salvare la stringa di connessione come `NorthwindConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>

4. <span data-ttu-id="bf6e3-163">Quando viene richiesto di scegliere gli oggetti di database, selezionare le tabelle `Customers` e `Orders` e denominare il set di dati generato `NorthwindDataSet`.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>

## <a name="binding-to-the-data-source"></a><span data-ttu-id="bf6e3-164">Associazione all'origine dati</span><span class="sxs-lookup"><span data-stu-id="bf6e3-164">Binding to the Data Source</span></span>

<span data-ttu-id="bf6e3-165">Il componente <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> fornisce un'interfaccia uniforme per l'origine dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="bf6e3-166">L'associazione all'origine dati è implementata nel file code-behind.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-166">Binding to the data source is implemented in the code-behind file.</span></span>

### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="bf6e3-167">Per associare l'origine dati</span><span class="sxs-lookup"><span data-stu-id="bf6e3-167">To bind to the data source</span></span>

1. <span data-ttu-id="bf6e3-168">Aprire il file code-behind, denominato MainWindow.xaml.vb o MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="bf6e3-169">Copiare il codice seguente nella definizione della classe `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-169">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="bf6e3-170">Questo codice dichiara il componente <xref:System.Windows.Forms.BindingSource> e le classi helper associate che si connettono al database.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. <span data-ttu-id="bf6e3-171">Copiare il seguente codice nel costruttore.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-171">Copy the following code into the constructor.</span></span>

     <span data-ttu-id="bf6e3-172">Questo codice crea e inizializza il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. <span data-ttu-id="bf6e3-173">Aprire MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-173">Open MainWindow.xaml.</span></span>

5. <span data-ttu-id="bf6e3-174">Nella visualizzazione progettazione o nella visualizzazione XAML Selezionare l'elemento <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="bf6e3-175">Nella Finestra Proprietà fare clic sulla scheda **eventi** .</span><span class="sxs-lookup"><span data-stu-id="bf6e3-175">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="bf6e3-176">Fare doppio clic sull'evento <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="bf6e3-177">Copiare il codice seguente nel gestore eventi <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

     <span data-ttu-id="bf6e3-178">Questo codice assegna il componente <xref:System.Windows.Forms.BindingSource> come contesto dati e popola gli oggetti `Customers` e `Orders` adapter.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. <span data-ttu-id="bf6e3-179">Copiare il codice seguente nella definizione della classe `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-179">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="bf6e3-180">Questo metodo gestisce l'evento <xref:System.Windows.Data.CollectionView.CurrentChanged> e aggiorna l'elemento corrente del data binding.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. <span data-ttu-id="bf6e3-181">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bf6e3-181">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf6e3-182">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf6e3-182">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="bf6e3-183">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bf6e3-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="bf6e3-184">Esempio di associazione dati in applicazioni ibride</span><span class="sxs-lookup"><span data-stu-id="bf6e3-184">Data Binding in Hybrid Applications Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159983)
- [<span data-ttu-id="bf6e3-185">Procedura dettagliata: Hosting di controlli Windows Form compositi in WPF</span><span class="sxs-lookup"><span data-stu-id="bf6e3-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="bf6e3-186">Procedura dettaglia: hosting di un controllo WPF composito in Windows Form</span><span class="sxs-lookup"><span data-stu-id="bf6e3-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
