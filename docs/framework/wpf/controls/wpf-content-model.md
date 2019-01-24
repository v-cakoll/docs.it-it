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
ms.openlocfilehash: 751cbcc3a3b70f0937a8fe84c0fad5d8771a32ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718156"
---
# <a name="wpf-content-model"></a><span data-ttu-id="3ecfe-102">Modello di contenuto WPF</span><span class="sxs-lookup"><span data-stu-id="3ecfe-102">WPF Content Model</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="3ecfe-103">è una piattaforma di presentazione che offre numerosi controlli e tipi simili a controlli il cui scopo principale consiste nel visualizzare tipi di contenuto diversi.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-103">is a presentation platform that provides many controls and control-like types whose primary purpose is to display different types of content.</span></span> <span data-ttu-id="3ecfe-104">Per stabilire quale controllo usare o da quale controllo eseguire la derivazione, è consigliabile comprendere i tipi di oggetti che possono essere visualizzati in modo ottimale da un determinato controllo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-104">To determine which control to use or which control to derive from, you should understand the kinds of objects a particular control can best display.</span></span>  
  
 <span data-ttu-id="3ecfe-105">Questo argomento riepiloga il modello di contenuto per i controlli e i tipi simili ai controlli [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ecfe-105">This topic summarizes the content model for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control and control-like types.</span></span> <span data-ttu-id="3ecfe-106">Il modello di contenuto descrive il contenuto che può essere usato in un controllo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-106">The content model describes what content can be used in a control.</span></span> <span data-ttu-id="3ecfe-107">Questo argomento include anche un elenco delle proprietà di contenuto per ogni modello di contenuto.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-107">This topic also lists the content properties for each content model.</span></span> <span data-ttu-id="3ecfe-108">Una proprietà di contenuto è una proprietà che viene usata per archiviare il contenuto dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-108">A content property is a property that is used to store the content of the object.</span></span>  
  
 
  
<a name="classes_that_contain_arbitrary_content"></a>   
## <a name="classes-that-contain-arbitrary-content"></a><span data-ttu-id="3ecfe-109">Classi con contenuto arbitrario</span><span class="sxs-lookup"><span data-stu-id="3ecfe-109">Classes That Contain Arbitrary Content</span></span>  
 <span data-ttu-id="3ecfe-110">Alcuni controlli possono contenere un oggetto di qualsiasi tipo, ad esempio una stringa, un <xref:System.DateTime> oggetto, o un <xref:System.Windows.UIElement> vale a dire un contenitore per altri elementi.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-110">Some controls can contain an object of any type, such as a string, a <xref:System.DateTime> object, or a <xref:System.Windows.UIElement> that is a container for additional items.</span></span> <span data-ttu-id="3ecfe-111">Ad esempio, un <xref:System.Windows.Controls.Button> può contenere un'immagine e del testo, o un <xref:System.Windows.Controls.CheckBox> può contenere il valore di <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-111">For example, a <xref:System.Windows.Controls.Button> can contain an image and some text; or a <xref:System.Windows.Controls.CheckBox> can contain the value of <xref:System.DateTime.Now%2A?displayProperty=nameWithType>.</span></span>  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="3ecfe-112">offre quattro classi in grado di includere contenuto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-112">has four classes that can contain arbitrary content.</span></span> <span data-ttu-id="3ecfe-113">La tabella seguente elenca le classi che ereditano da <xref:System.Windows.Controls.Control>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-113">The following table lists the classes, which inherit from <xref:System.Windows.Controls.Control>.</span></span>  
  
|<span data-ttu-id="3ecfe-114">Classe con contenuto arbitrario</span><span class="sxs-lookup"><span data-stu-id="3ecfe-114">Class that contains arbitrary content</span></span>|<span data-ttu-id="3ecfe-115">Content</span><span class="sxs-lookup"><span data-stu-id="3ecfe-115">Content</span></span>|  
|-------------------------------------------|-------------|  
|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="3ecfe-116">Un singolo oggetto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-116">A single arbitrary object.</span></span>|  
|<xref:System.Windows.Controls.HeaderedContentControl>|<span data-ttu-id="3ecfe-117">Un'intestazione e un singolo elemento, che sono entrambi oggetti arbitrari.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-117">A header and a single item, both of which are arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.ItemsControl>|<span data-ttu-id="3ecfe-118">Una raccolta di oggetti arbitrari.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-118">A collection of arbitrary objects.</span></span>|  
|<xref:System.Windows.Controls.HeaderedItemsControl>|<span data-ttu-id="3ecfe-119">Un'intestazione e una raccolta di elementi, che costituiscono tutti oggetti arbitrari.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-119">A header and a collection of items, all of which are arbitrary objects.</span></span>|  
  
 <span data-ttu-id="3ecfe-120">I controlli che ereditano da queste classi possono contenere lo stesso tipo di contenuto e gestiscono il contenuto nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-120">Controls that inherit from these classes can contain the same type of content and treat the content in the same way.</span></span> <span data-ttu-id="3ecfe-121">La figura seguente illustra un controllo di ogni modello di contenuto che contiene un'immagine e del testo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-121">The following illustration shows one control from each content model that contains an image and some text.</span></span>  
  
 <span data-ttu-id="3ecfe-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span><span class="sxs-lookup"><span data-stu-id="3ecfe-122">![Button, GroupBox, Listbax, TreeViewItem](../../../../docs/framework/wpf/controls/media/controlcontentmodelimagetextinto.PNG "ControlContentModelImageTextInto")</span></span>  
  
### <a name="controls-that-contain-a-single-arbitrary-object"></a><span data-ttu-id="3ecfe-123">Controlli che contengono un singolo oggetto arbitrario</span><span class="sxs-lookup"><span data-stu-id="3ecfe-123">Controls That Contain a Single Arbitrary Object</span></span>  
 <span data-ttu-id="3ecfe-124">Il <xref:System.Windows.Controls.ContentControl> classe contiene un singolo elemento di contenuto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-124">The <xref:System.Windows.Controls.ContentControl> class contains a single piece of arbitrary content.</span></span> <span data-ttu-id="3ecfe-125">Proprietà di contenuto corrispondente è <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-125">Its content property is <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="3ecfe-126">I controlli seguenti ereditano da <xref:System.Windows.Controls.ContentControl> e usano il corrispondente modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="3ecfe-126">The following controls inherit from <xref:System.Windows.Controls.ContentControl> and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="3ecfe-127">La figura seguente illustra quattro pulsanti la cui <xref:System.Windows.Controls.ContentControl.Content%2A> è impostata su una stringa, un <xref:System.DateTime> oggetto, un <xref:System.Windows.Shapes.Rectangle>e un <xref:System.Windows.Controls.Panel> che contiene un' <xref:System.Windows.Shapes.Ellipse> e un <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-127">The following illustration shows four buttons whose <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a string, a <xref:System.DateTime> object, a <xref:System.Windows.Shapes.Rectangle>, and a <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="3ecfe-128">![Quattro pulsanti](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span><span class="sxs-lookup"><span data-stu-id="3ecfe-128">![Four buttons](../../../../docs/framework/wpf/controls/media/controlcontentmodelbuttons.PNG "ControlContentModelButtons")</span></span>  
<span data-ttu-id="3ecfe-129">Quattro pulsanti che dispongono di tipi di contenuto diversi</span><span class="sxs-lookup"><span data-stu-id="3ecfe-129">Four buttons that have different types of content</span></span>  
  
 <span data-ttu-id="3ecfe-130">Per un esempio di come impostare il <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà, vedere <xref:System.Windows.Controls.ContentControl>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-130">For an example of how to set the <xref:System.Windows.Controls.ContentControl.Content%2A> property, see <xref:System.Windows.Controls.ContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-single-arbitrary-object"></a><span data-ttu-id="3ecfe-131">Controlli che contengono un'intestazione e un singolo oggetto arbitrario</span><span class="sxs-lookup"><span data-stu-id="3ecfe-131">Controls That Contain a Header and a Single Arbitrary Object</span></span>  
 <span data-ttu-id="3ecfe-132">Il <xref:System.Windows.Controls.HeaderedContentControl> classe eredita da <xref:System.Windows.Controls.ContentControl> e visualizza il contenuto con un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-132">The <xref:System.Windows.Controls.HeaderedContentControl> class inherits from <xref:System.Windows.Controls.ContentControl> and displays content with a header.</span></span> <span data-ttu-id="3ecfe-133">Eredita la proprietà di contenuto <xref:System.Windows.Controls.ContentControl.Content%2A>, dal <xref:System.Windows.Controls.ContentControl> e definisce il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> proprietà che è di tipo <xref:System.Object>; pertanto, entrambi possono essere un oggetto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-133">It inherits the content property, <xref:System.Windows.Controls.ContentControl.Content%2A>, from <xref:System.Windows.Controls.ContentControl> and defines the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> property that is of type <xref:System.Object>; therefore, both can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="3ecfe-134">I controlli seguenti ereditano da <xref:System.Windows.Controls.HeaderedContentControl> e usano il corrispondente modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="3ecfe-134">The following controls inherit from <xref:System.Windows.Controls.HeaderedContentControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.Expander>  
  
-   <xref:System.Windows.Controls.GroupBox>  
  
-   <xref:System.Windows.Controls.TabItem>  
  
 <span data-ttu-id="3ecfe-135">La figura seguente mostra due <xref:System.Windows.Controls.TabItem> oggetti.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-135">The following illustration shows two <xref:System.Windows.Controls.TabItem> objects.</span></span> <span data-ttu-id="3ecfe-136">Il primo <xref:System.Windows.Controls.TabItem> ha <xref:System.Windows.UIElement> oggetti come i <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e il <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-136">The first <xref:System.Windows.Controls.TabItem> has <xref:System.Windows.UIElement> objects as the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span> <span data-ttu-id="3ecfe-137">Il <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> è impostata su una <xref:System.Windows.Controls.StackPanel> che contiene un' <xref:System.Windows.Shapes.Ellipse> e un <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-137">The <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="3ecfe-138">Il <xref:System.Windows.Controls.ContentControl.Content%2A> è impostata su una <xref:System.Windows.Controls.StackPanel> che contiene un <xref:System.Windows.Controls.TextBlock> e un <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-138">The <xref:System.Windows.Controls.ContentControl.Content%2A> is set to a <xref:System.Windows.Controls.StackPanel> that contains a <xref:System.Windows.Controls.TextBlock> and a <xref:System.Windows.Controls.Label>.</span></span> <span data-ttu-id="3ecfe-139">La seconda <xref:System.Windows.Controls.TabItem> dispone di una stringa nel <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> e una <xref:System.Windows.Controls.TextBlock> nel <xref:System.Windows.Controls.ContentControl.Content%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-139">The second <xref:System.Windows.Controls.TabItem> has a string in the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and a <xref:System.Windows.Controls.TextBlock> in the <xref:System.Windows.Controls.ContentControl.Content%2A>.</span></span>  
  
 <span data-ttu-id="3ecfe-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span><span class="sxs-lookup"><span data-stu-id="3ecfe-140">![TabControl](../../../../docs/framework/wpf/controls/media/controlcontentmodelteabitem.PNG "ControlContentModelTeabItem")</span></span>  
<span data-ttu-id="3ecfe-141">TabControl con tipi diversi nella proprietà Header</span><span class="sxs-lookup"><span data-stu-id="3ecfe-141">TabControl that uses different types in the Header property</span></span>  
  
 <span data-ttu-id="3ecfe-142">Per un esempio di come creare <xref:System.Windows.Controls.TabItem> oggetti, vedere <xref:System.Windows.Controls.HeaderedContentControl>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-142">For an example of how to create <xref:System.Windows.Controls.TabItem> objects, see <xref:System.Windows.Controls.HeaderedContentControl>.</span></span>  
  
### <a name="controls-that-contain-a-collection-of-arbitrary-objects"></a><span data-ttu-id="3ecfe-143">Controlli che contengono una raccolta di oggetti arbitrari</span><span class="sxs-lookup"><span data-stu-id="3ecfe-143">Controls That Contain a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="3ecfe-144">Il <xref:System.Windows.Controls.ItemsControl> classe eredita da <xref:System.Windows.Controls.Control> e può contenere più elementi, ad esempio stringhe, oggetti o altri elementi.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-144">The <xref:System.Windows.Controls.ItemsControl> class inherits from <xref:System.Windows.Controls.Control> and can contain multiple items, such as strings, objects, or other elements.</span></span> <span data-ttu-id="3ecfe-145">Le proprietà di contenuto vengono <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> e <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-145">Its content properties are <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> and <xref:System.Windows.Controls.ItemsControl.Items%2A>.</span></span> <span data-ttu-id="3ecfe-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> in genere viene utilizzato per popolare il <xref:System.Windows.Controls.ItemsControl> con una raccolta di dati.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-146"><xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> is typically used to populate the <xref:System.Windows.Controls.ItemsControl> with a data collection.</span></span> <span data-ttu-id="3ecfe-147">Se non si desidera usare una raccolta per popolare la <xref:System.Windows.Controls.ItemsControl>, è possibile aggiungere elementi usando il <xref:System.Windows.Controls.ItemsControl.Items%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-147">If you do not want to use a collection to populate the <xref:System.Windows.Controls.ItemsControl>, you can add items by using the <xref:System.Windows.Controls.ItemsControl.Items%2A> property.</span></span>  
  
 <span data-ttu-id="3ecfe-148">I controlli seguenti ereditano da <xref:System.Windows.Controls.ItemsControl> e usano il corrispondente modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="3ecfe-148">The following controls inherit from <xref:System.Windows.Controls.ItemsControl> and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="3ecfe-149">La figura seguente mostra un <xref:System.Windows.Controls.ListBox> che contiene i tipi di elementi:</span><span class="sxs-lookup"><span data-stu-id="3ecfe-149">The following illustration shows a <xref:System.Windows.Controls.ListBox> that contains these types of items:</span></span>  
  
-   <span data-ttu-id="3ecfe-150">Stringa.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-150">A string.</span></span>  
  
-   <span data-ttu-id="3ecfe-151">Oggetto <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-151">A <xref:System.DateTime> object.</span></span>  
  
-   <span data-ttu-id="3ecfe-152">Oggetto <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-152">A <xref:System.Windows.UIElement>.</span></span>  
  
-   <span data-ttu-id="3ecfe-153">Oggetto <xref:System.Windows.Controls.Panel> che contiene un <xref:System.Windows.Shapes.Ellipse> e un <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-153">A <xref:System.Windows.Controls.Panel> that contains an <xref:System.Windows.Shapes.Ellipse> and a <xref:System.Windows.Controls.TextBlock>.</span></span>  
  
 <span data-ttu-id="3ecfe-154">![ListBox con quattro tipi di contenuto](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span><span class="sxs-lookup"><span data-stu-id="3ecfe-154">![ListBox with four types of content](../../../../docs/framework/wpf/controls/media/controlcontentmodellistbox2.PNG "ControlContentModelListBox2")</span></span>  
<span data-ttu-id="3ecfe-155">ListBox con più tipi di oggetti</span><span class="sxs-lookup"><span data-stu-id="3ecfe-155">ListBox that contains multiple types of objects</span></span>  
  
### <a name="controls-that-contain-a-header-and-a-collection-of-arbitrary-objects"></a><span data-ttu-id="3ecfe-156">Controlli che contengono un'intestazione e una raccolta di oggetti arbitrari</span><span class="sxs-lookup"><span data-stu-id="3ecfe-156">Controls That Contain a Header and a Collection of Arbitrary Objects</span></span>  
 <span data-ttu-id="3ecfe-157">Il <xref:System.Windows.Controls.HeaderedItemsControl> classe eredita da <xref:System.Windows.Controls.ItemsControl> e può contenere più elementi, ad esempio stringhe, oggetti, o altri elementi e un'intestazione.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-157">The <xref:System.Windows.Controls.HeaderedItemsControl> class inherits from <xref:System.Windows.Controls.ItemsControl> and can contain multiple items, such as strings, objects, or other elements, and a header.</span></span> <span data-ttu-id="3ecfe-158">Eredita le <xref:System.Windows.Controls.ItemsControl> proprietà, del contenuto <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, e <xref:System.Windows.Controls.ItemsControl.Items%2A>, e definisce il <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> proprietà che può essere un oggetto arbitrario.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-158">It inherits the <xref:System.Windows.Controls.ItemsControl> content properties, <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, and <xref:System.Windows.Controls.ItemsControl.Items%2A>, and it defines the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> property that can be an arbitrary object.</span></span>  
  
 <span data-ttu-id="3ecfe-159">I controlli seguenti ereditano da <xref:System.Windows.Controls.HeaderedItemsControl> e usano il corrispondente modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="3ecfe-159">The following controls inherit from <xref:System.Windows.Controls.HeaderedItemsControl> and use its content model:</span></span>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeViewItem>  
  
<a name="classes_that_contain_a_collection_of_uielement_objects"></a>   
## <a name="classes-that-contain-a-collection-of-uielement-objects"></a><span data-ttu-id="3ecfe-160">Classi che contengono una raccolta di oggetti UIElement</span><span class="sxs-lookup"><span data-stu-id="3ecfe-160">Classes That Contain a Collection of UIElement Objects</span></span>  
 <span data-ttu-id="3ecfe-161">Il <xref:System.Windows.Controls.Panel> classe di posizionare e disporre figlio <xref:System.Windows.UIElement> oggetti.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-161">The <xref:System.Windows.Controls.Panel> class positions and arranges child <xref:System.Windows.UIElement> objects.</span></span> <span data-ttu-id="3ecfe-162">Proprietà di contenuto corrispondente è <xref:System.Windows.Controls.Panel.Children%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-162">Its content property is <xref:System.Windows.Controls.Panel.Children%2A>.</span></span>  
  
 <span data-ttu-id="3ecfe-163">Le classi seguenti ereditano dal <xref:System.Windows.Controls.Panel> classe e usare il modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="3ecfe-163">The following classes inherit from the <xref:System.Windows.Controls.Panel> class and use its content model:</span></span>  
  
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
  
 <span data-ttu-id="3ecfe-164">Per altre informazioni, vedere [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3ecfe-164">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
<a name="classes_that_affects_the_appearance_of_a_uielement"></a>   
## <a name="classes-that-affect-the-appearance-of-a-uielement"></a><span data-ttu-id="3ecfe-165">Classi che influiscono sull'aspetto di un oggetto UIElement</span><span class="sxs-lookup"><span data-stu-id="3ecfe-165">Classes That Affect the Appearance of a UIElement</span></span>  
 <span data-ttu-id="3ecfe-166">Il <xref:System.Windows.Controls.Decorator> classe applica effetti visivi a o attorno a un singolo elemento figlio <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-166">The <xref:System.Windows.Controls.Decorator> class applies visual effects onto or around a single child <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="3ecfe-167">Proprietà di contenuto corrispondente è <xref:System.Windows.Controls.Decorator.Child%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-167">Its content property is <xref:System.Windows.Controls.Decorator.Child%2A>.</span></span> <span data-ttu-id="3ecfe-168">Le classi seguenti ereditano da <xref:System.Windows.Controls.Decorator> e usano il corrispondente modello di contenuto:</span><span class="sxs-lookup"><span data-stu-id="3ecfe-168">The following classes inherit from <xref:System.Windows.Controls.Decorator> and use its content model:</span></span>  
  
-   <xref:System.Windows.Documents.AdornerDecorator>  
  
-   <xref:System.Windows.Controls.Border>  
  
-   <xref:System.Windows.Controls.Primitives.BulletDecorator>  
  
-   <xref:Microsoft.Windows.Themes.ButtonChrome>  
  
-   <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>  
  
-   <xref:System.Windows.Controls.InkPresenter>  
  
-   <xref:Microsoft.Windows.Themes.ListBoxChrome>  
  
-   <xref:Microsoft.Windows.Themes.SystemDropShadowChrome>  
  
-   <xref:System.Windows.Controls.Viewbox>  
  
 <span data-ttu-id="3ecfe-169">La figura seguente mostra una <xref:System.Windows.Controls.TextBox> che ha (è decorato con) un <xref:System.Windows.Controls.Border> intorno a esso.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-169">The following illustration shows a <xref:System.Windows.Controls.TextBox> that has (is decorated with) a <xref:System.Windows.Controls.Border> around it.</span></span>  
  
 <span data-ttu-id="3ecfe-170">![TextBox con bordo nero](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span><span class="sxs-lookup"><span data-stu-id="3ecfe-170">![TextBox with black border](../../../../docs/framework/wpf/controls/media/layout-border-around-textbox.png "Layout_Border_around_TextBox")</span></span>  
<span data-ttu-id="3ecfe-171">TextBlock con bordo nero</span><span class="sxs-lookup"><span data-stu-id="3ecfe-171">TextBlock that has a Border</span></span>  
  
<a name="classes_that_provides_visual_feedback_about_a_uielement"></a>   
## <a name="classes-that-provide-visual-feedback-about-a-uielement"></a><span data-ttu-id="3ecfe-172">Classi che forniscono feedback visivo su un oggetto UIElement</span><span class="sxs-lookup"><span data-stu-id="3ecfe-172">Classes That Provide Visual Feedback About a UIElement</span></span>  
 <span data-ttu-id="3ecfe-173">Il <xref:System.Windows.Documents.Adorner> classe offre indicazioni visive a un utente.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-173">The <xref:System.Windows.Documents.Adorner> class provides visual cues to a user.</span></span> <span data-ttu-id="3ecfe-174">Ad esempio, usare un <xref:System.Windows.Documents.Adorner> per aggiungere handle funzionali agli elementi o fornire informazioni sullo stato relative a un controllo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-174">For example, use an <xref:System.Windows.Documents.Adorner> to add functional handles to elements or provide state information about a control.</span></span> <span data-ttu-id="3ecfe-175">Il <xref:System.Windows.Documents.Adorner> classe fornisce un framework in modo che sia possibile creare strumenti decorativi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-175">The <xref:System.Windows.Documents.Adorner> class provides a framework so that you can create your own adorners.</span></span> <span data-ttu-id="3ecfe-176">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non sono inclusi strumenti decorativi implementati.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-176">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] does not provide any implemented adorners.</span></span> <span data-ttu-id="3ecfe-177">Per altre informazioni, vedere [Cenni preliminari sugli strumenti decorativi](../../../../docs/framework/wpf/controls/adorners-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3ecfe-177">For more information, see [Adorners Overview](../../../../docs/framework/wpf/controls/adorners-overview.md).</span></span>  
  
<a name="classes_that_enable_users_to_enter_text"></a>   
## <a name="classes-that-enable-users-to-enter-text"></a><span data-ttu-id="3ecfe-178">Classi che consentono agli utenti di immettere testo</span><span class="sxs-lookup"><span data-stu-id="3ecfe-178">Classes That Enable Users to Enter Text</span></span>  
 <span data-ttu-id="3ecfe-179">In WPF sono disponibili tre controlli primari che consentono agli utenti di immettere testo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-179">WPF provides three primary controls that enable users to enter text.</span></span> <span data-ttu-id="3ecfe-180">Ogni controllo determina una visualizzazione diversa del testo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-180">Each control displays the text differently.</span></span> <span data-ttu-id="3ecfe-181">La tabella seguente elenca questi tre controlli correlati al testo, le relative funzionalità per la visualizzazione di testo, nonché le relative proprietà contenenti il testo del controllo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-181">The following table lists these three text-related controls, their capabilities when they display text, and their properties that contain the control's text.</span></span>  
  
|<span data-ttu-id="3ecfe-182">Control</span><span class="sxs-lookup"><span data-stu-id="3ecfe-182">Control</span></span>|<span data-ttu-id="3ecfe-183">Il testo viene visualizzato come</span><span class="sxs-lookup"><span data-stu-id="3ecfe-183">Text is displayed as</span></span>|<span data-ttu-id="3ecfe-184">Proprietà di contenuto</span><span class="sxs-lookup"><span data-stu-id="3ecfe-184">Content property</span></span>|  
|-------------|--------------------------|----------------------|  
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="3ecfe-185">Testo normale</span><span class="sxs-lookup"><span data-stu-id="3ecfe-185">Plain text</span></span>|<xref:System.Windows.Controls.TextBox.Text%2A>|  
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="3ecfe-186">Testo formattato</span><span class="sxs-lookup"><span data-stu-id="3ecfe-186">Formatted text</span></span>|<xref:System.Windows.Controls.RichTextBox.Document%2A>|  
|<xref:System.Windows.Controls.PasswordBox>|<span data-ttu-id="3ecfe-187">Testo nascosto (i caratteri sono mascherati)</span><span class="sxs-lookup"><span data-stu-id="3ecfe-187">Hidden text (characters are masked)</span></span>|<xref:System.Windows.Controls.PasswordBox.Password%2A>|  
  
<a name="classes_that_display_text"></a>   
## <a name="classes-that-display-your-text"></a><span data-ttu-id="3ecfe-188">Classi che consentono di visualizzare il testo dell'utente</span><span class="sxs-lookup"><span data-stu-id="3ecfe-188">Classes That Display Your Text</span></span>  
 <span data-ttu-id="3ecfe-189">Per la visualizzazione di testo normale o formattato sono disponibili numerose classi.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-189">Several classes can be used to display plain or formatted text.</span></span> <span data-ttu-id="3ecfe-190">È possibile usare <xref:System.Windows.Controls.TextBlock> visualizzare piccole quantità di testo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-190">You can use <xref:System.Windows.Controls.TextBlock> to display small amounts of text.</span></span> <span data-ttu-id="3ecfe-191">Se si desidera visualizzare grandi quantità di testo, usare il <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, o <xref:System.Windows.Controls.FlowDocumentScrollViewer> controlli.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-191">If you want to display large amounts of text, use the <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, or <xref:System.Windows.Controls.FlowDocumentScrollViewer> controls.</span></span>  
  
 <span data-ttu-id="3ecfe-192">Il <xref:System.Windows.Controls.TextBlock> ha due proprietà di contenuto: <xref:System.Windows.Controls.TextBlock.Text%2A> e <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-192">The <xref:System.Windows.Controls.TextBlock> has two content properties: <xref:System.Windows.Controls.TextBlock.Text%2A> and <xref:System.Windows.Controls.TextBlock.Inlines%2A>.</span></span> <span data-ttu-id="3ecfe-193">Quando si desidera visualizzare il testo che usa una formattazione coerente, di <xref:System.Windows.Controls.TextBlock.Text%2A> proprietà è spesso la scelta migliore.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-193">When you want to display text that uses consistent formatting, the <xref:System.Windows.Controls.TextBlock.Text%2A> property is often your best choice.</span></span> <span data-ttu-id="3ecfe-194">Se si prevede di usare una formattazione diversa in tutto il testo, usare il <xref:System.Windows.Controls.TextBlock.Inlines%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-194">If you plan to use different formatting throughout the text, use the <xref:System.Windows.Controls.TextBlock.Inlines%2A> property.</span></span> <span data-ttu-id="3ecfe-195">Il <xref:System.Windows.Controls.TextBlock.Inlines%2A> proprietà è una raccolta di <xref:System.Windows.Documents.Inline> oggetti, che specificano la modalità di formattazione del testo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-195">The <xref:System.Windows.Controls.TextBlock.Inlines%2A> property is a collection of <xref:System.Windows.Documents.Inline> objects, which specify how to format text.</span></span>  
  
 <span data-ttu-id="3ecfe-196">Nella tabella seguente elenca le proprietà per <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, e <xref:System.Windows.Controls.FlowDocumentScrollViewer> classi.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-196">The following table lists the content property for <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, and <xref:System.Windows.Controls.FlowDocumentScrollViewer> classes.</span></span>  
  
|<span data-ttu-id="3ecfe-197">Control</span><span class="sxs-lookup"><span data-stu-id="3ecfe-197">Control</span></span>|<span data-ttu-id="3ecfe-198">Proprietà di contenuto</span><span class="sxs-lookup"><span data-stu-id="3ecfe-198">Content property</span></span>|<span data-ttu-id="3ecfe-199">Tipo proprietà di contenuto</span><span class="sxs-lookup"><span data-stu-id="3ecfe-199">Content property type</span></span>|  
|-------------|----------------------|---------------------------|  
|<xref:System.Windows.Controls.FlowDocumentPageViewer>|<span data-ttu-id="3ecfe-200">Document</span><span class="sxs-lookup"><span data-stu-id="3ecfe-200">Document</span></span>|<xref:System.Windows.Documents.IDocumentPaginatorSource>|  
|<xref:System.Windows.Controls.FlowDocumentReader>|<span data-ttu-id="3ecfe-201">Document</span><span class="sxs-lookup"><span data-stu-id="3ecfe-201">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
|<xref:System.Windows.Controls.FlowDocumentScrollViewer>|<span data-ttu-id="3ecfe-202">Document</span><span class="sxs-lookup"><span data-stu-id="3ecfe-202">Document</span></span>|<xref:System.Windows.Documents.FlowDocument>|  
  
 <span data-ttu-id="3ecfe-203">Il <xref:System.Windows.Documents.FlowDocument> implementa la <xref:System.Windows.Documents.IDocumentPaginatorSource> interfaccia; pertanto, tutte le tre classi possono adottare un <xref:System.Windows.Documents.FlowDocument> come contenuto.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-203">The <xref:System.Windows.Documents.FlowDocument> implements the <xref:System.Windows.Documents.IDocumentPaginatorSource> interface; therefore, all three classes can take a <xref:System.Windows.Documents.FlowDocument> as content.</span></span>  
  
<a name="classes_that_format_text"></a>   
## <a name="classes-that-format-your-text"></a><span data-ttu-id="3ecfe-204">Classi che consentono di formattare il testo dell'utente</span><span class="sxs-lookup"><span data-stu-id="3ecfe-204">Classes That Format Your Text</span></span>  
 <span data-ttu-id="3ecfe-205"><xref:System.Windows.Documents.TextElement> e le relative classi consentono di formattare il testo.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-205"><xref:System.Windows.Documents.TextElement> and its related classes allow you to format text.</span></span> <span data-ttu-id="3ecfe-206"><xref:System.Windows.Documents.TextElement> gli oggetti contengono e formattare il testo nei <xref:System.Windows.Controls.TextBlock> e <xref:System.Windows.Documents.FlowDocument> oggetti.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-206"><xref:System.Windows.Documents.TextElement> objects contain and format text in <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Documents.FlowDocument> objects.</span></span> <span data-ttu-id="3ecfe-207">I due tipi principali di <xref:System.Windows.Documents.TextElement> gli oggetti vengono <xref:System.Windows.Documents.Block> gli elementi e <xref:System.Windows.Documents.Inline> elementi.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-207">The two primary types of <xref:System.Windows.Documents.TextElement> objects are <xref:System.Windows.Documents.Block> elements and <xref:System.Windows.Documents.Inline> elements.</span></span> <span data-ttu-id="3ecfe-208">Oggetto <xref:System.Windows.Documents.Block> elemento rappresenta un blocco di testo, ad esempio un paragrafo o un elenco.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-208">A <xref:System.Windows.Documents.Block> element represents a block of text, such as a paragraph or list.</span></span> <span data-ttu-id="3ecfe-209">Un <xref:System.Windows.Documents.Inline> elemento rappresenta una porzione di testo in un blocco.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-209">An <xref:System.Windows.Documents.Inline> element represents a portion of text in a block.</span></span> <span data-ttu-id="3ecfe-210">Molti <xref:System.Windows.Documents.Inline> classi specificano la formattazione per il testo a cui sono applicati.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-210">Many <xref:System.Windows.Documents.Inline> classes specify formatting for the text to which they are applied.</span></span> <span data-ttu-id="3ecfe-211">Ogni <xref:System.Windows.Documents.TextElement> ha un proprio modello di contenuto.</span><span class="sxs-lookup"><span data-stu-id="3ecfe-211">Each <xref:System.Windows.Documents.TextElement> has its own content model.</span></span> <span data-ttu-id="3ecfe-212">Per altre informazioni, vedere il [Cenni preliminari sul modello di contenuto di TextElement](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3ecfe-212">For more information, see the [TextElement Content Model Overview](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ecfe-213">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ecfe-213">See also</span></span>
- [<span data-ttu-id="3ecfe-214">Avanzate</span><span class="sxs-lookup"><span data-stu-id="3ecfe-214">Advanced</span></span>](../../../../docs/framework/wpf/advanced/index.md)
