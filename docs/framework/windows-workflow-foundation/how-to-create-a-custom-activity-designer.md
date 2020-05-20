---
title: 'Procedura: Creare un ActivityDesigner personalizzato'
description: Questo articolo descrive come creare un ActivityDesigner personalizzato di Workflow Foundation con un'area di rilascio in cui è possibile posizionare un'attività arbitraria.
ms.date: 03/30/2017
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
ms.openlocfilehash: 015efd1e482e2b531d28b9caec411c76116c9653
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419785"
---
# <a name="how-to-create-a-custom-activity-designer"></a><span data-ttu-id="096dc-103">Procedura: Creare un ActivityDesigner personalizzato</span><span class="sxs-lookup"><span data-stu-id="096dc-103">How to: Create a Custom Activity Designer</span></span>

<span data-ttu-id="096dc-104">Gli ActivityDesigner personalizzati vengono in genere implementati in modo che le attività associate siano componibili con altre attività le cui finestre di progettazione possono essere rilasciate sull'area di progettazione insieme ad esse.</span><span class="sxs-lookup"><span data-stu-id="096dc-104">Custom activity designers are typically implemented so that their associated activities are composable with other activities whose designers can be dropped on to the design surface with them.</span></span> <span data-ttu-id="096dc-105">Questa funzionalità richiede che un ActivityDesigner personalizzato fornisca un'"area di rilascio" in cui è possibile posizionare un'attività arbitraria e anche i mezzi per gestire la raccolta di elementi risultante nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="096dc-105">This functionality requires that a custom activity designer provide a "drop zone" where an arbitrary activity can be placed and also the means to manage the resulting collection of elements on the design surface.</span></span> <span data-ttu-id="096dc-106">In questo argomento viene descritto come creare un ActivityDesigner personalizzato contenente tale area di rilascio e come creare un ActivityDesigner personalizzato che fornisca la funzionalità di modifica necessaria per gestire la raccolta di elementi della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="096dc-106">This topic describes how to create a custom activity designer that contains such a drop zone and how to create a custom activity designer that provides that editing functionality needed to manage the collection of designer elements.</span></span>

<span data-ttu-id="096dc-107">L'ActivityDesigner personalizzato eredita in genere da <xref:System.Activities.Presentation.ActivityDesigner> che è il tipo di ActivityDesigner di base predefinito per qualsiasi attività senza una finestra di progettazione specifica.</span><span class="sxs-lookup"><span data-stu-id="096dc-107">Custom activity designers typically inherit from <xref:System.Activities.Presentation.ActivityDesigner> which is the default base activity designer type for any activities without a specific designer.</span></span> <span data-ttu-id="096dc-108">Questo tipo fornisce una fase di progettazione per l'interazione con la griglia delle proprietà e per la configurazione degli aspetti di base, ad esempio la gestione di colori e icone.</span><span class="sxs-lookup"><span data-stu-id="096dc-108">This type provides the design-time experience of interacting with the property grid and configuring basic aspects such as managing colors and icons.</span></span>

<span data-ttu-id="096dc-109">L'oggetto <xref:System.Activities.Presentation.ActivityDesigner> usa due controlli di supporto, <xref:System.Activities.Presentation.WorkflowItemPresenter> e <xref:System.Activities.Presentation.WorkflowItemsPresenter>, per facilitare lo sviluppo di ActivityDesigner personalizzati.</span><span class="sxs-lookup"><span data-stu-id="096dc-109"><xref:System.Activities.Presentation.ActivityDesigner> uses two helper controls, <xref:System.Activities.Presentation.WorkflowItemPresenter> and <xref:System.Activities.Presentation.WorkflowItemsPresenter> to make it easier to develop custom activity designers.</span></span> <span data-ttu-id="096dc-110">Questi consentono di gestire funzionalità comuni quali il trascinamento e rilascio di elementi figlio, l'eliminazione, la selezione nonché l'aggiunta di tali elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="096dc-110">They handle common functionality like dragging and dropping of child elements, deletion, selection, and addition of those child elements.</span></span> <span data-ttu-id="096dc-111"><xref:System.Activities.Presentation.WorkflowItemPresenter>Consente un singolo elemento dell'interfaccia utente figlio all'interno di, fornendo l'"area di rilascio", mentre <xref:System.Activities.Presentation.WorkflowItemsPresenter> può fornire supporto per più elementi dell'interfaccia utente, incluse funzionalità aggiuntive come l'ordinamento, lo stato di trasferimento, l'eliminazione e l'aggiunta di elementi figlio.</span><span class="sxs-lookup"><span data-stu-id="096dc-111">The <xref:System.Activities.Presentation.WorkflowItemPresenter> allows a single child UI element inside, providing the "drop zone", it while the <xref:System.Activities.Presentation.WorkflowItemsPresenter> can provide support multiple UI elements, including additional functionality like the ordering, moving, deleting, and adding of child elements.</span></span>

