---
title: "Attività 2: ospitare l'utilità di progettazione del flusso di lavoro"
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 8e4c17ed182cec7748b9a1f11f76ff90aa60c39e
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715783"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="2db2a-102">Attività 2: ospitare l'utilità di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2db2a-102">Task 2: Host the Workflow Designer</span></span>

<span data-ttu-id="2db2a-103">In questo argomento viene descritta la procedura per ospitare un'istanza del Progettazione flussi di lavoro di Windows in un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="2db2a-103">This topic describes the procedure for hosting an instance of the Windows Workflow Designer in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="2db2a-104">Nella procedura viene configurato il controllo **Grid** che contiene la finestra di progettazione, viene creata a livello di codice un'istanza del <xref:System.Activities.Presentation.WorkflowDesigner> che contiene un'attività <xref:System.Activities.Statements.Sequence> predefinita, vengono registrati i metadati della finestra di progettazione per fornire supporto della finestra di progettazione per tutte le attività predefinite e vengono ospitati i progettazione flussi di lavoro nell'applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="2db2a-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the Workflow Designer in the WPF application.</span></span>

## <a name="to-host-the-workflow-designer"></a><span data-ttu-id="2db2a-105">Per ospitare la finestra di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2db2a-105">To host the workflow designer</span></span>

1. <span data-ttu-id="2db2a-106">Aprire il progetto HostingApplication creato nell' [attività 1: creare una nuova applicazione Windows Presentation Foundation](task-1-create-a-new-wpf-app.md).</span><span class="sxs-lookup"><span data-stu-id="2db2a-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md).</span></span>

2. <span data-ttu-id="2db2a-107">Modificare le dimensioni della finestra per semplificare l'utilizzo del Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2db2a-107">Adjust the size of the window to make it easier to use the Workflow Designer.</span></span> <span data-ttu-id="2db2a-108">A tale scopo, selezionare **MainWindow** nella finestra di progettazione, premere F4 per visualizzare la finestra **Proprietà** e, nella sezione del **layout** , impostare la **larghezza** su un valore 600 e l' **altezza** su un valore pari a 350.</span><span class="sxs-lookup"><span data-stu-id="2db2a-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>

