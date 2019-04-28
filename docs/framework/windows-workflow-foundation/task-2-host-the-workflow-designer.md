---
title: 'Attività 2: Ospitare Progettazione flussi di lavoro'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 3f7964e907fe513679e60c18292f07c84128590b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641579"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="9ec36-102">Attività 2: Ospitare Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="9ec36-102">Task 2: Host the Workflow Designer</span></span>
<span data-ttu-id="9ec36-103">In questo argomento viene descritta la procedura per l'hosting di un'istanza di [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="9ec36-103">This topic describes the procedure for hosting an instance of the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="9ec36-104">La procedura consente di configurare il **griglia** controllo che contiene la finestra di progettazione, a livello di codice crea un'istanza del <xref:System.Activities.Presentation.WorkflowDesigner> che contiene un valore predefinito <xref:System.Activities.Statements.Sequence> attività, registra i metadati della finestra di progettazione per fornire supporto di progettazione per attività tutte predefinite e gli host il [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] nella [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9ec36-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in the [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] application.</span></span>  
  
### <a name="to-host-the-workflow-designer"></a><span data-ttu-id="9ec36-105">Per ospitare la finestra di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9ec36-105">To host the workflow designer</span></span>  
  
1. <span data-ttu-id="9ec36-106">Aprire il progetto HostingApplication creato in [attività 1: Creare una nuova applicazione Windows Presentation Foundation](task-1-create-a-new-wpf-app.md).</span><span class="sxs-lookup"><span data-stu-id="9ec36-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md).</span></span>  
  
2. <span data-ttu-id="9ec36-107">Regolare le dimensioni della finestra per semplificare l'uso di [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ec36-107">Adjust the size of the window to make it easier to use the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="9ec36-108">A questo scopo, selezionare **MainWindow** nella finestra di progettazione, premere F4 per visualizzare i **proprietà** finestra e, nella **Layout** sezione non esiste, impostare il **larghezza** su un valore pari a 600 e il **altezza** su un valore di 350.</span><span class="sxs-lookup"><span data-stu-id="9ec36-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>  
  
3. <span data-ttu-id="9ec36-109">Impostare il nome della griglia selezionando il **griglia** pannello nella finestra di progettazione (fare clic sulla casella all'interno del **MainWindow**) e impostando il **nome** proprietà nella parte superiore del  **Proprietà** finestra su "grid1".</span><span class="sxs-lookup"><span data-stu-id="9ec36-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>  
  
4. <span data-ttu-id="9ec36-110">Nel **delle proprietà** finestra, fare clic sui puntini di sospensione (**...** ) accanto al `ColumnDefinitions` per aprire il **Editor della raccolta** nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="9ec36-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>  
  
5. <span data-ttu-id="9ec36-111">Nel **Editor della raccolta** della finestra di dialogo fare clic sui **Add** tre volte per inserire tre colonne nel layout.</span><span class="sxs-lookup"><span data-stu-id="9ec36-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="9ec36-112">La prima colonna conterrà il **della casella degli strumenti**, mentre la seconda ospiterà il [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], e la terza colonna verrà utilizzata per il controllo proprietà.</span><span class="sxs-lookup"><span data-stu-id="9ec36-112">The first column will contain the **Toolbox**, the second column will host the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], and the third column will be used for the property inspector.</span></span>  
  
6. <span data-ttu-id="9ec36-113">Impostare il `Width` proprietà della colonna centrale sul valore "4 \*".</span><span class="sxs-lookup"><span data-stu-id="9ec36-113">Set the `Width` property of the middle column to the value "4\*".</span></span>  
  
7. <span data-ttu-id="9ec36-114">Fare clic su **OK** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="9ec36-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="9ec36-115">Il seguente codice XAML viene aggiunto al file MainWindow.xaml:</span><span class="sxs-lookup"><span data-stu-id="9ec36-115">The following XAML is added to your MainWindow.xaml file:</span></span>  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8. <span data-ttu-id="9ec36-116">Nelle **Esplora soluzioni**, fare doppio clic su MainWindow. XAML e selezionare **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="9ec36-116">In **Solution Explorer**, right-click MainWindow.xaml and select **View Code**.</span></span> <span data-ttu-id="9ec36-117">Modificare il codice attenendosi ai passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ec36-117">Modify the code by following these steps:</span></span>  
  
    1. <span data-ttu-id="9ec36-118">Aggiungere gli spazi dei nomi seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ec36-118">Add the following namespaces:</span></span>  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2. <span data-ttu-id="9ec36-119">Per dichiarare un campo membro privato per contenere un'istanza di <xref:System.Activities.Presentation.WorkflowDesigner>, aggiungere il codice seguente alla classe `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="9ec36-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class.</span></span>  
  
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
  
    3. <span data-ttu-id="9ec36-120">Aggiungere il metodo `AddDesigner` seguente alla classe `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="9ec36-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="9ec36-121">L'implementazione crea un'istanza di <xref:System.Activities.Presentation.WorkflowDesigner>, aggiunge un <xref:System.Activities.Statements.Sequence> attività e lo inserisce nella colonna centrale della grid1 **griglia**.</span><span class="sxs-lookup"><span data-stu-id="9ec36-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>  
  
        ```csharp  
        private void AddDesigner()  
        {  
            //Create an instance of WorkflowDesigner class.  
            this.wd = new WorkflowDesigner();  
  
            //Place the designer canvas in the middle column of the grid.  
            Grid.SetColumn(this.wd.View, 1);  
  
            //Load a new Sequence as default.  
            this.wd.Load(new Sequence());  
  
            //Add the designer canvas to the grid.  
            grid1.Children.Add(this.wd.View);  
        }  
        ```  
  
    4. <span data-ttu-id="9ec36-122">Registrare i metadati della finestra di progettazione per aggiungere il supporto della finestra di progettazione per tutte le attività incorporate.</span><span class="sxs-lookup"><span data-stu-id="9ec36-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="9ec36-123">In questo modo sarà possibile spostare le attività dalla casella degli strumenti all'attività <xref:System.Activities.Statements.Sequence> originale in [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ec36-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="9ec36-124">A tal fine, aggiungere il metodo `RegisterMetadata` alla classe `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="9ec36-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class.</span></span>  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         <span data-ttu-id="9ec36-125">Per altre informazioni sulla registrazione di ActivityDesigner, vedere [come: Creare un ActivityDesigner personalizzato](how-to-create-a-custom-activity-designer.md).</span><span class="sxs-lookup"><span data-stu-id="9ec36-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](how-to-create-a-custom-activity-designer.md).</span></span>  
  
    5. <span data-ttu-id="9ec36-126">Nel costruttore della classe `MainWindow`, aggiungere chiamate ai metodi dichiarati precedentemente per registrare i metadati per il supporto della finestra di progettazione e per creare l'oggetto <xref:System.Activities.Presentation.WorkflowDesigner>.</span><span class="sxs-lookup"><span data-stu-id="9ec36-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>  
  
        ```csharp  
        public MainWindow()  
        {  
            InitializeComponent();  
  
            // Register the metadata  
            RegisterMetadata();  
  
            // Add the WFF Designer  
            AddDesigner();  
        }  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="9ec36-127">Il metodo `RegisterMetadata` registra i metadati della finestra di progettazione di attività incorporate, inclusa l'attività <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="9ec36-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="9ec36-128">Poiché il metodo `AddDesigner` usa l'attività <xref:System.Activities.Statements.Sequence>, è necessario chiamare innanzitutto il metodo `RegisterMetadata`.</span><span class="sxs-lookup"><span data-stu-id="9ec36-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>  
  
9. <span data-ttu-id="9ec36-129">Premere F5 per compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="9ec36-129">Press F5 to build and run the solution.</span></span>  
  
10. <span data-ttu-id="9ec36-130">Vedere [attività 3: Creare la casella degli strumenti e riquadri PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md) per informazioni su come aggiungere **casella degli strumenti** e **PropertyGrid** supportano alla finestra di progettazione del flusso di lavoro ospitata nuovamente.</span><span class="sxs-lookup"><span data-stu-id="9ec36-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec36-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ec36-131">See also</span></span>

- [<span data-ttu-id="9ec36-132">Riallocazione di Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="9ec36-132">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="9ec36-133">Attività 1: Creare una nuova applicazione Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="9ec36-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="9ec36-134">Attività 3: Creare la casella degli strumenti e PropertyGrid riquadri</span><span class="sxs-lookup"><span data-stu-id="9ec36-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)
