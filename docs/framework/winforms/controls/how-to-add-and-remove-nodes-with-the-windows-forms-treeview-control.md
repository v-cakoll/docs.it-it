---
title: Aggiungere e rimuovere nodi con il controllo TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
ms.openlocfilehash: 02b3a7286798c6f2a6426e09c8fc6c18b74a6bf0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731955"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="45bd5-102">Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView Windows Form</span><span class="sxs-lookup"><span data-stu-id="45bd5-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="45bd5-103">Il controllo Windows Forms <xref:System.Windows.Forms.TreeView> archivia i nodi di primo livello nella raccolta di <xref:System.Windows.Forms.TreeView.Nodes%2A>.</span><span class="sxs-lookup"><span data-stu-id="45bd5-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="45bd5-104">Ogni <xref:System.Windows.Forms.TreeNode> dispone inoltre di una propria raccolta <xref:System.Windows.Forms.TreeNode.Nodes%2A> per archiviare i relativi nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="45bd5-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="45bd5-105">Entrambe le proprietà della raccolta sono di tipo <xref:System.Windows.Forms.TreeNodeCollection>, che fornisce membri della raccolta standard che consentono di aggiungere, rimuovere e ridisporre i nodi a un singolo livello della gerarchia del nodo.</span><span class="sxs-lookup"><span data-stu-id="45bd5-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="45bd5-106">Per aggiungere nodi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="45bd5-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="45bd5-107">Utilizzare il metodo <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> della proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A> della visualizzazione albero.</span><span class="sxs-lookup"><span data-stu-id="45bd5-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="45bd5-108">Per rimuovere i nodi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="45bd5-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="45bd5-109">Usare il metodo <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> della proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A> della visualizzazione albero per rimuovere un singolo nodo o il metodo <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> per cancellare tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="45bd5-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing   
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="45bd5-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45bd5-110">See also</span></span>

- [<span data-ttu-id="45bd5-111">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="45bd5-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="45bd5-112">Panoramica sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="45bd5-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="45bd5-113">Procedura: Impostare icone per il controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="45bd5-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="45bd5-114">Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="45bd5-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="45bd5-115">Procedura: Individuare il nodo di TreeView scelto</span><span class="sxs-lookup"><span data-stu-id="45bd5-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="45bd5-116">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="45bd5-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