3. <span data-ttu-id="2db2a-109">Impostare il nome della griglia selezionando il pannello **griglia** nella finestra di progettazione (fare clic sulla casella all'interno di **MainWindow**) e impostare la proprietà **Name** nella parte superiore della finestra **Proprietà** su "Grid1".</span><span class="sxs-lookup"><span data-stu-id="2db2a-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>

4. <span data-ttu-id="2db2a-110">Nella finestra **Proprietà** fare clic sui puntini di sospensione ( **...** ) accanto alla proprietà `ColumnDefinitions` per aprire la finestra di dialogo **Editor della raccolta** .</span><span class="sxs-lookup"><span data-stu-id="2db2a-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>

5. <span data-ttu-id="2db2a-111">Nella finestra di dialogo **Editor della raccolta** fare clic tre volte sul pulsante **Aggiungi** per inserire tre colonne nel layout.</span><span class="sxs-lookup"><span data-stu-id="2db2a-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="2db2a-112">La prima colonna conterrà la **casella degli strumenti**, la seconda colonna ospiterà il progettazione flussi di lavoro e la terza colonna verrà utilizzata per il controllo proprietà.</span><span class="sxs-lookup"><span data-stu-id="2db2a-112">The first column will contain the **Toolbox**, the second column will host the Workflow Designer, and the third column will be used for the property inspector.</span></span>

6. <span data-ttu-id="2db2a-113">Impostare la proprietà `Width` della colonna intermedia sul valore "4 \*".</span><span class="sxs-lookup"><span data-stu-id="2db2a-113">Set the `Width` property of the middle column to the value "4\*".</span></span>

7. <span data-ttu-id="2db2a-114">Fare clic su **OK** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2db2a-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="2db2a-115">Il codice XAML seguente viene aggiunto al file *MainWindow. XAML* :</span><span class="sxs-lookup"><span data-stu-id="2db2a-115">The following XAML is added to your *MainWindow.xaml* file:</span></span>

    ```xaml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. <span data-ttu-id="2db2a-116">In **Esplora soluzioni**fare clic con il pulsante destro del mouse su *MainWindow. XAML* e selezionare **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="2db2a-116">In **Solution Explorer**, right-click *MainWindow.xaml* and select **View Code**.</span></span> <span data-ttu-id="2db2a-117">Modificare il codice attenendosi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2db2a-117">Modify the code by following these steps:</span></span>

    1. <span data-ttu-id="2db2a-118">Aggiungere gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2db2a-118">Add the following namespaces:</span></span>

        ```csharp
        using System.Activities;
        using System.Activities.Core.Presentation;
        using System.Activities.Presentation;
        using System.Activities.Presentation.Metadata;
        using System.Activities.Presentation.Toolbox;
        using System.Activities.Statements;
        using System.ComponentModel;
        ```

    2. <span data-ttu-id="2db2a-119">Per dichiarare un campo membro privato che contenga un'istanza del <xref:System.Activities.Presentation.WorkflowDesigner>, aggiungere il codice seguente alla classe `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="2db2a-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class:</span></span>

        ```csharp
        public partial class MainWindow : Window
        {
            private WorkflowDesigner wd;

            public MainWindow()
            {
                InitializeComponent();
            }
        }
        ```

    3. <span data-ttu-id="2db2a-120">Aggiungere il metodo `AddDesigner` seguente alla classe `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="2db2a-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="2db2a-121">L'implementazione crea un'istanza del <xref:System.Activities.Presentation.WorkflowDesigner>, aggiunge un'attività <xref:System.Activities.Statements.Sequence> e la inserisce nella colonna centrale della **griglia**Grid1.</span><span class="sxs-lookup"><span data-stu-id="2db2a-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>

        ```csharp
        private void AddDesigner()
        {
            // Create an instance of WorkflowDesigner class.
            this.wd = new WorkflowDesigner();

            // Place the designer canvas in the middle column of the grid.
            Grid.SetColumn(this.wd.View, 1);

            // Load a new Sequence as default.
            this.wd.Load(new Sequence());

            // Add the designer canvas to the grid.
            grid1.Children.Add(this.wd.View);
        }
        ```

    4. <span data-ttu-id="2db2a-122">Registrare i metadati della finestra di progettazione per aggiungere il supporto della finestra di progettazione per tutte le attività incorporate.</span><span class="sxs-lookup"><span data-stu-id="2db2a-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="2db2a-123">In questo modo è possibile trascinare le attività dalla casella degli strumenti all'attività <xref:System.Activities.Statements.Sequence> originale nel Progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="2db2a-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the Workflow Designer.</span></span> <span data-ttu-id="2db2a-124">A tale scopo, aggiungere il metodo `RegisterMetadata` alla classe `MainWindow`:</span><span class="sxs-lookup"><span data-stu-id="2db2a-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class:</span></span>

        ```csharp
        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        <span data-ttu-id="2db2a-125">Per ulteriori informazioni sulla registrazione di ActivityDesigner, vedere [procedura: creare un ActivityDesigner personalizzato](how-to-create-a-custom-activity-designer.md).</span><span class="sxs-lookup"><span data-stu-id="2db2a-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](how-to-create-a-custom-activity-designer.md).</span></span>

    5. <span data-ttu-id="2db2a-126">Nel costruttore della classe `MainWindow`, aggiungere chiamate ai metodi dichiarati precedentemente per registrare i metadati per il supporto della finestra di progettazione e per creare l'oggetto <xref:System.Activities.Presentation.WorkflowDesigner>.</span><span class="sxs-lookup"><span data-stu-id="2db2a-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>

        ```csharp
        public MainWindow()
        {
            InitializeComponent();

            // Register the metadata.
            RegisterMetadata();

            // Add the WFF Designer.
            AddDesigner();
        }
        ```

        > [!NOTE]
        > <span data-ttu-id="2db2a-127">Il metodo `RegisterMetadata` registra i metadati della finestra di progettazione di attività incorporate, inclusa l'attività <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="2db2a-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="2db2a-128">Poiché il metodo `AddDesigner` usa l'attività <xref:System.Activities.Statements.Sequence>, è necessario chiamare innanzitutto il metodo `RegisterMetadata`.</span><span class="sxs-lookup"><span data-stu-id="2db2a-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>

9. <span data-ttu-id="2db2a-129">Premere <kbd>F5</kbd> per compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="2db2a-129">Press <kbd>F5</kbd> to build and run the solution.</span></span>

10. <span data-ttu-id="2db2a-130">Vedere [attività 3: creare i riquadri Casella degli strumenti e PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md) per informazioni su come aggiungere la **casella degli strumenti** e il supporto **PropertyGrid** alla finestra di progettazione flussi di lavoro riallocata.</span><span class="sxs-lookup"><span data-stu-id="2db2a-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="2db2a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2db2a-131">See also</span></span>

- [<span data-ttu-id="2db2a-132">Riallocazione di Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="2db2a-132">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="2db2a-133">Attività 1: Creare una nuova applicazione Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="2db2a-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="2db2a-134">Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="2db2a-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)
