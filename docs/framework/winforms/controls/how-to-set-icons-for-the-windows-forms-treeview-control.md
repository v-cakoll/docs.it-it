---
title: 'Procedura: Impostare icone per il controllo TreeView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: 515ff2bd4ab0f4fa93eada61396bd45c587cded6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703569"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="cdf8b-102">Procedura: Impostare icone per il controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cdf8b-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="cdf8b-103">I moduli di Windows <xref:System.Windows.Forms.TreeView> controllo può visualizzare le icone accanto a ogni nodo.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="cdf8b-104">Le icone vengono posizionate a sinistra del testo del nodo.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="cdf8b-105">Per visualizzare queste icone, è necessario associare la visualizzazione struttura ad albero con un <xref:System.Windows.Forms.ImageList> controllo.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="cdf8b-106">Per altre informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [come: Aggiungere o rimuovere immagini tramite il Windows Form componente ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="cdf8b-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cdf8b-107">Un bug in Microsoft .NET Framework versione 1.1 impedisce le immagini nei <xref:System.Windows.Forms.TreeView> nodi quando l'applicazione chiama <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cdf8b-108">Per risolvere questo errore, chiamare <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> nella `Main` metodo immediatamente dopo la chiamata <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="cdf8b-109">Questo bug è stato risolto in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cdf8b-109">This bug is fixed in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="cdf8b-110">Per visualizzare le immagini in una visualizzazione albero</span><span class="sxs-lookup"><span data-stu-id="cdf8b-110">To display images in a tree view</span></span>  
  
1.  <span data-ttu-id="cdf8b-111">Impostare il <xref:System.Windows.Forms.TreeView> del controllo <xref:System.Windows.Forms.TreeView.ImageList%2A> proprietà esistente <xref:System.Windows.Forms.ImageList> controllo da usare.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="cdf8b-112">Queste proprietà possono essere impostate nella finestra di progettazione con la finestra proprietà o nel codice.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  <span data-ttu-id="cdf8b-113">Impostare il nodo <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> e <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="cdf8b-114">Il <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> proprietà determina l'immagine visualizzata per gli stati di normale ed espanso del nodo e il <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> proprietà determina l'immagine visualizzata per lo stato del nodo selezionato.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="cdf8b-115">Queste proprietà possono essere impostate nel codice o tramite l'Editor TreeNode.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="cdf8b-116">Per aprire l'Editor objektu TreeNode, fare clic sui puntini di sospensione ( ![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) accanto al <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-116">To open the TreeNode Editor, click the ellipsis button ( ![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cdf8b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdf8b-117">See also</span></span>
- [<span data-ttu-id="cdf8b-118">Panoramica sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="cdf8b-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="cdf8b-119">Procedura: Aggiungere e rimuovere nodi con il controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cdf8b-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="cdf8b-120">Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cdf8b-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="cdf8b-121">Procedura: Individuare il nodo di TreeView scelto</span><span class="sxs-lookup"><span data-stu-id="cdf8b-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="cdf8b-122">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="cdf8b-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
