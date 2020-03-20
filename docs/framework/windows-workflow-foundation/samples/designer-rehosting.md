---
title: Riallocazione della finestra di progettazione
ms.date: 03/30/2017
ms.assetid: b676ad31-5f64-4d84-9a36-b4d7113a2f4d
ms.openlocfilehash: b72e3450799db40988c8b99e4db3707de330d8ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182815"
---
# <a name="designer-rehosting"></a><span data-ttu-id="0eb99-102">Riallocazione della finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="0eb99-102">Designer Rehosting</span></span>
<span data-ttu-id="0eb99-103">La riallocazione della finestra di progettazione è un scenario comune che si riferisce all'hosting dell'area di progettazione flussi di lavoro all'interno di un'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="0eb99-103">Designer rehosting is a common scenario that refers to hosting the workflow design canvas inside of a custom application.</span></span> <span data-ttu-id="0eb99-104">La maggior parte degli utenti dell'applicazione host usa Visual Studio, tuttavia esistono scenari in cui potrebbe essere utile visualizzare la progettazione flussi di lavoro in un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="0eb99-104">The hosting application most people are familiar with is Visual Studio, however there are a number of scenarios where showing the workflow designer in an application may be useful:</span></span>  
  
- <span data-ttu-id="0eb99-105">Monitoraggio delle applicazioni: per consentire a un utente finale di visualizzare il processo e i dati di runtime sul processo, ad esempio i dati relativi allo stato attivo attualmente, quelli relativi al tempo di esecuzione dell'aggregazione o altre informazioni su un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0eb99-105">Monitoring applications (allowing an end user to visualize the process, as well as runtime data about the process such as the currently active state, aggregate execution time data, or other information about an instance of the workflow).</span></span>  
  
- <span data-ttu-id="0eb99-106">Applicazioni che consentono a un utente di personalizzare il processo con un set limitato di attività.</span><span class="sxs-lookup"><span data-stu-id="0eb99-106">Applications that allow a user to customize the process with a limited set of activities.</span></span>  
  
 <span data-ttu-id="0eb99-107">Per supportare questi tipi di applicazioni, la progettazione flussi di lavoro viene fornita all'interno di .NET Framework e può essere ospitata in un'applicazione WPF o in un'applicazione Windows Form con il codice host WPF appropriato.</span><span class="sxs-lookup"><span data-stu-id="0eb99-107">To support these types of applications, the workflow designer ships inside the .NET Framework, and can be hosted inside a WPF application, or in a WinForms application with the appropriate WPF hosting code.</span></span> <span data-ttu-id="0eb99-108">Questo esempio dimostra:</span><span class="sxs-lookup"><span data-stu-id="0eb99-108">This sample demonstrates:</span></span>  
  
- <span data-ttu-id="0eb99-109">Riallocazione della progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="0eb99-109">Rehosting the WF designer.</span></span>  
  
- <span data-ttu-id="0eb99-110">Utilizzo della casella degli strumenti riallocata nonché della griglia delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="0eb99-110">Using the rehosted toolbox and property grid as well.</span></span>  
  
## <a name="rehosting-the-designer"></a><span data-ttu-id="0eb99-111">Riallocazione della progettazione</span><span class="sxs-lookup"><span data-stu-id="0eb99-111">Rehosting the designer</span></span>  
 <span data-ttu-id="0eb99-112">In questo esempio viene illustrato come creare il layout WPF per contenere la finestra di progettazione, visualizzata nel layout della griglia seguente (codice della Casella degli strumenti omesso per motivi di spazio).</span><span class="sxs-lookup"><span data-stu-id="0eb99-112">This sample shows how to create the WPF layout to contain the designer, seen in the following grid layout (Toolbox code omitted for space concerns).</span></span> <span data-ttu-id="0eb99-113">Si noti la denominazione dei bordi che contengono la finestra di progettazione e la griglia delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="0eb99-113">Note the naming of the borders which contain the designer and property grid.</span></span>  
  
