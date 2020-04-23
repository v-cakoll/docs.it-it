---
title: Creare un modello in WPF - .NET Desktop
description: Informazioni su come creare e fare riferimento a un modello di controllo in Windows Presentation Foundation e .NET Core.Learn how to create and reference a control template in Windows Presentation Foundation and .NET Core.
author: thraka
ms.author: adegeo
ms.date: 11/15/2019
no-loc:
- <Window>
- <ControlTemplate>
- <Ellipse>
- <ContentPresenter>
- <Trigger>
- <Setter>
- <PropertyTrigger>
- <Grid>
- <VisualStateManager.VisualStateGroups>
- <VisualStateGroup>
- <VisualState>
- <Storyboard>
- SizeToContent
- MinWidth
- TargetType
- Title
helpviewer_keywords:
- control contract [WPF]
- controls [WPF], visual structure changes
- ControlTemplate [WPF], customizing for existing controls
- skinning controls [WPF]
- controls [WPF], appearance specified by state
- templates [WPF], custom for existing controls
ms.openlocfilehash: c901864d387b8de976bbfa9a9b3c14a7d5a0b4d8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2019
ms.locfileid: "82071248"
---
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="4c436-103">Creare un modello per un controlloCreate a template for a control</span><span class="sxs-lookup"><span data-stu-id="4c436-103">Create a template for a control</span></span>

<span data-ttu-id="4c436-104">Con Windows Presentation Foundation (WPF), è possibile personalizzare la struttura visiva e il comportamento di un controllo esistente con il proprio modello riutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="4c436-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="4c436-105">I modelli possono essere applicati globalmente all'applicazione, alle finestre e alle pagine o direttamente ai controlli.</span><span class="sxs-lookup"><span data-stu-id="4c436-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="4c436-106">La maggior parte degli scenari che richiedono la creazione di un nuovo controllo possono essere coperti creando invece un nuovo modello per un controllo esistente.</span><span class="sxs-lookup"><span data-stu-id="4c436-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="4c436-107">In questo articolo verrà esaminata <xref:System.Windows.Controls.ControlTemplate> la <xref:System.Windows.Controls.Button> creazione di una nuova per il controllo.</span><span class="sxs-lookup"><span data-stu-id="4c436-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="4c436-108">Quando creare un ControlTemplateWhen to create a ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="4c436-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="4c436-109">I controlli hanno molte <xref:System.Windows.Controls.Border.Background%2A> <xref:System.Windows.Controls.Control.Foreground%2A>proprietà, <xref:System.Windows.Controls.Control.FontFamily%2A>ad esempio , , e .</span><span class="sxs-lookup"><span data-stu-id="4c436-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="4c436-110">Queste proprietà controllano diversi aspetti dell'aspetto del controllo, ma le modifiche che è possibile apportare impostando queste proprietà sono limitate.</span><span class="sxs-lookup"><span data-stu-id="4c436-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="4c436-111">Ad esempio, è <xref:System.Windows.Controls.Control.Foreground%2A> possibile impostare <xref:System.Windows.Controls.Control.FontStyle%2A> la proprietà <xref:System.Windows.Controls.CheckBox>su blu e corsivo su un oggetto .</span><span class="sxs-lookup"><span data-stu-id="4c436-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="4c436-112">Quando si desidera personalizzare l'aspetto del controllo oltre a quanto l'impostazione delle altre proprietà del controllo, creare un <xref:System.Windows.Controls.ControlTemplate>oggetto .</span><span class="sxs-lookup"><span data-stu-id="4c436-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="4c436-113">Nella maggior parte delle interfacce utente, un pulsante ha lo stesso aspetto generale: un rettangolo con del testo.</span><span class="sxs-lookup"><span data-stu-id="4c436-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="4c436-114">Se si desidera creare un pulsante arrotondato, è possibile creare un nuovo controllo che eredita dal pulsante o ricrea la funzionalità del pulsante.</span><span class="sxs-lookup"><span data-stu-id="4c436-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="4c436-115">Inoltre, il nuovo controllo utente fornirebbe l'oggetto visivo circolare.</span><span class="sxs-lookup"><span data-stu-id="4c436-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="4c436-116">È possibile evitare di creare nuovi controlli personalizzando il layout visivo di un controllo esistente.</span><span class="sxs-lookup"><span data-stu-id="4c436-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="4c436-117">Con un pulsante arrotondato, si crea un <xref:System.Windows.Controls.ControlTemplate> con il layout visivo desiderato.</span><span class="sxs-lookup"><span data-stu-id="4c436-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="4c436-118">D'altra parte, se è necessario un controllo con nuove funzionalità, proprietà <xref:System.Windows.Controls.UserControl>diverse e nuove impostazioni, è necessario creare un nuovo file .</span><span class="sxs-lookup"><span data-stu-id="4c436-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c436-119">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4c436-119">Prerequisites</span></span>

