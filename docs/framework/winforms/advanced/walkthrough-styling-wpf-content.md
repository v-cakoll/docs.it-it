---
title: 'Procedura dettagliata: applicazione di stili al contenuto WPF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae150e93958b622a772258ab41fa4281014dd567
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-styling-wpf-content"></a><span data-ttu-id="1ddce-102">Procedura dettagliata: applicazione di stili al contenuto WPF</span><span class="sxs-lookup"><span data-stu-id="1ddce-102">Walkthrough: Styling WPF Content</span></span>
<span data-ttu-id="1ddce-103">Questa procedura dettagliata mostra come applicare uno stile a un controllo Windows Presentation Foundation (WPF) incluso in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1ddce-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>  
  
 <span data-ttu-id="1ddce-104">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ddce-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="1ddce-105">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="1ddce-105">Create the project.</span></span>  
  
-   <span data-ttu-id="1ddce-106">Creare il tipo di controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="1ddce-106">Create the WPF control type.</span></span>  
  
-   <span data-ttu-id="1ddce-107">Applicare uno stile al controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="1ddce-107">Apply a style to the WPF control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ddce-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="1ddce-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1ddce-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="1ddce-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1ddce-110">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="1ddce-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1ddce-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1ddce-111">Prerequisites</span></span>  
 <span data-ttu-id="1ddce-112">Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ddce-112">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="1ddce-113">.</span><span class="sxs-lookup"><span data-stu-id="1ddce-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="1ddce-114">Creazione del progetto</span><span class="sxs-lookup"><span data-stu-id="1ddce-114">Creating the Project</span></span>  
 <span data-ttu-id="1ddce-115">Il primo passaggio consiste nella creazione del progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1ddce-115">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1ddce-116">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1ddce-116">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="1ddce-117">Per creare il progetto</span><span class="sxs-lookup"><span data-stu-id="1ddce-117">To create the project</span></span>  
  
-   <span data-ttu-id="1ddce-118">Creare un nuovo progetto applicazione Windows Forms in Visual Basic o Visual c# denominato `StylingWpfContent`.</span><span class="sxs-lookup"><span data-stu-id="1ddce-118">Create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>  
  
## <a name="creating-the-wpf-control-types"></a><span data-ttu-id="1ddce-119">Creazione di tipi di controllo WPF</span><span class="sxs-lookup"><span data-stu-id="1ddce-119">Creating the WPF Control Types</span></span>  
 <span data-ttu-id="1ddce-120">Dopo avere aggiunto un tipo di controllo WPF al progetto, è possibile inserirlo in un controllo <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="1ddce-120">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
#### <a name="to-create-wpf-control-types"></a><span data-ttu-id="1ddce-121">Per creare i tipi di controllo WPF</span><span class="sxs-lookup"><span data-stu-id="1ddce-121">To create WPF control types</span></span>  
  
