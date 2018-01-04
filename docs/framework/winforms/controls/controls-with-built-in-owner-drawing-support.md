---
title: Controlli con supporto incorporato per la creazione da parte del proprietario
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: efd297dcc11005d6b6d47bb9ce3853a757046e8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="controls-with-built-in-owner-drawing-support"></a><span data-ttu-id="24d2a-102">Controlli con supporto incorporato per la creazione da parte del proprietario</span><span class="sxs-lookup"><span data-stu-id="24d2a-102">Controls with Built-In Owner-Drawing Support</span></span>
<span data-ttu-id="24d2a-103">Il disegno da parte del proprietario in Windows Form, noto anche come disegno personalizzato, è una tecnica che consente di modificare l'aspetto visivo di alcuni controlli.</span><span class="sxs-lookup"><span data-stu-id="24d2a-103">Owner drawing in Windows Forms, which is also known as custom drawing, is a technique for changing the visual appearance of certain controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24d2a-104">La parola "controllo" in questo argomento viene utilizzata per indicare le classi che derivano da <xref:System.Windows.Forms.Control> o <xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="24d2a-104">The word "control" in this topic is used to mean classes that derive from either <xref:System.Windows.Forms.Control> or <xref:System.ComponentModel.Component>.</span></span>  
  
 <span data-ttu-id="24d2a-105">In genere, Windows gestisce il disegno automaticamente utilizzando le impostazioni delle proprietà, ad esempio <xref:System.Windows.Forms.Control.BackColor%2A> per determinare l'aspetto di un controllo.</span><span class="sxs-lookup"><span data-stu-id="24d2a-105">Typically, Windows handles painting automatically by using property settings such as <xref:System.Windows.Forms.Control.BackColor%2A> to determine the appearance of a control.</span></span> <span data-ttu-id="24d2a-106">Con il disegno da parte del proprietario, si acquisisce la precedenza sul processo di disegno, modificando elementi dell'aspetto non disponibili quando si usano le proprietà.</span><span class="sxs-lookup"><span data-stu-id="24d2a-106">With owner drawing, you take over the painting process, changing elements of appearance that are not available by using properties.</span></span> <span data-ttu-id="24d2a-107">Molti controlli, ad esempio, consentono di impostare il colore del testo visualizzato, ma è previsto un limite di un solo colore.</span><span class="sxs-lookup"><span data-stu-id="24d2a-107">For example, many controls let you set the color of the text that is displayed, but you are limited to a single color.</span></span> <span data-ttu-id="24d2a-108">Il disegno da parte del proprietario consente, ad esempio, di visualizzare parte del testo in nero e parte in rosso.</span><span class="sxs-lookup"><span data-stu-id="24d2a-108">Owner drawing enables you to do things like display part of the text in black and part in red.</span></span>  
  
 <span data-ttu-id="24d2a-109">Il disegno da parte del proprietario è in pratica simile al disegno di elementi grafici in un form.</span><span class="sxs-lookup"><span data-stu-id="24d2a-109">In practice, owner drawing is similar to drawing graphics on a form.</span></span> <span data-ttu-id="24d2a-110">Ad esempio, è possibile utilizzare i metodi grafici in un gestore per il form <xref:System.Windows.Forms.Control.Paint> evento per emulare un `ListBox` controllo, ma è necessario scrivere codice personalizzato per gestire tutte le interazioni utente.</span><span class="sxs-lookup"><span data-stu-id="24d2a-110">For example, you could use graphics methods in a handler for the form's <xref:System.Windows.Forms.Control.Paint> event to emulate a `ListBox` control, but you would have to write your own code to handle all user interaction.</span></span> <span data-ttu-id="24d2a-111">Con il disegno da parte del proprietario, il controllo usa il codice per disegnare i contenuti, ma mantiene tutte le funzionalità intrinseche.</span><span class="sxs-lookup"><span data-stu-id="24d2a-111">With owner drawing, the control uses your code to draw its contents but otherwise retains all its intrinsic capabilities.</span></span> <span data-ttu-id="24d2a-112">È possibile usare metodi Graphics per disegnare ogni elemento nel controllo o per personalizzare alcuni dettagli di ogni elemento mentre si usa l'aspetto predefinito per altri dettagli di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="24d2a-112">You can use graphics methods to draw each item in the control or to customize some aspects of each item while you use the default appearance for other aspects of each item.</span></span>  
  
