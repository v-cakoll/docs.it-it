---
title: 'Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ab73f6e4dc6a4e348853183046db564e748360b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="f1b73-102">Procedura: Associare un menu di scelta rapida a un TreeNode usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="f1b73-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="f1b73-103">Windows Form <xref:System.Windows.Forms.TreeView> controllo Visualizza una gerarchia di nodi, simile ai file e cartelle vengono visualizzati nel riquadro sinistro della funzionalità Esplora risorse nei sistemi operativi Windows.</span><span class="sxs-lookup"><span data-stu-id="f1b73-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="f1b73-104">Impostando il <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà, è possibile fornire operazioni sensibili al contesto per l'utente quando sono destro la <xref:System.Windows.Forms.TreeView> controllo.</span><span class="sxs-lookup"><span data-stu-id="f1b73-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="f1b73-105">Associando un <xref:System.Windows.Forms.ContextMenuStrip> componente con singoli <xref:System.Windows.Forms.TreeNode> elementi, è possibile aggiungere un livello di funzionalità del menu di scelta rapida per personalizzato il <xref:System.Windows.Forms.TreeView> controlli.</span><span class="sxs-lookup"><span data-stu-id="f1b73-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1b73-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="f1b73-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f1b73-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="f1b73-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f1b73-108">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f1b73-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="f1b73-109">Per associare un menu di scelta rapida a un TreeNode in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="f1b73-109">To associate a shortcut menu with a TreeNode at design time</span></span>  
  
1.  <span data-ttu-id="f1b73-110">Aggiungere un <xref:System.Windows.Forms.TreeView> il controllo al form e quindi aggiungere i nodi per il <xref:System.Windows.Forms.TreeView> in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="f1b73-110">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="f1b73-111">Per ulteriori informazioni, vedere [procedura: aggiungere e rimuovere nodi con il controllo TreeView Windows Form](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span><span class="sxs-lookup"><span data-stu-id="f1b73-111">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>  
  
2.  <span data-ttu-id="f1b73-112">Aggiungere un <xref:System.Windows.Forms.ContextMenuStrip> componente al form, quindi aggiungere le voci di menu al menu di scelta rapida che rappresentano le operazioni a livello di nodo che si desidera rendere disponibili in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f1b73-112">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="f1b73-113">Per ulteriori informazioni, vedere [procedura: aggiungere voci di Menu a un ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).</span><span class="sxs-lookup"><span data-stu-id="f1b73-113">For more information, see [How to: Add Menu Items to a ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>  
  
3.  <span data-ttu-id="f1b73-114">Riaprire il **Editor TreeNode** la finestra di dialogo per la <xref:System.Windows.Forms.TreeView> di controllo, selezionare il nodo da modificare e impostare il relativo <xref:System.Windows.Forms.ContextMenuStrip> proprietà per il menu di scelta rapida che è stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="f1b73-114">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>  
  
4.  <span data-ttu-id="f1b73-115">Quando questa proprietà è impostata, verrà visualizzato il menu di scelta rapida si fa clic con il pulsante destro del nodo.</span><span class="sxs-lookup"><span data-stu-id="f1b73-115">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
     <span data-ttu-id="f1b73-116">Inoltre, è possibile scrivere codice per gestire il <xref:System.Windows.Forms.ToolStripItem.Click> gli eventi per queste voci di menu.</span><span class="sxs-lookup"><span data-stu-id="f1b73-116">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b73-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1b73-117">See Also</span></span>  
 [<span data-ttu-id="f1b73-118">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="f1b73-118">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="f1b73-119">Panoramica sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="f1b73-119">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="f1b73-120">Controllo ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="f1b73-120">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
