---
title: 'Procedura dettagliata: creazione di un pulsante tramite XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: 96d54efbabbd95a24f1fb7118305ddbff4dfd110
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415824"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a><span data-ttu-id="d4a19-102">Procedura dettagliata: creazione di un pulsante tramite XAML</span><span class="sxs-lookup"><span data-stu-id="d4a19-102">Walkthrough: Create a Button by Using XAML</span></span>
<span data-ttu-id="d4a19-103">L'obiettivo di questa procedura dettagliata consiste nel comprendere come creare un pulsante animato per l'uso in un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="d4a19-103">The objective of this walkthrough is to learn how to create an animated button for use in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="d4a19-104">Questa procedura dettagliata Usa stili e un modello per creare una risorsa pulsante personalizzato che consente il riutilizzo del codice e la separazione della logica di pulsante dalla dichiarazione del pulsante.</span><span class="sxs-lookup"><span data-stu-id="d4a19-104">This walkthrough uses styles and a template to create a customized button resource that allows reuse of code and separation of button logic from the button declaration.</span></span> <span data-ttu-id="d4a19-105">Questa procedura dettagliata viene scritta interamente in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4a19-105">This walkthrough is written entirely in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d4a19-106">Questa procedura dettagliata descrive i passaggi per creare l'applicazione digitando o copiando e incollando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] in Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d4a19-106">This walkthrough guides you through the steps for creating the application by typing or copying and pasting [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] into Microsoft Visual Studio.</span></span> <span data-ttu-id="d4a19-107">Se si preferisce imparare a usare uno strumento di progettazione (Microsoft Expression Blend) per creare la stessa applicazione, vedere [creare un pulsante by Using Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span><span class="sxs-lookup"><span data-stu-id="d4a19-107">If you would prefer to learn how to use a design tool (Microsoft Expression Blend) to create the same application, see [Create a Button by Using Microsoft Expression Blend](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md).</span></span>  
  
 <span data-ttu-id="d4a19-108">Nella figura seguente mostra i pulsanti completati.</span><span class="sxs-lookup"><span data-stu-id="d4a19-108">The following figure shows the finished buttons.</span></span>  
  
 <span data-ttu-id="d4a19-109">![Pulsanti personalizzati che sono stati creati tramite XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="d4a19-109">![Custom buttons that were created by using XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-basic-buttons"></a><span data-ttu-id="d4a19-110">Creare pulsanti di base</span><span class="sxs-lookup"><span data-stu-id="d4a19-110">Create Basic Buttons</span></span>  
 <span data-ttu-id="d4a19-111">Iniziamo creando un nuovo progetto e aggiungere alcuni pulsanti alla finestra.</span><span class="sxs-lookup"><span data-stu-id="d4a19-111">Let's start by creating a new project and adding a few buttons to the window.</span></span>  
  
#### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a><span data-ttu-id="d4a19-112">Per creare un nuovo progetto WPF e aggiungere i pulsanti alla finestra</span><span class="sxs-lookup"><span data-stu-id="d4a19-112">To create a new WPF project and add buttons to the window</span></span>  
  
1.  <span data-ttu-id="d4a19-113">Avviare Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d4a19-113">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d4a19-114">**Creare un nuovo progetto WPF:** sul **File** dal menu **New**, quindi fare clic su **progetto**.</span><span class="sxs-lookup"><span data-stu-id="d4a19-114">**Create a new WPF project:** On the **File** menu, point to **New**, and then click **Project**.</span></span> <span data-ttu-id="d4a19-115">Trovare il **applicazione di Windows (WPF)** modello e il nome del progetto "AnimatedButton".</span><span class="sxs-lookup"><span data-stu-id="d4a19-115">Find the **Windows Application (WPF)** template and name the project "AnimatedButton".</span></span> <span data-ttu-id="d4a19-116">Verrà creata la struttura per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4a19-116">This will create the skeleton for the application.</span></span>  
  
3.  <span data-ttu-id="d4a19-117">**Aggiungere i pulsanti predefiniti di base:** tutti i file necessari per questa procedura dettagliata vengono forniti dal modello.</span><span class="sxs-lookup"><span data-stu-id="d4a19-117">**Add basic default buttons:** All the files you need for this walkthrough are provided by the template.</span></span> <span data-ttu-id="d4a19-118">Aprire il file Window1.xaml facendo doppio clic su di esso in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="d4a19-118">Open the Window1.xaml file by double clicking it in Solution Explorer.</span></span> <span data-ttu-id="d4a19-119">Per impostazione predefinita, è presente un <xref:System.Windows.Controls.Grid> elemento in Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="d4a19-119">By default, there is a <xref:System.Windows.Controls.Grid> element in Window1.xaml.</span></span> <span data-ttu-id="d4a19-120">Rimuovere il <xref:System.Windows.Controls.Grid> elemento e aggiungere alcuni pulsanti per la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pagina digitando o copiando e incollando il seguente codice evidenziato in Window1.xaml:</span><span class="sxs-lookup"><span data-stu-id="d4a19-120">Remove the <xref:System.Windows.Controls.Grid> element and add a few buttons to the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page by typing or copy and pasting the following highlighted code to Window1.xaml:</span></span>  
  
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
  
     <span data-ttu-id="d4a19-121">Premere F5 per eseguire l'applicazione. si dovrebbe visualizzare un set di pulsanti che è simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="d4a19-121">Press F5 to run the application; you should see a set of buttons that looks like the following figure.</span></span>  
  
     <span data-ttu-id="d4a19-122">![Tre pulsanti di base](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span><span class="sxs-lookup"><span data-stu-id="d4a19-122">![Three basic buttons](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")</span></span>  
  
     <span data-ttu-id="d4a19-123">Dopo avere creato i pulsanti di base, desidera eseguire altre operazioni nel file Window1.xaml.</span><span class="sxs-lookup"><span data-stu-id="d4a19-123">Now that you have created the basic buttons, you are finished working in the Window1.xaml file.</span></span> <span data-ttu-id="d4a19-124">Il resto della procedura dettagliata si concentra sul file app. XAML, la definizione di stili e un modello per i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="d4a19-124">The rest of the walkthrough focuses on the app.xaml file, defining styles and a template for the buttons.</span></span>  
  
## <a name="set-basic-properties"></a><span data-ttu-id="d4a19-125">Impostare le proprietà di base</span><span class="sxs-lookup"><span data-stu-id="d4a19-125">Set Basic Properties</span></span>  
 <span data-ttu-id="d4a19-126">Successivamente, è possibile impostare alcune proprietà dei pulsanti per controllare l'aspetto del pulsante e il layout.</span><span class="sxs-lookup"><span data-stu-id="d4a19-126">Next, let's set some properties on these buttons to control the button appearance and layout.</span></span> <span data-ttu-id="d4a19-127">Anziché impostare le proprietà sui pulsanti singolarmente, si userà le risorse per definire proprietà dei pulsanti per l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4a19-127">Rather than setting properties on the buttons individually, you will use resources to define button properties for the entire application.</span></span> <span data-ttu-id="d4a19-128">Le risorse dell'applicazione sono concettualmente simili a esterno [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] per le pagine Web; tuttavia, le risorse sono molto più potenti [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], come verrà visualizzato al termine di questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="d4a19-128">Application resources are conceptually similar to external [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)] for Web pages; however, resources are much more powerful than [!INCLUDE[TLA#tla_css](../../../../includes/tlasharptla-css-md.md)], as you will see by the end of this walkthrough.</span></span> <span data-ttu-id="d4a19-129">Per altre informazioni sulle risorse, vedere [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="d4a19-129">To learn more about resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
#### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a><span data-ttu-id="d4a19-130">Come utilizzare gli stili per impostare le proprietà di base sui pulsanti</span><span class="sxs-lookup"><span data-stu-id="d4a19-130">To use styles to set basic properties on the buttons</span></span>  
  
1.  <span data-ttu-id="d4a19-131">**Definire un blocco di Resources:** aprire l'app. XAML e aggiungere il markup evidenziato seguente se non è già presente:</span><span class="sxs-lookup"><span data-stu-id="d4a19-131">**Define an Application.Resources block:** Open app.xaml and add the following highlighted markup if it is not already there:</span></span>  
  
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
  
     <span data-ttu-id="d4a19-132">Ambito di risorse è determinato da in cui si definisce la risorsa.</span><span class="sxs-lookup"><span data-stu-id="d4a19-132">Resource scope is determined by where you define the resource.</span></span> <span data-ttu-id="d4a19-133">Definizione delle risorse in `Application.Resources` nell'app. XAML file consente la risorsa essere utilizzato da un punto qualsiasi nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4a19-133">Defining resources in `Application.Resources` in the app.xaml file enables the resource to be used from anywhere in the application.</span></span> <span data-ttu-id="d4a19-134">Per altre informazioni sulla definizione dell'ambito delle risorse, vedere [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="d4a19-134">To learn more about defining the scope of your resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
2.  <span data-ttu-id="d4a19-135">**Creare uno stile e definire i valori delle proprietà di base:** aggiungere il markup seguente per il `Application.Resources` blocco.</span><span class="sxs-lookup"><span data-stu-id="d4a19-135">**Create a style and define basic property values with it:** Add the following markup to the `Application.Resources` block.</span></span> <span data-ttu-id="d4a19-136">Questo codice crea un <xref:System.Windows.Style> che si applica a tutti i pulsanti nell'applicazione, impostare il <xref:System.Windows.FrameworkElement.Width%2A> dei pulsanti per 90 e il <xref:System.Windows.FrameworkElement.Margin%2A> a 10:</span><span class="sxs-lookup"><span data-stu-id="d4a19-136">This markup creates a <xref:System.Windows.Style> that applies to all buttons in the application, setting the <xref:System.Windows.FrameworkElement.Width%2A> of the buttons to 90 and the <xref:System.Windows.FrameworkElement.Margin%2A> to 10:</span></span>  
  
    ```xaml  
    <Application.Resources>  
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>  
    </Application.Resources>  
    ```  
  
     <span data-ttu-id="d4a19-137">Il <xref:System.Windows.Style.TargetType%2A> proprietà specifica che lo stile applicato a tutti gli oggetti di tipo <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="d4a19-137">The <xref:System.Windows.Style.TargetType%2A> property specifies that the style applies to all objects of type <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="d4a19-138">Ciascuna <xref:System.Windows.Setter> imposta un valore di proprietà diversi per il <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="d4a19-138">Each <xref:System.Windows.Setter> sets a different property value for the <xref:System.Windows.Style>.</span></span> <span data-ttu-id="d4a19-139">Pertanto, a questo punto ogni pulsante nell'applicazione abbia una larghezza pari a 90 e un margine di 10.</span><span class="sxs-lookup"><span data-stu-id="d4a19-139">Therefore, at this point every button in the application has a width of 90 and a margin of 10.</span></span>  <span data-ttu-id="d4a19-140">Se si preme F5 per eseguire l'applicazione, viene visualizzata la finestra seguente.</span><span class="sxs-lookup"><span data-stu-id="d4a19-140">If you press F5 to run the application, you see the following window.</span></span>  
  
     <span data-ttu-id="d4a19-141">![Pulsanti di una larghezza pari a 90, con un margine di 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span><span class="sxs-lookup"><span data-stu-id="d4a19-141">![Buttons with a width of 90 and a margin of 10](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")</span></span>  
  
     <span data-ttu-id="d4a19-142">È molto più che è possibile eseguire con gli stili, inclusi un'ampia gamma di modi per ottimizzare gli oggetti che vengono considerati come destinazione, specificando i valori di proprietà complessa e anche utilizzati come input per altri stili.</span><span class="sxs-lookup"><span data-stu-id="d4a19-142">There is much more you can do with styles, including a variety of ways to fine-tune what objects are targeted, specifying complex property values, and even using styles as input for other styles.</span></span> <span data-ttu-id="d4a19-143">Per altre informazioni, vedere [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="d4a19-143">For more information, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
3.  <span data-ttu-id="d4a19-144">**Impostare il valore di una proprietà di stile a una risorsa:** grazie alle risorse in modo semplice riutilizzare i valori e oggetti comunemente definiti.</span><span class="sxs-lookup"><span data-stu-id="d4a19-144">**Set a style property value to a resource:** Resources enable a simple way to reuse commonly defined objects and values.</span></span> <span data-ttu-id="d4a19-145">È particolarmente utile definire valori complessi usando le risorse per rendere più modulare il codice.</span><span class="sxs-lookup"><span data-stu-id="d4a19-145">It is especially useful to define complex values using resources to make your code more modular.</span></span> <span data-ttu-id="d4a19-146">Aggiungere il markup evidenziato seguente a app. Xaml.</span><span class="sxs-lookup"><span data-stu-id="d4a19-146">Add the following highlighted markup to app.xaml.</span></span>  
  
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
  
     <span data-ttu-id="d4a19-147">Direttamente sotto il `Application.Resources` blocco, è stata creata una risorsa denominata "GrayBlueGradientBrush".</span><span class="sxs-lookup"><span data-stu-id="d4a19-147">Directly under the `Application.Resources` block, you created a resource called "GrayBlueGradientBrush".</span></span> <span data-ttu-id="d4a19-148">Risorsa che definisce una sfumatura orizzontale.</span><span class="sxs-lookup"><span data-stu-id="d4a19-148">This resource defines a horizontal gradient.</span></span> <span data-ttu-id="d4a19-149">Questa risorsa può essere utilizzata come valore della proprietà da qualsiasi posizione nell'applicazione, anche all'interno di setter di stile pulsante per la <xref:System.Windows.Controls.Control.Background%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="d4a19-149">This resource can be used as a property value from anywhere in the application, including inside the button style setter for the <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="d4a19-150">A questo punto, tutti i pulsanti hanno un <xref:System.Windows.Controls.Control.Background%2A> valore della proprietà di questo tipo di sfumatura.</span><span class="sxs-lookup"><span data-stu-id="d4a19-150">Now, all the buttons have a <xref:System.Windows.Controls.Control.Background%2A> property value of this gradient.</span></span>  
  
     <span data-ttu-id="d4a19-151">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4a19-151">Press F5 to run the application.</span></span> <span data-ttu-id="d4a19-152">Dovrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="d4a19-152">It should look like the following.</span></span>  
  
     <span data-ttu-id="d4a19-153">![I pulsanti con uno sfondo sfumato](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span><span class="sxs-lookup"><span data-stu-id="d4a19-153">![Buttons with a gradient background](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")</span></span>  
  
## <a name="create-a-template-that-defines-the-look-of-the-button"></a><span data-ttu-id="d4a19-154">Creare un modello che definisce l'aspetto del pulsante</span><span class="sxs-lookup"><span data-stu-id="d4a19-154">Create a Template That Defines the Look of the Button</span></span>  
 <span data-ttu-id="d4a19-155">In questa sezione creare un modello che consente di personalizzare l'aspetto (presentazione) del pulsante.</span><span class="sxs-lookup"><span data-stu-id="d4a19-155">In this section, you create a template that customizes the appearance (presentation) of the button.</span></span> <span data-ttu-id="d4a19-156">La presentazione del pulsante è costituita da oggetti diversi tra cui rettangoli e altri componenti per conferire un aspetto univoco al pulsante.</span><span class="sxs-lookup"><span data-stu-id="d4a19-156">The button presentation is made up of several objects including rectangles and other components to give the button a unique look.</span></span>  
  
 <span data-ttu-id="d4a19-157">Finora, il controllo dell'aspetto di pulsanti nell'applicazione è stato limitato alla modifica delle proprietà del pulsante.</span><span class="sxs-lookup"><span data-stu-id="d4a19-157">So far, the control of how buttons look in the application has been confined to changing properties of the button.</span></span> <span data-ttu-id="d4a19-158">Cosa accade se si desidera apportare modifiche più radicali all'aspetto del pulsante?</span><span class="sxs-lookup"><span data-stu-id="d4a19-158">What if you want to make more radical changes to the button's appearance?</span></span> <span data-ttu-id="d4a19-159">I modelli consentono un controllo sulla presentazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="d4a19-159">Templates enable powerful control over the presentation of an object.</span></span> <span data-ttu-id="d4a19-160">Poiché i modelli possono essere utilizzati all'interno degli stili, è possibile applicare un modello a tutti gli oggetti che lo stile applicato alla (in questa procedura dettagliata, il pulsante).</span><span class="sxs-lookup"><span data-stu-id="d4a19-160">Because templates can be used within styles, you can apply a template to all objects that the style applies to (in this walkthrough, the button).</span></span>  
  
#### <a name="to-use-the-template-to-define-the-look-of-the-button"></a><span data-ttu-id="d4a19-161">Usare il modello per definire l'aspetto del pulsante</span><span class="sxs-lookup"><span data-stu-id="d4a19-161">To use the template to define the look of the button</span></span>  
  
1.  <span data-ttu-id="d4a19-162">**Configurare il modello:** poiché i controlli come <xref:System.Windows.Controls.Button> hanno una <xref:System.Windows.Controls.Control.Template%2A> proprietà, è possibile definire il valore della proprietà modello proprio come gli altri valori di proprietà è stato impostato in un <xref:System.Windows.Style> usando un <xref:System.Windows.Setter>.</span><span class="sxs-lookup"><span data-stu-id="d4a19-162">**Set up the template:** Because controls like <xref:System.Windows.Controls.Button> have a <xref:System.Windows.Controls.Control.Template%2A> property, you can define the template property value just like the other property values we have set in a <xref:System.Windows.Style> using a <xref:System.Windows.Setter>.</span></span> <span data-ttu-id="d4a19-163">Aggiungere il markup evidenziato seguente allo stile del pulsante.</span><span class="sxs-lookup"><span data-stu-id="d4a19-163">Add the following highlighted markup to your button style.</span></span>  
  
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
  
2.  <span data-ttu-id="d4a19-164">**Presentazione del pulsante di ALTER:** a questo punto, è necessario definire il modello.</span><span class="sxs-lookup"><span data-stu-id="d4a19-164">**Alter button presentation:** At this point, you need to define the template.</span></span> <span data-ttu-id="d4a19-165">Aggiungere il markup evidenziato seguente.</span><span class="sxs-lookup"><span data-stu-id="d4a19-165">Add the following highlighted markup.</span></span> <span data-ttu-id="d4a19-166">Questo markup specifica due <xref:System.Windows.Shapes.Rectangle> elementi con gli angoli arrotondati, seguito da un <xref:System.Windows.Controls.DockPanel>.</span><span class="sxs-lookup"><span data-stu-id="d4a19-166">This markup specifies two <xref:System.Windows.Shapes.Rectangle> elements with rounded edges, followed by a <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="d4a19-167">Il <xref:System.Windows.Controls.DockPanel> viene usato per ospitare il <xref:System.Windows.Controls.ContentPresenter> del pulsante.</span><span class="sxs-lookup"><span data-stu-id="d4a19-167">The <xref:System.Windows.Controls.DockPanel> is used to host the <xref:System.Windows.Controls.ContentPresenter> of the button.</span></span> <span data-ttu-id="d4a19-168">Oggetto <xref:System.Windows.Controls.ContentPresenter> consente di visualizzare il contenuto del pulsante.</span><span class="sxs-lookup"><span data-stu-id="d4a19-168">A <xref:System.Windows.Controls.ContentPresenter> displays the content of the button.</span></span> <span data-ttu-id="d4a19-169">In questa procedura dettagliata, il contenuto è testo ("Pulsante 1", "Pulsante 2", "Pulsante 3").</span><span class="sxs-lookup"><span data-stu-id="d4a19-169">In this walkthrough, the content is text ("Button 1", "Button 2", "Button 3").</span></span> <span data-ttu-id="d4a19-170">Tutti i componenti del modello (i rettangoli e le <xref:System.Windows.Controls.DockPanel>) sono disposte all'interno di un <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="d4a19-170">All of the template components (the rectangles and the <xref:System.Windows.Controls.DockPanel>) are laid out inside of a <xref:System.Windows.Controls.Grid>.</span></span>  
  
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
  
     <span data-ttu-id="d4a19-171">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4a19-171">Press F5 to run the application.</span></span> <span data-ttu-id="d4a19-172">Dovrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="d4a19-172">It should look like the following.</span></span>  
  
     <span data-ttu-id="d4a19-173">![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span><span class="sxs-lookup"><span data-stu-id="d4a19-173">![](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-4.gif "custom_button_AnimatedButton_4")</span></span>  
  
3.  <span data-ttu-id="d4a19-174">**Aggiungere un effetto cristallo al modello:** successivamente si aggiungerà l'effetto cristallo.</span><span class="sxs-lookup"><span data-stu-id="d4a19-174">**Add a glasseffect to the template:** Next you will add the glass.</span></span> <span data-ttu-id="d4a19-175">È innanzitutto necessario creare alcune risorse che crea un effetto cristallo.</span><span class="sxs-lookup"><span data-stu-id="d4a19-175">First you create some resources that create a glass gradient effect.</span></span> <span data-ttu-id="d4a19-176">Aggiungere queste sfumature risorse in un punto qualsiasi all'interno di `Application.Resources` blocco:</span><span class="sxs-lookup"><span data-stu-id="d4a19-176">Add these gradient resources anywhere within the `Application.Resources` block:</span></span>  
  
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
  
     <span data-ttu-id="d4a19-177">Queste risorse vengono usate come il <xref:System.Windows.Shapes.Shape.Fill%2A> per un rettangolo che abbiamo inserito il <xref:System.Windows.Controls.Grid> del modello di pulsante.</span><span class="sxs-lookup"><span data-stu-id="d4a19-177">These resources are used as the <xref:System.Windows.Shapes.Shape.Fill%2A> for a rectangle that we insert into the <xref:System.Windows.Controls.Grid> of the button template.</span></span> <span data-ttu-id="d4a19-178">Aggiungere il markup evidenziato seguente al modello.</span><span class="sxs-lookup"><span data-stu-id="d4a19-178">Add the following highlighted markup to the template.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="d4a19-179">Si noti che il <xref:System.Windows.UIElement.Opacity%2A> del rettangolo con il `x:Name` proprietà di "glassCube" è 0, in modo che quando si esegue l'esempio, non viene visualizzato il rettangolo trasparente sovrapposto nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="d4a19-179">Notice that the <xref:System.Windows.UIElement.Opacity%2A> of the rectangle with the `x:Name` property of "glassCube" is 0, so when you run the sample, you do not see the glass rectangle overlaid on top.</span></span> <span data-ttu-id="d4a19-180">Questo avviene perché seguito verranno aggiunti i trigger per il modello per quando l'utente interagisce con il pulsante.</span><span class="sxs-lookup"><span data-stu-id="d4a19-180">This is because we will later add triggers to the template for when the user interacts with the button.</span></span> <span data-ttu-id="d4a19-181">Tuttavia, è possibile visualizzare il pulsante di come appare ora modificando il <xref:System.Windows.UIElement.Opacity%2A> valore su 1 e l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4a19-181">However, you can see what the button looks like now by changing the <xref:System.Windows.UIElement.Opacity%2A> value to 1 and running the application.</span></span> <span data-ttu-id="d4a19-182">Vedere la figura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="d4a19-182">See the following figure.</span></span> <span data-ttu-id="d4a19-183">Prima di procedere al passaggio successivo, cambiare il <xref:System.Windows.UIElement.Opacity%2A> nuovamente su 0.</span><span class="sxs-lookup"><span data-stu-id="d4a19-183">Before proceeding to the next step, change the <xref:System.Windows.UIElement.Opacity%2A> back to 0.</span></span>  
  
     <span data-ttu-id="d4a19-184">![Pulsanti personalizzati che sono stati creati tramite XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span><span class="sxs-lookup"><span data-stu-id="d4a19-184">![Custom buttons that were created by using XAML](../../../../docs/framework/wpf/controls/media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")</span></span>  
  
## <a name="create-button-interactivity"></a><span data-ttu-id="d4a19-185">Creare l'interattività del pulsante</span><span class="sxs-lookup"><span data-stu-id="d4a19-185">Create Button Interactivity</span></span>  
 <span data-ttu-id="d4a19-186">In questa sezione si creerà i trigger di proprietà e i trigger di evento per modificare i valori delle proprietà ed eseguire animazioni in risposta alle azioni dell'utente, ad esempio spostando il puntatore del mouse su esso e fare clic su.</span><span class="sxs-lookup"><span data-stu-id="d4a19-186">In this section, you will create property triggers and event triggers to change property values and run animations in response to user actions such as moving the mouse pointer over the button and clicking.</span></span>  
  
 <span data-ttu-id="d4a19-187">Un modo semplice per aggiungere interattività (puntatore del mouse, in uscita del mouse, fare clic e così via) consiste nel definire i trigger all'interno del modello o stile.</span><span class="sxs-lookup"><span data-stu-id="d4a19-187">An easy way to add interactivity (mouse-over, mouse-leave, click, and so on) is to define triggers within your template or style.</span></span> <span data-ttu-id="d4a19-188">Per creare un <xref:System.Windows.Trigger>, si definisce una proprietà "condition", ad esempio: il pulsante <xref:System.Windows.UIElement.IsMouseOver%2A> è uguale al valore della proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="d4a19-188">To create a <xref:System.Windows.Trigger>, you define a property "condition" such as: The button <xref:System.Windows.UIElement.IsMouseOver%2A> property value is equal to `true`.</span></span> <span data-ttu-id="d4a19-189">È quindi possibile definire metodi di impostazione (azioni) che si verificano quando viene soddisfatta la condizione del trigger.</span><span class="sxs-lookup"><span data-stu-id="d4a19-189">You then define setters (actions) that take place when the trigger condition is true.</span></span>  
  
#### <a name="to-create-button-interactivity"></a><span data-ttu-id="d4a19-190">Per creare interattività del pulsante</span><span class="sxs-lookup"><span data-stu-id="d4a19-190">To create button interactivity</span></span>  
  
1.  <span data-ttu-id="d4a19-191">**Aggiungere i trigger dei modelli:** aggiungere il markup evidenziato per il modello.</span><span class="sxs-lookup"><span data-stu-id="d4a19-191">**Add template triggers:** Add the highlighted markup to your template.</span></span>  
  
    ```  
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
  
2.  <span data-ttu-id="d4a19-192">**Aggiungere trigger di proprietà:** aggiungere il markup evidenziato per il `ControlTemplate.Triggers` blocco:</span><span class="sxs-lookup"><span data-stu-id="d4a19-192">**Add property triggers:** Add the highlighted markup to the `ControlTemplate.Triggers` block:</span></span>  
  
    ```  
    <ControlTemplate.Triggers>  
  
      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>  
  
    <ControlTemplate.Triggers/>  
    ```  
  
     <span data-ttu-id="d4a19-193">Premere F5 per eseguire l'applicazione e verificarne l'effetto quando si esegue il puntatore del mouse sui pulsanti.</span><span class="sxs-lookup"><span data-stu-id="d4a19-193">Press F5 to run the application and see the effect as you run the mouse pointer over the buttons.</span></span>  
  
3.  <span data-ttu-id="d4a19-194">**Aggiungere un trigger di messa a fuoco:** successivamente, verrà aggiunto alcuni metodi di impostazione per gestire il caso in cui il pulsante è attivo (ad esempio, dopo un clic dell'utente).</span><span class="sxs-lookup"><span data-stu-id="d4a19-194">**Add a focus trigger:** Next, we'll add some similar setters to handle the case when the button has focus (for example, after the user clicks it).</span></span>  
  
    ```  
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
  
     <span data-ttu-id="d4a19-195">Premere F5 per eseguire l'applicazione e fare clic su uno dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="d4a19-195">Press F5 to run the application and click on one of the buttons.</span></span> <span data-ttu-id="d4a19-196">Si noti che il pulsante rimane evidenziato dopo aver selezionato perché è ancora evidenziato.</span><span class="sxs-lookup"><span data-stu-id="d4a19-196">Notice that the button stays highlighted after you click it because it still has focus.</span></span> <span data-ttu-id="d4a19-197">Se si fa clic su un altro pulsante, il nuovo pulsante Ottiene lo stato attivo mentre il penultimo lo perde.</span><span class="sxs-lookup"><span data-stu-id="d4a19-197">If you click another button, the new button gains focus while the last one loses it.</span></span>  
  
4.  <span data-ttu-id="d4a19-198">**Aggiungere animazioni per** <xref:System.Windows.UIElement.MouseEnter> **e** <xref:System.Windows.UIElement.MouseLeave> **:** successivamente verranno aggiunte alcune animazioni per i trigger.</span><span class="sxs-lookup"><span data-stu-id="d4a19-198">**Add animations for**  <xref:System.Windows.UIElement.MouseEnter> **and** <xref:System.Windows.UIElement.MouseLeave> **:** Next we add some animations to the triggers.</span></span> <span data-ttu-id="d4a19-199">Aggiungere il markup seguente in un punto qualsiasi all'interno del `ControlTemplate.Triggers` blocco.</span><span class="sxs-lookup"><span data-stu-id="d4a19-199">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="d4a19-200">Quando il puntatore del mouse viene spostato su esso e che restituisce nuovamente alle dimensioni normali quando il puntatore esce, si riduce il rettangolo trasparente.</span><span class="sxs-lookup"><span data-stu-id="d4a19-200">The glass rectangle shrinks when the mouse pointer moves over the button and returns back to normal size when the pointer leaves.</span></span>  
  
     <span data-ttu-id="d4a19-201">Esistono due animazioni che vengono attivate quando il puntatore del mouse passa sul pulsante (<xref:System.Windows.UIElement.MouseEnter> viene generato l'evento).</span><span class="sxs-lookup"><span data-stu-id="d4a19-201">There are two animations that are triggered when the pointer goes over the button (<xref:System.Windows.UIElement.MouseEnter> event is raised).</span></span> <span data-ttu-id="d4a19-202">Queste animazioni compattare il rettangolo trasparente lungo l'asse X e Y.</span><span class="sxs-lookup"><span data-stu-id="d4a19-202">These animations shrink the glass rectangle along the X and Y axis.</span></span> <span data-ttu-id="d4a19-203">Si noti che le proprietà nel <xref:System.Windows.Media.Animation.DoubleAnimation> elementi, ovvero <xref:System.Windows.Media.Animation.Timeline.Duration%2A> e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4a19-203">Notice the properties on the <xref:System.Windows.Media.Animation.DoubleAnimation> elements — <xref:System.Windows.Media.Animation.Timeline.Duration%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.</span></span> <span data-ttu-id="d4a19-204">Il <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifica che l'animazione viene eseguita per mezzo secondo, e <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifica che l'effetto cristallo viene ridotto del 10%.</span><span class="sxs-lookup"><span data-stu-id="d4a19-204">The <xref:System.Windows.Media.Animation.Timeline.Duration%2A> specifies that the animation occurs over half a second, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> specifies that the glass shrinks by 10%.</span></span>  
  
     <span data-ttu-id="d4a19-205">Il secondo trigger evento (<xref:System.Windows.UIElement.MouseLeave>) interrompe semplicemente il primo.</span><span class="sxs-lookup"><span data-stu-id="d4a19-205">The second event trigger (<xref:System.Windows.UIElement.MouseLeave>) simply stops the first one.</span></span> <span data-ttu-id="d4a19-206">Quando si arresta un <xref:System.Windows.Media.Animation.Storyboard>, tutte le proprietà animate restituiscono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="d4a19-206">When you stop a <xref:System.Windows.Media.Animation.Storyboard>, all the animated properties return to their default values.</span></span> <span data-ttu-id="d4a19-207">Pertanto, quando l'utente sposta il puntatore del mouse dal pulsante, il pulsante Torna al modo in cui che si trovava prima di spostata il puntatore del mouse su esso.</span><span class="sxs-lookup"><span data-stu-id="d4a19-207">Therefore, when the user moves the pointer off the button, the button goes back to the way it was before the mouse pointer moved over the button.</span></span> <span data-ttu-id="d4a19-208">Per altre informazioni sulle animazioni, vedere [Cenni preliminari sull'animazione](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d4a19-208">For more information about animations, see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
5.  <span data-ttu-id="d4a19-209">**Aggiungere un'animazione quando si fa clic sul pulsante:** il passaggio finale consiste nell'aggiungere un trigger per quando l'utente fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="d4a19-209">**Add an animation for when the button is clicked:** The final step is to add a trigger for when the user clicks the button.</span></span> <span data-ttu-id="d4a19-210">Aggiungere il markup seguente in un punto qualsiasi all'interno del `ControlTemplate.Triggers` blocco:</span><span class="sxs-lookup"><span data-stu-id="d4a19-210">Add the following markup anywhere inside of the `ControlTemplate.Triggers` block:</span></span>  
  
    ```  
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
  
     <span data-ttu-id="d4a19-211">Premere F5 per eseguire l'applicazione, quindi fare clic su uno dei pulsanti.</span><span class="sxs-lookup"><span data-stu-id="d4a19-211">Press F5 to run the application, and click one of the buttons.</span></span> <span data-ttu-id="d4a19-212">Quando si fa clic su un pulsante, il rettangolo ruota.</span><span class="sxs-lookup"><span data-stu-id="d4a19-212">When you click a button, the glass rectangle spins around.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="d4a19-213">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="d4a19-213">Summary</span></span>  
 <span data-ttu-id="d4a19-214">In questa procedura dettagliata, sono stati eseguiti gli esercizi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d4a19-214">In this walkthrough, you performed the following exercises:</span></span>  
  
-   <span data-ttu-id="d4a19-215">Destinazione un <xref:System.Windows.Style> a un tipo di oggetto (<xref:System.Windows.Controls.Button>).</span><span class="sxs-lookup"><span data-stu-id="d4a19-215">Targeted a <xref:System.Windows.Style> to an object type (<xref:System.Windows.Controls.Button>).</span></span>  
  
-   <span data-ttu-id="d4a19-216">Controllare le proprietà di base dei pulsanti nell'intera applicazione usando il <xref:System.Windows.Style>.</span><span class="sxs-lookup"><span data-stu-id="d4a19-216">Controlled basic properties of the buttons in the entire application using the <xref:System.Windows.Style>.</span></span>  
  
-   <span data-ttu-id="d4a19-217">Creazione di risorse, ad esempio sfumature da usare per i valori della proprietà di <xref:System.Windows.Style> Setter.</span><span class="sxs-lookup"><span data-stu-id="d4a19-217">Created resources like gradients to use for property values of the <xref:System.Windows.Style> setters.</span></span>  
  
-   <span data-ttu-id="d4a19-218">Personalizzare l'aspetto dei pulsanti dell'intera applicazione applicando un modello per i pulsanti.</span><span class="sxs-lookup"><span data-stu-id="d4a19-218">Customized the look of buttons in the entire application by applying a template to the buttons.</span></span>  
  
-   <span data-ttu-id="d4a19-219">Personalizzare il comportamento dei pulsanti in risposta alle azioni dell'utente (ad esempio <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, e <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) che è includere gli effetti di animazione.</span><span class="sxs-lookup"><span data-stu-id="d4a19-219">Customized behavior for the buttons in response to user actions (such as <xref:System.Windows.UIElement.MouseEnter>, <xref:System.Windows.UIElement.MouseLeave>, and <xref:System.Windows.Controls.Primitives.ButtonBase.Click>) that included animation effects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a19-220">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4a19-220">See Also</span></span>  
 [<span data-ttu-id="d4a19-221">Creare un pulsante usando Microsoft Expression Blend</span><span class="sxs-lookup"><span data-stu-id="d4a19-221">Create a Button by Using Microsoft Expression Blend</span></span>](../../../../docs/framework/wpf/controls/walkthrough-create-a-button-by-using-microsoft-expression-blend.md)  
 [<span data-ttu-id="d4a19-222">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="d4a19-222">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d4a19-223">Cenni preliminari sull'animazione</span><span class="sxs-lookup"><span data-stu-id="d4a19-223">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="d4a19-224">Cenni sul disegno con colori a tinta unita e sfumature</span><span class="sxs-lookup"><span data-stu-id="d4a19-224">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="d4a19-225">Panoramica sugli effetti bitmap</span><span class="sxs-lookup"><span data-stu-id="d4a19-225">Bitmap Effects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/bitmap-effects-overview.md)
