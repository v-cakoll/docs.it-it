---
title: Controlli con supporto incorporato per la creazione da parte del proprietario
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: f0d4b99f9ee0134fc7334a941dd5ef4fd7ba3df3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930186"
---
# <a name="controls-with-built-in-owner-drawing-support"></a><span data-ttu-id="c94de-102">Controlli con supporto incorporato per la creazione da parte del proprietario</span><span class="sxs-lookup"><span data-stu-id="c94de-102">Controls with Built-In Owner-Drawing Support</span></span>
<span data-ttu-id="c94de-103">Il disegno da parte del proprietario in Windows Form, noto anche come disegno personalizzato, è una tecnica che consente di modificare l'aspetto visivo di alcuni controlli.</span><span class="sxs-lookup"><span data-stu-id="c94de-103">Owner drawing in Windows Forms, which is also known as custom drawing, is a technique for changing the visual appearance of certain controls.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c94de-104">Il termine "controllo" in questo argomento viene usato per indicare le classi che derivano <xref:System.Windows.Forms.Control> da <xref:System.ComponentModel.Component>o.</span><span class="sxs-lookup"><span data-stu-id="c94de-104">The word "control" in this topic is used to mean classes that derive from either <xref:System.Windows.Forms.Control> or <xref:System.ComponentModel.Component>.</span></span>  
  
 <span data-ttu-id="c94de-105">In genere, Windows gestisce automaticamente il disegno usando le impostazioni delle <xref:System.Windows.Forms.Control.BackColor%2A> proprietà, ad esempio, per determinare l'aspetto di un controllo.</span><span class="sxs-lookup"><span data-stu-id="c94de-105">Typically, Windows handles painting automatically by using property settings such as <xref:System.Windows.Forms.Control.BackColor%2A> to determine the appearance of a control.</span></span> <span data-ttu-id="c94de-106">Con il disegno da parte del proprietario, si acquisisce la precedenza sul processo di disegno, modificando elementi dell'aspetto non disponibili quando si usano le proprietà.</span><span class="sxs-lookup"><span data-stu-id="c94de-106">With owner drawing, you take over the painting process, changing elements of appearance that are not available by using properties.</span></span> <span data-ttu-id="c94de-107">Molti controlli, ad esempio, consentono di impostare il colore del testo visualizzato, ma è previsto un limite di un solo colore.</span><span class="sxs-lookup"><span data-stu-id="c94de-107">For example, many controls let you set the color of the text that is displayed, but you are limited to a single color.</span></span> <span data-ttu-id="c94de-108">Il disegno da parte del proprietario consente, ad esempio, di visualizzare parte del testo in nero e parte in rosso.</span><span class="sxs-lookup"><span data-stu-id="c94de-108">Owner drawing enables you to do things like display part of the text in black and part in red.</span></span>  
  
 <span data-ttu-id="c94de-109">Il disegno da parte del proprietario è in pratica simile al disegno di elementi grafici in un form.</span><span class="sxs-lookup"><span data-stu-id="c94de-109">In practice, owner drawing is similar to drawing graphics on a form.</span></span> <span data-ttu-id="c94de-110">Ad esempio, è possibile usare i metodi grafici in un gestore per l' <xref:System.Windows.Forms.Control.Paint> evento del modulo per emulare un `ListBox` controllo, ma è necessario scrivere codice personalizzato per gestire l'interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c94de-110">For example, you could use graphics methods in a handler for the form's <xref:System.Windows.Forms.Control.Paint> event to emulate a `ListBox` control, but you would have to write your own code to handle all user interaction.</span></span> <span data-ttu-id="c94de-111">Con il disegno da parte del proprietario, il controllo usa il codice per disegnare i contenuti, ma mantiene tutte le funzionalità intrinseche.</span><span class="sxs-lookup"><span data-stu-id="c94de-111">With owner drawing, the control uses your code to draw its contents but otherwise retains all its intrinsic capabilities.</span></span> <span data-ttu-id="c94de-112">È possibile usare metodi Graphics per disegnare ogni elemento nel controllo o per personalizzare alcuni dettagli di ogni elemento mentre si usa l'aspetto predefinito per altri dettagli di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="c94de-112">You can use graphics methods to draw each item in the control or to customize some aspects of each item while you use the default appearance for other aspects of each item.</span></span>  
  
