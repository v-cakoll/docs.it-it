---
title: Modello di contenuto
ms.date: 03/30/2017
helpviewer_keywords:
- UIElement class [WPF], displaying content
- content model [WPF], controls
- controls [WPF], displaying text
- content display [WPF], controls
- controls [WPF], formatting text
- displaying content [WPF]
- arbitrary content classes [WPF], content model
- ContentControl class [WPF], displaying content
ms.assetid: 214da5ef-547a-4cf8-9b07-4aa8a0e52cdd
ms.openlocfilehash: ec4e96c0883489135b77f09a3c19f144cb4d30bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187397"
---
# <a name="wpf-content-model"></a><span data-ttu-id="af975-102">Modello di contenuto WPF</span><span class="sxs-lookup"><span data-stu-id="af975-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="af975-103">è una piattaforma di presentazione che offre numerosi controlli e tipi simili a controlli il cui scopo principale consiste nel visualizzare tipi di contenuto diversi.</span><span class="sxs-lookup"><span data-stu-id="af975-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="af975-104">Per stabilire quale controllo usare o da quale controllo eseguire la derivazione, è consigliabile comprendere i tipi di oggetti che possono essere visualizzati in modo ottimale da un determinato controllo.</span><span class="sxs-lookup"><span data-stu-id="af975-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="af975-105">Questo argomento riepiloga il modello di contenuto per i controlli e i tipi simili ai controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af975-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="af975-106">Il modello di contenuto descrive il contenuto che può essere usato in un controllo.</span><span class="sxs-lookup"><span data-stu-id="af975-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="af975-107">Questo argomento include anche un elenco delle proprietà di contenuto per ogni modello di contenuto.</span><span class="sxs-lookup"><span data-stu-id="af975-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="af975-108">Una proprietà di contenuto è una proprietà che viene usata per archiviare il contenuto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="af975-108">A content property is a property that is used to store the content of the object.</span></span>  

<a name="classes_that_contain_arbitrary_content"></a>
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="af975-109">Classi con contenuto arbitrario</span><span class="sxs-lookup"><span data-stu-id="af975-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="af975-110">Alcuni controlli possono contenere un oggetto di qualsiasi <xref:System.DateTime> tipo, <xref:System.Windows.UIElement> ad esempio una stringa, un oggetto o un oggetto che è un contenitore per gli elementi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="af975-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="af975-111">Ad esempio, <xref:System.Windows.Controls.Button> un può contenere un'immagine e del testo; o <xref:System.Windows.Controls.CheckBox> un può contenere il valore di <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="af975-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="af975-112">offre quattro classi in grado di includere contenuto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="af975-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="af975-113">Nella tabella seguente sono elencate <xref:System.Windows.Controls.Control>le classi , che ereditano da .</span><span class="sxs-lookup"><span data-stu-id="af975-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="af975-114">Classe con contenuto arbitrario</span><span class="sxs-lookup"><span data-stu-id="af975-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="af975-115">Contenuto</span><span class="sxs-lookup"><span data-stu-id="af975-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="af975-116">Un singolo oggetto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="af975-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="af975-117">Un'intestazione e un singolo elemento, che sono entrambi oggetti arbitrari.</span><span class="sxs-lookup"><span data-stu-id="af975-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="af975-118">Una raccolta di oggetti arbitrari.</span><span class="sxs-lookup"><span data-stu-id="af975-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="af975-119">Un'intestazione e una raccolta di elementi, che costituiscono tutti oggetti arbitrari.</span><span class="sxs-lookup"><span data-stu-id="af975-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="af975-120">I controlli che ereditano da queste classi possono contenere lo stesso tipo di contenuto e gestiscono il contenuto nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="af975-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="af975-121">Nella figura seguente viene illustrato un controllo da ogni modello di contenuto che contiene un'immagine e del testo:The following illustration shows one control from each content model that contains an image and some text:</span><span class="sxs-lookup"><span data-stu-id="af975-121">The following illustration shows one control from each content model that contains an image and some text:</span></span>  
  
 ![Screenshot che mostra quattro controlli diversi, uno per ogni modello di contenuto.](./media/wpf-content-model/control-content-model-image-text.png)  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="af975-123">Controlli che contengono un singolo oggetto arbitrario</span><span class="sxs-lookup"><span data-stu-id="af975-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="af975-124">La <xref:System.Windows.Controls.ContentControl> classe contiene una singola parte di contenuto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="af975-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="af975-125">La proprietà <xref:System.Windows.Controls.ContentControl.Content%2A>content è .</span><span class="sxs-lookup"><span data-stu-id="af975-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="af975-126">I controlli seguenti <xref:System.Windows.Controls.ContentControl> ereditano da e utilizzano il relativo modello di contenuto:The following controls inherit from and use its content model:</span><span class="sxs-lookup"><span data-stu-id="af975-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Button>  
  
