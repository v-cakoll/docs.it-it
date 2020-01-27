---
title: Ancorare i controlli (Dock)
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 02f1c26dcb322a39c41781c83d8c820bd2fd27e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745518"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="8ae0a-102">Procedura: ancorare i controlli in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8ae0a-102">How to: Dock controls on Windows Forms</span></span>

<span data-ttu-id="8ae0a-103">È possibile ancorare i controlli ai bordi del form oppure fare in modo che riempiano il contenitore del controllo, ovvero un form o un controllo contenitore.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="8ae0a-104">Esplora risorse, ad esempio, ancora il controllo <xref:System.Windows.Forms.TreeView> al lato sinistro della finestra e il relativo controllo <xref:System.Windows.Forms.ListView> sul lato destro della finestra.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="8ae0a-105">Usare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> per tutti i controlli Windows Forms visibili per definire la modalità di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>

> [!NOTE]
> <span data-ttu-id="8ae0a-106">I controlli sono ancorati nell'ordine z inverso.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-106">Controls are docked in reverse z-order.</span></span>

<span data-ttu-id="8ae0a-107">La proprietà <xref:System.Windows.Forms.Control.Dock%2A> interagisce con la proprietà <xref:System.Windows.Forms.Control.AutoSize%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="8ae0a-108">Per ulteriori informazioni, vedere [Panoramica delle proprietà AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8ae0a-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="to-dock-a-control"></a><span data-ttu-id="8ae0a-109">Per ancorare un controllo</span><span class="sxs-lookup"><span data-stu-id="8ae0a-109">To dock a control</span></span>

1. <span data-ttu-id="8ae0a-110">In Visual Studio selezionare il controllo che si desidera ancorare.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-110">In Visual Studio, select the control that you want to dock.</span></span>

2. <span data-ttu-id="8ae0a-111">Nella finestra **Proprietà** fare clic sulla freccia a destra della proprietà <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-111">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

   <span data-ttu-id="8ae0a-112">Viene visualizzato un editor che mostra una serie di caselle che rappresentano i bordi e il centro del form.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>

3. <span data-ttu-id="8ae0a-113">Fare clic sul pulsante che rappresenta il bordo del form in cui si desidera ancorare il controllo.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="8ae0a-114">Per riempire il contenuto del form o del controllo contenitore del controllo, fare clic sulla casella al centro.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="8ae0a-115">Per disabilitare l'ancoraggio, fare clic su **(nessuno)** .</span><span class="sxs-lookup"><span data-stu-id="8ae0a-115">Click **(none)** to disable docking.</span></span>

   <span data-ttu-id="8ae0a-116">Il controllo viene ridimensionato automaticamente per adattarsi ai limiti del bordo ancorato.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8ae0a-117">I controlli ereditati devono essere `Protected` per poter essere ancorati.</span><span class="sxs-lookup"><span data-stu-id="8ae0a-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="8ae0a-118">Per modificare il livello di accesso di un controllo, impostarne la proprietà **Modifier** nella finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="8ae0a-118">To change the access level of a control, set its **Modifier** property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ae0a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ae0a-119">See also</span></span>

- [<span data-ttu-id="8ae0a-120">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="8ae0a-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="8ae0a-121">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="8ae0a-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="8ae0a-122">Controlli da utilizzare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="8ae0a-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="8ae0a-123">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="8ae0a-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="8ae0a-124">Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8ae0a-124">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="8ae0a-125">Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8ae0a-125">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="8ae0a-126">Panoramica sulla proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="8ae0a-126">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="8ae0a-127">Procedura: Agganciare i controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="8ae0a-127">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
