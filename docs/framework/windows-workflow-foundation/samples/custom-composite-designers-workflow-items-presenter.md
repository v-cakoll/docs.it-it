---
title: Finestre di progettazione composite personalizzate - Relatore di elementi del flusso di lavoro
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
ms.openlocfilehash: f0a3616e6723d43ee4f2772c37e930c5facef31a
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/12/2018
ms.locfileid: "49122331"
---
# <a name="custom-composite-designers---workflow-items-presenter"></a><span data-ttu-id="687a0-102">Finestre di progettazione composite personalizzate - Relatore di elementi del flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="687a0-102">Custom Composite Designers - Workflow Items Presenter</span></span>
<span data-ttu-id="687a0-103"><xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> è un tipo chiave nel modello di programmazione della finestra di progettazione di WF che consente la modifica di una raccolta di elementi contenuti.</span><span class="sxs-lookup"><span data-stu-id="687a0-103">The <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> is a key type in the WF designer programming model that allows for the editing of a collection of contained elements.</span></span> <span data-ttu-id="687a0-104">In questo esempio viene illustrato come compilare un ActivityDesigner che espone una raccolta modificabile.</span><span class="sxs-lookup"><span data-stu-id="687a0-104">This sample shows how to build an activity designer that surfaces such an editable collection.</span></span>

 <span data-ttu-id="687a0-105">In questo esempio viene illustrato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="687a0-105">This sample demonstrates:</span></span>

-   <span data-ttu-id="687a0-106">Creazione di un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="687a0-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span>

-   <span data-ttu-id="687a0-107">Creazione di un ActivityDesigner con una visualizzazione "compressa" ed "espansa".</span><span class="sxs-lookup"><span data-stu-id="687a0-107">Creating an activity designer with a "collapsed" and "expanded" view.</span></span>

-   <span data-ttu-id="687a0-108">Esecuzione dell'override di una finestra di progettazione predefinita in un'applicazione riallocata.</span><span class="sxs-lookup"><span data-stu-id="687a0-108">Overriding a default designer in a rehosted application.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="687a0-109">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="687a0-109">To set up, build, and run the sample</span></span>

1.  <span data-ttu-id="687a0-110">Aprire il **Usingworkflowitemspresenter** soluzione di esempio per c# o Visual Basic in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="687a0-110">Open the **UsingWorkflowItemsPresenter.sln** sample solution for C# or for VB in Visual Studio 2010.</span></span>

2.  <span data-ttu-id="687a0-111">Compilare ed eseguire la soluzione.</span><span class="sxs-lookup"><span data-stu-id="687a0-111">Build and run the solution.</span></span> <span data-ttu-id="687a0-112">Dovrebbe essere visualizzata un'applicazione della finestra di progettazione flussi di lavoro riallocata in cui è possibile trascinare attività nell'area di disegno.</span><span class="sxs-lookup"><span data-stu-id="687a0-112">A rehosted workflow designer application should open, and you can drag activities onto the canvas.</span></span>

## <a name="sample-highlights"></a><span data-ttu-id="687a0-113">Evidenziazioni di esempio</span><span class="sxs-lookup"><span data-stu-id="687a0-113">Sample Highlights</span></span>
 <span data-ttu-id="687a0-114">Nel codice di questo esempio viene illustrato quanto segue:</span><span class="sxs-lookup"><span data-stu-id="687a0-114">The code for this sample shows the following:</span></span>

-   <span data-ttu-id="687a0-115">Compilazione di una finestra di progettazione dell'attività per: `Parallel`</span><span class="sxs-lookup"><span data-stu-id="687a0-115">The activity a designer is built for:  `Parallel`</span></span>

-   <span data-ttu-id="687a0-116">La creazione di un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="687a0-116">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span> <span data-ttu-id="687a0-117">Alcune considerazioni:</span><span class="sxs-lookup"><span data-stu-id="687a0-117">A few things to point out:</span></span>

    -   <span data-ttu-id="687a0-118">Notare l'uso dell'associazione dati WPF per eseguire l'associazione a `ModelItem.Branches`.</span><span class="sxs-lookup"><span data-stu-id="687a0-118">Note the use of WPF data binding to bind to `ModelItem.Branches`.</span></span> <span data-ttu-id="687a0-119">`ModelItem` è la proprietà su `WorkflowElementDesigner` che fa riferimento all'oggetto sottostante la finestra di progettazione per il quale è usata, in questo caso, `Parallel`.</span><span class="sxs-lookup"><span data-stu-id="687a0-119">`ModelItem` is the property on `WorkflowElementDesigner` that refers to the underlying object the designer is being used for, in this case, our `Parallel`.</span></span>

    -   <span data-ttu-id="687a0-120"><xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> può essere usato per inserire un elemento visivo per visualizzare i singoli elementi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="687a0-120">The <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> can be used to put a visual to display between the individual items in the collection.</span></span>

    -   <span data-ttu-id="687a0-121"><xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> è un modello che può essere fornito per determinare il layout degli elementi nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="687a0-121"><xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> is a template that can be provided to determine the layout of the items in the collection.</span></span> <span data-ttu-id="687a0-122">In questo caso, viene usato un pannello Stack orizzontale.</span><span class="sxs-lookup"><span data-stu-id="687a0-122">In this case, a horizontal stack panel is used.</span></span>

 <span data-ttu-id="687a0-123">Nel codice dell'esempio seguente viene illustrata questa operazione.</span><span class="sxs-lookup"><span data-stu-id="687a0-123">This following example code shows this.</span></span>

