---
title: 'Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040452"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="33eec-102">Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="33eec-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="33eec-103">Il controllo <xref:System.Windows.Forms.TreeView> Windows Forms Visualizza una gerarchia di nodi, in modo analogo ai file e alle cartelle visualizzati nel riquadro sinistro della funzionalità Esplora risorse nei sistemi operativi Windows.</span><span class="sxs-lookup"><span data-stu-id="33eec-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="33eec-104">Impostando la <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire all'utente operazioni sensibili al contesto facendo clic con il pulsante destro del <xref:System.Windows.Forms.TreeView> mouse sul controllo.</span><span class="sxs-lookup"><span data-stu-id="33eec-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="33eec-105">Associando un <xref:System.Windows.Forms.ContextMenuStrip> componente a singoli <xref:System.Windows.Forms.TreeNode> elementi, è possibile aggiungere un livello personalizzato di funzionalità del menu di <xref:System.Windows.Forms.TreeView> scelta rapida ai controlli.</span><span class="sxs-lookup"><span data-stu-id="33eec-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="33eec-106">Per associare un menu di scelta rapida a un oggetto TreeNode in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="33eec-106">To associate a shortcut menu with a TreeNode at design time</span></span>

1. <span data-ttu-id="33eec-107">Aggiungere un <xref:System.Windows.Forms.TreeView> controllo al form e quindi aggiungere nodi <xref:System.Windows.Forms.TreeView> a in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="33eec-107">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="33eec-108">Per altre informazioni, vedere [Procedura: Aggiungere e rimuovere nodi con il controllo](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)TreeView Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="33eec-108">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>

2. <span data-ttu-id="33eec-109">Aggiungere un <xref:System.Windows.Forms.ContextMenuStrip> componente al form, quindi aggiungere voci di menu al menu di scelta rapida che rappresentano le operazioni a livello di nodo che si desidera rendere disponibili in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="33eec-109">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="33eec-110">Per altre informazioni, vedere [Procedura: Aggiungere voci di menu a un](how-to-add-menu-items-to-a-contextmenustrip.md)ContextMenuStrip.</span><span class="sxs-lookup"><span data-stu-id="33eec-110">For more information, see [How to: Add Menu Items to a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>

3. <span data-ttu-id="33eec-111">Riaprire la finestra di dialogo **Editor TreeNode** per <xref:System.Windows.Forms.TreeView> il controllo, selezionare il nodo da modificare e impostare la <xref:System.Windows.Forms.ContextMenuStrip> relativa proprietà sul menu di scelta rapida aggiunto.</span><span class="sxs-lookup"><span data-stu-id="33eec-111">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>

4. <span data-ttu-id="33eec-112">Quando questa proprietà è impostata, il menu di scelta rapida viene visualizzato quando si fa clic con il pulsante destro del mouse sul nodo.</span><span class="sxs-lookup"><span data-stu-id="33eec-112">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>

     <span data-ttu-id="33eec-113">Inoltre, sarà necessario scrivere il codice per gestire gli <xref:System.Windows.Forms.ToolStripItem.Click> eventi per queste voci di menu.</span><span class="sxs-lookup"><span data-stu-id="33eec-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>

## <a name="see-also"></a><span data-ttu-id="33eec-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33eec-114">See also</span></span>

- [<span data-ttu-id="33eec-115">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="33eec-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="33eec-116">Panoramica sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="33eec-116">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="33eec-117">Controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="33eec-117">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
