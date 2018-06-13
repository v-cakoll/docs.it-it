---
title: Modello di contenuto WPF
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
ms.openlocfilehash: 48e96b04a3459aa18a52624758d5fa2347570fcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558200"
---
# <a name="wpf-content-model"></a><span data-ttu-id="be939-102">Modello di contenuto WPF</span><span class="sxs-lookup"><span data-stu-id="be939-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="be939-103"> è una piattaforma di presentazione che offre numerosi controlli e tipi simili a controlli il cui scopo principale consiste nel visualizzare tipi di contenuto diversi.</span><span class="sxs-lookup"><span data-stu-id="be939-103"> is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="be939-104">Per stabilire quale controllo usare o da quale controllo eseguire la derivazione, è consigliabile comprendere i tipi di oggetti che possono essere visualizzati in modo ottimale da un determinato controllo.</span><span class="sxs-lookup"><span data-stu-id="be939-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="be939-105">Questo argomento riepiloga il modello di contenuto per i controlli e i tipi simili ai controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="be939-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="be939-106">Il modello di contenuto descrive il contenuto che può essere usato in un controllo.</span><span class="sxs-lookup"><span data-stu-id="be939-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="be939-107">Questo argomento include anche un elenco delle proprietà di contenuto per ogni modello di contenuto.</span><span class="sxs-lookup"><span data-stu-id="be939-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="be939-108">Una proprietà di contenuto è una proprietà che viene usata per archiviare il contenuto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="be939-108">A content property is a property that is used to store the content of the object.</span></span>  
  
 
  
<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="be939-109">Classi con contenuto arbitrario</span><span class="sxs-lookup"><span data-stu-id="be939-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="be939-110">Alcuni controlli possono contenere un oggetto di qualsiasi tipo, ad esempio una stringa, un <xref:System.DateTime> oggetto, o un <xref:System.Windows.UIElement> che rappresenta un contenitore per altri elementi.</span><span class="sxs-lookup"><span data-stu-id="be939-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="be939-111">Ad esempio, un <xref:System.Windows.Controls.Button> può contenere un'immagine e testo; o un <xref:System.Windows.Controls.CheckBox> può contenere il valore di <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="be939-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="be939-112"> offre quattro classi in grado di includere contenuto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="be939-112"> has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="be939-113">Nella tabella seguente sono elencate le classi che ereditano da <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="be939-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="be939-114">Classe con contenuto arbitrario</span><span class="sxs-lookup"><span data-stu-id="be939-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="be939-115">Content</span><span class="sxs-lookup"><span data-stu-id="be939-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="be939-116">Un singolo oggetto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="be939-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="be939-117">Un'intestazione e un singolo elemento, che sono entrambi oggetti arbitrari.</span><span class="sxs-lookup"><span data-stu-id="be939-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="be939-118">Una raccolta di oggetti arbitrari.</span><span class="sxs-lookup"><span data-stu-id="be939-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="be939-119">Un'intestazione e una raccolta di elementi, che costituiscono tutti oggetti arbitrari.</span><span class="sxs-lookup"><span data-stu-id="be939-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="be939-120">I controlli che ereditano da queste classi possono contenere lo stesso tipo di contenuto e gestiscono il contenuto nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="be939-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="be939-121">La figura seguente illustra un controllo di ogni modello di contenuto che contiene un'immagine e del testo.</span><span class="sxs-lookup"><span data-stu-id="be939-121">The following illustration shows one control from each content model that contains an image and some text.</span></span>  
  
 <span data-ttu-id="be939-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span><span class="sxs-lookup"><span data-stu-id="be939-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span></span>  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="be939-123">Controlli che contengono un singolo oggetto arbitrario</span><span class="sxs-lookup"><span data-stu-id="be939-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="be939-124">La <xref:System.Windows.Controls.ContentControl> classe contiene un singolo elemento di contenuto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="be939-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="be939-125">Proprietà di contenuto è <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="be939-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="be939-126">I seguenti controlli ereditano <xref:System.Windows.Controls.ContentControl> e utilizzare il modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="be939-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Button>  
  
-   <xref:System.Windows.Controls.Primitives.ButtonBase>  
  
