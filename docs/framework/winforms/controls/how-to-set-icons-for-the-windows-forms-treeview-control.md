---
title: Imposta icone per il controllo TreeView
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
ms.openlocfilehash: e3d7fc35c6d9f70822cdd0b69dd12f3d469f4ffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737268"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="ac1c7-102">Procedura: Impostare icone per il controllo TreeView Windows Form</span><span class="sxs-lookup"><span data-stu-id="ac1c7-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="ac1c7-103">Il controllo Windows Forms <xref:System.Windows.Forms.TreeView> può visualizzare le icone accanto a ogni nodo.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="ac1c7-104">Le icone vengono posizionate all'estrema sinistra del testo del nodo.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="ac1c7-105">Per visualizzare queste icone, è necessario associare la visualizzazione ad albero a un controllo <xref:System.Windows.Forms.ImageList>.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="ac1c7-106">Per altre informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [procedura: aggiungere o rimuovere immagini con il componente Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="ac1c7-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac1c7-107">Un bug in Microsoft .NET Framework versione 1,1 impedisce che le immagini vengano visualizzate nei nodi <xref:System.Windows.Forms.TreeView> quando l'applicazione chiama <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ac1c7-108">Per ovviare a questo bug, chiamare <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> nel metodo `Main` immediatamente dopo aver chiamato <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="ac1c7-109">Questo bug è stato risolto in .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-109">This bug is fixed in .NET Framework 2.0.</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="ac1c7-110">Per visualizzare le immagini in una visualizzazione albero</span><span class="sxs-lookup"><span data-stu-id="ac1c7-110">To display images in a tree view</span></span>  
  
1. <span data-ttu-id="ac1c7-111">Impostare la proprietà <xref:System.Windows.Forms.TreeView.ImageList%2A> del controllo <xref:System.Windows.Forms.TreeView> sul controllo <xref:System.Windows.Forms.ImageList> esistente che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="ac1c7-112">È possibile impostare queste proprietà nella finestra di progettazione con il Finestra Proprietà o nel codice.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. <span data-ttu-id="ac1c7-113">Impostare le proprietà <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> e <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> del nodo.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="ac1c7-114">La proprietà <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> determina l'immagine visualizzata per gli stati normali e espansi del nodo e la proprietà <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> determina l'immagine visualizzata per lo stato selezionato del nodo.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="ac1c7-115">Queste proprietà possono essere impostate nel codice o nell'editor di TreeNode.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="ac1c7-116">Per aprire l'Editor TreeNode, fare clic sul pulsante con i puntini di sospensione (![pulsante con i puntini di sospensione (...) nell'Finestra Proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) accanto alla proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A> nella Finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="ac1c7-116">To open the TreeNode Editor, click the ellipsis button ( ![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac1c7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac1c7-117">See also</span></span>

- [<span data-ttu-id="ac1c7-118">Panoramica sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="ac1c7-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="ac1c7-119">Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ac1c7-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="ac1c7-120">Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ac1c7-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="ac1c7-121">Procedura: Individuare il nodo di TreeView scelto</span><span class="sxs-lookup"><span data-stu-id="ac1c7-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="ac1c7-122">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="ac1c7-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
