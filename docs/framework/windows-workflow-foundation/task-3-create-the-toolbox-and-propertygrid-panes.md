---
title: 'Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 6339969c52a5c4eedfb0e89eebdc982ca3fe6686
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988705"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid
In questa attività verranno creati i riquadri **casella degli strumenti** e **PropertyGrid** e verranno aggiunti al riallocato [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].  
  
 Per riferimento, al termine di questo argomento viene fornito il codice che deve trovarsi nel file MainWindow.xaml.cs dopo aver completato le tre attività riportate nella sezione relativa alla [riallocazione della progettazione flussi di lavoro](rehosting-the-workflow-designer.md) serie di argomenti.  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>Per creare la casella degli strumenti e aggiungerla alla griglia  
  
1. Aprire il progetto HostingApplication ottenuto seguendo la procedura descritta nell' [attività 2: Ospitare il Progettazione flussi di lavoro](task-2-host-the-workflow-designer.md).  
  
2. Nel riquadro **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file MainWindow. XAML e selezionare **Visualizza codice**.  
  
3. Aggiungere un `GetToolboxControl` `MainWindow` metodo alla classe che crea un oggetto <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, aggiunge una nuova categoria della **casella degli strumenti** alla **casella degli**strumenti e <xref:System.Activities.Statements.Assign> assegna <xref:System.Activities.Statements.Sequence> i tipi di attività e alla categoria.  
  
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
  
4. Aggiungere un metodo `AddToolbox` privato `MainWindow` alla classe che posiziona la **casella degli strumenti** nella colonna sinistra della griglia.  
  
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
  
6. Premere F5 per compilare ed eseguire la soluzione. La **casella degli strumenti** <xref:System.Activities.Statements.Assign> contenente <xref:System.Activities.Statements.Sequence> le attività e deve essere visualizzata.  
  
### <a name="to-create-the-propertygrid"></a>Per creare il riquadro PropertyGrid  
  
1. Nel riquadro **Esplora soluzioni** fare clic con il pulsante destro del mouse sul file MainWindow. XAML e selezionare **Visualizza codice**.  
  
2. Aggiungere il `AddPropertyInspector` metodo `MainWindow` alla classe per posizionare il riquadro **PropertyGrid** nella colonna più a destra nella griglia.  
  
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
  
4. Premere F5 per compilare ed eseguire la soluzione. La **casella degli strumenti**, l'area di disegno del flusso di lavoro e i riquadri **PropertyGrid** dovrebbero essere tutti <xref:System.Activities.Statements.Assign> visualizzati e quando <xref:System.Activities.Statements.Sequence> si trascina un'attività o un'attività nell'area di disegno, la griglia delle proprietà deve essere aggiornata a seconda del attività evidenziata.  
  
## <a name="example"></a>Esempio  
 Il file MainWindow.xaml.cs ora deve contenere il codice seguente.  
  
```csharp  
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
- [Attività 2: Ospitare il Progettazione flussi di lavoro](task-2-host-the-workflow-designer.md)
