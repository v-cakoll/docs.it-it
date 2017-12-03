---
title: 'Procedura: Creare un ActivityDesigner personalizzato'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f0b1f27af6b4ec372b9dbd63e4bc89a5c435efe6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-custom-activity-designer"></a><span data-ttu-id="1b1c7-102">Procedura: Creare un ActivityDesigner personalizzato</span><span class="sxs-lookup"><span data-stu-id="1b1c7-102">How to: Create a Custom Activity Designer</span></span>
<span data-ttu-id="1b1c7-103">Gli ActivityDesigner personalizzati vengono in genere implementati in modo che le attività associate siano componibili con altre attività le cui finestre di progettazione possono essere rilasciate sull'area di progettazione insieme ad esse.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-103">Custom activity designers are typically implemented so that their associated activities are composable with other activities whose designers can be dropped on to the design surface with them.</span></span> <span data-ttu-id="1b1c7-104">Questa funzionalità richiede che un ActivityDesigner personalizzato fornisca un' "area di rilascio" in cui è possibile posizionare un'attività arbitraria, nonché i mezzi per gestire la raccolta di elementi nell'area di progettazione risultante.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-104">This functionality requires that a custom activity designer provide a "drop zone" where an arbitrary activity can be placed and also the means to manage the resulting collection of elements on the design surface.</span></span> <span data-ttu-id="1b1c7-105">In questo argomento viene descritto come creare un ActivityDesigner personalizzato contenente tale area di rilascio e come creare un ActivityDesigner personalizzato che fornisca la funzionalità di modifica necessaria per gestire la raccolta di elementi della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-105">This topic describes how to create a custom activity designer that contains such a drop zone and how to create a custom activity designer that provides that editing functionality needed to manage the collection of designer elements.</span></span>  
  
 <span data-ttu-id="1b1c7-106">L'ActivityDesigner personalizzato eredita in genere da <xref:System.Activities.Presentation.ActivityDesigner> che è il tipo di ActivityDesigner di base predefinito per qualsiasi attività senza una finestra di progettazione specifica.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-106">Custom activity designers typically inherit from <xref:System.Activities.Presentation.ActivityDesigner> which is the default base activity designer type for any activities without a specific designer.</span></span> <span data-ttu-id="1b1c7-107">Questo tipo fornisce una fase di progettazione per l'interazione con la griglia delle proprietà e per la configurazione degli aspetti di base, ad esempio la gestione di colori e icone.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-107">This type provides the design-time experience of interacting with the property grid and configuring basic aspects such as managing colors and icons.</span></span>  
  
 <span data-ttu-id="1b1c7-108">L'oggetto <xref:System.Activities.Presentation.ActivityDesigner> usa due controlli di supporto, <xref:System.Activities.Presentation.WorkflowItemPresenter> e <xref:System.Activities.Presentation.WorkflowItemsPresenter>, per facilitare lo sviluppo di ActivityDesigner personalizzati.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-108"><xref:System.Activities.Presentation.ActivityDesigner> uses two helper controls, <xref:System.Activities.Presentation.WorkflowItemPresenter> and <xref:System.Activities.Presentation.WorkflowItemsPresenter> to make it easier to develop custom activity designers.</span></span> <span data-ttu-id="1b1c7-109">Questi consentono di gestire funzionalità comuni quali il trascinamento e rilascio di elementi figlio, l'eliminazione, la selezione nonché l'aggiunta di tali elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-109">They handle common functionality like dragging and dropping of child elements, deletion, selection, and addition of those child elements.</span></span> <span data-ttu-id="1b1c7-110">Il <xref:System.Activities.Presentation.WorkflowItemPresenter> consente a un singolo elemento figlio elemento dell'interfaccia utente, fornendo il "area di rilascio", mentre il <xref:System.Activities.Presentation.WorkflowItemsPresenter> possibile fornire supporto di più elementi dell'interfaccia utente, incluse le funzionalità aggiuntive quali ordinamento, spostamento, eliminazione e aggiunta di elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-110">The <xref:System.Activities.Presentation.WorkflowItemPresenter> allows a single child UI element inside, providing the "drop zone", it while the <xref:System.Activities.Presentation.WorkflowItemsPresenter> can provide support multiple UI elements, including additional functionality like the ordering, moving, deleting, and adding of child elements.</span></span>  
  
 <span data-ttu-id="1b1c7-111">L'altro aspetto principale che è opportuno evidenziare nell'implementazione di un ActivityDesigner personalizzato riguarda il modo in cui vengono associate le modifiche visive usando l'associazione dati di [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] all'istanza archiviata in memoria degli elementi in fase di modifica nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-111">The other key part of the story that needs highlighting in the implementation of a custom activity designer concerns the way in which the visual edits are bound using [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] data binding to the instance stored in memory of what we are editing in the designer.</span></span> <span data-ttu-id="1b1c7-112">Questa operazione viene eseguita dall'albero degli elementi del modello che è inoltre responsabile per l'abilitazione della notifica di modifiche e il rilevamento di eventi quali le modifiche degli stati.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-112">This is accomplished by the Model Item tree, which is also responsible for enabling change notification and the tracking of events like changes in states.</span></span>  
  
 <span data-ttu-id="1b1c7-113">In questo argomento vengono delineate due procedure.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-113">This topic outlines two procedures.</span></span>  
  