```xaml  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition Width="2*"/>  
        <ColumnDefinition Width="7*"/>  
        <ColumnDefinition Width="3*"/>  
    </Grid.ColumnDefinitions>  
    <Border Grid.Column="0">  
        <sapt:ToolboxControl>...</sapt:ToolboxControl>  
    </Border>  
    <Border Grid.Column="1" Name="DesignerBorder"/>  
    <Border Grid.Column="2" Name="PropertyBorder"/>  
</Grid>  
```  
  
 <span data-ttu-id="0eb99-114">Successivamente nell'esempio viene creata la finestra di progettazione e vengono associate le relative proprietà primarie <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> e <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> al contenitore appropriato nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0eb99-114">Next the sample creates the designer, and associates its primary <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> with the appropriate container in the user interface.</span></span> <span data-ttu-id="0eb99-115">Esistono alcune righe aggiuntive di codice nell'esempio seguente per le quali è opportuno fornire alcune spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="0eb99-115">There are a few additional lines of code in the following example that merit some explanation.</span></span> <span data-ttu-id="0eb99-116">La <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> chiamata è necessaria per associare gli ActivityDesigner predefiniti per le attività fornite con .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0eb99-116">The <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> call is required to associate the default activity designers for the activities shipped with .NET Framework.</span></span> <span data-ttu-id="0eb99-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> viene chiamato per passare l'elemento WF da modificare.</span><span class="sxs-lookup"><span data-stu-id="0eb99-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> is called to pass in the WF item to be edited.</span></span> <span data-ttu-id="0eb99-118">Infine, le proprietà <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (area di disegno primaria) e <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (griglia delle proprietà) vengono posizionate sull'area dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0eb99-118">Finally, the <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (primary canvas) and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (property grid) are placed onto the user interface surface.</span></span>  
  
```csharp  
protected override void OnInitialized(EventArgs e)  
{  
   base.OnInitialized(e);  
   // register metadata  
   (new DesignerMetadata()).Register();  
  
   // create the workflow designer  
   WorkflowDesigner wd = new WorkflowDesigner();  
   wd.Load(new Sequence());  
   DesignerBorder.Child = wd.View;  
   PropertyBorder.Child = wd.PropertyInspectorView;  
}  
```  
  
## <a name="using-the-rehosted-toolbox"></a><span data-ttu-id="0eb99-119">Utilizzo della casella degli strumenti riallocata</span><span class="sxs-lookup"><span data-stu-id="0eb99-119">Using the rehosted toolbox</span></span>  
 <span data-ttu-id="0eb99-120">In questo esempio viene usato in modo dichiarativo il controllo della casella degli strumenti riallocata in XAML.</span><span class="sxs-lookup"><span data-stu-id="0eb99-120">This sample uses the rehosted toolbox control declaratively in XAML.</span></span> <span data-ttu-id="0eb99-121">Si noti che nel codice, è possibile passare un tipo al costruttore <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper>.</span><span class="sxs-lookup"><span data-stu-id="0eb99-121">Note that in code, one can pass a type to the <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper> constructor.</span></span>  
  
```xaml  
<!-- Copyright (c) Microsoft Corporation. All rights reserved-->  
<Window x:Class="Microsoft.Samples.DesignerRehosting.RehostingWfDesigner"  
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
            <sapt:ToolboxControl>  
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
  
#### <a name="using-the-sample"></a><span data-ttu-id="0eb99-122">Utilizzo dell'esempio</span><span class="sxs-lookup"><span data-stu-id="0eb99-122">Using the sample</span></span>  
  
1. <span data-ttu-id="0eb99-123">Aprire la soluzione DesignerRehosting.sln in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="0eb99-123">Open the DesignerRehosting.sln solution in Visual Studio 2010.</span></span>  
  
2. <span data-ttu-id="0eb99-124">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0eb99-124">Press F5 to compile and run the application.</span></span>  
  
3. <span data-ttu-id="0eb99-125">Un'applicazione WPF viene avviata con una finestra di progettazione riallocata.</span><span class="sxs-lookup"><span data-stu-id="0eb99-125">A WPF application starts with a rehosted designer.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0eb99-126">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="0eb99-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0eb99-127">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="0eb99-127">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="0eb99-128">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="0eb99-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0eb99-129">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="0eb99-129">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\DesignerRehosting\Basic`
