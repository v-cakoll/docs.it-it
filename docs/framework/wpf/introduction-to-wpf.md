---
title: Introduzione a WPF
titleSuffix: ''
description: Crea esperienze utente visivamente accattivanti in Windows. Scopri le funzionalità e i concetti chiave di Windows Presentation Foundation (WPF).
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b8d7cf43-d1f2-4f3d-adb0-4f3a6428edc0
dev_langs:
- csharp
- vb
ms.openlocfilehash: 7a79174f5f3aebe90190db45566b37bd5e9fbe3f
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853582"
---
# <a name="wpf-overview"></a><span data-ttu-id="da385-104">Panoramica di WPF</span><span class="sxs-lookup"><span data-stu-id="da385-104">WPF overview</span></span>

<span data-ttu-id="da385-105">Windows Presentation Foundation (WPF) consente di creare applicazioni client desktop per Windows capaci di offrire all'utente un'esperienza visiva sorprendente.</span><span class="sxs-lookup"><span data-stu-id="da385-105">Windows Presentation Foundation (WPF) lets you create desktop client applications for Windows with visually stunning user experiences.</span></span>

![Esempio di interfaccia utente Contoso Healthcare](media/introduction-to-wpf/wpfintrofigure24.png)

<span data-ttu-id="da385-107">L'elemento principale di WPF è un motore di rendering vettoriale e indipendente dalla risoluzione compilato per sfruttare i vantaggi dei moderni componenti hardware grafici.</span><span class="sxs-lookup"><span data-stu-id="da385-107">The core of WPF is a resolution-independent and vector-based rendering engine that is built to take advantage of modern graphics hardware.</span></span> <span data-ttu-id="da385-108">Oltre a questo elemento principale, WPF offre un set completo di funzionalità per lo sviluppo di applicazioni che includono Extensible Application Markup Language (XAML), controlli, data binding, layout, grafica 2D e 3D, animazioni, stili, modelli, documenti, supporti, testo e tipografia.</span><span class="sxs-lookup"><span data-stu-id="da385-108">WPF extends the core with a comprehensive set of application-development features that include Extensible Application Markup Language (XAML), controls, data binding, layout, 2D and 3D graphics, animation, styles, templates, documents, media, text, and typography.</span></span> <span data-ttu-id="da385-109">WPF fa parte di .NET e, pertanto, è possibile compilare applicazioni che incorporano altri elementi dell'API .NET.</span><span class="sxs-lookup"><span data-stu-id="da385-109">WPF is part of .NET, so you can build applications that incorporate other elements of the .NET API.</span></span>

<span data-ttu-id="da385-110">Questa panoramica, destinata ai principianti, illustra le funzionalità e i concetti chiave di WPF.</span><span class="sxs-lookup"><span data-stu-id="da385-110">This overview is intended for newcomers and covers the key capabilities and concepts of WPF.</span></span>

## <a name="program-with-wpf"></a><span data-ttu-id="da385-111">Programmazione con WPF</span><span class="sxs-lookup"><span data-stu-id="da385-111">Program with WPF</span></span>

<span data-ttu-id="da385-112">WPF è un subset di tipi di .NET in gran parte contenuti nello spazio dei nomi <xref:System.Windows>.</span><span class="sxs-lookup"><span data-stu-id="da385-112">WPF exists as a subset of .NET types that are (for the most part) located in the <xref:System.Windows> namespace.</span></span> <span data-ttu-id="da385-113">Se in precedenza si sono già compilate applicazioni con .NET usando tecnologie gestite come ASP.NET e Windows Forms, si è già acquisita familiarità con le operazioni fondamentali di programmazione WPF. È possibile creare istanze di classi, impostare proprietà, chiamare metodi e gestire eventi usando il linguaggio di programmazione .NET preferito, ad esempio C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="da385-113">If you have previously built applications with .NET using managed technologies like ASP.NET and Windows Forms, the fundamental WPF programming experience should be familiar; you instantiate classes, set properties, call methods, and handle events, using your favorite .NET programming language, such as C# or Visual Basic.</span></span>

<span data-ttu-id="da385-114">WPF include costrutti di programmazione aggiuntivi che migliorano proprietà ed eventi: [proprietà di dipendenza](advanced/dependency-properties-overview.md) ed [eventi indirizzati](advanced/routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-114">WPF includes additional programming constructs that enhance properties and events: [dependency properties](advanced/dependency-properties-overview.md) and [routed events](advanced/routed-events-overview.md).</span></span>

## <a name="markup-and-code-behind"></a><span data-ttu-id="da385-115">Markup e code-behind</span><span class="sxs-lookup"><span data-stu-id="da385-115">Markup and code-behind</span></span>

<span data-ttu-id="da385-116">WPF consente di sviluppare applicazioni usando sia *markup* sia *code-behind*, un'esperienza nota agli sviluppatori ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="da385-116">WPF lets you develop an application using both *markup* and *code-behind*, an experience with which ASP.NET developers should be familiar.</span></span> <span data-ttu-id="da385-117">Il markup XAML viene normalmente usato per implementare l'aspetto di un'applicazione, mentre i linguaggi di programmazione gestiti (code-behind) vengono usati per implementarne il comportamento.</span><span class="sxs-lookup"><span data-stu-id="da385-117">You generally use XAML markup to implement the appearance of an application while using managed programming languages (code-behind) to implement its behavior.</span></span> <span data-ttu-id="da385-118">La separazione tra aspetto e comportamento offre alcuni vantaggi:</span><span class="sxs-lookup"><span data-stu-id="da385-118">This separation of appearance and behavior has the following benefits:</span></span>

- <span data-ttu-id="da385-119">I costi di sviluppo e gestione risultano ridotti, perché il markup specifico per l'aspetto non è associato strettamente a codice specifico per il comportamento.</span><span class="sxs-lookup"><span data-stu-id="da385-119">Development and maintenance costs are reduced because appearance-specific markup is not tightly coupled with behavior-specific code.</span></span>

- <span data-ttu-id="da385-120">Lo sviluppo è più efficiente, perché i progettisti possono implementare l'aspetto di un'applicazione mentre, contemporaneamente, gli sviluppatori ne implementano il comportamento.</span><span class="sxs-lookup"><span data-stu-id="da385-120">Development is more efficient because designers can implement an application's appearance simultaneously with developers who are implementing the application's behavior.</span></span>

- <span data-ttu-id="da385-121">Le operazioni di[globalizzazione e localizzazione](advanced/wpf-globalization-and-localization-overview.md) delle applicazioni WPF sono state semplificate.</span><span class="sxs-lookup"><span data-stu-id="da385-121">[Globalization and localization](advanced/wpf-globalization-and-localization-overview.md) for WPF applications is simplified.</span></span>

### <a name="markup"></a><span data-ttu-id="da385-122">markup</span><span class="sxs-lookup"><span data-stu-id="da385-122">Markup</span></span>

<span data-ttu-id="da385-123">XAML è un linguaggio di markup basato su XML che implementa l'aspetto di un'applicazione in modo dichiarativo.</span><span class="sxs-lookup"><span data-stu-id="da385-123">XAML is an XML-based markup language that implements an application's appearance declaratively.</span></span> <span data-ttu-id="da385-124">Viene in genere usato per creare finestre, finestre di dialogo, pagine e controlli utente e per inserire in questi elementi controlli, forme e grafica.</span><span class="sxs-lookup"><span data-stu-id="da385-124">You typically use it to create windows, dialog boxes, pages, and user controls, and to fill them with controls, shapes, and graphics.</span></span>

<span data-ttu-id="da385-125">Nell'esempio seguente viene usato XAML per implementare l'aspetto di una finestra che contiene un singolo pulsante:</span><span class="sxs-lookup"><span data-stu-id="da385-125">The following example uses XAML to implement the appearance of a window that contains a single button:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button">Click Me!</Button>

</Window>
```

<span data-ttu-id="da385-126">In particolare, questo codice XAML definisce una finestra e un pulsante con gli elementi `Window` e `Button` , rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="da385-126">Specifically, this XAML defines a window and a button by using the `Window` and `Button` elements, respectively.</span></span> <span data-ttu-id="da385-127">Ogni elemento viene configurato con attributi, ad esempio l'attributo `Window` dell'elemento `Title` per specificare il testo della barra del titolo della finestra.</span><span class="sxs-lookup"><span data-stu-id="da385-127">Each element is configured with attributes, such as the `Window` element's `Title` attribute to specify the window's title-bar text.</span></span> <span data-ttu-id="da385-128">In fase di esecuzione, WPF converte gli elementi e gli attributi definiti nel markup in istanze di classi WPF.</span><span class="sxs-lookup"><span data-stu-id="da385-128">At run time, WPF converts the elements and attributes that are defined in markup to instances of WPF classes.</span></span> <span data-ttu-id="da385-129">Ad esempio, l'elemento `Window` viene convertito in un'istanza della classe <xref:System.Windows.Window> la cui proprietà <xref:System.Windows.Window.Title%2A> è il valore dell'attributo `Title` .</span><span class="sxs-lookup"><span data-stu-id="da385-129">For example, the `Window` element is converted to an instance of the <xref:System.Windows.Window> class whose <xref:System.Windows.Window.Title%2A> property is the value of the `Title` attribute.</span></span>

<span data-ttu-id="da385-130">Nella figura seguente viene illustrata l'interfaccia utente (UI) definita da XAML nell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="da385-130">The following figure shows the user interface (UI) that is defined by the XAML in the previous example:</span></span>

![Finestra contenente un pulsante](media/introduction-to-wpf/wpfintrofigure10.png)

<span data-ttu-id="da385-132">Poiché XAML è basato su XML, l'interfaccia utente composta con tale linguaggio viene assemblata in una gerarchia di elementi annidati nota come [struttura ad albero di elementi](advanced/trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="da385-132">Since XAML is XML-based, the UI that you compose with it is assembled in a hierarchy of nested elements known as an [element tree](advanced/trees-in-wpf.md).</span></span> <span data-ttu-id="da385-133">Questa struttura ad albero di elementi costituisce un modo logico e intuitivo per creare e gestire le interfacce utente.</span><span class="sxs-lookup"><span data-stu-id="da385-133">The element tree provides a logical and intuitive way to create and manage UIs.</span></span>

### <a name="code-behind"></a><span data-ttu-id="da385-134">Code-behind</span><span class="sxs-lookup"><span data-stu-id="da385-134">Code-behind</span></span>

<span data-ttu-id="da385-135">Il comportamento principale di un'applicazione consiste nell'implementare la funzionalità che risponde alle interazioni dell'utente, inclusa la gestione di eventi (ad esempio la scelta di un menu, una barra degli strumenti o un pulsante) e la chiamata alla logica di business e alla logica di accesso ai dati in risposta a tali eventi.</span><span class="sxs-lookup"><span data-stu-id="da385-135">The main behavior of an application is to implement the functionality that responds to user interactions, including handling events (for example, clicking a menu, tool bar, or button) and calling business logic and data access logic in response.</span></span> <span data-ttu-id="da385-136">In WPF questo comportamento viene in genere implementato in codice associato a markup.</span><span class="sxs-lookup"><span data-stu-id="da385-136">In WPF, this behavior is implemented in code that is associated with markup.</span></span> <span data-ttu-id="da385-137">Questo tipo di codice è noto come code-behind.</span><span class="sxs-lookup"><span data-stu-id="da385-137">This type of code is known as code-behind.</span></span> <span data-ttu-id="da385-138">L'esempio seguente illustra il markup aggiornato dell'esempio precedente e il code-behind:</span><span class="sxs-lookup"><span data-stu-id="da385-138">The following example shows the updated markup from the previous example and the code-behind:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.AWindow"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button" Click="button_Click">Click Me!</Button>

</Window>
```

```csharp
using System.Windows; // Window, RoutedEventArgs, MessageBox

namespace SDKSample
{
    public partial class AWindow : Window
    {
        public AWindow()
        {
            // InitializeComponent call is required to merge the UI
            // that is defined in markup with this class, including  
            // setting properties and registering event handlers
            InitializeComponent();
        }

        void button_Click(object sender, RoutedEventArgs e)
        {
            // Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!");
        }
    }
}
```

```vb
Namespace SDKSample

    Partial Public Class AWindow
        Inherits System.Windows.Window

        Public Sub New()

            ' InitializeComponent call is required to merge the UI
            ' that is defined in markup with this class, including  
            ' setting properties and registering event handlers
            InitializeComponent()

        End Sub

        Private Sub button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)

            ' Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!")

        End Sub

    End Class

End Namespace
```

<span data-ttu-id="da385-139">In questo esempio il code-behind implementa una classe che deriva dalla classe <xref:System.Windows.Window> .</span><span class="sxs-lookup"><span data-stu-id="da385-139">In this example, the code-behind implements a class that derives from the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="da385-140">L'attributo `x:Class` viene usato per associare il markup alla classe code-behind.</span><span class="sxs-lookup"><span data-stu-id="da385-140">The `x:Class` attribute is used to associate the markup with the code-behind class.</span></span> <span data-ttu-id="da385-141">`InitializeComponent` viene chiamato dal costruttore della classe code-behind per unire l'interfaccia utente definita nel markup con la classe code-behind.</span><span class="sxs-lookup"><span data-stu-id="da385-141">`InitializeComponent` is called from the code-behind class's constructor to merge the UI that is defined in markup with the code-behind class.</span></span> <span data-ttu-id="da385-142">`InitializeComponent`viene generato automaticamente quando viene compilata l'applicazione, motivo per cui non è necessario implementarla manualmente. La combinazione di `x:Class` e `InitializeComponent` assicura che l'implementazione venga inizializzata correttamente ogni volta che viene creata.</span><span class="sxs-lookup"><span data-stu-id="da385-142">(`InitializeComponent` is generated for you when your application is built, which is why you don't need to implement it manually.) The combination of `x:Class` and `InitializeComponent` ensure that your implementation is correctly initialized whenever it is created.</span></span> <span data-ttu-id="da385-143">La classe code-behind implementa anche un gestore dell'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del pulsante.</span><span class="sxs-lookup"><span data-stu-id="da385-143">The code-behind class also implements an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span> <span data-ttu-id="da385-144">Quando si fa clic sul pulsante, il gestore eventi mostra una finestra di messaggio chiamando il metodo <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="da385-144">When the button is clicked, the event handler shows a message box by calling the <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> method.</span></span>