<span data-ttu-id="096dc-112">L'altra parte essenziale della storia che necessita di evidenziare nell'implementazione di un ActivityDesigner personalizzato riguarda il modo in cui le modifiche visive vengono associate utilizzando WPF data binding all'istanza archiviata in memoria degli elementi che vengono modificati nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="096dc-112">The other key part of the story that needs highlighting in the implementation of a custom activity designer concerns the way in which the visual edits are bound using WPF data binding to the instance stored in memory of what we are editing in the designer.</span></span> <span data-ttu-id="096dc-113">Questa operazione viene eseguita dall'albero degli elementi del modello che è inoltre responsabile per l'abilitazione della notifica di modifiche e il rilevamento di eventi quali le modifiche degli stati.</span><span class="sxs-lookup"><span data-stu-id="096dc-113">This is accomplished by the Model Item tree, which is also responsible for enabling change notification and the tracking of events like changes in states.</span></span>

<span data-ttu-id="096dc-114">In questo argomento vengono delineate due procedure.</span><span class="sxs-lookup"><span data-stu-id="096dc-114">This topic outlines two procedures.</span></span>

1. <span data-ttu-id="096dc-115">Nella prima viene descritto come creare un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemPresenter> che fornisce l'area di rilascio che riceve altre attività.</span><span class="sxs-lookup"><span data-stu-id="096dc-115">The first procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter> that provides the drop zone that receives other activities.</span></span> <span data-ttu-id="096dc-116">Questa procedura è basata sull'esempio di finestra di [progettazione composita personalizzata-elemento del flusso di lavoro](./samples/custom-composite-designers-workflow-item-presenter.md) .</span><span class="sxs-lookup"><span data-stu-id="096dc-116">This procedure is based on the [Custom Composite Designers - Workflow Item Presenter](./samples/custom-composite-designers-workflow-item-presenter.md) sample.</span></span>

2. <span data-ttu-id="096dc-117">Nella seconda viene descritto come creare un ActivityDesigner personalizzato con un <xref:System.Activities.Presentation.WorkflowItemsPresenter> che fornisce la funzionalità necessaria per modificare una raccolta di elementi contenuti.</span><span class="sxs-lookup"><span data-stu-id="096dc-117">The second procedure describes how to create a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter> that provides the functionality needed to edit of a collection of contained elements.</span></span> <span data-ttu-id="096dc-118">Questa procedura è basata sull'esempio della finestra di [progettazione composita personalizzata-elementi del flusso di lavoro](./samples/custom-composite-designers-workflow-items-presenter.md) .</span><span class="sxs-lookup"><span data-stu-id="096dc-118">This procedure is based on the [Custom Composite Designers - Workflow Items Presenter](./samples/custom-composite-designers-workflow-items-presenter.md) sample.</span></span>

## <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a><span data-ttu-id="096dc-119">Per creare un ActivityDesigner personalizzato con un'area di rilascio usando WorkflowItemPresenter</span><span class="sxs-lookup"><span data-stu-id="096dc-119">To create a custom activity designer with a drop zone using WorkflowItemPresenter</span></span>

1. <span data-ttu-id="096dc-120">Avviare Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="096dc-120">Start Visual Studio 2010.</span></span>

2. <span data-ttu-id="096dc-121">Scegliere **nuovo**dal menu **file** , quindi selezionare **progetto.**</span><span class="sxs-lookup"><span data-stu-id="096dc-121">On the **File** menu, point to **New**, and then select **Project…**.</span></span>

     <span data-ttu-id="096dc-122">Verrà visualizzata la finestra di dialogo **Nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="096dc-122">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="096dc-123">Nel riquadro **modelli installati** selezionare **Windows** dalla categoria di lingua preferita.</span><span class="sxs-lookup"><span data-stu-id="096dc-123">In the **Installed Templates** pane, select **Windows** from your preferred language category.</span></span>

4. <span data-ttu-id="096dc-124">Nel riquadro **modelli** selezionare **applicazione WPF**.</span><span class="sxs-lookup"><span data-stu-id="096dc-124">In the **Templates** pane, select **WPF Application**.</span></span>