## <a name="owner-drawing-in-windows-forms-controls"></a><span data-ttu-id="24d2a-113">Disegno da parte del proprietario nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="24d2a-113">Owner Drawing in Windows Forms Controls</span></span>  
 <span data-ttu-id="24d2a-114">Per eseguire il disegno da parte del proprietario nei controlli che lo supportano, in genere è necessario impostare una proprietà e gestire uno o più eventi.</span><span class="sxs-lookup"><span data-stu-id="24d2a-114">To perform owner drawing in controls that support it, you will typically set one property and handle one or more events.</span></span>  
  
 <span data-ttu-id="24d2a-115">La maggior parte dei controlli che supportano il disegno da parte del proprietario ha una proprietà `OwnerDraw` o `DrawMode` che indica se il controllo genera uno o più eventi correlati al disegno quando disegna se stesso.</span><span class="sxs-lookup"><span data-stu-id="24d2a-115">Most controls that support owner drawing have an `OwnerDraw` or `DrawMode` property that indicates whether the control will raise its drawing-related event or events when it paints itself.</span></span>  
  
 <span data-ttu-id="24d2a-116">I controlli senza la proprietà `OwnerDraw` o `DrawMode` includono il controllo `DataGridView`, che fornisce eventi di disegno che si verificano automaticamente, e il controllo `ToolStrip`, che viene disegnato usando una classe di rendering esterna con i propri eventi correlati al disegno.</span><span class="sxs-lookup"><span data-stu-id="24d2a-116">Controls that do not have an `OwnerDraw` or `DrawMode` property include the `DataGridView` control, which provides drawing events that occur automatically, and the `ToolStrip` control, which is drawn using an external rendering class that has its own drawing-related events.</span></span>  
  
 <span data-ttu-id="24d2a-117">Sono disponibili molti tipi di eventi di disegno diversi, ma un evento di disegno tipico si verifica per disegnare un singolo elemento in un controllo.</span><span class="sxs-lookup"><span data-stu-id="24d2a-117">There are many different kinds of drawing events, but a typical drawing event occurs in order to draw a single item within a control.</span></span> <span data-ttu-id="24d2a-118">Il gestore eventi riceve un oggetto `EventArgs` che contiene informazioni sull'elemento che viene disegnato e sugli strumenti che è possibile usare per disegnarlo.</span><span class="sxs-lookup"><span data-stu-id="24d2a-118">The event handler receives an `EventArgs` object that contains information about the item being drawn and tools you can use to draw it.</span></span> <span data-ttu-id="24d2a-119">Ad esempio, l'oggetto contiene in genere il numero di indice dell'elemento all'interno della raccolta padre, un <xref:System.Drawing.Rectangle> che indica i limiti di visualizzazione dell'elemento e un <xref:System.Drawing.Graphics> oggetto per la chiamata di metodi di disegno.</span><span class="sxs-lookup"><span data-stu-id="24d2a-119">For example, this object typically contains the item's index number within its parent collection, a <xref:System.Drawing.Rectangle> that indicates the item's display boundaries, and a <xref:System.Drawing.Graphics> object for calling paint methods.</span></span> <span data-ttu-id="24d2a-120">Per alcuni eventi, l'oggetto `EventArgs` fornisce informazioni aggiuntive sull'elemento e sui metodi che è possibile chiamare per disegnare alcuni dettagli dell'elemento per impostazione predefinita, ad esempio lo sfondo o il rettangolo dello stato attivo.</span><span class="sxs-lookup"><span data-stu-id="24d2a-120">For some events, the `EventArgs` object provides additional information about the item and methods that you can call to paint some aspects of the item by default, such as the background or a focus rectangle.</span></span>  
  
 <span data-ttu-id="24d2a-121">Per creare un controllo riutilizzabile contenente le personalizzazioni disegnate dal proprietario, creare una nuova classe che deriva da una classe di controlli che supporta il disegno da parte del proprietario.</span><span class="sxs-lookup"><span data-stu-id="24d2a-121">To create a reusable control that contains your owner-drawn customizations, create a new class that derives from a control class that supports owner drawing.</span></span> <span data-ttu-id="24d2a-122">Invece di gestire gli eventi di disegno, includere il codice del disegno da parte del proprietario negli override per uno o più metodi `On`*EventName* appropriati nella nuova classe.</span><span class="sxs-lookup"><span data-stu-id="24d2a-122">Rather than handling drawing events, include your owner-drawing code in overrides for the appropriate `On`*EventName* method or methods in the new class.</span></span> <span data-ttu-id="24d2a-123">In questo caso, verificare di chiamare il metodo o i metodi `On`*EventName* della classe base in modo che gli utenti del controllo possano gestire gli eventi di disegno da parte del proprietario e creare personalizzazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="24d2a-123">Make sure that you call the base class `On`*EventName* method or methods in this case so that users of your control can handle owner-drawing events and provide additional customization.</span></span>  
  
 <span data-ttu-id="24d2a-124">I controlli Windows Form seguenti supportano il disegno da parte del proprietario in tutte le versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="24d2a-124">The following Windows Forms controls support owner drawing in all versions of the .NET Framework:</span></span>  
  