-   <xref:System.Windows.Controls.CheckBox>  
  
-   <xref:System.Windows.Controls.ComboBoxItem>  
  
-   <xref:System.Windows.Controls.ContentControl>  
  
-   <xref:System.Windows.Controls.Frame>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GroupItem>  
  
-   <xref:System.Windows.Controls.Label>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Navigation.NavigationWindow>  
  
-   <xref:System.Windows.Controls.RadioButton>  
  
-   <xref:System.Windows.Controls.Primitives.RepeatButton>  
  
-   <xref:System.Windows.Controls.ScrollViewer>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBarItem>  
  
-   <xref:System.Windows.Controls.Primitives.ToggleButton>  
  
-   <xref:System.Windows.Controls.ToolTip>  
  
-   <xref:System.Windows.Controls.UserControl>  
  
-   <xref:System.Windows.Window>  
  
 <span data-ttu-id="be939-127">La figura seguente mostra quattro pulsanti la cui <xref:System.Windows.Controls.ContentControl.Content%2A> è impostata su una stringa, un <xref:System.DateTime> oggetto, un <xref:System.Windows.Shapes.Rectangle>e un <xref:System.Windows.Controls.Panel> che contiene un <xref:System.Windows.Shapes.Ellipse> e <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="be939-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="be939-128">![Quattro pulsanti](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span><span class="sxs-lookup"><span data-stu-id="be939-128">![Four buttons](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span></span>  
<span data-ttu-id="be939-129">Quattro pulsanti che dispongono di tipi di contenuto diversi</span><span class="sxs-lookup"><span data-stu-id="be939-129">Four buttons that have different types of content</span></span>  
  
 <span data-ttu-id="be939-130">Per un esempio di come impostare il <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà, vedere <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="be939-130">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="be939-131">Controlli che contengono un'intestazione e un singolo oggetto arbitrario</span><span class="sxs-lookup"><span data-stu-id="be939-131">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="be939-132">Il <xref:System.Windows.Controls.HeaderedContentControl> classe eredita da <xref:System.Windows.Controls.ContentControl> e visualizza il contenuto con un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="be939-132">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="be939-133">Eredita la proprietà di contenuto, <xref:System.Windows.Controls.ContentControl.Content%2A>, da <xref:System.Windows.Controls.ContentControl> e definisce la <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> proprietà che è di tipo <xref:System.Object>; pertanto, entrambi possono essere un oggetto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="be939-133">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="be939-134">I seguenti controlli ereditano <xref:System.Windows.Controls.HeaderedContentControl> e utilizzare il modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="be939-134">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="be939-135">Nella figura seguente vengono illustrati due <xref:System.Windows.Controls.TabItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="be939-135">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="be939-136">Il primo <xref:System.Windows.Controls.TabItem> è <xref:System.Windows.UIElement> oggetti come il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="be939-136">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="be939-137">Il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> è impostata su un <xref:System.Windows.Controls.StackPanel> che contiene un <xref:System.Windows.Shapes.Ellipse> e <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="be939-137">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="be939-138">Il <xref:System.Windows.Controls.ContentControl.Content%2A> è impostata su un <xref:System.Windows.Controls.StackPanel> che contiene un <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="be939-138">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="be939-139">Il secondo <xref:System.Windows.Controls.TabItem> è una stringa <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e <xref:System.Windows.Controls.TextBlock> nel <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="be939-139">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 <span data-ttu-id="be939-140">![Controllo TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span><span class="sxs-lookup"><span data-stu-id="be939-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span></span>  