5. <span data-ttu-id="096dc-125">Nella casella **nome** immettere `UsingWorkflowItemPresenter` .</span><span class="sxs-lookup"><span data-stu-id="096dc-125">In the **Name** box, enter `UsingWorkflowItemPresenter`.</span></span>

6. <span data-ttu-id="096dc-126">Nella casella **percorso** immettere la directory in cui si desidera salvare il progetto oppure fare clic su **Sfoglia** per passare a tale directory.</span><span class="sxs-lookup"><span data-stu-id="096dc-126">In the **Location** box, enter the directory in which you want to save your project, or click **Browse** to navigate to it.</span></span>

7. <span data-ttu-id="096dc-127">Nella casella **soluzione** accettare il valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="096dc-127">In the **Solution** box, accept the default value.</span></span>

8. <span data-ttu-id="096dc-128">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="096dc-128">Click **OK**.</span></span>

9. <span data-ttu-id="096dc-129">Fare clic con il pulsante destro del mouse sul file *MainWindows. XAML* nella **Esplora soluzioni**, selezionare **Elimina** e confermare **OK** nella finestra di dialogo **Microsoft Visual Studio** .</span><span class="sxs-lookup"><span data-stu-id="096dc-129">Right-click the *MainWindows.xaml* file in the **Solution Explorer**, select **Delete** and confirm **OK** in the **Microsoft Visual Studio** dialog box.</span></span>

10. <span data-ttu-id="096dc-130">Fare clic con il pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora soluzioni**, scegliere **Aggiungi**, quindi **nuovo elemento...**</span><span class="sxs-lookup"><span data-stu-id="096dc-130">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="096dc-131">per visualizzare la finestra di dialogo **Aggiungi nuovo elemento** e selezionare la categoria **WPF** nella sezione **modelli installati** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="096dc-131">to bring up the **Add New Item** dialog and select the **WPF** category from the **Installed Templates** section on the left.</span></span>

11. <span data-ttu-id="096dc-132">Selezionare il modello **finestra (WPF)** , denominarlo `RehostingWFDesigner` e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="096dc-132">Select the  **Window (WPF)** template, name it `RehostingWFDesigner`, and click **Add**.</span></span>

12. <span data-ttu-id="096dc-133">Aprire il file *RehostingWFDesigner. XAML* e incollarvi il codice seguente per definire l'interfaccia utente per l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="096dc-133">Open the *RehostingWFDesigner.xaml* file and paste the following code into it to define the UI for the application:</span></span>

    ```xaml
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

13. <span data-ttu-id="096dc-134">Per associare un ActivityDesigner a un tipo di attività, è necessario registrare tale ActivityDesigner con l'archivio dei metadati.</span><span class="sxs-lookup"><span data-stu-id="096dc-134">To associate an activity designer with an activity type, you must register that activity designer with the metadata store.</span></span> <span data-ttu-id="096dc-135">A tal fine, aggiungere il metodo `RegisterMetadata` alla classe `RehostingWFDesigner`.</span><span class="sxs-lookup"><span data-stu-id="096dc-135">To do this, add the `RegisterMetadata` method to the `RehostingWFDesigner` class.</span></span> <span data-ttu-id="096dc-136">Nell'ambito del metodo `RegisterMetadata` creare un oggetto <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> e chiamare il metodo <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> per aggiungervi attributi.</span><span class="sxs-lookup"><span data-stu-id="096dc-136">Within the scope of the  `RegisterMetadata` method, create an <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> object and call the <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> method to add the attributes to it.</span></span> <span data-ttu-id="096dc-137">Chiamare il metodo <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> per aggiungere l'oggetto <xref:System.Activities.Presentation.Metadata.AttributeTable> all'archivio dei metadati.</span><span class="sxs-lookup"><span data-stu-id="096dc-137">Call the <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> method to add the <xref:System.Activities.Presentation.Metadata.AttributeTable> to the metadata store.</span></span> <span data-ttu-id="096dc-138">Il codice seguente contiene la logica di riallocazione per la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="096dc-138">The following code contains the rehosting logic for the designer.</span></span> <span data-ttu-id="096dc-139">Registra i metadati, inserisce `SimpleNativeActivity` nella casella degli strumenti e crea il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="096dc-139">It registers the metadata, puts the `SimpleNativeActivity` into the toolbox, and creates the workflow.</span></span> <span data-ttu-id="096dc-140">Inserire questo codice nel file *RehostingWFDesigner.XAML.cs* .</span><span class="sxs-lookup"><span data-stu-id="096dc-140">Put this code into the *RehostingWFDesigner.xaml.cs* file.</span></span>

    ```csharp
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
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();
                // Add custom activity to toolbox.
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