## <a name="owner-drawing-in-windows-forms-controls"></a><span data-ttu-id="c94de-113">Disegno da parte del proprietario nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="c94de-113">Owner Drawing in Windows Forms Controls</span></span>  
 <span data-ttu-id="c94de-114">Per eseguire il disegno da parte del proprietario nei controlli che lo supportano, in genere è necessario impostare una proprietà e gestire uno o più eventi.</span><span class="sxs-lookup"><span data-stu-id="c94de-114">To perform owner drawing in controls that support it, you will typically set one property and handle one or more events.</span></span>  
  
 <span data-ttu-id="c94de-115">La maggior parte dei controlli che supportano il disegno da parte del proprietario ha una proprietà `OwnerDraw` o `DrawMode` che indica se il controllo genera uno o più eventi correlati al disegno quando disegna se stesso.</span><span class="sxs-lookup"><span data-stu-id="c94de-115">Most controls that support owner drawing have an `OwnerDraw` or `DrawMode` property that indicates whether the control will raise its drawing-related event or events when it paints itself.</span></span>  
  
 <span data-ttu-id="c94de-116">I controlli senza la proprietà `OwnerDraw` o `DrawMode` includono il controllo `DataGridView`, che fornisce eventi di disegno che si verificano automaticamente, e il controllo `ToolStrip`, che viene disegnato usando una classe di rendering esterna con i propri eventi correlati al disegno.</span><span class="sxs-lookup"><span data-stu-id="c94de-116">Controls that do not have an `OwnerDraw` or `DrawMode` property include the `DataGridView` control, which provides drawing events that occur automatically, and the `ToolStrip` control, which is drawn using an external rendering class that has its own drawing-related events.</span></span>  
  
 <span data-ttu-id="c94de-117">Sono disponibili molti tipi di eventi di disegno diversi, ma un evento di disegno tipico si verifica per disegnare un singolo elemento in un controllo.</span><span class="sxs-lookup"><span data-stu-id="c94de-117">There are many different kinds of drawing events, but a typical drawing event occurs in order to draw a single item within a control.</span></span> <span data-ttu-id="c94de-118">Il gestore eventi riceve un oggetto `EventArgs` che contiene informazioni sull'elemento che viene disegnato e sugli strumenti che è possibile usare per disegnarlo.</span><span class="sxs-lookup"><span data-stu-id="c94de-118">The event handler receives an `EventArgs` object that contains information about the item being drawn and tools you can use to draw it.</span></span> <span data-ttu-id="c94de-119">Questo oggetto, ad esempio, contiene in genere il numero di indice dell'elemento all'interno della <xref:System.Drawing.Rectangle> raccolta padre, un che indica i limiti di visualizzazione <xref:System.Drawing.Graphics> dell'elemento e un oggetto per chiamare i metodi di disegno.</span><span class="sxs-lookup"><span data-stu-id="c94de-119">For example, this object typically contains the item's index number within its parent collection, a <xref:System.Drawing.Rectangle> that indicates the item's display boundaries, and a <xref:System.Drawing.Graphics> object for calling paint methods.</span></span> <span data-ttu-id="c94de-120">Per alcuni eventi, l'oggetto `EventArgs` fornisce informazioni aggiuntive sull'elemento e sui metodi che è possibile chiamare per disegnare alcuni dettagli dell'elemento per impostazione predefinita, ad esempio lo sfondo o il rettangolo dello stato attivo.</span><span class="sxs-lookup"><span data-stu-id="c94de-120">For some events, the `EventArgs` object provides additional information about the item and methods that you can call to paint some aspects of the item by default, such as the background or a focus rectangle.</span></span>  
  
 <span data-ttu-id="c94de-121">Per creare un controllo riutilizzabile contenente le personalizzazioni disegnate dal proprietario, creare una nuova classe che deriva da una classe di controlli che supporta il disegno da parte del proprietario.</span><span class="sxs-lookup"><span data-stu-id="c94de-121">To create a reusable control that contains your owner-drawn customizations, create a new class that derives from a control class that supports owner drawing.</span></span> <span data-ttu-id="c94de-122">Invece di gestire gli eventi di disegno, includere il codice del disegno da parte del proprietario negli override per uno o più metodi `On`*EventName* appropriati nella nuova classe.</span><span class="sxs-lookup"><span data-stu-id="c94de-122">Rather than handling drawing events, include your owner-drawing code in overrides for the appropriate `On`*EventName* method or methods in the new class.</span></span> <span data-ttu-id="c94de-123">In questo caso, verificare di chiamare il metodo o i metodi `On`*EventName* della classe base in modo che gli utenti del controllo possano gestire gli eventi di disegno da parte del proprietario e creare personalizzazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c94de-123">Make sure that you call the base class `On`*EventName* method or methods in this case so that users of your control can handle owner-drawing events and provide additional customization.</span></span>  
  
 <span data-ttu-id="c94de-124">I controlli Windows Form seguenti supportano il disegno da parte del proprietario in tutte le versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c94de-124">The following Windows Forms controls support owner drawing in all versions of the .NET Framework:</span></span>  
  