- <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
- <xref:System.Windows.Controls.CheckBox>  
  
- <xref:System.Windows.Controls.ComboBoxItem>  
  
- <xref:System.Windows.Controls.ContentControl>  
  
- <xref:System.Windows.Controls.Frame>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GroupItem>  
  
- <xref:System.Windows.Controls.Label>  
  
- <xref:System.Windows.Controls.ListBoxItem>  
  
- <xref:System.Windows.Controls.ListViewItem>  
  
- <xref:System.Windows.Navigation.NavigationWindow>  
  
- <xref:System.Windows.Controls.RadioButton>  
  
- <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
- <xref:System.Windows.Controls.ScrollViewer>  
  
- <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
- <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
- <xref:System.Windows.Controls.ToolTip>  
  
- <xref:System.Windows.Controls.UserControl>  
  
- <xref:System.Windows.Window>  
  
 <span data-ttu-id="af975-127">Nella figura seguente vengono <xref:System.Windows.Controls.ContentControl.Content%2A> illustrati quattro pulsanti <xref:System.DateTime> il <xref:System.Windows.Shapes.Rectangle>cui è <xref:System.Windows.Controls.Panel> impostato <xref:System.Windows.Shapes.Ellipse> su <xref:System.Windows.Controls.TextBlock>una stringa, un oggetto, un oggetto e un che contiene un oggetto e un :</span><span class="sxs-lookup"><span data-stu-id="af975-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>:</span></span>  
  
 ![Screenshot che mostra quattro pulsanti con tipi di contenuto diversi.](./media/wpf-content-model/control-content-model-buttons.png)  
  
 <span data-ttu-id="af975-129">Per un esempio di <xref:System.Windows.Controls.ContentControl.Content%2A> impostazione <xref:System.Windows.Controls.ContentControl>della proprietà, vedere .</span><span class="sxs-lookup"><span data-stu-id="af975-129">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="af975-130">Controlli che contengono un'intestazione e un singolo oggetto arbitrario</span><span class="sxs-lookup"><span data-stu-id="af975-130">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="af975-131">La <xref:System.Windows.Controls.HeaderedContentControl> classe eredita <xref:System.Windows.Controls.ContentControl> da e visualizza il contenuto con un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="af975-131">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="af975-132">Eredita <xref:System.Windows.Controls.ContentControl.Content%2A>la proprietà content, <xref:System.Windows.Controls.ContentControl> , da <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e definisce <xref:System.Object>la proprietà di tipo ; pertanto, entrambi possono essere un oggetto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="af975-132">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="af975-133">I controlli seguenti <xref:System.Windows.Controls.HeaderedContentControl> ereditano da e utilizzano il relativo modello di contenuto:The following controls inherit from and use its content model:</span><span class="sxs-lookup"><span data-stu-id="af975-133">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Expander>  
  
- <xref:System.Windows.Controls.GroupBox>  
  
