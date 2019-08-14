---
title: 'Procedura dettagliata: Applicazione di stili a contenuto WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: 32ca9658ddf4ab6e8690f29797b7ac7b09df2ca7
ms.sourcegitcommit: d98fdb087d9c8aba7d2cb93fe4b4ee35a2308cee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2019
ms.locfileid: "69012951"
---
# <a name="walkthrough-style-wpf-content"></a><span data-ttu-id="a7296-102">Procedura dettagliata: Stile contenuto WPF</span><span class="sxs-lookup"><span data-stu-id="a7296-102">Walkthrough: Style WPF content</span></span>

<span data-ttu-id="a7296-103">Questa procedura dettagliata mostra come applicare uno stile a un controllo Windows Presentation Foundation (WPF) incluso in un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a7296-103">This walkthrough show you how to apply styling to a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>

 <span data-ttu-id="a7296-104">Questa procedura dettagliata prevede l'esecuzione delle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="a7296-104">In this walkthrough, you perform the following tasks:</span></span>

- <span data-ttu-id="a7296-105">Creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="a7296-105">Create the project.</span></span>

- <span data-ttu-id="a7296-106">Creare il tipo di controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="a7296-106">Create the WPF control type.</span></span>

- <span data-ttu-id="a7296-107">Applicare uno stile al controllo WPF.</span><span class="sxs-lookup"><span data-stu-id="a7296-107">Apply a style to the WPF control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a7296-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="a7296-108">Prerequisites</span></span>

<span data-ttu-id="a7296-109">Per completare la procedura dettagliata, è necessario Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a7296-109">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="a7296-110">Creare il progetto</span><span class="sxs-lookup"><span data-stu-id="a7296-110">Create the project</span></span>

<span data-ttu-id="a7296-111">Aprire Visual Studio e creare un nuovo progetto di applicazione Windows Forms in Visual Basic o C# in `StylingWpfContent`un oggetto visivo denominato.</span><span class="sxs-lookup"><span data-stu-id="a7296-111">Open Visual Studio and create a new Windows Forms Application project in Visual Basic or Visual C# named `StylingWpfContent`.</span></span>

> [!NOTE]
> <span data-ttu-id="a7296-112">Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a7296-112">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>

## <a name="create-the-wpf-control-types"></a><span data-ttu-id="a7296-113">Creare i tipi di controllo WPF</span><span class="sxs-lookup"><span data-stu-id="a7296-113">Create the WPF control types</span></span>

<span data-ttu-id="a7296-114">Dopo avere aggiunto un tipo di controllo WPF al progetto, è possibile inserirlo in un controllo <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="a7296-114">After you add a WPF control type to the project, you can host it in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

