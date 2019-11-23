---
title: "Attività 2: ospitare l'utilità di progettazione del flusso di lavoro"
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 15657ad79632812d3802e4da22b9ef297d08f932
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180255"
---
# <a name="task-2-host-the-workflow-designer"></a>Attività 2: ospitare l'utilità di progettazione del flusso di lavoro

In questo argomento viene descritta la procedura per ospitare un'istanza del [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in un'applicazione Windows Presentation Foundation (WPF).

Nella procedura viene configurato il controllo **Grid** che contiene la finestra di progettazione, viene creata a livello di codice un'istanza del <xref:System.Activities.Presentation.WorkflowDesigner> che contiene un'attività <xref:System.Activities.Statements.Sequence> predefinita, vengono registrati i metadati della finestra di progettazione per fornire supporto della finestra di progettazione per tutte le attività predefinite e vengono ospitati i [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] nell'applicazione WPF.

## <a name="to-host-the-workflow-designer"></a>Per ospitare la finestra di progettazione del flusso di lavoro

1. Aprire il progetto HostingApplication creato nell' [attività 1: creare una nuova applicazione Windows Presentation Foundation](task-1-create-a-new-wpf-app.md).

2. Regolare le dimensioni della finestra per semplificare l'uso di [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. A tale scopo, selezionare **MainWindow** nella finestra di progettazione, premere F4 per visualizzare la finestra **Proprietà** e, nella sezione del **layout** , impostare la **larghezza** su un valore 600 e l' **altezza** su un valore pari a 350.

3. Impostare il nome della griglia selezionando il pannello **griglia** nella finestra di progettazione (fare clic sulla casella all'interno di **MainWindow**) e impostare la proprietà **Name** nella parte superiore della finestra **Proprietà** su "Grid1".

4. Nella finestra **Proprietà** fare clic sui puntini di sospensione ( **...** ) accanto alla proprietà `ColumnDefinitions` per aprire la finestra di dialogo **Editor della raccolta** .

5. Nella finestra di dialogo **Editor della raccolta** fare clic tre volte sul pulsante **Aggiungi** per inserire tre colonne nel layout. La prima colonna conterrà la **casella degli strumenti**, la seconda colonna ospiterà il [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]e la terza colonna verrà utilizzata per il controllo proprietà.

6. Impostare la proprietà `Width` della colonna intermedia sul valore "4 *".

7. Fare clic su **OK** per salvare le modifiche. Il codice XAML seguente viene aggiunto al file *MainWindow. XAML* :

    ```xaml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. In **Esplora soluzioni**fare clic con il pulsante destro del mouse su *MainWindow. XAML* e selezionare **Visualizza codice**. Modificare il codice attenendosi ai passaggi seguenti:

    1. Aggiungere gli spazi dei nomi seguenti:

        ```csharp
        using System.Activities;
        using System.Activities.Core.Presentation;
        using System.Activities.Presentation;
        using System.Activities.Presentation.Metadata;
        using System.Activities.Presentation.Toolbox;
        using System.Activities.Statements;
        using System.ComponentModel;
        ```

    2. Per dichiarare un campo membro privato che contenga un'istanza del <xref:System.Activities.Presentation.WorkflowDesigner>, aggiungere il codice seguente alla classe `MainWindow`:

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

    3. Aggiungere il metodo `AddDesigner` seguente alla classe `MainWindow`. L'implementazione crea un'istanza del <xref:System.Activities.Presentation.WorkflowDesigner>, aggiunge un'attività <xref:System.Activities.Statements.Sequence> e la inserisce nella colonna centrale della **griglia**Grid1.

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

    4. Registrare i metadati della finestra di progettazione per aggiungere il supporto della finestra di progettazione per tutte le attività incorporate. In questo modo sarà possibile spostare le attività dalla casella degli strumenti all'attività <xref:System.Activities.Statements.Sequence> originale in [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]. A tale scopo, aggiungere il metodo `RegisterMetadata` alla classe `MainWindow`:

        ```csharp
        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        Per ulteriori informazioni sulla registrazione di ActivityDesigner, vedere [procedura: creare un ActivityDesigner personalizzato](how-to-create-a-custom-activity-designer.md).

    5. Nel costruttore della classe `MainWindow`, aggiungere chiamate ai metodi dichiarati precedentemente per registrare i metadati per il supporto della finestra di progettazione e per creare l'oggetto <xref:System.Activities.Presentation.WorkflowDesigner>.

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
        > Il metodo `RegisterMetadata` registra i metadati della finestra di progettazione di attività incorporate, inclusa l'attività <xref:System.Activities.Statements.Sequence>. Poiché il metodo `AddDesigner` usa l'attività <xref:System.Activities.Statements.Sequence>, è necessario chiamare innanzitutto il metodo `RegisterMetadata`.

9. Premere <kbd>F5</kbd> per compilare ed eseguire la soluzione.

10. Vedere [attività 3: creare i riquadri Casella degli strumenti e PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md) per informazioni su come aggiungere la **casella degli strumenti** e il supporto **PropertyGrid** alla finestra di progettazione flussi di lavoro riallocata.

## <a name="see-also"></a>Vedere anche

- [Riallocazione di Progettazione flussi di lavoro](rehosting-the-workflow-designer.md)
- [Attività 1: Creare una nuova applicazione Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
- [Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md)
