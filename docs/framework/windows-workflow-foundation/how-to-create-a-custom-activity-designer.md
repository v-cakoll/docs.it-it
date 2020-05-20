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
# <a name="how-to-create-a-custom-activity-designer"></a>Procedura: Creare un ActivityDesigner personalizzato

Gli ActivityDesigner personalizzati vengono in genere implementati in modo che le attività associate siano componibili con altre attività le cui finestre di progettazione possono essere rilasciate sull'area di progettazione insieme ad esse. Questa funzionalità richiede che un ActivityDesigner personalizzato fornisca un'"area di rilascio" in cui è possibile posizionare un'attività arbitraria e anche i mezzi per gestire la raccolta di elementi risultante nell'area di progettazione. In questo argomento viene descritto come creare un ActivityDesigner personalizzato contenente tale area di rilascio e come creare un ActivityDesigner personalizzato che fornisca la funzionalità di modifica necessaria per gestire la raccolta di elementi della finestra di progettazione.

L'ActivityDesigner personalizzato eredita in genere da <xref:System.Activities.Presentation.ActivityDesigner> che è il tipo di ActivityDesigner di base predefinito per qualsiasi attività senza una finestra di progettazione specifica. Questo tipo fornisce una fase di progettazione per l'interazione con la griglia delle proprietà e per la configurazione degli aspetti di base, ad esempio la gestione di colori e icone.

L'oggetto <xref:System.Activities.Presentation.ActivityDesigner> usa due controlli di supporto, <xref:System.Activities.Presentation.WorkflowItemPresenter> e <xref:System.Activities.Presentation.WorkflowItemsPresenter>, per facilitare lo sviluppo di ActivityDesigner personalizzati. Questi consentono di gestire funzionalità comuni quali il trascinamento e rilascio di elementi figlio, l'eliminazione, la selezione nonché l'aggiunta di tali elementi figlio. <xref:System.Activities.Presentation.WorkflowItemPresenter>Consente un singolo elemento dell'interfaccia utente figlio all'interno di, fornendo l'"area di rilascio", mentre <xref:System.Activities.Presentation.WorkflowItemsPresenter> può fornire supporto per più elementi dell'interfaccia utente, incluse funzionalità aggiuntive come l'ordinamento, lo stato di trasferimento, l'eliminazione e l'aggiunta di elementi figlio.

L'altra parte essenziale della storia che necessita di evidenziare nell'implementazione di un ActivityDesigner personalizzato riguarda il modo in cui le modifiche visive vengono associate utilizzando WPF data binding all'istanza archiviata in memoria degli elementi che vengono modificati nella finestra di progettazione. Questa operazione viene eseguita dall'albero degli elementi del modello che è inoltre responsabile per l'abilitazione della notifica di modifiche e il rilevamento di eventi quali le modifiche degli stati.

In questo argomento vengono delineate due procedure.

1. Nella prima viene descritto come creare un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemPresenter> che fornisce l'area di rilascio che riceve altre attività. Questa procedura è basata sull'esempio di finestra di [progettazione composita personalizzata-elemento del flusso di lavoro](./samples/custom-composite-designers-workflow-item-presenter.md) .

2. Nella seconda viene descritto come creare un ActivityDesigner personalizzato con un <xref:System.Activities.Presentation.WorkflowItemsPresenter> che fornisce la funzionalità necessaria per modificare una raccolta di elementi contenuti. Questa procedura è basata sull'esempio della finestra di [progettazione composita personalizzata-elementi del flusso di lavoro](./samples/custom-composite-designers-workflow-items-presenter.md) .

## <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a>Per creare un ActivityDesigner personalizzato con un'area di rilascio usando WorkflowItemPresenter

1. Avviare Visual Studio 2010.

2. Scegliere **nuovo**dal menu **file** , quindi selezionare **progetto.**

     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .

3. Nel riquadro **modelli installati** selezionare **Windows** dalla categoria di lingua preferita.

4. Nel riquadro **modelli** selezionare **applicazione WPF**.

5. Nella casella **nome** immettere `UsingWorkflowItemPresenter` .

6. Nella casella **percorso** immettere la directory in cui si desidera salvare il progetto oppure fare clic su **Sfoglia** per passare a tale directory.

7. Nella casella **soluzione** accettare il valore predefinito.

8. Fare clic su **OK**.

9. Fare clic con il pulsante destro del mouse sul file *MainWindows. XAML* nella **Esplora soluzioni**, selezionare **Elimina** e confermare **OK** nella finestra di dialogo **Microsoft Visual Studio** .

10. Fare clic con il pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora soluzioni**, scegliere **Aggiungi**, quindi **nuovo elemento...** per visualizzare la finestra di dialogo **Aggiungi nuovo elemento** e selezionare la categoria **WPF** nella sezione **modelli installati** a sinistra.