-   <xref:System.Windows.Forms.ListBox>  
  
-   <xref:System.Windows.Forms.ComboBox>  
  
-   <span data-ttu-id="24d2a-125"><xref:System.Windows.Forms.MenuItem>(utilizzato da <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu>)</span><span class="sxs-lookup"><span data-stu-id="24d2a-125"><xref:System.Windows.Forms.MenuItem> (used by <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu>)</span></span>  
  
-   <xref:System.Windows.Forms.TabControl>  
  
 <span data-ttu-id="24d2a-126">I controlli seguenti supportano il disegno da parte del proprietario solo in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="24d2a-126">The following controls support owner drawing only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
-   <xref:System.Windows.Forms.ToolTip>  
  
-   <xref:System.Windows.Forms.ListView>  
  
-   <xref:System.Windows.Forms.TreeView>  
  
 <span data-ttu-id="24d2a-127">I controlli seguenti, che supportano il disegno da parte del proprietario, sono nuovi in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="24d2a-127">The following controls support owner drawing and are new in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridView>  
  
-   <xref:System.Windows.Forms.ToolStrip>  
  
 <span data-ttu-id="24d2a-128">Le sezioni seguenti contengono altre informazioni dettagliate su ogni controllo.</span><span class="sxs-lookup"><span data-stu-id="24d2a-128">The following sections provide additional details for each of these controls.</span></span>  
  
### <a name="listbox-and-combobox-controls"></a><span data-ttu-id="24d2a-129">Controlli ListBox e ComboBox</span><span class="sxs-lookup"><span data-stu-id="24d2a-129">ListBox and ComboBox Controls</span></span>  
 <span data-ttu-id="24d2a-130">Il <xref:System.Windows.Forms.ListBox> e <xref:System.Windows.Forms.ComboBox> controlli consentono di disegnare singoli elementi nel controllo stessa dimensione o dimensioni variabili.</span><span class="sxs-lookup"><span data-stu-id="24d2a-130">The <xref:System.Windows.Forms.ListBox> and <xref:System.Windows.Forms.ComboBox> controls enable you to draw individual items in the control either all in one size, or in varying sizes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24d2a-131">Sebbene il <xref:System.Windows.Forms.CheckedListBox> controllo derivato dal <xref:System.Windows.Forms.ListBox> (controllo), non supporta il disegno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="24d2a-131">Although the <xref:System.Windows.Forms.CheckedListBox> control is derived from the <xref:System.Windows.Forms.ListBox> control, it does not support owner drawing.</span></span>  
  
 <span data-ttu-id="24d2a-132">Per disegnare ogni elemento con la stessa dimensione, impostare il `DrawMode` proprietà <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> e gestire il `DrawItem` evento.</span><span class="sxs-lookup"><span data-stu-id="24d2a-132">To draw each item the same size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="24d2a-133">Per disegnare ogni elemento con dimensioni diverse, impostare il `DrawMode` proprietà <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> e gestire entrambi i `MeasureItem` e `DrawItem` eventi.</span><span class="sxs-lookup"><span data-stu-id="24d2a-133">To draw each item using a different size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> and handle both the `MeasureItem` and `DrawItem` events.</span></span> <span data-ttu-id="24d2a-134">L'evento `MeasureItem` consente di indicare le dimensioni di un elemento prima che si verifichi l'evento `DrawItem` per tale elemento.</span><span class="sxs-lookup"><span data-stu-id="24d2a-134">The `MeasureItem` event lets you indicate the size of an item before the `DrawItem` event occurs for that item.</span></span>  
  
 <span data-ttu-id="24d2a-135">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="24d2a-135">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