<span data-ttu-id="be939-141">TabControl con tipi diversi nella proprietà Header</span><span class="sxs-lookup"><span data-stu-id="be939-141">TabControl that uses different types in the Header property</span></span>  
  
 <span data-ttu-id="be939-142">Per un esempio di come creare <xref:System.Windows.Controls.TabItem> degli oggetti, vedere <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="be939-142">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="be939-143">Controlli che contengono una raccolta di oggetti arbitrari</span><span class="sxs-lookup"><span data-stu-id="be939-143">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="be939-144">Il <xref:System.Windows.Controls.ItemsControl> classe eredita da <xref:System.Windows.Controls.Control> e può contenere più elementi, ad esempio stringhe, oggetti o altri elementi.</span><span class="sxs-lookup"><span data-stu-id="be939-144">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="be939-145">Le proprietà di contenuto sono <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> e <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="be939-145">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="be939-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> in genere viene utilizzato per popolare il <xref:System.Windows.Controls.ItemsControl> con una raccolta di dati.</span><span class="sxs-lookup"><span data-stu-id="be939-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="be939-147">Se non si desidera utilizzare una raccolta per popolare il <xref:System.Windows.Controls.ItemsControl>, è possibile aggiungere elementi utilizzando il <xref:System.Windows.Controls.ItemsControl.Items%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="be939-147">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="be939-148">I seguenti controlli ereditano <xref:System.Windows.Controls.ItemsControl> e utilizzare il modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="be939-148">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Menu>  
  
-   <xref:System.Windows.Controls.Primitives.MenuBase>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ItemsControl>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.TabControl>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
-   <xref:System.Windows.Controls.Primitives.Selector>  
  
-   <xref:System.Windows.Controls.Primitives.StatusBar>  
  
 <span data-ttu-id="be939-149">La figura seguente mostra un <xref:System.Windows.Controls.ListBox> che contiene i tipi di elementi:</span><span class="sxs-lookup"><span data-stu-id="be939-149">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
-   <span data-ttu-id="be939-150">Una stringa.</span><span class="sxs-lookup"><span data-stu-id="be939-150">A string.</span></span>  
  
-   <span data-ttu-id="be939-151">Oggetto <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="be939-151">A <xref:System.DateTime> object.</span></span>  
  
