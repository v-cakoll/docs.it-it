---
title: 'Procedura: Allineare un controllo ai bordi dei moduli in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: 8f74a6b56e99e016bfb27bbe1b271f6c71af8f87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140894"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="47bf3-102">Procedura: Allineare un controllo ai bordi dei moduli in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="47bf3-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>
<span data-ttu-id="47bf3-103">È possibile allineare un controllo per il bordo dei form impostando la <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="47bf3-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A>.</span></span> <span data-ttu-id="47bf3-104">che designa la posizione del controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="47bf3-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="47bf3-105">La proprietà <xref:System.Windows.Forms.Control.Dock%2A> può essere impostata su uno dei valori riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="47bf3-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="47bf3-106">Impostazione</span><span class="sxs-lookup"><span data-stu-id="47bf3-106">Setting</span></span>|<span data-ttu-id="47bf3-107">Effetto sul controllo</span><span class="sxs-lookup"><span data-stu-id="47bf3-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="47bf3-108">Il controllo viene ancorato alla parte inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="47bf3-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="47bf3-109">Il controllo occupa tutto lo spazio rimanente nel form.</span><span class="sxs-lookup"><span data-stu-id="47bf3-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="47bf3-110">Il controllo viene ancorato al lato sinistro del form.</span><span class="sxs-lookup"><span data-stu-id="47bf3-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="47bf3-111">Non viene ancorato e viene visualizzato nella posizione specificata dal relativo <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="47bf3-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="47bf3-112">Il controllo viene ancorato al lato destro del form.</span><span class="sxs-lookup"><span data-stu-id="47bf3-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="47bf3-113">Il controllo viene ancorato alla parte superiore del form.</span><span class="sxs-lookup"><span data-stu-id="47bf3-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="47bf3-114">Questi valori possono anche essere impostati nel codice.</span><span class="sxs-lookup"><span data-stu-id="47bf3-114">These values can also be set in code.</span></span> <span data-ttu-id="47bf3-115">Per altre informazioni, vedere [Procedura: Allineare un controllo ai bordi dei form](how-to-align-a-control-to-the-edges-of-forms.md).</span><span class="sxs-lookup"><span data-stu-id="47bf3-115">For more information, see [How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47bf3-116">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="47bf3-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="47bf3-117">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="47bf3-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="47bf3-118">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="47bf3-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="47bf3-119">Per impostare la proprietà Dock del controllo in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="47bf3-119">To set the Dock property for your control at design time</span></span>  
  
1.  <span data-ttu-id="47bf3-120">Nella finestra di progettazione Windows Form, selezionare il controllo.</span><span class="sxs-lookup"><span data-stu-id="47bf3-120">In the Windows Forms Designer, select your control.</span></span>  
  
2.  <span data-ttu-id="47bf3-121">Nel **delle proprietà** fare clic sulla casella di elenco a discesa accanto al <xref:System.Windows.Forms.Control.Dock%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="47bf3-121">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="47bf3-122">Un'interfaccia grafica che rappresenta le sei possibili <xref:System.Windows.Forms.Control.Dock%2A> impostazioni viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="47bf3-122">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>  
  
3.  <span data-ttu-id="47bf3-123">Scegliere l'impostazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="47bf3-123">Choose the appropriate setting.</span></span>  
  
4.  <span data-ttu-id="47bf3-124">Il controllo verrà ancorato nel modo specificato dall'impostazione.</span><span class="sxs-lookup"><span data-stu-id="47bf3-124">Your control will now dock in the manner specified by the setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47bf3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="47bf3-125">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="47bf3-126">Procedura: Allineare un controllo ai bordi dei moduli</span><span class="sxs-lookup"><span data-stu-id="47bf3-126">How to: Align a Control to the Edges of Forms</span></span>](how-to-align-a-control-to-the-edges-of-forms.md)
- [<span data-ttu-id="47bf3-127">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando le guide di allineamento</span><span class="sxs-lookup"><span data-stu-id="47bf3-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="47bf3-128">Procedura: Agganciare i controlli in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="47bf3-128">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
- [<span data-ttu-id="47bf3-129">Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="47bf3-129">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="47bf3-130">Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="47bf3-130">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="47bf3-131">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="47bf3-131">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="47bf3-132">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="47bf3-132">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="47bf3-133">Sviluppo di controlli Windows Form in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="47bf3-133">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
