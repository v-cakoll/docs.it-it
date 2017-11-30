---
title: Riallocazione della finestra di progettazione
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b676ad31-5f64-4d84-9a36-b4d7113a2f4d
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 005d6f98a7341954801c9b98e9eefdb1f0391d6c
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2017
---
# <a name="designer-rehosting"></a><span data-ttu-id="3ae33-102">Riallocazione della finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3ae33-102">Designer ReHosting</span></span>
<span data-ttu-id="3ae33-103">La riallocazione della finestra di progettazione è un scenario comune che si riferisce all'hosting dell'area di progettazione flussi di lavoro all'interno di un'applicazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="3ae33-103">Designer rehosting is a common scenario that refers to hosting the workflow design canvas inside of a custom application.</span></span> <span data-ttu-id="3ae33-104">La maggior parte degli utenti dell'applicazione host usa Visual Studio, tuttavia esistono scenari in cui potrebbe essere utile visualizzare la progettazione flussi di lavoro in un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="3ae33-104">The hosting application most people are familiar with is Visual Studio, however there are a number of scenarios where showing the workflow designer in an application may be useful:</span></span>  
  
-   <span data-ttu-id="3ae33-105">Monitoraggio delle applicazioni: per consentire a un utente finale di visualizzare il processo e i dati di runtime sul processo, ad esempio i dati relativi allo stato attivo attualmente, quelli relativi al tempo di esecuzione dell'aggregazione o altre informazioni su un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3ae33-105">Monitoring applications (allowing an end user to visualize the process, as well as runtime data about the process such as the currently active state, aggregate execution time data, or other information about an instance of the workflow).</span></span>  
  
-   <span data-ttu-id="3ae33-106">Applicazioni che consentono a un utente di personalizzare il processo con un set limitato di attività.</span><span class="sxs-lookup"><span data-stu-id="3ae33-106">Applications that allow a user to customize the process with a limited set of activities.</span></span>  
  
 <span data-ttu-id="3ae33-107">Per supportare questi tipi di applicazioni, la progettazione flussi di lavoro viene fornita all'interno di .NET Framework e può essere ospitata in un'applicazione WPF o in un'applicazione Windows Form con il codice host WPF appropriato.</span><span class="sxs-lookup"><span data-stu-id="3ae33-107">To support these types of applications, the workflow designer ships inside the .NET Framework, and can be hosted inside a WPF application, or in a WinForms application with the appropriate WPF hosting code.</span></span> <span data-ttu-id="3ae33-108">In questo esempio viene illustrato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3ae33-108">This sample demonstrates:</span></span>  
  
-   <span data-ttu-id="3ae33-109">Riallocazione della progettazione flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="3ae33-109">Rehosting the WF designer.</span></span>  
  
-   <span data-ttu-id="3ae33-110">Utilizzo della casella degli strumenti riallocata nonché della griglia delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="3ae33-110">Using the rehosted toolbox and property grid as well.</span></span>  
  
## <a name="rehosting-the-designer"></a><span data-ttu-id="3ae33-111">Riallocazione della progettazione</span><span class="sxs-lookup"><span data-stu-id="3ae33-111">Rehosting the designer</span></span>  
 <span data-ttu-id="3ae33-112">In questo esempio viene illustrato come creare il layout WPF per contenere la finestra di progettazione, visualizzata nel layout della griglia seguente (codice della Casella degli strumenti omesso per motivi di spazio).</span><span class="sxs-lookup"><span data-stu-id="3ae33-112">This sample shows how to create the WPF layout to contain the designer, seen in the following grid layout (Toolbox code omitted for space concerns).</span></span> <span data-ttu-id="3ae33-113">Si noti la denominazione dei bordi che contengono la finestra di progettazione e la griglia delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="3ae33-113">Note the naming of the borders which contain the designer and property grid.</span></span>  
  
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
  
 <span data-ttu-id="3ae33-114">Successivamente nell'esempio viene creata la finestra di progettazione e vengono associate le relative proprietà primarie <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> e <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> al contenitore appropriato nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="3ae33-114">Next the sample creates the designer, and associates its primary <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> with the appropriate container in the user interface.</span></span> <span data-ttu-id="3ae33-115">Esistono alcune righe aggiuntive di codice nell'esempio seguente per le quali è opportuno fornire alcune spiegazioni.</span><span class="sxs-lookup"><span data-stu-id="3ae33-115">There are a few additional lines of code in the following example that merit some explanation.</span></span> <span data-ttu-id="3ae33-116">La chiamata al metodo <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> è necessaria per associare l'ActivityDesigner predefinito per le attività fornite con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ae33-116">The <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> call is required to associate the default activity designers for the activities shipped with [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="3ae33-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> viene chiamato per passare l'elemento WF da modificare.</span><span class="sxs-lookup"><span data-stu-id="3ae33-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> is called to pass in the WF item to be edited.</span></span> <span data-ttu-id="3ae33-118">Infine, le proprietà <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (area di disegno primaria) e <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (griglia delle proprietà) vengono posizionate sull'area dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="3ae33-118">Finally, the <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (primary canvas) and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (property grid) are placed onto the user interface surface.</span></span>  
  
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
  
## <a name="using-the-rehosted-toolbox"></a><span data-ttu-id="3ae33-119">Utilizzo della casella degli strumenti riallocata</span><span class="sxs-lookup"><span data-stu-id="3ae33-119">Using the rehosted toolbox</span></span>  
 <span data-ttu-id="3ae33-120">In questo esempio viene usato in modo dichiarativo il controllo della casella degli strumenti riallocata in XAML.</span><span class="sxs-lookup"><span data-stu-id="3ae33-120">This sample uses the rehosted toolbox control declaratively in XAML.</span></span> <span data-ttu-id="3ae33-121">Si noti che nel codice, è possibile passare un tipo al costruttore <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper>.</span><span class="sxs-lookup"><span data-stu-id="3ae33-121">Note that in code, one can pass a type to the <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper> constructor.</span></span>  
  
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
  
#### <a name="using-the-sample"></a><span data-ttu-id="3ae33-122">Utilizzo dell'esempio</span><span class="sxs-lookup"><span data-stu-id="3ae33-122">Using the sample</span></span>  
  
1.  <span data-ttu-id="3ae33-123">Aprire la soluzione DesignerRehosting.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ae33-123">Open the DesignerRehosting.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="3ae33-124">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ae33-124">Press F5 to compile and run the application.</span></span>  
  
3.  <span data-ttu-id="3ae33-125">Un'applicazione WPF viene avviata con una finestra di progettazione riallocata.</span><span class="sxs-lookup"><span data-stu-id="3ae33-125">A WPF application starts with a rehosted designer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3ae33-126">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="3ae33-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3ae33-127">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="3ae33-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3ae33-128">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3ae33-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3ae33-129">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="3ae33-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\DesignerRehosting\Basic`