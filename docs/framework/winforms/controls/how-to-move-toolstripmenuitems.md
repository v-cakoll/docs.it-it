---
title: 'Procedura: Spostare i ToolStripMenuItems'
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: 50b5fd16780147ad7592035a901d993495dcb878
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708951"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="c6800-102">Procedura: Spostare i ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="c6800-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="c6800-103">In fase di progettazione, è possibile passare interi menu di primo livello e i relativi elementi in un'altra posizione di <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="c6800-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="c6800-104">È anche possibile spostare singole voci di menu tra menu di primo livello o modificare la posizione delle voci di menu all'interno di un menu.</span><span class="sxs-lookup"><span data-stu-id="c6800-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6800-105">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="c6800-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c6800-106">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c6800-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c6800-107">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c6800-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="c6800-108">Per spostare un menu di primo livello e le voci di menu in un'altra posizione di primo livello</span><span class="sxs-lookup"><span data-stu-id="c6800-108">To move a top-level menu and its menu items to another top-level location</span></span>  
  
1.  <span data-ttu-id="c6800-109">Fare clic e tenere premuto il pulsante sinistro del mouse sul menu da spostare.</span><span class="sxs-lookup"><span data-stu-id="c6800-109">Click and hold down the left mouse button on the menu that you want to move.</span></span>  
  
2.  <span data-ttu-id="c6800-110">Trascinare il punto di inserimento per il menu di primo livello che precede la nuova posizione e rilasciare il pulsante sinistro del mouse.</span><span class="sxs-lookup"><span data-stu-id="c6800-110">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>  
  
     <span data-ttu-id="c6800-111">Menu selezionato viene spostato a destra del punto di inserimento.</span><span class="sxs-lookup"><span data-stu-id="c6800-111">The selected menu moves to the right of the insertion point.</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="c6800-112">Per spostare un menu di primo livello e le voci di menu in un percorso di elenco a discesa</span><span class="sxs-lookup"><span data-stu-id="c6800-112">To move a top-level menu and its menu items to a drop-down location</span></span>  
  
1.  <span data-ttu-id="c6800-113">Fare clic sul menu che si desidera spostare e premere CTRL + X, o il menu di scelta rapida e selezionare **Taglia** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="c6800-113">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="c6800-114">Nel menu di primo livello di destinazione, fare clic sulla voce di menu precede la nuova posizione e premere CTRL + V, o la voce di menu precede la nuova posizione e scegliere **Incolla** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="c6800-114">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="c6800-115">Il menu che si taglia viene inserito dopo la voce di menu selezionata.</span><span class="sxs-lookup"><span data-stu-id="c6800-115">The menu that you cut is inserted after the selected menu item.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="c6800-116">Per spostare una voce di menu all'interno di un menu con l'Editor della raccolta Items</span><span class="sxs-lookup"><span data-stu-id="c6800-116">To move a menu item within a menu using the Items Collection Editor</span></span>  
  
1.  <span data-ttu-id="c6800-117">Menu di scelta rapida che contiene la voce di menu da spostare.</span><span class="sxs-lookup"><span data-stu-id="c6800-117">Right-click the menu that contains the menu item you want to move.</span></span>  
  
2.  <span data-ttu-id="c6800-118">Dal menu di scelta rapida, scegliere **Modifica DropDownItems**.</span><span class="sxs-lookup"><span data-stu-id="c6800-118">From the shortcut menu, choose **Edit DropDownItems**.</span></span>  
  
3.  <span data-ttu-id="c6800-119">Nel **Editor della raccolta Items**, fare clic sulla voce di menu da spostare.</span><span class="sxs-lookup"><span data-stu-id="c6800-119">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>  
  
4.  <span data-ttu-id="c6800-120">Fare clic sui tasti di direzione su e giù per spostare la voce di menu all'interno del menu.</span><span class="sxs-lookup"><span data-stu-id="c6800-120">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>  
  
5.  <span data-ttu-id="c6800-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6800-121">Click **OK**.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="c6800-122">Per spostare una voce di menu all'interno di un menu con la tastiera</span><span class="sxs-lookup"><span data-stu-id="c6800-122">To move a menu item within a menu using the keyboard</span></span>  
  
1.  <span data-ttu-id="c6800-123">Premere e tenere premuto il tasto ALT.</span><span class="sxs-lookup"><span data-stu-id="c6800-123">Press and hold down the ALT key.</span></span>  
  
2.  <span data-ttu-id="c6800-124">Fare clic e tenere premuto il pulsante sinistro del mouse sulla voce di menu che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="c6800-124">Click and hold the left mouse button on the menu item that you want to move.</span></span>  
  
3.  <span data-ttu-id="c6800-125">Trascinare la voce di menu al nuovo percorso e rilasciare il pulsante sinistro del mouse.</span><span class="sxs-lookup"><span data-stu-id="c6800-125">Drag the menu item to the new location and release the left mouse button.</span></span>  
  
### <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="c6800-126">Per spostare una voce di menu in un altro menu</span><span class="sxs-lookup"><span data-stu-id="c6800-126">To move a menu item to another menu</span></span>  
  
1.  <span data-ttu-id="c6800-127">Fare clic sulla voce di menu che si desidera spostare e premere CTRL + X, oppure fare doppio clic la voce di menu e scegliere **Taglia** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="c6800-127">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="c6800-128">Fare clic sul menu di scelta che conterrà la voce di menu che si taglia.</span><span class="sxs-lookup"><span data-stu-id="c6800-128">Left-click the menu that will contain the menu item that you cut.</span></span>  
  
3.  <span data-ttu-id="c6800-129">Fare clic sulla voce di menu che precede la nuova posizione e premere CTRL + V oppure fare clic sulla voce di menu che precede la nuova posizione e selezionare **Incolla** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="c6800-129">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="c6800-130">La voce di menu che si taglia viene inserita dopo la voce di menu selezionata.</span><span class="sxs-lookup"><span data-stu-id="c6800-130">The menu item that you cut is inserted after the selected menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6800-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6800-131">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="c6800-132">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="c6800-132">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