- <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="af975-134">Nella figura seguente <xref:System.Windows.Controls.TabItem> vengono illustrati due oggetti.</span><span class="sxs-lookup"><span data-stu-id="af975-134">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="af975-135">Il <xref:System.Windows.Controls.TabItem> primo <xref:System.Windows.UIElement> dispone <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> di <xref:System.Windows.Controls.ContentControl.Content%2A>oggetti come il e il .</span><span class="sxs-lookup"><span data-stu-id="af975-135">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="af975-136"><xref:System.Windows.Controls.HeaderedContentControl.Header%2A> L'oggetto è <xref:System.Windows.Controls.StackPanel> impostato <xref:System.Windows.Shapes.Ellipse> su <xref:System.Windows.Controls.TextBlock>a che contiene un e un oggetto .</span><span class="sxs-lookup"><span data-stu-id="af975-136">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="af975-137"><xref:System.Windows.Controls.ContentControl.Content%2A> L'oggetto è <xref:System.Windows.Controls.StackPanel> impostato <xref:System.Windows.Controls.TextBlock> su <xref:System.Windows.Controls.Label>a che contiene a e un oggetto .</span><span class="sxs-lookup"><span data-stu-id="af975-137">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="af975-138">Il <xref:System.Windows.Controls.TabItem> secondo ha una <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> stringa <xref:System.Windows.Controls.TextBlock> in <xref:System.Windows.Controls.ContentControl.Content%2A>e a nel file .</span><span class="sxs-lookup"><span data-stu-id="af975-138">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 ![TabControl che utilizza tipi diversi nel Header proprietà.](./media/wpf-content-model/control-content-model-tab.png)  
  
 <span data-ttu-id="af975-140">Per un esempio di <xref:System.Windows.Controls.TabItem> creazione <xref:System.Windows.Controls.HeaderedContentControl>di oggetti, vedere .</span><span class="sxs-lookup"><span data-stu-id="af975-140">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="af975-141">Controlli che contengono una raccolta di oggetti arbitrari</span><span class="sxs-lookup"><span data-stu-id="af975-141">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="af975-142">La <xref:System.Windows.Controls.ItemsControl> classe eredita <xref:System.Windows.Controls.Control> da e può contenere più elementi, ad esempio stringhe, oggetti o altri elementi.</span><span class="sxs-lookup"><span data-stu-id="af975-142">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="af975-143">Le proprietà <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> di <xref:System.Windows.Controls.ItemsControl.Items%2A>contenuto sono e .</span><span class="sxs-lookup"><span data-stu-id="af975-143">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="af975-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>viene in genere <xref:System.Windows.Controls.ItemsControl> utilizzato per popolare l'oggetto con una raccolta di dati.</span><span class="sxs-lookup"><span data-stu-id="af975-144"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="af975-145">Se non si desidera utilizzare un <xref:System.Windows.Controls.ItemsControl>insieme per popolare l'oggetto , è possibile aggiungere elementi utilizzando la <xref:System.Windows.Controls.ItemsControl.Items%2A> proprietà .</span><span class="sxs-lookup"><span data-stu-id="af975-145">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="af975-146">I controlli seguenti <xref:System.Windows.Controls.ItemsControl> ereditano da e utilizzano il relativo modello di contenuto:The following controls inherit from and use its content model:</span><span class="sxs-lookup"><span data-stu-id="af975-146">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Menu>  
  
- <xref:System.Windows.Controls.Primitives.MenuBase>  
  
- <xref:System.Windows.Controls.ContextMenu>  
  
- <xref:System.Windows.Controls.ComboBox>  
  
- <xref:System.Windows.Controls.ItemsControl>  
  
- <xref:System.Windows.Controls.ListBox>  
  
- <xref:System.Windows.Controls.ListView>  
  
- <xref:System.Windows.Controls.TabControl>  
  
- <xref:System.Windows.Controls.TreeView>  
  
- <xref:System.Windows.Controls.Primitives.Selector>  
  
- <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="af975-147">Nella figura seguente <xref:System.Windows.Controls.ListBox> viene illustrato un che contiene questi tipi di elementi:</span><span class="sxs-lookup"><span data-stu-id="af975-147">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
- <span data-ttu-id="af975-148">Stringa.</span><span class="sxs-lookup"><span data-stu-id="af975-148">A string.</span></span>  
  
- <span data-ttu-id="af975-149">Oggetto <xref:System.DateTime> .</span><span class="sxs-lookup"><span data-stu-id="af975-149">A <xref:System.DateTime> object.</span></span>  
  
- <span data-ttu-id="af975-150"><xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="af975-150">A <xref:System.Windows.UIElement>.</span></span>  
  