<span data-ttu-id="da385-145">La figura seguente mostra il risultato quando si fa clic sul pulsante:</span><span class="sxs-lookup"><span data-stu-id="da385-145">The following figure shows the result when the button is clicked:</span></span>

![MessageBox](media/introduction-to-wpf/wpfintrofigure25.png)

## <a name="controls"></a><span data-ttu-id="da385-147">Controlli</span><span class="sxs-lookup"><span data-stu-id="da385-147">Controls</span></span>

<span data-ttu-id="da385-148">Le esperienze utente fornite dal modello di applicazione sono controlli costruiti.</span><span class="sxs-lookup"><span data-stu-id="da385-148">The user experiences that are delivered by the application model are constructed controls.</span></span> <span data-ttu-id="da385-149">In WPF, *controllo* è un termine generico che si applica a una categoria di classi WPF ospitate in una finestra o una pagina, che hanno un'interfaccia utente e che implementano un comportamento.</span><span class="sxs-lookup"><span data-stu-id="da385-149">In WPF, *control* is an umbrella term that applies to a category of WPF classes that are hosted in either a window or a page, have a user interface, and implement some behavior.</span></span>

<span data-ttu-id="da385-150">Per altre informazioni, vedere [Controlli](controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="da385-150">For more information, see [Controls](controls/index.md).</span></span>

### <a name="wpf-controls-by-function"></a><span data-ttu-id="da385-151">Controlli WPF per funzione</span><span class="sxs-lookup"><span data-stu-id="da385-151">WPF controls by function</span></span>

<span data-ttu-id="da385-152">I controlli WPF incorporati sono elencati di seguito:</span><span class="sxs-lookup"><span data-stu-id="da385-152">The built-in WPF controls are listed here:</span></span>

- <span data-ttu-id="da385-153">**Pulsanti**: <xref:System.Windows.Controls.Button> e <xref:System.Windows.Controls.Primitives.RepeatButton> .</span><span class="sxs-lookup"><span data-stu-id="da385-153">**Buttons**: <xref:System.Windows.Controls.Button> and <xref:System.Windows.Controls.Primitives.RepeatButton>.</span></span>

- <span data-ttu-id="da385-154">**Visualizzazione dei dati**: <xref:System.Windows.Controls.DataGrid> , <xref:System.Windows.Controls.ListView> e <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="da385-154">**Data Display**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>, and <xref:System.Windows.Controls.TreeView>.</span></span>

- <span data-ttu-id="da385-155">**Visualizzazione e selezione di date**: <xref:System.Windows.Controls.Calendar> e <xref:System.Windows.Controls.DatePicker> .</span><span class="sxs-lookup"><span data-stu-id="da385-155">**Date Display and Selection**: <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>.</span></span>

- <span data-ttu-id="da385-156">**Finestre di dialogo**: <xref:Microsoft.Win32.OpenFileDialog> , <xref:System.Windows.Controls.PrintDialog> e <xref:Microsoft.Win32.SaveFileDialog> .</span><span class="sxs-lookup"><span data-stu-id="da385-156">**Dialog Boxes**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>, and <xref:Microsoft.Win32.SaveFileDialog>.</span></span>

- <span data-ttu-id="da385-157">**Input penna digitale**: <xref:System.Windows.Controls.InkCanvas> e <xref:System.Windows.Controls.InkPresenter> .</span><span class="sxs-lookup"><span data-stu-id="da385-157">**Digital Ink**: <xref:System.Windows.Controls.InkCanvas> and <xref:System.Windows.Controls.InkPresenter>.</span></span>

- <span data-ttu-id="da385-158">**Documenti**: <xref:System.Windows.Controls.DocumentViewer> , <xref:System.Windows.Controls.FlowDocumentPageViewer> , <xref:System.Windows.Controls.FlowDocumentReader> , <xref:System.Windows.Controls.FlowDocumentScrollViewer> e <xref:System.Windows.Controls.StickyNoteControl> .</span><span class="sxs-lookup"><span data-stu-id="da385-158">**Documents**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>, and <xref:System.Windows.Controls.StickyNoteControl>.</span></span>

- <span data-ttu-id="da385-159">**Input**: <xref:System.Windows.Controls.TextBox> , <xref:System.Windows.Controls.RichTextBox> e <xref:System.Windows.Controls.PasswordBox> .</span><span class="sxs-lookup"><span data-stu-id="da385-159">**Input**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Controls.PasswordBox>.</span></span>

- <span data-ttu-id="da385-160">**Layout**: <xref:System.Windows.Controls.Border> , <xref:System.Windows.Controls.Primitives.BulletDecorator> , <xref:System.Windows.Controls.Canvas> , <xref:System.Windows.Controls.DockPanel> , <xref:System.Windows.Controls.Expander> , <xref:System.Windows.Controls.Grid> , <xref:System.Windows.Controls.GridView> , <xref:System.Windows.Controls.GridSplitter> , <xref:System.Windows.Controls.GroupBox> , <xref:System.Windows.Controls.Panel> , <xref:System.Windows.Controls.Primitives.ResizeGrip> , <xref:System.Windows.Controls.Separator> , <xref:System.Windows.Controls.Primitives.ScrollBar> , <xref:System.Windows.Controls.ScrollViewer> , <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.Primitives.Thumb> , <xref:System.Windows.Controls.Viewbox> , <xref:System.Windows.Controls.VirtualizingStackPanel> , <xref:System.Windows.Window> e <xref:System.Windows.Controls.WrapPanel> .</span><span class="sxs-lookup"><span data-stu-id="da385-160">**Layout**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>, <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>, and <xref:System.Windows.Controls.WrapPanel>.</span></span>

- <span data-ttu-id="da385-161">**Supporti**: <xref:System.Windows.Controls.Image> , <xref:System.Windows.Controls.MediaElement> e <xref:System.Windows.Controls.SoundPlayerAction> .</span><span class="sxs-lookup"><span data-stu-id="da385-161">**Media**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>, and <xref:System.Windows.Controls.SoundPlayerAction>.</span></span>

- <span data-ttu-id="da385-162">**Menu**: <xref:System.Windows.Controls.ContextMenu> , <xref:System.Windows.Controls.Menu> e <xref:System.Windows.Controls.ToolBar> .</span><span class="sxs-lookup"><span data-stu-id="da385-162">**Menus**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>, and <xref:System.Windows.Controls.ToolBar>.</span></span>

- <span data-ttu-id="da385-163">**Navigazione**: <xref:System.Windows.Controls.Frame> , <xref:System.Windows.Documents.Hyperlink> , <xref:System.Windows.Controls.Page> , <xref:System.Windows.Navigation.NavigationWindow> e <xref:System.Windows.Controls.TabControl> .</span><span class="sxs-lookup"><span data-stu-id="da385-163">**Navigation**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, and <xref:System.Windows.Controls.TabControl>.</span></span>

- <span data-ttu-id="da385-164">**Selezione**: <xref:System.Windows.Controls.CheckBox> , <xref:System.Windows.Controls.ComboBox> , <xref:System.Windows.Controls.ListBox> , <xref:System.Windows.Controls.RadioButton> e <xref:System.Windows.Controls.Slider> .</span><span class="sxs-lookup"><span data-stu-id="da385-164">**Selection**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>, and <xref:System.Windows.Controls.Slider>.</span></span>

- <span data-ttu-id="da385-165">**Informazioni utente**: <xref:System.Windows.Controls.AccessText> , <xref:System.Windows.Controls.Label> , <xref:System.Windows.Controls.Primitives.Popup> , <xref:System.Windows.Controls.ProgressBar> , <xref:System.Windows.Controls.Primitives.StatusBar> , <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Controls.ToolTip> .</span><span class="sxs-lookup"><span data-stu-id="da385-165">**User Information**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>, and <xref:System.Windows.Controls.ToolTip>.</span></span>

## <a name="input-and-commands"></a><span data-ttu-id="da385-166">Input e comandi</span><span class="sxs-lookup"><span data-stu-id="da385-166">Input and commands</span></span>

<span data-ttu-id="da385-167">I controlli nella maggior parte dei casi rilevano e rispondono all'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="da385-167">Controls most often detect and respond to user input.</span></span> <span data-ttu-id="da385-168">Il [sistema di input di WPF](advanced/input-overview.md) usa eventi sia diretti sia indirizzati per supportare l'input di testo, la gestione dello stato attivo e il posizionamento del mouse.</span><span class="sxs-lookup"><span data-stu-id="da385-168">The [WPF input system](advanced/input-overview.md) uses both direct and routed events to support text input, focus management, and mouse positioning.</span></span>

<span data-ttu-id="da385-169">I requisiti di input delle applicazioni sono spesso complessi.</span><span class="sxs-lookup"><span data-stu-id="da385-169">Applications often have complex input requirements.</span></span> <span data-ttu-id="da385-170">In WPF è disponibile un [sistema di comandi](advanced/commanding-overview.md) che separa le azioni di input utente dal codice che risponde a tali azioni.</span><span class="sxs-lookup"><span data-stu-id="da385-170">WPF provides a [command system](advanced/commanding-overview.md) that separates user-input actions from the code that responds to those actions.</span></span>

## <a name="layout"></a><span data-ttu-id="da385-171">Layout</span><span class="sxs-lookup"><span data-stu-id="da385-171">Layout</span></span>

<span data-ttu-id="da385-172">Quando si crea un'interfaccia utente, si dispongono i controlli per percorso e dimensione per creare un layout.</span><span class="sxs-lookup"><span data-stu-id="da385-172">When you create a user interface, you arrange your controls by location and size to form a layout.</span></span> <span data-ttu-id="da385-173">Il requisito principale di qualsiasi layout è quello di adattarsi alle modifiche nella dimensione delle finestre e nelle impostazioni di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="da385-173">A key requirement of any layout is to adapt to changes in window size and display settings.</span></span> <span data-ttu-id="da385-174">Anziché richiedere la scrittura di codice per adattare un layout in tali circostanze, WPF offre un efficiente sistema di layout estendibile.</span><span class="sxs-lookup"><span data-stu-id="da385-174">Rather than forcing you to write the code to adapt a layout in these circumstances, WPF provides a first-class, extensible layout system for you.</span></span>

<span data-ttu-id="da385-175">L'elemento fondamentale del sistema di layout è il posizionamento relativo che aumenta la capacità di adattamento a condizioni di finestre e visualizzazione mutevoli.</span><span class="sxs-lookup"><span data-stu-id="da385-175">The cornerstone of the layout system is relative positioning, which increases the ability to adapt to changing window and display conditions.</span></span> <span data-ttu-id="da385-176">Il sistema di layout gestisce inoltre la negoziazione tra i controlli per determinare il layout.</span><span class="sxs-lookup"><span data-stu-id="da385-176">In addition, the layout system manages the negotiation between controls to determine the layout.</span></span> <span data-ttu-id="da385-177">La negoziazione è un processo a due fasi in cui innanzitutto un controllo indica il percorso e le dimensioni richieste alla relativa entità principale, quindi l'entità principale indica lo spazio disponibile al controllo.</span><span class="sxs-lookup"><span data-stu-id="da385-177">The negotiation is a two-step process: first, a control tells its parent what location and size it requires; second, the parent tells the control what space it can have.</span></span>

<span data-ttu-id="da385-178">Il sistema di layout viene esposto ai controlli figlio tramite le classi base di WPF.</span><span class="sxs-lookup"><span data-stu-id="da385-178">The layout system is exposed to child controls through base WPF classes.</span></span> <span data-ttu-id="da385-179">Per layout comuni, ad esempio griglie, sovrapposizioni e ancoraggio, WPF include vari controlli di layout:</span><span class="sxs-lookup"><span data-stu-id="da385-179">For common layouts such as grids, stacking, and docking, WPF includes several layout controls:</span></span>

- <span data-ttu-id="da385-180"><xref:System.Windows.Controls.Canvas>: i controlli figlio forniscono il proprio layout.</span><span class="sxs-lookup"><span data-stu-id="da385-180"><xref:System.Windows.Controls.Canvas>: Child controls provide their own layout.</span></span>

- <span data-ttu-id="da385-181"><xref:System.Windows.Controls.DockPanel>: i controlli figlio sono allineati ai bordi del pannello.</span><span class="sxs-lookup"><span data-stu-id="da385-181"><xref:System.Windows.Controls.DockPanel>: Child controls are aligned to the edges of the panel.</span></span>

- <span data-ttu-id="da385-182"><xref:System.Windows.Controls.Grid>: i controlli figlio sono posizionati per righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="da385-182"><xref:System.Windows.Controls.Grid>: Child controls are positioned by rows and columns.</span></span>

- <span data-ttu-id="da385-183"><xref:System.Windows.Controls.StackPanel>: i controlli figlio sono sovrapposti in verticale o in orizzontale.</span><span class="sxs-lookup"><span data-stu-id="da385-183"><xref:System.Windows.Controls.StackPanel>: Child controls are stacked either vertically or horizontally.</span></span>

- <span data-ttu-id="da385-184"><xref:System.Windows.Controls.VirtualizingStackPanel>: i controlli figlio sono virtualizzati e disposti su una sola riga orientata in senso orizzontale o verticale.</span><span class="sxs-lookup"><span data-stu-id="da385-184"><xref:System.Windows.Controls.VirtualizingStackPanel>: Child controls are virtualized and arranged on a single line that is either horizontally or vertically oriented.</span></span>

- <span data-ttu-id="da385-185"><xref:System.Windows.Controls.WrapPanel>: i controlli figlio sono posizionati in ordine da sinistra a destra e mandati a capo quando sulla riga corrente sono presenti troppi controlli rispetto allo spazio disponibile.</span><span class="sxs-lookup"><span data-stu-id="da385-185"><xref:System.Windows.Controls.WrapPanel>: Child controls are positioned in left-to-right order and wrapped to the next line when there are more controls on the current line than space allows.</span></span>

<span data-ttu-id="da385-186">Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Controls.DockPanel> per disporre diversi <xref:System.Windows.Controls.TextBox> Controlli:</span><span class="sxs-lookup"><span data-stu-id="da385-186">The following example uses a <xref:System.Windows.Controls.DockPanel> to lay out several <xref:System.Windows.Controls.TextBox> controls:</span></span>

[!code-xaml[IntroToWPFSnippets#LayoutMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_1.xaml)]

<span data-ttu-id="da385-187"><xref:System.Windows.Controls.DockPanel> consente ai controlli <xref:System.Windows.Controls.TextBox> figlio di indicare la modalità di disposizione.</span><span class="sxs-lookup"><span data-stu-id="da385-187">The <xref:System.Windows.Controls.DockPanel> allows the child <xref:System.Windows.Controls.TextBox> controls to tell it how to arrange them.</span></span> <span data-ttu-id="da385-188">A tale scopo, <xref:System.Windows.Controls.DockPanel> implementa una proprietà associata `Dock` esposta ai controlli figlio per consentire a ognuno di essi di specificare uno stile di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="da385-188">To do this, the <xref:System.Windows.Controls.DockPanel> implements a `Dock` attached property that is exposed to the child controls to allow each of them to specify a dock style.</span></span>

> [!NOTE]
> <span data-ttu-id="da385-189">Una proprietà implementata da un controllo padre per essere usata dai controlli figlio è un costrutto di WPF denominato [proprietà associata](advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-189">A property that's implemented by a parent control for use by child controls is a WPF construct called an [attached property](advanced/attached-properties-overview.md).</span></span>

<span data-ttu-id="da385-190">La figura seguente illustra il risultato del markup XAML nell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="da385-190">The following figure shows the result of the XAML markup in the preceding example:</span></span>

![Pagina DockPanel](media/introduction-to-wpf/wpfintrofigure11.png)

## <a name="data-binding"></a><span data-ttu-id="da385-192">Associazione dati</span><span class="sxs-lookup"><span data-stu-id="da385-192">Data binding</span></span>

<span data-ttu-id="da385-193">La maggior parte delle applicazioni viene creata per consentire agli utenti di visualizzare e modificare i dati.</span><span class="sxs-lookup"><span data-stu-id="da385-193">Most applications are created to provide users with the means to view and edit data.</span></span> <span data-ttu-id="da385-194">Per le applicazioni WPF, le operazioni di archiviazione e accesso ai dati sono fornite da tecnologie quali SQL Server e ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="da385-194">For WPF applications, the work of storing and accessing data is already provided for by technologies such as SQL Server and ADO .NET.</span></span> <span data-ttu-id="da385-195">Dopo l'accesso ai dati e il loro caricamento negli oggetti gestiti di un'applicazione, ha inizio la fase più complessa delle applicazioni WPF.</span><span class="sxs-lookup"><span data-stu-id="da385-195">After the data is accessed and loaded into an application's managed objects, the hard work for WPF applications begins.</span></span> <span data-ttu-id="da385-196">Questa fase comporta essenzialmente due punti:</span><span class="sxs-lookup"><span data-stu-id="da385-196">Essentially, this involves two things:</span></span>

1. <span data-ttu-id="da385-197">Copia dei dati dagli oggetti gestiti ai controlli, per consentirne la visualizzazione e la modifica.</span><span class="sxs-lookup"><span data-stu-id="da385-197">Copying the data from the managed objects into controls, where the data can be displayed and edited.</span></span>

2. <span data-ttu-id="da385-198">Verifica che le modifiche apportate ai dati usando i controlli vengano copiate negli oggetti gestiti.</span><span class="sxs-lookup"><span data-stu-id="da385-198">Ensuring that changes made to data by using controls are copied back to the managed objects.</span></span>

<span data-ttu-id="da385-199">Per semplificare lo sviluppo delle applicazioni, in WPF è disponibile un motore di data binding per eseguire automaticamente queste operazioni.</span><span class="sxs-lookup"><span data-stu-id="da385-199">To simplify application development, WPF provides a data binding engine to automatically perform these steps.</span></span> <span data-ttu-id="da385-200">L'unità principale di questo motore è la classe <xref:System.Windows.Data.Binding> , il cui scopo è associare un controllo (destinazione) a un oggetto dati (origine).</span><span class="sxs-lookup"><span data-stu-id="da385-200">The core unit of the data binding engine is the <xref:System.Windows.Data.Binding> class, whose job is to bind a control (the binding target) to a data object (the binding source).</span></span> <span data-ttu-id="da385-201">La figura seguente illustra questa relazione:</span><span class="sxs-lookup"><span data-stu-id="da385-201">This relationship is illustrated by the following figure:</span></span>

![Diagramma di associazione dati di base](media/introduction-to-wpf/databindingmostbasic.png)

<span data-ttu-id="da385-203">L'esempio seguente descrive come associare un oggetto <xref:System.Windows.Controls.TextBox> a un'istanza di un oggetto `Person` personalizzato.</span><span class="sxs-lookup"><span data-stu-id="da385-203">The next example demonstrates how to bind a <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object.</span></span> <span data-ttu-id="da385-204">L'esempio di codice seguente mostra l'implementazione di `Person`:</span><span class="sxs-lookup"><span data-stu-id="da385-204">The `Person` implementation is shown in the following code:</span></span>

[!code-vb[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_2.vb)]
[!code-csharp[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_2.cs)]

<span data-ttu-id="da385-205">Il markup seguente associa <xref:System.Windows.Controls.TextBox> a un'istanza di un `Person` oggetto personalizzato:</span><span class="sxs-lookup"><span data-stu-id="da385-205">The following markup binds the <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object:</span></span>

```xaml
 <Window
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     x:Class="SDKSample.DataBindingWindow">

   <!-- Bind the TextBox to the data source (TextBox.Text to Person.Name) -->
   <TextBox Name="personNameTextBox" Text="{Binding Path=Name}" />

 </Window>
```

[!code-vb[SimpleDataBindingSnippets#DataBindingCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_6.vb)]
[!code-csharp[SimpleDataBindingSnippets#DataBindingCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_6.cs)]

<span data-ttu-id="da385-206">In questo esempio viene creata un'istanza della classe `Person` in code-behind e viene impostata come contesto dei dati per l'oggetto `DataBindingWindow`.</span><span class="sxs-lookup"><span data-stu-id="da385-206">In this example, the `Person` class is instantiated in code-behind and is set as the data context for the `DataBindingWindow`.</span></span> <span data-ttu-id="da385-207">Nel markup la proprietà <xref:System.Windows.Controls.TextBox.Text%2A> dell'oggetto <xref:System.Windows.Controls.TextBox> è associata alla proprietà `Person.Name` per mezzo della sintassi XAML "`{Binding ... }`".</span><span class="sxs-lookup"><span data-stu-id="da385-207">In markup, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> is bound to the `Person.Name` property (using the "`{Binding ... }`" XAML syntax).</span></span> <span data-ttu-id="da385-208">Questo codice XAML comunica a WPF di associare il controllo <xref:System.Windows.Controls.TextBox> all'oggetto `Person` archiviato nella proprietà <xref:System.Windows.FrameworkElement.DataContext%2A> della finestra.</span><span class="sxs-lookup"><span data-stu-id="da385-208">This XAML tells WPF to bind the <xref:System.Windows.Controls.TextBox> control to the `Person` object that is stored in the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the window.</span></span>

<span data-ttu-id="da385-209">Il motore di data binding di WPF offre supporto aggiuntivo che include convalida, ordinamento, filtro e raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="da385-209">The WPF data binding engine provides additional support that includes validation, sorting, filtering, and grouping.</span></span> <span data-ttu-id="da385-210">Il data binding supporta anche l'uso di modelli di dati per creare un'interfaccia utente personalizzata per i dati associati quando l'interfaccia utente visualizzata dai controlli WPF standard non è adatta.</span><span class="sxs-lookup"><span data-stu-id="da385-210">Furthermore, data binding supports the use of data templates to create custom user interface for bound data when the user interface displayed by the standard WPF controls is not appropriate.</span></span>

<span data-ttu-id="da385-211">Per altre informazioni, vedere [Cenni preliminari sul data binding](../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-211">For more information, see [Data binding overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

## <a name="graphics"></a><span data-ttu-id="da385-212">Grafica</span><span class="sxs-lookup"><span data-stu-id="da385-212">Graphics</span></span>

<span data-ttu-id="da385-213">In WPF è disponibile un set completo, scalabile e flessibile di funzionalità grafiche che offrono i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="da385-213">WPF introduces an extensive, scalable, and flexible set of graphics features that have the following benefits:</span></span>

- <span data-ttu-id="da385-214">**Grafica indipendente dalla risoluzione e dal dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="da385-214">**Resolution-independent and device-independent graphics**.</span></span> <span data-ttu-id="da385-215">L'unità di misura di base nel sistema grafico di WPF è il Device Independent Pixel, pari a 1/96 di pollice, indipendentemente dall'effettiva risoluzione dello schermo, che costituisce la base per il rendering indipendente dalla risoluzione e dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="da385-215">The basic unit of measurement in the WPF graphics system is the device-independent pixel, which is 1/96th of an inch, regardless of actual screen resolution, and provides the foundation for resolution-independent and device-independent rendering.</span></span> <span data-ttu-id="da385-216">Ogni Device Independent Pixel viene ridimensionato automaticamente in modo da corrispondere all'impostazione in punti per pollice (dpi) del sistema in cui viene eseguito il rendering.</span><span class="sxs-lookup"><span data-stu-id="da385-216">Each device-independent pixel automatically scales to match the dots-per-inch (dpi) setting of the system it renders on.</span></span>

- <span data-ttu-id="da385-217">**Maggiore precisione**.</span><span class="sxs-lookup"><span data-stu-id="da385-217">**Improved precision**.</span></span> <span data-ttu-id="da385-218">Il sistema di coordinate WPF viene misurato con numeri a virgola mobile a precisione doppia anziché a precisione singola.</span><span class="sxs-lookup"><span data-stu-id="da385-218">The WPF coordinate system is measured with double-precision floating-point numbers rather than single-precision.</span></span> <span data-ttu-id="da385-219">Anche i valori di opacità e delle trasformazioni vengono espressi come precisione doppia.</span><span class="sxs-lookup"><span data-stu-id="da385-219">Transformations and opacity values are also expressed as double-precision.</span></span> <span data-ttu-id="da385-220">WPF supporta anche un'ampia gamma di colori (scRGB) e offre il supporto integrato per la gestione di input da spazi colore diversi.</span><span class="sxs-lookup"><span data-stu-id="da385-220">WPF also supports a wide color gamut (scRGB) and provides integrated support for managing inputs from different color spaces.</span></span>

- <span data-ttu-id="da385-221">**Grafica e supporto dell'animazione avanzati**.</span><span class="sxs-lookup"><span data-stu-id="da385-221">**Advanced graphics and animation support**.</span></span> <span data-ttu-id="da385-222">WPF semplifica la programmazione grafica. Grazie alla gestione automatica delle scene di animazione, infatti, non occorre preoccuparsi dell'elaborazione delle scene, dei cicli di rendering e dell'interpolazione bilineare.</span><span class="sxs-lookup"><span data-stu-id="da385-222">WPF simplifies graphics programming by managing animation scenes for you; there is no need to worry about scene processing, rendering loops, and bilinear interpolation.</span></span> <span data-ttu-id="da385-223">In WPF è anche disponibile il supporto per hit testing e composizione alfa completa.</span><span class="sxs-lookup"><span data-stu-id="da385-223">Additionally, WPF provides hit-testing support and full alpha-compositing support.</span></span>

- <span data-ttu-id="da385-224">**Accelerazione hardware**.</span><span class="sxs-lookup"><span data-stu-id="da385-224">**Hardware acceleration**.</span></span> <span data-ttu-id="da385-225">Il sistema grafico di WPF sfrutta i vantaggi dei componenti hardware grafici per ridurre al minimo l'uso della CPU.</span><span class="sxs-lookup"><span data-stu-id="da385-225">The WPF graphics system takes advantage of graphics hardware to minimize CPU usage.</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="da385-226">Forme 2D</span><span class="sxs-lookup"><span data-stu-id="da385-226">2D shapes</span></span>

<span data-ttu-id="da385-227">In WPF è disponibile una libreria di forme 2D comuni disegnate da vettori, ad esempio i rettangoli e le ellissi mostrati nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="da385-227">WPF provides a library of common vector-drawn 2D shapes, such as the rectangles and ellipses that are shown in the following illustration:</span></span>

![Ellissi e rettangoli](media/introduction-to-wpf/wpfintrofigure4.PNG)

<span data-ttu-id="da385-229">La caratteristica interessante delle forme è che non vengono usate solo per la visualizzazione. Le forme, infatti, implementano molte delle funzionalità fornite dai controlli, incluso l'input della tastiera e del mouse.</span><span class="sxs-lookup"><span data-stu-id="da385-229">An interesting capability of shapes is that they are not just for display; shapes implement many of the features that you expect from controls, including keyboard and mouse input.</span></span> <span data-ttu-id="da385-230">Nell'esempio seguente viene illustrato l' <xref:System.Windows.UIElement.MouseUp> evento di un oggetto <xref:System.Windows.Shapes.Ellipse> gestito:</span><span class="sxs-lookup"><span data-stu-id="da385-230">The following example shows the <xref:System.Windows.UIElement.MouseUp> event of an <xref:System.Windows.Shapes.Ellipse> being handled:</span></span>

[!code-xaml[IntroToWPFSnippets#HandleEllipseMouseUpEventMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_7.xaml)]

[!code-vb[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_8.vb)]
[!code-csharp[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_8.cs)]

<span data-ttu-id="da385-231">Nella figura seguente viene illustrato ciò che viene prodotto dal codice precedente:</span><span class="sxs-lookup"><span data-stu-id="da385-231">The following figure shows what is produced by the preceding code:</span></span>

![Finestra con il testo "you clicked the ellipse&#33;"](media/introduction-to-wpf/wpfintrofigure12.png)

<span data-ttu-id="da385-233">Per altre informazioni, vedere [Cenni preliminari sulle forme e il disegno di base in WPF](../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-233">For more information, see [Shapes and basic drawing in WPF overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="da385-234">Geometrie 2D</span><span class="sxs-lookup"><span data-stu-id="da385-234">2D geometries</span></span>

<span data-ttu-id="da385-235">Le forme 2D disponibili in WPF coprono il set standard di forme di base.</span><span class="sxs-lookup"><span data-stu-id="da385-235">The 2D shapes provided by WPF cover the standard set of basic shapes.</span></span> <span data-ttu-id="da385-236">Può tuttavia essere necessario creare forme personalizzate per semplificare la progettazione di un'interfaccia utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="da385-236">However, you may need to create custom shapes to facilitate the design of a customized user interface.</span></span> <span data-ttu-id="da385-237">A questo scopo, in WPF sono disponibili le geometrie.</span><span class="sxs-lookup"><span data-stu-id="da385-237">For this purpose, WPF provides geometries.</span></span> <span data-ttu-id="da385-238">La figura seguente illustra come usare le geometrie per creare una forma personalizzata che può essere disegnata direttamente o usata come pennello o per ritagliare altre forme e controlli.</span><span class="sxs-lookup"><span data-stu-id="da385-238">The following figure demonstrates the use of geometries to create a custom shape that can be drawn directly, used as a brush, or used to clip other shapes and controls.</span></span>

<span data-ttu-id="da385-239">Gli oggetti<xref:System.Windows.Shapes.Path> possono essere usati per disegnare forme chiuse o aperte, più forme e anche forme curve.</span><span class="sxs-lookup"><span data-stu-id="da385-239"><xref:System.Windows.Shapes.Path> objects can be used to draw closed or open shapes, multiple shapes, and even curved shapes.</span></span>

<span data-ttu-id="da385-240">Gli oggetti <xref:System.Windows.Media.Geometry> possono essere usati per ritagliare ed eseguire hit testing e rendering di dati grafici 2D.</span><span class="sxs-lookup"><span data-stu-id="da385-240"><xref:System.Windows.Media.Geometry> objects can be used for clipping, hit-testing, and rendering 2D graphic data.</span></span>

![Vari usi di un percorso](media/introduction-to-wpf/wpfintrofigure5.png)

<span data-ttu-id="da385-242">Per altre informazioni, vedere [Cenni preliminari sulle classi Geometry](graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-242">For more information, see [Geometry overview](graphics-multimedia/geometry-overview.md).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="da385-243">Effetti 2D</span><span class="sxs-lookup"><span data-stu-id="da385-243">2D effects</span></span>

<span data-ttu-id="da385-244">Un subset di funzionalità 2D di WPF include effetti visivi, ad esempio sfumature, bitmap, disegni, disegni con video, rotazione, ridimensionamento e inclinazione.</span><span class="sxs-lookup"><span data-stu-id="da385-244">A subset of WPF 2D capabilities includes visual effects, such as gradients, bitmaps, drawings, painting with videos, rotation, scaling, and skewing.</span></span> <span data-ttu-id="da385-245">Si ottengono tutti con pennelli; nella figura seguente vengono illustrati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="da385-245">These are all achieved with brushes; the following figure shows some examples:</span></span>

![Illustrazione di pennelli diversi](media/introduction-to-wpf/wpfintrofigure6.png)

<span data-ttu-id="da385-247">Per altre informazioni, vedere [Cenni preliminari sui pennelli di WPF](graphics-multimedia/wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-247">For more information, see [WPF brushes overview](graphics-multimedia/wpf-brushes-overview.md).</span></span>

### <a name="3d-rendering"></a><span data-ttu-id="da385-248">Rendering 3D</span><span class="sxs-lookup"><span data-stu-id="da385-248">3D rendering</span></span>

<span data-ttu-id="da385-249">WPF include anche funzionalità di rendering 3D che si integrano con la grafica 2D per consentire la creazione di interfacce utente più interessanti e interessanti.</span><span class="sxs-lookup"><span data-stu-id="da385-249">WPF also includes 3D rendering capabilities that integrate with 2D graphics to allow the creation of more exciting and interesting user interfaces.</span></span> <span data-ttu-id="da385-250">Ad esempio, la figura seguente mostra le immagini 2D sottoposte a rendering su forme 3D:</span><span class="sxs-lookup"><span data-stu-id="da385-250">For example, the following figure shows 2D images rendered onto 3D shapes:</span></span>

![Schermata dell'esempio Visual3D](media/introduction-to-wpf/wpfintrofigure13.png)

<span data-ttu-id="da385-252">Per altre informazioni, vedere [Cenni preliminari sulla grafica tridimensionale](graphics-multimedia/3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-252">For more information, see [3D graphics overview](graphics-multimedia/3-d-graphics-overview.md).</span></span>

## <a name="animation"></a><span data-ttu-id="da385-253">Animazione</span><span class="sxs-lookup"><span data-stu-id="da385-253">Animation</span></span>

<span data-ttu-id="da385-254">Il supporto di animazione di WPF consente di fare crescere, muovere, ruotare e dissolvere i controlli per creare interessanti transizioni di pagina e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="da385-254">WPF animation support lets you make controls grow, shake, spin, and fade, to create interesting page transitions, and more.</span></span> <span data-ttu-id="da385-255">È possibile animare la maggior parte delle classi WPF, anche quelle personalizzate.</span><span class="sxs-lookup"><span data-stu-id="da385-255">You can animate most WPF classes, even custom classes.</span></span> <span data-ttu-id="da385-256">Nella figura seguente viene illustrata un'animazione semplice in azione:</span><span class="sxs-lookup"><span data-stu-id="da385-256">The following figure shows a simple animation in action:</span></span>

![Immagini di un cubo animato](media/introduction-to-wpf/wpfintrofigure7.png)

<span data-ttu-id="da385-258">Per altre informazioni, vedere [Cenni preliminari sull'animazione](graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-258">For more information, see [Animation overview](graphics-multimedia/animation-overview.md).</span></span>

## <a name="media"></a><span data-ttu-id="da385-259">Contenuti multimediali</span><span class="sxs-lookup"><span data-stu-id="da385-259">Media</span></span>

<span data-ttu-id="da385-260">L'uso di supporti audiovisivi è un modo per inserire contenuto dettagliato.</span><span class="sxs-lookup"><span data-stu-id="da385-260">One way to convey rich content is through the use of audiovisual media.</span></span> <span data-ttu-id="da385-261">WPF offre un supporto speciale per immagini, video e audio.</span><span class="sxs-lookup"><span data-stu-id="da385-261">WPF provides special support for images, video, and audio.</span></span>

### <a name="images"></a><span data-ttu-id="da385-262">Immagini</span><span class="sxs-lookup"><span data-stu-id="da385-262">Images</span></span>

<span data-ttu-id="da385-263">Le immagini sono comuni alla maggior parte delle applicazioni e in WPF possono essere usate in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="da385-263">Images are common to most applications, and WPF provides several ways to use them.</span></span> <span data-ttu-id="da385-264">La figura seguente illustra un'interfaccia utente con una casella di riepilogo che contiene immagini di anteprima.</span><span class="sxs-lookup"><span data-stu-id="da385-264">The following figure shows a user interface with a list box that contains thumbnail images.</span></span> <span data-ttu-id="da385-265">Quando si seleziona un'anteprima, l'immagine viene visualizzata ingrandita.</span><span class="sxs-lookup"><span data-stu-id="da385-265">When a thumbnail is selected, the image is shown full-size.</span></span>

![Immagini di anteprima e con le dimensioni originali](media/introduction-to-wpf/wpfintrofigure8.png)

<span data-ttu-id="da385-267">Per altre informazioni, vedere [Cenni preliminari sulla creazione dell'immagine](graphics-multimedia/imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-267">For more information, see [Imaging overview](graphics-multimedia/imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="da385-268">Video e audio</span><span class="sxs-lookup"><span data-stu-id="da385-268">Video and audio</span></span>

<span data-ttu-id="da385-269">Il controllo <xref:System.Windows.Controls.MediaElement> consente di riprodurre video e audio e, grazie alle caratteristiche di flessibilità, può essere usato come base per un lettore multimediale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="da385-269">The <xref:System.Windows.Controls.MediaElement> control is capable of playing both video and audio, and it is flexible enough to be the basis for a custom media player.</span></span> <span data-ttu-id="da385-270">Il markup XAML seguente implementa un lettore multimediale:</span><span class="sxs-lookup"><span data-stu-id="da385-270">The following XAML markup implements a media player:</span></span>

[!code-xaml[IntroToWPFSnippets#MediaElementMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_9.xaml)]

<span data-ttu-id="da385-271">La finestra nella figura seguente illustra il <xref:System.Windows.Controls.MediaElement> controllo in azione:</span><span class="sxs-lookup"><span data-stu-id="da385-271">The window in the following figure shows the <xref:System.Windows.Controls.MediaElement> control in action:</span></span>

![Controllo MediaElement con audio e video](media/introduction-to-wpf/wpfintrofigure1.png)

<span data-ttu-id="da385-273">Per altre informazioni, vedere [Grafica e funzionalità multimediali](graphics-multimedia/index.md).</span><span class="sxs-lookup"><span data-stu-id="da385-273">For more information, see [Graphics and multimedia](graphics-multimedia/index.md).</span></span>

## <a name="text-and-typography"></a><span data-ttu-id="da385-274">Testo e tipografia</span><span class="sxs-lookup"><span data-stu-id="da385-274">Text and typography</span></span>

<span data-ttu-id="da385-275">Per semplificare il rendering di testo di alta qualità, WPF offre le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="da385-275">To facilitate high-quality text rendering, WPF offers the following features:</span></span>

- <span data-ttu-id="da385-276">Supporto dei tipi di carattere OpenType</span><span class="sxs-lookup"><span data-stu-id="da385-276">OpenType font support.</span></span>

- <span data-ttu-id="da385-277">Miglioramenti di ClearType.</span><span class="sxs-lookup"><span data-stu-id="da385-277">ClearType enhancements.</span></span>

- <span data-ttu-id="da385-278">Prestazioni elevate che sfruttano i vantaggi dell'accelerazione hardware.</span><span class="sxs-lookup"><span data-stu-id="da385-278">High performance that takes advantage of hardware acceleration.</span></span>

- <span data-ttu-id="da385-279">Integrazione del testo con elementi multimediali, grafica e animazione.</span><span class="sxs-lookup"><span data-stu-id="da385-279">Integration of text with media, graphics, and animation.</span></span>

- <span data-ttu-id="da385-280">Supporto dei tipi di carattere internazionali e meccanismi di fallback.</span><span class="sxs-lookup"><span data-stu-id="da385-280">International font support and fallback mechanisms.</span></span>

<span data-ttu-id="da385-281">Come dimostrazione dell'integrazione del testo con la grafica, la figura seguente illustra l'applicazione di decorazioni di testo:</span><span class="sxs-lookup"><span data-stu-id="da385-281">As a demonstration of text integration with graphics, the following figure shows the application of text decorations:</span></span>

![Testo con varie decorazioni](media/introduction-to-wpf/wpfintrofigure23.png)

<span data-ttu-id="da385-283">Per altre informazioni, vedere [Funzionalità tipografiche di WPF](advanced/typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="da385-283">For more information, see [Typography in Windows Presentation Foundation](advanced/typography-in-wpf.md).</span></span>

## <a name="customize-wpf-apps"></a><span data-ttu-id="da385-284">Personalizzazione delle applicazioni WPF</span><span class="sxs-lookup"><span data-stu-id="da385-284">Customize WPF apps</span></span>

<span data-ttu-id="da385-285">Finora, sono stati presentati i blocchi di compilazione principali di WPF per lo sviluppo di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="da385-285">Up to this point, you've seen the core WPF building blocks for developing applications.</span></span> <span data-ttu-id="da385-286">Il modello di applicazione viene usato per ospitare e fornire contenuto di applicazione, costituito principalmente da controlli.</span><span class="sxs-lookup"><span data-stu-id="da385-286">You use the application model to host and deliver application content, which consists mainly of controls.</span></span> <span data-ttu-id="da385-287">Per semplificare la disposizione dei controlli in un'interfaccia utente e per mantenere tale disposizione anche in caso di modifiche alle dimensioni della finestra e alle impostazioni di visualizzazione, viene usato il sistema di layout di WPF.</span><span class="sxs-lookup"><span data-stu-id="da385-287">To simplify the arrangement of controls in a user interface, and to ensure the arrangement is maintained in the face of changes to window size and display settings, you use the WPF layout system.</span></span> <span data-ttu-id="da385-288">Poiché la maggior parte delle applicazioni consente agli utenti di interagire con i dati, per ridurre le operazioni di integrazione dell'interfaccia utente con i dati viene usato il data binding.</span><span class="sxs-lookup"><span data-stu-id="da385-288">Because most applications let users interact with data, you use data binding to reduce the work of integrating your user interface with data.</span></span> <span data-ttu-id="da385-289">Per migliorare l'aspetto visivo dell'applicazione, è possibile usare una gamma completa di grafica, animazione ed elementi multimediali disponibili in WPF.</span><span class="sxs-lookup"><span data-stu-id="da385-289">To enhance the visual appearance of your application, you use the comprehensive range of graphics, animation, and media support provided by WPF.</span></span>

<span data-ttu-id="da385-290">Spesso, tuttavia, le funzionalità di base non sono sufficienti per creare e gestire applicazioni davvero uniche e visivamente sorprendenti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="da385-290">Often, though, the basics are not enough for creating and managing a truly distinct and visually stunning user experience.</span></span> <span data-ttu-id="da385-291">I controlli WPF standard potrebbero non integrarsi con l'aspetto desiderato dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da385-291">The standard WPF controls might not integrate with the desired appearance of your application.</span></span> <span data-ttu-id="da385-292">I dati potrebbero non essere visualizzati nel modo più efficace.</span><span class="sxs-lookup"><span data-stu-id="da385-292">Data might not be displayed in the most effective way.</span></span> <span data-ttu-id="da385-293">L'esperienza utente complessiva di un'applicazione può non essere adeguata all'aspetto dei temi di Windows.</span><span class="sxs-lookup"><span data-stu-id="da385-293">Your application's overall user experience may not be suited to the default look and feel of Windows themes.</span></span> <span data-ttu-id="da385-294">Per una tecnologia di presentazione è necessaria l'estendibilità visiva, tanto quanto altri tipi di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="da385-294">In many ways, a presentation technology needs visual extensibility as much as any other type of extensibility.</span></span>

<span data-ttu-id="da385-295">Per questo motivo, WPF offre una varietà di meccanismi per la creazione di esperienze utente univoche, incluso un modello di contenuto dettagliato per controlli, trigger, modelli di controllo e di dati, stili, risorse dell'interfaccia utente, temi e interfacce.</span><span class="sxs-lookup"><span data-stu-id="da385-295">For this reason, WPF provides a variety of mechanisms for creating unique user experiences, including a rich content model for controls, triggers, control and data templates, styles, user interface resources, and themes and skins.</span></span>

### <a name="content-model"></a><span data-ttu-id="da385-296">Modello di contenuto</span><span class="sxs-lookup"><span data-stu-id="da385-296">Content model</span></span>

<span data-ttu-id="da385-297">Lo scopo principale di gran parte dei controlli di WPF è quello di visualizzare il contenuto.</span><span class="sxs-lookup"><span data-stu-id="da385-297">The main purpose of a majority of the WPF controls is to display content.</span></span> <span data-ttu-id="da385-298">In WPF il tipo e il numero di elementi che possono costituire il contenuto di un controllo è indicato come *modello di contenuto*del controllo.</span><span class="sxs-lookup"><span data-stu-id="da385-298">In WPF, the type and number of items that can constitute the content of a control is referred to as the control's *content model*.</span></span> <span data-ttu-id="da385-299">Alcuni controlli possono contenere un solo elemento e tipo di contenuto. Ad esempio, il contenuto di un oggetto <xref:System.Windows.Controls.TextBox> è un valore stringa assegnato alla proprietà <xref:System.Windows.Controls.TextBox.Text%2A> .</span><span class="sxs-lookup"><span data-stu-id="da385-299">Some controls can contain a single item and type of content; for example, the content of a <xref:System.Windows.Controls.TextBox> is a string value that is assigned to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="da385-300">Nell'esempio seguente viene impostato il contenuto di un oggetto <xref:System.Windows.Controls.TextBox> :</span><span class="sxs-lookup"><span data-stu-id="da385-300">The following example sets the content of a <xref:System.Windows.Controls.TextBox>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.TextBoxContentWindow"
    Title="TextBox Content">

    <TextBox Text="This is the content of a TextBox." />
</Window>
```

<span data-ttu-id="da385-301">Nella figura seguente viene illustrato il risultato:</span><span class="sxs-lookup"><span data-stu-id="da385-301">The following figure shows the result:</span></span>

![Controllo TextBox contenente testo](media/introduction-to-wpf/wpfintrofigure21.png)

<span data-ttu-id="da385-303">Gli altri controlli, tuttavia, possono contenere più elementi di tipi diversi di contenuto. Il contenuto di un oggetto <xref:System.Windows.Controls.Button>, specificato dalla proprietà <xref:System.Windows.Controls.ContentControl.Content%2A>, può contenere vari elementi, inclusi i controlli di layout, testo, immagini e forme.</span><span class="sxs-lookup"><span data-stu-id="da385-303">Other controls, however, can contain multiple items of different types of content; the content of a <xref:System.Windows.Controls.Button>, specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property, can contain a variety of items including layout controls, text, images, and shapes.</span></span> <span data-ttu-id="da385-304">Nell'esempio seguente viene illustrato un oggetto <xref:System.Windows.Controls.Button> con contenuto che include un oggetto <xref:System.Windows.Controls.DockPanel> , un oggetto, un oggetto <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Border> e un oggetto <xref:System.Windows.Controls.MediaElement> :</span><span class="sxs-lookup"><span data-stu-id="da385-304">The following example shows a <xref:System.Windows.Controls.Button> with content that includes a <xref:System.Windows.Controls.DockPanel>, a <xref:System.Windows.Controls.Label>, a <xref:System.Windows.Controls.Border>, and a <xref:System.Windows.Controls.MediaElement>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ButtonContentWindow"
    Title="Button Content">

  <Button Margin="20">
    <!-- Button Content -->
    <DockPanel Width="200" Height="180">
      <Label DockPanel.Dock="Top" HorizontalAlignment="Center">Click Me!</Label>
      <Border Background="Black" BorderBrush="Yellow" BorderThickness="2"
        CornerRadius="2" Margin="5">
        <MediaElement Source="media/wpf.wmv" Stretch="Fill" />
      </Border>
    </DockPanel>
  </Button>
</Window>
```

<span data-ttu-id="da385-305">Nella figura seguente viene illustrato il contenuto di questo pulsante:</span><span class="sxs-lookup"><span data-stu-id="da385-305">The following figure shows the content of this button:</span></span>

![Pulsante con più tipi di contenuto](media/introduction-to-wpf/wpfintrofigure22.png)

<span data-ttu-id="da385-307">Per altre informazioni sui tipi di contenuto supportati dai vari controlli, vedere [Modello di contenuto WPF](controls/wpf-content-model.md).</span><span class="sxs-lookup"><span data-stu-id="da385-307">For more information on the kinds of content that is supported by various controls, see [WPF content model](controls/wpf-content-model.md).</span></span>

### <a name="triggers"></a><span data-ttu-id="da385-308">Trigger</span><span class="sxs-lookup"><span data-stu-id="da385-308">Triggers</span></span>

<span data-ttu-id="da385-309">Anche se lo scopo principale del markup XAML consiste nell'implementare l'aspetto di un'applicazione, è anche possibile usare XAML per implementare alcuni aspetti del comportamento di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da385-309">Although the main purpose of XAML markup is to implement an application's appearance, you can also use XAML to implement some aspects of an application's behavior.</span></span> <span data-ttu-id="da385-310">Un esempio è dato dall'uso dei trigger per modificare l'aspetto di un'applicazione in base alle interazioni dell'utente.</span><span class="sxs-lookup"><span data-stu-id="da385-310">One example is the use of triggers to change an application's appearance based on user interactions.</span></span> <span data-ttu-id="da385-311">Per altre informazioni, vedere [stili e modelli](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-311">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="control-templates"></a><span data-ttu-id="da385-312">Modelli di controllo</span><span class="sxs-lookup"><span data-stu-id="da385-312">Control templates</span></span>

<span data-ttu-id="da385-313">Le interfacce utente predefinite per i controlli WPF sono in genere costituite da altri controlli e forme.</span><span class="sxs-lookup"><span data-stu-id="da385-313">The default user interfaces for WPF controls are typically constructed from other controls and shapes.</span></span> <span data-ttu-id="da385-314">Ad esempio, un oggetto <xref:System.Windows.Controls.Button> è composto da entrambi i controlli <xref:Microsoft.Windows.Themes.ButtonChrome> e <xref:System.Windows.Controls.ContentPresenter> .</span><span class="sxs-lookup"><span data-stu-id="da385-314">For example, a <xref:System.Windows.Controls.Button> is composed of both <xref:Microsoft.Windows.Themes.ButtonChrome> and <xref:System.Windows.Controls.ContentPresenter> controls.</span></span> <span data-ttu-id="da385-315"><xref:Microsoft.Windows.Themes.ButtonChrome> fornisce l'aspetto del pulsante standard, mentre <xref:System.Windows.Controls.ContentPresenter> consente di visualizzare il contenuto del pulsante, come specificato dalla proprietà <xref:System.Windows.Controls.ContentControl.Content%2A> .</span><span class="sxs-lookup"><span data-stu-id="da385-315">The <xref:Microsoft.Windows.Themes.ButtonChrome> provides the standard button appearance, while the <xref:System.Windows.Controls.ContentPresenter> displays the button's content, as specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property.</span></span>

<span data-ttu-id="da385-316">A volte l'aspetto predefinito di un controllo può non essere coerente con l'aspetto complessivo di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da385-316">Sometimes the default appearance of a control may be incongruent with the overall appearance of an application.</span></span> <span data-ttu-id="da385-317">In tal caso, è possibile usare un oggetto <xref:System.Windows.Controls.ControlTemplate> per modificare l'aspetto dell'interfaccia utente del controllo senza modificarne il contenuto e il comportamento.</span><span class="sxs-lookup"><span data-stu-id="da385-317">In this case, you can use a <xref:System.Windows.Controls.ControlTemplate> to change the appearance of the control's user interface without changing its content and behavior.</span></span>

<span data-ttu-id="da385-318">Nell'esempio seguente viene illustrato come modificare l'aspetto di un oggetto <xref:System.Windows.Controls.Button> utilizzando un oggetto <xref:System.Windows.Controls.ControlTemplate> :</span><span class="sxs-lookup"><span data-stu-id="da385-318">The following example shows how to change the appearance of a <xref:System.Windows.Controls.Button> by using a <xref:System.Windows.Controls.ControlTemplate>:</span></span>

[!code-xaml[IntroToWPFSnippets#ButtonControlTemplateWindowMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_16.xaml)]

[!code-csharp[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_17.cs)]
[!code-vb[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_17.vb)]

<span data-ttu-id="da385-319">In questo esempio, l'interfaccia utente predefinita del pulsante è stata sostituita con un oggetto <xref:System.Windows.Shapes.Ellipse> che presenta un bordo blu scuro e viene riempito con un oggetto <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="da385-319">In this example, the default button user interface has been replaced with an <xref:System.Windows.Shapes.Ellipse> that has a dark blue border and is filled using a <xref:System.Windows.Media.RadialGradientBrush>.</span></span> <span data-ttu-id="da385-320">Il controllo <xref:System.Windows.Controls.ContentPresenter> consente di visualizzare il contenuto dell'oggetto <xref:System.Windows.Controls.Button>, "Click Me!".</span><span class="sxs-lookup"><span data-stu-id="da385-320">The <xref:System.Windows.Controls.ContentPresenter> control displays the content of the <xref:System.Windows.Controls.Button>, "Click Me!"</span></span> <span data-ttu-id="da385-321">Quando si fa clic sull'oggetto <xref:System.Windows.Controls.Button> , viene comunque generato l'evento <xref:System.Windows.Controls.Primitives.ButtonBase.Click> come parte del comportamento predefinito del controllo <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="da385-321">When the <xref:System.Windows.Controls.Button> is clicked, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event is still raised as part of the <xref:System.Windows.Controls.Button> control's default behavior.</span></span> <span data-ttu-id="da385-322">Il risultato è illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="da385-322">The result is shown in the following figure:</span></span>

![Pulsante ellittico e una seconda finestra](media/introduction-to-wpf/wpfintrofigure2.png)

### <a name="data-templates"></a><span data-ttu-id="da385-324">Modelli di dati</span><span class="sxs-lookup"><span data-stu-id="da385-324">Data templates</span></span>

<span data-ttu-id="da385-325">Mentre un modello di controllo consente di specificare l'aspetto di un controllo, un modello di dati consente di specificare l'aspetto del contenuto di un controllo.</span><span class="sxs-lookup"><span data-stu-id="da385-325">Whereas a control template lets you specify the appearance of a control, a data template lets you specify the appearance of a control's content.</span></span> <span data-ttu-id="da385-326">I modelli di dati sono spesso usati per migliorare la modalità di visualizzazione dei dati associati.</span><span class="sxs-lookup"><span data-stu-id="da385-326">Data templates are frequently used to enhance how bound data is displayed.</span></span> <span data-ttu-id="da385-327">Nella figura seguente viene illustrato l'aspetto predefinito per un oggetto <xref:System.Windows.Controls.ListBox> associato a una raccolta di `Task` oggetti, dove ogni attività ha un nome, una descrizione e una priorità:</span><span class="sxs-lookup"><span data-stu-id="da385-327">The following figure shows the default appearance for a <xref:System.Windows.Controls.ListBox> that is bound to a collection of `Task` objects, where each task has a name, description, and priority:</span></span>

![Casella di riepilogo con aspetto predefinito](media/introduction-to-wpf/wpfintrofigure18.png)

<span data-ttu-id="da385-329">L'aspetto predefinito è quello previsto per un oggetto <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="da385-329">The default appearance is what you would expect from a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="da385-330">L'aspetto predefinito di ciascuna attività, tuttavia, contiene solo il nome dell'attività.</span><span class="sxs-lookup"><span data-stu-id="da385-330">However, the default appearance of each task contains only the task name.</span></span> <span data-ttu-id="da385-331">Per visualizzare il nome, la descrizione e la priorità di un'attività, è necessario modificare l'aspetto predefinito degli elementi elenco associati del controllo <xref:System.Windows.Controls.ListBox> usando un oggetto <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="da385-331">To show the task name, description, and priority, the default appearance of the <xref:System.Windows.Controls.ListBox> control's bound list items must be changed by using a <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="da385-332">Il codice XAML seguente definisce un oggetto <xref:System.Windows.DataTemplate> , che viene applicato a ogni attività tramite l' <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> attributo:</span><span class="sxs-lookup"><span data-stu-id="da385-332">The following XAML defines such a <xref:System.Windows.DataTemplate>, which is applied to each task by using the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> attribute:</span></span>

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="SDKSample.DataTemplateWindow"
  Title="With a Data Template">
  <Window.Resources>
    <!-- Data Template (applied to each bound task item in the task collection) -->
    <DataTemplate x:Key="myTaskTemplate">
      <Border Name="border" BorderBrush="DarkSlateBlue" BorderThickness="2"
        CornerRadius="2" Padding="5" Margin="5">
        <Grid>
          <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
            <RowDefinition/>
          </Grid.RowDefinitions>
          <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" />
            <ColumnDefinition />
          </Grid.ColumnDefinitions>
          <TextBlock Grid.Row="0" Grid.Column="0" Padding="0,0,5,0" Text="Task Name:"/>
          <TextBlock Grid.Row="0" Grid.Column="1" Text="{Binding Path=TaskName}"/>
          <TextBlock Grid.Row="1" Grid.Column="0" Padding="0,0,5,0" Text="Description:"/>
          <TextBlock Grid.Row="1" Grid.Column="1" Text="{Binding Path=Description}"/>
          <TextBlock Grid.Row="2" Grid.Column="0" Padding="0,0,5,0" Text="Priority:"/>
          <TextBlock Grid.Row="2" Grid.Column="1" Text="{Binding Path=Priority}"/>
        </Grid>
      </Border>
    </DataTemplate>
  </Window.Resources>

  <!-- UI -->
  <DockPanel>
    <!-- Title -->
    <Label DockPanel.Dock="Top" FontSize="18" Margin="5" Content="My Task List:"/>

    <!-- Data template is specified by the ItemTemplate attribute -->
    <ListBox
      ItemsSource="{Binding}"
      ItemTemplate="{StaticResource myTaskTemplate}"
      HorizontalContentAlignment="Stretch"
      IsSynchronizedWithCurrentItem="True"
      Margin="5,0,5,5" />

 </DockPanel>
</Window>
```

<span data-ttu-id="da385-333">Nella figura seguente viene illustrato l'effetto di questo codice:</span><span class="sxs-lookup"><span data-stu-id="da385-333">The following figure shows the effect of this code:</span></span>

![Casella di riepilogo che usa un modello di dati](media/introduction-to-wpf/wpfintrofigure19.png)

<span data-ttu-id="da385-335">Si noti che <xref:System.Windows.Controls.ListBox> mantiene il proprio comportamento e l'aspetto complessivo. Solo l'aspetto del contenuto visualizzato dalla casella di riepilogo viene modificato.</span><span class="sxs-lookup"><span data-stu-id="da385-335">Note that the <xref:System.Windows.Controls.ListBox> has retained its behavior and overall appearance; only the appearance of the content being displayed by the list box has changed.</span></span>

<span data-ttu-id="da385-336">Per altre informazioni, vedere [Cenni preliminari sui modelli di dati](data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-336">For more information, see [Data templating overview](data/data-templating-overview.md).</span></span>

### <a name="styles"></a><span data-ttu-id="da385-337">Stili</span><span class="sxs-lookup"><span data-stu-id="da385-337">Styles</span></span>

<span data-ttu-id="da385-338">Gli stili consentono agli sviluppatori e ai progettisti di standardizzare un determinato aspetto del prodotto.</span><span class="sxs-lookup"><span data-stu-id="da385-338">Styles enable developers and designers to standardize on a particular appearance for their product.</span></span> <span data-ttu-id="da385-339">WPF offre un modello di stile avanzato, basato sull'elemento <xref:System.Windows.Style> .</span><span class="sxs-lookup"><span data-stu-id="da385-339">WPF provides a strong style model, the foundation of which is the <xref:System.Windows.Style> element.</span></span> <span data-ttu-id="da385-340">Nell'esempio seguente viene creato uno stile che imposta il colore di sfondo per ogni <xref:System.Windows.Controls.Button> oggetto in una finestra per `Orange` :</span><span class="sxs-lookup"><span data-stu-id="da385-340">The following example creates a style that sets the background color for every <xref:System.Windows.Controls.Button> on a window to `Orange`:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.StyleWindow"
    Title="Styles">
  <!-- Style that will be applied to all buttons -->
  <Style TargetType="{x:Type Button}">
    <Setter Property="Background" Value="Orange" />
    <Setter Property="BorderBrush" Value="Crimson" />
    <Setter Property="FontSize" Value="20" />
    <Setter Property="FontWeight" Value="Bold" />
    <Setter Property="Margin" Value="5" />
  </Style>
  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>

  <!-- This label will not have the style applied to it -->
  <Label>Don't Click Me!</Label>

  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>
</Window>
```

<span data-ttu-id="da385-341">Poiché lo stile ha come destinazione tutti i controlli <xref:System.Windows.Controls.Button>, viene applicato automaticamente a tutti i pulsanti nella finestra, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="da385-341">Because this style targets all <xref:System.Windows.Controls.Button> controls, the style is automatically applied to all the buttons in the window, as shown in the following figure:</span></span>

![Due pulsanti di colore arancione](media/introduction-to-wpf/wpfintrofigure20.png)

<span data-ttu-id="da385-343">Per altre informazioni, vedere [stili e modelli](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-343">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="resources"></a><span data-ttu-id="da385-344">Risorse</span><span class="sxs-lookup"><span data-stu-id="da385-344">Resources</span></span>

<span data-ttu-id="da385-345">I controlli di un'applicazione devono condividere lo stesso aspetto, che può includere qualsiasi elemento dai tipi di carattere e i colori di sfondo ai modelli di controllo e di dati, agli stili.</span><span class="sxs-lookup"><span data-stu-id="da385-345">Controls in an application should share the same appearance, which can include anything from fonts and background colors to control templates, data templates, and styles.</span></span> <span data-ttu-id="da385-346">È possibile usare il supporto WPF per le risorse dell'interfaccia utente per incapsulare queste risorse in un'unica posizione e permettere di usarle nuovamente.</span><span class="sxs-lookup"><span data-stu-id="da385-346">You can use WPF's support for user interface resources to encapsulate these resources in a single location for reuse.</span></span>

<span data-ttu-id="da385-347">L'esempio seguente definisce un colore di sfondo comune condiviso da un oggetto <xref:System.Windows.Controls.Button> e un oggetto <xref:System.Windows.Controls.Label> :</span><span class="sxs-lookup"><span data-stu-id="da385-347">The following example defines a common background color that is shared by a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.Label>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ResourcesWindow"
    Title="Resources Window">

  <!-- Define window-scoped background color resource -->
  <Window.Resources>
    <SolidColorBrush x:Key="defaultBackground" Color="Red" />
  </Window.Resources>

  <!-- Button background is defined by window-scoped resource -->
  <Button Background="{StaticResource defaultBackground}">One Button</Button>

  <!-- Label background is defined by window-scoped resource -->
  <Label Background="{StaticResource defaultBackground}">One Label</Label>
</Window>
```

<span data-ttu-id="da385-348">Questo esempio implementa una risorsa di colore di sfondo usando l'elemento della proprietà `Window.Resources` .</span><span class="sxs-lookup"><span data-stu-id="da385-348">This example implements a background color resource by using the `Window.Resources` property element.</span></span> <span data-ttu-id="da385-349">Questa risorsa è disponibile per tutti gli elementi figlio dell'oggetto <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="da385-349">This resource is available to all children of the <xref:System.Windows.Window>.</span></span> <span data-ttu-id="da385-350">Sono disponibili vari ambiti di risorsa, inclusi quelli riportati di seguito, elencati nell'ordine in cui vengono risolti:</span><span class="sxs-lookup"><span data-stu-id="da385-350">There are a variety of resource scopes, including the following, listed in the order in which they are resolved:</span></span>

1. <span data-ttu-id="da385-351">Un singolo controllo (che usa la proprietà <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> ereditata).</span><span class="sxs-lookup"><span data-stu-id="da385-351">An individual control (using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

2. <span data-ttu-id="da385-352">Un oggetto <xref:System.Windows.Window> o <xref:System.Windows.Controls.Page> (che usa la proprietà <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> ereditata).</span><span class="sxs-lookup"><span data-stu-id="da385-352">A <xref:System.Windows.Window> or a <xref:System.Windows.Controls.Page> (also using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

3. <span data-ttu-id="da385-353">Un oggetto <xref:System.Windows.Application> (che usa la proprietà <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> ).</span><span class="sxs-lookup"><span data-stu-id="da385-353">An <xref:System.Windows.Application> (using the <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> property).</span></span>

<span data-ttu-id="da385-354">La varietà degli ambiti offre flessibilità riguardo alla modalità di definizione e condivisione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="da385-354">The variety of scopes gives you flexibility with respect to the way in which you define and share your resources.</span></span>

<span data-ttu-id="da385-355">In alternativa all'associazione diretta delle risorse a un determinato ambito, è possibile comprimere una o più risorse usando un oggetto <xref:System.Windows.ResourceDictionary> separato a cui è possibile fare riferimento in altre parti di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="da385-355">As an alternative to directly associating your resources with a particular scope, you can package one or more resources by using a separate <xref:System.Windows.ResourceDictionary> that can be referenced in other parts of an application.</span></span> <span data-ttu-id="da385-356">Ad esempio, l'esempio seguente definisce un colore di sfondo predefinito in un dizionario risorse:</span><span class="sxs-lookup"><span data-stu-id="da385-356">For example, the following example defines a default background color in a resource dictionary:</span></span>

```xaml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <!-- Define background color resource -->
  <SolidColorBrush x:Key="defaultBackground" Color="Red" />

  <!-- Define other resources -->
</ResourceDictionary>
```

<span data-ttu-id="da385-357">Nell'esempio seguente viene fatto riferimento al dizionario risorse definito nell'esempio precedente in modo che sia condiviso tra un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="da385-357">The following example references the resource dictionary defined in the previous example so that it is shared across an application:</span></span>

```xaml
<Application
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.App">

  <Application.Resources>
    <ResourceDictionary>
      <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="BackgroundColorResources.xaml"/>
      </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
  </Application.Resources>
</Application>
```

<span data-ttu-id="da385-358">Risorse e dizionari risorse sono la base del supporto di WPF per temi e interfacce.</span><span class="sxs-lookup"><span data-stu-id="da385-358">Resources and resource dictionaries are the foundation of WPF support for themes and skins.</span></span>

<span data-ttu-id="da385-359">Per altre informazioni, vedere [Risorse](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="da385-359">For more information, see [Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="custom-controls"></a><span data-ttu-id="da385-360">Controlli personalizzati</span><span class="sxs-lookup"><span data-stu-id="da385-360">Custom controls</span></span>

<span data-ttu-id="da385-361">Anche se WPF offre un ampio supporto per la personalizzazione, in alcune situazioni i controlli di WPF esistenti potrebbero non soddisfare le necessità di un'applicazione o degli utenti.</span><span class="sxs-lookup"><span data-stu-id="da385-361">Although WPF provides a host of customization support, you may encounter situations where existing WPF controls do not meet the needs of either your application or its users.</span></span> <span data-ttu-id="da385-362">Questo può verificarsi nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="da385-362">This can occur when:</span></span>

- <span data-ttu-id="da385-363">Non è possibile creare l'interfaccia utente richiesta personalizzando l'aspetto delle implementazioni di WPF esistenti.</span><span class="sxs-lookup"><span data-stu-id="da385-363">The user interface that you require cannot be created by customizing the look and feel of existing WPF implementations.</span></span>

- <span data-ttu-id="da385-364">Il comportamento richiesto non è supportato (o non è supportato facilmente) dalle implementazioni di WPF esistenti.</span><span class="sxs-lookup"><span data-stu-id="da385-364">The behavior that you require is not supported (or not easily supported) by existing WPF implementations.</span></span>

<span data-ttu-id="da385-365">A questo punto, è tuttavia possibile sfruttare uno dei tre modelli di WPF per creare un nuovo controllo.</span><span class="sxs-lookup"><span data-stu-id="da385-365">At this point, however, you can take advantage of one of three WPF models to create a new control.</span></span> <span data-ttu-id="da385-366">Ogni modello è destinato a uno scenario specifico e richiede che il controllo personalizzato derivi da una determinata classe di base di WPF.</span><span class="sxs-lookup"><span data-stu-id="da385-366">Each model targets a specific scenario and requires your custom control to derive from a particular WPF base class.</span></span> <span data-ttu-id="da385-367">I tre modelli sono elencati di seguito:</span><span class="sxs-lookup"><span data-stu-id="da385-367">The three models are listed here:</span></span>

- <span data-ttu-id="da385-368">**Modello di controllo utente**.</span><span class="sxs-lookup"><span data-stu-id="da385-368">**User Control Model**.</span></span> <span data-ttu-id="da385-369">Un controllo personalizzato deriva da <xref:System.Windows.Controls.UserControl> ed è composto da uno o più controlli.</span><span class="sxs-lookup"><span data-stu-id="da385-369">A custom control derives from <xref:System.Windows.Controls.UserControl> and is composed of one or more other controls.</span></span>

- <span data-ttu-id="da385-370">**Modello di controllo**.</span><span class="sxs-lookup"><span data-stu-id="da385-370">**Control Model**.</span></span> <span data-ttu-id="da385-371">Un controllo personalizzato deriva da <xref:System.Windows.Controls.Control> e viene usato per compilare implementazioni che separano il comportamento dall'aspetto tramite modelli, come la maggior parte dei controlli di WPF.</span><span class="sxs-lookup"><span data-stu-id="da385-371">A custom control derives from <xref:System.Windows.Controls.Control> and is used to build implementations that separate their behavior from their appearance using templates, much like the majority of WPF controls.</span></span> <span data-ttu-id="da385-372">La derivazione da <xref:System.Windows.Controls.Control> consente una maggiore libertà nella creazione di un'interfaccia utente personalizzata rispetto ai controlli utente, ma può risultare più complessa.</span><span class="sxs-lookup"><span data-stu-id="da385-372">Deriving from <xref:System.Windows.Controls.Control> allows you more freedom for creating a custom user interface than user controls, but it may require more effort.</span></span>

- <span data-ttu-id="da385-373">**Modello di elemento framework**.</span><span class="sxs-lookup"><span data-stu-id="da385-373">**Framework Element Model**.</span></span> <span data-ttu-id="da385-374">Un controllo personalizzato deriva da <xref:System.Windows.FrameworkElement> quando il suo aspetto è definito da logica di rendering personalizzata (non dai modelli).</span><span class="sxs-lookup"><span data-stu-id="da385-374">A custom control derives from <xref:System.Windows.FrameworkElement> when its appearance is defined by custom rendering logic (not templates).</span></span>

<span data-ttu-id="da385-375">L'esempio seguente mostra un controllo su/giù numerico personalizzato che deriva da <xref:System.Windows.Controls.UserControl> :</span><span class="sxs-lookup"><span data-stu-id="da385-375">The following example shows a custom numeric up/down control that derives from <xref:System.Windows.Controls.UserControl>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_33.xaml)]

[!code-csharp[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_34.cs)]
[!code-vb[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_34.vb)]

<span data-ttu-id="da385-376">Nell'esempio seguente viene illustrato il codice XAML necessario per incorporare il controllo utente in un <xref:System.Windows.Window> :</span><span class="sxs-lookup"><span data-stu-id="da385-376">The following example illustrates the XAML that is required to incorporate the user control into a <xref:System.Windows.Window>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlWindowMARKUP1](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_37.xaml)]

<span data-ttu-id="da385-377">La figura seguente mostra il `NumericUpDown` controllo ospitato in un <xref:System.Windows.Window> :</span><span class="sxs-lookup"><span data-stu-id="da385-377">The following figure shows the `NumericUpDown` control hosted in a <xref:System.Windows.Window>:</span></span>

![UserControl personalizzato](media/introduction-to-wpf/wpfintrofigure3.png)

<span data-ttu-id="da385-379">Per altre informazioni sui controlli personalizzati, vedere [Cenni preliminari sulla modifica di controlli](controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da385-379">For more information on custom controls, see [Control authoring overview](controls/control-authoring-overview.md).</span></span>

## <a name="wpf-best-practices"></a><span data-ttu-id="da385-380">Procedure consigliate di WPF</span><span class="sxs-lookup"><span data-stu-id="da385-380">WPF best practices</span></span>

<span data-ttu-id="da385-381">Come per qualsiasi piattaforma di sviluppo, è possibile usare WPF in diversi modi per ottenere il risultato desiderato.</span><span class="sxs-lookup"><span data-stu-id="da385-381">As with any development platform, WPF can be used in a variety of ways to achieve the desired result.</span></span> <span data-ttu-id="da385-382">Per creare applicazioni WPF capaci di fornire l'esperienza utente richiesta e soddisfare le esigenze generali dei destinatari, ci sono procedure consigliate per l'accessibilità, la globalizzazione e localizzazione e le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="da385-382">As a way of ensuring that your WPF applications provide the required user experience and meet the demands of the audience in general, there are recommended best practices for accessibility, globalization and localization, and performance.</span></span> <span data-ttu-id="da385-383">Per altre informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="da385-383">For more information, see:</span></span>

- [<span data-ttu-id="da385-384">Accessibilità</span><span class="sxs-lookup"><span data-stu-id="da385-384">Accessibility</span></span>](../ui-automation/accessibility-best-practices.md)
- [<span data-ttu-id="da385-385">Globalizzazione e localizzazione WPF</span><span class="sxs-lookup"><span data-stu-id="da385-385">WPF globalization and localization</span></span>](advanced/wpf-globalization-and-localization-overview.md)
- [<span data-ttu-id="da385-386">Prestazioni dell'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="da385-386">WPF app performance</span></span>](advanced/optimizing-wpf-application-performance.md)
- [<span data-ttu-id="da385-387">Sicurezza WPF</span><span class="sxs-lookup"><span data-stu-id="da385-387">WPF security</span></span>](security-wpf.md)

## <a name="next-steps"></a><span data-ttu-id="da385-388">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="da385-388">Next steps</span></span>

<span data-ttu-id="da385-389">Abbiamo esaminato le funzionalità chiave di WPF.</span><span class="sxs-lookup"><span data-stu-id="da385-389">We've looked at the key features of WPF.</span></span> <span data-ttu-id="da385-390">Adesso è necessario compilare la prima applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="da385-390">Now it's time to build your first WPF app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="da385-391">Procedura dettagliata: Prima applicazione desktop WPF</span><span class="sxs-lookup"><span data-stu-id="da385-391">Walkthrough: My first WPF desktop app</span></span>](getting-started/walkthrough-my-first-wpf-desktop-application.md)

## <a name="see-also"></a><span data-ttu-id="da385-392">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da385-392">See also</span></span>

- [<span data-ttu-id="da385-393">Guida introduttiva a WPF</span><span class="sxs-lookup"><span data-stu-id="da385-393">Get started with WPF</span></span>](getting-started/index.md)
- [<span data-ttu-id="da385-394">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="da385-394">Windows Presentation Foundation</span></span>](index.md)
- [<span data-ttu-id="da385-395">Risorse della community WPF</span><span class="sxs-lookup"><span data-stu-id="da385-395">WPF community resources</span></span>](getting-started/community-feedback.md)