-   [<span data-ttu-id="24d2a-136">Procedura: Creare testo di dimensioni variabili in un controllo ComboBox</span><span class="sxs-lookup"><span data-stu-id="24d2a-136">How to: Create Variable Sized Text in a ComboBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a><span data-ttu-id="24d2a-137">Componente MenuItem</span><span class="sxs-lookup"><span data-stu-id="24d2a-137">MenuItem Component</span></span>  
 <span data-ttu-id="24d2a-138">Il <xref:System.Windows.Forms.MenuItem> componente rappresenta una singola voce di menu in un <xref:System.Windows.Forms.MainMenu> o <xref:System.Windows.Forms.ContextMenu> componente.</span><span class="sxs-lookup"><span data-stu-id="24d2a-138">The <xref:System.Windows.Forms.MenuItem> component represents a single menu item in a <xref:System.Windows.Forms.MainMenu> or <xref:System.Windows.Forms.ContextMenu> component.</span></span>  
  
 <span data-ttu-id="24d2a-139">Per disegnare un <xref:System.Windows.Forms.MenuItem>, impostare il relativo `OwnerDraw` proprietà `true` e gestire relativo `DrawItem` evento.</span><span class="sxs-lookup"><span data-stu-id="24d2a-139">To draw a <xref:System.Windows.Forms.MenuItem>, set its `OwnerDraw` property to `true` and handle its `DrawItem` event.</span></span> <span data-ttu-id="24d2a-140">Per personalizzare le dimensioni della voce di menu prima che si verifichi l'evento `DrawItem`, gestire l'evento `MeasureItem` dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="24d2a-140">To customize the size of the menu item before the `DrawItem` event occurs, handle the item's `MeasureItem` event.</span></span>  
  
 <span data-ttu-id="24d2a-141">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:</span><span class="sxs-lookup"><span data-stu-id="24d2a-141">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a><span data-ttu-id="24d2a-142">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="24d2a-142">TabControl Control</span></span>  
 <span data-ttu-id="24d2a-143">Il <xref:System.Windows.Forms.TabControl> controllo consente di disegnare singole schede nel controllo.</span><span class="sxs-lookup"><span data-stu-id="24d2a-143">The <xref:System.Windows.Forms.TabControl> control enables you to draw individual tabs in the control.</span></span> <span data-ttu-id="24d2a-144">Il disegno personalizzato influisce solo sulle schede. il <xref:System.Windows.Forms.TabPage> non subiscono alcun contenuto.</span><span class="sxs-lookup"><span data-stu-id="24d2a-144">Owner drawing affects only the tabs; the <xref:System.Windows.Forms.TabPage> contents are not affected.</span></span>  
  
 <span data-ttu-id="24d2a-145">Per disegnare ogni scheda in un <xref:System.Windows.Forms.TabControl>, impostare il `DrawMode` proprietà <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> e gestire il `DrawItem` evento.</span><span class="sxs-lookup"><span data-stu-id="24d2a-145">To draw each tab in a <xref:System.Windows.Forms.TabControl>, set the `DrawMode` property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span> <span data-ttu-id="24d2a-146">Questo evento si verifica una volta per ogni scheda solo quando la scheda è visibile nel controllo.</span><span class="sxs-lookup"><span data-stu-id="24d2a-146">This event occurs once for each tab only when the tab is visible in the control.</span></span>  
  
 <span data-ttu-id="24d2a-147">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:</span><span class="sxs-lookup"><span data-stu-id="24d2a-147">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a><span data-ttu-id="24d2a-148">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="24d2a-148">ToolTip Component</span></span>  
 <span data-ttu-id="24d2a-149">Il <xref:System.Windows.Forms.ToolTip> componente consente di disegnare la descrizione comandi quando viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="24d2a-149">The <xref:System.Windows.Forms.ToolTip> component enables you to draw the entire ToolTip when it is displayed.</span></span>  
  
 <span data-ttu-id="24d2a-150">Per disegnare un <xref:System.Windows.Forms.ToolTip>, impostare il relativo `OwnerDraw` proprietà `true` e gestire relativo `Draw` evento.</span><span class="sxs-lookup"><span data-stu-id="24d2a-150">To draw a <xref:System.Windows.Forms.ToolTip>, set its `OwnerDraw` property to `true` and handle its `Draw` event.</span></span> <span data-ttu-id="24d2a-151">Per personalizzare le dimensioni del <xref:System.Windows.Forms.ToolTip> prima il `Draw` si verifica l'evento, gestire il `Popup` evento e impostare il <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> proprietà nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="24d2a-151">To customize the size of the <xref:System.Windows.Forms.ToolTip> before the `Draw` event occurs, handle the `Popup` event and set the <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> property in the event handler.</span></span>  
  
 <span data-ttu-id="24d2a-152">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:</span><span class="sxs-lookup"><span data-stu-id="24d2a-152">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a><span data-ttu-id="24d2a-153">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="24d2a-153">ListView Control</span></span>  
 <span data-ttu-id="24d2a-154">Il <xref:System.Windows.Forms.ListView> controllo consente di disegnare singoli elementi, gli elementi secondari e le intestazioni di colonna nel controllo.</span><span class="sxs-lookup"><span data-stu-id="24d2a-154">The <xref:System.Windows.Forms.ListView> control enables you to draw individual items, subitems, and column headers in the control.</span></span>  
  
 <span data-ttu-id="24d2a-155">Per abilitare il disegno da parte del proprietario nel controllo, impostare la proprietà `OwnerDraw` su `true`.</span><span class="sxs-lookup"><span data-stu-id="24d2a-155">To enable owner drawing in the control, set the `OwnerDraw` property to `true`.</span></span>  
  
 <span data-ttu-id="24d2a-156">Per disegnare ogni elemento nel controllo, gestire l'evento `DrawItem`.</span><span class="sxs-lookup"><span data-stu-id="24d2a-156">To draw each item in the control, handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="24d2a-157">Per disegnare ogni intestazione dell'elemento secondario o di colonna nel controllo quando il <xref:System.Windows.Forms.ListView.View%2A> è impostata su <xref:System.Windows.Forms.View.Details>, gestire il `DrawSubItem` e `DrawColumnHeader` eventi.</span><span class="sxs-lookup"><span data-stu-id="24d2a-157">To draw each subitem or column header in the control when the <xref:System.Windows.Forms.ListView.View%2A> property is set to <xref:System.Windows.Forms.View.Details>, handle the `DrawSubItem` and `DrawColumnHeader` events.</span></span>  
  
 <span data-ttu-id="24d2a-158">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:</span><span class="sxs-lookup"><span data-stu-id="24d2a-158">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a><span data-ttu-id="24d2a-159">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="24d2a-159">TreeView Control</span></span>  
 <span data-ttu-id="24d2a-160">Il <xref:System.Windows.Forms.TreeView> controllo consente di disegnare singoli nodi nel controllo.</span><span class="sxs-lookup"><span data-stu-id="24d2a-160">The <xref:System.Windows.Forms.TreeView> control enables you to draw individual nodes in the control.</span></span>  
  
 <span data-ttu-id="24d2a-161">Per disegnare solo il testo da visualizzare in ogni nodo, impostare il `DrawMode` proprietà <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> e gestire il `DrawNode` disegnare il testo dell'evento.</span><span class="sxs-lookup"><span data-stu-id="24d2a-161">To draw only the text displayed in each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> and handle the `DrawNode` event to draw the text.</span></span>  
  
 <span data-ttu-id="24d2a-162">Per disegnare tutti gli elementi di ogni nodo, impostare il `DrawMode` proprietà <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> e gestire il `DrawNode` evento necessari, ad esempio testo, icone, caselle di controllo, segni più e meno e linee che collegano i nodi.</span><span class="sxs-lookup"><span data-stu-id="24d2a-162">To draw all elements of each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> and handle the `DrawNode` event to draw whichever elements you need, such as text, icons, check boxes, plus and minus signs, and lines connecting the nodes.</span></span>  
  
 <span data-ttu-id="24d2a-163">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti di riferimento seguenti:</span><span class="sxs-lookup"><span data-stu-id="24d2a-163">For more information, including code examples, see the following reference topics:</span></span>  
  
-   <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a><span data-ttu-id="24d2a-164">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="24d2a-164">DataGridView Control</span></span>  
 <span data-ttu-id="24d2a-165">Il <xref:System.Windows.Forms.DataGridView> controllo consente di disegnare singole celle e righe nel controllo.</span><span class="sxs-lookup"><span data-stu-id="24d2a-165">The <xref:System.Windows.Forms.DataGridView> control enables you to draw individual cells and rows in the control.</span></span>  
  
 <span data-ttu-id="24d2a-166">Per disegnare singole celle, gestire l'evento `CellPainting`.</span><span class="sxs-lookup"><span data-stu-id="24d2a-166">To draw individual cells, handle the `CellPainting` event.</span></span>  
  
 <span data-ttu-id="24d2a-167">Per disegnare singole righe o elementi delle righe, gestire uno o entrambi gli eventi `RowPrePaint` e `RowPostPaint`.</span><span class="sxs-lookup"><span data-stu-id="24d2a-167">To draw individual rows or elements of rows, handle one or both of the `RowPrePaint` and `RowPostPaint` events.</span></span> <span data-ttu-id="24d2a-168">L'evento `RowPrePaint` si verifica prima che le celle in una riga vengano disegnate e l'evento `RowPostPaint` si verifica dopo che le celle sono state disegnate.</span><span class="sxs-lookup"><span data-stu-id="24d2a-168">The `RowPrePaint` event occurs before the cells in a row are painted, and the `RowPostPaint` event occurs after the cells are painted.</span></span> <span data-ttu-id="24d2a-169">È possibile gestire entrambi gli eventi e l'evento `CellPainting` per disegnare separatamente lo sfondo delle righe, le singole celle e il primo piano delle righe oppure è possibile fornire personalizzazioni specifiche ove necessario e usare la visualizzazione predefinita per gli altri elementi della riga.</span><span class="sxs-lookup"><span data-stu-id="24d2a-169">You can handle both events and the `CellPainting` event to paint row background, individual cells, and row foreground separately, or you can provide specific customizations where you need them and use the default display for other elements of the row.</span></span>  
  
 <span data-ttu-id="24d2a-170">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="24d2a-170">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
-   <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
-   [<span data-ttu-id="24d2a-171">Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24d2a-171">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
  
-   [<span data-ttu-id="24d2a-172">Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="24d2a-172">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a><span data-ttu-id="24d2a-173">Controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="24d2a-173">ToolStrip Control</span></span>  
 <span data-ttu-id="24d2a-174"><xref:System.Windows.Forms.ToolStrip>e i controlli derivati consentono di personalizzare l'aspetto di aspetto.</span><span class="sxs-lookup"><span data-stu-id="24d2a-174"><xref:System.Windows.Forms.ToolStrip> and derived controls enable you to customize any aspect of their appearance.</span></span>  
  
 <span data-ttu-id="24d2a-175">Per fornire per il rendering personalizzate per <xref:System.Windows.Forms.ToolStrip> i controlli, impostare il `Renderer` proprietà di un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, o <xref:System.Windows.Forms.ToolStripContentPanel> per un `ToolStripRenderer` dell'oggetto e gestire uno o più dei numerosi eventi di disegno forniti dal `ToolStripRenderer` classe.</span><span class="sxs-lookup"><span data-stu-id="24d2a-175">To provide custom rendering for <xref:System.Windows.Forms.ToolStrip> controls, set the `Renderer` property of a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, or <xref:System.Windows.Forms.ToolStripContentPanel> to a `ToolStripRenderer` object and handle one or more of the many drawing events provided by the `ToolStripRenderer` class.</span></span> <span data-ttu-id="24d2a-176">In alternativa, impostare un `Renderer` proprietà a un'istanza della classe personalizzata derivata da `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, o <xref:System.Windows.Forms.ToolStripSystemRenderer> che implementa o si esegue l'override specifico `On` *EventName* metodi.</span><span class="sxs-lookup"><span data-stu-id="24d2a-176">Alternatively, set a `Renderer` property to an instance of your own class derived from `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, or <xref:System.Windows.Forms.ToolStripSystemRenderer> that implements or overrides specific `On`*EventName* methods.</span></span>  
  
 <span data-ttu-id="24d2a-177">Per altre informazioni, inclusi gli esempi di codice, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="24d2a-177">For more information, including code examples, see the following topics:</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripRenderer>  
  
-   [<span data-ttu-id="24d2a-178">Procedura: Creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Form</span><span class="sxs-lookup"><span data-stu-id="24d2a-178">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
-   [<span data-ttu-id="24d2a-179">Procedura: Eseguire un disegno personalizzato di un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="24d2a-179">How to: Custom Draw a ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a><span data-ttu-id="24d2a-180">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24d2a-180">See Also</span></span>  
 [<span data-ttu-id="24d2a-181">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="24d2a-181">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