- <span data-ttu-id="af975-151">Oggetto <xref:System.Windows.Controls.Panel> che <xref:System.Windows.Shapes.Ellipse> contiene <xref:System.Windows.Controls.TextBlock>un e un oggetto .</span><span class="sxs-lookup"><span data-stu-id="af975-151">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 ![Screenshot che mostra un controllo ListBox con quattro tipi di contenuto.](./media/wpf-content-model/control-content-model-listbox.png)  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="af975-153">Controlli che contengono un'intestazione e una raccolta di oggetti arbitrari</span><span class="sxs-lookup"><span data-stu-id="af975-153">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="af975-154">La <xref:System.Windows.Controls.HeaderedItemsControl> classe eredita <xref:System.Windows.Controls.ItemsControl> da e può contenere più elementi, ad esempio stringhe, oggetti o altri elementi e un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="af975-154">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="af975-155">Eredita le <xref:System.Windows.Controls.ItemsControl> proprietà di <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>contenuto, , e <xref:System.Windows.Controls.ItemsControl.Items%2A> <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> , e definisce la proprietà che può essere un oggetto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="af975-155">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="af975-156">I controlli seguenti <xref:System.Windows.Controls.HeaderedItemsControl> ereditano da e utilizzano il relativo modello di contenuto:The following controls inherit from and use its content model:</span><span class="sxs-lookup"><span data-stu-id="af975-156">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.MenuItem>  
  
- <xref:System.Windows.Controls.ToolBar>  
  
- <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="af975-157">Classi che contengono una raccolta di oggetti UIElement</span><span class="sxs-lookup"><span data-stu-id="af975-157">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="af975-158">La <xref:System.Windows.Controls.Panel> classe posiziona e <xref:System.Windows.UIElement> dispone gli oggetti figlio.</span><span class="sxs-lookup"><span data-stu-id="af975-158">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="af975-159">La proprietà <xref:System.Windows.Controls.Panel.Children%2A>content è .</span><span class="sxs-lookup"><span data-stu-id="af975-159">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="af975-160">Le classi seguenti <xref:System.Windows.Controls.Panel> ereditano dalla classe e utilizzano il relativo modello di contenuto:The following classes inherit from the class and use its content model:</span><span class="sxs-lookup"><span data-stu-id="af975-160">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
- <xref:System.Windows.Controls.Canvas>  
  
- <xref:System.Windows.Controls.DockPanel>  
  
- <xref:System.Windows.Controls.Grid>  
  
- <xref:System.Windows.Controls.Primitives.TabPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
- <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
- <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
- <xref:System.Windows.Controls.StackPanel>  
  
- <xref:System.Windows.Controls.VirtualizingPanel>  
  
