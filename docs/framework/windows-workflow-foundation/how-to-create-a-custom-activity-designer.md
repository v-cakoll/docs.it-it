---
title: 'Procedura: Creare un ActivityDesigner personalizzato'
ms.date: 03/30/2017
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
ms.openlocfilehash: e4aab60a598be2d6df5546ab1c98a289b4aef04a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520344"
---
# <a name="how-to-create-a-custom-activity-designer"></a>Procedura: Creare un ActivityDesigner personalizzato
Gli ActivityDesigner personalizzati vengono in genere implementati in modo che le attività associate siano componibili con altre attività le cui finestre di progettazione possono essere rilasciate sull'area di progettazione insieme ad esse. Questa funzionalità richiede che un ActivityDesigner personalizzato fornisca un' "area di rilascio" in cui è possibile posizionare un'attività arbitraria, nonché i mezzi per gestire la raccolta di elementi nell'area di progettazione risultante. In questo argomento viene descritto come creare un ActivityDesigner personalizzato contenente tale area di rilascio e come creare un ActivityDesigner personalizzato che fornisca la funzionalità di modifica necessaria per gestire la raccolta di elementi della finestra di progettazione.  
  
 L'ActivityDesigner personalizzato eredita in genere da <xref:System.Activities.Presentation.ActivityDesigner> che è il tipo di ActivityDesigner di base predefinito per qualsiasi attività senza una finestra di progettazione specifica. Questo tipo fornisce una fase di progettazione per l'interazione con la griglia delle proprietà e per la configurazione degli aspetti di base, ad esempio la gestione di colori e icone.  
  
 L'oggetto <xref:System.Activities.Presentation.ActivityDesigner> usa due controlli di supporto, <xref:System.Activities.Presentation.WorkflowItemPresenter> e <xref:System.Activities.Presentation.WorkflowItemsPresenter>, per facilitare lo sviluppo di ActivityDesigner personalizzati. Questi consentono di gestire funzionalità comuni quali il trascinamento e rilascio di elementi figlio, l'eliminazione, la selezione nonché l'aggiunta di tali elementi figlio. Il <xref:System.Activities.Presentation.WorkflowItemPresenter> consente a un singolo elemento figlio elemento dell'interfaccia utente, fornendo il "area di rilascio", mentre il <xref:System.Activities.Presentation.WorkflowItemsPresenter> possibile fornire supporto di più elementi dell'interfaccia utente, incluse le funzionalità aggiuntive quali ordinamento, spostamento, eliminazione e aggiunta di elementi figlio.  
  
 L'altro aspetto principale che è opportuno evidenziare nell'implementazione di un ActivityDesigner personalizzato riguarda il modo in cui vengono associate le modifiche visive usando l'associazione dati di [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] all'istanza archiviata in memoria degli elementi in fase di modifica nella finestra di progettazione. Questa operazione viene eseguita dall'albero degli elementi del modello che è inoltre responsabile per l'abilitazione della notifica di modifiche e il rilevamento di eventi quali le modifiche degli stati.  
  
 In questo argomento vengono delineate due procedure.  
  
1.  Nella prima viene descritto come creare un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemPresenter> che fornisce l'area di rilascio che riceve altre attività. Questa procedura si basa sul [finestre di progettazione Composite personalizzate - relatore di elementi del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-item-presenter.md) esempio.  
  
2.  Nella seconda viene descritto come creare un ActivityDesigner personalizzato con un <xref:System.Activities.Presentation.WorkflowItemsPresenter> che fornisce la funzionalità necessaria per modificare una raccolta di elementi contenuti. Questa procedura si basa sul [finestre di progettazione Composite personalizzate - relatore di elementi del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/samples/custom-composite-designers-workflow-items-presenter.md) esempio.  
  
### <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a>Per creare un ActivityDesigner personalizzato con un'area di rilascio usando WorkflowItemPresenter  
  