-   <span data-ttu-id="be939-152">Oggetto <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="be939-152">A <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="be939-153">Oggetto <xref:System.Windows.Controls.Panel> che contiene un <xref:System.Windows.Shapes.Ellipse> e <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="be939-153">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="be939-154">![ListBox con quattro tipi di contenuto](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span><span class="sxs-lookup"><span data-stu-id="be939-154">![ListBox with four types of content](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span></span>  
<span data-ttu-id="be939-155">ListBox con più tipi di oggetti</span><span class="sxs-lookup"><span data-stu-id="be939-155">ListBox that contains multiple types of objects</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="be939-156">Controlli che contengono un'intestazione e una raccolta di oggetti arbitrari</span><span class="sxs-lookup"><span data-stu-id="be939-156">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="be939-157">Il <xref:System.Windows.Controls.HeaderedItemsControl> classe eredita da <xref:System.Windows.Controls.ItemsControl> e può contenere più elementi, ad esempio stringhe, oggetti, o altri elementi e un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="be939-157">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="be939-158">Eredita il <xref:System.Windows.Controls.ItemsControl> , proprietà del contenuto <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, e <xref:System.Windows.Controls.ItemsControl.Items%2A>, e definisce la <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà che può essere un oggetto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="be939-158">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="be939-159">I seguenti controlli ereditano <xref:System.Windows.Controls.HeaderedItemsControl> e utilizzare il modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="be939-159">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="be939-160">Classi che contengono una raccolta di oggetti UIElement</span><span class="sxs-lookup"><span data-stu-id="be939-160">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="be939-161">Il <xref:System.Windows.Controls.Panel> classe posiziona e dispone di figlio <xref:System.Windows.UIElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="be939-161">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="be939-162">Proprietà di contenuto è <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="be939-162">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="be939-163">Le classi seguenti ereditano la <xref:System.Windows.Controls.Panel> classe e utilizzare il modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="be939-163">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.Primitives.TabPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
  
-   <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
  
-   <xref:System.Windows.Controls.Primitives.UniformGrid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="be939-164">Per altre informazioni, vedere [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="be939-164">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="be939-165">Classi che influiscono sull'aspetto di un oggetto UIElement</span><span class="sxs-lookup"><span data-stu-id="be939-165">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="be939-166">Il <xref:System.Windows.Controls.Decorator> classe applica effetti visivi a o attorno a un singolo elemento figlio <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="be939-166">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="be939-167">Proprietà di contenuto è <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="be939-167">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="be939-168">Le seguenti classi ereditano da <xref:System.Windows.Controls.Decorator> e utilizzare il modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="be939-168">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="be939-169">La figura seguente mostra un <xref:System.Windows.Controls.TextBox> che ha (è decorato con) una <xref:System.Windows.Controls.Border> intorno a esso.</span><span class="sxs-lookup"><span data-stu-id="be939-169">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="be939-170">![TextBox con bordo nero](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="be939-170">![TextBox with black border](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="be939-171">TextBlock con bordo nero</span><span class="sxs-lookup"><span data-stu-id="be939-171">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="be939-172">Classi che forniscono feedback visivo su un oggetto UIElement</span><span class="sxs-lookup"><span data-stu-id="be939-172">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="be939-173">La <xref:System.Windows.Documents.Adorner> classe fornisce indicazioni visive a un utente.</span><span class="sxs-lookup"><span data-stu-id="be939-173">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="be939-174">Ad esempio, utilizzare un <xref:System.Windows.Documents.Adorner> aggiungere handle funzionali a elementi o fornire informazioni sullo stato relative a un controllo.</span><span class="sxs-lookup"><span data-stu-id="be939-174">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="be939-175">La <xref:System.Windows.Documents.Adorner> classe fornisce un framework che è possibile creare i propri strumenti decorativi visuali.</span><span class="sxs-lookup"><span data-stu-id="be939-175">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> <span data-ttu-id="be939-176">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non sono inclusi strumenti decorativi implementati.</span><span class="sxs-lookup"><span data-stu-id="be939-176">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] does not provide any implemented adorners.</span></span> <span data-ttu-id="be939-177">Per altre informazioni, vedere [Cenni preliminari sugli strumenti decorativi](../../../../docs/framework/wpf/controls/adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="be939-177">For more information, see [Adorners Overview](../../../../docs/framework/wpf/controls/adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="be939-178">Classi che consentono agli utenti di immettere testo</span><span class="sxs-lookup"><span data-stu-id="be939-178">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="be939-179">In WPF sono disponibili tre controlli primari che consentono agli utenti di immettere testo.</span><span class="sxs-lookup"><span data-stu-id="be939-179">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="be939-180">Ogni controllo determina una visualizzazione diversa del testo.</span><span class="sxs-lookup"><span data-stu-id="be939-180">Each control displays the text differently.</span></span> <span data-ttu-id="be939-181">La tabella seguente elenca questi tre controlli correlati al testo, le relative funzionalità per la visualizzazione di testo, nonché le relative proprietà contenenti il testo del controllo.</span><span class="sxs-lookup"><span data-stu-id="be939-181">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="be939-182">Control</span><span class="sxs-lookup"><span data-stu-id="be939-182">Control</span></span>|<span data-ttu-id="be939-183">Il testo viene visualizzato come</span><span class="sxs-lookup"><span data-stu-id="be939-183">Text is displayed as</span></span>|<span data-ttu-id="be939-184">Proprietà di contenuto</span><span class="sxs-lookup"><span data-stu-id="be939-184">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="be939-185">Testo normale</span><span class="sxs-lookup"><span data-stu-id="be939-185">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="be939-186">Testo formattato</span><span class="sxs-lookup"><span data-stu-id="be939-186">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="be939-187">Testo nascosto (i caratteri sono mascherati)</span><span class="sxs-lookup"><span data-stu-id="be939-187">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="be939-188">Classi che consentono di visualizzare il testo dell'utente</span><span class="sxs-lookup"><span data-stu-id="be939-188">Classes That Display Your Text</span></span>  
 <span data-ttu-id="be939-189">Per la visualizzazione di testo normale o formattato sono disponibili numerose classi.</span><span class="sxs-lookup"><span data-stu-id="be939-189">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="be939-190">È possibile utilizzare <xref:System.Windows.Controls.TextBlock> per visualizzare piccole quantità di testo.</span><span class="sxs-lookup"><span data-stu-id="be939-190">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="be939-191">Se si desidera visualizzare grandi quantità di testo, utilizzare il <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, o <xref:System.Windows.Controls.FlowDocumentScrollViewer> controlli.</span><span class="sxs-lookup"><span data-stu-id="be939-191">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="be939-192">Il <xref:System.Windows.Controls.TextBlock> ha due proprietà di contenuto: <xref:System.Windows.Controls.TextBlock.Text%2A> e <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="be939-192">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="be939-193">Quando si desidera visualizzare il testo che utilizza una formattazione coerente, il <xref:System.Windows.Controls.TextBlock.Text%2A> è spesso la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="be939-193">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="be939-194">Se si prevede di utilizzare il testo con formattazioni diverse, utilizzare il <xref:System.Windows.Controls.TextBlock.Inlines%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="be939-194">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="be939-195">Il <xref:System.Windows.Controls.TextBlock.Inlines%2A> proprietà è una raccolta di <xref:System.Windows.Documents.Inline> gli oggetti che specificano la modalità di formattazione del testo.</span><span class="sxs-lookup"><span data-stu-id="be939-195">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="be939-196">Nella tabella seguente sono elencate le proprietà di contenuto per <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, e <xref:System.Windows.Controls.FlowDocumentScrollViewer> classi.</span><span class="sxs-lookup"><span data-stu-id="be939-196">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="be939-197">Control</span><span class="sxs-lookup"><span data-stu-id="be939-197">Control</span></span>|<span data-ttu-id="be939-198">Proprietà di contenuto</span><span class="sxs-lookup"><span data-stu-id="be939-198">Content property</span></span>|<span data-ttu-id="be939-199">Tipo proprietà di contenuto</span><span class="sxs-lookup"><span data-stu-id="be939-199">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="be939-200">Document</span><span class="sxs-lookup"><span data-stu-id="be939-200">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="be939-201">Document</span><span class="sxs-lookup"><span data-stu-id="be939-201">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="be939-202">Document</span><span class="sxs-lookup"><span data-stu-id="be939-202">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="be939-203">Il <xref:System.Windows.Documents.FlowDocument> implementa il <xref:System.Windows.Documents.IDocumentPaginatorSource> interfaccia; pertanto, è possano portare tutte le tre classi un <xref:System.Windows.Documents.FlowDocument> come contenuto.</span><span class="sxs-lookup"><span data-stu-id="be939-203">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="be939-204">Classi che consentono di formattare il testo dell'utente</span><span class="sxs-lookup"><span data-stu-id="be939-204">Classes That Format Your Text</span></span>  
 <span data-ttu-id="be939-205"><xref:System.Windows.Documents.TextElement> e le relative classi consentono di formattare il testo.</span><span class="sxs-lookup"><span data-stu-id="be939-205"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="be939-206"><xref:System.Windows.Documents.TextElement> gli oggetti contengono e formattare il testo nei <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument> oggetti.</span><span class="sxs-lookup"><span data-stu-id="be939-206"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="be939-207">I due tipi principali di <xref:System.Windows.Documents.TextElement> sono oggetti <xref:System.Windows.Documents.Block> elementi e <xref:System.Windows.Documents.Inline> elementi.</span><span class="sxs-lookup"><span data-stu-id="be939-207">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="be939-208">Oggetto <xref:System.Windows.Documents.Block> elemento rappresenta un blocco di testo, ad esempio un paragrafo o un elenco.</span><span class="sxs-lookup"><span data-stu-id="be939-208">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="be939-209">Un <xref:System.Windows.Documents.Inline> elemento rappresenta una parte del testo in un blocco.</span><span class="sxs-lookup"><span data-stu-id="be939-209">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="be939-210">Molti <xref:System.Windows.Documents.Inline> classi specificano la formattazione del testo in cui vengono applicati.</span><span class="sxs-lookup"><span data-stu-id="be939-210">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="be939-211">Ogni <xref:System.Windows.Documents.TextElement> ha il proprio modello di contenuto.</span><span class="sxs-lookup"><span data-stu-id="be939-211">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="be939-212">Per altre informazioni, vedere il [Cenni preliminari sul modello di contenuto di TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="be939-212">For more information, see the [TextElement Content Model Overview](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be939-213">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be939-213">See Also</span></span>  
 [<span data-ttu-id="be939-214">Avanzate</span><span class="sxs-lookup"><span data-stu-id="be939-214">Advanced</span></span>](../../../../docs/framework/wpf/advanced/index.md)
