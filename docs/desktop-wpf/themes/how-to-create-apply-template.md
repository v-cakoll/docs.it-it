---
title: Creare un modello in WPF-desktop .NET
description: Informazioni su come creare e fare riferimento a un modello di controllo in Windows Presentation Foundation e .NET Core.
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
# <a name="create-a-template-for-a-control"></a><span data-ttu-id="d6024-103">Creare un modello per un controllo</span><span class="sxs-lookup"><span data-stu-id="d6024-103">Create a template for a control</span></span>

<span data-ttu-id="d6024-104">Con Windows Presentation Foundation (WPF), è possibile personalizzare la struttura visiva e il comportamento di un controllo esistente con un modello riutilizzabile.</span><span class="sxs-lookup"><span data-stu-id="d6024-104">With Windows Presentation Foundation (WPF), you can customize an existing control's visual structure and behavior with your own reusable template.</span></span> <span data-ttu-id="d6024-105">I modelli possono essere applicati a livello globale per l'applicazione, le finestre e le pagine o direttamente ai controlli.</span><span class="sxs-lookup"><span data-stu-id="d6024-105">Templates can be applied globally to your application, windows and pages, or directly to controls.</span></span> <span data-ttu-id="d6024-106">La maggior parte degli scenari che richiedono la creazione di un nuovo controllo può essere analizzata creando invece un nuovo modello per un controllo esistente.</span><span class="sxs-lookup"><span data-stu-id="d6024-106">Most scenarios that require you to create a new control can be covered by instead creating a new template for an existing control.</span></span>

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

<span data-ttu-id="d6024-107">In questo articolo si esaminerà la creazione di <xref:System.Windows.Controls.ControlTemplate> un nuovo <xref:System.Windows.Controls.Button> oggetto per il controllo.</span><span class="sxs-lookup"><span data-stu-id="d6024-107">In this article, you'll explore creating a new <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>

## <a name="when-to-create-a-controltemplate"></a><span data-ttu-id="d6024-108">Quando creare un oggetto ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d6024-108">When to create a ControlTemplate</span></span>

<span data-ttu-id="d6024-109">I controlli hanno molte proprietà, ad <xref:System.Windows.Controls.Border.Background%2A>esempio <xref:System.Windows.Controls.Control.Foreground%2A>, e <xref:System.Windows.Controls.Control.FontFamily%2A>.</span><span class="sxs-lookup"><span data-stu-id="d6024-109">Controls have many properties, such as <xref:System.Windows.Controls.Border.Background%2A>, <xref:System.Windows.Controls.Control.Foreground%2A>, and <xref:System.Windows.Controls.Control.FontFamily%2A>.</span></span> <span data-ttu-id="d6024-110">Queste proprietà controllano aspetti diversi dell'aspetto del controllo, ma le modifiche che è possibile apportare impostando queste proprietà sono limitate.</span><span class="sxs-lookup"><span data-stu-id="d6024-110">These properties control different aspects of the control's appearance, but the changes that you can make by setting these properties are limited.</span></span> <span data-ttu-id="d6024-111">Ad esempio, è possibile impostare la <xref:System.Windows.Controls.Control.Foreground%2A> proprietà su blu e <xref:System.Windows.Controls.Control.FontStyle%2A> su corsivo in un <xref:System.Windows.Controls.CheckBox>oggetto.</span><span class="sxs-lookup"><span data-stu-id="d6024-111">For example, you can set the <xref:System.Windows.Controls.Control.Foreground%2A> property to blue and <xref:System.Windows.Controls.Control.FontStyle%2A> to italic on a <xref:System.Windows.Controls.CheckBox>.</span></span> <span data-ttu-id="d6024-112">Quando si desidera personalizzare l'aspetto del controllo oltre a ciò che è possibile impostare per le altre proprietà del controllo, è necessario <xref:System.Windows.Controls.ControlTemplate>creare un oggetto.</span><span class="sxs-lookup"><span data-stu-id="d6024-112">When you want to customize the control's appearance beyond what setting the other properties on the control can do, you create a <xref:System.Windows.Controls.ControlTemplate>.</span></span>

