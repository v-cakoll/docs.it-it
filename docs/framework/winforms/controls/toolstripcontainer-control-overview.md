---
title: Cenni preliminari sul controllo ToolStripContainer
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: 59afb9de3a97545407fe96f5ded60faee9d9f725
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536341"
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="8bc86-102">Cenni preliminari sul controllo ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="8bc86-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="8bc86-103">Oggetto <xref:System.Windows.Forms.ToolStripContainer> contiene dei pannelli sui relativi sinistro, destro, superiore e inferiore per posizionare e raggruppare <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, e <xref:System.Windows.Forms.StatusStrip> controlli.</span><span class="sxs-lookup"><span data-stu-id="8bc86-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="8bc86-104">Più controlli <xref:System.Windows.Forms.ToolStrip> vengono raggruppati verticalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> di sinistra o di destra.</span><span class="sxs-lookup"><span data-stu-id="8bc86-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="8bc86-105">Vengono raggruppati orizzontalmente se li si inserisce nell'oggetto <xref:System.Windows.Forms.ToolStripContainer> in alto o in basso.</span><span class="sxs-lookup"><span data-stu-id="8bc86-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="8bc86-106">È possibile usare l'oggetto <xref:System.Windows.Forms.ToolStripContentPanel> centrale di <xref:System.Windows.Forms.ToolStripContainer> per posizionare i tradizionali controlli sul form.</span><span class="sxs-lookup"><span data-stu-id="8bc86-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="8bc86-107">Alcuni o tutti i controlli <xref:System.Windows.Forms.ToolStripContainer> sono direttamente selezionabili in fase di progettazione e possono essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="8bc86-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="8bc86-108">Ogni pannello di un <xref:System.Windows.Forms.ToolStripContainer> è espandibile e comprimibile e viene ridimensionato con i controlli in esso contenuti.</span><span class="sxs-lookup"><span data-stu-id="8bc86-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="8bc86-109">Membri importanti di ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="8bc86-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="8bc86-110">nome</span><span class="sxs-lookup"><span data-stu-id="8bc86-110">Name</span></span>|<span data-ttu-id="8bc86-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8bc86-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="8bc86-112">Ottiene il pannello inferiore del <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="8bc86-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="8bc86-113">Ottiene o imposta un valore che indica se il riquadro inferiore del <xref:System.Windows.Forms.ToolStripContainer> è visibile.</span><span class="sxs-lookup"><span data-stu-id="8bc86-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="8bc86-114">Ottiene il pannello di sinistra di <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="8bc86-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="8bc86-115">Ottiene o imposta un valore che indica se il riquadro sinistro del <xref:System.Windows.Forms.ToolStripContainer> è visibile.</span><span class="sxs-lookup"><span data-stu-id="8bc86-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="8bc86-116">Ottiene il pannello di destra la <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="8bc86-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="8bc86-117">Ottiene o imposta un valore che indica se il riquadro destro del <xref:System.Windows.Forms.ToolStripContainer> è visibile.</span><span class="sxs-lookup"><span data-stu-id="8bc86-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="8bc86-118">Ottiene il riquadro superiore del <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="8bc86-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="8bc86-119">Ottiene o imposta un valore che indica se il riquadro superiore del <xref:System.Windows.Forms.ToolStripContainer> è visibile.</span><span class="sxs-lookup"><span data-stu-id="8bc86-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8bc86-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bc86-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>