1.  Avviare [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Nel **File** dal menu **New**, quindi selezionare **progetto...** .  
  
     Verrà visualizzata la finestra di dialogo **Nuovo progetto** .  
  
3.  Nel **modelli installati** riquadro, selezionare **Windows** dalla categoria di linguaggio preferita.  
  
4.  Nel **modelli** riquadro, selezionare **applicazione WPF**.  
  
5.  Nel **nome** immettere `UsingWorkflowItemPresenter`.  
  
6.  Nel **percorso** , immettere la directory in cui si desidera salvare il progetto oppure fare clic su **Sfoglia** per passare a tale.  
  
7.  Nel **soluzione** casella, accettare il valore predefinito.  
  
8.  Fare clic su **OK**.  
  
9. Il file MainWindows nel **Esplora**selezionare **eliminare** e confermare **OK** nel **Microsoft Visual Studio**finestra di dialogo.  
  
10. Pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora soluzioni**, selezionare **Add**, quindi **nuovo elemento...** Per visualizzare il **Aggiungi nuovo elemento** finestra di dialogo e selezionare il **WPF** categoria di **modelli installati** sezione a sinistra.  
  
11. Selezionare il **finestra (WPF)** modello, il nome `RehostingWFDesigner`, fare clic su **Aggiungi**.  
  
12. Aprire il file RehostingWFDesigner.xaml e incollarvi il codice seguente per definire l'interfaccia utente per l'applicazione.  
  
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
  
13. Per associare un ActivityDesigner a un tipo di attività, è necessario registrare tale ActivityDesigner con l'archivio dei metadati. A tal fine, aggiungere il metodo `RegisterMetadata` alla classe `RehostingWFDesigner`. Nell'ambito del metodo `RegisterMetadata` creare un oggetto <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder> e chiamare il metodo <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A> per aggiungervi attributi. Chiamare il metodo <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A> per aggiungere l'oggetto <xref:System.Activities.Presentation.Metadata.AttributeTable> all'archivio dei metadati. Il codice seguente contiene la logica di riallocazione per la finestra di progettazione. Registra i metadati, inserisce `SimpleNativeActivity` nella casella degli strumenti e crea il flusso di lavoro. Inserire il codice seguente nel file RehostingWFDesigner.xaml.cs.  
  
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
  
14. La directory dei riferimenti in Esplora soluzioni e scegliere **Aggiungi riferimento...** Per visualizzare il **Aggiungi riferimento** finestra di dialogo.  
  
15. Fare clic su di **.NET** , individuare l'assembly denominato **System.Activities.Core.Presentation**, selezionarlo e fare clic su **OK**.  
  
16. Tramite la stessa procedura aggiungere riferimenti agli assembly indicati di seguito:  
  
    1.  System.Data.DataSetExtensions.dll  
  
    2.  System.Activities.Presentation.dll  
  
    3.  System.ServiceModel.Activities.dll  
  
17. Aprire il file app. XAML e impostare il valore di StartUpUri su "Rehostingwfdesigner".  
  
18. Pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora soluzioni**, selezionare **Add**, quindi **nuovo elemento...** Per visualizzare il **Aggiungi nuovo elemento** finestra di dialogo e selezionare il **flusso di lavoro** categoria di **modelli installati** sezione a sinistra.  
  
19. Selezionare il **ActivityDesigner** modello, il nome `SimpleNativeDesigner`, fare clic su **Aggiungi**.  
  
20. Aprire il file SimpleNativeDesigner.xaml e incollarvi il codice riportato di seguito. Questo codice usa <xref:System.Activities.Presentation.ActivityDesigner> come elemento radice e illustra come usare l'associazione per  integrare <xref:System.Activities.Presentation.WorkflowItemPresenter> nella finestra di progettazione in modo da poter visualizzare un tipo figlio nel CompositeActivityDesigner.  
  
    > [!NOTE]
    >  Lo schema dell'oggetto <xref:System.Activities.Presentation.ActivityDesigner> consente di aggiungere un unico elemento figlio alla definizione dell'ActivityDesigner personalizzato. Questo elemento, tuttavia, potrebbe essere un oggetto `StackPanel`, `Grid` o un altro elemento composito dell'interfaccia utente.  
  
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
  
21. Pulsante destro del mouse sul progetto UsingWorkflowItemPresenter in **Esplora soluzioni**, selezionare **Add**, quindi **nuovo elemento...** Per visualizzare il **Aggiungi nuovo elemento** finestra di dialogo e selezionare il **flusso di lavoro** categoria di **modelli installati** sezione a sinistra.  
  
22. Selezionare il **attività codice** modello, il nome `SimpleNativeActivity`, fare clic su **Aggiungi**.  
  
23. Implementare la classe `SimpleNativeActivity` immettendo il codice seguente nel file SimpleNativeActivity.cs.  
  
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
  
24. Selezionare **Compila soluzione** dal **compilare** menu.  
  
25. Selezionare **Avvia senza eseguire debug** dal **Debug** menu per aprire la finestra di progettazione riallocata.  
  
### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a>Per creare un ActivityDesigner personalizzato usando WorkflowItemsPresenter  
  
1.  La procedura per il secondo ActivityDesigner personalizzato è analoga alla prima con alcune modifiche, la prima delle quali viene assegnato un nome della seconda applicazione `UsingWorkflowItemsPresenter`. Questa applicazione non definisce inoltre una nuova attività personalizzata.  
  
2.  Le differenze principali sono contenute nei file CustomParallelDesigner.xaml e  RehostingWFDesigner.xaml.cs. Di seguito è riportato il codice del file CustomParallelDesigne.xaml che definisce l'interfaccia utente.  
  
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
  
3.  Di seguito è riportato il codice dal file RehostingWFDesigner.xaml.cs che fornisce la logica di riallocazione.  
  
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
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Activities.Presentation.ActivityDesigner>  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>  
 <xref:System.Activities.Presentation.WorkflowViewElement>  
 <xref:System.Activities.Presentation.Model.ModelItem>  
 [Personalizzazione della fase di progettazione del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/customizing-the-workflow-design-experience.md)
