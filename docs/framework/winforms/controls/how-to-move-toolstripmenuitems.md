---
title: 'Procedura: Spostare ToolStripMenuItems'
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
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039806"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="02809-102">Procedura: Spostare ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="02809-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="02809-103">In fase di progettazione è possibile spostare interi menu di primo livello e le voci di menu in una posizione diversa <xref:System.Windows.Forms.MenuStrip>in.</span><span class="sxs-lookup"><span data-stu-id="02809-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="02809-104">È anche possibile spostare singole voci di menu tra i menu di primo livello o modificare la posizione delle voci di menu all'interno di un menu.</span><span class="sxs-lookup"><span data-stu-id="02809-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="02809-105">Per spostare un menu di primo livello e le voci di menu in un'altra posizione di primo livello</span><span class="sxs-lookup"><span data-stu-id="02809-105">To move a top-level menu and its menu items to another top-level location</span></span>

1. <span data-ttu-id="02809-106">Fare clic e tenendo premuto il pulsante sinistro del mouse sul menu che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="02809-106">Click and hold down the left mouse button on the menu that you want to move.</span></span>

2. <span data-ttu-id="02809-107">Trascinare il punto di inserimento nel menu di primo livello che precede la nuova posizione desiderata e rilasciare il pulsante sinistro del mouse.</span><span class="sxs-lookup"><span data-stu-id="02809-107">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>

     <span data-ttu-id="02809-108">Il menu selezionato si sposta a destra del punto di inserimento.</span><span class="sxs-lookup"><span data-stu-id="02809-108">The selected menu moves to the right of the insertion point.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="02809-109">Per spostare un menu di primo livello e le voci di menu in un percorso a discesa</span><span class="sxs-lookup"><span data-stu-id="02809-109">To move a top-level menu and its menu items to a drop-down location</span></span>

1. <span data-ttu-id="02809-110">Fare clic sul menu che si desidera spostare e premere CTRL + X oppure fare clic con il pulsante destro del mouse sul menu e scegliere **taglia** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="02809-110">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="02809-111">Nel menu di primo livello di destinazione, fare clic sulla voce di menu sopra la nuova posizione desiderata e premere CTRL + V oppure fare clic con il pulsante destro del mouse sulla voce di menu sopra la nuova posizione desiderata e scegliere **Incolla** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="02809-111">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="02809-112">Il menu tagliato viene inserito dopo la voce di menu selezionata.</span><span class="sxs-lookup"><span data-stu-id="02809-112">The menu that you cut is inserted after the selected menu item.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="02809-113">Per spostare una voce di menu all'interno di un menu mediante l'editor della raccolta Items</span><span class="sxs-lookup"><span data-stu-id="02809-113">To move a menu item within a menu using the Items Collection Editor</span></span>

1. <span data-ttu-id="02809-114">Fare clic con il pulsante destro del mouse sul menu che contiene la voce di menu che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="02809-114">Right-click the menu that contains the menu item you want to move.</span></span>

2. <span data-ttu-id="02809-115">Dal menu di scelta rapida scegliere **Modifica DropDownItems**.</span><span class="sxs-lookup"><span data-stu-id="02809-115">From the shortcut menu, choose **Edit DropDownItems**.</span></span>

3. <span data-ttu-id="02809-116">Nell' **Editor della raccolta Items**, fare clic sulla voce di menu che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="02809-116">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>

4. <span data-ttu-id="02809-117">Fare clic sui tasti freccia su e giù per spostare la voce di menu nel menu.</span><span class="sxs-lookup"><span data-stu-id="02809-117">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>

5. <span data-ttu-id="02809-118">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="02809-118">Click **OK**.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="02809-119">Per spostare una voce di menu all'interno di un menu utilizzando la tastiera</span><span class="sxs-lookup"><span data-stu-id="02809-119">To move a menu item within a menu using the keyboard</span></span>

1. <span data-ttu-id="02809-120">Premere e tenere premuto il tasto ALT.</span><span class="sxs-lookup"><span data-stu-id="02809-120">Press and hold down the ALT key.</span></span>

2. <span data-ttu-id="02809-121">Fare clic e tenendo premuto il pulsante sinistro del mouse sulla voce di menu che si desidera spostare.</span><span class="sxs-lookup"><span data-stu-id="02809-121">Click and hold the left mouse button on the menu item that you want to move.</span></span>

3. <span data-ttu-id="02809-122">Trascinare la voce di menu nella nuova posizione e rilasciare il pulsante sinistro del mouse.</span><span class="sxs-lookup"><span data-stu-id="02809-122">Drag the menu item to the new location and release the left mouse button.</span></span>

## <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="02809-123">Per spostare una voce di menu in un altro menu</span><span class="sxs-lookup"><span data-stu-id="02809-123">To move a menu item to another menu</span></span>

1. <span data-ttu-id="02809-124">Fare clic sulla voce di menu che si desidera spostare e premere CTRL + X oppure fare clic con il pulsante destro del mouse sulla voce di menu e scegliere **taglia** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="02809-124">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="02809-125">Fare clic sul menu che conterrà la voce di menu tagliata.</span><span class="sxs-lookup"><span data-stu-id="02809-125">Left-click the menu that will contain the menu item that you cut.</span></span>

3. <span data-ttu-id="02809-126">Fare clic sulla voce di menu che precede la nuova posizione desiderata e premere CTRL + V oppure fare clic con il pulsante destro del mouse sulla voce di menu che precede la nuova posizione desiderata e selezionare **Incolla** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="02809-126">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="02809-127">La voce di menu tagliata viene inserita dopo la voce di menu selezionata.</span><span class="sxs-lookup"><span data-stu-id="02809-127">The menu item that you cut is inserted after the selected menu item.</span></span>

## <a name="see-also"></a><span data-ttu-id="02809-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02809-128">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="02809-129">Panoramica sul controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="02809-129">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
