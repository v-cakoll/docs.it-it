---
title: Architettura del controllo DataGridView (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3b3e51b87cdd766adcc10aa3f682647b28fbbe4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="65a2e-102">Architettura del controllo DataGridView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="65a2e-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="65a2e-103">Il <xref:System.Windows.Forms.DataGridView> controllo e le relative classi sono progettate per essere un sistema flessibile ed estendibile per la visualizzazione e modifica di dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="65a2e-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="65a2e-104">Queste classi sono contenute nel <xref:System.Windows.Forms?displayProperty=nameWithType> dello spazio dei nomi e nomi con il prefisso "DataGridView".</span><span class="sxs-lookup"><span data-stu-id="65a2e-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="65a2e-105">Elementi dell'architettura</span><span class="sxs-lookup"><span data-stu-id="65a2e-105">Architecture Elements</span></span>  
 <span data-ttu-id="65a2e-106">Il database primario <xref:System.Windows.Forms.DataGridView> classi correlate derivano da <xref:System.Windows.Forms.DataGridViewElement>.</span><span class="sxs-lookup"><span data-stu-id="65a2e-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="65a2e-107">Il modello a oggetti seguente viene illustrato il <xref:System.Windows.Forms.DataGridViewElement> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="65a2e-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="65a2e-108">![Modello a oggetti DataGridViewElement](../../../../docs/framework/winforms/controls/media/datagridviewelement.gif "DataGridViewElement")</span><span class="sxs-lookup"><span data-stu-id="65a2e-108">![DataGridViewElement Object Model](../../../../docs/framework/winforms/controls/media/datagridviewelement.gif "DataGridViewElement")</span></span>  
<span data-ttu-id="65a2e-109">Modello a oggetti DataGridViewElement</span><span class="sxs-lookup"><span data-stu-id="65a2e-109">DataGridViewElement object model</span></span>  
  
 <span data-ttu-id="65a2e-110">Il <xref:System.Windows.Forms.DataGridViewElement> classe fornisce un riferimento all'elemento padre <xref:System.Windows.Forms.DataGridView> controllare e ha un <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà che contiene un valore che rappresenta una combinazione di valori dal <xref:System.Windows.Forms.DataGridViewElementStates> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="65a2e-110">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="65a2e-111">Le sezioni seguenti descrivono il <xref:System.Windows.Forms.DataGridView> complementare classi in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="65a2e-111">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="65a2e-112">Oggetto DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="65a2e-112">DataGridViewElementStates</span></span>  
 <span data-ttu-id="65a2e-113">Il <xref:System.Windows.Forms.DataGridViewElementStates> enumerazione contiene i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="65a2e-113">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="65a2e-114">I valori di questa enumerazione possono essere combinati con gli operatori logici OR bit per bit, pertanto la <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà in grado di esprimere più di uno stato in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="65a2e-114">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="65a2e-115">Ad esempio, un <xref:System.Windows.Forms.DataGridViewElement> che può essere contemporaneamente <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, e <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span><span class="sxs-lookup"><span data-stu-id="65a2e-115">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="65a2e-116">Le celle e bande</span><span class="sxs-lookup"><span data-stu-id="65a2e-116">Cells and Bands</span></span>  
 <span data-ttu-id="65a2e-117">Il <xref:System.Windows.Forms.DataGridView> controllo comprende due tipi fondamentali di oggetti: celle e bande.</span><span class="sxs-lookup"><span data-stu-id="65a2e-117">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="65a2e-118">Tutte le celle derivano il <xref:System.Windows.Forms.DataGridViewCell> classe di base.</span><span class="sxs-lookup"><span data-stu-id="65a2e-118">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="65a2e-119">I due tipi di bande, <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewRow>, entrambi derivano dalla <xref:System.Windows.Forms.DataGridViewBand> classe di base.</span><span class="sxs-lookup"><span data-stu-id="65a2e-119">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="65a2e-120">Il <xref:System.Windows.Forms.DataGridView> controllo interagisce con diverse classi, ma sono i più comuni <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, e <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="65a2e-120">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="65a2e-121">Oggetto DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="65a2e-121">DataGridViewCell</span></span>  
 <span data-ttu-id="65a2e-122">La cella è l'unità fondamentale di interazione per i <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="65a2e-122">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="65a2e-123">La visualizzazione si basa sulle celle e immissione di dati viene spesso eseguita tramite le celle.</span><span class="sxs-lookup"><span data-stu-id="65a2e-123">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="65a2e-124">È possibile accedere alle celle con il <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> insieme del <xref:System.Windows.Forms.DataGridViewRow> classe ed è possibile accedere alle celle selezionate utilizzando il <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> insieme del <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="65a2e-124">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="65a2e-125">Il modello a oggetti seguente viene illustrato l'utilizzo e Mostra il <xref:System.Windows.Forms.DataGridViewCell> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="65a2e-125">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="65a2e-126">![Modello a oggetti DataGridViewCell](../../../../docs/framework/winforms/controls/media/datagridviewcell.gif "DataGridViewCell")</span><span class="sxs-lookup"><span data-stu-id="65a2e-126">![DataGridViewCell Object Model](../../../../docs/framework/winforms/controls/media/datagridviewcell.gif "DataGridViewCell")</span></span>  
<span data-ttu-id="65a2e-127">Modello a oggetti DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="65a2e-127">DataGridViewCell object model</span></span>  
  
 <span data-ttu-id="65a2e-128">Il <xref:System.Windows.Forms.DataGridViewCell> tipo è una classe base astratta da cui derivano tutti i tipi di cella.</span><span class="sxs-lookup"><span data-stu-id="65a2e-128">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="65a2e-129"><xref:System.Windows.Forms.DataGridViewCell>e i tipi derivati non sono controlli Windows Form, ma alcuni controlli Windows Form host.</span><span class="sxs-lookup"><span data-stu-id="65a2e-129"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="65a2e-130">Supportato da una cella qualsiasi funzionalità di modifica viene in genere gestita da un controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="65a2e-130">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="65a2e-131"><xref:System.Windows.Forms.DataGridViewCell>gli oggetti non controllare l'aspetto e le funzionalità di disegno nello stesso modo dei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="65a2e-131"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="65a2e-132">Al contrario, il <xref:System.Windows.Forms.DataGridView> è responsabile per l'aspetto del relativo <xref:System.Windows.Forms.DataGridViewCell> oggetti.</span><span class="sxs-lookup"><span data-stu-id="65a2e-132">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="65a2e-133">È possibile modificare in modo significativo l'aspetto e il comportamento di celle tramite l'interazione con il <xref:System.Windows.Forms.DataGridView> proprietà e gli eventi del controllo.</span><span class="sxs-lookup"><span data-stu-id="65a2e-133">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="65a2e-134">Quando si dispone di requisiti speciali per le personalizzazioni che vanno oltre le capacità del <xref:System.Windows.Forms.DataGridView> (controllo), è possibile implementare la propria classe che deriva da <xref:System.Windows.Forms.DataGridViewCell> o una delle relative classi figlio.</span><span class="sxs-lookup"><span data-stu-id="65a2e-134">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="65a2e-135">L'elenco seguente mostra le classi derivate da <xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="65a2e-135">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
-   <xref:System.Windows.Forms.DataGridViewImageCell>  
  
-   <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
-   <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
-   <span data-ttu-id="65a2e-136">I tipi di cella personalizzato</span><span class="sxs-lookup"><span data-stu-id="65a2e-136">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="65a2e-137">Elemento DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="65a2e-137">DataGridViewColumn</span></span>  
 <span data-ttu-id="65a2e-138">Lo schema del <xref:System.Windows.Forms.DataGridView> archivio dati collegati del controllo è espresso il <xref:System.Windows.Forms.DataGridView> colonne del controllo.</span><span class="sxs-lookup"><span data-stu-id="65a2e-138">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="65a2e-139">È possibile accedere il <xref:System.Windows.Forms.DataGridView> colonne del controllo utilizzando il <xref:System.Windows.Forms.DataGridView.Columns%2A> insieme.</span><span class="sxs-lookup"><span data-stu-id="65a2e-139">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="65a2e-140">È possibile accedere alle colonne selezionate utilizzando il <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> insieme.</span><span class="sxs-lookup"><span data-stu-id="65a2e-140">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="65a2e-141">Il modello a oggetti seguente viene illustrato l'utilizzo e Mostra il <xref:System.Windows.Forms.DataGridViewColumn> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="65a2e-141">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="65a2e-142">![Modello a oggetti DataGridViewColumn](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.gif "DataGridViewColumn")</span><span class="sxs-lookup"><span data-stu-id="65a2e-142">![DataGridViewColumn Object Model](../../../../docs/framework/winforms/controls/media/datagridviewcolumn.gif "DataGridViewColumn")</span></span>  
<span data-ttu-id="65a2e-143">Modello a oggetti DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="65a2e-143">DataGridViewColumn object model</span></span>  
  
 <span data-ttu-id="65a2e-144">Alcuni dei tipi di cella chiave hanno tipi di colonna corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="65a2e-144">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="65a2e-145">Questi sono derivati dalla <xref:System.Windows.Forms.DataGridViewColumn> classe di base.</span><span class="sxs-lookup"><span data-stu-id="65a2e-145">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="65a2e-146">L'elenco seguente mostra le classi derivate da <xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="65a2e-146">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   <span data-ttu-id="65a2e-147">Tipi di colonna personalizzati</span><span class="sxs-lookup"><span data-stu-id="65a2e-147">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="65a2e-148">Controlli di modifica DataGridView</span><span class="sxs-lookup"><span data-stu-id="65a2e-148">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="65a2e-149">Le celle che supportano le funzionalità avanzate di modifica in genere utilizzano un controllo derivato da un controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="65a2e-149">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="65a2e-150">Questi controlli implementano anche il <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="65a2e-150">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="65a2e-151">Il modello a oggetti seguente viene illustrato l'utilizzo di questi controlli.</span><span class="sxs-lookup"><span data-stu-id="65a2e-151">The following object model illustrates the usage of these controls.</span></span>  
  
 <span data-ttu-id="65a2e-152">![Modello oggetto di controllo di modifica DataGridView](../../../../docs/framework/winforms/controls/media/datagridviewediting.gif "DataGridViewEditing")</span><span class="sxs-lookup"><span data-stu-id="65a2e-152">![DataGridView Editing Control Object Model](../../../../docs/framework/winforms/controls/media/datagridviewediting.gif "DataGridViewEditing")</span></span>  
<span data-ttu-id="65a2e-153">Modifica modello a oggetti controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="65a2e-153">DataGridView editing control object model</span></span>  
  
 <span data-ttu-id="65a2e-154">Vengono forniti i seguenti controlli di modificando con il <xref:System.Windows.Forms.DataGridView> controllo:</span><span class="sxs-lookup"><span data-stu-id="65a2e-154">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="65a2e-155">Per informazioni sulla creazione di controlli personalizzati di modifica, vedere [come: i controlli Host nelle celle del controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).</span><span class="sxs-lookup"><span data-stu-id="65a2e-155">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="65a2e-156">Nella tabella seguente viene illustrata la relazione tra i tipi di cella, i tipi di colonna e i controlli di modifica.</span><span class="sxs-lookup"><span data-stu-id="65a2e-156">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="65a2e-157">Tipo di cella</span><span class="sxs-lookup"><span data-stu-id="65a2e-157">Cell type</span></span>|<span data-ttu-id="65a2e-158">Controllo ospitato</span><span class="sxs-lookup"><span data-stu-id="65a2e-158">Hosted control</span></span>|<span data-ttu-id="65a2e-159">Tipo di colonna</span><span class="sxs-lookup"><span data-stu-id="65a2e-159">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="65a2e-160">N/D</span><span class="sxs-lookup"><span data-stu-id="65a2e-160">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="65a2e-161">n/d</span><span class="sxs-lookup"><span data-stu-id="65a2e-161">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="65a2e-162">n/d</span><span class="sxs-lookup"><span data-stu-id="65a2e-162">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="65a2e-163">N/D</span><span class="sxs-lookup"><span data-stu-id="65a2e-163">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="65a2e-164">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="65a2e-164">DataGridViewRow</span></span>  
 <span data-ttu-id="65a2e-165">Il <xref:System.Windows.Forms.DataGridViewRow> Visualizza di classe campi dati di un record dai dati di archivio a cui il <xref:System.Windows.Forms.DataGridView> controllo associato.</span><span class="sxs-lookup"><span data-stu-id="65a2e-165">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="65a2e-166">È possibile accedere il <xref:System.Windows.Forms.DataGridView> righe del controllo utilizzando il <xref:System.Windows.Forms.DataGridView.Rows%2A> insieme.</span><span class="sxs-lookup"><span data-stu-id="65a2e-166">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="65a2e-167">È possibile accedere alle righe selezionate utilizzando il <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> insieme.</span><span class="sxs-lookup"><span data-stu-id="65a2e-167">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="65a2e-168">Il modello a oggetti seguente viene illustrato l'utilizzo e Mostra il <xref:System.Windows.Forms.DataGridViewRow> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="65a2e-168">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="65a2e-169">![Modello a oggetti DataGridViewRow](../../../../docs/framework/winforms/controls/media/datagridviewrow.gif "DataGridViewRow")</span><span class="sxs-lookup"><span data-stu-id="65a2e-169">![DataGridViewRow Object Model](../../../../docs/framework/winforms/controls/media/datagridviewrow.gif "DataGridViewRow")</span></span>  
<span data-ttu-id="65a2e-170">Modello a oggetti DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="65a2e-170">DataGridViewRow object model</span></span>  
  
 <span data-ttu-id="65a2e-171">È possibile derivare tipi personalizzati dalla <xref:System.Windows.Forms.DataGridViewRow> classe, anche se ciò corrisponderà in genere non necessario.</span><span class="sxs-lookup"><span data-stu-id="65a2e-171">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="65a2e-172">Il <xref:System.Windows.Forms.DataGridView> controllo dispone di numerosi eventi correlati alla riga e proprietà per personalizzare il comportamento del relativo <xref:System.Windows.Forms.DataGridViewRow> oggetti.</span><span class="sxs-lookup"><span data-stu-id="65a2e-172">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="65a2e-173">Se si abilita il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> viene visualizzata una riga speciale per l'aggiunta di nuove righe di proprietà, come l'ultima riga.</span><span class="sxs-lookup"><span data-stu-id="65a2e-173">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="65a2e-174">Questa riga fa parte di <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta, ma dispone di funzionalità speciali che potrebbero richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="65a2e-174">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="65a2e-175">Per ulteriori informazioni, vedere [mediante la riga dei nuovi record nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="65a2e-175">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a2e-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65a2e-176">See Also</span></span>  
 [<span data-ttu-id="65a2e-177">Panoramica sul controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="65a2e-177">DataGridView Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)  
 [<span data-ttu-id="65a2e-178">Personalizzazione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="65a2e-178">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="65a2e-179">Uso della riga per i nuovi record del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="65a2e-179">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