1.  <span data-ttu-id="1b1c7-114">Nella prima viene descritto come creare un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemPresenter> che fornisce l'area di rilascio che riceve altre attività.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-114">The first procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter> that provides the drop zone that receives other activities.</span></span> <span data-ttu-id="1b1c7-115">Questa procedura si basa sul [finestre di progettazione Composite personalizzate - relatore di elementi del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-115">This procedure is based on the [Custom Composite Designers - Workflow Item Presenter](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md) sample.</span></span>  
  
2.  <span data-ttu-id="1b1c7-116">Nella seconda viene descritto come creare un ActivityDesigner personalizzato con un <xref:System.Activities.Presentation.WorkflowItemsPresenter> che fornisce la funzionalità necessaria per modificare una raccolta di elementi contenuti.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-116">The second procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter> that provides the functionality needed to edit of a collection of contained elements.</span></span> <span data-ttu-id="1b1c7-117">Questa procedura si basa sul [finestre di progettazione Composite personalizzate - relatore di elementi del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md) esempio.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-117">This procedure is based on the [Custom Composite Designers - Workflow Items Presenter](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md) sample.</span></span>  
  
### <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a><span data-ttu-id="1b1c7-118">Per creare un ActivityDesigner personalizzato con un'area di rilascio usando WorkflowItemPresenter</span><span class="sxs-lookup"><span data-stu-id="1b1c7-118">To create a custom activity designer with a drop zone using WorkflowItemPresenter</span></span>  
  