<span data-ttu-id="d6024-113">Nella maggior parte delle interfacce utente, un pulsante ha lo stesso aspetto generale: un rettangolo con testo.</span><span class="sxs-lookup"><span data-stu-id="d6024-113">In most user interfaces, a button has the same general appearance: a rectangle with some text.</span></span> <span data-ttu-id="d6024-114">Se si desidera creare un pulsante arrotondato, è possibile creare un nuovo controllo che eredita dal pulsante o ricrea la funzionalità del pulsante.</span><span class="sxs-lookup"><span data-stu-id="d6024-114">If you wanted to create a rounded button, you could create a new control that inherits from the button or recreates the functionality of the button.</span></span> <span data-ttu-id="d6024-115">Inoltre, il nuovo controllo utente fornirebbe l'oggetto visivo circolare.</span><span class="sxs-lookup"><span data-stu-id="d6024-115">In addition, the new user control would provide the circular visual.</span></span>

<span data-ttu-id="d6024-116">È possibile evitare di creare nuovi controlli personalizzando il layout visivo di un controllo esistente.</span><span class="sxs-lookup"><span data-stu-id="d6024-116">You can avoid creating new controls by customizing the visual layout of an existing control.</span></span> <span data-ttu-id="d6024-117">Con un pulsante arrotondato è possibile creare <xref:System.Windows.Controls.ControlTemplate> un oggetto con il layout visivo desiderato.</span><span class="sxs-lookup"><span data-stu-id="d6024-117">With a rounded button, you create a <xref:System.Windows.Controls.ControlTemplate> with the desired visual layout.</span></span>

<span data-ttu-id="d6024-118">D'altra parte, se è necessario un controllo con nuove funzionalità, proprietà diverse e nuove impostazioni, creare un nuovo <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="d6024-118">On the other hand, if you need a control with new functionality, different properties, and new settings, you would create a new <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6024-119">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d6024-119">Prerequisites</span></span>

