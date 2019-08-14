---
title: 'Procedura dettagliata: Creare un pulsante usando XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 3d8fb3fbbf31b547644ae171aaf81654812d8a20
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971908"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="2e87f-102">Procedura dettagliata: Creare un pulsante usando XAML</span><span class="sxs-lookup"><span data-stu-id="2e87f-102">Walkthrough: Create a Button by Using XAML</span></span>

<span data-ttu-id="2e87f-103">In questa procedura dettagliata viene illustrato come creare un pulsante animato da utilizzare in un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="2e87f-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="2e87f-104">Questa procedura dettagliata USA stili e un modello per creare una risorsa pulsante personalizzata che consente il riutilizzo del codice e la separazione della logica dei pulsanti dalla dichiarazione del pulsante.</span><span class="sxs-lookup"><span data-stu-id="2e87f-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="2e87f-105">Questa procedura dettagliata viene scritta interamente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]in.</span><span class="sxs-lookup"><span data-stu-id="2e87f-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e87f-106">Questa procedura dettagliata illustra i passaggi per la creazione dell'applicazione digitando o copiando e [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] incollando in Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2e87f-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Microsoft Visual Studio.</span></span> <span data-ttu-id="2e87f-107">Per informazioni sull'utilizzo di uno strumento di progettazione (Microsoft Expression Blend) per creare la stessa applicazione, vedere [creare un pulsante tramite Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span><span class="sxs-lookup"><span data-stu-id="2e87f-107">If you would prefer to learn how to use a design tool (Microsoft Expression Blend) to create the same application, see [Create a Button by Using Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>

<span data-ttu-id="2e87f-108">Nella figura seguente sono illustrati i pulsanti finiti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-108">The following figure shows the finished buttons.</span></span>

<span data-ttu-id="2e87f-109">![Pulsanti personalizzati creati tramite XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="2e87f-109">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-basic-buttons"></a><span data-ttu-id="2e87f-110">Crea pulsanti di base</span><span class="sxs-lookup"><span data-stu-id="2e87f-110">Create Basic Buttons</span></span>

<span data-ttu-id="2e87f-111">Iniziamo creando un nuovo progetto e aggiungendo alcuni pulsanti alla finestra.</span><span class="sxs-lookup"><span data-stu-id="2e87f-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="2e87f-112">Per creare un nuovo progetto WPF e aggiungere pulsanti alla finestra</span><span class="sxs-lookup"><span data-stu-id="2e87f-112">To create a new WPF project and add buttons to the window</span></span>

1. <span data-ttu-id="2e87f-113">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2e87f-113">Start Visual Studio.</span></span>

2. <span data-ttu-id="2e87f-114">**Creare un nuovo progetto WPF:** Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="2e87f-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="2e87f-115">Trovare il modello di **applicazione Windows (WPF)** e denominare il progetto "AnimatedButton".</span><span class="sxs-lookup"><span data-stu-id="2e87f-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="2e87f-116">Verrà creata la struttura per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e87f-116">This will create the skeleton for the application.</span></span>

3. <span data-ttu-id="2e87f-117">**Aggiungere i pulsanti predefiniti di base:** Tutti i file necessari per questa procedura dettagliata sono forniti dal modello.</span><span class="sxs-lookup"><span data-stu-id="2e87f-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="2e87f-118">Aprire il file Window1. xaml facendo doppio clic su di esso in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="2e87f-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="2e87f-119">Per impostazione predefinita, è presente <xref:System.Windows.Controls.Grid> un elemento in Window1. XAML.</span><span class="sxs-lookup"><span data-stu-id="2e87f-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="2e87f-120">Rimuovere l' <xref:System.Windows.Controls.Grid> elemento e aggiungere alcuni pulsanti [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] alla pagina digitando o copiando e incollando il codice evidenziato seguente in Window1. XAML:</span><span class="sxs-lookup"><span data-stu-id="2e87f-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>

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

     <span data-ttu-id="2e87f-121">Premere F5 per eseguire l'applicazione; verrà visualizzato un set di pulsanti simile a quello illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="2e87f-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>

     <span data-ttu-id="2e87f-122">![Tre pulsanti di base](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="2e87f-122">![Three basic buttons](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>

     <span data-ttu-id="2e87f-123">Ora che sono stati creati i pulsanti di base, si è terminato di usare il file Window1. XAML.</span><span class="sxs-lookup"><span data-stu-id="2e87f-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="2e87f-124">Il resto della procedura dettagliata è incentrato sul file app. XAML, definendo gli stili e un modello per i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>

## <a name="set-basic-properties"></a><span data-ttu-id="2e87f-125">Imposta proprietà di base</span><span class="sxs-lookup"><span data-stu-id="2e87f-125">Set Basic Properties</span></span>

<span data-ttu-id="2e87f-126">Successivamente, è possibile impostare alcune proprietà su questi pulsanti per controllare l'aspetto e il layout dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="2e87f-127">Invece di impostare le proprietà sui pulsanti singolarmente, si utilizzeranno le risorse per definire le proprietà dei pulsanti per l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e87f-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="2e87f-128">Le risorse dell'applicazione sono concettualmente simili a Cascading Style Sheets esterno (CSS) per le pagine Web; Tuttavia, le risorse sono molto più potenti di Cascading Style Sheets (CSS), come si vedrà alla fine di questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="2e87f-128">Application resources are conceptually similar to external Cascading Style Sheets (CSS) for Web pages; however, resources are much more powerful than Cascading Style Sheets (CSS), as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="2e87f-129">Per altre informazioni sulle risorse, vedere [risorse XAML](../advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="2e87f-129">To learn more about resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="2e87f-130">Per utilizzare gli stili per impostare le proprietà di base sui pulsanti</span><span class="sxs-lookup"><span data-stu-id="2e87f-130">To use styles to set basic properties on the buttons</span></span>

1. <span data-ttu-id="2e87f-131">**Definire un blocco Application. resources:** Aprire app. XAML e aggiungere il markup evidenziato seguente se non è già presente:</span><span class="sxs-lookup"><span data-stu-id="2e87f-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>

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

     <span data-ttu-id="2e87f-132">L'ambito della risorsa è determinato dalla posizione in cui viene definita la risorsa.</span><span class="sxs-lookup"><span data-stu-id="2e87f-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="2e87f-133">La definizione delle `Application.Resources` risorse in nel file app. XAML consente di usare la risorsa da qualsiasi punto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e87f-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="2e87f-134">Per altre informazioni sulla definizione dell'ambito delle risorse, vedere [risorse XAML](../advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="2e87f-134">To learn more about defining the scope of your resources, see [XAML Resources](../advanced/xaml-resources.md).</span></span>

2. <span data-ttu-id="2e87f-135">**Creare uno stile e definire i valori di proprietà di base:** Aggiungere al `Application.Resources` blocco il markup seguente.</span><span class="sxs-lookup"><span data-stu-id="2e87f-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="2e87f-136">Questo markup crea un <xref:System.Windows.Style> oggetto che si applica a tutti i pulsanti nell'applicazione, <xref:System.Windows.FrameworkElement.Width%2A> impostando il dei <xref:System.Windows.FrameworkElement.Margin%2A> pulsanti su 90 e su 10:</span><span class="sxs-lookup"><span data-stu-id="2e87f-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     <span data-ttu-id="2e87f-137">La <xref:System.Windows.Style.TargetType%2A> proprietà specifica che lo stile si applica a tutti gli oggetti <xref:System.Windows.Controls.Button>di tipo.</span><span class="sxs-lookup"><span data-stu-id="2e87f-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="2e87f-138">Ogni <xref:System.Windows.Setter> imposta un valore di proprietà diverso per <xref:System.Windows.Style>l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="2e87f-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="2e87f-139">Quindi, a questo punto ogni pulsante nell'applicazione ha una larghezza di 90 e un margine di 10.</span><span class="sxs-lookup"><span data-stu-id="2e87f-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="2e87f-140">Se si preme F5 per eseguire l'applicazione, viene visualizzata la finestra seguente.</span><span class="sxs-lookup"><span data-stu-id="2e87f-140">If you press F5 to run the application, you see the following window.</span></span>

     <span data-ttu-id="2e87f-141">![Pulsanti con una larghezza di 90 e un margine di 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="2e87f-141">![Buttons with a width of 90 and a margin of 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>

     <span data-ttu-id="2e87f-142">È possibile eseguire molte altre operazioni con gli stili, inclusi diversi modi per ottimizzare gli oggetti di destinazione, specificare valori di proprietà complessi e persino usare gli stili come input per altri stili.</span><span class="sxs-lookup"><span data-stu-id="2e87f-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="2e87f-143">Per altre informazioni, vedere [Applicazione di stili e modelli](styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="2e87f-143">For more information, see [Styling and Templating](styling-and-templating.md).</span></span>

3. <span data-ttu-id="2e87f-144">**Impostare un valore di proprietà di stile su una risorsa:** Le risorse consentono un metodo semplice per riutilizzare oggetti e valori comunemente definiti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="2e87f-145">È particolarmente utile per definire valori complessi usando le risorse per rendere il codice più modulare.</span><span class="sxs-lookup"><span data-stu-id="2e87f-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="2e87f-146">Aggiungere il markup evidenziato seguente ad app. XAML.</span><span class="sxs-lookup"><span data-stu-id="2e87f-146">Add the following highlighted markup to app.xaml.</span></span>

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

     <span data-ttu-id="2e87f-147">Direttamente sotto il `Application.Resources` blocco è stata creata una risorsa denominata "GrayBlueGradientBrush".</span><span class="sxs-lookup"><span data-stu-id="2e87f-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="2e87f-148">Questa risorsa definisce una sfumatura orizzontale.</span><span class="sxs-lookup"><span data-stu-id="2e87f-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="2e87f-149">Questa risorsa può essere usata come valore della proprietà da qualsiasi punto dell'applicazione, incluso all'interno del setter di stile del <xref:System.Windows.Controls.Control.Background%2A> pulsante per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="2e87f-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="2e87f-150">A questo punto, tutti i pulsanti <xref:System.Windows.Controls.Control.Background%2A> hanno un valore della proprietà di questa sfumatura.</span><span class="sxs-lookup"><span data-stu-id="2e87f-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>

     <span data-ttu-id="2e87f-151">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e87f-151">Press F5 to run the application.</span></span> <span data-ttu-id="2e87f-152">Dovrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="2e87f-152">It should look like the following.</span></span>

     <span data-ttu-id="2e87f-153">![Pulsanti con sfondo sfumato](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="2e87f-153">![Buttons with a gradient background](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>

## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="2e87f-154">Creare un modello che definisce l'aspetto del pulsante</span><span class="sxs-lookup"><span data-stu-id="2e87f-154">Create a Template That Defines the Look of the Button</span></span>

<span data-ttu-id="2e87f-155">In questa sezione viene creato un modello per personalizzare l'aspetto (presentazione) del pulsante.</span><span class="sxs-lookup"><span data-stu-id="2e87f-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="2e87f-156">La presentazione del pulsante è costituita da diversi oggetti, inclusi i rettangoli e altri componenti, per dare al pulsante un aspetto univoco.</span><span class="sxs-lookup"><span data-stu-id="2e87f-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>

<span data-ttu-id="2e87f-157">Fino a questo punto, il controllo dell'aspetto dei pulsanti nell'applicazione è stato limitato alla modifica delle proprietà del pulsante.</span><span class="sxs-lookup"><span data-stu-id="2e87f-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="2e87f-158">Che cosa accade se si desidera apportare modifiche più radicali all'aspetto del pulsante?</span><span class="sxs-lookup"><span data-stu-id="2e87f-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="2e87f-159">I modelli consentono un controllo potente sulla presentazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="2e87f-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="2e87f-160">Poiché i modelli possono essere utilizzati all'interno di stili, è possibile applicare un modello a tutti gli oggetti a cui lo stile si applica (in questa procedura dettagliata, il pulsante).</span><span class="sxs-lookup"><span data-stu-id="2e87f-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="2e87f-161">Per usare il modello per definire l'aspetto del pulsante</span><span class="sxs-lookup"><span data-stu-id="2e87f-161">To use the template to define the look of the button</span></span>

1. <span data-ttu-id="2e87f-162">**Configurare il modello:** Poiché i controlli <xref:System.Windows.Controls.Button> come hanno <xref:System.Windows.Controls.Control.Template%2A> una proprietà, è possibile definire il valore della proprietà del modello proprio come gli altri valori di proprietà impostati <xref:System.Windows.Style> in un <xref:System.Windows.Setter>oggetto usando un oggetto.</span><span class="sxs-lookup"><span data-stu-id="2e87f-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="2e87f-163">Aggiungere il markup evidenziato seguente allo stile del pulsante.</span><span class="sxs-lookup"><span data-stu-id="2e87f-163">Add the following highlighted markup to your button style.</span></span>

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

2. <span data-ttu-id="2e87f-164">**Presentazione pulsante modifica:** A questo punto, è necessario definire il modello.</span><span class="sxs-lookup"><span data-stu-id="2e87f-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="2e87f-165">Aggiungere il markup evidenziato seguente.</span><span class="sxs-lookup"><span data-stu-id="2e87f-165">Add the following highlighted markup.</span></span> <span data-ttu-id="2e87f-166">Questo markup specifica due <xref:System.Windows.Shapes.Rectangle> elementi con bordi arrotondati, seguiti <xref:System.Windows.Controls.DockPanel>da.</span><span class="sxs-lookup"><span data-stu-id="2e87f-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="2e87f-167">Viene utilizzato per ospitare l'oggetto <xref:System.Windows.Controls.ContentPresenter> del pulsante. <xref:System.Windows.Controls.DockPanel></span><span class="sxs-lookup"><span data-stu-id="2e87f-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="2e87f-168">Un <xref:System.Windows.Controls.ContentPresenter> oggetto Visualizza il contenuto del pulsante.</span><span class="sxs-lookup"><span data-stu-id="2e87f-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="2e87f-169">In questa procedura dettagliata il contenuto è testo ("Button 1", "Button 2", "Button 3").</span><span class="sxs-lookup"><span data-stu-id="2e87f-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="2e87f-170">Tutti i componenti del modello, ovvero i rettangoli e <xref:System.Windows.Controls.DockPanel>, sono disposti all'interno di un <xref:System.Windows.Controls.Grid>oggetto.</span><span class="sxs-lookup"><span data-stu-id="2e87f-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>

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

     <span data-ttu-id="2e87f-171">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e87f-171">Press F5 to run the application.</span></span> <span data-ttu-id="2e87f-172">Dovrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="2e87f-172">It should look like the following.</span></span>

     <span data-ttu-id="2e87f-173">![](./media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span><span class="sxs-lookup"><span data-stu-id="2e87f-173">![](./media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span></span>

3. <span data-ttu-id="2e87f-174">**Aggiungere un GlassEffect al modello:** Successivamente, verrà aggiunto il vetro.</span><span class="sxs-lookup"><span data-stu-id="2e87f-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="2e87f-175">Prima di tutto, è necessario creare alcune risorse che creino un effetto gradiente di cristallo.</span><span class="sxs-lookup"><span data-stu-id="2e87f-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="2e87f-176">Aggiungere queste risorse gradienti in qualsiasi `Application.Resources` punto all'interno del blocco:</span><span class="sxs-lookup"><span data-stu-id="2e87f-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>

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

     <span data-ttu-id="2e87f-177">Queste risorse vengono usate come <xref:System.Windows.Shapes.Shape.Fill%2A> per un rettangolo inserito nell'oggetto <xref:System.Windows.Controls.Grid> del modello di pulsante.</span><span class="sxs-lookup"><span data-stu-id="2e87f-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="2e87f-178">Aggiungere il markup evidenziato seguente al modello.</span><span class="sxs-lookup"><span data-stu-id="2e87f-178">Add the following highlighted markup to the template.</span></span>

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

     <span data-ttu-id="2e87f-179">Si noti che <xref:System.Windows.UIElement.Opacity%2A> il del rettangolo con la `x:Name` proprietà di "glassCube" è 0, pertanto quando si esegue l'esempio, il rettangolo di cristallo viene sovrapposto alla parte superiore.</span><span class="sxs-lookup"><span data-stu-id="2e87f-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="2e87f-180">Ciò è dovuto al fatto che in seguito si aggiungeranno trigger al modello per quando l'utente interagisce con il pulsante.</span><span class="sxs-lookup"><span data-stu-id="2e87f-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="2e87f-181">Tuttavia, è possibile visualizzare l'aspetto del pulsante modificando il <xref:System.Windows.UIElement.Opacity%2A> valore in 1 ed eseguendo l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e87f-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="2e87f-182">Vedere la figura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="2e87f-182">See the following figure.</span></span> <span data-ttu-id="2e87f-183">Prima di procedere con il passaggio successivo, modificare il <xref:System.Windows.UIElement.Opacity%2A> ritorno a 0.</span><span class="sxs-lookup"><span data-stu-id="2e87f-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>

     <span data-ttu-id="2e87f-184">![Pulsanti personalizzati creati tramite XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="2e87f-184">![Custom buttons that were created by using XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>

## <a name="create-button-interactivity"></a><span data-ttu-id="2e87f-185">Interattività pulsante Crea</span><span class="sxs-lookup"><span data-stu-id="2e87f-185">Create Button Interactivity</span></span>

<span data-ttu-id="2e87f-186">In questa sezione si creeranno trigger di proprietà e trigger di evento per modificare i valori delle proprietà ed eseguire animazioni in risposta alle azioni dell'utente, ad esempio lo spostamento del puntatore del mouse sul pulsante e sulla selezione.</span><span class="sxs-lookup"><span data-stu-id="2e87f-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>

<span data-ttu-id="2e87f-187">Un modo semplice per aggiungere interattività (passaggio del mouse, uscita dal mouse, clic e così via) consiste nel definire i trigger all'interno del modello o dello stile.</span><span class="sxs-lookup"><span data-stu-id="2e87f-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="2e87f-188">Per creare un <xref:System.Windows.Trigger>oggetto, definire una proprietà "Condition", ad esempio: Il valore <xref:System.Windows.UIElement.IsMouseOver%2A> della proprietà del pulsante è `true`uguale a.</span><span class="sxs-lookup"><span data-stu-id="2e87f-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="2e87f-189">Si definiscono quindi i setter (azioni) che avvengono quando la condizione del trigger è true.</span><span class="sxs-lookup"><span data-stu-id="2e87f-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>

### <a name="to-create-button-interactivity"></a><span data-ttu-id="2e87f-190">Per creare l'interattività di un pulsante</span><span class="sxs-lookup"><span data-stu-id="2e87f-190">To create button interactivity</span></span>

1. <span data-ttu-id="2e87f-191">**Aggiungere trigger di modello:** Aggiungere il markup evidenziato al modello.</span><span class="sxs-lookup"><span data-stu-id="2e87f-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>

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

2. <span data-ttu-id="2e87f-192">**Aggiungere trigger di proprietà:** Aggiungere il markup evidenziato al `ControlTemplate.Triggers` blocco:</span><span class="sxs-lookup"><span data-stu-id="2e87f-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     <span data-ttu-id="2e87f-193">Premere F5 per eseguire l'applicazione e visualizzare l'effetto quando si esegue il puntatore del mouse sui pulsanti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>

3. <span data-ttu-id="2e87f-194">**Aggiungere un trigger di attivazione:** Successivamente, verranno aggiunti alcuni setter simili per gestire il caso in cui il pulsante ha lo stato attivo, ad esempio dopo che l'utente ha fatto clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="2e87f-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>

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

     <span data-ttu-id="2e87f-195">Premere F5 per eseguire l'applicazione e fare clic su uno dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="2e87f-196">Si noti che il pulsante rimane evidenziato dopo aver fatto clic su di esso perché ha ancora lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="2e87f-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="2e87f-197">Se si fa clic su un altro pulsante, il pulsante nuovo acquisisce lo stato attivo mentre l'ultimo lo perde.</span><span class="sxs-lookup"><span data-stu-id="2e87f-197">If you click another button, the new button gains focus while the last one loses it.</span></span>

4. <span data-ttu-id="2e87f-198">**Aggiungere animazioni per** <xref:System.Windows.UIElement.MouseEnter> e **:** <xref:System.Windows.UIElement.MouseLeave>   Successivamente, si aggiungono alcune animazioni ai trigger.</span><span class="sxs-lookup"><span data-stu-id="2e87f-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="2e87f-199">Aggiungere il markup seguente in qualsiasi punto all' `ControlTemplate.Triggers` interno del blocco.</span><span class="sxs-lookup"><span data-stu-id="2e87f-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>

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

     <span data-ttu-id="2e87f-200">Il rettangolo di cristallo viene compattato quando il puntatore del mouse viene spostato sul pulsante e torna alla dimensione normale quando il puntatore viene lasciato.</span><span class="sxs-lookup"><span data-stu-id="2e87f-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>

     <span data-ttu-id="2e87f-201">Ci sono due animazioni che vengono attivate quando il puntatore viene posizionato sul pulsante (<xref:System.Windows.UIElement.MouseEnter> viene generato l'evento).</span><span class="sxs-lookup"><span data-stu-id="2e87f-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="2e87f-202">Queste animazioni compattano il rettangolo vetro lungo l'asse X e Y.</span><span class="sxs-lookup"><span data-stu-id="2e87f-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="2e87f-203">Si notino le proprietà <xref:System.Windows.Media.Animation.DoubleAnimation> degli elementi <xref:System.Windows.Media.Animation.Timeline.Duration%2A> , <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>e.</span><span class="sxs-lookup"><span data-stu-id="2e87f-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="2e87f-204">Specifica che l'animazione viene eseguita oltre mezzo secondo e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifica che il vetro viene compattato del 10%. <xref:System.Windows.Media.Animation.Timeline.Duration%2A></span><span class="sxs-lookup"><span data-stu-id="2e87f-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>

     <span data-ttu-id="2e87f-205">Il secondo trigger di evento<xref:System.Windows.UIElement.MouseLeave>() arresta semplicemente la prima.</span><span class="sxs-lookup"><span data-stu-id="2e87f-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="2e87f-206">Quando si arresta un <xref:System.Windows.Media.Animation.Storyboard>oggetto, tutte le proprietà animate restituiscono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="2e87f-207">Pertanto, quando l'utente sposta il puntatore del mouse sul pulsante, il pulsante Torna al modo in cui si trovava prima che il puntatore del mouse venisse spostato sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="2e87f-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="2e87f-208">Per ulteriori informazioni sulle animazioni, vedere [Cenni preliminari sull'animazione](../graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2e87f-208">For more information about animations, see [Animation Overview](../graphics-multimedia/animation-overview.md).</span></span>

5. <span data-ttu-id="2e87f-209">**Aggiungere un'animazione per quando si fa clic sul pulsante:** Il passaggio finale consiste nell'aggiungere un trigger per quando l'utente fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="2e87f-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="2e87f-210">Aggiungere il markup seguente in qualsiasi punto all' `ControlTemplate.Triggers` interno del blocco:</span><span class="sxs-lookup"><span data-stu-id="2e87f-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>

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

     <span data-ttu-id="2e87f-211">Premere F5 per eseguire l'applicazione e fare clic su uno dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="2e87f-212">Quando si fa clic su un pulsante, il rettangolo di vetro ruota intorno.</span><span class="sxs-lookup"><span data-stu-id="2e87f-212">When you click a button, the glass rectangle spins around.</span></span>

## <a name="summary"></a><span data-ttu-id="2e87f-213">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="2e87f-213">Summary</span></span>
 <span data-ttu-id="2e87f-214">In questa procedura dettagliata sono stati eseguiti gli esercizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e87f-214">In this walkthrough, you performed the following exercises:</span></span>

- <span data-ttu-id="2e87f-215">Destinata <xref:System.Windows.Style> a un tipo di oggetto<xref:System.Windows.Controls.Button>().</span><span class="sxs-lookup"><span data-stu-id="2e87f-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>

- <span data-ttu-id="2e87f-216">Proprietà di base controllate dei pulsanti nell'intera applicazione usando <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="2e87f-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>

- <span data-ttu-id="2e87f-217">Risorse create come le sfumature da usare per i valori delle <xref:System.Windows.Style> proprietà dei setter.</span><span class="sxs-lookup"><span data-stu-id="2e87f-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>

- <span data-ttu-id="2e87f-218">Personalizzare l'aspetto dei pulsanti nell'intera applicazione applicando un modello ai pulsanti.</span><span class="sxs-lookup"><span data-stu-id="2e87f-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>

- <span data-ttu-id="2e87f-219">Comportamento personalizzato per i pulsanti in risposta alle azioni dell'utente <xref:System.Windows.UIElement.MouseEnter>, ad esempio, <xref:System.Windows.UIElement.MouseLeave>e <xref:System.Windows.Controls.Primitives.ButtonBase.Click>, che includevano gli effetti di animazione.</span><span class="sxs-lookup"><span data-stu-id="2e87f-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e87f-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e87f-220">See also</span></span>

- [<span data-ttu-id="2e87f-221">Creare un pulsante usando Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="2e87f-221">Create a Button by Using Microsoft Expression Blend</span></span>](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [<span data-ttu-id="2e87f-222">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="2e87f-222">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="2e87f-223">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="2e87f-223">Animation Overview</span></span>](../graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="2e87f-224">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="2e87f-224">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="2e87f-225">Panoramica sugli effetti bitmap</span><span class="sxs-lookup"><span data-stu-id="2e87f-225">Bitmap Effects Overview</span></span>](../graphics-multimedia/bitmap-effects-overview.md)