1.  <span data-ttu-id="1b1c7-119">Avviare [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b1c7-119">Start [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="1b1c7-120">Nel **File** dal menu **New**, quindi selezionare **progetto...** .</span><span class="sxs-lookup"><span data-stu-id="1b1c7-120">On the **File** menu, point to **New**, and then select **Project…**.</span></span>  
  
     <span data-ttu-id="1b1c7-121">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="1b1c7-121">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="1b1c7-122">Nel **modelli installati** riquadro, selezionare **Windows** dalla categoria di linguaggio preferita.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-122">In the **Installed Templates** pane, select **Windows** from your preferred language category.</span></span>  
  
4.  <span data-ttu-id="1b1c7-123">Nel **modelli** riquadro, selezionare **applicazione WPF**.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-123">In the **Templates** pane, select **WPF Application**.</span></span>  
  
5.  <span data-ttu-id="1b1c7-124">Nel **nome** immettere `UsingWorkflowItemPresenter`.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-124">In the **Name** box, enter `UsingWorkflowItemPresenter`.</span></span>  
  
6.  <span data-ttu-id="1b1c7-125">Nel **percorso** , immettere la directory in cui si desidera salvare il progetto oppure fare clic su **Sfoglia** per passare a tale.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-125">In the **Location** box, enter the directory in which you want to save your project, or click **Browse** to navigate to it.</span></span>  
  
7.  <span data-ttu-id="1b1c7-126">Nel **soluzione** casella, accettare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-126">In the **Solution** box, accept the default value.</span></span>  
  
8.  <span data-ttu-id="1b1c7-127">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-127">Click **OK**.</span></span>  
  
9. <span data-ttu-id="1b1c7-128">Il file MainWindows nel **Esplora**selezionare **eliminare** e confermare **OK** nel **Microsoft Visual Studio**finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-128">Right-click the MainWindows.xaml file in the **Solution Explorer**, select **Delete** and confirm **OK** in the **Microsoft Visual Studio** dialogue box.</span></span>  
  
10. <span data-ttu-id="1b1c7-129">Pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora**selezionare **Aggiungi**, quindi **nuovo elemento...**</span><span class="sxs-lookup"><span data-stu-id="1b1c7-129">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="1b1c7-130">Per visualizzare il **Aggiungi nuovo elemento** finestra di dialogo e selezionare il **WPF** categoria di **modelli installati** sezione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-130">to bring up the **Add New Item** dialogue and select the **WPF** category from the **Installed Templates** section on the left.</span></span>  
  
11. <span data-ttu-id="1b1c7-131">Selezionare il **finestra (WPF)** modello, il nome `RehostingWFDesigner`, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-131">Select the  **Window (WPF)** template, name it `RehostingWFDesigner`, and click **Add**.</span></span>  
  
12. <span data-ttu-id="1b1c7-132">Aprire il file RehostingWFDesigner.xaml e incollarvi il codice seguente per definire l'interfaccia utente per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-132">Open the RehostingWFDesigner.xaml file and paste the following code into it to define the UI for the application.</span></span>  
  
    ```xml  
    <Window x:Class=" UsingWorkflowItemPresenter.RehostingWFDesigner"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            xmlns:sapt="clr-namespace:System.Activities.Presentation.Toolbox;assembly=System.Activities.Presentation"  
            xmlns:sys="clr-namespace:System;assembly=mscorlib"  
            Title="Window1" Height="600" Width="900">  
        <Window.Resources>  
            <sys:String x:Key="AssemblyName">System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35</sys:String>  
        </Window.Resources>  
        <Grid>  
            <Grid.ColumnDefinitions>  
                <ColumnDefinition Width="2*"/>  
                <ColumnDefinition Width="7*"/>  
                <ColumnDefinition Width="3*"/>  
            </Grid.ColumnDefinitions>  
            <Border Grid.Column="0">  
                <sapt:ToolboxControl Name="Toolbox">  
                    <sapt:ToolboxCategory CategoryName="Basic">  
                        <sapt:ToolboxItemWrapper AssemblyName="{StaticResource AssemblyName}" >  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.Sequence  
                            </sapt:ToolboxItemWrapper.ToolName>  
                           </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.WriteLine  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.If  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">  
                            <sapt:ToolboxItemWrapper.ToolName>  
                                System.Activities.Statements.While  
                            </sapt:ToolboxItemWrapper.ToolName>  
  
                        </sapt:ToolboxItemWrapper>  
                    </sapt:ToolboxCategory>  
                </sapt:ToolboxControl>  
            </Border>  
            <Border Grid.Column="1" Name="DesignerBorder"/>  
            <Border Grid.Column="2" Name="PropertyBorder"/>  
        </Grid>  
    </Window>  
    ```  
  
13. <span data-ttu-id="1b1c7-133">Per associare un ActivityDesigner a un tipo di attività, è necessario registrare tale ActivityDesigner con l'archivio dei metadati.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-133">To associate an activity designer with an activity type, you must register that activity designer with the metadata store.</span></span> <span data-ttu-id="1b1c7-134">A tal fine, aggiungere il metodo `RegisterMetadata` alla classe `RehostingWFDesigner`.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-134">To do this, add the `RegisterMetadata` method to the `RehostingWFDesigner` class.</span></span> <span data-ttu-id="1b1c7-135">Nell'ambito del metodo `RegisterMetadata` creare un oggetto <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> e chiamare il metodo <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> per aggiungervi attributi.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-135">Within the scope of the  `RegisterMetadata` method, create an <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> object and call the <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> method to add the attributes to it.</span></span> <span data-ttu-id="1b1c7-136">Chiamare il metodo <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> per aggiungere l'oggetto <xref:System.Activities.Presentation.Metadata.AttributeTable> all'archivio dei metadati.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-136">Call the <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> method to add the <xref:System.Activities.Presentation.Metadata.AttributeTable> to the metadata store.</span></span> <span data-ttu-id="1b1c7-137">Il codice seguente contiene la logica di riallocazione per la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-137">The following code contains the rehosting logic for the designer.</span></span> <span data-ttu-id="1b1c7-138">Registra i metadati, inserisce `SimpleNativeActivity` nella casella degli strumenti e crea il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-138">It registers the metadata, puts the `SimpleNativeActivity` into the toolbox, and creates the workflow.</span></span> <span data-ttu-id="1b1c7-139">Inserire il codice seguente nel file RehostingWFDesigner.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-139">Put this code into the RehostingWFDesigner.xaml.cs file.</span></span>  
  
    ```  
    using System;  
    using System.Activities.Core.Presentation;  
    using System.Activities.Presentation;  
    using System.Activities.Presentation.Metadata;  
    using System.Activities.Presentation.Toolbox;  
    using System.Activities.Statements;  
    using System.ComponentModel;  
    using System.Windows;  
  
    namespace UsingWorkflowItemPresenter  
    {  
        // Interaction logic for RehostingWFDesigner.xaml  
        public partial class RehostingWFDesigner  
        {  
            public RehostingWFDesigner()  
            {  
                InitializeComponent();  
            }  
  
            protected override void OnInitialized(EventArgs e)  
            {  
                base.OnInitialized(e);  
                // register metadata  
                (new DesignerMetadata()).Register();  
                RegisterCustomMetadata();  
                // add custom activity to toolbox  
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));  
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));  
  
                // create the workflow designer  
                WorkflowDesigner wd = new WorkflowDesigner();  
                wd.Load(new Sequence());  
                DesignerBorder.Child = wd.View;  
                PropertyBorder.Child = wd.PropertyInspectorView;  
  
            }  
  
            void RegisterCustomMetadata()  
            {  
                AttributeTableBuilder builder = new AttributeTableBuilder();  
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));  
                MetadataStore.AddAttributeTable(builder.CreateTable());  
            }  
        }  
    }  
    ```  
  
14. <span data-ttu-id="1b1c7-140">Fare clic sulla directory riferimenti in Esplora soluzioni e selezionare **Aggiungi riferimento...**</span><span class="sxs-lookup"><span data-stu-id="1b1c7-140">Right-click the References directory in Solution Explorer and select **Add Reference …**</span></span> <span data-ttu-id="1b1c7-141">Per visualizzare il **Aggiungi riferimento** finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-141">to bring up the **Add Reference** dialogue.</span></span>  
  
15. <span data-ttu-id="1b1c7-142">Fare clic su di **.NET** , individuare l'assembly denominato **System.Activities.Core.Presentation**, selezionarlo e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-142">Click the **.NET** tab, locate the assembly named **System.Activities.Core.Presentation**, select it and click **OK**.</span></span>  
  
16. <span data-ttu-id="1b1c7-143">Tramite la stessa procedura aggiungere riferimenti agli assembly indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="1b1c7-143">Using the same procedure, add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="1b1c7-144">System.Data.DataSetExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="1b1c7-144">System.Data.DataSetExtensions.dll</span></span>  
  
    2.  <span data-ttu-id="1b1c7-145">System.Activities.Presentation.dll</span><span class="sxs-lookup"><span data-stu-id="1b1c7-145">System.Activities.Presentation.dll</span></span>  
  
    3.  <span data-ttu-id="1b1c7-146">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="1b1c7-146">System.ServiceModel.Activities.dll</span></span>  
  
17. <span data-ttu-id="1b1c7-147">Aprire il file app. XAML e impostare il valore di StartUpUri su "Rehostingwfdesigner".</span><span class="sxs-lookup"><span data-stu-id="1b1c7-147">Open the App.xaml file and change the value of the StartUpUri to "RehostingWFDesigner.xaml".</span></span>  
  
18. <span data-ttu-id="1b1c7-148">Pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora**selezionare **Aggiungi**, quindi **nuovo elemento...**</span><span class="sxs-lookup"><span data-stu-id="1b1c7-148">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="1b1c7-149">Per visualizzare il **Aggiungi nuovo elemento** finestra di dialogo e selezionare il **flusso di lavoro** categoria di **modelli installati** sezione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-149">to bring up the **Add New Item** dialogue and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>  
  
19. <span data-ttu-id="1b1c7-150">Selezionare il **ActivityDesigner** modello, il nome `SimpleNativeDesigner`, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-150">Select the **Activity Designer** template, name it `SimpleNativeDesigner`, and click **Add**.</span></span>  
  
20. <span data-ttu-id="1b1c7-151">Aprire il file SimpleNativeDesigner.xaml e incollarvi il codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-151">Open the SimpleNativeDesigner.xaml file and paste the following code into it.</span></span> <span data-ttu-id="1b1c7-152">Questo codice usa <xref:System.Activities.Presentation.ActivityDesigner> come elemento radice e illustra come usare l'associazione per  integrare <xref:System.Activities.Presentation.WorkflowItemPresenter> nella finestra di progettazione in modo da poter visualizzare un tipo figlio nel CompositeActivityDesigner.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-152">Note this code uses <xref:System.Activities.Presentation.ActivityDesigner> as your root element and shows how binding is used to integrate <xref:System.Activities.Presentation.WorkflowItemPresenter> into your designer so a child type can be displayed in your composite activity designer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b1c7-153">Lo schema dell'oggetto <xref:System.Activities.Presentation.ActivityDesigner> consente di aggiungere un unico elemento figlio alla definizione dell'ActivityDesigner personalizzato. Questo elemento, tuttavia, potrebbe essere un oggetto `StackPanel`, `Grid` o un altro elemento composito dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-153">The schema for <xref:System.Activities.Presentation.ActivityDesigner> allows the addition of only one child element to your custom activity designer definition; however, this element could be a `StackPanel`, `Grid`, or some other composite UI element.</span></span>  
  
    ```xml  
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemPresenter.SimpleNativeDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
        <sap:ActivityDesigner.Resources>  
            <DataTemplate x:Key="Collapsed">  
                <StackPanel>  
                    <TextBlock>This is the collapsed view</TextBlock>  
                </StackPanel>  
            </DataTemplate>  
            <DataTemplate x:Key="Expanded">  
                <StackPanel>  
                    <TextBlock>Custom Text</TextBlock>  
                    <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
                                            HintText="Please drop an activity here" />  
                </StackPanel>  
            </DataTemplate>  
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
                <Style.Triggers>  
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                    </DataTrigger>  
                </Style.Triggers>  
            </Style>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />  
        </Grid>  
    </sap:ActivityDesigner>  
    ```  
  
21. <span data-ttu-id="1b1c7-154">Pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora**selezionare **Aggiungi**, quindi **nuovo elemento...**</span><span class="sxs-lookup"><span data-stu-id="1b1c7-154">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="1b1c7-155">Per visualizzare il **Aggiungi nuovo elemento** finestra di dialogo e selezionare il **flusso di lavoro** categoria di **modelli installati** sezione a sinistra.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-155">to bring up the **Add New Item** dialogue and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>  
  
22. <span data-ttu-id="1b1c7-156">Selezionare il **attività codice** modello, il nome `SimpleNativeActivity`, fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-156">Select the  **Code Activity** template, name it `SimpleNativeActivity`, and click **Add**.</span></span>  
  
23. <span data-ttu-id="1b1c7-157">Implementare la classe `SimpleNativeActivity` immettendo il codice seguente nel file SimpleNativeActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-157">Implement the `SimpleNativeActivity` class by entering the following code into the SimpleNativeActivity.cs file.</span></span>  
  
    ```  
    using System.Activities;  
  
    namespace UsingWorkflowItemPresenter  
    {  
        public sealed class SimpleNativeActivity : NativeActivity  
        {  
            // this property contains an activity that will be scheduled in the execute method  
    // the WorkflowItemPresenter in the designer is bound to this to enable editing  
    // of the value  
            public Activity Body { get; set; }  
  
            protected override void CacheMetadata(NativeActivityMetadata metadata)  
            {  
               metadata.AddChild(Body);  
               base.CacheMetadata(metadata);  
  
            }  
  
            protected override void Execute(NativeActivityContext context)  
            {  
                context.ScheduleActivity(Body);  
            }  
        }  
    }  
    ```  
  
24. <span data-ttu-id="1b1c7-158">Selezionare **Compila soluzione** dal **compilare** menu.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-158">Select **Build Solution** from the **Build** menu.</span></span>  
  
25. <span data-ttu-id="1b1c7-159">Selezionare **Avvia senza eseguire debug** dal **Debug** menu per aprire la finestra di progettazione riallocata.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-159">Select **Start Without Debugging** from the **Debug** menu to open the rehosted custom design window.</span></span>  
  
### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a><span data-ttu-id="1b1c7-160">Per creare un ActivityDesigner personalizzato usando WorkflowItemsPresenter</span><span class="sxs-lookup"><span data-stu-id="1b1c7-160">To create a custom activity designer using WorkflowItemsPresenter</span></span>  
  
1.  <span data-ttu-id="1b1c7-161">La procedura per il secondo ActivityDesigner personalizzato è analoga alla prima con alcune modifiche, la prima delle quali viene assegnato un nome della seconda applicazione `UsingWorkflowItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-161">The procedure for the second custom activity designer is the parallels the first with a few modifications, the first of which is to name the second application `UsingWorkflowItemsPresenter`.</span></span> <span data-ttu-id="1b1c7-162">Questa applicazione non definisce inoltre una nuova attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-162">Also this application does not define a new custom activity.</span></span>  
  
2.  <span data-ttu-id="1b1c7-163">Le differenze principali sono contenute nei file CustomParallelDesigner.xaml e  RehostingWFDesigner.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-163">Key differences are contained in the CustomParallelDesigner.xaml and RehostingWFDesigner.xaml.cs files.</span></span> <span data-ttu-id="1b1c7-164">Di seguito è riportato il codice del file CustomParallelDesigne.xaml che definisce l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-164">Here is the code from the CustomParallelDesigne.xaml file that defines the UI.</span></span>  
  
    ```xml  
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemsPresenter.CustomParallelDesigner"  
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"  
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">  
        <sap:ActivityDesigner.Resources>  
            <DataTemplate x:Key="Collapsed">  
                <TextBlock>This is the Collapsed View</TextBlock>  
            </DataTemplate>  
            <DataTemplate x:Key="Expanded">  
                <StackPanel>  
                    <TextBlock HorizontalAlignment="Center">This is the</TextBlock>  
                    <TextBlock HorizontalAlignment="Center">extended view</TextBlock>  
                    <sap:WorkflowItemsPresenter HintText="Drop Activities Here"  
                                        Items="{Binding Path=ModelItem.Branches}">  
                        <sap:WorkflowItemsPresenter.SpacerTemplate>  
                            <DataTemplate>  
                                <Ellipse Width="10" Height="10" Fill="Black"/>  
                            </DataTemplate>  
                        </sap:WorkflowItemsPresenter.SpacerTemplate>  
                        <sap:WorkflowItemsPresenter.ItemsPanel>  
                            <ItemsPanelTemplate>  
                                <StackPanel Orientation="Horizontal"/>  
                            </ItemsPanelTemplate>  
                        </sap:WorkflowItemsPresenter.ItemsPanel>  
                    </sap:WorkflowItemsPresenter>  
                </StackPanel>  
            </DataTemplate>  
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">  
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>  
                <Style.Triggers>  
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">  
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>  
                    </DataTrigger>  
                </Style.Triggers>  
            </Style>  
        </sap:ActivityDesigner.Resources>  
        <Grid>  
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>  
        </Grid>  
    </sap:ActivityDesigner>  
    ```  
  
3.  <span data-ttu-id="1b1c7-165">Di seguito è riportato il codice dal file RehostingWFDesigner.xaml.cs che fornisce la logica di riallocazione.</span><span class="sxs-lookup"><span data-stu-id="1b1c7-165">Here is the code from the RehostingWFDesigner.xaml.cs file that provides the rehosting logic.</span></span>  
  
    ```  
    using System;  
    using System.Activities.Core.Presentation;  
    using System.Activities.Presentation;  
    using System.Activities.Presentation.Metadata;  
    using System.Activities.Statements;  
    using System.ComponentModel;  
    using System.Windows;  
  
    namespaceUsingWorkflowItemsPresenter  
    {  
        public partial class RehostingWfDesigner : Window  
        {  
            public RehostingWfDesigner()  
            {  
                InitializeComponent();  
            }  
  
            protected override void OnInitialized(EventArgs e)  
            {  
                base.OnInitialized(e);  
                // register metadata  
                (new DesignerMetadata()).Register();  
                RegisterCustomMetadata();  
  
                // create the workflow designer  
                WorkflowDesigner wd = new WorkflowDesigner();  
                wd.Load(new Sequence());  
                DesignerBorder.Child = wd.View;  
                PropertyBorder.Child = wd.PropertyInspectorView;  
  
            }  
  
            void RegisterCustomMetadata()  
            {  
                AttributeTableBuilder builder = new AttributeTableBuilder();  
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));  
                MetadataStore.AddAttributeTable(builder.CreateTable());  
            }  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1b1c7-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b1c7-166">See Also</span></span>  
 <xref:System.Activities.Presentation.ActivityDesigner>  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>  
 <xref:System.Activities.Presentation.WorkflowViewElement>  
 <xref:System.Activities.Presentation.Model.ModelItem>  
 [<span data-ttu-id="1b1c7-167">Personalizzazione della fase di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="1b1c7-167">Customizing the Workflow Design Experience</span></span>](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
