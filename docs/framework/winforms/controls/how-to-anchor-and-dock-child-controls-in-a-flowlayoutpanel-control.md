---
title: 'Procedura: ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel'
description: Informazioni su come agganciare e ancorare i controlli figlio a livello di codice in un Windows Forms controllo FlowLayoutPanel.
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: b4fb3bf6d148a526a75926bd67c1f967286332bf
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174536"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="a1786-103">Procedura: ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a1786-103">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>

<span data-ttu-id="a1786-104">Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> supporta le proprietà <xref:System.Windows.Forms.Control.Anchor%2A> e <xref:System.Windows.Forms.Control.Dock%2A> nei controlli figlio.</span><span class="sxs-lookup"><span data-stu-id="a1786-104">The <xref:System.Windows.Forms.FlowLayoutPanel> control supports the <xref:System.Windows.Forms.Control.Anchor%2A> and <xref:System.Windows.Forms.Control.Dock%2A> properties in its child controls.</span></span>

### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a><span data-ttu-id="a1786-105">Per ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a1786-105">To anchor and dock child controls in a FlowLayoutPanel control</span></span>

1. <span data-ttu-id="a1786-106">Creare un controllo <xref:System.Windows.Forms.FlowLayoutPanel> nel form.</span><span class="sxs-lookup"><span data-stu-id="a1786-106">Create a <xref:System.Windows.Forms.FlowLayoutPanel> control on your form.</span></span>

2. <span data-ttu-id="a1786-107">Impostare la proprietà <xref:System.Windows.Forms.Control.Width%2A> del <xref:System.Windows.Forms.FlowLayoutPanel> controllo su **300**e impostare la relativa proprietà <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> su <xref:System.Windows.Forms.FlowDirection.TopDown> .</span><span class="sxs-lookup"><span data-stu-id="a1786-107">Set the <xref:System.Windows.Forms.Control.Width%2A> of the <xref:System.Windows.Forms.FlowLayoutPanel> control to **300**, and set its <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> to <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>

3. <span data-ttu-id="a1786-108">Creare due controlli <xref:System.Windows.Forms.Button> e inserirli nel controllo <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="a1786-108">Create two <xref:System.Windows.Forms.Button> controls, and place them in the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

4. <span data-ttu-id="a1786-109">Impostare la <xref:System.Windows.Forms.Control.Width%2A> del primo pulsante su **200**.</span><span class="sxs-lookup"><span data-stu-id="a1786-109">Set the <xref:System.Windows.Forms.Control.Width%2A> of the first button to **200**.</span></span>

5. <span data-ttu-id="a1786-110">Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> del secondo pulsante su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="a1786-110">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1786-111">Il secondo pulsante assume la stessa larghezza del primo.</span><span class="sxs-lookup"><span data-stu-id="a1786-111">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="a1786-112">Non si adatta alla larghezza del controllo <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="a1786-112">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="a1786-113">Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> del secondo pulsante su `None`.</span><span class="sxs-lookup"><span data-stu-id="a1786-113">Set the <xref:System.Windows.Forms.Control.Dock%2A> property of the second button to `None`.</span></span> <span data-ttu-id="a1786-114">Verrà ripristinata la larghezza originale del pulsante.</span><span class="sxs-lookup"><span data-stu-id="a1786-114">This causes the button to assume its original width.</span></span>

