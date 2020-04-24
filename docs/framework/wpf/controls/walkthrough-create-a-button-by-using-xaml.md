---
title: 'Procedura dettagliata: creazione di un pulsante tramite XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646473"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="dc57e-102">Procedura dettagliata: creazione di un pulsante tramite XAML</span><span class="sxs-lookup"><span data-stu-id="dc57e-102">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="dc57e-103">L'obiettivo di questa procedura dettagliata consiste nell'imparare a creare un pulsante animato da utilizzare in un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="dc57e-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="dc57e-104">In questa procedura dettagliata vengono utilizzati gli stili e un modello per creare una risorsa pulsante personalizzata che consente il riutilizzo del codice e la separazione della logica del pulsante dalla dichiarazione del pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="dc57e-105">Questa procedura dettagliata [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]è scritta interamente in .</span><span class="sxs-lookup"><span data-stu-id="dc57e-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc57e-106">Questa procedura dettagliata illustra i passaggi per la creazione [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] dell'applicazione digitandoo o copiando e incollando in Visual Studio.This walkthrough guides you through the steps for creating the application by typing or copying and pasting into Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dc57e-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Visual Studio.</span></span> <span data-ttu-id="dc57e-107">Se si preferisce imparare a utilizzare una finestra di progettazione per creare la stessa applicazione, vedere [Creare un pulsante utilizzando Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span><span class="sxs-lookup"><span data-stu-id="dc57e-107">If you would prefer to learn how to use a designer to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="dc57e-108">La figura seguente mostra i pulsanti finiti.</span><span class="sxs-lookup"><span data-stu-id="dc57e-108">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="dc57e-109">![Pulsanti personalizzati creati utilizzando XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="dc57e-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="dc57e-110">Creazione di pulsanti di base</span><span class="sxs-lookup"><span data-stu-id="dc57e-110">Create Basic Buttons</span></span>

<span data-ttu-id="dc57e-111">Iniziamo creando un nuovo progetto e aggiungendo alcuni pulsanti alla finestra.</span><span class="sxs-lookup"><span data-stu-id="dc57e-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="dc57e-112">Per creare un nuovo progetto WPF e aggiungere pulsanti alla finestraTo create a new WPF project and add buttons to the window</span><span class="sxs-lookup"><span data-stu-id="dc57e-112">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="dc57e-113">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dc57e-113">Start Visual Studio.</span></span>

2. <span data-ttu-id="dc57e-114">**Creare un nuovo progetto WPF:Create** a new WPF project: Scegliere **Nuovo**dal menu **File** , quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="dc57e-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="dc57e-115">Individuare il modello **di applicazione Windows (WPF)** e denominare il progetto "AnimatedButton".</span><span class="sxs-lookup"><span data-stu-id="dc57e-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="dc57e-116">Questo creerà lo scheletro per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc57e-116">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="dc57e-117">**Aggiungere pulsanti predefiniti di base:** Tutti i file necessari per questa procedura dettagliata vengono forniti dal modello.</span><span class="sxs-lookup"><span data-stu-id="dc57e-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="dc57e-118">Aprire il file Window1.xaml facendo doppio clic su di esso in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="dc57e-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="dc57e-119">Per impostazione predefinita, è presente un elemento in Window1.xaml.By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="dc57e-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="dc57e-120">Rimuovi <xref:System.Windows.Controls.Grid> l'elemento e aggiungi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] alcuni pulsanti alla pagina digitando o copiando e incollando il seguente codice evidenziato in Window1.xaml:</span><span class="sxs-lookup"><span data-stu-id="dc57e-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     <span data-ttu-id="dc57e-121">Premere F5 per eseguire l'applicazione; si dovrebbe vedere un set di pulsanti che assomiglia alla figura seguente.</span><span class="sxs-lookup"><span data-stu-id="dc57e-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="dc57e-122">![Tre pulsanti di base](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="dc57e-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="dc57e-123">Dopo aver creato i pulsanti di base, si sta terminando di lavorare nel file Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="dc57e-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="dc57e-124">Il resto della procedura dettagliata è incentrato sul file app.xaml, sulla definizione degli stili e su un modello per i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="dc57e-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="dc57e-125">Impostazione delle proprietà di base</span><span class="sxs-lookup"><span data-stu-id="dc57e-125">Set Basic Properties</span></span>

<span data-ttu-id="dc57e-126">Successivamente, è possibile impostare alcune proprietà su questi pulsanti per controllare l'aspetto e il layout del pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="dc57e-127">Anziché impostare le proprietà sui pulsanti singolarmente, si utilizzeranno le risorse per definire le proprietà dei pulsanti per l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc57e-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="dc57e-128">Le risorse dell'applicazione sono concettualmente simili ai css (Cascading Style Sheets) esterni per le pagine Web. tuttavia, le risorse sono molto più potenti dei fogli di stile CSS (Cascading Style Sheets), come si vedrà alla fine di questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="dc57e-128">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="dc57e-129">Per altre informazioni sulle risorse, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="dc57e-129">To learn more about resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="dc57e-130">Per utilizzare gli stili per impostare le proprietà di base sui pulsanti</span><span class="sxs-lookup"><span data-stu-id="dc57e-130">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="dc57e-131">**Definire un blocco Application.Resources:Define an Application.Resources block:** Apri app.xaml e aggiungi il markup evidenziato seguente, se non è già presente:</span><span class="sxs-lookup"><span data-stu-id="dc57e-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     <span data-ttu-id="dc57e-132">L'ambito della risorsa è determinato dalla posizione in cui si definisce la risorsa.</span><span class="sxs-lookup"><span data-stu-id="dc57e-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="dc57e-133">La definizione delle risorse nel `Application.Resources` file app.xaml consente di usare la risorsa da qualsiasi punto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc57e-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="dc57e-134">Per altre informazioni sulla definizione dell'ambito delle risorse, vedere [Risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="dc57e-134">To learn more about defining the scope of your resources, see [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

2. <span data-ttu-id="dc57e-135">Creare uno stile e definire i valori di **proprietà di base con esso:Create** a style and define basic property values with it: Aggiungere il markup `Application.Resources` seguente al blocco.</span><span class="sxs-lookup"><span data-stu-id="dc57e-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="dc57e-136">Questo markup <xref:System.Windows.Style> crea un che si applica a <xref:System.Windows.FrameworkElement.Width%2A> tutti i pulsanti <xref:System.Windows.FrameworkElement.Margin%2A> nell'applicazione, impostando il dei pulsanti su 90 e il a 10:</span><span class="sxs-lookup"><span data-stu-id="dc57e-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="dc57e-137">La <xref:System.Windows.Style.TargetType%2A> proprietà specifica che lo stile si <xref:System.Windows.Controls.Button>applica a tutti gli oggetti di tipo .</span><span class="sxs-lookup"><span data-stu-id="dc57e-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="dc57e-138">Ognuno <xref:System.Windows.Setter> imposta un valore <xref:System.Windows.Style>di proprietà diverso per il file .</span><span class="sxs-lookup"><span data-stu-id="dc57e-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="dc57e-139">Pertanto, a questo punto ogni pulsante nell'applicazione ha una larghezza di 90 e un margine di 10.</span><span class="sxs-lookup"><span data-stu-id="dc57e-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="dc57e-140">Se si preme F5 per eseguire l'applicazione, viene visualizzata la finestra seguente.</span><span class="sxs-lookup"><span data-stu-id="dc57e-140">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="dc57e-141">![Pulsanti con una larghezza di 90 e un margine di 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="dc57e-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="dc57e-142">C'è molto di più che si può fare con gli stili, tra cui una varietà di modi per ottimizzare quali oggetti sono mirati, specificando valori di proprietà complessi, e anche utilizzando gli stili come input per altri stili.</span><span class="sxs-lookup"><span data-stu-id="dc57e-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="dc57e-143">Per altre informazioni, vedere [Applicazione di stili e modelli](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dc57e-143">For more information, see [Styling and Templating](../../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

3. <span data-ttu-id="dc57e-144">**Impostare il valore di una proprietà di stile su una risorsa:Set a style property value to a resource:** Le risorse consentono un modo semplice per riutilizzare oggetti e valori comunemente definiti.</span><span class="sxs-lookup"><span data-stu-id="dc57e-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="dc57e-145">È particolarmente utile definire valori complessi usando le risorse per rendere il codice più modulare.</span><span class="sxs-lookup"><span data-stu-id="dc57e-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="dc57e-146">Aggiungi il markup evidenziato seguente a app.xaml.</span><span class="sxs-lookup"><span data-stu-id="dc57e-146">Add the following highlighted markup to app.xaml.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="dc57e-147">Direttamente sotto `Application.Resources` il blocco, è stata creata una risorsa denominata "GrayBlueGradientBrush".</span><span class="sxs-lookup"><span data-stu-id="dc57e-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="dc57e-148">Questa risorsa definisce una sfumatura orizzontale.</span><span class="sxs-lookup"><span data-stu-id="dc57e-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="dc57e-149">Questa risorsa può essere utilizzata come valore della proprietà da qualsiasi punto <xref:System.Windows.Controls.Control.Background%2A> dell'applicazione, incluso il setter di stile del pulsante per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc57e-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="dc57e-150">A questo punto, <xref:System.Windows.Controls.Control.Background%2A> tutti i pulsanti hanno un valore di proprietà di questa sfumatura.</span><span class="sxs-lookup"><span data-stu-id="dc57e-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="dc57e-151">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc57e-151">Press F5 to run the application.</span></span> <span data-ttu-id="dc57e-152">Dovrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="dc57e-152">It should look like the following.</span></span>

     <span data-ttu-id="dc57e-153">![Pulsanti con uno sfondo sfumato](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="dc57e-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="dc57e-154">Creazione di un modello che definisce l'aspetto del pulsante</span><span class="sxs-lookup"><span data-stu-id="dc57e-154">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="dc57e-155">In questa sezione viene creato un modello che personalizza l'aspetto (presentazione) del pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="dc57e-156">La presentazione del pulsante è composta da diversi oggetti, tra cui rettangoli e altri componenti per conferire al pulsante un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="dc57e-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="dc57e-157">Finora, il controllo dell'aspetto dei pulsanti nell'applicazione è stato limitato alla modifica delle proprietà del pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="dc57e-158">Cosa succede se si desidera apportare modifiche più radicali all'aspetto del pulsante?</span><span class="sxs-lookup"><span data-stu-id="dc57e-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="dc57e-159">I modelli consentono un potente controllo sulla presentazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="dc57e-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="dc57e-160">Poiché i modelli possono essere utilizzati all'interno di stili, è possibile applicare un modello a tutti gli oggetti a cui si applica lo stile (in questa procedura dettagliata, il pulsante).</span><span class="sxs-lookup"><span data-stu-id="dc57e-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="dc57e-161">Per utilizzare il modello per definire l'aspetto del pulsante</span><span class="sxs-lookup"><span data-stu-id="dc57e-161">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="dc57e-162">**Impostare il modello:** Poiché <xref:System.Windows.Controls.Button> i <xref:System.Windows.Controls.Control.Template%2A> controlli come dispongono di una proprietà, è possibile definire <xref:System.Windows.Style> il <xref:System.Windows.Setter>valore della proprietà del modello come gli altri valori di proprietà impostati in un oggetto using a .</span><span class="sxs-lookup"><span data-stu-id="dc57e-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="dc57e-163">Aggiungere il markup evidenziato seguente allo stile del pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-163">Add the following highlighted markup to your button style.</span></span>

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. <span data-ttu-id="dc57e-164">**Cambia presentazione pulsante:** A questo punto, è necessario definire il modello.</span><span class="sxs-lookup"><span data-stu-id="dc57e-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="dc57e-165">Aggiungere il markup evidenziato seguente.</span><span class="sxs-lookup"><span data-stu-id="dc57e-165">Add the following highlighted markup.</span></span> <span data-ttu-id="dc57e-166">Questo markup specifica <xref:System.Windows.Shapes.Rectangle> due elementi con bordi <xref:System.Windows.Controls.DockPanel>arrotondati, seguiti da un oggetto .</span><span class="sxs-lookup"><span data-stu-id="dc57e-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="dc57e-167">L'oggetto <xref:System.Windows.Controls.DockPanel> viene <xref:System.Windows.Controls.ContentPresenter> utilizzato per ospitare il pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="dc57e-168">A <xref:System.Windows.Controls.ContentPresenter> visualizza il contenuto del pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="dc57e-169">In questa procedura dettagliata, il contenuto è testo ("Pulsante 1", "Pulsante 2", "Pulsante 3").</span><span class="sxs-lookup"><span data-stu-id="dc57e-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="dc57e-170">Tutti i componenti del modello (i rettangoli e <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Grid>il ) sono disposti all'interno di un oggetto .</span><span class="sxs-lookup"><span data-stu-id="dc57e-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="dc57e-171">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc57e-171">Press F5 to run the application.</span></span> <span data-ttu-id="dc57e-172">Dovrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="dc57e-172">It should look like the following.</span></span>

     ![Finestra con 3 pulsanti](./media/custom-button-animatedbutton-4.gif)

3. <span data-ttu-id="dc57e-174">**Aggiungere un effetto vetro al modello:** Successivamente si aggiungerà il vetro.</span><span class="sxs-lookup"><span data-stu-id="dc57e-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="dc57e-175">Per prima cosa si creano alcune risorse che creano un effetto sfumatura di vetro.</span><span class="sxs-lookup"><span data-stu-id="dc57e-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="dc57e-176">Aggiungere queste risorse sfumatura in qualsiasi punto del blocco:Add these gradient resources anywhere within the `Application.Resources` block:</span><span class="sxs-lookup"><span data-stu-id="dc57e-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     <span data-ttu-id="dc57e-177">Queste risorse vengono <xref:System.Windows.Shapes.Shape.Fill%2A> utilizzate come per un <xref:System.Windows.Controls.Grid> rettangolo che inseriamo nel modello di pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="dc57e-178">Aggiungere il markup evidenziato seguente al modello.</span><span class="sxs-lookup"><span data-stu-id="dc57e-178">Add the following highlighted markup to the template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     <span data-ttu-id="dc57e-179">Si noti che <xref:System.Windows.UIElement.Opacity%2A> il `x:Name` rettangolo con la proprietà di "glassCube" è 0, pertanto quando si esegue l'esempio, non viene visualizzato il rettangolo di vetro sovrapposto.</span><span class="sxs-lookup"><span data-stu-id="dc57e-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="dc57e-180">Questo perché in seguito aggiungeremo trigger al modello per quando l'utente interagisce con il pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="dc57e-181">Tuttavia, è possibile visualizzare l'aspetto <xref:System.Windows.UIElement.Opacity%2A> del pulsante modificando il valore in 1 ed eseguendo l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc57e-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="dc57e-182">Vedere la figura seguente.</span><span class="sxs-lookup"><span data-stu-id="dc57e-182">See the following figure.</span></span> <span data-ttu-id="dc57e-183">Prima di procedere al passaggio successivo, impostare la riadesu0 <xref:System.Windows.UIElement.Opacity%2A> su 0.</span><span class="sxs-lookup"><span data-stu-id="dc57e-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="dc57e-184">![Pulsanti personalizzati creati utilizzando XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="dc57e-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="dc57e-185">Crea interattività pulsante</span><span class="sxs-lookup"><span data-stu-id="dc57e-185">Create Button Interactivity</span></span>

<span data-ttu-id="dc57e-186">In questa sezione verranno creati trigger di proprietà e trigger di evento per modificare i valori delle proprietà ed eseguire animazioni in risposta alle azioni dell'utente, ad esempio spostando il puntatore del mouse sul pulsante e facendo clic.</span><span class="sxs-lookup"><span data-stu-id="dc57e-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="dc57e-187">Un modo semplice per aggiungere interattività (mouse-over, mouse-leave, click e così via) consiste nel definire i trigger all'interno del modello o dello stile.</span><span class="sxs-lookup"><span data-stu-id="dc57e-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="dc57e-188">Per creare <xref:System.Windows.Trigger>una , si definisce una proprietà <xref:System.Windows.UIElement.IsMouseOver%2A> "condizione", `true`ad esempio: il valore della proprietà button è uguale a .</span><span class="sxs-lookup"><span data-stu-id="dc57e-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="dc57e-189">È quindi possibile definire i setter (azioni) che si verificano quando la condizione del trigger è true.</span><span class="sxs-lookup"><span data-stu-id="dc57e-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="dc57e-190">Per creare l'interattività dei pulsanti</span><span class="sxs-lookup"><span data-stu-id="dc57e-190">To create button interactivity</span></span>

1. <span data-ttu-id="dc57e-191">**Aggiungere trigger di modello:** Aggiungere il markup evidenziato al modello.</span><span class="sxs-lookup"><span data-stu-id="dc57e-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. <span data-ttu-id="dc57e-192">**Aggiungere trigger di proprietà:** Aggiungere il markup `ControlTemplate.Triggers` evidenziato al blocco:</span><span class="sxs-lookup"><span data-stu-id="dc57e-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="dc57e-193">Premere F5 per eseguire l'applicazione e vedere l'effetto mentre si esegue il puntatore del mouse sui pulsanti.</span><span class="sxs-lookup"><span data-stu-id="dc57e-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="dc57e-194">**Aggiungere un trigger di messa a fuoco:Add** a focus trigger: Successivamente, aggiungeremo alcuni setter simili per gestire il caso in cui il pulsante ha lo stato attivo (ad esempio, dopo che l'utente fa clic su di esso).</span><span class="sxs-lookup"><span data-stu-id="dc57e-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     <span data-ttu-id="dc57e-195">Premere F5 per eseguire l'applicazione e fare clic su uno dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="dc57e-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="dc57e-196">Si noti che il pulsante rimane evidenziato dopo aver fatto clic su di esso perché ha ancora lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="dc57e-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="dc57e-197">Se si fa clic su un altro pulsante, il nuovo pulsante ottiene lo stato attivo mentre l'ultimo lo perde.</span><span class="sxs-lookup"><span data-stu-id="dc57e-197">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="dc57e-198">**Aggiungi animazioni per** <xref:System.Windows.UIElement.MouseEnter> **e** <xref:System.Windows.UIElement.MouseLeave> **:** Successivamente aggiungiamo alcune animazioni ai trigger.  </span><span class="sxs-lookup"><span data-stu-id="dc57e-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="dc57e-199">Aggiungere il markup seguente `ControlTemplate.Triggers` in un punto qualsiasi all'interno del blocco.</span><span class="sxs-lookup"><span data-stu-id="dc57e-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="dc57e-200">Il rettangolo di vetro si riduce quando il puntatore del mouse si sposta sul pulsante e torna alle dimensioni normali quando il puntatore esce.</span><span class="sxs-lookup"><span data-stu-id="dc57e-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="dc57e-201">Esistono due animazioni che vengono attivate quando<xref:System.Windows.UIElement.MouseEnter> il puntatore passa sopra il pulsante (viene generato l'evento).</span><span class="sxs-lookup"><span data-stu-id="dc57e-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="dc57e-202">Queste animazioni riducono il rettangolo di vetro lungo gli assi X e Y.</span><span class="sxs-lookup"><span data-stu-id="dc57e-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="dc57e-203">Si notino <xref:System.Windows.Media.Animation.DoubleAnimation> le <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>proprietà degli elementi, e .</span><span class="sxs-lookup"><span data-stu-id="dc57e-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="dc57e-204">Specifica <xref:System.Windows.Media.Animation.Timeline.Duration%2A> che l'animazione si verifica <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> per più di mezzo secondo e specifica che il vetro si riduce del 10%.</span><span class="sxs-lookup"><span data-stu-id="dc57e-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="dc57e-205">Il secondo trigger<xref:System.Windows.UIElement.MouseLeave>di evento ( ) arresta semplicemente il primo.</span><span class="sxs-lookup"><span data-stu-id="dc57e-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="dc57e-206">Quando si <xref:System.Windows.Media.Animation.Storyboard>interrompe un oggetto , tutte le proprietà animate tornano ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="dc57e-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="dc57e-207">Pertanto, quando l'utente sposta il puntatore fuori dal pulsante, il pulsante torna al modo in cui era prima che il puntatore del mouse spostato sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="dc57e-208">Per ulteriori informazioni sulle animazioni, consultate [Cenni preliminari](../graphics-multimedia/animation-overview.md)sulle animazioni.</span><span class="sxs-lookup"><span data-stu-id="dc57e-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="dc57e-209">**Aggiungere un'animazione per quando si fa clic sul pulsante:** Il passaggio finale consiste nell'aggiungere un trigger per quando l'utente fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="dc57e-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="dc57e-210">Aggiungere il markup seguente `ControlTemplate.Triggers` in qualsiasi punto all'interno del blocco:</span><span class="sxs-lookup"><span data-stu-id="dc57e-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     <span data-ttu-id="dc57e-211">Premere F5 per eseguire l'applicazione e fare clic su uno dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="dc57e-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="dc57e-212">Quando si fa clic su un pulsante, il rettangolo di vetro ruota intorno.</span><span class="sxs-lookup"><span data-stu-id="dc57e-212">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="dc57e-213">Summary</span><span class="sxs-lookup"><span data-stu-id="dc57e-213">Summary</span></span>
 <span data-ttu-id="dc57e-214">In questa procedura dettagliata sono stati eseguiti gli esercizi seguenti:In this walkthrough, you performed the following exercises:</span><span class="sxs-lookup"><span data-stu-id="dc57e-214">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="dc57e-215">Destinato <xref:System.Windows.Style> a un tipo<xref:System.Windows.Controls.Button>di oggetto ( ).</span><span class="sxs-lookup"><span data-stu-id="dc57e-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="dc57e-216">Controllate le proprietà di base dei <xref:System.Windows.Style>pulsanti nell'intera applicazione utilizzando il metodo .</span><span class="sxs-lookup"><span data-stu-id="dc57e-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="dc57e-217">Risorse create come sfumature da utilizzare <xref:System.Windows.Style> per i valori delle proprietà dei setter.</span><span class="sxs-lookup"><span data-stu-id="dc57e-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="dc57e-218">Personalizzato l'aspetto dei pulsanti nell'intera applicazione applicando un modello ai pulsanti.</span><span class="sxs-lookup"><span data-stu-id="dc57e-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="dc57e-219">Comportamento personalizzato per i pulsanti in risposta <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave>alle <xref:System.Windows.Controls.Primitives.ButtonBase.Click>azioni dell'utente (ad esempio , e ) che includevano effetti di animazione.</span><span class="sxs-lookup"><span data-stu-id="dc57e-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc57e-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc57e-220">See also</span></span>

- [<span data-ttu-id="dc57e-221">Creare un pulsante usando Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="dc57e-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="dc57e-222">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="dc57e-222">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="dc57e-223">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="dc57e-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="dc57e-224">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="dc57e-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="dc57e-225">Cenni preliminari sugli effetti bitmap</span><span class="sxs-lookup"><span data-stu-id="dc57e-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
