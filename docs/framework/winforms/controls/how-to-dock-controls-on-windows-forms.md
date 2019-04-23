---
title: 'Procedura: Ancorare i controlli in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: d015dce7307bec092f6da1dc5ee31691a6baf1f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317259"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="700f8-102">Procedura: Ancorare i controlli in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="700f8-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="700f8-103">È possibile ancorare i controlli ai bordi dei form o chiedere di riempire il contenitore del controllo (un form o un controllo contenitore).</span><span class="sxs-lookup"><span data-stu-id="700f8-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="700f8-104">Ad esempio, Windows Explorer ancora relativi <xref:System.Windows.Forms.TreeView> controllo sul lato sinistro della finestra e la relativa <xref:System.Windows.Forms.ListView> controllo sul lato destro della finestra.</span><span class="sxs-lookup"><span data-stu-id="700f8-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="700f8-105">Usare il <xref:System.Windows.Forms.Control.Dock%2A> proprietà per tutti i controlli Windows Form visibili definire la modalità di ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="700f8-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="700f8-106">I controlli ancorati in ordine inverso.</span><span class="sxs-lookup"><span data-stu-id="700f8-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="700f8-107">Il <xref:System.Windows.Forms.Control.Dock%2A> proprietà interagisce con il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="700f8-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="700f8-108">Per altre informazioni, vedere [Cenni preliminari sulle proprietà AutoSize](autosize-property-overview.md).</span><span class="sxs-lookup"><span data-stu-id="700f8-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="700f8-109">Per ancorare un controllo</span><span class="sxs-lookup"><span data-stu-id="700f8-109">To dock a control</span></span>  
  
1. <span data-ttu-id="700f8-110">Selezionare il controllo che si desidera ancorare.</span><span class="sxs-lookup"><span data-stu-id="700f8-110">Select the control that you want to dock.</span></span>  
  
2. <span data-ttu-id="700f8-111">Nella finestra Proprietà, fare clic sulla freccia a destra del <xref:System.Windows.Forms.Control.Dock%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="700f8-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="700f8-112">Viene visualizzato un editor che mostra una serie di finestre che rappresenta i bordi e il centro del form.</span><span class="sxs-lookup"><span data-stu-id="700f8-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3. <span data-ttu-id="700f8-113">Fare clic sul pulsante che rappresenta il bordo del form in cui si desidera ancorare il controllo.</span><span class="sxs-lookup"><span data-stu-id="700f8-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="700f8-114">Per riempire il contenuto form del controllo o controllo contenitore, fare clic su casella al centro.</span><span class="sxs-lookup"><span data-stu-id="700f8-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="700f8-115">Fare clic su **(nessuno)** per disabilitare l'ancoraggio.</span><span class="sxs-lookup"><span data-stu-id="700f8-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="700f8-116">Il controllo viene ridimensionato automaticamente per adattarsi ai limiti del bordo ancorato.</span><span class="sxs-lookup"><span data-stu-id="700f8-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="700f8-117">I controlli ereditati devono essere `Protected` per poter essere ancorata.</span><span class="sxs-lookup"><span data-stu-id="700f8-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="700f8-118">Per modificare il livello di accesso di un controllo, impostare il relativo **modificatore** proprietà nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="700f8-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="700f8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="700f8-119">See also</span></span>

- [<span data-ttu-id="700f8-120">Controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="700f8-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="700f8-121">Disposizione di controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="700f8-121">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="700f8-122">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="700f8-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="700f8-123">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="700f8-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="700f8-124">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="700f8-124">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="700f8-125">Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="700f8-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="700f8-126">Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="700f8-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="700f8-127">Panoramica sulla proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="700f8-127">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="700f8-128">Procedura: Ancoraggio dei controlli in Windows Form</span><span class="sxs-lookup"><span data-stu-id="700f8-128">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
