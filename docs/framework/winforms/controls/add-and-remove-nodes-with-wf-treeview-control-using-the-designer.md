---
title: 'Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: ecf0b758a9c45a0354a68b6cbfecdb1c49ab390f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59322628"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="8b5f6-102">Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Forms usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="8b5f6-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>
<span data-ttu-id="8b5f6-103">Poiché il Windows Form <xref:System.Windows.Forms.TreeView> controllo consente di visualizzare i nodi in modo gerarchico, quando si aggiunge un nodo è necessario prestare attenzione a ciò che è il relativo nodo padre.</span><span class="sxs-lookup"><span data-stu-id="8b5f6-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>  
  
 <span data-ttu-id="8b5f6-104">La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.TreeView> controllo.</span><span class="sxs-lookup"><span data-stu-id="8b5f6-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="8b5f6-105">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="8b5f6-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b5f6-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="8b5f6-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8b5f6-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="8b5f6-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8b5f6-108">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="8b5f6-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="8b5f6-109">Per aggiungere o rimuovere nodi nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="8b5f6-109">To add or remove nodes in the designer</span></span>  
  
1. <span data-ttu-id="8b5f6-110">Selezionare il controllo <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="8b5f6-110">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
2. <span data-ttu-id="8b5f6-111">Nel **delle proprietà** finestra, fare clic sul **puntini di sospensione** (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) accanto alla il <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="8b5f6-111">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
     <span data-ttu-id="8b5f6-112">Il **Editor objektu TreeNode** viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="8b5f6-112">The **TreeNode Editor** appears.</span></span>  
  
3. <span data-ttu-id="8b5f6-113">Per aggiungere nodi, deve esistere un nodo radice; Se non ne esiste, è necessario aggiungere innanzitutto una radice facendo il **radice aggiungere** pulsante.</span><span class="sxs-lookup"><span data-stu-id="8b5f6-113">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="8b5f6-114">È quindi possibile aggiungere i nodi figlio, selezionando la radice o qualsiasi altro nodo e scegliendo il **Aggiungi figlio** pulsante.</span><span class="sxs-lookup"><span data-stu-id="8b5f6-114">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>  
  
4. <span data-ttu-id="8b5f6-115">Per eliminare i nodi, selezionare il nodo da eliminare e quindi scegliere il **eliminare** pulsante.</span><span class="sxs-lookup"><span data-stu-id="8b5f6-115">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b5f6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b5f6-116">See also</span></span>

- [<span data-ttu-id="8b5f6-117">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="8b5f6-117">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="8b5f6-118">Panoramica del controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="8b5f6-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="8b5f6-119">Procedura: Impostare icone per il controllo TreeView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b5f6-119">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="8b5f6-120">Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b5f6-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="8b5f6-121">Procedura: Individuare il nodo di TreeView scelto</span><span class="sxs-lookup"><span data-stu-id="8b5f6-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="8b5f6-122">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="8b5f6-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
