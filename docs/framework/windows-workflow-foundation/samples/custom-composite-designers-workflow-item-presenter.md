---
title: Finestre di progettazione composte personalizzate - relatore dell'elemento del flusso di lavoro
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: d1047b8be35545e83eaa8788b53751b6b0056984
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338050"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="2e7b0-102">Finestre di progettazione composte personalizzate - relatore dell'elemento del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="2e7b0-102">Custom Composite Designers - Workflow Item Presenter</span></span>

<span data-ttu-id="2e7b0-103">Il <xref:System.Activities.Presentation.WorkflowItemPresenter> è un tipo di chiave nel modello di programmazione di progettazione WF che consente la creazione di un'"area di rilascio" in cui è possibile posizionare un'attività arbitraria.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="2e7b0-104">In questo esempio viene illustrato come compilare un ActivityDesigner che emerge come "area di rilascio".</span><span class="sxs-lookup"><span data-stu-id="2e7b0-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>

<span data-ttu-id="2e7b0-105">In questo esempio viene illustrato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2e7b0-105">This sample demonstrates:</span></span>

- <span data-ttu-id="2e7b0-106">Creazione di un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

- <span data-ttu-id="2e7b0-107">Registrazione della finestra di progettazione personalizzata usando l'archivio di metadati.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-107">Registering the custom designer using the metadata store.</span></span>

- <span data-ttu-id="2e7b0-108">Programmazione della casella degli strumenti riallocata in modo dichiarativo e imperativo.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-108">Programming the rehosted toolbox declaratively and imperatively.</span></span>

## <a name="sample-details"></a><span data-ttu-id="2e7b0-109">Dettagli dell'esempio</span><span class="sxs-lookup"><span data-stu-id="2e7b0-109">Sample Details</span></span>

<span data-ttu-id="2e7b0-110">Il codice per questo esempio illustra:</span><span class="sxs-lookup"><span data-stu-id="2e7b0-110">The code for this sample shows:</span></span>

- <span data-ttu-id="2e7b0-111">L'ActivityDesigner personalizzato compilato per la classe `SimpleNativeActivity`.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-111">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>

- <span data-ttu-id="2e7b0-112">La creazione di un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-112">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

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

 <span data-ttu-id="2e7b0-113">Notare l'uso dell'associazione dati WPF per eseguire l'associazione a `ModelItem.Body`.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-113">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="2e7b0-114">`ModelItem` è la proprietà di <xref:System.Activities.Presentation.ActivityDesigner> che fa riferimento all'oggetto sottostante per il quale viene utilizzata la finestra di progettazione, in questo caso **SimpleNativeActivity**.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-114">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="2e7b0-115">Configurare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="2e7b0-115">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="2e7b0-116">Aprire la soluzione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-116">Open the solution in Visual Studio.</span></span>

2. <span data-ttu-id="2e7b0-117">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-117">Press **F5** to compile and run the application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e7b0-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2e7b0-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-119">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="2e7b0-120">Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2e7b0-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="2e7b0-121">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`

## <a name="see-also"></a><span data-ttu-id="2e7b0-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e7b0-122">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [<span data-ttu-id="2e7b0-123">Sviluppo di applicazioni con Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="2e7b0-123">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
