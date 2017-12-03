---
title: Finestre di progettazione composte personalizzate - relatore dell'elemento del flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bba89e9da78fd96d0cd7d61e825e4792729bae5b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="64746-102">Finestre di progettazione composte personalizzate - relatore dell'elemento del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="64746-102">Custom Composite Designers - Workflow Item Presenter</span></span>
<span data-ttu-id="64746-103">Il <xref:System.Activities.Presentation.WorkflowItemPresenter> è un tipo chiave nel modello di programmazione della finestra di progettazione di WF che consente la creazione di un' "area di rilascio" in cui è possibile posizionare un'attività arbitraria.</span><span class="sxs-lookup"><span data-stu-id="64746-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="64746-104">In questo esempio viene illustrato come compilare un ActivityDesigner che espone tale "area di rilascio."</span><span class="sxs-lookup"><span data-stu-id="64746-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>  
  
 <span data-ttu-id="64746-105">In questo esempio viene illustrato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="64746-105">This sample demonstrates:</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="64746-106">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="64746-106">Demonstrates</span></span>  
  
-   <span data-ttu-id="64746-107">Creazione di un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="64746-107">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>  
  
-   <span data-ttu-id="64746-108">Registrazione della finestra di progettazione personalizzata usando l'archivio di metadati.</span><span class="sxs-lookup"><span data-stu-id="64746-108">Registering the custom designer using the metadata store.</span></span>  
  
-   <span data-ttu-id="64746-109">Programmazione della casella degli strumenti riallocata in modo dichiarativo e imperativo.</span><span class="sxs-lookup"><span data-stu-id="64746-109">Programming the rehosted toolbox declaratively and imperatively.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="64746-110">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="64746-110">Sample Details</span></span>  
 <span data-ttu-id="64746-111">Il codice per questo esempio illustra:</span><span class="sxs-lookup"><span data-stu-id="64746-111">The code for this sample shows:</span></span>  
  
-   <span data-ttu-id="64746-112">L'ActivityDesigner personalizzato compilato per la classe `SimpleNativeActivity`.</span><span class="sxs-lookup"><span data-stu-id="64746-112">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>  
  
-   <span data-ttu-id="64746-113">La creazione di un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="64746-113">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>  
  
```xaml  
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"  
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
  
 <span data-ttu-id="64746-114">Notare l'uso dell'associazione dati WPF per eseguire l'associazione a `ModelItem.Body`.</span><span class="sxs-lookup"><span data-stu-id="64746-114">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="64746-115">`ModelItem`è la proprietà su <xref:System.Activities.Presentation.ActivityDesigner> che fa riferimento all'oggetto sottostante la finestra di progettazione viene utilizzato, in questo caso, **SimpleNativeActivity**.</span><span class="sxs-lookup"><span data-stu-id="64746-115">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>  
  
#### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="64746-116">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="64746-116">To setup, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="64746-117">Aprire la soluzione in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64746-117">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="64746-118">Premere F5 per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="64746-118">Press F5 to compile and run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="64746-119">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="64746-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="64746-120">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="64746-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="64746-121">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="64746-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="64746-122">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="64746-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="64746-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64746-123">See Also</span></span>  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 [<span data-ttu-id="64746-124">Sviluppo di applicazioni con Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="64746-124">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
