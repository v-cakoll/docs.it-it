---
title: 'Procedura: Nascondere ToolStripMenuItems usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 0e1cd7d1868adabd4d3eec9510f6ee567ba3867d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966621"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="4a867-102">Procedura: Nascondere ToolStripMenuItems usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="4a867-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="4a867-103">Nascondere le voci di menu consente di controllare l'interfaccia utente dell'applicazione e limitare i comandi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4a867-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="4a867-104">Spesso è necessario nascondere un intero menu quando tutte le voci di menu non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="4a867-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="4a867-105">Questa operazione presenta un minor numero di distrazioni per l'utente.</span><span class="sxs-lookup"><span data-stu-id="4a867-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="4a867-106">Inoltre, potrebbe essere necessario nascondere e disabilitare il menu o la voce di menu, perché nascondersi da solo non impedisce all'utente di accedere a un comando di menu utilizzando un tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="4a867-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="4a867-107">Per ulteriori informazioni sulla disabilitazione delle voci di menu [, vedere Procedura: Disabilitare ToolStripMenuItems usando la finestra](how-to-disable-toolstripmenuitems-using-the-designer.md)di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4a867-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="4a867-108">Per nascondere un menu di primo livello e le relative voci di sottomenu</span><span class="sxs-lookup"><span data-stu-id="4a867-108">To hide a top-level menu and its submenu items</span></span>

1. <span data-ttu-id="4a867-109">Selezionare la voce di menu di primo livello e impostare <xref:System.Windows.Forms.ToolStripItem.Visible%2A> la <xref:System.Windows.Forms.ToolStripItem.Available%2A> relativa proprietà `false`o su.</span><span class="sxs-lookup"><span data-stu-id="4a867-109">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>

     <span data-ttu-id="4a867-110">Quando si nasconde la voce di menu di primo livello, vengono nascoste anche tutte le voci di menu all'interno di tale menu.</span><span class="sxs-lookup"><span data-stu-id="4a867-110">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="4a867-111">Se si fa clic in un punto diverso <xref:System.Windows.Forms.MenuStrip> da dopo <xref:System.Windows.Forms.ToolStripItem.Visible%2A> l' `false`impostazione di su, l'intera voce di menu di primo livello e le relative voci di sottomenu scompariranno dal form, in modo da visualizzare l'effetto della fase di esecuzione dell'azione.</span><span class="sxs-lookup"><span data-stu-id="4a867-111">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="4a867-112">Per visualizzare la voce di menu di primo livello nascosta in fase di progettazione, fare <xref:System.Windows.Forms.MenuStrip> clic su nella **barra dei componenti**, nella struttura del **documento**o nella parte superiore della griglia delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="4a867-112">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>

> [!NOTE]
> <span data-ttu-id="4a867-113">Si nasconderà raramente un intero menu eccetto i menu figlio dell'interfaccia a documenti multipli (MDI) in uno scenario di Unione.</span><span class="sxs-lookup"><span data-stu-id="4a867-113">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>

## <a name="to-hide-a-submenu-item"></a><span data-ttu-id="4a867-114">Per nascondere una voce di sottomenu</span><span class="sxs-lookup"><span data-stu-id="4a867-114">To hide a submenu item</span></span>

1. <span data-ttu-id="4a867-115">Selezionare la voce di sottomenu e impostare <xref:System.Windows.Forms.ToolStripItem.Visible%2A> la relativa `false`proprietà su.</span><span class="sxs-lookup"><span data-stu-id="4a867-115">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>

     <span data-ttu-id="4a867-116">Quando si nasconde una voce di sottomenu, rimane visibile nel form in fase di progettazione in modo che sia possibile selezionarla facilmente per un ulteriore lavoro.</span><span class="sxs-lookup"><span data-stu-id="4a867-116">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="4a867-117">Che verrà nascosta in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a867-117">It will actually be hidden at run time.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a867-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a867-118">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="4a867-119">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="4a867-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="4a867-120">Procedura: Disabilitare ToolStripMenuItems usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="4a867-120">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
