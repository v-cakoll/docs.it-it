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
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Procedura: aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Form
Il controllo <xref:System.Windows.Forms.TreeView> Windows Form archivia i <xref:System.Windows.Forms.TreeView.Nodes%2A> nodi di primo livello nella relativa raccolta. Ognuno <xref:System.Windows.Forms.TreeNode> ha <xref:System.Windows.Forms.TreeNode.Nodes%2A> anche la propria raccolta per archiviare i propri nodi figlio. Entrambe le proprietà <xref:System.Windows.Forms.TreeNodeCollection>dell'insieme sono di tipo , che fornisce membri di raccolta standard che consentono di aggiungere, rimuovere e ridisporre i nodi a un singolo livello della gerarchia dei nodi.  
  
### <a name="to-add-nodes-programmatically"></a>Per aggiungere nodi a livello di codiceTo add nodes programmatically  
  
1. Utilizzare <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> il metodo della proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A> della visualizzazione struttura ad albero.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>Per rimuovere nodi a livello di codiceTo remove nodes programmatically  
  
1. Utilizzare <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> il metodo della proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A> della visualizzazione struttura ad <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> albero per rimuovere un singolo nodo o il metodo per cancellare tutti i nodi.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Controllo TreeView](treeview-control-windows-forms.md)
- [Panoramica del controllo TreeView](treeview-control-overview-windows-forms.md)
- [Procedura: impostare icone per il controllo TreeView Windows Form](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Procedura: scorrere tutti i nodi di un controllo TreeView Windows Form](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Procedura: individuare il nodo di TreeView scelto](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