<span data-ttu-id="d6024-120">Creare una nuova applicazione WPF e in *MainWindow. XAML* (o in un'altra finestra di propria scelta) impostare le proprietà seguenti nell'elemento \*\* \<>della finestra\*\* :</span><span class="sxs-lookup"><span data-stu-id="d6024-120">Create a new WPF application and in *MainWindow.xaml* (or another window of your choice) set the following properties on the **\<Window>** element:</span></span>

|     |     |
| --- | --- |
| **[!OP.NO-LOC(Title)]**         | `Template Intro Sample` |
| **[!OP.NO-LOC(SizeToContent)]** | `WidthAndHeight` |
| **[!OP.NO-LOC(MinWidth)]**      | `250` |

<span data-ttu-id="d6024-121">Impostare il contenuto dell'elemento \*\* \<>della finestra\*\* sul seguente codice XAML:</span><span class="sxs-lookup"><span data-stu-id="d6024-121">Set the content of the **\<Window>** element to the following XAML:</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="d6024-122">Alla fine, il file *MainWindow. XAML* dovrebbe essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d6024-122">In the end, the *MainWindow.xaml* file should look similar to the following:</span></span>

[!code-xaml[InitialWhole](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#InitialWhole)]

<span data-ttu-id="d6024-123">Se si esegue l'applicazione, l'aspetto sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d6024-123">If you run the application, it looks like the following:</span></span>

![Finestra WPF con due pulsanti senza stile](media/create-apply-template/unstyled-button.png)

## <a name="create-a-controltemplate"></a><span data-ttu-id="d6024-125">Creare un ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d6024-125">Create a ControlTemplate</span></span>

<span data-ttu-id="d6024-126">Il modo più comune per dichiarare un <xref:System.Windows.Controls.ControlTemplate> è come una risorsa nella `Resources` sezione di un file XAML.</span><span class="sxs-lookup"><span data-stu-id="d6024-126">The most common way to declare a <xref:System.Windows.Controls.ControlTemplate> is as a resource in the `Resources` section in a XAML file.</span></span> <span data-ttu-id="d6024-127">Poiché i modelli sono risorse, rispettano le stesse regole di ambito che si applicano a tutte le risorse.</span><span class="sxs-lookup"><span data-stu-id="d6024-127">Because templates are resources, they obey the same scoping rules that apply to all resources.</span></span> <span data-ttu-id="d6024-128">Inserire semplicemente, dove si dichiara un modello influiscono sul punto in cui è possibile applicare il modello.</span><span class="sxs-lookup"><span data-stu-id="d6024-128">Put simply, where you declare a template affects where the template can be applied.</span></span> <span data-ttu-id="d6024-129">Se, ad esempio, si dichiara il modello nell'elemento radice del file XAML della definizione dell'applicazione, il modello può essere usato in qualsiasi punto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d6024-129">For example, if you declare the template in the root element of your application definition XAML file, the template can be used anywhere in your application.</span></span> <span data-ttu-id="d6024-130">Se si definisce il modello in una finestra, solo i controlli in tale finestra possono usare il modello.</span><span class="sxs-lookup"><span data-stu-id="d6024-130">If you define the template in a window, only the controls in that window can use the template.</span></span>

<span data-ttu-id="d6024-131">Per iniziare, aggiungere un `Window.Resources` elemento al file *MainWindow. XAML* :</span><span class="sxs-lookup"><span data-stu-id="d6024-131">To start with, add a `Window.Resources` element to your *MainWindow.xaml* file:</span></span>

[!code-xaml[WindowResStart](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window2.xaml#WindowResStart)]

<span data-ttu-id="d6024-132">Creare una nuova \*\* \<>ControlTemplate\*\* con le seguenti proprietà impostate:</span><span class="sxs-lookup"><span data-stu-id="d6024-132">Create a new **\<ControlTemplate>** with the following properties set:</span></span>

|     |     |
| --- | --- |
| <span data-ttu-id="d6024-133">**x:Key**</span><span class="sxs-lookup"><span data-stu-id="d6024-133">**x:Key**</span></span>         | `roundbutton` |
| **TargetType**    | `Button` |

<span data-ttu-id="d6024-134">Questo modello di controllo sarà semplice:</span><span class="sxs-lookup"><span data-stu-id="d6024-134">This control template will be simple:</span></span>

- <span data-ttu-id="d6024-135">elemento radice per il controllo,<xref:System.Windows.Controls.Grid></span><span class="sxs-lookup"><span data-stu-id="d6024-135">a root element for the control, a <xref:System.Windows.Controls.Grid></span></span>
- <span data-ttu-id="d6024-136">oggetto <xref:System.Windows.Shapes.Ellipse> per creare l'aspetto arrotondato del pulsante</span><span class="sxs-lookup"><span data-stu-id="d6024-136">an <xref:System.Windows.Shapes.Ellipse> to draw the rounded appearance of the button</span></span>
- <span data-ttu-id="d6024-137">oggetto <xref:System.Windows.Controls.ContentPresenter> per visualizzare il contenuto del pulsante specificato dall'utente</span><span class="sxs-lookup"><span data-stu-id="d6024-137">a <xref:System.Windows.Controls.ContentPresenter> to display the user-specified button content</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#ControlTemplate)]

### <a name="templatebinding"></a><span data-ttu-id="d6024-138">TemplateBinding</span><span class="sxs-lookup"><span data-stu-id="d6024-138">TemplateBinding</span></span>

<span data-ttu-id="d6024-139">Quando si crea un nuovo <xref:System.Windows.Controls.ControlTemplate>, è comunque possibile usare le proprietà pubbliche per modificare l'aspetto del controllo.</span><span class="sxs-lookup"><span data-stu-id="d6024-139">When you create a new <xref:System.Windows.Controls.ControlTemplate>, you still might want to use the public properties to change the control's appearance.</span></span> <span data-ttu-id="d6024-140">L'estensione di markup [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) associa una proprietà di un elemento che si trova in <xref:System.Windows.Controls.ControlTemplate> a una proprietà pubblica definita dal controllo.</span><span class="sxs-lookup"><span data-stu-id="d6024-140">The [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) markup extension binds a property of an element that is in the <xref:System.Windows.Controls.ControlTemplate> to a public property that is defined by the control.</span></span> <span data-ttu-id="d6024-141">Quando si utilizza un oggetto [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), si abilitano le proprietà del controllo in modo che fungano da parametri per il modello.</span><span class="sxs-lookup"><span data-stu-id="d6024-141">When you use a [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md), you enable properties on the control to act as parameters to the template.</span></span> <span data-ttu-id="d6024-142">Ovvero, quando si imposta una proprietà per un controllo, tale valore viene passato all'elemento che dispone del [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="d6024-142">That is, when a property on a control is set, that value is passed on to the element that has the [TemplateBinding](../../framework/wpf/advanced/templatebinding-markup-extension.md) on it.</span></span>

### <a name="ellipse"></a><span data-ttu-id="d6024-143">Ellipse</span><span class="sxs-lookup"><span data-stu-id="d6024-143">Ellipse</span></span>

<span data-ttu-id="d6024-144">Si noti che **:::no-loc text="Fill":::** le **:::no-loc text="Stroke":::** proprietà e dell'elemento \*\* \<ellisse>\*\* sono associate alle proprietà <xref:System.Windows.Controls.Control.Foreground> e <xref:System.Windows.Controls.Control.Background> del controllo.</span><span class="sxs-lookup"><span data-stu-id="d6024-144">Notice that the **:::no-loc text="Fill":::** and **:::no-loc text="Stroke":::** properties of the **\<Ellipse>** element are bound to the control's <xref:System.Windows.Controls.Control.Foreground> and <xref:System.Windows.Controls.Control.Background> properties.</span></span>

### <a name="contentpresenter"></a><span data-ttu-id="d6024-145">ContentPresenter</span><span class="sxs-lookup"><span data-stu-id="d6024-145">ContentPresenter</span></span>

<span data-ttu-id="d6024-146">Al modello viene aggiunto anche un [ \<elemento>ContentPresenter](xref:System.Windows.Controls.ContentPresenter) .</span><span class="sxs-lookup"><span data-stu-id="d6024-146">A [\<ContentPresenter>](xref:System.Windows.Controls.ContentPresenter) element is also added to the template.</span></span> <span data-ttu-id="d6024-147">Poiché questo modello è progettato per un pulsante, prendere in considerazione che il pulsante eredita da <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="d6024-147">Because this template is designed for a button, take into consideration that the button inherits from <xref:System.Windows.Controls.ContentControl>.</span></span> <span data-ttu-id="d6024-148">Il pulsante presenta il contenuto dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d6024-148">The button presents the content of the element.</span></span> <span data-ttu-id="d6024-149">È possibile impostare qualsiasi elemento all'interno del pulsante, ad esempio testo normale o anche un altro controllo.</span><span class="sxs-lookup"><span data-stu-id="d6024-149">You can set anything inside of the button, such as plain text or even another control.</span></span> <span data-ttu-id="d6024-150">Entrambi i pulsanti validi sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6024-150">Both of the following are valid buttons:</span></span>

```xaml
<Button>My Text</Button>

<!-- and -->

<Button>
    <CheckBox>Checkbox in a button</CheckBox>
</Button>
```

<span data-ttu-id="d6024-151">In entrambi gli esempi precedenti, il testo e la casella di controllo vengono impostati come proprietà [Button. Content](xref:System.Windows.Controls.ContentControl.Content) .</span><span class="sxs-lookup"><span data-stu-id="d6024-151">In both of the previous examples, the text and the checkbox are set as the [Button.Content](xref:System.Windows.Controls.ContentControl.Content) property.</span></span> <span data-ttu-id="d6024-152">Qualsiasi elemento viene impostato in quanto il contenuto può essere presentato tramite un \*\* \<>ContentPresenter \*\*, che corrisponde al modello.</span><span class="sxs-lookup"><span data-stu-id="d6024-152">Whatever is set as the content can be presented through a **\<ContentPresenter>**, which is what the template does.</span></span>

<span data-ttu-id="d6024-153">Se l' <xref:System.Windows.Controls.ControlTemplate> oggetto viene applicato a <xref:System.Windows.Controls.ContentControl> un tipo, ad esempio `Button`, un <xref:System.Windows.Controls.ContentPresenter> oggetto viene cercato nell'albero degli elementi.</span><span class="sxs-lookup"><span data-stu-id="d6024-153">If the <xref:System.Windows.Controls.ControlTemplate> is applied to a <xref:System.Windows.Controls.ContentControl> type, such as a `Button`, a <xref:System.Windows.Controls.ContentPresenter> is searched for in the element tree.</span></span> <span data-ttu-id="d6024-154">Se `ContentPresenter` viene trovato, il modello associa automaticamente la <xref:System.Windows.Controls.ContentControl.Content> proprietà del controllo a. `ContentPresenter`</span><span class="sxs-lookup"><span data-stu-id="d6024-154">If the `ContentPresenter` is found, the template automatically binds the control's <xref:System.Windows.Controls.ContentControl.Content> property to the `ContentPresenter`.</span></span>

## <a name="use-the-template"></a><span data-ttu-id="d6024-155">Modello</span><span class="sxs-lookup"><span data-stu-id="d6024-155">Use the template</span></span>

<span data-ttu-id="d6024-156">Trovare i pulsanti dichiarati all'inizio di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d6024-156">Find the buttons that were declared at the start of this article.</span></span>

[!code-xaml[Initial](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window1.xaml#Initial)]

<span data-ttu-id="d6024-157">Impostare la <xref:System.Windows.Controls.Control.Template> proprietà del secondo pulsante sulla `roundbutton` risorsa:</span><span class="sxs-lookup"><span data-stu-id="d6024-157">Set the second button's <xref:System.Windows.Controls.Control.Template> property to the `roundbutton` resource:</span></span>

[!code-xaml[StyledButton](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButton)]

<span data-ttu-id="d6024-158">Se si esegue il progetto e si osserva il risultato, si noterà che il pulsante ha uno sfondo arrotondato.</span><span class="sxs-lookup"><span data-stu-id="d6024-158">If you run the project and look at the result, you'll see that the button has a rounded background.</span></span>

![Finestra WPF con un pulsante ovale del modello](media/create-apply-template/styled-button.png)

<span data-ttu-id="d6024-160">Si noterà che il pulsante non è un cerchio ma è inclinato.</span><span class="sxs-lookup"><span data-stu-id="d6024-160">You may have noticed that the button isn't a circle but is skewed.</span></span> <span data-ttu-id="d6024-161">A causa della modalità di funzionamento dell' \*\* \<ellisse>\*\* elemento, si espande sempre per riempire lo spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="d6024-161">Because of the way the **\<Ellipse>** element works, it always expands to fill the available space.</span></span> <span data-ttu-id="d6024-162">Rendere uniforme il cerchio modificando le proprietà **:::no-loc text="width":::** e **:::no-loc text="height":::** del pulsante sullo stesso valore:</span><span class="sxs-lookup"><span data-stu-id="d6024-162">Make the circle uniform by changing the button's  **:::no-loc text="width":::** and **:::no-loc text="height":::** properties to the same value:</span></span>

[!code-xaml[StyledButtonSize](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window3.xaml#StyledButtonSize)]

![Finestra WPF con un pulsante circolare del modello](media/create-apply-template/styled-uniform-button.png)

## <a name="add-a-trigger"></a><span data-ttu-id="d6024-164">Aggiungere un trigger</span><span class="sxs-lookup"><span data-stu-id="d6024-164">Add a Trigger</span></span>

<span data-ttu-id="d6024-165">Anche se un pulsante con un modello applicato è diverso, si comporta allo stesso modo di qualsiasi altro pulsante.</span><span class="sxs-lookup"><span data-stu-id="d6024-165">Even though a button with a template applied looks different, it behaves the same as any other button.</span></span> <span data-ttu-id="d6024-166">Se si preme il pulsante, viene <xref:System.Windows.Controls.Primitives.ButtonBase.Click> generato l'evento.</span><span class="sxs-lookup"><span data-stu-id="d6024-166">If you press the button, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event fires.</span></span> <span data-ttu-id="d6024-167">Tuttavia, è possibile notare che quando si sposta il puntatore del mouse sul pulsante, gli oggetti visivi del pulsante non cambiano.</span><span class="sxs-lookup"><span data-stu-id="d6024-167">However, you may have noticed that when you move your mouse over the button, the button's visuals don't change.</span></span> <span data-ttu-id="d6024-168">Queste interazioni visive sono tutte definite dal modello.</span><span class="sxs-lookup"><span data-stu-id="d6024-168">These visual interactions are all defined by the template.</span></span>

<span data-ttu-id="d6024-169">Con l'evento dinamico e i sistemi di proprietà forniti da WPF, è possibile controllare una proprietà specifica per un valore e quindi ridefinire lo stile del modello quando appropriato.</span><span class="sxs-lookup"><span data-stu-id="d6024-169">With the dynamic event and property systems that WPF provides, you can watch a specific property for a value and then restyle the template when appropriate.</span></span> <span data-ttu-id="d6024-170">In questo esempio si osserverà la <xref:System.Windows.UIElement.IsMouseOver> proprietà del pulsante.</span><span class="sxs-lookup"><span data-stu-id="d6024-170">In this example, you'll watch the button's <xref:System.Windows.UIElement.IsMouseOver> property.</span></span> <span data-ttu-id="d6024-171">Quando il mouse si trova sul controllo, applicare uno stile all' \*\* \<ellisse>\*\* con un nuovo colore.</span><span class="sxs-lookup"><span data-stu-id="d6024-171">When the mouse is over the control, style the **\<Ellipse>** with a new color.</span></span> <span data-ttu-id="d6024-172">Questo tipo di trigger è noto come *PropertyTrigger*.</span><span class="sxs-lookup"><span data-stu-id="d6024-172">This type of trigger is known as a *PropertyTrigger*.</span></span>

<span data-ttu-id="d6024-173">Per eseguire questa operazione, è necessario aggiungere un nome al \*\* \<>ellisse\*\* a cui è possibile fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="d6024-173">For this to work, you'll need to add a name to the **\<Ellipse>** that you can reference.</span></span> <span data-ttu-id="d6024-174">Assegnargli il nome di **BackgroundElement**.</span><span class="sxs-lookup"><span data-stu-id="d6024-174">Give it the name of **backgroundElement**.</span></span>

[!code-xaml[EllipseName](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml#EllipseName)]

<span data-ttu-id="d6024-175">Successivamente, aggiungere un nuovo <xref:System.Windows.Trigger> oggetto alla raccolta [ControlTemplate. Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) .</span><span class="sxs-lookup"><span data-stu-id="d6024-175">Next, add a new <xref:System.Windows.Trigger> to the [ControlTemplate.Triggers](xref:System.Windows.Controls.ControlTemplate.Triggers) collection.</span></span> <span data-ttu-id="d6024-176">Il trigger osserverà l' `IsMouseOver` evento per il valore `true`.</span><span class="sxs-lookup"><span data-stu-id="d6024-176">The trigger will watch the `IsMouseOver` event for the value `true`.</span></span>

[!code-xaml[ControlTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window4.xaml?name=ControlTemplate&highlight=6-10)]

<span data-ttu-id="d6024-177">Aggiungere quindi un \*\* \<Setter>\*\* al \*\* \<trigger>\*\* che modifica la proprietà **Fill** dell' \*\* \<ellisse>\*\* in un nuovo colore.</span><span class="sxs-lookup"><span data-stu-id="d6024-177">Next, add a **\<Setter>** to the **\<Trigger>** that changes the **Fill** property of the **\<Ellipse>** to a new color.</span></span>

[!code-xaml[MouseOver](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#MouseOver)]

<span data-ttu-id="d6024-178">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="d6024-178">Run the project.</span></span> <span data-ttu-id="d6024-179">Si noti che quando si sposta il puntatore del mouse sul pulsante, il colore dell' \*\* \<ellisse>\*\* cambia.</span><span class="sxs-lookup"><span data-stu-id="d6024-179">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** changes.</span></span>

![pulsante di spostamento del mouse su WPF per modificare il colore di riempimento](media/create-apply-template/mouse-move-over-button.gif)

## <a name="use-a-visualstate"></a><span data-ttu-id="d6024-181">Usare un VisualState</span><span class="sxs-lookup"><span data-stu-id="d6024-181">Use a VisualState</span></span>

<span data-ttu-id="d6024-182">Gli Stati di visualizzazione vengono definiti e attivati da un controllo.</span><span class="sxs-lookup"><span data-stu-id="d6024-182">Visual states are defined and triggered by a control.</span></span> <span data-ttu-id="d6024-183">Ad esempio, quando il mouse viene spostato sopra il controllo, lo `CommonStates.MouseOver` stato viene attivato.</span><span class="sxs-lookup"><span data-stu-id="d6024-183">For example, when the mouse is moved on top of the control, the `CommonStates.MouseOver` state is triggered.</span></span> <span data-ttu-id="d6024-184">È possibile aggiungere un'animazione alle modifiche delle proprietà in base allo stato corrente del controllo.</span><span class="sxs-lookup"><span data-stu-id="d6024-184">You can animate property changes based on the current state of the control.</span></span> <span data-ttu-id="d6024-185">Nella sezione precedente è stato usato un \*\* \<>PropertyTrigger\*\* per modificare il primo piano del pulsante in `AliceBlue` quando la `IsMouseOver` proprietà era. `true`</span><span class="sxs-lookup"><span data-stu-id="d6024-185">In the previous section, a **\<PropertyTrigger>** was used to change the foreground of the button to `AliceBlue` when the `IsMouseOver` property was `true`.</span></span> <span data-ttu-id="d6024-186">In alternativa, creare uno stato di visualizzazione che aggiunge un'animazione alla modifica di questo colore, fornendo una transizione senza problemi.</span><span class="sxs-lookup"><span data-stu-id="d6024-186">Instead, create a visual state that animates the change of this color, providing a smooth transition.</span></span> <span data-ttu-id="d6024-187">Per altre informazioni su *controlli VisualState*, vedere [stili e modelli in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span><span class="sxs-lookup"><span data-stu-id="d6024-187">For more information about *VisualStates*, see [Styles and templates in WPF](../fundamentals/styles-templates-overview.md#visual-states).</span></span>

<span data-ttu-id="d6024-188">Per convertire il \*\* \<>PropertyTrigger\*\* in uno stato di visualizzazione animato, rimuovere prima di tutto l' \*\* \<elemento ControlTemplate. Triggers>\*\* dal modello.</span><span class="sxs-lookup"><span data-stu-id="d6024-188">To convert the **\<PropertyTrigger>** to an animated visual state, First, remove the **\<ControlTemplate.Triggers>** element from your template.</span></span>

[!code-xaml[CleanTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window5.xaml#CleanTemplate)]

<span data-ttu-id="d6024-189">Quindi, nella \*\* \<griglia>\*\* radice del modello di controllo, aggiungere l' \*\* \<elemento VisualStateManager. VisualStateGroups>\*\* con un \*\* \<>VisualStateGroup\*\* per. `CommonStates`</span><span class="sxs-lookup"><span data-stu-id="d6024-189">Next, in the **\<Grid>** root of the control template, add the **\<VisualStateManager.VisualStateGroups>** element with a **\<VisualStateGroup>** for `CommonStates`.</span></span> <span data-ttu-id="d6024-190">Definire due Stati, `Normal` e `MouseOver`.</span><span class="sxs-lookup"><span data-stu-id="d6024-190">Define two states, `Normal` and `MouseOver`.</span></span>

[!code-xaml[VisualState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#VisualState)]

<span data-ttu-id="d6024-191">Tutte le animazioni definite in un oggetto \*\* \<VisualState>\*\* vengono applicate quando lo stato viene attivato.</span><span class="sxs-lookup"><span data-stu-id="d6024-191">Any animations defined in a **\<VisualState>** are applied when that state is triggered.</span></span> <span data-ttu-id="d6024-192">Creare animazioni per ogni stato.</span><span class="sxs-lookup"><span data-stu-id="d6024-192">Create animations for each state.</span></span> <span data-ttu-id="d6024-193">Le animazioni vengono inserite all'interno di uno \*\* \<storyboard>\*\* elemento.</span><span class="sxs-lookup"><span data-stu-id="d6024-193">Animations are put inside of a **\<Storyboard>** element.</span></span> <span data-ttu-id="d6024-194">Per ulteriori informazioni sugli storyboard, vedere [Cenni preliminari sugli storyboard](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d6024-194">For more information about storyboards, see [Storyboards Overview](../../framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>

- <span data-ttu-id="d6024-195">Normale</span><span class="sxs-lookup"><span data-stu-id="d6024-195">Normal</span></span>

  <span data-ttu-id="d6024-196">Questo stato aggiunge un'animazione al riempimento dell'ellisse, ripristinando il `Background` colore del controllo.</span><span class="sxs-lookup"><span data-stu-id="d6024-196">This state animates the ellipse fill, restoring it to the control's `Background` color.</span></span>

  [!code-xaml[NormalState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#NormalState)]

- <span data-ttu-id="d6024-197">MouseOver</span><span class="sxs-lookup"><span data-stu-id="d6024-197">MouseOver</span></span>

  <span data-ttu-id="d6024-198">Questo stato aggiunge un'animazione al `Background` colore dell'ellisse a un `Yellow`nuovo colore:.</span><span class="sxs-lookup"><span data-stu-id="d6024-198">This state animates the ellipse `Background` color to a new color: `Yellow`.</span></span>

  [!code-xaml[MouseOverState](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window6.xaml#MouseOverState)]

<span data-ttu-id="d6024-199">Il \*\* \<>ControlTemplate\*\* dovrebbe ora essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="d6024-199">The **\<ControlTemplate>** should now look like the following.</span></span>

[!code-xaml[FinalTemplate](~/samples/snippets/desktop-guide/wpf/styles-templates-create-apply-template/csharp/Window7.xaml#FinalTemplate)]

<span data-ttu-id="d6024-200">Eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="d6024-200">Run the project.</span></span> <span data-ttu-id="d6024-201">Si noti che quando si sposta il puntatore del mouse sul pulsante, il colore dell' \*\* \<ellisse>\*\* viene animato.</span><span class="sxs-lookup"><span data-stu-id="d6024-201">Notice that when you move the mouse over the button, the color of the **\<Ellipse>** animates.</span></span>

![pulsante di spostamento del mouse su WPF per modificare il colore di riempimento](media/create-apply-template/mouse-move-over-button-visualstate.gif)

## <a name="next-steps"></a><span data-ttu-id="d6024-203">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d6024-203">Next steps</span></span>

- [<span data-ttu-id="d6024-204">Creare uno stile per un controllo in WPF</span><span class="sxs-lookup"><span data-stu-id="d6024-204">Create a style for a control in WPF</span></span>](../fundamentals/styles-templates-create-apply-style.md)
- [<span data-ttu-id="d6024-205">Stili e modelli in WPF</span><span class="sxs-lookup"><span data-stu-id="d6024-205">Styles and templates in WPF</span></span>](../fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="d6024-206">Panoramica delle risorse XAML</span><span class="sxs-lookup"><span data-stu-id="d6024-206">Overview of XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
