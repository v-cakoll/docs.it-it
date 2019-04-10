---
title: 'Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Forms'
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
ms.openlocfilehash: 4cbb5fbdb24790a7ddbce5c38060703c7ba7024a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59326892"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="611eb-102">Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="611eb-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="611eb-103">I moduli di Windows <xref:System.Windows.Forms.TreeView> controllo Archivia i nodi di primo livello nel relativo <xref:System.Windows.Forms.TreeView.Nodes%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="611eb-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="611eb-104">Ciascuna <xref:System.Windows.Forms.TreeNode> inoltre dispone di una propria <xref:System.Windows.Forms.TreeNode.Nodes%2A> raccolta per archiviare i relativi nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="611eb-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="611eb-105">Entrambe le proprietà della raccolta sono di tipo <xref:System.Windows.Forms.TreeNodeCollection>, che fornisce i membri della raccolta standard che consentono di aggiungere, rimuovere e ridisporre i nodi in un singolo livello della gerarchia di nodi.</span><span class="sxs-lookup"><span data-stu-id="611eb-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="611eb-106">Per aggiungere nodi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="611eb-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="611eb-107">Usare la <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> metodo della visualizzazione albero <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="611eb-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
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
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="611eb-108">Rimozione di nodi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="611eb-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="611eb-109">Usare la <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> metodo della visualizzazione albero <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà per rimuovere un singolo nodo, o <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> metodo per cancellare tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="611eb-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="611eb-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="611eb-110">See also</span></span>

- [<span data-ttu-id="611eb-111">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="611eb-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="611eb-112">Panoramica del controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="611eb-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="611eb-113">Procedura: Impostare icone per il controllo TreeView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="611eb-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="611eb-114">Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="611eb-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="611eb-115">Procedura: Individuare il nodo di TreeView scelto</span><span class="sxs-lookup"><span data-stu-id="611eb-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="611eb-116">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="611eb-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
