---
title: Finestre di progettazione composite personalizzate - Relatore di elementi del flusso di lavoro
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
ms.openlocfilehash: 081dce85946fab85cff474508c46770c762b9e76
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338718"
---
# <a name="custom-composite-designers---workflow-items-presenter"></a>Finestre di progettazione composite personalizzate - Relatore di elementi del flusso di lavoro

<xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> è un tipo chiave nel modello di programmazione della finestra di progettazione di WF che consente la modifica di una raccolta di elementi contenuti. In questo esempio viene illustrato come compilare un ActivityDesigner che espone una raccolta modificabile.

In questo esempio viene illustrato quanto segue:

- Creazione di un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.

- Creazione di un ActivityDesigner con una visualizzazione "compresso" ed "espanso".

- Esecuzione dell'override di una finestra di progettazione predefinita in un'applicazione riallocata.

## <a name="set-up-build-and-run-the-sample"></a>Configurare, compilare ed eseguire l'esempio

1. Aprire la soluzione di esempio **UsingWorkflowItemsPresenter. sln** per C# o per Visual Basic in Visual Studio 2010.

2. Compilare ed eseguire la soluzione.

   Si apre un'applicazione di progettazione flussi di lavoro riallocata ed è possibile trascinare le attività nell'area di disegno.

## <a name="sample-highlights"></a>Evidenziazioni di esempio

Nel codice di questo esempio viene illustrato quanto segue:

- Compilazione di una finestra di progettazione dell'attività per: `Parallel`

- La creazione di un ActivityDesigner personalizzato con un oggetto <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>. Alcune considerazioni:

  - Notare l'uso dell'associazione dati WPF per eseguire l'associazione a `ModelItem.Branches`. `ModelItem` è la proprietà su `WorkflowElementDesigner` che fa riferimento all'oggetto sottostante la finestra di progettazione per il quale è usata, in questo caso, `Parallel`.

  - <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> può essere usato per inserire un elemento visivo per visualizzare i singoli elementi nella raccolta.

  - <xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> è un modello che può essere fornito per determinare il layout degli elementi nella raccolta. In questo caso, viene usato un pannello Stack orizzontale.

  Nel codice dell'esempio seguente viene illustrata questa operazione.

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

- Eseguire un'associazione di `DesignerAttribute` al tipo `Parallel`, quindi restituire gli attributi indicati.

  - Registrare innanzitutto tutte le finestre di progettazione predefinite.

    Di seguito è riportato l'esempio di codice.

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

  - Eseguire quindi l'override dell'elemento parallelo nel metodo `RegisterCustomMetadata`.

    Nel codice seguente viene illustrato questa operazione in C# e Visual Basic.

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

- Osservare infine notare l'uso di diversi modelli di dati e trigger per selezionare il modello appropriato in base alla proprietà `IsRootDesigner`.

  Di seguito è riportato l'esempio di codice.

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
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`

## <a name="see-also"></a>Vedere anche

- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- [Sviluppo di applicazioni con Progettazione flussi di lavoro](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
