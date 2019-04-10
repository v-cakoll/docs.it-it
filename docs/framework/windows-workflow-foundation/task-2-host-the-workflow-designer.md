---
title: 'Attività 2: Ospitare Progettazione flussi di lavoro'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 3f7964e907fe513679e60c18292f07c84128590b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299267"
---
# <a name="task-2-host-the-workflow-designer"></a>Attività 2: Ospitare Progettazione flussi di lavoro
In questo argomento viene descritta la procedura per l'hosting di un'istanza di [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in un'applicazione Windows Presentation Foundation (WPF).  
  
 La procedura consente di configurare il **griglia** controllo che contiene la finestra di progettazione, a livello di codice crea un'istanza del <xref:System.Activities.Presentation.WorkflowDesigner> che contiene un valore predefinito <xref:System.Activities.Statements.Sequence> attività, registra i metadati della finestra di progettazione per fornire supporto di progettazione per attività tutte predefinite e gli host il [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] nella [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] dell'applicazione.  
  
### <a name="to-host-the-workflow-designer"></a>Per ospitare la finestra di progettazione del flusso di lavoro  
  
1. Aprire il progetto HostingApplication creato in [attività 1: Creare una nuova applicazione Windows Presentation Foundation](task-1-create-a-new-wpf-app.md).  
  
2. Regolare le dimensioni della finestra per semplificare l'uso di [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. A questo scopo, selezionare **MainWindow** nella finestra di progettazione, premere F4 per visualizzare i **proprietà** finestra e, nella **Layout** sezione non esiste, impostare il **larghezza** su un valore pari a 600 e il **altezza** su un valore di 350.  
  
3. Impostare il nome della griglia selezionando il **griglia** pannello nella finestra di progettazione (fare clic sulla casella all'interno del **MainWindow**) e impostando il **nome** proprietà nella parte superiore del  **Proprietà** finestra su "grid1".  
  
4. Nel **delle proprietà** finestra, fare clic sui puntini di sospensione (**...** ) accanto al `ColumnDefinitions` per aprire il **Editor della raccolta** nella finestra di dialogo.  
  
5. Nel **Editor della raccolta** della finestra di dialogo fare clic sui **Add** tre volte per inserire tre colonne nel layout. La prima colonna conterrà il **della casella degli strumenti**, mentre la seconda ospiterà il [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], e la terza colonna verrà utilizzata per il controllo proprietà.  
  
6. Impostare il `Width` proprietà della colonna centrale sul valore "4 *".  
  
7. Fare clic su **OK** per salvare le modifiche. Il seguente codice XAML viene aggiunto al file MainWindow.xaml:  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8. Nelle **Esplora soluzioni**, fare doppio clic su MainWindow. XAML e selezionare **Visualizza codice**. Modificare il codice attenendosi ai passaggi seguenti:  
  
    1.  Aggiungere gli spazi dei nomi seguenti:  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2.  Per dichiarare un campo membro privato per contenere un'istanza di <xref:System.Activities.Presentation.WorkflowDesigner>, aggiungere il codice seguente alla classe `MainWindow`.  
  
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
  
    3.  Aggiungere il metodo `AddDesigner` seguente alla classe `MainWindow`. L'implementazione crea un'istanza di <xref:System.Activities.Presentation.WorkflowDesigner>, aggiunge un <xref:System.Activities.Statements.Sequence> attività e lo inserisce nella colonna centrale della grid1 **griglia**.  
  
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
  
    4.  Registrare i metadati della finestra di progettazione per aggiungere il supporto della finestra di progettazione per tutte le attività incorporate. In questo modo sarà possibile spostare le attività dalla casella degli strumenti all'attività <xref:System.Activities.Statements.Sequence> originale in [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. A tal fine, aggiungere il metodo `RegisterMetadata` alla classe `MainWindow`.  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         Per altre informazioni sulla registrazione di ActivityDesigner, vedere [come: Creare un ActivityDesigner personalizzato](how-to-create-a-custom-activity-designer.md).  
  
    5.  Nel costruttore della classe `MainWindow`, aggiungere chiamate ai metodi dichiarati precedentemente per registrare i metadati per il supporto della finestra di progettazione e per creare l'oggetto <xref:System.Activities.Presentation.WorkflowDesigner>.  
  
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
        >  Il metodo `RegisterMetadata` registra i metadati della finestra di progettazione di attività incorporate, inclusa l'attività <xref:System.Activities.Statements.Sequence>. Poiché il metodo `AddDesigner` usa l'attività <xref:System.Activities.Statements.Sequence>, è necessario chiamare innanzitutto il metodo `RegisterMetadata`.  
  
9. Premere F5 per compilare ed eseguire la soluzione.  
  
10. Vedere [attività 3: Creare la casella degli strumenti e riquadri PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md) per informazioni su come aggiungere **casella degli strumenti** e **PropertyGrid** supportano alla finestra di progettazione del flusso di lavoro ospitata nuovamente.  
  
## <a name="see-also"></a>Vedere anche

- [Riallocazione dell'utilità di progettazione del flusso di lavoro](rehosting-the-workflow-designer.md)
- [Attività 1: Creare una nuova applicazione Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
- [Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md)
