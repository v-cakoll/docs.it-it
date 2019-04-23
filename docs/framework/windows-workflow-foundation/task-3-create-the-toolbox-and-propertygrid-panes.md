---
title: 'Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 15e5b4ea08b6bc243484b6963c1c06f448bb985b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306016"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid
In questa attività si creerà il **casella degli strumenti** e **PropertyGrid** riquadri e aggiungerle a riallocato [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].  
  
 Per riferimento, il codice che deve essere nel file MainWindow.xaml.cs dopo aver completato le tre attività nel [riallocazione della finestra di progettazione del flusso di lavoro](rehosting-the-workflow-designer.md) serie di argomenti viene fornito alla fine di questo argomento.  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>Per creare la casella degli strumenti e aggiungerla alla griglia  
  
1. Aprire il progetto HostingApplication ottenuto seguendo la procedura descritta in [attività 2: Ospitare la finestra di progettazione del flusso di lavoro](task-2-host-the-workflow-designer.md).  
  
2. Nel **Esplora soluzioni** riquadro, fare clic sul file MainWindow. XAML e selezionare **Visualizza codice**.  
  
3. Aggiungere un `GetToolboxControl` metodo per il `MainWindow` classe che crea un <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, aggiunge un nuovo **della casella degli strumenti** categoria per il **casella degli strumenti**e assegna la <xref:System.Activities.Statements.Assign> e <xref:System.Activities.Statements.Sequence> tipi di attività per tale categoria.  
  
    ```csharp  
    private ToolboxControl GetToolboxControl()  
    {  
        // Create the ToolBoxControl.  
        ToolboxControl ctrl = new ToolboxControl();  
  
        // Create a category.  
        ToolboxCategory category = new ToolboxCategory("category1");  
  
        // Create Toolbox items.  
        ToolboxItemWrapper tool1 =   
            new ToolboxItemWrapper("System.Activities.Statements.Assign",   
            typeof(Assign).Assembly.FullName, null, "Assign");  
  
        ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",   
            typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
        // Add the Toolbox items to the category.  
        category.Add(tool1);  
        category.Add(tool2);  
  
        // Add the category to the ToolBox control.  
        ctrl.Categories.Add(category);  
        return ctrl;  
    }  
    ```  
  
4. Aggiungere una privata `AddToolbox` metodo per il `MainWindow` classe che inserisce il **della casella degli strumenti** nella colonna sinistra sulla griglia.  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5. Aggiungere una chiamata al metodo `AddToolBox` nel costruttore della classe `MainWindow()` come illustrato nel codice seguente.  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6. Premere F5 per compilare ed eseguire la soluzione. Il **casella degli strumenti** contenente le <xref:System.Activities.Statements.Assign> e <xref:System.Activities.Statements.Sequence> attività devono essere visualizzate.  
  
### <a name="to-create-the-propertygrid"></a>Per creare il riquadro PropertyGrid  
  
1. Nel **Esplora soluzioni** riquadro, fare clic sul file MainWindow. XAML e selezionare **Visualizza codice**.  
  
2. Aggiungere il `AddPropertyInspector` metodo per il `MainWindow` classe per posizionare il **PropertyGrid** riquadro in colonna all'estremità destra nella griglia.  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3. Aggiungere una chiamata al metodo `AddPropertyInspector` nel costruttore della classe `MainWindow()` come illustrato nel codice seguente.  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
        this.AddToolBox();  
  
        this.AddPropertyInspector();   
    }  
    ```  
  
4. Premere F5 per compilare ed eseguire la soluzione. Il **casella degli strumenti**, canvas di progettazione del flusso di lavoro, e **PropertyGrid** riquadri devono essere visualizzati e quando si trascina un' <xref:System.Activities.Statements.Assign> attività o un <xref:System.Activities.Statements.Sequence> attività nell'area di progettazione, il griglia delle proprietà è necessario aggiornare a seconda dell'attività evidenziata.  
  
## <a name="example"></a>Esempio  
 Il file MainWindow.xaml.cs ora deve contenere il codice seguente.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
//dlls added  
using System.Activities;  
using System.Activities.Core.Presentation;  
using System.Activities.Presentation;  
using System.Activities.Presentation.Metadata;  
using System.Activities.Presentation.Toolbox;  
using System.Activities.Statements;  
using System.ComponentModel;  
  
namespace HostingApplication  
{  
    /// <summary>  
    /// Interaction logic for MainWindow.xaml  
    /// </summary>  
    public partial class MainWindow : Window  
    {  
        private WorkflowDesigner wd;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
            RegisterMetadata();  
            AddDesigner();  
            this.AddToolBox();  
            this.AddPropertyInspector();  
        }  
  
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
  
        private void RegisterMetadata()  
        {  
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        private ToolboxControl GetToolboxControl()  
        {  
            // Create the ToolBoxControl.  
            ToolboxControl ctrl = new ToolboxControl();  
  
            // Create a category.  
            ToolboxCategory category = new ToolboxCategory("category1");  
  
            // Create Toolbox items.  
            ToolboxItemWrapper tool1 =  
                new ToolboxItemWrapper("System.Activities.Statements.Assign",  
                typeof(Assign).Assembly.FullName, null, "Assign");  
  
            ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",  
                typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
            // Add the Toolbox items to the category.  
            category.Add(tool1);  
            category.Add(tool2);  
  
            // Add the category to the ToolBox control.  
            ctrl.Categories.Add(category);  
            return ctrl;  
        }  
  
        private void AddToolBox()  
        {  
            ToolboxControl tc = GetToolboxControl();  
            Grid.SetColumn(tc, 0);  
            grid1.Children.Add(tc);  
        }  
  
        private void AddPropertyInspector()  
        {  
            Grid.SetColumn(wd.PropertyInspectorView, 2);  
            grid1.Children.Add(wd.PropertyInspectorView);  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Riallocazione di Progettazione flussi di lavoro](rehosting-the-workflow-designer.md)
- [Attività 1: Creare una nuova applicazione Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
- [Attività 2: Host di progettazione del flusso di lavoro](task-2-host-the-workflow-designer.md)