14. <span data-ttu-id="096dc-141">Fare clic con il pulsante destro del mouse sulla directory References in Esplora soluzioni e scegliere **Aggiungi riferimento.**</span><span class="sxs-lookup"><span data-stu-id="096dc-141">Right-click the References directory in Solution Explorer and select **Add Reference …**</span></span> <span data-ttu-id="096dc-142">per visualizzare la finestra di dialogo **Aggiungi riferimento** .</span><span class="sxs-lookup"><span data-stu-id="096dc-142">to bring up the **Add Reference** dialog.</span></span>

15. <span data-ttu-id="096dc-143">Fare clic sulla scheda **.NET** , individuare l'assembly denominato **System. Activities. Core. Presentation**, selezionarlo e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="096dc-143">Click the **.NET** tab, locate the assembly named **System.Activities.Core.Presentation**, select it and click **OK**.</span></span>

16. <span data-ttu-id="096dc-144">Tramite la stessa procedura aggiungere riferimenti agli assembly indicati di seguito:</span><span class="sxs-lookup"><span data-stu-id="096dc-144">Using the same procedure, add references to the following assemblies:</span></span>

    1. <span data-ttu-id="096dc-145">System.Data.DataSetExtensions.dll</span><span class="sxs-lookup"><span data-stu-id="096dc-145">System.Data.DataSetExtensions.dll</span></span>

    2. <span data-ttu-id="096dc-146">System.Activities.Presentation.dll</span><span class="sxs-lookup"><span data-stu-id="096dc-146">System.Activities.Presentation.dll</span></span>

    3. <span data-ttu-id="096dc-147">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="096dc-147">System.ServiceModel.Activities.dll</span></span>

17. <span data-ttu-id="096dc-148">Aprire il file *app. XAML* e modificare il valore di StartupUri in "RehostingWFDesigner. xaml".</span><span class="sxs-lookup"><span data-stu-id="096dc-148">Open the *App.xaml* file and change the value of the StartUpUri to "RehostingWFDesigner.xaml".</span></span>

18. <span data-ttu-id="096dc-149">Fare clic con il pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora soluzioni**, scegliere **Aggiungi**, quindi **nuovo elemento...**</span><span class="sxs-lookup"><span data-stu-id="096dc-149">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="096dc-150">per visualizzare la finestra di dialogo **Aggiungi nuovo elemento** e selezionare la categoria **flusso di lavoro** nella sezione **modelli installati** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="096dc-150">to bring up the **Add New Item** dialog and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>

19. <span data-ttu-id="096dc-151">Selezionare il **modello ActivityDesigner,** denominarlo `SimpleNativeDesigner` e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="096dc-151">Select the **Activity Designer** template, name it `SimpleNativeDesigner`, and click **Add**.</span></span>

20. <span data-ttu-id="096dc-152">Aprire il file *SimpleNativeDesigner. XAML* e incollarvi il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="096dc-152">Open the *SimpleNativeDesigner.xaml* file and paste the following code into it.</span></span> <span data-ttu-id="096dc-153">Questo codice usa <xref:System.Activities.Presentation.ActivityDesigner> come elemento radice e illustra come usare l'associazione per  integrare <xref:System.Activities.Presentation.WorkflowItemPresenter> nella finestra di progettazione in modo da poter visualizzare un tipo figlio nel CompositeActivityDesigner.</span><span class="sxs-lookup"><span data-stu-id="096dc-153">Note this code uses <xref:System.Activities.Presentation.ActivityDesigner> as your root element and shows how binding is used to integrate <xref:System.Activities.Presentation.WorkflowItemPresenter> into your designer so a child type can be displayed in your composite activity designer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="096dc-154">Lo schema dell'oggetto <xref:System.Activities.Presentation.ActivityDesigner> consente di aggiungere un unico elemento figlio alla definizione dell'ActivityDesigner personalizzato. Questo elemento, tuttavia, potrebbe essere un oggetto `StackPanel`, `Grid` o un altro elemento composito dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="096dc-154">The schema for <xref:System.Activities.Presentation.ActivityDesigner> allows the addition of only one child element to your custom activity designer definition; however, this element could be a `StackPanel`, `Grid`, or some other composite UI element.</span></span>

    ```xaml
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

21. <span data-ttu-id="096dc-155">Fare clic con il pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora soluzioni**, scegliere **Aggiungi**, quindi **nuovo elemento...**</span><span class="sxs-lookup"><span data-stu-id="096dc-155">Right-click the UsingWorkflowItemPresenter project in **Solution Explorer**, select **Add**, then **New Item…**</span></span> <span data-ttu-id="096dc-156">per visualizzare la finestra di dialogo **Aggiungi nuovo elemento** e selezionare la categoria **flusso di lavoro** nella sezione **modelli installati** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="096dc-156">to bring up the **Add New Item** dialog and select the **Workflow** category form the **Installed Templates** section on the left.</span></span>

22. <span data-ttu-id="096dc-157">Selezionare il modello **attività codice** , denominarlo `SimpleNativeActivity` e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="096dc-157">Select the  **Code Activity** template, name it `SimpleNativeActivity`, and click **Add**.</span></span>

23. <span data-ttu-id="096dc-158">Implementare la `SimpleNativeActivity` classe immettendo il codice seguente nel file *SimpleNativeActivity.cs* :</span><span class="sxs-lookup"><span data-stu-id="096dc-158">Implement the `SimpleNativeActivity` class by entering the following code into the *SimpleNativeActivity.cs* file:</span></span>

    ```csharp
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