<span data-ttu-id="4c436-120">Creare una nuova applicazione WPF WPF e in *MainWindow.xaml* (o un'altra finestra di propria scelta) impostare le proprietà seguenti nell'elemento \*\* \<>Window:\*\*</span><span class="sxs-lookup"><span data-stu-id="4c436-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

<span data-ttu-id="4c436-121">Impostare il \*\* \<\*\* contenuto dell'elemento>Window sul codice XAML seguente:</span><span class="sxs-lookup"><span data-stu-id="4c436-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="4c436-122">Alla fine, il file *MainWindow.xaml* dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4c436-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="4c436-123">Se si esegue l'applicazione, è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="4c436-123">If you run the application, it looks like the following:</span></span>

![Finestra WPF con due pulsanti senza stileWPF window with two unstyled buttons](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="4c436-125">Creare un ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="4c436-125">Create a ControlTemplate</span></span>

<span data-ttu-id="4c436-126">Il modo più comune <xref:System.Windows.Controls.ControlTemplate> per dichiarare un `Resources` è come risorsa nella sezione in un file XAML.</span><span class="sxs-lookup"><span data-stu-id="4c436-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="4c436-127">Poiché i modelli sono risorse, rispettano le stesse regole di ambito che si applicano a tutte le risorse.</span><span class="sxs-lookup"><span data-stu-id="4c436-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="4c436-128">In parole povere, in cui si dichiara un modello influisce sulla posizione in cui il modello può essere applicato.</span><span class="sxs-lookup"><span data-stu-id="4c436-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="4c436-129">Ad esempio, se si dichiara il modello nell'elemento radice del file XAML di definizione dell'applicazione, il modello può essere utilizzato in qualsiasi punto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4c436-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="4c436-130">Se si definisce il modello in una finestra, solo i controlli in tale finestra possono utilizzare il modello.</span><span class="sxs-lookup"><span data-stu-id="4c436-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="4c436-131">Per iniziare, aggiungi `Window.Resources` un elemento al file *MainWindow.xaml:*</span><span class="sxs-lookup"><span data-stu-id="4c436-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="4c436-132">Creare un nuovo \*\* \<controllo ControlTemplate>\*\* con le proprietà seguenti impostate:Create a new ControlTemplate>with the following properties set:</span><span class="sxs-lookup"><span data-stu-id="4c436-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="4c436-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="4c436-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="4c436-134">Questo modello di controllo sarà semplice:This control template will be simple:</span><span class="sxs-lookup"><span data-stu-id="4c436-134">This control template will be simple:</span></span>

- <span data-ttu-id="4c436-135">un elemento radice per il controllo, un<xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="4c436-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="4c436-136">an <xref:System.Windows.Shapes.Ellipse> per disegnare l'aspetto arrotondato del pulsante</span><span class="sxs-lookup"><span data-stu-id="4c436-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="4c436-137">a <xref:System.Windows.Controls.ContentPresenter> per visualizzare il contenuto del pulsante specificato dall'utente</span><span class="sxs-lookup"><span data-stu-id="4c436-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="4c436-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="4c436-138">TemplateBinding</span></span>

<span data-ttu-id="4c436-139">Quando si crea <xref:System.Windows.Controls.ControlTemplate>un nuovo oggetto , è comunque possibile utilizzare le proprietà pubbliche per modificare l'aspetto del controllo.</span><span class="sxs-lookup"><span data-stu-id="4c436-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="4c436-140">Il [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) estensione di markup associa una proprietà <xref:System.Windows.Controls.ControlTemplate> di un elemento che si trova in un a una proprietà pubblica definita dal controllo.</span><span class="sxs-lookup"><span data-stu-id="4c436-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="4c436-141">Quando si utilizza un [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), si abilitano le proprietà del controllo in modo che fungano da parametri per il modello.</span><span class="sxs-lookup"><span data-stu-id="4c436-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="4c436-142">Ovvero, quando si imposta una proprietà per un controllo, tale valore viene passato all'elemento che dispone del [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="4c436-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="4c436-143">Ellipse</span><span class="sxs-lookup"><span data-stu-id="4c436-143">Ellipse</span></span>

<span data-ttu-id="4c436-144">Si **:::no-loc text="Fill":::** noti **:::no-loc text="Stroke":::** che le proprietà e dell'elemento \*\* \<\*\* <xref:System.Windows.Controls.Control.Foreground> Ellipse>sono associate alle proprietà e <xref:System.Windows.Controls.Control.Background> del controllo.</span><span class="sxs-lookup"><span data-stu-id="4c436-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="4c436-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="4c436-145">ContentPresenter</span></span>

<span data-ttu-id="4c436-146">Un [ \<elemento ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) viene aggiunto anche al modello.</span><span class="sxs-lookup"><span data-stu-id="4c436-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="4c436-147">Poiché questo modello è progettato per un pulsante, prendere in considerazione che il pulsante eredita da <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="4c436-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="4c436-148">Il pulsante presenta il contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4c436-148">The button presents the content of the element.</span></span> <span data-ttu-id="4c436-149">È possibile impostare qualsiasi elemento all'interno del pulsante, ad esempio testo normale o anche un altro controllo.</span><span class="sxs-lookup"><span data-stu-id="4c436-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="4c436-150">Entrambi i pulsanti validi sono entrambi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="4c436-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="4c436-151">In entrambi gli esempi precedenti, il testo e la casella di controllo sono impostati come proprietà [Button.Content.](xref:System.Windows.Controls.ContentControl.Content)</span><span class="sxs-lookup"><span data-stu-id="4c436-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="4c436-152">Qualunque sia il contenuto può essere presentato tramite un \*\* \<ContentPresenter>\*\*, che è ciò che fa il modello.</span><span class="sxs-lookup"><span data-stu-id="4c436-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="4c436-153">Se <xref:System.Windows.Controls.ControlTemplate> l'oggetto <xref:System.Windows.Controls.ContentControl> viene applicato a `Button`un <xref:System.Windows.Controls.ContentPresenter> tipo, ad esempio un oggetto , viene eseguita la ricerca di a nella struttura ad albero dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4c436-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="4c436-154">Se `ContentPresenter` l'oggetto viene trovato, il modello <xref:System.Windows.Controls.ContentControl.Content> associa `ContentPresenter`automaticamente la proprietà del controllo all'oggetto .</span><span class="sxs-lookup"><span data-stu-id="4c436-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="4c436-155">Modello</span><span class="sxs-lookup"><span data-stu-id="4c436-155">Use the template</span></span>

<span data-ttu-id="4c436-156">Trovare i pulsanti dichiarati all'inizio di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="4c436-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="4c436-157">Impostare la proprietà <xref:System.Windows.Controls.Control.Template> del `roundbutton` secondo pulsante sulla risorsa:Set the second button's property to the resource:</span><span class="sxs-lookup"><span data-stu-id="4c436-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="4c436-158">Se si esegue il progetto e si guarda il risultato, si noterà che il pulsante ha uno sfondo arrotondato.</span><span class="sxs-lookup"><span data-stu-id="4c436-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![Finestra WPF con un pulsante ovale del modelloWPF window with one template oval button](media/create-apply-template/styled-button.png)

<span data-ttu-id="4c436-160">Avrete notato che il pulsante non è un cerchio, ma è inclinato.</span><span class="sxs-lookup"><span data-stu-id="4c436-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="4c436-161">A causa del funzionamento dell'elemento \*\* \<>Ellipse,\*\* si espande sempre per riempire lo spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="4c436-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="4c436-162">Rendere uniforme il cerchio modificando **:::no-loc text="width":::** le **:::no-loc text="height":::** proprietà e del pulsante sullo stesso valore:</span><span class="sxs-lookup"><span data-stu-id="4c436-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Finestra WPF con un pulsante circolare del modelloWPF window with one template circular button](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="4c436-164">Aggiungere un triggerAdd a Trigger</span><span class="sxs-lookup"><span data-stu-id="4c436-164">Add a Trigger</span></span>

<span data-ttu-id="4c436-165">Anche se un pulsante con un modello applicato ha un aspetto diverso, si comporta come qualsiasi altro pulsante.</span><span class="sxs-lookup"><span data-stu-id="4c436-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="4c436-166">Se si preme <xref:System.Windows.Controls.Primitives.ButtonBase.Click> il pulsante, viene generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="4c436-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="4c436-167">Tuttavia, avrete notato che quando si sposta il mouse sul pulsante, gli oggetti visivi del pulsante non cambiano.</span><span class="sxs-lookup"><span data-stu-id="4c436-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="4c436-168">Queste interazioni visive sono tutte definite dal modello.</span><span class="sxs-lookup"><span data-stu-id="4c436-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="4c436-169">Con i sistemi di proprietà e eventi dinamici forniti da WPFWPF, è possibile controllare una proprietà specifica per un valore e quindi ridefinire lo stile del modello quando appropriato.</span><span class="sxs-lookup"><span data-stu-id="4c436-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="4c436-170">In questo esempio, si guarderà <xref:System.Windows.UIElement.IsMouseOver> la proprietà del pulsante.</span><span class="sxs-lookup"><span data-stu-id="4c436-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="4c436-171">Quando il mouse si trova \*\* \<\*\* sopra il controllo, applicare uno stile al>Ellipse con un nuovo colore.</span><span class="sxs-lookup"><span data-stu-id="4c436-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="4c436-172">Questo tipo di trigger è noto come *PropertyTrigger*.</span><span class="sxs-lookup"><span data-stu-id="4c436-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="4c436-173">Affinché questo funzioni, è necessario aggiungere un nome al \*\* \<>Ellipse\*\* a cui è possibile fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="4c436-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="4c436-174">Assegnare il nome di **backgroundElement**.</span><span class="sxs-lookup"><span data-stu-id="4c436-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="4c436-175">Successivamente, aggiungere <xref:System.Windows.Trigger> un nuovo per il [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) insieme.</span><span class="sxs-lookup"><span data-stu-id="4c436-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="4c436-176">Il trigger guarderà l'evento `IsMouseOver` per il valore `true`.</span><span class="sxs-lookup"><span data-stu-id="4c436-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="4c436-177">Successivamente, aggiungere un \*\* \<>Setter\*\* al \*\* \<>Trigger\*\* che modifica il **Fill** proprietà del \*\* \<>Ellipse\*\* in un nuovo colore.</span><span class="sxs-lookup"><span data-stu-id="4c436-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="4c436-178">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="4c436-178">Run the project.</span></span> <span data-ttu-id="4c436-179">Si noti che quando si sposta il mouse sul pulsante, il colore \*\* \<dell'>Ellipse\*\* cambia.</span><span class="sxs-lookup"><span data-stu-id="4c436-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![il mouse si sposta sul pulsante WPF per modificare il colore di riempimento](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="4c436-181">Usare un VisualStateUse a VisualState</span><span class="sxs-lookup"><span data-stu-id="4c436-181">Use a VisualState</span></span>

<span data-ttu-id="4c436-182">Gli stati di visualizzazione vengono definiti e attivati da un controllo.</span><span class="sxs-lookup"><span data-stu-id="4c436-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="4c436-183">Ad esempio, quando il mouse viene spostato `CommonStates.MouseOver` sopra il controllo, lo stato viene attivato.</span><span class="sxs-lookup"><span data-stu-id="4c436-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="4c436-184">È possibile animare le modifiche delle proprietà in base allo stato corrente del controllo.</span><span class="sxs-lookup"><span data-stu-id="4c436-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="4c436-185">Nella sezione precedente, `IsMouseOver` un `true` \*\* \<>PropertyTrigger\*\* è stato utilizzato `AliceBlue` per modificare il primo piano del pulsante quando la proprietà era .</span><span class="sxs-lookup"><span data-stu-id="4c436-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="4c436-186">Creare invece uno stato di visualizzazione che anima la modifica di questo colore, fornendo una transizione uniforme.</span><span class="sxs-lookup"><span data-stu-id="4c436-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="4c436-187">Per ulteriori informazioni su *VisualStates*, vedere [Stili e modelli in WPF.](../fundamentals/styles-templates-overview.md#visual-states)</span><span class="sxs-lookup"><span data-stu-id="4c436-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="4c436-188">Per convertire il \*\* \<PropertyTrigger>\*\* in uno stato di visualizzazione animato, First, rimuovere il \*\* \<ControlTemplate.Triggers>elemento\*\* dal modello.</span><span class="sxs-lookup"><span data-stu-id="4c436-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="4c436-189">Successivamente, nella \*\* \<griglia>\*\* radice del modello di controllo, aggiungere il `CommonStates` \*\* \<VisualStateManager.VisualStateGroups>\*\* elemento con un \*\* \<VisualStateGroup>\*\* per .</span><span class="sxs-lookup"><span data-stu-id="4c436-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="4c436-190">Definire due `Normal` stati `MouseOver`e .</span><span class="sxs-lookup"><span data-stu-id="4c436-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="4c436-191">Tutte le animazioni definite in un \*\* \<VisualState>\*\* vengono applicate quando tale stato viene attivato.</span><span class="sxs-lookup"><span data-stu-id="4c436-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="4c436-192">Creare animazioni per ogni stato.</span><span class="sxs-lookup"><span data-stu-id="4c436-192">Create animations for each state.</span></span> <span data-ttu-id="4c436-193">Le animazioni vengono \*\* \<\*\* inserite all'interno di un Storyboard>elemento.</span><span class="sxs-lookup"><span data-stu-id="4c436-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="4c436-194">Per altre informazioni sugli storyboard, vedere [Cenni preliminari](../../framework/wpf/graphics-multimedia/storyboards-overview.md)sugli storyboard.</span><span class="sxs-lookup"><span data-stu-id="4c436-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="4c436-195">Normale</span><span class="sxs-lookup"><span data-stu-id="4c436-195">Normal</span></span>

  <span data-ttu-id="4c436-196">Questo stato anima il riempimento dell'ellisse, ripristinandolo nel colore del `Background` controllo.</span><span class="sxs-lookup"><span data-stu-id="4c436-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="4c436-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4c436-197">MouseOver</span></span>

  <span data-ttu-id="4c436-198">Questo stato aggiunge `Background` un'animazione al `Yellow`colore dell'ellisse su un nuovo colore: .</span><span class="sxs-lookup"><span data-stu-id="4c436-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="4c436-199">Il \*\* \<ControlTemplate>\*\* dovrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="4c436-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="4c436-200">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="4c436-200">Run the project.</span></span> <span data-ttu-id="4c436-201">Si noti che quando si sposta il mouse sul pulsante, il colore del \*\* \<Ellipse>\*\* aggiunge un'animazione.</span><span class="sxs-lookup"><span data-stu-id="4c436-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![il mouse si sposta sul pulsante WPF per modificare il colore di riempimento](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="4c436-203">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4c436-203">Next steps</span></span>

- [<span data-ttu-id="4c436-204">Creare uno stile per un controllo in WPFCreate a style for a control in WPFWPF</span><span class="sxs-lookup"><span data-stu-id="4c436-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="4c436-205">Stili e modelli in WPF</span><span class="sxs-lookup"><span data-stu-id="4c436-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="4c436-206">Panoramica delle risorse XAMLOverview of XAML Resources</span><span class="sxs-lookup"><span data-stu-id="4c436-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
