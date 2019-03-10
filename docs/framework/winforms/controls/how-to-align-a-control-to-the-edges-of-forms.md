---
title: 'Procedura: Allineare un controllo ai bordi dei form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: 33a3b2e996bdab280eb7a4cd8ad7c59ccb1a1bd2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713891"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a><span data-ttu-id="8ff4d-102">Procedura: Allineare un controllo ai bordi dei form</span><span class="sxs-lookup"><span data-stu-id="8ff4d-102">How to: Align a Control to the Edges of Forms</span></span>
<span data-ttu-id="8ff4d-103">È possibile allineare un controllo al bordo dei form impostando la proprietà <xref:System.Windows.Forms.Control.Dock%2A></span><span class="sxs-lookup"><span data-stu-id="8ff4d-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="8ff4d-104">che designa la posizione del controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="8ff4d-105">La proprietà <xref:System.Windows.Forms.Control.Dock%2A> può essere impostata su uno dei valori riportati di seguito:</span><span class="sxs-lookup"><span data-stu-id="8ff4d-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="8ff4d-106">Impostazione</span><span class="sxs-lookup"><span data-stu-id="8ff4d-106">Setting</span></span>|<span data-ttu-id="8ff4d-107">Effetto sul controllo</span><span class="sxs-lookup"><span data-stu-id="8ff4d-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="8ff4d-108">Il controllo viene ancorato alla parte inferiore del form.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="8ff4d-109">Il controllo occupa tutto lo spazio rimanente nel form.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="8ff4d-110">Il controllo viene ancorato al lato sinistro del form.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="8ff4d-111">Il controllo non viene ancorato e viene visualizzato nella posizione specificata dalla relativa proprietà <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="8ff4d-112">Il controllo viene ancorato al lato destro del form.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="8ff4d-113">Il controllo viene ancorato alla parte superiore del form.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="8ff4d-114">È disponibile supporto in fase di progettazione per questa funzionalità in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-114">There is design-time support for this feature in Visual Studio.</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a><span data-ttu-id="8ff4d-115">Per impostare la proprietà Dock del controllo in fase di esecuzione</span><span class="sxs-lookup"><span data-stu-id="8ff4d-115">To set the Dock property for your control at run time</span></span>  
  
1.  <span data-ttu-id="8ff4d-116">Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> sul valore appropriato nel codice.</span><span class="sxs-lookup"><span data-stu-id="8ff4d-116">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to the appropriate value in code.</span></span>  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8ff4d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ff4d-117">See also</span></span>
- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8ff4d-118">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8ff4d-118">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="8ff4d-119">Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8ff4d-119">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="8ff4d-120">Procedura: Ancorare e agganciare controlli figlio in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="8ff4d-120">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="8ff4d-121">Panoramica sulla proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="8ff4d-121">AutoSize Property Overview</span></span>](autosize-property-overview.md)
