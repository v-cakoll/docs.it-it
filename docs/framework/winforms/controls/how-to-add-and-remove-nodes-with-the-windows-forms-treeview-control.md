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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59326892"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Forms
I moduli di Windows <xref:System.Windows.Forms.TreeView> controllo Archivia i nodi di primo livello nel relativo <xref:System.Windows.Forms.TreeView.Nodes%2A> raccolta. Ciascuna <xref:System.Windows.Forms.TreeNode> inoltre dispone di una propria <xref:System.Windows.Forms.TreeNode.Nodes%2A> raccolta per archiviare i relativi nodi figlio. Entrambe le proprietà della raccolta sono di tipo <xref:System.Windows.Forms.TreeNodeCollection>, che fornisce i membri della raccolta standard che consentono di aggiungere, rimuovere e ridisporre i nodi in un singolo livello della gerarchia di nodi.  
  
### <a name="to-add-nodes-programmatically"></a>Per aggiungere nodi a livello di codice  
  
1. Usare la <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> metodo della visualizzazione albero <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>Rimozione di nodi a livello di codice  
  
1. Usare la <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> metodo della visualizzazione albero <xref:System.Windows.Forms.TreeView.Nodes%2A> proprietà per rimuovere un singolo nodo, o <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> metodo per cancellare tutti i nodi.  
  
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
- [Panoramica sul controllo TreeView](treeview-control-overview-windows-forms.md)
- [Procedura: Impostare icone per il controllo TreeView di Windows Form](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Procedura: Scorrere tutti i nodi di un controllo TreeView di Windows Form](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Procedura: Individuare il nodo di TreeView scelto](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
