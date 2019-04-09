---
title: Architettura del controllo DataGridView (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 892168ec282fbf168c43515e0718fe5486a345a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130260"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="c145e-102">Architettura del controllo DataGridView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="c145e-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="c145e-103">Il <xref:System.Windows.Forms.DataGridView> controllo e le classi correlate sono progettate per essere un sistema flessibile ed estendibile per la visualizzazione e modifica di dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="c145e-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="c145e-104">Tutte queste classi sono contenute nel <xref:System.Windows.Forms?displayProperty=nameWithType> dello spazio dei nomi essi sono denominati con il prefisso "DataGridView".</span><span class="sxs-lookup"><span data-stu-id="c145e-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="c145e-105">Elementi dell'architettura</span><span class="sxs-lookup"><span data-stu-id="c145e-105">Architecture Elements</span></span>  
 <span data-ttu-id="c145e-106">Il database primario <xref:System.Windows.Forms.DataGridView> complementare classi derivano da <xref:System.Windows.Forms.DataGridViewElement>.</span><span class="sxs-lookup"><span data-stu-id="c145e-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="c145e-107">Il modello a oggetti seguente viene illustrato il <xref:System.Windows.Forms.DataGridViewElement> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="c145e-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewElement.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="c145e-109">Il <xref:System.Windows.Forms.DataGridViewElement> classe fornisce un riferimento all'elemento padre <xref:System.Windows.Forms.DataGridView> controllano e dispone di un <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà, che contiene un valore che rappresenta una combinazione di valori dal <xref:System.Windows.Forms.DataGridViewElementStates> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c145e-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="c145e-110">Le sezioni seguenti descrivono la <xref:System.Windows.Forms.DataGridView> companion in classi in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="c145e-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="c145e-111">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="c145e-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="c145e-112">Il <xref:System.Windows.Forms.DataGridViewElementStates> enumerazione contiene i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c145e-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
-   <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="c145e-113">I valori di questa enumerazione possono essere combinati con gli operatori logici bit per bit, pertanto il <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà possibile esprimere in una sola volta più di uno stato.</span><span class="sxs-lookup"><span data-stu-id="c145e-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="c145e-114">Ad esempio, un <xref:System.Windows.Forms.DataGridViewElement> può essere contemporaneamente <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, e <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span><span class="sxs-lookup"><span data-stu-id="c145e-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="c145e-115">Le celle e bande</span><span class="sxs-lookup"><span data-stu-id="c145e-115">Cells and Bands</span></span>  
 <span data-ttu-id="c145e-116">Il <xref:System.Windows.Forms.DataGridView> comprende due tipi principali di oggetti: le celle e bande.</span><span class="sxs-lookup"><span data-stu-id="c145e-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="c145e-117">Tutte le celle derivano dal <xref:System.Windows.Forms.DataGridViewCell> classe di base.</span><span class="sxs-lookup"><span data-stu-id="c145e-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="c145e-118">I due tipi di bande, <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewRow>, entrambi derivano dal <xref:System.Windows.Forms.DataGridViewBand> classe di base.</span><span class="sxs-lookup"><span data-stu-id="c145e-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="c145e-119">Il <xref:System.Windows.Forms.DataGridView> controllo interagisce con diverse classi, ma sono le più comuni <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, e <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="c145e-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="c145e-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="c145e-120">DataGridViewCell</span></span>  
 <span data-ttu-id="c145e-121">La cella è l'unità fondamentale di interazione per i <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="c145e-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="c145e-122">La visualizzazione si basa su celle e immissione di dati viene spesso eseguita tramite le celle.</span><span class="sxs-lookup"><span data-stu-id="c145e-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="c145e-123">Le celle è possibile accedere usando il <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> raccolta del <xref:System.Windows.Forms.DataGridViewRow> classe ed è possibile accedere alle celle selezionate tramite il <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> raccolta del <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="c145e-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c145e-124">Il modello a oggetti seguente ne illustra l'utilizzo e viene illustrato il <xref:System.Windows.Forms.DataGridViewCell> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="c145e-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewCell.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="c145e-126">Il <xref:System.Windows.Forms.DataGridViewCell> tipo è una classe base astratta, da cui derivano tutti i tipi di cella.</span><span class="sxs-lookup"><span data-stu-id="c145e-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <xref:System.Windows.Forms.DataGridViewCell> <span data-ttu-id="c145e-127">e non i relativi tipi derivati sono controlli Windows Form, ma alcuni controlli Windows Form host.</span><span class="sxs-lookup"><span data-stu-id="c145e-127">and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="c145e-128">Nessuna funzionalità di modifica supportata da una cella viene in genere gestita da un controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="c145e-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell> <span data-ttu-id="c145e-129">gli oggetti non controllano proprio aspetto e funzionalità di disegno nello stesso modo dei controlli Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c145e-129">objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="c145e-130">Al contrario, il <xref:System.Windows.Forms.DataGridView> è responsabile per l'aspetto del relativo <xref:System.Windows.Forms.DataGridViewCell> oggetti.</span><span class="sxs-lookup"><span data-stu-id="c145e-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="c145e-131">È possibile modificare in modo significativo l'aspetto e il comportamento di celle tramite l'interazione con il <xref:System.Windows.Forms.DataGridView> proprietà e gli eventi del controllo.</span><span class="sxs-lookup"><span data-stu-id="c145e-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="c145e-132">Quando si hanno requisiti speciali per le personalizzazioni che vanno oltre le capacità dei <xref:System.Windows.Forms.DataGridView> (controllo), è possibile implementare una classe che deriva da <xref:System.Windows.Forms.DataGridViewCell> o una delle relative classi figlio.</span><span class="sxs-lookup"><span data-stu-id="c145e-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="c145e-133">Nell'elenco seguente vengono illustrate le classi derivate da <xref:System.Windows.Forms.DataGridViewCell>:</span><span class="sxs-lookup"><span data-stu-id="c145e-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
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
  
-   <span data-ttu-id="c145e-134">I tipi di cella personalizzato</span><span class="sxs-lookup"><span data-stu-id="c145e-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="c145e-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="c145e-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="c145e-136">Lo schema del <xref:System.Windows.Forms.DataGridView> archivio di dati collegati del controllo è espressa nel <xref:System.Windows.Forms.DataGridView> colonne del controllo.</span><span class="sxs-lookup"><span data-stu-id="c145e-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="c145e-137">È possibile accedere la <xref:System.Windows.Forms.DataGridView> colonne del controllo utilizzando il <xref:System.Windows.Forms.DataGridView.Columns%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="c145e-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="c145e-138">È possibile accedere alle colonne selezionate tramite il <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="c145e-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="c145e-139">Il modello a oggetti seguente ne illustra l'utilizzo e viene illustrato il <xref:System.Windows.Forms.DataGridViewColumn> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="c145e-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewColumn.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="c145e-141">Alcuni dei tipi di cella chiave hanno tipi di colonna corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="c145e-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="c145e-142">Questi sono derivati dal <xref:System.Windows.Forms.DataGridViewColumn> classe di base.</span><span class="sxs-lookup"><span data-stu-id="c145e-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="c145e-143">Nell'elenco seguente vengono illustrate le classi derivate da <xref:System.Windows.Forms.DataGridViewColumn>:</span><span class="sxs-lookup"><span data-stu-id="c145e-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
-   <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
-   <span data-ttu-id="c145e-144">I tipi di colonna personalizzata</span><span class="sxs-lookup"><span data-stu-id="c145e-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="c145e-145">Controlli di modifica DataGridView</span><span class="sxs-lookup"><span data-stu-id="c145e-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="c145e-146">Le celle che supportano le funzionalità avanzate di modifica in genere usano un controllo ospitato che deriva da un controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c145e-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="c145e-147">Questi controlli implementano anche il <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c145e-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="c145e-148">Il modello a oggetti seguente viene illustrato l'utilizzo di questi controlli.</span><span class="sxs-lookup"><span data-stu-id="c145e-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![Diagramma che mostra la gerarchia del modello oggetto di controllo di modifica DataGridView.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="c145e-150">I seguenti controlli di modifica forniti con il <xref:System.Windows.Forms.DataGridView> controllo:</span><span class="sxs-lookup"><span data-stu-id="c145e-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
-   <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
-   <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="c145e-151">Per informazioni sulla creazione di controlli personalizzati di modifica, vedere [come: Inserire controlli in Windows Form celle DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span><span class="sxs-lookup"><span data-stu-id="c145e-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="c145e-152">Nella tabella seguente viene illustrata la relazione tra i tipi di cella, tipi di colonna e i controlli di modifica.</span><span class="sxs-lookup"><span data-stu-id="c145e-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="c145e-153">Tipo di cella</span><span class="sxs-lookup"><span data-stu-id="c145e-153">Cell type</span></span>|<span data-ttu-id="c145e-154">Controllo ospitato</span><span class="sxs-lookup"><span data-stu-id="c145e-154">Hosted control</span></span>|<span data-ttu-id="c145e-155">Tipo di colonna</span><span class="sxs-lookup"><span data-stu-id="c145e-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="c145e-156">N/D</span><span class="sxs-lookup"><span data-stu-id="c145e-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="c145e-157">N/D</span><span class="sxs-lookup"><span data-stu-id="c145e-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="c145e-158">N/D</span><span class="sxs-lookup"><span data-stu-id="c145e-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="c145e-159">N/D</span><span class="sxs-lookup"><span data-stu-id="c145e-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="c145e-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="c145e-160">DataGridViewRow</span></span>  
 <span data-ttu-id="c145e-161">Il <xref:System.Windows.Forms.DataGridViewRow> classe visualizza i campi dati di un record dai dati di archivio a cui il <xref:System.Windows.Forms.DataGridView> controllo associato.</span><span class="sxs-lookup"><span data-stu-id="c145e-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="c145e-162">È possibile accedere la <xref:System.Windows.Forms.DataGridView> righe del controllo utilizzando il <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="c145e-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="c145e-163">È possibile accedere alle righe selezionate tramite il <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="c145e-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="c145e-164">Il modello a oggetti seguente ne illustra l'utilizzo e viene illustrato il <xref:System.Windows.Forms.DataGridViewRow> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="c145e-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewRow.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="c145e-166">È possibile derivare tipi personalizzati dal <xref:System.Windows.Forms.DataGridViewRow> classe, anche se ciò in genere non sarà più necessario.</span><span class="sxs-lookup"><span data-stu-id="c145e-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="c145e-167">Il <xref:System.Windows.Forms.DataGridView> controllo dispone di diversi eventi correlati alla riga e le proprietà per personalizzare il comportamento del relativo <xref:System.Windows.Forms.DataGridViewRow> oggetti.</span><span class="sxs-lookup"><span data-stu-id="c145e-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="c145e-168">Se si abilita il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> viene visualizzata una riga speciale per l'aggiunta di nuove righe di proprietà, come l'ultima riga.</span><span class="sxs-lookup"><span data-stu-id="c145e-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="c145e-169">Questa riga fa parte di <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta, ma ha funzionalità speciali che potrebbero richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="c145e-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="c145e-170">Per altre informazioni, vedere [usando la riga per i nuovi record nel controllo DataGridView Windows Form](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="c145e-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c145e-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c145e-171">See also</span></span>

- [<span data-ttu-id="c145e-172">Panoramica del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="c145e-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="c145e-173">Personalizzazione del controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="c145e-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="c145e-174">Utilizzo della riga per i nuovi record del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c145e-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
