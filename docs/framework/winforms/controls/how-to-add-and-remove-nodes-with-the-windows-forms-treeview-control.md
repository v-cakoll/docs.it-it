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
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Procedura: Aggiungere e rimuovere nodi tramite il controllo TreeView Windows Form
Il controllo Windows Forms <xref:System.Windows.Forms.TreeView> archivia i nodi di primo livello nella raccolta di <xref:System.Windows.Forms.TreeView.Nodes%2A>. Ogni <xref:System.Windows.Forms.TreeNode> dispone inoltre di una propria raccolta <xref:System.Windows.Forms.TreeNode.Nodes%2A> per archiviare i relativi nodi figlio. Entrambe le proprietà della raccolta sono di tipo <xref:System.Windows.Forms.TreeNodeCollection>, che fornisce membri della raccolta standard che consentono di aggiungere, rimuovere e ridisporre i nodi a un singolo livello della gerarchia del nodo.  
  
### <a name="to-add-nodes-programmatically"></a>Per aggiungere nodi a livello di codice  
  
1. Utilizzare il metodo <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> della proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A> della visualizzazione albero.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>Per rimuovere i nodi a livello di codice  
  
1. Usare il metodo <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> della proprietà <xref:System.Windows.Forms.TreeView.Nodes%2A> della visualizzazione albero per rimuovere un singolo nodo o il metodo <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> per cancellare tutti i nodi.  
  
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