1.  <span data-ttu-id="1ddce-122">Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="1ddce-122">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="1ddce-123">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="1ddce-123">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="1ddce-124">Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="1ddce-124">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="1ddce-125">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="1ddce-125">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="1ddce-126">Per ulteriori informazioni, vedere [procedura: selezionare e spostare elementi nella finestra di progettazione](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span><span class="sxs-lookup"><span data-stu-id="1ddce-126">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="1ddce-127">Nel **proprietà** finestra, impostare il valore della <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> proprietà `200`.</span><span class="sxs-lookup"><span data-stu-id="1ddce-127">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="1ddce-128">Aggiungere un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> controllo il <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="1ddce-128">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>  
  
5.  <span data-ttu-id="1ddce-129">Aggiungere un secondo <xref:System.Windows.Controls.Button?displayProperty=nameWithType> controllo il <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà **OK**.</span><span class="sxs-lookup"><span data-stu-id="1ddce-129">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>  
  
6.  <span data-ttu-id="1ddce-130">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="1ddce-130">Build the project.</span></span>  
  
## <a name="applying-a-style-to-a-wpf-control"></a><span data-ttu-id="1ddce-131">Applicazione di uno stile a un controllo WPF</span><span class="sxs-lookup"><span data-stu-id="1ddce-131">Applying a Style to a WPF Control</span></span>  
 <span data-ttu-id="1ddce-132">È possibile applicare uno stile diverso a un controllo WPF per modificarne l'aspetto e il comportamento.</span><span class="sxs-lookup"><span data-stu-id="1ddce-132">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>  
  
#### <a name="to-apply-a-style-to-a-wpf-control"></a><span data-ttu-id="1ddce-133">Per applicare uno stile a un controllo WPF</span><span class="sxs-lookup"><span data-stu-id="1ddce-133">To apply a style to a WPF control</span></span>  
  
1.  <span data-ttu-id="1ddce-134">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1ddce-134">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="1ddce-135">Nel **della casella degli strumenti**, fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nel form.</span><span class="sxs-lookup"><span data-stu-id="1ddce-135">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="1ddce-136">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="1ddce-136">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="1ddce-137">Nel pannello smart tag per `elementHost1`, fare clic su **modifica contenuto ospitato** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="1ddce-137">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>  
  
     <span data-ttu-id="1ddce-138">`UserControl1` si apre in [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ddce-138">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="1ddce-139">Nella visualizzazione XAML inserire il seguente codice XAML dopo il tag di apertura `<UserControl>`.</span><span class="sxs-lookup"><span data-stu-id="1ddce-139">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>  
  
     <span data-ttu-id="1ddce-140">Questo codice XAML crea una sfumatura con un bordo sfumato a contrasto.</span><span class="sxs-lookup"><span data-stu-id="1ddce-140">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="1ddce-141">Quando si fa clic sul controllo, le sfumature vengono modificate per generare l'aspetto di un pulsante premuto.</span><span class="sxs-lookup"><span data-stu-id="1ddce-141">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="1ddce-142">Per altre informazioni, vedere [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="1ddce-142">For more information, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
```xaml  
<UserControl.Resources>  
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#FFF" Offset="0.0"/>  
        <GradientStop Color="#CCC" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#BBB" Offset="0.0"/>  
        <GradientStop Color="#EEE" Offset="0.1"/>  
        <GradientStop Color="#EEE" Offset="0.9"/>  
        <GradientStop Color="#FFF" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#CCC" Offset="0.0"/>  
        <GradientStop Color="#444" Offset="1.0"/>  
    </LinearGradientBrush>  
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">  
        <GradientStop Color="#444" Offset="0.0"/>  
        <GradientStop Color="#888" Offset="1.0"/>  
    </LinearGradientBrush>  
  
    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">  
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>  
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>  
        <Setter Property="Template">  
            <Setter.Value>  
                <ControlTemplate TargetType="{x:Type Button}">  
                    <Grid x:Name="Grid">  
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>  
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>  
                    </Grid>  
                    <ControlTemplate.Triggers>  
                        <Trigger Property="IsPressed" Value="true">  
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>  
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>  
                        </Trigger>  
                    </ControlTemplate.Triggers>  
                </ControlTemplate>  
            </Setter.Value>  
        </Setter>  
    </Style>  
</UserControl.Resources>  
```  
  
1.  <span data-ttu-id="1ddce-143">Applicare al pulsante Cancel lo stile `SimpleButton` definito nel passaggio precedente inserendo il seguente codice XAML nel tag `<Button>` del pulsante Cancel.</span><span class="sxs-lookup"><span data-stu-id="1ddce-143">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>  
  
    ```  
    Style="{StaticResource SimpleButton}  
    ```  
  
     <span data-ttu-id="1ddce-144">La dichiarazione del pulsante sarà simile al seguente codice XAML.</span><span class="sxs-lookup"><span data-stu-id="1ddce-144">Your button declaration will resemble the following XAML.</span></span>  
  
```xaml  
<Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"  
                Style="{StaticResource SimpleButton}">Cancel</Button>  
```  
  
1.  <span data-ttu-id="1ddce-145">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="1ddce-145">Build the project.</span></span>  
  
2.  <span data-ttu-id="1ddce-146">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="1ddce-146">Open `Form1` in the Windows Forms Designer.</span></span>  
  
3.  <span data-ttu-id="1ddce-147">Il nuovo stile viene applicato al pulsante.</span><span class="sxs-lookup"><span data-stu-id="1ddce-147">The new style is applied to the button control.</span></span>  
  
4.  <span data-ttu-id="1ddce-148">Dal **Debug** dal menu **Avvia debug** per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1ddce-148">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>  
  
5.  <span data-ttu-id="1ddce-149">Fare clic sui pulsanti OK e Cancel e visualizzare le differenze.</span><span class="sxs-lookup"><span data-stu-id="1ddce-149">Click the OK and Cancel buttons and view the differences.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ddce-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ddce-150">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="1ddce-151">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="1ddce-151">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="1ddce-152">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="1ddce-152">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="1ddce-153">WPF Designer</span><span class="sxs-lookup"><span data-stu-id="1ddce-153">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="1ddce-154">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="1ddce-154">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="1ddce-155">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="1ddce-155">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