11. Selezionare il modello **finestra (WPF)** , denominarlo `RehostingWFDesigner` e fare clic su **Aggiungi**.

12. Aprire il file *RehostingWFDesigner. XAML* e incollarvi il codice seguente per definire l'interfaccia utente per l'applicazione:

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

13. Per associare un ActivityDesigner a un tipo di attività, è necessario registrare tale ActivityDesigner con l'archivio dei metadati. A tal fine, aggiungere il metodo `RegisterMetadata` alla classe `RehostingWFDesigner`. Nell'ambito del metodo `RegisterMetadata` creare un oggetto <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> e chiamare il metodo <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> per aggiungervi attributi. Chiamare il metodo <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> per aggiungere l'oggetto <xref:System.Activities.Presentation.Metadata.AttributeTable> all'archivio dei metadati. Il codice seguente contiene la logica di riallocazione per la finestra di progettazione. Registra i metadati, inserisce `SimpleNativeActivity` nella casella degli strumenti e crea il flusso di lavoro. Inserire questo codice nel file *RehostingWFDesigner.XAML.cs* .

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

14. Fare clic con il pulsante destro del mouse sulla directory References in Esplora soluzioni e scegliere **Aggiungi riferimento.** per visualizzare la finestra di dialogo **Aggiungi riferimento** .

15. Fare clic sulla scheda **.NET** , individuare l'assembly denominato **System. Activities. Core. Presentation**, selezionarlo e fare clic su **OK**.

16. Tramite la stessa procedura aggiungere riferimenti agli assembly indicati di seguito:

    1. System.Data.DataSetExtensions.dll

    2. System.Activities.Presentation.dll

    3. System.ServiceModel.Activities.dll

17. Aprire il file *app. XAML* e modificare il valore di StartupUri in "RehostingWFDesigner. xaml".

18. Fare clic con il pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora soluzioni**, scegliere **Aggiungi**, quindi **nuovo elemento...** per visualizzare la finestra di dialogo **Aggiungi nuovo elemento** e selezionare la categoria **flusso di lavoro** nella sezione **modelli installati** a sinistra.

19. Selezionare il **modello ActivityDesigner,** denominarlo `SimpleNativeDesigner` e fare clic su **Aggiungi**.

20. Aprire il file *SimpleNativeDesigner. XAML* e incollarvi il codice seguente. Questo codice usa <xref:System.Activities.Presentation.ActivityDesigner> come elemento radice e illustra come usare l'associazione per  integrare <xref:System.Activities.Presentation.WorkflowItemPresenter> nella finestra di progettazione in modo da poter visualizzare un tipo figlio nel CompositeActivityDesigner.

    > [!NOTE]
    > Lo schema dell'oggetto <xref:System.Activities.Presentation.ActivityDesigner> consente di aggiungere un unico elemento figlio alla definizione dell'ActivityDesigner personalizzato. Questo elemento, tuttavia, potrebbe essere un oggetto `StackPanel`, `Grid` o un altro elemento composito dell'interfaccia utente.

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

21. Fare clic con il pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora soluzioni**, scegliere **Aggiungi**, quindi **nuovo elemento...** per visualizzare la finestra di dialogo **Aggiungi nuovo elemento** e selezionare la categoria **flusso di lavoro** nella sezione **modelli installati** a sinistra.

22. Selezionare il modello **attività codice** , denominarlo `SimpleNativeActivity` e fare clic su **Aggiungi**.

23. Implementare la `SimpleNativeActivity` classe immettendo il codice seguente nel file *SimpleNativeActivity.cs* :

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

24. Scegliere **Compila soluzione** dal menu **Compila** .

25. Selezionare **Avvia senza eseguire debug** dal menu **debug** per aprire la finestra di progettazione personalizzata riallocata.

### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a>Per creare un ActivityDesigner personalizzato usando WorkflowItemsPresenter

1. La procedura per il secondo ActivityDesigner personalizzato è Parallels alla prima con alcune modifiche, la prima delle quali consiste nel denominare la seconda applicazione `UsingWorkflowItemsPresenter` . Questa applicazione non definisce inoltre una nuova attività personalizzata.

2. Le differenze principali sono contenute nei file *CustomParallelDesigner. XAML* e *RehostingWFDesigner.XAML.cs* . Ecco il codice del file *CustomParallelDesigner. XAML* che definisce l'interfaccia utente:

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

3. Ecco il codice del file *RehostingWFDesigner.XAML.cs* che fornisce la logica di riallocazione:

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

## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Presentation.ActivityDesigner>
- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- <xref:System.Activities.Presentation.WorkflowViewElement>
- <xref:System.Activities.Presentation.Model.ModelItem>
- [Personalizzazione della fase di progettazione del flusso di lavoro](customizing-the-workflow-design-experience.md)
