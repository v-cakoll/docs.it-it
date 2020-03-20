---
title: Aggiungere e rimuovere nodi con il controllo TreeViewAdd and Remove Nodes with TreeView Control
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
ms.openlocfilehash: f1e74e6d2f827167c32a6955b3010b59cb2f85b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142212"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="c073c-102">Procedura: aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c073c-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="c073c-103">Il controllo <xref:System.Windows.Forms.TreeView> Windows Form archivia i <xref:System.Windows.Forms.TreeView.Nodes%2A> nodi di primo livello nella relativa raccolta.</span><span class="sxs-lookup"><span data-stu-id="c073c-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="c073c-104">Ognuno <xref:System.Windows.Forms.TreeNode> ha <xref:System.Windows.Forms.TreeNode.Nodes%2A> anche la propria raccolta per archiviare i propri nodi figlio.</span><span class="sxs-lookup"><span data-stu-id="c073c-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="c073c-105">Entrambe le proprietà <xref:System.Windows.Forms.TreeNodeCollection>dell'insieme sono di tipo , che fornisce membri di raccolta standard che consentono di aggiungere, rimuovere e ridisporre i nodi a un singolo livello della gerarchia dei nodi.</span><span class="sxs-lookup"><span data-stu-id="c073c-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="c073c-106">Per aggiungere nodi a livello di codiceTo add nodes programmatically</span><span class="sxs-lookup"><span data-stu-id="c073c-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="c073c-107">Utilizzare <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> il metodo della proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A> della visualizzazione struttura ad albero.</span><span class="sxs-lookup"><span data-stu-id="c073c-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
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
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="c073c-108">Per rimuovere nodi a livello di codiceTo remove nodes programmatically</span><span class="sxs-lookup"><span data-stu-id="c073c-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="c073c-109">Utilizzare <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> il metodo della proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A> della visualizzazione struttura ad <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> albero per rimuovere un singolo nodo o il metodo per cancellare tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="c073c-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c073c-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c073c-110">See also</span></span>

- [<span data-ttu-id="c073c-111">Controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="c073c-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="c073c-112">Panoramica del controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="c073c-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="c073c-113">Procedura: impostare icone per il controllo TreeView Windows Form</span><span class="sxs-lookup"><span data-stu-id="c073c-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="c073c-114">Procedura: scorrere tutti i nodi di un controllo TreeView Windows Form</span><span class="sxs-lookup"><span data-stu-id="c073c-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="c073c-115">Procedura: individuare il nodo di TreeView scelto</span><span class="sxs-lookup"><span data-stu-id="c073c-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="c073c-116">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="c073c-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