1. <span data-ttu-id="a7296-115">Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="a7296-115">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="a7296-116">Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="a7296-116">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="a7296-117">Per altre informazioni, vedere [Procedura dettagliata: Creazione di nuovo contenuto WPF in Windows Forms in fase](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a7296-117">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="a7296-118">In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="a7296-118">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="a7296-119">Per altre informazioni, vedere [Procedura: Consente di selezionare e spostare elementi nell'](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100))area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="a7296-119">For more information, see [How to: Select and Move Elements on the Design Surface](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb514527(v=vs.100)).</span></span>

3. <span data-ttu-id="a7296-120">Nella finestra **Proprietà** impostare il valore delle <xref:System.Windows.FrameworkElement.Width%2A> proprietà e <xref:System.Windows.FrameworkElement.Height%2A> su `200`.</span><span class="sxs-lookup"><span data-stu-id="a7296-120">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>

4. <span data-ttu-id="a7296-121">Aggiungere un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> <xref:System.Windows.Controls.UserControl> controllo a e <xref:System.Windows.Controls.ContentControl.Content%2A> impostare il valore della proprietà su **Cancel**.</span><span class="sxs-lookup"><span data-stu-id="a7296-121">Add a <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **Cancel**.</span></span>

5. <span data-ttu-id="a7296-122">Aggiungere un secondo <xref:System.Windows.Controls.Button?displayProperty=nameWithType> controllo <xref:System.Windows.Controls.UserControl> a e <xref:System.Windows.Controls.ContentControl.Content%2A> impostare il valore della proprietà su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7296-122">Add a second <xref:System.Windows.Controls.Button?displayProperty=nameWithType> control to the <xref:System.Windows.Controls.UserControl> and set the value of the <xref:System.Windows.Controls.ContentControl.Content%2A> property to **OK**.</span></span>

6. <span data-ttu-id="a7296-123">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="a7296-123">Build the project.</span></span>

## <a name="apply-a-style-to-a-wpf-control"></a><span data-ttu-id="a7296-124">Applicare uno stile a un controllo WPF</span><span class="sxs-lookup"><span data-stu-id="a7296-124">Apply a Style to a WPF Control</span></span>

<span data-ttu-id="a7296-125">È possibile applicare uno stile diverso a un controllo WPF per modificarne l'aspetto e il comportamento.</span><span class="sxs-lookup"><span data-stu-id="a7296-125">You can apply different styling to a WPF control to change its appearance and behavior.</span></span>

1. <span data-ttu-id="a7296-126">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a7296-126">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="a7296-127">Nella **casella degli strumenti**fare doppio clic `UserControl1` su per creare un'istanza `UserControl1` di nel form.</span><span class="sxs-lookup"><span data-stu-id="a7296-127">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>

     <span data-ttu-id="a7296-128">L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="a7296-128">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

1. <span data-ttu-id="a7296-129">Nel pannello smart tag per `elementHost1`fare clic su **modifica contenuto ospitato** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="a7296-129">In the smart tag panel for `elementHost1`, click **Edit Hosted Content** from the drop-down list.</span></span>

     <span data-ttu-id="a7296-130">`UserControl1` si apre in [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7296-130">`UserControl1` opens in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

1. <span data-ttu-id="a7296-131">Nella visualizzazione XAML inserire il seguente codice XAML dopo il tag di apertura `<UserControl>`.</span><span class="sxs-lookup"><span data-stu-id="a7296-131">In XAML view, insert the following XAML after the `<UserControl>` opening tag.</span></span>

     <span data-ttu-id="a7296-132">Questo codice XAML crea una sfumatura con un bordo sfumato a contrasto.</span><span class="sxs-lookup"><span data-stu-id="a7296-132">This XAML creates a gradient with a contrasting gradient border.</span></span> <span data-ttu-id="a7296-133">Quando si fa clic sul controllo, le sfumature vengono modificate per generare l'aspetto di un pulsante premuto.</span><span class="sxs-lookup"><span data-stu-id="a7296-133">When the control is clicked, the gradients are changed to generate a pressed button look.</span></span> <span data-ttu-id="a7296-134">Per altre informazioni, vedere [Applicazione di stili e modelli](../../wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="a7296-134">For more information, see [Styling and Templating](../../wpf/controls/styling-and-templating.md).</span></span>

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

1. <span data-ttu-id="a7296-135">Applicare al pulsante Cancel lo stile `SimpleButton` definito nel passaggio precedente inserendo il seguente codice XAML nel tag `<Button>` del pulsante Cancel.</span><span class="sxs-lookup"><span data-stu-id="a7296-135">Apply the `SimpleButton` style defined in the previous step to the Cancel button by inserting the following XAML in the `<Button>` tag of the Cancel button.</span></span>

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   <span data-ttu-id="a7296-136">La dichiarazione di un pulsante sarà simile al codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="a7296-136">Your button declaration will resemble the following XAML:</span></span>

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. <span data-ttu-id="a7296-137">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="a7296-137">Build the project.</span></span>

1. <span data-ttu-id="a7296-138">Aprire `Form1` in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a7296-138">Open `Form1` in the Windows Forms Designer.</span></span>

1. <span data-ttu-id="a7296-139">Il nuovo stile viene applicato al pulsante.</span><span class="sxs-lookup"><span data-stu-id="a7296-139">The new style is applied to the button control.</span></span>

1. <span data-ttu-id="a7296-140">Scegliere **Avvia debug** dal menu **debug** per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7296-140">From the **Debug** menu, select **Start Debugging** to run the application.</span></span>

1. <span data-ttu-id="a7296-141">Fare clic sui pulsanti OK e Cancel e visualizzare le differenze.</span><span class="sxs-lookup"><span data-stu-id="a7296-141">Click the OK and Cancel buttons and view the differences.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7296-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7296-142">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a7296-143">Migrazione e interoperabilità</span><span class="sxs-lookup"><span data-stu-id="a7296-143">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="a7296-144">Uso di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="a7296-144">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="a7296-145">Progettare XAML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a7296-145">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="a7296-146">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="a7296-146">XAML Overview (WPF)</span></span>](../../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="a7296-147">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="a7296-147">Styling and Templating</span></span>](../../wpf/controls/styling-and-templating.md)