- <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
- <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="af975-161">Per altre informazioni, vedere [Cenni preliminari sugli elementi Panel](panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="af975-161">For more information, see [Panels Overview](panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="af975-162">Classi che influiscono sull'aspetto di un oggetto UIElement</span><span class="sxs-lookup"><span data-stu-id="af975-162">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="af975-163">La <xref:System.Windows.Controls.Decorator> classe applica effetti visivi su <xref:System.Windows.UIElement>o intorno a un singolo figlio .</span><span class="sxs-lookup"><span data-stu-id="af975-163">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="af975-164">La proprietà <xref:System.Windows.Controls.Decorator.Child%2A>content è .</span><span class="sxs-lookup"><span data-stu-id="af975-164">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="af975-165">Le classi seguenti <xref:System.Windows.Controls.Decorator> ereditano da e utilizzano il relativo modello di contenuto:The following classes inherit from and use its content model:</span><span class="sxs-lookup"><span data-stu-id="af975-165">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
- <xref:System.Windows.Documents.AdornerDecorator>  
  
- <xref:System.Windows.Controls.Border>  
  
- <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
- <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
- <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
- <xref:System.Windows.Controls.InkPresenter>  
  
- <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
- <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
- <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="af975-166">Nella figura seguente <xref:System.Windows.Controls.TextBox> viene illustrato un che <xref:System.Windows.Controls.Border> ha (è decorato con) un intorno ad esso.</span><span class="sxs-lookup"><span data-stu-id="af975-166">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="af975-167">![TextBox con bordo nero](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="af975-167">![TextBox with black border](./media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="af975-168">TextBlock con bordo nero</span><span class="sxs-lookup"><span data-stu-id="af975-168">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="af975-169">Classi che forniscono feedback visivo su un oggetto UIElement</span><span class="sxs-lookup"><span data-stu-id="af975-169">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="af975-170">La <xref:System.Windows.Documents.Adorner> classe fornisce segnali visivi a un utente.</span><span class="sxs-lookup"><span data-stu-id="af975-170">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="af975-171">Ad esempio, <xref:System.Windows.Documents.Adorner> utilizzare un oggetto per aggiungere handle funzionali agli elementi o fornire informazioni sullo stato di un controllo.</span><span class="sxs-lookup"><span data-stu-id="af975-171">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="af975-172">La <xref:System.Windows.Documents.Adorner> classe fornisce un framework in modo che è possibile creare strumenti decorativi visuali personalizzati.</span><span class="sxs-lookup"><span data-stu-id="af975-172">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> <span data-ttu-id="af975-173">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non sono inclusi strumenti decorativi implementati.</span><span class="sxs-lookup"><span data-stu-id="af975-173">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] does not provide any implemented adorners.</span></span> <span data-ttu-id="af975-174">Per altre informazioni, vedere [Cenni preliminari sugli strumenti decorativi](adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="af975-174">For more information, see [Adorners Overview](adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="af975-175">Classi che consentono agli utenti di immettere testo</span><span class="sxs-lookup"><span data-stu-id="af975-175">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="af975-176">In WPF sono disponibili tre controlli primari che consentono agli utenti di immettere testo.</span><span class="sxs-lookup"><span data-stu-id="af975-176">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="af975-177">Ogni controllo determina una visualizzazione diversa del testo.</span><span class="sxs-lookup"><span data-stu-id="af975-177">Each control displays the text differently.</span></span> <span data-ttu-id="af975-178">La tabella seguente elenca questi tre controlli correlati al testo, le relative funzionalità per la visualizzazione di testo, nonché le relative proprietà contenenti il testo del controllo.</span><span class="sxs-lookup"><span data-stu-id="af975-178">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="af975-179">Controllo</span><span class="sxs-lookup"><span data-stu-id="af975-179">Control</span></span>|<span data-ttu-id="af975-180">Il testo viene visualizzato come</span><span class="sxs-lookup"><span data-stu-id="af975-180">Text is displayed as</span></span>|<span data-ttu-id="af975-181">Proprietà di contenuto</span><span class="sxs-lookup"><span data-stu-id="af975-181">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="af975-182">Testo normale</span><span class="sxs-lookup"><span data-stu-id="af975-182">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="af975-183">Testo formattato</span><span class="sxs-lookup"><span data-stu-id="af975-183">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="af975-184">Testo nascosto (i caratteri sono mascherati)</span><span class="sxs-lookup"><span data-stu-id="af975-184">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>
## <a name="classes-that-display-your-text"></a><span data-ttu-id="af975-185">Classi che consentono di visualizzare il testo dell'utente</span><span class="sxs-lookup"><span data-stu-id="af975-185">Classes That Display Your Text</span></span>  
 <span data-ttu-id="af975-186">Per la visualizzazione di testo normale o formattato sono disponibili numerose classi.</span><span class="sxs-lookup"><span data-stu-id="af975-186">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="af975-187">È possibile <xref:System.Windows.Controls.TextBlock> utilizzare per visualizzare piccole quantità di testo.</span><span class="sxs-lookup"><span data-stu-id="af975-187">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="af975-188">Se si desidera visualizzare grandi quantità di <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentPageViewer>testo, <xref:System.Windows.Controls.FlowDocumentScrollViewer> utilizzare i controlli , o .</span><span class="sxs-lookup"><span data-stu-id="af975-188">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="af975-189">Il <xref:System.Windows.Controls.TextBlock> dispone di <xref:System.Windows.Controls.TextBlock.Text%2A> due <xref:System.Windows.Controls.TextBlock.Inlines%2A>proprietà di contenuto: e .</span><span class="sxs-lookup"><span data-stu-id="af975-189">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="af975-190">Quando si desidera visualizzare testo che <xref:System.Windows.Controls.TextBlock.Text%2A> utilizza una formattazione coerente, la proprietà è spesso la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="af975-190">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="af975-191">Se si prevede di utilizzare una formattazione diversa in tutto il testo, utilizzare la <xref:System.Windows.Controls.TextBlock.Inlines%2A> proprietà .</span><span class="sxs-lookup"><span data-stu-id="af975-191">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="af975-192">La <xref:System.Windows.Controls.TextBlock.Inlines%2A> proprietà è <xref:System.Windows.Documents.Inline> una raccolta di oggetti che specificano come formattare il testo.</span><span class="sxs-lookup"><span data-stu-id="af975-192">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="af975-193">Nella tabella seguente sono <xref:System.Windows.Controls.FlowDocumentReader>elencate <xref:System.Windows.Controls.FlowDocumentPageViewer>le <xref:System.Windows.Controls.FlowDocumentScrollViewer> proprietà di contenuto per le classi , e .</span><span class="sxs-lookup"><span data-stu-id="af975-193">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="af975-194">Controllo</span><span class="sxs-lookup"><span data-stu-id="af975-194">Control</span></span>|<span data-ttu-id="af975-195">Proprietà di contenuto</span><span class="sxs-lookup"><span data-stu-id="af975-195">Content property</span></span>|<span data-ttu-id="af975-196">Tipo proprietà di contenuto</span><span class="sxs-lookup"><span data-stu-id="af975-196">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="af975-197">Document</span><span class="sxs-lookup"><span data-stu-id="af975-197">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="af975-198">Document</span><span class="sxs-lookup"><span data-stu-id="af975-198">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="af975-199">Document</span><span class="sxs-lookup"><span data-stu-id="af975-199">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="af975-200">Implementa <xref:System.Windows.Documents.FlowDocument> l'interfaccia; <xref:System.Windows.Documents.IDocumentPaginatorSource> pertanto, tutte e <xref:System.Windows.Documents.FlowDocument> tre le classi possono prendere un come contenuto.</span><span class="sxs-lookup"><span data-stu-id="af975-200">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>
## <a name="classes-that-format-your-text"></a><span data-ttu-id="af975-201">Classi che consentono di formattare il testo dell'utente</span><span class="sxs-lookup"><span data-stu-id="af975-201">Classes That Format Your Text</span></span>  
 <span data-ttu-id="af975-202"><xref:System.Windows.Documents.TextElement>e le classi correlate consentono di formattare il testo.</span><span class="sxs-lookup"><span data-stu-id="af975-202"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="af975-203"><xref:System.Windows.Documents.TextElement>oggetti contengono e <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Documents.FlowDocument> formattano il testo e gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="af975-203"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="af975-204">I due tipi <xref:System.Windows.Documents.TextElement> principali <xref:System.Windows.Documents.Block> di <xref:System.Windows.Documents.Inline> oggetti sono elementi ed elementi.</span><span class="sxs-lookup"><span data-stu-id="af975-204">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="af975-205">Un <xref:System.Windows.Documents.Block> elemento rappresenta un blocco di testo, ad esempio un paragrafo o un elenco.</span><span class="sxs-lookup"><span data-stu-id="af975-205">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="af975-206">Un <xref:System.Windows.Documents.Inline> elemento rappresenta una parte di testo in un blocco.</span><span class="sxs-lookup"><span data-stu-id="af975-206">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="af975-207">Molte <xref:System.Windows.Documents.Inline> classi specificano la formattazione per il testo a cui vengono applicate.</span><span class="sxs-lookup"><span data-stu-id="af975-207">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="af975-208">Ognuno <xref:System.Windows.Documents.TextElement> ha il proprio modello di contenuto.</span><span class="sxs-lookup"><span data-stu-id="af975-208">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="af975-209">Per altre informazioni, vedere il [Cenni preliminari sul modello di contenuto di TextElement](../advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="af975-209">For more information, see the [TextElement Content Model Overview](../advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af975-210">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af975-210">See also</span></span>

- [<span data-ttu-id="af975-211">Avanzate</span><span class="sxs-lookup"><span data-stu-id="af975-211">Advanced</span></span>](../advanced/index.md)
