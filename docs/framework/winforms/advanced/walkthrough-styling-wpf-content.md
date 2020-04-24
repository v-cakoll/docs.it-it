---
title: 'Procedura dettagliata: Stile del contenuto WPFWalkthrough: Style WPF Content'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07241d41e3fbf270a76bd241765bfa369ee265d5
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646323"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="215ca-102">Procedura dettagliata: Stile del contenuto WPFWalkthrough: Style WPF Content</span><span class="sxs-lookup"><span data-stu-id="215ca-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="215ca-103">In questo articolo viene illustrato come applicare lo stile a un controllo Windows Presentation Foundation (WPF) ospitato in un Windows Form.This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span><span class="sxs-lookup"><span data-stu-id="215ca-103">This article show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="215ca-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="215ca-104">Prerequisites</span></span>

<span data-ttu-id="215ca-105">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="215ca-105">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="215ca-106">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="215ca-106">Create the project</span></span>

<span data-ttu-id="215ca-107">Aprire Visual Studio e creare un nuovo progetto di applicazione `StylingWpfContent`Windows Form denominato Visual Basic o Visual C.</span><span class="sxs-lookup"><span data-stu-id="215ca-107">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="215ca-108">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="215ca-108">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="215ca-109">Creare i tipi di controllo WPFCreate the WPFwpf types</span><span class="sxs-lookup"><span data-stu-id="215ca-109">Create the WPF control types</span></span>

<span data-ttu-id="215ca-110">Dopo avere aggiunto un tipo di controllo WPF al progetto, è possibile inserirlo in un controllo <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="215ca-110">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="215ca-111">Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="215ca-111">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="215ca-112">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="215ca-112">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="215ca-113">Per altre informazioni, vedere [Procedura dettagliata: creazione di nuovo contenuto WPF in Windows Form in fase di progettazione.](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)</span><span class="sxs-lookup"><span data-stu-id="215ca-113">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="215ca-114">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="215ca-114">In Design view, make sure that `UserControl1` is selected.</span></span>

3. <span data-ttu-id="215ca-115">Nella finestra **Proprietà** impostare il <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> valore delle proprietà e su **200**.</span><span class="sxs-lookup"><span data-stu-id="215ca-115">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to **200**.</span></span>

4. <span data-ttu-id="215ca-116">Aggiungere <xref:System.Windows.Controls.Button?displayProperty=nameWithType> un controllo <xref:System.Windows.Controls.UserControl> a e impostare il valore della <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà su **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="215ca-116">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="215ca-117">Aggiungere un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> secondo <xref:System.Windows.Controls.UserControl> controllo a e <xref:System.Windows.Controls.ContentControl.Content%2A> impostare il valore della proprietà **su OK**.</span><span class="sxs-lookup"><span data-stu-id="215ca-117">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="215ca-118">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="215ca-118">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="215ca-119">Applicare uno stile a un controllo WPFApply a Style to a WPF Control</span><span class="sxs-lookup"><span data-stu-id="215ca-119">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="215ca-120">È possibile applicare uno stile diverso a un controllo WPF per modificarne l'aspetto e il comportamento.</span><span class="sxs-lookup"><span data-stu-id="215ca-120">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="215ca-121">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="215ca-121">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="215ca-122">Nella **Casella degli**strumenti `UserControl1` fare doppio `UserControl1` clic per creare un'istanza di nel form.</span><span class="sxs-lookup"><span data-stu-id="215ca-122">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

   <span data-ttu-id="215ca-123">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="215ca-123">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="215ca-124">Nel pannello smart `elementHost1`tag per , fare clic su **Modifica contenuto ospitato** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="215ca-124">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

   <span data-ttu-id="215ca-125">`UserControl1`viene aperto in Progettazione WPF.</span><span class="sxs-lookup"><span data-stu-id="215ca-125">`UserControl1` opens in the WPF Designer.</span></span>

1. <span data-ttu-id="215ca-126">Nella visualizzazione XAML inserire il seguente codice XAML dopo il tag di apertura `<UserControl>`.</span><span class="sxs-lookup"><span data-stu-id="215ca-126">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span> <span data-ttu-id="215ca-127">Questo codice XAML crea una sfumatura con un bordo sfumato a contrasto.</span><span class="sxs-lookup"><span data-stu-id="215ca-127">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="215ca-128">Quando si fa clic sul controllo, le sfumature vengono modificate per generare l'aspetto di un pulsante premuto.</span><span class="sxs-lookup"><span data-stu-id="215ca-128">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="215ca-129">Per altre informazioni, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="215ca-129">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

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

1. <span data-ttu-id="215ca-130">Applicare `SimpleButton` lo stile definito nel passaggio precedente al pulsante `<Button>` Annulla inserendo il codice XAML seguente nel tag del pulsante **Annulla.**</span><span class="sxs-lookup"><span data-stu-id="215ca-130">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the **Cancel** button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="215ca-131">La dichiarazione del pulsante sarà simile al codice XAML seguente:Your button declaration will resemble the following XAML:</span><span class="sxs-lookup"><span data-stu-id="215ca-131">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="215ca-132">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="215ca-132">Build the project.</span></span>

1. <span data-ttu-id="215ca-133">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="215ca-133">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="215ca-134">Il nuovo stile viene applicato al pulsante.</span><span class="sxs-lookup"><span data-stu-id="215ca-134">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="215ca-135">Scegliere **Avvia** debug **dal** menu Debug per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="215ca-135">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="215ca-136">Fare clic sui pulsanti **OK** e **Annulla** e visualizzare le differenze.</span><span class="sxs-lookup"><span data-stu-id="215ca-136">Click the **OK** and **Cancel** buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="215ca-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="215ca-137">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="215ca-138">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="215ca-138">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="215ca-139">Utilizzo di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="215ca-139">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="215ca-140">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="215ca-140">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="215ca-141">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="215ca-141">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="215ca-142">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="215ca-142">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