7. <span data-ttu-id="a1786-115">Impostare la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> del secondo pulsante su `Left, Right`.</span><span class="sxs-lookup"><span data-stu-id="a1786-115">Set the <xref:System.Windows.Forms.Control.Anchor%2A> property of the second button to `Left, Right`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a1786-116">Il secondo pulsante assume la stessa larghezza del primo.</span><span class="sxs-lookup"><span data-stu-id="a1786-116">The second button assumes the same width as the first button.</span></span> <span data-ttu-id="a1786-117">Non si adatta alla larghezza del controllo <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="a1786-117">It does not stretch across the width of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span> <span data-ttu-id="a1786-118">Di seguito è riportata la regola generale per l'ancoraggio e l'aggancio nel controllo <xref:System.Windows.Forms.FlowLayoutPanel>: per le direzioni del flusso verticale il controllo <xref:System.Windows.Forms.FlowLayoutPanel> calcola la larghezza di una colonna implicita dal controllo figlio più largo presente nella colonna.</span><span class="sxs-lookup"><span data-stu-id="a1786-118">This is the general rule for anchoring and docking in the <xref:System.Windows.Forms.FlowLayoutPanel> control: for vertical flow directions, the <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the width of an implied column from the widest child control in the column.</span></span> <span data-ttu-id="a1786-119">Tutti gli altri controlli in questa colonna con la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> o <xref:System.Windows.Forms.Control.Dock%2A> vengono allineati o estesi in base alla colonna implicita.</span><span class="sxs-lookup"><span data-stu-id="a1786-119">All other controls in this column with <xref:System.Windows.Forms.Control.Anchor%2A> or <xref:System.Windows.Forms.Control.Dock%2A> properties are aligned or stretched to fit this implied column.</span></span> <span data-ttu-id="a1786-120">Le direzioni del flusso orizzontale si comportano in modo simile.</span><span class="sxs-lookup"><span data-stu-id="a1786-120">The behavior works in a similar way for horizontal flow directions.</span></span> <span data-ttu-id="a1786-121">Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> calcola l'altezza di una riga implicita dal controllo figlio più alto presente nella riga e tutti i controlli figlio agganciati o ancorati in questa riga vengono allineati o ridimensionati di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="a1786-121">The <xref:System.Windows.Forms.FlowLayoutPanel> control calculates the height of an implied row from the tallest child control in the row, and all docked or anchored child controls in this row are aligned or sized to fit the implied row.</span></span>

## <a name="example"></a><span data-ttu-id="a1786-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="a1786-122">Example</span></span>

<span data-ttu-id="a1786-123">La figura seguente illustra quattro pulsanti ancorati e agganciati rispetto al pulsante blu in un controllo <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="a1786-123">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="a1786-124">Il <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> è <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span><span class="sxs-lookup"><span data-stu-id="a1786-124">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.LeftToRight>.</span></span>

<span data-ttu-id="a1786-125">![Ancoraggio FlowLayoutPanel](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span><span class="sxs-lookup"><span data-stu-id="a1786-125">![FlowLayoutPanel anchoring](./media/net-flpanchorexp.gif "NET_FLPanchorExp")</span></span>

<span data-ttu-id="a1786-126">La figura seguente illustra quattro pulsanti ancorati e agganciati rispetto al pulsante blu in un controllo <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="a1786-126">The following illustration shows four buttons that are anchored and docked relative to the blue button in a <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="a1786-127">Il <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> è <xref:System.Windows.Forms.FlowDirection.TopDown>.</span><span class="sxs-lookup"><span data-stu-id="a1786-127">The <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> is <xref:System.Windows.Forms.FlowDirection.TopDown>.</span></span>

<span data-ttu-id="a1786-128">![Ancoraggio FlowLayoutPanel](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span><span class="sxs-lookup"><span data-stu-id="a1786-128">![FlowLayoutPanel anchoring](./media/vs-flpanchor2.gif "VS_FLPanchor2")</span></span>

<span data-ttu-id="a1786-129">L'esempio di codice seguente illustra diversi valori della proprietà <xref:System.Windows.Forms.Control.Anchor%2A> per un controllo <xref:System.Windows.Forms.Button> in un controllo <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="a1786-129">The following code example demonstrates various <xref:System.Windows.Forms.Control.Anchor%2A> property values for a <xref:System.Windows.Forms.Button> control in a <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

[!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
[!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]

## <a name="compiling-the-code"></a><span data-ttu-id="a1786-130">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a1786-130">Compiling the Code</span></span>

<span data-ttu-id="a1786-131">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a1786-131">This example requires:</span></span>

- <span data-ttu-id="a1786-132">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="a1786-132">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1786-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1786-133">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="a1786-134">Cenni preliminari sul controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="a1786-134">FlowLayoutPanel Control Overview</span></span>](flowlayoutpanel-control-overview.md)
