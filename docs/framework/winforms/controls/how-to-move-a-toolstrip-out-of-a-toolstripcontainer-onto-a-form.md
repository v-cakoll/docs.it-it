---
title: 'Procedura: spostare ToolStrip da ToolStripContainer a un form'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 6cc54264033eca541ce845b75d608087fee8a542
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532329"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="2477e-102">Procedura: spostare ToolStrip da ToolStripContainer a un form</span><span class="sxs-lookup"><span data-stu-id="2477e-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="2477e-103">Utilizzare la procedura seguente per spostare un <xref:System.Windows.Forms.ToolStrip> da un <xref:System.Windows.Forms.ToolStripContainer> in un form.</span><span class="sxs-lookup"><span data-stu-id="2477e-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2477e-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="2477e-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2477e-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="2477e-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2477e-106">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="2477e-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="2477e-107">Per spostare ToolStrip da ToolStripContainer a un form</span><span class="sxs-lookup"><span data-stu-id="2477e-107">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>  
  
1.  <span data-ttu-id="2477e-108">Selezionare <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="2477e-108">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
2.  <span data-ttu-id="2477e-109">Taglia il <xref:System.Windows.Forms.ToolStrip> premendo CTRL + X o destro di <xref:System.Windows.Forms.ToolStrip> e scegliere **Taglia** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="2477e-109">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>  
  
3.  <span data-ttu-id="2477e-110">Selezionare il form.</span><span class="sxs-lookup"><span data-stu-id="2477e-110">Select the form.</span></span>  
  
4.  <span data-ttu-id="2477e-111">Incolla il <xref:System.Windows.Forms.ToolStrip> premendo CTRL + V oppure scegliere **Incolla** dal **modifica** menu.</span><span class="sxs-lookup"><span data-stu-id="2477e-111">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>  
  
5.  <span data-ttu-id="2477e-112">Impostare il <xref:System.Windows.Forms.ToolStrip.Dock%2A> proprietà del <xref:System.Windows.Forms.ToolStrip> a **Top**.</span><span class="sxs-lookup"><span data-stu-id="2477e-112">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2477e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2477e-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [<span data-ttu-id="2477e-114">Panoramica sul controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="2477e-114">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
