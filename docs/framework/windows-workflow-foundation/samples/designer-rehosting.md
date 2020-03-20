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
# <a name="designer-rehosting"></a>Riallocazione della finestra di progettazione
La riallocazione della finestra di progettazione è un scenario comune che si riferisce all'hosting dell'area di progettazione flussi di lavoro all'interno di un'applicazione personalizzata. La maggior parte degli utenti dell'applicazione host usa Visual Studio, tuttavia esistono scenari in cui potrebbe essere utile visualizzare la progettazione flussi di lavoro in un'applicazione:  
  
- Monitoraggio delle applicazioni: per consentire a un utente finale di visualizzare il processo e i dati di runtime sul processo, ad esempio i dati relativi allo stato attivo attualmente, quelli relativi al tempo di esecuzione dell'aggregazione o altre informazioni su un'istanza del flusso di lavoro.  
  
- Applicazioni che consentono a un utente di personalizzare il processo con un set limitato di attività.  
  
 Per supportare questi tipi di applicazioni, la progettazione flussi di lavoro viene fornita all'interno di .NET Framework e può essere ospitata in un'applicazione WPF o in un'applicazione Windows Form con il codice host WPF appropriato. Questo esempio dimostra:  
  
- Riallocazione della progettazione flussi di lavoro.  
  
- Utilizzo della casella degli strumenti riallocata nonché della griglia delle proprietà.  
  
## <a name="rehosting-the-designer"></a>Riallocazione della progettazione  
 In questo esempio viene illustrato come creare il layout WPF per contenere la finestra di progettazione, visualizzata nel layout della griglia seguente (codice della Casella degli strumenti omesso per motivi di spazio). Si noti la denominazione dei bordi che contengono la finestra di progettazione e la griglia delle proprietà.  
  
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
  
 Successivamente nell'esempio viene creata la finestra di progettazione e vengono associate le relative proprietà primarie <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> e <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> al contenitore appropriato nell'interfaccia utente. Esistono alcune righe aggiuntive di codice nell'esempio seguente per le quali è opportuno fornire alcune spiegazioni. La <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> chiamata è necessaria per associare gli ActivityDesigner predefiniti per le attività fornite con .NET Framework. <xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> viene chiamato per passare l'elemento WF da modificare. Infine, le proprietà <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (area di disegno primaria) e <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (griglia delle proprietà) vengono posizionate sull'area dell'interfaccia utente.  
  
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
  
## <a name="using-the-rehosted-toolbox"></a>Utilizzo della casella degli strumenti riallocata  
 In questo esempio viene usato in modo dichiarativo il controllo della casella degli strumenti riallocata in XAML. Si noti che nel codice, è possibile passare un tipo al costruttore <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper>.  
  
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
  
#### <a name="using-the-sample"></a>Utilizzo dell'esempio  
  
1. Aprire la soluzione DesignerRehosting.sln in Visual Studio 2010.  
  
2. Premere F5 per compilare ed eseguire l'applicazione.  
  
3. Un'applicazione WPF viene avviata con una finestra di progettazione riallocata.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\DesignerRehosting\Basic`