- <xref:System.Windows.Forms.ListBox>  
  
- <xref:System.Windows.Forms.ComboBox>  
  
- <span data-ttu-id="c94de-125"><xref:System.Windows.Forms.MenuItem>(utilizzato da <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu>)</span><span class="sxs-lookup"><span data-stu-id="c94de-125"><xref:System.Windows.Forms.MenuItem> (used by <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu>)</span></span>  
  
- <xref:System.Windows.Forms.TabControl>  
  
 <span data-ttu-id="c94de-126">I controlli seguenti supportano il disegno del proprietario solo in .NET Framework 2,0:</span><span class="sxs-lookup"><span data-stu-id="c94de-126">The following controls support owner drawing only in .NET Framework 2.0:</span></span>  
  
- <xref:System.Windows.Forms.ToolTip>  
  
- <xref:System.Windows.Forms.ListView>  
  
- <xref:System.Windows.Forms.TreeView>  
  
 <span data-ttu-id="c94de-127">I controlli seguenti supportano il disegno del proprietario e sono una novità di .NET Framework 2,0:</span><span class="sxs-lookup"><span data-stu-id="c94de-127">The following controls support owner drawing and are new in .NET Framework 2.0:</span></span>  
  
- <xref:System.Windows.Forms.DataGridView>  
  
- <xref:System.Windows.Forms.ToolStrip>  
  
 <span data-ttu-id="c94de-128">Le sezioni seguenti contengono altre informazioni dettagliate su ogni controllo.</span><span class="sxs-lookup"><span data-stu-id="c94de-128">The following sections provide additional details for each of these controls.</span></span>  
  
### <a name="listbox-and-combobox-controls"></a><span data-ttu-id="c94de-129">Controlli ListBox e ComboBox</span><span class="sxs-lookup"><span data-stu-id="c94de-129">ListBox and ComboBox Controls</span></span>  
 <span data-ttu-id="c94de-130">I <xref:System.Windows.Forms.ListBox> controlli <xref:System.Windows.Forms.ComboBox> e consentono di creare singoli elementi nel controllo in un'unica dimensione o in dimensioni variabili.</span><span class="sxs-lookup"><span data-stu-id="c94de-130">The <xref:System.Windows.Forms.ListBox> and <xref:System.Windows.Forms.ComboBox> controls enable you to draw individual items in the control either all in one size, or in varying sizes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c94de-131">Sebbene il <xref:System.Windows.Forms.CheckedListBox> controllo derivi <xref:System.Windows.Forms.ListBox> dal controllo, non supporta il disegno del proprietario.</span><span class="sxs-lookup"><span data-stu-id="c94de-131">Although the <xref:System.Windows.Forms.CheckedListBox> control is derived from the <xref:System.Windows.Forms.ListBox> control, it does not support owner drawing.</span></span>  
  
 <span data-ttu-id="c94de-132">Per tracciare ogni elemento con le stesse dimensioni, `DrawMode` impostare la <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> proprietà su e `DrawItem` gestire l'evento.</span><span class="sxs-lookup"><span data-stu-id="c94de-132">To draw each item the same size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="c94de-133">Per tracciare ogni elemento utilizzando dimensioni diverse, impostare la `DrawMode` proprietà su <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> e gestire entrambi gli `MeasureItem` eventi `DrawItem` e.</span><span class="sxs-lookup"><span data-stu-id="c94de-133">To draw each item using a different size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> and handle both the `MeasureItem` and `DrawItem` events.</span></span> <span data-ttu-id="c94de-134">L'evento `MeasureItem` consente di indicare le dimensioni di un elemento prima che si verifichi l'evento `DrawItem` per tale elemento.</span><span class="sxs-lookup"><span data-stu-id="c94de-134">The `MeasureItem` event lets you indicate the size of an item before the `DrawItem` event occurs for that item.</span></span>  
  
 <span data-ttu-id="c94de-135">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c94de-135">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
