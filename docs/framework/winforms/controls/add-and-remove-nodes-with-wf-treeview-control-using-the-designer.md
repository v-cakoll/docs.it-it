---
title: 'Procedura: aggiungere e rimuovere nodi nel controllo TreeView Windows Form mediante la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 95f3f097d8e01828f2727bac742c752b656019e5
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2018
ms.locfileid: "45507823"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="c93d5-102">Procedura: aggiungere e rimuovere nodi nel controllo TreeView Windows Form mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="c93d5-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>
<span data-ttu-id="c93d5-103">Poiché il Windows Form <xref:System.Windows.Forms.TreeView> controllo consente di visualizzare i nodi in modo gerarchico, quando si aggiunge un nodo è necessario prestare attenzione a ciò che è il relativo nodo padre.</span><span class="sxs-lookup"><span data-stu-id="c93d5-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>  
  
 <span data-ttu-id="c93d5-104">La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.TreeView> controllo.</span><span class="sxs-lookup"><span data-stu-id="c93d5-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="c93d5-105">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto di applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c93d5-105">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c93d5-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="c93d5-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c93d5-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="c93d5-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c93d5-108">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c93d5-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="c93d5-109">Per aggiungere o rimuovere nodi nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="c93d5-109">To add or remove nodes in the designer</span></span>  
  
1.  <span data-ttu-id="c93d5-110">Selezionare il controllo <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="c93d5-110">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
2.  <span data-ttu-id="c93d5-111">Nel **delle proprietà** finestra, fare clic sul **puntini di sospensione** (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) accanto alla il <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="c93d5-111">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
     <span data-ttu-id="c93d5-112">Il **Editor objektu TreeNode** viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="c93d5-112">The **TreeNode Editor** appears.</span></span>  
  
3.  <span data-ttu-id="c93d5-113">Per aggiungere nodi, deve esistere un nodo radice; Se non ne esiste, è necessario aggiungere innanzitutto una radice facendo il **radice aggiungere** pulsante.</span><span class="sxs-lookup"><span data-stu-id="c93d5-113">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="c93d5-114">È quindi possibile aggiungere i nodi figlio, selezionando la radice o qualsiasi altro nodo e scegliendo il **Aggiungi figlio** pulsante.</span><span class="sxs-lookup"><span data-stu-id="c93d5-114">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>  
  
4.  <span data-ttu-id="c93d5-115">Per eliminare i nodi, selezionare il nodo da eliminare e quindi scegliere il **eliminare** pulsante.</span><span class="sxs-lookup"><span data-stu-id="c93d5-115">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93d5-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c93d5-116">See Also</span></span>  
 [<span data-ttu-id="c93d5-117">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="c93d5-117">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="c93d5-118">Panoramica sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="c93d5-118">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="c93d5-119">Procedura: Impostare icone per il controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c93d5-119">How to: Set Icons for the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="c93d5-120">Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c93d5-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [<span data-ttu-id="c93d5-121">Procedura: Individuare il nodo di TreeView scelto</span><span class="sxs-lookup"><span data-stu-id="c93d5-121">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [<span data-ttu-id="c93d5-122">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="c93d5-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