24. <span data-ttu-id="096dc-159">Scegliere **Compila soluzione** dal menu **Compila** .</span><span class="sxs-lookup"><span data-stu-id="096dc-159">Select **Build Solution** from the **Build** menu.</span></span>

25. <span data-ttu-id="096dc-160">Selezionare **Avvia senza eseguire debug** dal menu **debug** per aprire la finestra di progettazione personalizzata riallocata.</span><span class="sxs-lookup"><span data-stu-id="096dc-160">Select **Start Without Debugging** from the **Debug** menu to open the rehosted custom design window.</span></span>

### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a><span data-ttu-id="096dc-161">Per creare un ActivityDesigner personalizzato usando WorkflowItemsPresenter</span><span class="sxs-lookup"><span data-stu-id="096dc-161">To create a custom activity designer using WorkflowItemsPresenter</span></span>

1. <span data-ttu-id="096dc-162">La procedura per il secondo ActivityDesigner personalizzato è Parallels alla prima con alcune modifiche, la prima delle quali consiste nel denominare la seconda applicazione `UsingWorkflowItemsPresenter` .</span><span class="sxs-lookup"><span data-stu-id="096dc-162">The procedure for the second custom activity designer is the parallels the first with a few modifications, the first of which is to name the second application `UsingWorkflowItemsPresenter`.</span></span> <span data-ttu-id="096dc-163">Questa applicazione non definisce inoltre una nuova attività personalizzata.</span><span class="sxs-lookup"><span data-stu-id="096dc-163">Also this application does not define a new custom activity.</span></span>

2. <span data-ttu-id="096dc-164">Le differenze principali sono contenute nei file *CustomParallelDesigner. XAML* e *RehostingWFDesigner.XAML.cs* .</span><span class="sxs-lookup"><span data-stu-id="096dc-164">Key differences are contained in the *CustomParallelDesigner.xaml* and *RehostingWFDesigner.xaml.cs* files.</span></span> <span data-ttu-id="096dc-165">Ecco il codice del file *CustomParallelDesigner. XAML* che definisce l'interfaccia utente:</span><span class="sxs-lookup"><span data-stu-id="096dc-165">Here is the code from the *CustomParallelDesigner.xaml* file that defines the UI:</span></span>

    ```xaml
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

3. <span data-ttu-id="096dc-166">Ecco il codice del file *RehostingWFDesigner.XAML.cs* che fornisce la logica di riallocazione:</span><span class="sxs-lookup"><span data-stu-id="096dc-166">Here is the code from the *RehostingWFDesigner.xaml.cs* file that provides the rehosting logic:</span></span>

    ```csharp
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
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="096dc-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="096dc-167">See also</span></span>

- <xref:System.Activities.Presentation.ActivityDesigner>
- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- <xref:System.Activities.Presentation.WorkflowViewElement>
- <xref:System.Activities.Presentation.Model.ModelItem>
- [<span data-ttu-id="096dc-168">Personalizzazione della fase di progettazione del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="096dc-168">Customizing the Workflow Design Experience</span></span>](customizing-the-workflow-design-experience.md)