- [<span data-ttu-id="c94de-136">Procedura: Creare testo di dimensioni variabili in un controllo ComboBox</span><span class="sxs-lookup"><span data-stu-id="c94de-136">How to: Create Variable Sized Text in a ComboBox Control</span></span>](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a><span data-ttu-id="c94de-137">Componente MenuItem</span><span class="sxs-lookup"><span data-stu-id="c94de-137">MenuItem Component</span></span>  
 <span data-ttu-id="c94de-138">Il <xref:System.Windows.Forms.MenuItem> componente rappresenta una singola voce di menu in <xref:System.Windows.Forms.MainMenu> un <xref:System.Windows.Forms.ContextMenu> componente o.</span><span class="sxs-lookup"><span data-stu-id="c94de-138">The <xref:System.Windows.Forms.MenuItem> component represents a single menu item in a <xref:System.Windows.Forms.MainMenu> or <xref:System.Windows.Forms.ContextMenu> component.</span></span>  
  
 <span data-ttu-id="c94de-139">Per creare un <xref:System.Windows.Forms.MenuItem>oggetto, `OwnerDraw` impostarne la `true` proprietà su e `DrawItem` gestirne l'evento.</span><span class="sxs-lookup"><span data-stu-id="c94de-139">To draw a <xref:System.Windows.Forms.MenuItem>, set its `OwnerDraw` property to `true` and handle its `DrawItem` event.</span></span> <span data-ttu-id="c94de-140">Per personalizzare le dimensioni della voce di menu prima che si verifichi l'evento `DrawItem`, gestire l'evento `MeasureItem` dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="c94de-140">To customize the size of the menu item before the `DrawItem` event occurs, handle the item's `MeasureItem` event.</span></span>  
  
 <span data-ttu-id="c94de-141">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:</span><span class="sxs-lookup"><span data-stu-id="c94de-141">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a><span data-ttu-id="c94de-142">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="c94de-142">TabControl Control</span></span>  
 <span data-ttu-id="c94de-143">Il <xref:System.Windows.Forms.TabControl> controllo consente di creare singole schede nel controllo.</span><span class="sxs-lookup"><span data-stu-id="c94de-143">The <xref:System.Windows.Forms.TabControl> control enables you to draw individual tabs in the control.</span></span> <span data-ttu-id="c94de-144">Il disegno del proprietario ha effetto solo sulle schede; il <xref:System.Windows.Forms.TabPage> contenuto non è interessato.</span><span class="sxs-lookup"><span data-stu-id="c94de-144">Owner drawing affects only the tabs; the <xref:System.Windows.Forms.TabPage> contents are not affected.</span></span>  
  
 <span data-ttu-id="c94de-145">Per creare ogni scheda in un <xref:System.Windows.Forms.TabControl>oggetto, impostare `DrawMode` la proprietà <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> su e gestire `DrawItem` l'evento.</span><span class="sxs-lookup"><span data-stu-id="c94de-145">To draw each tab in a <xref:System.Windows.Forms.TabControl>, set the `DrawMode` property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span> <span data-ttu-id="c94de-146">Questo evento si verifica una volta per ogni scheda solo quando la scheda è visibile nel controllo.</span><span class="sxs-lookup"><span data-stu-id="c94de-146">This event occurs once for each tab only when the tab is visible in the control.</span></span>  
  
 <span data-ttu-id="c94de-147">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:</span><span class="sxs-lookup"><span data-stu-id="c94de-147">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a><span data-ttu-id="c94de-148">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="c94de-148">ToolTip Component</span></span>  
 <span data-ttu-id="c94de-149">Il <xref:System.Windows.Forms.ToolTip> componente consente di creare l'intera descrizione comando quando viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="c94de-149">The <xref:System.Windows.Forms.ToolTip> component enables you to draw the entire ToolTip when it is displayed.</span></span>  
  
 <span data-ttu-id="c94de-150">Per creare un <xref:System.Windows.Forms.ToolTip>oggetto, `OwnerDraw` impostarne la `true` proprietà su e `Draw` gestirne l'evento.</span><span class="sxs-lookup"><span data-stu-id="c94de-150">To draw a <xref:System.Windows.Forms.ToolTip>, set its `OwnerDraw` property to `true` and handle its `Draw` event.</span></span> <span data-ttu-id="c94de-151">Per personalizzare <xref:System.Windows.Forms.ToolTip> le dimensioni di prima che si verifichi l' `Draw` evento, gestire `Popup` l'evento e impostare <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> la proprietà nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="c94de-151">To customize the size of the <xref:System.Windows.Forms.ToolTip> before the `Draw` event occurs, handle the `Popup` event and set the <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> property in the event handler.</span></span>  
  
 <span data-ttu-id="c94de-152">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:</span><span class="sxs-lookup"><span data-stu-id="c94de-152">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a><span data-ttu-id="c94de-153">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="c94de-153">ListView Control</span></span>  
 <span data-ttu-id="c94de-154">Il <xref:System.Windows.Forms.ListView> controllo consente di creare singoli elementi, elementi secondari e intestazioni di colonna nel controllo.</span><span class="sxs-lookup"><span data-stu-id="c94de-154">The <xref:System.Windows.Forms.ListView> control enables you to draw individual items, subitems, and column headers in the control.</span></span>  
  
 <span data-ttu-id="c94de-155">Per abilitare il disegno da parte del proprietario nel controllo, impostare la proprietà `OwnerDraw` su `true`.</span><span class="sxs-lookup"><span data-stu-id="c94de-155">To enable owner drawing in the control, set the `OwnerDraw` property to `true`.</span></span>  
  
 <span data-ttu-id="c94de-156">Per disegnare ogni elemento nel controllo, gestire l'evento `DrawItem`.</span><span class="sxs-lookup"><span data-stu-id="c94de-156">To draw each item in the control, handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="c94de-157">Per tracciare ogni elemento secondario o intestazione di colonna nel controllo quando <xref:System.Windows.Forms.ListView.View%2A> la proprietà è impostata <xref:System.Windows.Forms.View.Details>su, gestire `DrawSubItem` gli `DrawColumnHeader` eventi e.</span><span class="sxs-lookup"><span data-stu-id="c94de-157">To draw each subitem or column header in the control when the <xref:System.Windows.Forms.ListView.View%2A> property is set to <xref:System.Windows.Forms.View.Details>, handle the `DrawSubItem` and `DrawColumnHeader` events.</span></span>  
  
 <span data-ttu-id="c94de-158">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:</span><span class="sxs-lookup"><span data-stu-id="c94de-158">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a><span data-ttu-id="c94de-159">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="c94de-159">TreeView Control</span></span>  
 <span data-ttu-id="c94de-160">Il <xref:System.Windows.Forms.TreeView> controllo consente di creare singoli nodi nel controllo.</span><span class="sxs-lookup"><span data-stu-id="c94de-160">The <xref:System.Windows.Forms.TreeView> control enables you to draw individual nodes in the control.</span></span>  
  
 <span data-ttu-id="c94de-161">Per creare solo il testo visualizzato in ogni nodo, impostare la `DrawMode` proprietà su <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> e gestire l' `DrawNode` evento per creare il testo.</span><span class="sxs-lookup"><span data-stu-id="c94de-161">To draw only the text displayed in each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> and handle the `DrawNode` event to draw the text.</span></span>  
  
 <span data-ttu-id="c94de-162">Per tracciare tutti gli elementi di ogni nodo, `DrawMode` impostare la <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> proprietà su e `DrawNode` gestire l'evento per creare qualsiasi elemento necessario, ad esempio testo, icone, caselle di controllo, segni più e meno e linee che connettono i nodi.</span><span class="sxs-lookup"><span data-stu-id="c94de-162">To draw all elements of each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> and handle the `DrawNode` event to draw whichever elements you need, such as text, icons, check boxes, plus and minus signs, and lines connecting the nodes.</span></span>  
  
 <span data-ttu-id="c94de-163">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:</span><span class="sxs-lookup"><span data-stu-id="c94de-163">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a><span data-ttu-id="c94de-164">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="c94de-164">DataGridView Control</span></span>  
 <span data-ttu-id="c94de-165">Il <xref:System.Windows.Forms.DataGridView> controllo consente di creare singole celle e righe nel controllo.</span><span class="sxs-lookup"><span data-stu-id="c94de-165">The <xref:System.Windows.Forms.DataGridView> control enables you to draw individual cells and rows in the control.</span></span>  
  
 <span data-ttu-id="c94de-166">Per disegnare singole celle, gestire l'evento `CellPainting`.</span><span class="sxs-lookup"><span data-stu-id="c94de-166">To draw individual cells, handle the `CellPainting` event.</span></span>  
  
 <span data-ttu-id="c94de-167">Per disegnare singole righe o elementi delle righe, gestire uno o entrambi gli eventi `RowPrePaint` e `RowPostPaint`.</span><span class="sxs-lookup"><span data-stu-id="c94de-167">To draw individual rows or elements of rows, handle one or both of the `RowPrePaint` and `RowPostPaint` events.</span></span> <span data-ttu-id="c94de-168">L'evento `RowPrePaint` si verifica prima che le celle in una riga vengano disegnate e l'evento `RowPostPaint` si verifica dopo che le celle sono state disegnate.</span><span class="sxs-lookup"><span data-stu-id="c94de-168">The `RowPrePaint` event occurs before the cells in a row are painted, and the `RowPostPaint` event occurs after the cells are painted.</span></span> <span data-ttu-id="c94de-169">È possibile gestire entrambi gli eventi e l'evento `CellPainting` per disegnare separatamente lo sfondo delle righe, le singole celle e il primo piano delle righe oppure è possibile fornire personalizzazioni specifiche ove necessario e usare la visualizzazione predefinita per gli altri elementi della riga.</span><span class="sxs-lookup"><span data-stu-id="c94de-169">You can handle both events and the `CellPainting` event to paint row background, individual cells, and row foreground separately, or you can provide specific customizations where you need them and use the default display for other elements of the row.</span></span>  
  
 <span data-ttu-id="c94de-170">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c94de-170">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
- <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
- <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
- [<span data-ttu-id="c94de-171">Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c94de-171">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
- [<span data-ttu-id="c94de-172">Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c94de-172">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a><span data-ttu-id="c94de-173">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c94de-173">ToolStrip Control</span></span>  
 <span data-ttu-id="c94de-174"><xref:System.Windows.Forms.ToolStrip>e i controlli derivati consentono di personalizzare qualsiasi aspetto dell'aspetto.</span><span class="sxs-lookup"><span data-stu-id="c94de-174"><xref:System.Windows.Forms.ToolStrip> and derived controls enable you to customize any aspect of their appearance.</span></span>  
  
 <span data-ttu-id="c94de-175">Per fornire il rendering personalizzato <xref:System.Windows.Forms.ToolStrip> per i controlli, `Renderer` impostare la proprietà <xref:System.Windows.Forms.ToolStrip>di <xref:System.Windows.Forms.ToolStripManager>un <xref:System.Windows.Forms.ToolStripPanel>oggetto, <xref:System.Windows.Forms.ToolStripContentPanel> , o `ToolStripRenderer` su un oggetto e gestire uno o più degli eventi di disegno forniti dal comando `ToolStripRenderer` classe.</span><span class="sxs-lookup"><span data-stu-id="c94de-175">To provide custom rendering for <xref:System.Windows.Forms.ToolStrip> controls, set the `Renderer` property of a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, or <xref:System.Windows.Forms.ToolStripContentPanel> to a `ToolStripRenderer` object and handle one or more of the many drawing events provided by the `ToolStripRenderer` class.</span></span> <span data-ttu-id="c94de-176">In alternativa, impostare una `Renderer` proprietà su un'istanza della classe derivata da `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>o <xref:System.Windows.Forms.ToolStripSystemRenderer> che implementa o esegue l'override di metodi `On` *EventName* specifici.</span><span class="sxs-lookup"><span data-stu-id="c94de-176">Alternatively, set a `Renderer` property to an instance of your own class derived from `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, or <xref:System.Windows.Forms.ToolStripSystemRenderer> that implements or overrides specific `On`*EventName* methods.</span></span>  
  
 <span data-ttu-id="c94de-177">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c94de-177">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.ToolStripRenderer>  
  
- [<span data-ttu-id="c94de-178">Procedura: Creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c94de-178">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
- [<span data-ttu-id="c94de-179">Procedura: Progetto personalizzato di un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="c94de-179">How to: Custom Draw a ToolStrip Control</span></span>](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a><span data-ttu-id="c94de-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c94de-180">See also</span></span>

- [<span data-ttu-id="c94de-181">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c94de-181">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