```xaml
<sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                              Items="{Binding Path=ModelItem.Branches}">
    <sad:WorkflowItemsPresenter.SpacerTemplate>
      <DataTemplate>
        <Ellipse Width="10" Height="10" Fill="Black"/>
      </DataTemplate>
    </sad:WorkflowItemsPresenter.SpacerTemplate>
    <sad:WorkflowItemsPresenter.ItemsPanel>
      <ItemsPanelTemplate>
        <StackPanel Orientation="Horizontal"/>
      </ItemsPanelTemplate>
    </sad:WorkflowItemsPresenter.ItemsPanel>
  </sad:WorkflowItemsPresenter>
```

-   <span data-ttu-id="687a0-124">Eseguire un'associazione di `DesignerAttribute` al tipo `Parallel`, quindi restituire gli attributi indicati.</span><span class="sxs-lookup"><span data-stu-id="687a0-124">Perform an association of the `DesignerAttribute` to the `Parallel` type and then output the attributes reported.</span></span>

    -   <span data-ttu-id="687a0-125">Registrare innanzitutto tutte le finestre di progettazione predefinite.</span><span class="sxs-lookup"><span data-stu-id="687a0-125">First, register all of the default designers.</span></span>

 <span data-ttu-id="687a0-126">Di seguito è riportato l'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="687a0-126">The following is the code example.</span></span>

```csharp
// register metadata
(new DesignerMetadata()).Register();
RegisterCustomMetadata();
```

```vb
' register metadata
Dim metadata = New DesignerMetadata()
metadata.Register()
' register custom metadata
RegisterCustomMetadata()
```

    -   <span data-ttu-id="687a0-127">Eseguire quindi l'override dell'elemento parallelo nel metodo `RegisterCustomMetadata`.</span><span class="sxs-lookup"><span data-stu-id="687a0-127">Then, override the parallel in `RegisterCustomMetadata` method.</span></span>

 <span data-ttu-id="687a0-128">Nel codice seguente viene illustrato questa operazione in C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="687a0-128">The following code shows this in C# and Visual Basic.</span></span>

```csharp
void RegisterCustomMetadata()
{
      AttributeTableBuilder builder = new AttributeTableBuilder();
      builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
      MetadataStore.AddAttributeTable(builder.CreateTable());
}
```

```vb
Sub RegisterCustomMetadata()
   Dim builder As New AttributeTableBuilder()
   builder.AddCustomAttributes(GetType(Parallel), New DesignerAttribute(GetType(CustomParallelDesigner)))
   MetadataStore.AddAttributeTable(builder.CreateTable())
End Sub
```

-   <span data-ttu-id="687a0-129">Osservare infine notare l'uso di diversi modelli di dati e trigger per selezionare il modello appropriato in base alla proprietà `IsRootDesigner`.</span><span class="sxs-lookup"><span data-stu-id="687a0-129">Finally, note the use of differing data templates and triggers to select the appropriate template based on the `IsRootDesigner` property.</span></span>

 <span data-ttu-id="687a0-130">Di seguito è riportato l'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="687a0-130">The following is the code example.</span></span>

```xaml
<sad:ActivityDesigner x:Class="Microsoft.Samples.CustomParallelDesigner"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:sad="clr-namespace:System.Activities.Design;assembly=System.Activities.Design"
    xmlns:sadv="clr-namespace:System.Activities.Design.View;assembly=System.Activities.Design">
  <sad:ActivityDesigner.Resources>
    <DataTemplate x:Key="Expanded">
      <StackPanel>
        <TextBlock>This is the Expanded View</TextBlock>
        <sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                                    Items="{Binding Path=ModelItem.Branches}">
          <sad:WorkflowItemsPresenter.SpacerTemplate>
            <DataTemplate>
              <Ellipse Width="10" Height="10" Fill="Black"/>
            </DataTemplate>
          </sad:WorkflowItemsPresenter.SpacerTemplate>
          <sad:WorkflowItemsPresenter.ItemsPanel>
            <ItemsPanelTemplate>
              <StackPanel Orientation="Horizontal"/>
            </ItemsPanelTemplate>
          </sad:WorkflowItemsPresenter.ItemsPanel>
        </sad:WorkflowItemsPresenter>
      </StackPanel>
    </DataTemplate>
    <DataTemplate x:Key="Collapsed">
      <TextBlock>This is the Collapsed View</TextBlock>
    </DataTemplate>
    <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
      <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
      <Style.Triggers>
        <DataTrigger Binding="{Binding Path=IsRootDesigner}" Value="true">
          <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
        </DataTrigger>
      </Style.Triggers>
    </Style>
  </sad: ActivityDesigner.Resources>
  <Grid>
    <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
  </Grid>
</sad: ActivityDesigner>
```

> [!IMPORTANT]
>  <span data-ttu-id="687a0-131">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="687a0-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="687a0-132">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="687a0-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="687a0-133">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="687a0-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="687a0-134">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="687a0-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="687a0-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="687a0-135">See Also</span></span>  
 <xref:System.Activities.Presentation.WorkflowItemsPresenter>  
 [<span data-ttu-id="687a0-136">Sviluppo di applicazioni con Progettazione flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="687a0-136">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
