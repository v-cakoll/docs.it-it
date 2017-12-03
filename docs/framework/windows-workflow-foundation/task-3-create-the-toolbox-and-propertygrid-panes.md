---
title: "Attività 3: creare i riquadri Casella degli strumenti e PropertyGrid"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cfb1d09fc8bc52a03576054197488dff0aacf841
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>Attività 3: creare i riquadri Casella degli strumenti e PropertyGrid
In questa attività si creerà il **della casella degli strumenti** e **PropertyGrid** riquadri e li aggiunge riallocato [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].  
  
 Per riferimento, il codice che deve essere nel file MainWindow.xaml.cs dopo aver completato le tre attività di [riallocazione della finestra di progettazione del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md) serie di argomenti viene fornito alla fine di questo argomento.  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>Per creare la casella degli strumenti e aggiungerla alla griglia  
  
1.  Aprire il progetto HostingApplication ottenuto seguendo la procedura descritta in [attività 2: ospitare la finestra di progettazione del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md).  
  
2.  Nel **Esplora** riquadro, il file MainWindow. XAML e scegliere **Visualizza codice**.  
  
3.  Aggiungere un `GetToolboxControl` metodo il `MainWindow` classe che crea un <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, aggiunge un nuovo **della casella degli strumenti** categoria per il **della casella degli strumenti**e assegna il <xref:System.Activities.Statements.Assign> e <xref:System.Activities.Statements.Sequence> tipi di attività per tale categoria.  
  
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
  
4.  Aggiungere una privata `AddToolbox` metodo il `MainWindow` classe che inserisce il **della casella degli strumenti** nella colonna sinistra sulla griglia.  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5.  Aggiungere una chiamata al metodo `AddToolBox` nel costruttore della classe `MainWindow()` come illustrato nel codice seguente.  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6.  Premere F5 per compilare ed eseguire la soluzione. Il **della casella degli strumenti** contenente il <xref:System.Activities.Statements.Assign> e <xref:System.Activities.Statements.Sequence> attività devono essere visualizzate.  
  
### <a name="to-create-the-propertygrid"></a>Per creare il riquadro PropertyGrid  
  
1.  Nel **Esplora** riquadro, il file MainWindow. XAML e scegliere **Visualizza codice**.  
  
2.  Aggiungere il `AddPropertyInspector` metodo il `MainWindow` classe per inserire il **PropertyGrid** riquadro nella colonna più a destra sulla griglia.  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3.  Aggiungere una chiamata al metodo `AddPropertyInspector` nel costruttore della classe `MainWindow()` come illustrato nel codice seguente.  
  
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
  
4.  Premere F5 per compilare ed eseguire la soluzione. Il **della casella degli strumenti**, area di progettazione del flusso di lavoro, e **PropertyGrid** riquadri devono essere visualizzati e quando si trascina un <xref:System.Activities.Statements.Assign> attività o un <xref:System.Activities.Statements.Sequence> attività nell'area di disegno di progettazione, il griglia delle proprietà è necessario aggiornare a seconda dell'attività evidenziata.  
  
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
 [Riallocazione di Progettazione flussi di lavoro](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [Attività 1: Creare una nuova applicazione Windows Presentation Foundation](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
 [Attività 2: Ospitare Progettazione flussi di lavoro](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
