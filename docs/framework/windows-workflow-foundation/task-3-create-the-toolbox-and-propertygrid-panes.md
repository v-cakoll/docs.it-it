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
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a><span data-ttu-id="7a8af-102">Attività 3: creare i riquadri Casella degli strumenti e PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="7a8af-102">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>
<span data-ttu-id="7a8af-103">In questa attività si creerà il **della casella degli strumenti** e **PropertyGrid** riquadri e li aggiunge riallocato [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a8af-103">In this task, you will create the **Toolbox** and **PropertyGrid** panes and add them to the rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span>  
  
 <span data-ttu-id="7a8af-104">Per riferimento, il codice che deve essere nel file MainWindow.xaml.cs dopo aver completato le tre attività di [riallocazione della finestra di progettazione del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md) serie di argomenti viene fornito alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="7a8af-104">For reference, the code that should be in the MainWindow.xaml.cs file after completing the three tasks in the [Rehosting the Workflow Designer](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md) series of topics is provided at the end of this topic.</span></span>  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a><span data-ttu-id="7a8af-105">Per creare la casella degli strumenti e aggiungerla alla griglia</span><span class="sxs-lookup"><span data-stu-id="7a8af-105">To create the Toolbox and add it to the grid</span></span>  
  
1.  <span data-ttu-id="7a8af-106">Aprire il progetto HostingApplication ottenuto seguendo la procedura descritta in [attività 2: ospitare la finestra di progettazione del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md).</span><span class="sxs-lookup"><span data-stu-id="7a8af-106">Open the HostingApplication project you obtained by following the procedure described in [Task 2: Host the Workflow Designer](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md).</span></span>  
  
2.  <span data-ttu-id="7a8af-107">Nel **Esplora** riquadro, il file MainWindow. XAML e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="7a8af-107">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
3.  <span data-ttu-id="7a8af-108">Aggiungere un `GetToolboxControl` metodo il `MainWindow` classe che crea un <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, aggiunge un nuovo **della casella degli strumenti** categoria per il **della casella degli strumenti**e assegna il <xref:System.Activities.Statements.Assign> e <xref:System.Activities.Statements.Sequence> tipi di attività per tale categoria.</span><span class="sxs-lookup"><span data-stu-id="7a8af-108">Add a `GetToolboxControl` method to the `MainWindow` class that creates a <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, adds a new **Toolbox** category to the **Toolbox**, and assigns the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activity types to that category.</span></span>  
  
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
  
4.  <span data-ttu-id="7a8af-109">Aggiungere una privata `AddToolbox` metodo il `MainWindow` classe che inserisce il **della casella degli strumenti** nella colonna sinistra sulla griglia.</span><span class="sxs-lookup"><span data-stu-id="7a8af-109">Add a private `AddToolbox` method to the `MainWindow` class that places the **Toolbox** in the left column on the grid.</span></span>  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5.  <span data-ttu-id="7a8af-110">Aggiungere una chiamata al metodo `AddToolBox` nel costruttore della classe `MainWindow()` come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7a8af-110">Add a call to the `AddToolBox` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6.  <span data-ttu-id="7a8af-111">Premere F5 per compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="7a8af-111">Press F5 to build and run your solution.</span></span> <span data-ttu-id="7a8af-112">Il **della casella degli strumenti** contenente il <xref:System.Activities.Statements.Assign> e <xref:System.Activities.Statements.Sequence> attività devono essere visualizzate.</span><span class="sxs-lookup"><span data-stu-id="7a8af-112">The **Toolbox** containing the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activities should be displayed.</span></span>  
  
### <a name="to-create-the-propertygrid"></a><span data-ttu-id="7a8af-113">Per creare il riquadro PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="7a8af-113">To create the PropertyGrid</span></span>  
  
1.  <span data-ttu-id="7a8af-114">Nel **Esplora** riquadro, il file MainWindow. XAML e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="7a8af-114">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
2.  <span data-ttu-id="7a8af-115">Aggiungere il `AddPropertyInspector` metodo il `MainWindow` classe per inserire il **PropertyGrid** riquadro nella colonna più a destra sulla griglia.</span><span class="sxs-lookup"><span data-stu-id="7a8af-115">Add the `AddPropertyInspector` method to the `MainWindow` class to place the **PropertyGrid** pane in the rightmost column on the grid.</span></span>  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3.  <span data-ttu-id="7a8af-116">Aggiungere una chiamata al metodo `AddPropertyInspector` nel costruttore della classe `MainWindow()` come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7a8af-116">Add a call to the `AddPropertyInspector` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
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
  
4.  <span data-ttu-id="7a8af-117">Premere F5 per compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="7a8af-117">Press F5 to build and run the solution.</span></span> <span data-ttu-id="7a8af-118">Il **della casella degli strumenti**, area di progettazione del flusso di lavoro, e **PropertyGrid** riquadri devono essere visualizzati e quando si trascina un <xref:System.Activities.Statements.Assign> attività o un <xref:System.Activities.Statements.Sequence> attività nell'area di disegno di progettazione, il griglia delle proprietà è necessario aggiornare a seconda dell'attività evidenziata.</span><span class="sxs-lookup"><span data-stu-id="7a8af-118">The **Toolbox**, workflow design canvas, and **PropertyGrid** panes should all be displayed, and when you drag an <xref:System.Activities.Statements.Assign> activity or a <xref:System.Activities.Statements.Sequence> activity onto the design canvas, the property grid should update depending on the highlighted activity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a8af-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="7a8af-119">Example</span></span>  
 <span data-ttu-id="7a8af-120">Il file MainWindow.xaml.cs ora deve contenere il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="7a8af-120">The MainWindow.xaml.cs file should now contain the following code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7a8af-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a8af-121">See Also</span></span>  
 [<span data-ttu-id="7a8af-122">Riallocazione di Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="7a8af-122">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="7a8af-123">Attività 1: Creare una nuova applicazione Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="7a8af-123">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
 [<span data-ttu-id="7a8af-124">Attività 2: Ospitare Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="7a8af-124">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
