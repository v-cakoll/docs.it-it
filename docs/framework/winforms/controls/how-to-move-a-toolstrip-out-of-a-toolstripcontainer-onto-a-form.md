---
title: 'Procedura: Spostare ToolStrip da ToolStripContainer a un modulo'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
ms.openlocfilehash: 100e744e6e49fbf214488e9bbb796b5b6fb9591a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142363"
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="f1a91-102">Procedura: Spostare ToolStrip da ToolStripContainer a un modulo</span><span class="sxs-lookup"><span data-stu-id="f1a91-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="f1a91-103">Usare la procedura seguente per spostare un <xref:System.Windows.Forms.ToolStrip> fuori un <xref:System.Windows.Forms.ToolStripContainer> in un form.</span><span class="sxs-lookup"><span data-stu-id="f1a91-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1a91-104">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="f1a91-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f1a91-105">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="f1a91-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f1a91-106">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f1a91-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="f1a91-107">Per spostare un controllo ToolStrip da ToolStripContainer a un form</span><span class="sxs-lookup"><span data-stu-id="f1a91-107">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>  
  
1.  <span data-ttu-id="f1a91-108">Selezionare <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="f1a91-108">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
2.  <span data-ttu-id="f1a91-109">Taglia il <xref:System.Windows.Forms.ToolStrip> premendo CTRL + X o fare doppio clic il <xref:System.Windows.Forms.ToolStrip> e scegliere **Taglia** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f1a91-109">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>  
  
3.  <span data-ttu-id="f1a91-110">Selezionare il form.</span><span class="sxs-lookup"><span data-stu-id="f1a91-110">Select the form.</span></span>  
  
4.  <span data-ttu-id="f1a91-111">Incollare il <xref:System.Windows.Forms.ToolStrip> premendo CTRL + V oppure scegliere **incollare** dal **modifica** menu.</span><span class="sxs-lookup"><span data-stu-id="f1a91-111">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>  
  
5.  <span data-ttu-id="f1a91-112">Impostare il <xref:System.Windows.Forms.ToolStrip.Dock%2A> proprietà del <xref:System.Windows.Forms.ToolStrip> al **Top**.</span><span class="sxs-lookup"><span data-stu-id="f1a91-112">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a91-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1a91-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripContainer>
- [<span data-ttu-id="f1a91-114">Panoramica del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="f1a91-114">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
